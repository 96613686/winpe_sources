# CreateTlgAggregateSession

- ea: `0x180010cd8`
- end: `0x180010d95`
- name: `CreateTlgAggregateSession`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180010bcc`

## callees

- `0x180010cd8`
- `0x180019b40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180010d20`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180010d20`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180010d42`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180010d42`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010cf2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010cf2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010d06`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010d06`

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
    if ( !a1 || !dword_180026678 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x180010cd8  mov     [rsp+arg_0], rbx
0x180010cdd  mov     [rsp+arg_18], rsi
0x180010ce2  push    rdi
0x180010ce3  sub     rsp, 20h
0x180010ce7  mov     sil, cl
0x180010cea  xor     dil, dil
0x180010ced  mov     [rsp+28h+arg_8], dil
0x180010cf2  call    cs:__imp_GetProcessHeap
0x180010cf8  mov     rcx, rax; hHeap
0x180010cfb  mov     edx, 8; dwFlags
0x180010d00  mov     r8d, 168h; dwBytes
0x180010d06  call    cs:__imp_HeapAlloc
0x180010d0c  mov     rbx, rax
0x180010d0f  mov     [rsp+28h+arg_10], rax
0x180010d14  test    rax, rax
0x180010d17  jz      short loc_180010D73
0x180010d19  lea     rcx, [rax+108h]; SRWLock
0x180010d20  call    cs:__imp_InitializeSRWLock
0x180010d26  test    sil, sil
0x180010d29  jz      short loc_180010D70
0x180010d2b  mov     ecx, cs:dword_180026678
0x180010d31  test    ecx, ecx
0x180010d33  jnz     short loc_180010D73
0x180010d35  xor     r8d, r8d; pcbe
0x180010d38  mov     rdx, rbx; pv
0x180010d3b  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x180010d42  call    cs:__imp_CreateThreadpoolTimer
0x180010d48  mov     [rbx+158h], rax
0x180010d4f  jmp     short loc_180010D66
0x180010d51  mov     eax, 1
0x180010d56  xchg    eax, cs:dword_180026678
0x180010d5c  mov     dil, [rsp+28h+arg_8]
0x180010d61  mov     rbx, [rsp+28h+arg_10]
0x180010d66  cmp     qword ptr [rbx+158h], 0
0x180010d6e  jz      short loc_180010D73
0x180010d70  mov     dil, 1
0x180010d73  test    dil, dil
0x180010d76  jnz     short loc_180010D82
0x180010d78  mov     rcx, rbx; lpMem
0x180010d7b  call    DestroyAggregateSession
0x180010d80  xor     ebx, ebx
0x180010d82  mov     rax, rbx
0x180010d85  mov     rbx, [rsp+28h+arg_0]
0x180010d8a  mov     rsi, [rsp+28h+arg_18]
0x180010d8f  add     rsp, 20h
0x180010d93  pop     rdi
0x180010d94  retn
0x18001abfe  push    rbp
0x18001ac00  sub     rsp, 20h
0x18001ac04  mov     rbp, rdx
0x18001ac07  mov     rax, [rcx]
0x18001ac0a  xor     ecx, ecx
0x18001ac0c  cmp     dword ptr [rax], 0C000000Dh
0x18001ac12  setz    cl
0x18001ac15  mov     eax, ecx
0x18001ac17  add     rsp, 20h
0x18001ac1b  pop     rbp
0x18001ac1c  retn
```
