# CreateTlgAggregateSession

- ea: `0x18000b308`
- end: `0x18000b3de`
- name: `CreateTlgAggregateSession`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000bb08`

## callees

- `0x18000b2ac`
- `0x18000b308`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000b350`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000b350`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b322`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b3b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b322`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b3b5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b3c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b3c3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b336`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b336`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000b372`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000b372`

## pseudocode

```c
RTL_SRWLOCK *__fastcall CreateTlgAggregateSession(char a1)
{
  char v2; // di
  HANDLE ProcessHeap; // rax
  RTL_SRWLOCK *v4; // rax
  RTL_SRWLOCK *v5; // rbx
  HANDLE v6; // rax

  v2 = 0;
  ProcessHeap = GetProcessHeap();
  v4 = (RTL_SRWLOCK *)HeapAlloc(ProcessHeap, 8u, 0x168u);
  v5 = v4;
  if ( v4 )
  {
    InitializeSRWLock(v4 + 33);
    if ( !a1 || !dword_180014508 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
      v2 = 1;
  }
  if ( !v2 )
  {
    if ( v5 )
    {
      CancelTimerCallbacksAndDeleteTimer((__int64)v5);
      v6 = GetProcessHeap();
      HeapFree(v6, 0, v5);
    }
    return 0;
  }
  return v5;
}

```

## disassembly

```asm
0x18000b308  mov     [rsp+arg_0], rbx
0x18000b30d  mov     [rsp+arg_18], rsi
0x18000b312  push    rdi
0x18000b313  sub     rsp, 20h
0x18000b317  mov     sil, cl
0x18000b31a  xor     dil, dil
0x18000b31d  mov     [rsp+28h+arg_8], dil
0x18000b322  call    cs:__imp_GetProcessHeap
0x18000b328  mov     rcx, rax; hHeap
0x18000b32b  mov     edx, 8; dwFlags
0x18000b330  mov     r8d, 168h; dwBytes
0x18000b336  call    cs:__imp_HeapAlloc
0x18000b33c  mov     rbx, rax
0x18000b33f  mov     [rsp+28h+arg_10], rax
0x18000b344  test    rax, rax
0x18000b347  jz      short loc_18000B3A3
0x18000b349  lea     rcx, [rax+108h]; SRWLock
0x18000b350  call    cs:__imp_InitializeSRWLock
0x18000b356  test    sil, sil
0x18000b359  jz      short loc_18000B3A0
0x18000b35b  mov     ecx, cs:dword_180014508
0x18000b361  test    ecx, ecx
0x18000b363  jnz     short loc_18000B3A3
0x18000b365  xor     r8d, r8d; pcbe
0x18000b368  mov     rdx, rbx; pv
0x18000b36b  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x18000b372  call    cs:__imp_CreateThreadpoolTimer
0x18000b378  mov     [rbx+158h], rax
0x18000b37f  jmp     short loc_18000B396
0x18000b381  mov     eax, 1
0x18000b386  xchg    eax, cs:dword_180014508
0x18000b38c  mov     dil, [rsp+28h+arg_8]
0x18000b391  mov     rbx, [rsp+28h+arg_10]
0x18000b396  cmp     qword ptr [rbx+158h], 0
0x18000b39e  jz      short loc_18000B3A3
0x18000b3a0  mov     dil, 1
0x18000b3a3  test    dil, dil
0x18000b3a6  jnz     short loc_18000B3CB
0x18000b3a8  test    rbx, rbx
0x18000b3ab  jz      short loc_18000B3C9
0x18000b3ad  mov     rcx, rbx
0x18000b3b0  call    CancelTimerCallbacksAndDeleteTimer
0x18000b3b5  call    cs:__imp_GetProcessHeap
0x18000b3bb  mov     rcx, rax; hHeap
0x18000b3be  mov     r8, rbx; lpMem
0x18000b3c1  xor     edx, edx; dwFlags
0x18000b3c3  call    cs:__imp_HeapFree
0x18000b3c9  xor     ebx, ebx
0x18000b3cb  mov     rax, rbx
0x18000b3ce  mov     rbx, [rsp+28h+arg_0]
0x18000b3d3  mov     rsi, [rsp+28h+arg_18]
0x18000b3d8  add     rsp, 20h
0x18000b3dc  pop     rdi
0x18000b3dd  retn
0x18000c73c  push    rbp
0x18000c73e  sub     rsp, 20h
0x18000c742  mov     rbp, rdx
0x18000c745  mov     rax, [rcx]
0x18000c748  xor     ecx, ecx
0x18000c74a  cmp     dword ptr [rax], 0C000000Dh
0x18000c750  setz    cl
0x18000c753  mov     eax, ecx
0x18000c755  add     rsp, 20h
0x18000c759  pop     rbp
0x18000c75a  retn
```
