# CreateTlgAggregateSession

- ea: `0x18000b5bc`
- end: `0x18000b692`
- name: `CreateTlgAggregateSession`
- size: `214`
- prototype: `RTL_SRWLOCK *__fastcall(char)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c0e8`

## callees

- `0x18000b320`
- `0x18000b5bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000b604`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000b604`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b5d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b669`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b5d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b669`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b5ea`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b5ea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b677`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b677`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000b626`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000b626`

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
    if ( !a1 || !dword_180015BB0 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x18000b5bc  mov     [rsp+arg_0], rbx
0x18000b5c1  mov     [rsp+arg_18], rsi
0x18000b5c6  push    rdi
0x18000b5c7  sub     rsp, 20h
0x18000b5cb  mov     sil, cl
0x18000b5ce  xor     dil, dil
0x18000b5d1  mov     [rsp+28h+arg_8], dil
0x18000b5d6  call    cs:__imp_GetProcessHeap
0x18000b5dc  mov     rcx, rax; hHeap
0x18000b5df  mov     edx, 8; dwFlags
0x18000b5e4  mov     r8d, 168h; dwBytes
0x18000b5ea  call    cs:__imp_HeapAlloc
0x18000b5f0  mov     rbx, rax
0x18000b5f3  mov     [rsp+28h+arg_10], rax
0x18000b5f8  test    rax, rax
0x18000b5fb  jz      short loc_18000B657
0x18000b5fd  lea     rcx, [rax+108h]; SRWLock
0x18000b604  call    cs:__imp_InitializeSRWLock
0x18000b60a  test    sil, sil
0x18000b60d  jz      short loc_18000B654
0x18000b60f  mov     ecx, cs:dword_180015BB0
0x18000b615  test    ecx, ecx
0x18000b617  jnz     short loc_18000B657
0x18000b619  xor     r8d, r8d; pcbe
0x18000b61c  mov     rdx, rbx; pv
0x18000b61f  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x18000b626  call    cs:__imp_CreateThreadpoolTimer
0x18000b62c  mov     [rbx+158h], rax
0x18000b633  jmp     short loc_18000B64A
0x18000b635  mov     eax, 1
0x18000b63a  xchg    eax, cs:dword_180015BB0
0x18000b640  mov     dil, [rsp+28h+arg_8]
0x18000b645  mov     rbx, [rsp+28h+arg_10]
0x18000b64a  cmp     qword ptr [rbx+158h], 0
0x18000b652  jz      short loc_18000B657
0x18000b654  mov     dil, 1
0x18000b657  test    dil, dil
0x18000b65a  jnz     short loc_18000B67F
0x18000b65c  test    rbx, rbx
0x18000b65f  jz      short loc_18000B67D
0x18000b661  mov     rcx, rbx
0x18000b664  call    CancelTimerCallbacksAndDeleteTimer
0x18000b669  call    cs:__imp_GetProcessHeap
0x18000b66f  mov     rcx, rax; hHeap
0x18000b672  mov     r8, rbx; lpMem
0x18000b675  xor     edx, edx; dwFlags
0x18000b677  call    cs:__imp_HeapFree
0x18000b67d  xor     ebx, ebx
0x18000b67f  mov     rax, rbx
0x18000b682  mov     rbx, [rsp+28h+arg_0]
0x18000b687  mov     rsi, [rsp+28h+arg_18]
0x18000b68c  add     rsp, 20h
0x18000b690  pop     rdi
0x18000b691  retn
0x18000d090  push    rbp
0x18000d092  sub     rsp, 20h
0x18000d096  mov     rbp, rdx
0x18000d099  mov     rax, [rcx]
0x18000d09c  xor     ecx, ecx
0x18000d09e  cmp     dword ptr [rax], 0C000000Dh
0x18000d0a4  setz    cl
0x18000d0a7  mov     eax, ecx
0x18000d0a9  add     rsp, 20h
0x18000d0ad  pop     rbp
0x18000d0ae  retn
```
