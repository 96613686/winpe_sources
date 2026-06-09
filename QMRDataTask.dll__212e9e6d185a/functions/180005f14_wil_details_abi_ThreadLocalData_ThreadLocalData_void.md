# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180005f14`
- end: `0x180005f90`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800056d4`

## callees

- `0x180005f14`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180005f39`
- `KERNEL32!GetProcessHeap` at `0x180005f6a`
- `KERNEL32!GetProcessHeap` at `0x180005f39`
- `KERNEL32!GetProcessHeap` at `0x180005f6a`
- `KERNEL32!HeapFree` at `0x180005f47`
- `KERNEL32!HeapFree` at `0x180005f78`
- `KERNEL32!HeapFree` at `0x180005f47`
- `KERNEL32!HeapFree` at `0x180005f78`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::~ThreadLocalData(wil::details_abi::ThreadLocalData *this)
{
  __int64 v2; // rdi
  __int64 v3; // rbp
  void *v4; // rbx
  HANDLE ProcessHeap; // rax
  void *v6; // rbx
  HANDLE v7; // rax

  v2 = *((_QWORD *)this + 3);
  v3 = v2 + 80LL * *((unsigned __int16 *)this + 16);
  while ( v2 != v3 )
  {
    v4 = *(void **)(v2 + 64);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
    *(_QWORD *)(v2 + 64) = 0;
    *(_QWORD *)(v2 + 72) = 0;
    v2 += 80;
  }
  v6 = (void *)*((_QWORD *)this + 3);
  v7 = GetProcessHeap();
  HeapFree(v7, 0, v6);
  *((_DWORD *)this + 8) = 0;
  *((_QWORD *)this + 3) = 0;
}

```

## disassembly

```asm
0x180005f14  push    rbx
0x180005f16  push    rbp
0x180005f17  push    rsi
0x180005f18  push    rdi
0x180005f19  sub     rsp, 28h
0x180005f1d  movzx   eax, word ptr [rcx+20h]
0x180005f21  mov     rsi, rcx
0x180005f24  mov     rdi, [rcx+18h]
0x180005f28  lea     rbp, [rax+rax*4]
0x180005f2c  shl     rbp, 4
0x180005f30  add     rbp, rdi
0x180005f33  jmp     short loc_180005F61
0x180005f35  mov     rbx, [rdi+40h]
0x180005f39  call    cs:__imp_GetProcessHeap
0x180005f3f  mov     r8, rbx; lpMem
0x180005f42  xor     edx, edx; dwFlags
0x180005f44  mov     rcx, rax; hHeap
0x180005f47  call    cs:__imp_HeapFree
0x180005f4d  mov     qword ptr [rdi+40h], 0
0x180005f55  mov     qword ptr [rdi+48h], 0
0x180005f5d  add     rdi, 50h ; 'P'
0x180005f61  cmp     rdi, rbp
0x180005f64  jnz     short loc_180005F35
0x180005f66  mov     rbx, [rsi+18h]
0x180005f6a  call    cs:__imp_GetProcessHeap
0x180005f70  mov     r8, rbx; lpMem
0x180005f73  xor     edx, edx; dwFlags
0x180005f75  mov     rcx, rax; hHeap
0x180005f78  call    cs:__imp_HeapFree
0x180005f7e  xor     eax, eax
0x180005f80  mov     [rsi+20h], eax
0x180005f83  mov     [rsi+18h], rax
0x180005f87  add     rsp, 28h
0x180005f8b  pop     rdi
0x180005f8c  pop     rsi
0x180005f8d  pop     rbp
0x180005f8e  pop     rbx
0x180005f8f  retn
```
