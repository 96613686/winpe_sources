# CreateTlgAggregateSession

- ea: `0x180022188`
- end: `0x180022245`
- name: `CreateTlgAggregateSession`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180022d80`

## callees

- `0x180022188`
- `0x18002224c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800221d0`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800221d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800221a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800221a2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800221b6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800221b6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800221f2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800221f2`

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
    if ( !a1 || !dword_180033880 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x180022188  mov     [rsp+arg_0], rbx
0x18002218d  mov     [rsp+arg_18], rsi
0x180022192  push    rdi
0x180022193  sub     rsp, 20h
0x180022197  mov     sil, cl
0x18002219a  xor     dil, dil
0x18002219d  mov     [rsp+28h+arg_8], dil
0x1800221a2  call    cs:__imp_GetProcessHeap
0x1800221a8  mov     rcx, rax; hHeap
0x1800221ab  mov     edx, 8; dwFlags
0x1800221b0  mov     r8d, 168h; dwBytes
0x1800221b6  call    cs:__imp_HeapAlloc
0x1800221bc  mov     rbx, rax
0x1800221bf  mov     [rsp+28h+arg_10], rax
0x1800221c4  test    rax, rax
0x1800221c7  jz      short loc_180022223
0x1800221c9  lea     rcx, [rax+108h]; SRWLock
0x1800221d0  call    cs:__imp_InitializeSRWLock
0x1800221d6  test    sil, sil
0x1800221d9  jz      short loc_180022220
0x1800221db  mov     ecx, cs:dword_180033880
0x1800221e1  test    ecx, ecx
0x1800221e3  jnz     short loc_180022223
0x1800221e5  xor     r8d, r8d; pcbe
0x1800221e8  mov     rdx, rbx; pv
0x1800221eb  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x1800221f2  call    cs:__imp_CreateThreadpoolTimer
0x1800221f8  mov     [rbx+158h], rax
0x1800221ff  jmp     short loc_180022216
0x180022201  mov     eax, 1
0x180022206  xchg    eax, cs:dword_180033880
0x18002220c  mov     dil, [rsp+28h+arg_8]
0x180022211  mov     rbx, [rsp+28h+arg_10]
0x180022216  cmp     qword ptr [rbx+158h], 0
0x18002221e  jz      short loc_180022223
0x180022220  mov     dil, 1
0x180022223  test    dil, dil
0x180022226  jnz     short loc_180022232
0x180022228  mov     rcx, rbx; lpMem
0x18002222b  call    DestroyAggregateSession
0x180022230  xor     ebx, ebx
0x180022232  mov     rax, rbx
0x180022235  mov     rbx, [rsp+28h+arg_0]
0x18002223a  mov     rsi, [rsp+28h+arg_18]
0x18002223f  add     rsp, 20h
0x180022243  pop     rdi
0x180022244  retn
0x1800248b4  push    rbp
0x1800248b6  sub     rsp, 20h
0x1800248ba  mov     rbp, rdx
0x1800248bd  mov     rax, [rcx]
0x1800248c0  xor     ecx, ecx
0x1800248c2  cmp     dword ptr [rax], 0C000000Dh
0x1800248c8  setz    cl
0x1800248cb  mov     eax, ecx
0x1800248cd  add     rsp, 20h
0x1800248d1  pop     rbp
0x1800248d2  retn
```
