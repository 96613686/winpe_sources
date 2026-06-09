# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180004018`
- end: `0x1800040ad`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `149`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003f44`

## callees

- `0x180004018`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000403d`
- `KERNEL32!GetProcessHeap` at `0x18000407a`
- `KERNEL32!GetProcessHeap` at `0x18000403d`
- `KERNEL32!GetProcessHeap` at `0x18000407a`
- `KERNEL32!HeapFree` at `0x180004051`
- `KERNEL32!HeapFree` at `0x18000408e`
- `KERNEL32!HeapFree` at `0x180004051`
- `KERNEL32!HeapFree` at `0x18000408e`

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
0x180004018  push    rbx
0x18000401a  push    rbp
0x18000401b  push    rsi
0x18000401c  push    rdi
0x18000401d  sub     rsp, 28h
0x180004021  movzx   eax, word ptr [rcx+20h]
0x180004025  mov     rsi, rcx
0x180004028  mov     rdi, [rcx+18h]
0x18000402c  lea     rbp, [rax+rax*4]
0x180004030  shl     rbp, 4
0x180004034  add     rbp, rdi
0x180004037  jmp     short loc_180004071
0x180004039  mov     rbx, [rdi+40h]
0x18000403d  call    cs:__imp_GetProcessHeap
0x180004044  nop     dword ptr [rax+rax+00h]
0x180004049  mov     r8, rbx; lpMem
0x18000404c  xor     edx, edx; dwFlags
0x18000404e  mov     rcx, rax; hHeap
0x180004051  call    cs:__imp_HeapFree
0x180004058  nop     dword ptr [rax+rax+00h]
0x18000405d  mov     qword ptr [rdi+40h], 0
0x180004065  mov     qword ptr [rdi+48h], 0
0x18000406d  add     rdi, 50h ; 'P'
0x180004071  cmp     rdi, rbp
0x180004074  jnz     short loc_180004039
0x180004076  mov     rbx, [rsi+18h]
0x18000407a  call    cs:__imp_GetProcessHeap
0x180004081  nop     dword ptr [rax+rax+00h]
0x180004086  mov     r8, rbx; lpMem
0x180004089  xor     edx, edx; dwFlags
0x18000408b  mov     rcx, rax; hHeap
0x18000408e  call    cs:__imp_HeapFree
0x180004095  nop     dword ptr [rax+rax+00h]
0x18000409a  xor     eax, eax
0x18000409c  mov     [rsi+20h], eax
0x18000409f  mov     [rsi+18h], rax
0x1800040a3  add     rsp, 28h
0x1800040a7  pop     rdi
0x1800040a8  pop     rsi
0x1800040a9  pop     rbp
0x1800040aa  pop     rbx
0x1800040ab  retn
```
