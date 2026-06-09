# CreateTlgAggregateSession

- ea: `0x18007e368`
- end: `0x18007e43e`
- name: `CreateTlgAggregateSession`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18007ee88`

## callees

- `0x18007e0cc`
- `0x18007e368`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18007e3b0`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18007e3b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007e382`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007e415`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007e382`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007e415`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007e396`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007e396`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007e423`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007e423`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18007e3d2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18007e3d2`

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
    if ( !a1 || !dword_1800AFD48 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x18007e368  mov     [rsp+arg_0], rbx
0x18007e36d  mov     [rsp+arg_18], rsi
0x18007e372  push    rdi
0x18007e373  sub     rsp, 20h
0x18007e377  mov     sil, cl
0x18007e37a  xor     dil, dil
0x18007e37d  mov     [rsp+28h+arg_8], dil
0x18007e382  call    cs:__imp_GetProcessHeap
0x18007e388  mov     rcx, rax; hHeap
0x18007e38b  mov     edx, 8; dwFlags
0x18007e390  mov     r8d, 168h; dwBytes
0x18007e396  call    cs:__imp_HeapAlloc
0x18007e39c  mov     rbx, rax
0x18007e39f  mov     [rsp+28h+arg_10], rax
0x18007e3a4  test    rax, rax
0x18007e3a7  jz      short loc_18007E403
0x18007e3a9  lea     rcx, [rax+108h]; SRWLock
0x18007e3b0  call    cs:__imp_InitializeSRWLock
0x18007e3b6  test    sil, sil
0x18007e3b9  jz      short loc_18007E400
0x18007e3bb  mov     ecx, cs:dword_1800AFD48
0x18007e3c1  test    ecx, ecx
0x18007e3c3  jnz     short loc_18007E403
0x18007e3c5  xor     r8d, r8d; pcbe
0x18007e3c8  mov     rdx, rbx; pv
0x18007e3cb  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x18007e3d2  call    cs:__imp_CreateThreadpoolTimer
0x18007e3d8  mov     [rbx+158h], rax
0x18007e3df  jmp     short loc_18007E3F6
0x18007e3e1  mov     eax, 1
0x18007e3e6  xchg    eax, cs:dword_1800AFD48
0x18007e3ec  mov     dil, [rsp+28h+arg_8]
0x18007e3f1  mov     rbx, [rsp+28h+arg_10]
0x18007e3f6  cmp     qword ptr [rbx+158h], 0
0x18007e3fe  jz      short loc_18007E403
0x18007e400  mov     dil, 1
0x18007e403  test    dil, dil
0x18007e406  jnz     short loc_18007E42B
0x18007e408  test    rbx, rbx
0x18007e40b  jz      short loc_18007E429
0x18007e40d  mov     rcx, rbx
0x18007e410  call    CancelTimerCallbacksAndDeleteTimer
0x18007e415  call    cs:__imp_GetProcessHeap
0x18007e41b  mov     rcx, rax; hHeap
0x18007e41e  mov     r8, rbx; lpMem
0x18007e421  xor     edx, edx; dwFlags
0x18007e423  call    cs:__imp_HeapFree
0x18007e429  xor     ebx, ebx
0x18007e42b  mov     rax, rbx
0x18007e42e  mov     rbx, [rsp+28h+arg_0]
0x18007e433  mov     rsi, [rsp+28h+arg_18]
0x18007e438  add     rsp, 20h
0x18007e43c  pop     rdi
0x18007e43d  retn
0x180088388  push    rbp
0x18008838a  sub     rsp, 20h
0x18008838e  mov     rbp, rdx
0x180088391  mov     rax, [rcx]
0x180088394  xor     ecx, ecx
0x180088396  cmp     dword ptr [rax], 0C000000Dh
0x18008839c  setz    cl
0x18008839f  mov     eax, ecx
0x1800883a1  add     rsp, 20h
0x1800883a5  pop     rbp
0x1800883a6  retn
```
