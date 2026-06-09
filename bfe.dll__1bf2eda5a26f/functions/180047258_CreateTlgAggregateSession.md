# CreateTlgAggregateSession

- ea: `0x180047258`
- end: `0x180047315`
- name: `CreateTlgAggregateSession`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18004714c`

## callees

- `0x180047258`
- `0x180075404`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800472c2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800472c2`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800472a0`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800472a0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180047286`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180047286`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180047272`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180047272`

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
    if ( !a1
      || !MEMORY[0x1800EF094][171] && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
    {
      v2 = 1;
    }
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
0x180047258  mov     [rsp+arg_0], rbx
0x18004725d  mov     [rsp+arg_18], rsi
0x180047262  push    rdi
0x180047263  sub     rsp, 20h
0x180047267  mov     sil, cl
0x18004726a  xor     dil, dil
0x18004726d  mov     [rsp+28h+arg_8], dil
0x180047272  call    cs:__imp_GetProcessHeap
0x180047278  mov     rcx, rax; hHeap
0x18004727b  mov     edx, 8; dwFlags
0x180047280  mov     r8d, 168h; dwBytes
0x180047286  call    cs:__imp_HeapAlloc
0x18004728c  mov     rbx, rax
0x18004728f  mov     [rsp+28h+arg_10], rax
0x180047294  test    rax, rax
0x180047297  jz      short loc_1800472F3
0x180047299  lea     rcx, [rax+108h]; SRWLock
0x1800472a0  call    cs:__imp_InitializeSRWLock
0x1800472a6  test    sil, sil
0x1800472a9  jz      short loc_1800472F0
0x1800472ab  mov     ecx, cs:1800EF340h
0x1800472b1  test    ecx, ecx
0x1800472b3  jnz     short loc_1800472F3
0x1800472b5  xor     r8d, r8d; pcbe
0x1800472b8  mov     rdx, rbx; pv
0x1800472bb  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x1800472c2  call    cs:__imp_CreateThreadpoolTimer
0x1800472c8  mov     [rbx+158h], rax
0x1800472cf  jmp     short loc_1800472E6
0x1800472d1  mov     eax, 1
0x1800472d6  xchg    eax, cs:1800EF340h
0x1800472dc  mov     dil, [rsp+28h+arg_8]
0x1800472e1  mov     rbx, [rsp+28h+arg_10]
0x1800472e6  cmp     qword ptr [rbx+158h], 0
0x1800472ee  jz      short loc_1800472F3
0x1800472f0  mov     dil, 1
0x1800472f3  test    dil, dil
0x1800472f6  jnz     short loc_180047302
0x1800472f8  mov     rcx, rbx; lpMem
0x1800472fb  call    DestroyAggregateSession
0x180047300  xor     ebx, ebx
0x180047302  mov     rax, rbx
0x180047305  mov     rbx, [rsp+28h+arg_0]
0x18004730a  mov     rsi, [rsp+28h+arg_18]
0x18004730f  add     rsp, 20h
0x180047313  pop     rdi
0x180047314  retn
0x180087eda  push    rbp
0x180087edc  sub     rsp, 20h
0x180087ee0  mov     rbp, rdx
0x180087ee3  mov     rax, [rcx]
0x180087ee6  xor     ecx, ecx
0x180087ee8  cmp     dword ptr [rax], 0C000000Dh
0x180087eee  setz    cl
0x180087ef1  mov     eax, ecx
0x180087ef3  add     rsp, 20h
0x180087ef7  pop     rbp
0x180087ef8  retn
```
