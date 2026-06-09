# ResolverData::Free(void)

- ea: `0x180004fa0`
- end: `0x180005017`
- name: `?Free@ResolverData@@QEAAXXZ`
- size: `119`
- prototype: `void __fastcall(ResolverData *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800036f0`
- `0x180003ac8`
- `0x180005410`

## callees

- `0x180004fa0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180004fc3`
- `KERNEL32!HeapFree` at `0x180004fe7`
- `KERNEL32!HeapFree` at `0x180004fc3`
- `KERNEL32!HeapFree` at `0x180004fe7`
- `KERNEL32!GetProcessHeap` at `0x180004fb5`
- `KERNEL32!GetProcessHeap` at `0x180004fd9`
- `KERNEL32!GetProcessHeap` at `0x180004fb5`
- `KERNEL32!GetProcessHeap` at `0x180004fd9`

## pseudocode

```c
void __fastcall ResolverData::Free(ResolverData *this)
{
  void *v1; // rdi
  HANDLE ProcessHeap; // rax
  void *v4; // rdi
  HANDLE v5; // rax

  v1 = *(void **)this;
  if ( *(_QWORD *)this )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
    *(_QWORD *)this = 0;
  }
  v4 = (void *)*((_QWORD *)this + 1);
  if ( v4 )
  {
    v5 = GetProcessHeap();
    HeapFree(v5, 0, v4);
    *((_QWORD *)this + 1) = 0;
  }
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_DWORD *)this + 8) = 0;
}

```

## disassembly

```asm
0x180004fa0  mov     [rsp+arg_0], rbx
0x180004fa5  push    rdi
0x180004fa6  sub     rsp, 20h
0x180004faa  mov     rdi, [rcx]
0x180004fad  mov     rbx, rcx
0x180004fb0  test    rdi, rdi
0x180004fb3  jz      short loc_180004FD0
0x180004fb5  call    cs:__imp_GetProcessHeap
0x180004fbb  mov     r8, rdi; lpMem
0x180004fbe  xor     edx, edx; dwFlags
0x180004fc0  mov     rcx, rax; hHeap
0x180004fc3  call    cs:__imp_HeapFree
0x180004fc9  mov     qword ptr [rbx], 0
0x180004fd0  mov     rdi, [rbx+8]
0x180004fd4  test    rdi, rdi
0x180004fd7  jz      short loc_180004FF5
0x180004fd9  call    cs:__imp_GetProcessHeap
0x180004fdf  mov     r8, rdi; lpMem
0x180004fe2  xor     edx, edx; dwFlags
0x180004fe4  mov     rcx, rax; hHeap
0x180004fe7  call    cs:__imp_HeapFree
0x180004fed  mov     qword ptr [rbx+8], 0
0x180004ff5  mov     qword ptr [rbx+10h], 0
0x180004ffd  mov     qword ptr [rbx+18h], 0
0x180005005  mov     dword ptr [rbx+20h], 0
0x18000500c  mov     rbx, [rsp+28h+arg_0]
0x180005011  add     rsp, 20h
0x180005015  pop     rdi
0x180005016  retn
```
