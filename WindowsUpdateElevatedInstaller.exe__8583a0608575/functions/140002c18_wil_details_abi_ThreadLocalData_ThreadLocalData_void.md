# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x140002c18`
- end: `0x140002c94`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140002a60`

## callees

- `0x140002c18`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140002c4b`
- `KERNEL32!HeapFree` at `0x140002c7c`
- `KERNEL32!HeapFree` at `0x140002c4b`
- `KERNEL32!HeapFree` at `0x140002c7c`
- `KERNEL32!GetProcessHeap` at `0x140002c3d`
- `KERNEL32!GetProcessHeap` at `0x140002c6e`
- `KERNEL32!GetProcessHeap` at `0x140002c3d`
- `KERNEL32!GetProcessHeap` at `0x140002c6e`

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
0x140002c18  push    rbx
0x140002c1a  push    rbp
0x140002c1b  push    rsi
0x140002c1c  push    rdi
0x140002c1d  sub     rsp, 28h
0x140002c21  movzx   eax, word ptr [rcx+20h]
0x140002c25  mov     rsi, rcx
0x140002c28  mov     rdi, [rcx+18h]
0x140002c2c  lea     rbp, [rax+rax*4]
0x140002c30  shl     rbp, 4
0x140002c34  add     rbp, rdi
0x140002c37  jmp     short loc_140002C65
0x140002c39  mov     rbx, [rdi+40h]
0x140002c3d  call    cs:__imp_GetProcessHeap
0x140002c43  mov     r8, rbx; lpMem
0x140002c46  xor     edx, edx; dwFlags
0x140002c48  mov     rcx, rax; hHeap
0x140002c4b  call    cs:__imp_HeapFree
0x140002c51  mov     qword ptr [rdi+40h], 0
0x140002c59  mov     qword ptr [rdi+48h], 0
0x140002c61  add     rdi, 50h ; 'P'
0x140002c65  cmp     rdi, rbp
0x140002c68  jnz     short loc_140002C39
0x140002c6a  mov     rbx, [rsi+18h]
0x140002c6e  call    cs:__imp_GetProcessHeap
0x140002c74  mov     r8, rbx; lpMem
0x140002c77  xor     edx, edx; dwFlags
0x140002c79  mov     rcx, rax; hHeap
0x140002c7c  call    cs:__imp_HeapFree
0x140002c82  xor     eax, eax
0x140002c84  mov     [rsi+20h], eax
0x140002c87  mov     [rsi+18h], rax
0x140002c8b  add     rsp, 28h
0x140002c8f  pop     rdi
0x140002c90  pop     rsi
0x140002c91  pop     rbp
0x140002c92  pop     rbx
0x140002c93  retn
```
