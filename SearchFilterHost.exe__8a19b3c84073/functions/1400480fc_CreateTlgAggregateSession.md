# CreateTlgAggregateSession

- ea: `0x1400480fc`
- end: `0x1400481b9`
- name: `CreateTlgAggregateSession`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140048d18`

## callees

- `0x1400480fc`
- `0x1400481c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x140048144`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x140048144`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14004812a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14004812a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140048116`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140048116`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140048166`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140048166`

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
    if ( !a1 || !dword_14006BE04 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x1400480fc  mov     [rsp+arg_0], rbx
0x140048101  mov     [rsp+arg_18], rsi
0x140048106  push    rdi
0x140048107  sub     rsp, 20h
0x14004810b  mov     sil, cl
0x14004810e  xor     dil, dil
0x140048111  mov     [rsp+28h+arg_8], dil
0x140048116  call    cs:__imp_GetProcessHeap
0x14004811c  mov     rcx, rax; hHeap
0x14004811f  mov     edx, 8; dwFlags
0x140048124  mov     r8d, 168h; dwBytes
0x14004812a  call    cs:__imp_HeapAlloc
0x140048130  mov     rbx, rax
0x140048133  mov     [rsp+28h+arg_10], rax
0x140048138  test    rax, rax
0x14004813b  jz      short loc_140048197
0x14004813d  lea     rcx, [rax+108h]; SRWLock
0x140048144  call    cs:__imp_InitializeSRWLock
0x14004814a  test    sil, sil
0x14004814d  jz      short loc_140048194
0x14004814f  mov     ecx, cs:dword_14006BE04
0x140048155  test    ecx, ecx
0x140048157  jnz     short loc_140048197
0x140048159  xor     r8d, r8d; pcbe
0x14004815c  mov     rdx, rbx; pv
0x14004815f  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x140048166  call    cs:__imp_CreateThreadpoolTimer
0x14004816c  mov     [rbx+158h], rax
0x140048173  jmp     short loc_14004818A
0x140048175  mov     eax, 1
0x14004817a  xchg    eax, cs:dword_14006BE04
0x140048180  mov     dil, [rsp+28h+arg_8]
0x140048185  mov     rbx, [rsp+28h+arg_10]
0x14004818a  cmp     qword ptr [rbx+158h], 0
0x140048192  jz      short loc_140048197
0x140048194  mov     dil, 1
0x140048197  test    dil, dil
0x14004819a  jnz     short loc_1400481A6
0x14004819c  mov     rcx, rbx; lpMem
0x14004819f  call    DestroyAggregateSession
0x1400481a4  xor     ebx, ebx
0x1400481a6  mov     rax, rbx
0x1400481a9  mov     rbx, [rsp+28h+arg_0]
0x1400481ae  mov     rsi, [rsp+28h+arg_18]
0x1400481b3  add     rsp, 20h
0x1400481b7  pop     rdi
0x1400481b8  retn
0x14004e1bf  push    rbp
0x14004e1c1  sub     rsp, 20h
0x14004e1c5  mov     rbp, rdx
0x14004e1c8  mov     rax, [rcx]
0x14004e1cb  xor     ecx, ecx
0x14004e1cd  cmp     dword ptr [rax], 0C000000Dh
0x14004e1d3  setz    cl
0x14004e1d6  mov     eax, ecx
0x14004e1d8  add     rsp, 20h
0x14004e1dc  pop     rbp
0x14004e1dd  retn
```
