# CreateTlgAggregateSession

- ea: `0x180072754`
- end: `0x180072811`
- name: `CreateTlgAggregateSession`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180073350`

## callees

- `0x180072754`
- `0x180072818`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18007279c`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18007279c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180072782`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180072782`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007276e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007276e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800727be`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800727be`

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
    if ( !a1 || !dword_1800B2D48 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x180072754  mov     [rsp+arg_0], rbx
0x180072759  mov     [rsp+arg_18], rsi
0x18007275e  push    rdi
0x18007275f  sub     rsp, 20h
0x180072763  mov     sil, cl
0x180072766  xor     dil, dil
0x180072769  mov     [rsp+28h+arg_8], dil
0x18007276e  call    cs:__imp_GetProcessHeap
0x180072774  mov     rcx, rax; hHeap
0x180072777  mov     edx, 8; dwFlags
0x18007277c  mov     r8d, 168h; dwBytes
0x180072782  call    cs:__imp_HeapAlloc
0x180072788  mov     rbx, rax
0x18007278b  mov     [rsp+28h+arg_10], rax
0x180072790  test    rax, rax
0x180072793  jz      short loc_1800727EF
0x180072795  lea     rcx, [rax+108h]; SRWLock
0x18007279c  call    cs:__imp_InitializeSRWLock
0x1800727a2  test    sil, sil
0x1800727a5  jz      short loc_1800727EC
0x1800727a7  mov     ecx, cs:dword_1800B2D48
0x1800727ad  test    ecx, ecx
0x1800727af  jnz     short loc_1800727EF
0x1800727b1  xor     r8d, r8d; pcbe
0x1800727b4  mov     rdx, rbx; pv
0x1800727b7  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x1800727be  call    cs:__imp_CreateThreadpoolTimer
0x1800727c4  mov     [rbx+158h], rax
0x1800727cb  jmp     short loc_1800727E2
0x1800727cd  mov     eax, 1
0x1800727d2  xchg    eax, cs:dword_1800B2D48
0x1800727d8  mov     dil, [rsp+28h+arg_8]
0x1800727dd  mov     rbx, [rsp+28h+arg_10]
0x1800727e2  cmp     qword ptr [rbx+158h], 0
0x1800727ea  jz      short loc_1800727EF
0x1800727ec  mov     dil, 1
0x1800727ef  test    dil, dil
0x1800727f2  jnz     short loc_1800727FE
0x1800727f4  mov     rcx, rbx; lpMem
0x1800727f7  call    DestroyAggregateSession
0x1800727fc  xor     ebx, ebx
0x1800727fe  mov     rax, rbx
0x180072801  mov     rbx, [rsp+28h+arg_0]
0x180072806  mov     rsi, [rsp+28h+arg_18]
0x18007280b  add     rsp, 20h
0x18007280f  pop     rdi
0x180072810  retn
0x18009bd9c  push    rbp
0x18009bd9e  sub     rsp, 20h
0x18009bda2  mov     rbp, rdx
0x18009bda5  mov     rax, [rcx]
0x18009bda8  xor     ecx, ecx
0x18009bdaa  cmp     dword ptr [rax], 0C000000Dh
0x18009bdb0  setz    cl
0x18009bdb3  mov     eax, ecx
0x18009bdb5  add     rsp, 20h
0x18009bdb9  pop     rbp
0x18009bdba  retn
```
