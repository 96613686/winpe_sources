# CreateTlgAggregateSession

- ea: `0x1800992cc`
- end: `0x180099389`
- name: `CreateTlgAggregateSession`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180099ec0`

## callees

- `0x1800992cc`
- `0x180099390`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800992fa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800992fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800992e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800992e6`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180099314`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180099314`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180099336`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180099336`

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
    if ( !a1 || !dword_18012A478 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x1800992cc  mov     [rsp+arg_0], rbx
0x1800992d1  mov     [rsp+arg_18], rsi
0x1800992d6  push    rdi
0x1800992d7  sub     rsp, 20h
0x1800992db  mov     sil, cl
0x1800992de  xor     dil, dil
0x1800992e1  mov     [rsp+28h+arg_8], dil
0x1800992e6  call    cs:__imp_GetProcessHeap
0x1800992ec  mov     rcx, rax; hHeap
0x1800992ef  mov     edx, 8; dwFlags
0x1800992f4  mov     r8d, 168h; dwBytes
0x1800992fa  call    cs:__imp_HeapAlloc
0x180099300  mov     rbx, rax
0x180099303  mov     [rsp+28h+arg_10], rax
0x180099308  test    rax, rax
0x18009930b  jz      short loc_180099367
0x18009930d  lea     rcx, [rax+108h]; SRWLock
0x180099314  call    cs:__imp_InitializeSRWLock
0x18009931a  test    sil, sil
0x18009931d  jz      short loc_180099364
0x18009931f  mov     ecx, cs:dword_18012A478
0x180099325  test    ecx, ecx
0x180099327  jnz     short loc_180099367
0x180099329  xor     r8d, r8d; pcbe
0x18009932c  mov     rdx, rbx; pv
0x18009932f  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x180099336  call    cs:__imp_CreateThreadpoolTimer
0x18009933c  mov     [rbx+158h], rax
0x180099343  jmp     short loc_18009935A
0x180099345  mov     eax, 1
0x18009934a  xchg    eax, cs:dword_18012A478
0x180099350  mov     dil, [rsp+28h+arg_8]
0x180099355  mov     rbx, [rsp+28h+arg_10]
0x18009935a  cmp     qword ptr [rbx+158h], 0
0x180099362  jz      short loc_180099367
0x180099364  mov     dil, 1
0x180099367  test    dil, dil
0x18009936a  jnz     short loc_180099376
0x18009936c  mov     rcx, rbx; lpMem
0x18009936f  call    DestroyAggregateSession
0x180099374  xor     ebx, ebx
0x180099376  mov     rax, rbx
0x180099379  mov     rbx, [rsp+28h+arg_0]
0x18009937e  mov     rsi, [rsp+28h+arg_18]
0x180099383  add     rsp, 20h
0x180099387  pop     rdi
0x180099388  retn
0x1800e6034  push    rbp
0x1800e6036  sub     rsp, 20h
0x1800e603a  mov     rbp, rdx
0x1800e603d  mov     rax, [rcx]
0x1800e6040  xor     ecx, ecx
0x1800e6042  cmp     dword ptr [rax], 0C000000Dh
0x1800e6048  setz    cl
0x1800e604b  mov     eax, ecx
0x1800e604d  add     rsp, 20h
0x1800e6051  pop     rbp
0x1800e6052  retn
```
