# CreateTlgAggregateSession

- ea: `0x18009d048`
- end: `0x18009d105`
- name: `CreateTlgAggregateSession`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18009cf48`

## callees

- `0x18009d048`
- `0x180152a08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18009d090`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18009d090`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009d076`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009d076`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009d062`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009d062`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18009d0b2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18009d0b2`

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
    if ( !a1 || !dword_18033B144 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x18009d048  mov     [rsp+arg_0], rbx
0x18009d04d  mov     [rsp+arg_18], rsi
0x18009d052  push    rdi
0x18009d053  sub     rsp, 20h
0x18009d057  mov     sil, cl
0x18009d05a  xor     dil, dil
0x18009d05d  mov     [rsp+28h+arg_8], dil
0x18009d062  call    cs:__imp_GetProcessHeap
0x18009d068  mov     rcx, rax; hHeap
0x18009d06b  mov     edx, 8; dwFlags
0x18009d070  mov     r8d, 168h; dwBytes
0x18009d076  call    cs:__imp_HeapAlloc
0x18009d07c  mov     rbx, rax
0x18009d07f  mov     [rsp+28h+arg_10], rax
0x18009d084  test    rax, rax
0x18009d087  jz      short loc_18009D0E3
0x18009d089  lea     rcx, [rax+108h]; SRWLock
0x18009d090  call    cs:__imp_InitializeSRWLock
0x18009d096  test    sil, sil
0x18009d099  jz      short loc_18009D0E0
0x18009d09b  mov     ecx, cs:dword_18033B144
0x18009d0a1  test    ecx, ecx
0x18009d0a3  jnz     short loc_18009D0E3
0x18009d0a5  xor     r8d, r8d; pcbe
0x18009d0a8  mov     rdx, rbx; pv
0x18009d0ab  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x18009d0b2  call    cs:__imp_CreateThreadpoolTimer
0x18009d0b8  mov     [rbx+158h], rax
0x18009d0bf  jmp     short loc_18009D0D6
0x18009d0c1  mov     eax, 1
0x18009d0c6  xchg    eax, cs:dword_18033B144
0x18009d0cc  mov     dil, [rsp+28h+arg_8]
0x18009d0d1  mov     rbx, [rsp+28h+arg_10]
0x18009d0d6  cmp     qword ptr [rbx+158h], 0
0x18009d0de  jz      short loc_18009D0E3
0x18009d0e0  mov     dil, 1
0x18009d0e3  test    dil, dil
0x18009d0e6  jnz     short loc_18009D0F2
0x18009d0e8  mov     rcx, rbx; lpMem
0x18009d0eb  call    DestroyAggregateSession
0x18009d0f0  xor     ebx, ebx
0x18009d0f2  mov     rax, rbx
0x18009d0f5  mov     rbx, [rsp+28h+arg_0]
0x18009d0fa  mov     rsi, [rsp+28h+arg_18]
0x18009d0ff  add     rsp, 20h
0x18009d103  pop     rdi
0x18009d104  retn
0x18022a7e1  push    rbp
0x18022a7e3  sub     rsp, 20h
0x18022a7e7  mov     rbp, rdx
0x18022a7ea  mov     rax, [rcx]
0x18022a7ed  xor     ecx, ecx
0x18022a7ef  cmp     dword ptr [rax], 0C000000Dh
0x18022a7f5  setz    cl
0x18022a7f8  mov     eax, ecx
0x18022a7fa  add     rsp, 20h
0x18022a7fe  pop     rbp
0x18022a7ff  retn
```
