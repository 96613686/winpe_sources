# CreateTlgAggregateSession

- ea: `0x180016cb0`
- end: `0x180016d6d`
- name: `CreateTlgAggregateSession`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800169f0`

## callees

- `0x180016cb0`
- `0x180016d74`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180016cf8`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180016cf8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016cde`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016cde`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016cca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016cca`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180016d1a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180016d1a`

## pseudocode

```c
RTL_SRWLOCK *__fastcall CreateTlgAggregateSession(char a1)
{
  char v2; // di
  HANDLE ProcessHeap; // rax
  RTL_SRWLOCK *v4; // rax
  RTL_SRWLOCK *v5; // rbx

  v2 = 0;
  ProcessHeap = GetProcessHeap();
  v4 = (RTL_SRWLOCK *)HeapAlloc(ProcessHeap, 8u, 0x168u);
  v5 = v4;
  if ( v4 )
  {
    InitializeSRWLock(v4 + 33);
    if ( !a1 || !dword_180098118 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
      v2 = 1;
  }
  if ( !v2 )
  {
    DestroyAggregateSession(v5);
    return 0;
  }
  return v5;
}

```

## disassembly

```asm
0x180016cb0  mov     [rsp+arg_0], rbx
0x180016cb5  mov     [rsp+arg_18], rsi
0x180016cba  push    rdi
0x180016cbb  sub     rsp, 20h
0x180016cbf  mov     sil, cl
0x180016cc2  xor     dil, dil
0x180016cc5  mov     [rsp+28h+arg_8], dil
0x180016cca  call    cs:__imp_GetProcessHeap
0x180016cd0  mov     rcx, rax; hHeap
0x180016cd3  mov     edx, 8; dwFlags
0x180016cd8  mov     r8d, 168h; dwBytes
0x180016cde  call    cs:__imp_HeapAlloc
0x180016ce4  mov     rbx, rax
0x180016ce7  mov     [rsp+28h+arg_10], rax
0x180016cec  test    rax, rax
0x180016cef  jz      short loc_180016D4B
0x180016cf1  lea     rcx, [rax+108h]; SRWLock
0x180016cf8  call    cs:__imp_InitializeSRWLock
0x180016cfe  test    sil, sil
0x180016d01  jz      short loc_180016D48
0x180016d03  mov     ecx, cs:dword_180098118
0x180016d09  test    ecx, ecx
0x180016d0b  jnz     short loc_180016D4B
0x180016d0d  xor     r8d, r8d; pcbe
0x180016d10  mov     rdx, rbx; pv
0x180016d13  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x180016d1a  call    cs:__imp_CreateThreadpoolTimer
0x180016d20  mov     [rbx+158h], rax
0x180016d27  jmp     short loc_180016D3E
0x180016d29  mov     eax, 1
0x180016d2e  xchg    eax, cs:dword_180098118
0x180016d34  mov     dil, [rsp+28h+arg_8]
0x180016d39  mov     rbx, [rsp+28h+arg_10]
0x180016d3e  cmp     qword ptr [rbx+158h], 0
0x180016d46  jz      short loc_180016D4B
0x180016d48  mov     dil, 1
0x180016d4b  test    dil, dil
0x180016d4e  jnz     short loc_180016D5A
0x180016d50  mov     rcx, rbx; lpMem
0x180016d53  call    DestroyAggregateSession
0x180016d58  xor     ebx, ebx
0x180016d5a  mov     rax, rbx
0x180016d5d  mov     rbx, [rsp+28h+arg_0]
0x180016d62  mov     rsi, [rsp+28h+arg_18]
0x180016d67  add     rsp, 20h
0x180016d6b  pop     rdi
0x180016d6c  retn
0x18005b9ae  push    rbp
0x18005b9b0  sub     rsp, 20h
0x18005b9b4  mov     rbp, rdx
0x18005b9b7  mov     rax, [rcx]
0x18005b9ba  xor     ecx, ecx
0x18005b9bc  cmp     dword ptr [rax], 0C000000Dh
0x18005b9c2  setz    cl
0x18005b9c5  mov     eax, ecx
0x18005b9c7  add     rsp, 20h
0x18005b9cb  pop     rbp
0x18005b9cc  retn
```
