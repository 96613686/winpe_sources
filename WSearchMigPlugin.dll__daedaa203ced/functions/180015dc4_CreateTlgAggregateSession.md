# CreateTlgAggregateSession

- ea: `0x180015dc4`
- end: `0x180015e9a`
- name: `CreateTlgAggregateSession`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800168e8`

## callees

- `0x180015b28`
- `0x180015dc4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180015e0c`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180015e0c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015dde`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015e71`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015dde`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015e71`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015e7f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015e7f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015df2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015df2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180015e2e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180015e2e`

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
    if ( !a1 || !dword_180026140 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x180015dc4  mov     [rsp+arg_0], rbx
0x180015dc9  mov     [rsp+arg_18], rsi
0x180015dce  push    rdi
0x180015dcf  sub     rsp, 20h
0x180015dd3  mov     sil, cl
0x180015dd6  xor     dil, dil
0x180015dd9  mov     [rsp+28h+arg_8], dil
0x180015dde  call    cs:__imp_GetProcessHeap
0x180015de4  mov     rcx, rax; hHeap
0x180015de7  mov     edx, 8; dwFlags
0x180015dec  mov     r8d, 168h; dwBytes
0x180015df2  call    cs:__imp_HeapAlloc
0x180015df8  mov     rbx, rax
0x180015dfb  mov     [rsp+28h+arg_10], rax
0x180015e00  test    rax, rax
0x180015e03  jz      short loc_180015E5F
0x180015e05  lea     rcx, [rax+108h]; SRWLock
0x180015e0c  call    cs:__imp_InitializeSRWLock
0x180015e12  test    sil, sil
0x180015e15  jz      short loc_180015E5C
0x180015e17  mov     ecx, cs:dword_180026140
0x180015e1d  test    ecx, ecx
0x180015e1f  jnz     short loc_180015E5F
0x180015e21  xor     r8d, r8d; pcbe
0x180015e24  mov     rdx, rbx; pv
0x180015e27  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x180015e2e  call    cs:__imp_CreateThreadpoolTimer
0x180015e34  mov     [rbx+158h], rax
0x180015e3b  jmp     short loc_180015E52
0x180015e3d  mov     eax, 1
0x180015e42  xchg    eax, cs:dword_180026140
0x180015e48  mov     dil, [rsp+28h+arg_8]
0x180015e4d  mov     rbx, [rsp+28h+arg_10]
0x180015e52  cmp     qword ptr [rbx+158h], 0
0x180015e5a  jz      short loc_180015E5F
0x180015e5c  mov     dil, 1
0x180015e5f  test    dil, dil
0x180015e62  jnz     short loc_180015E87
0x180015e64  test    rbx, rbx
0x180015e67  jz      short loc_180015E85
0x180015e69  mov     rcx, rbx
0x180015e6c  call    CancelTimerCallbacksAndDeleteTimer
0x180015e71  call    cs:__imp_GetProcessHeap
0x180015e77  mov     rcx, rax; hHeap
0x180015e7a  mov     r8, rbx; lpMem
0x180015e7d  xor     edx, edx; dwFlags
0x180015e7f  call    cs:__imp_HeapFree
0x180015e85  xor     ebx, ebx
0x180015e87  mov     rax, rbx
0x180015e8a  mov     rbx, [rsp+28h+arg_0]
0x180015e8f  mov     rsi, [rsp+28h+arg_18]
0x180015e94  add     rsp, 20h
0x180015e98  pop     rdi
0x180015e99  retn
0x180017bdf  push    rbp
0x180017be1  sub     rsp, 20h
0x180017be5  mov     rbp, rdx
0x180017be8  mov     rax, [rcx]
0x180017beb  xor     ecx, ecx
0x180017bed  cmp     dword ptr [rax], 0C000000Dh
0x180017bf3  setz    cl
0x180017bf6  mov     eax, ecx
0x180017bf8  add     rsp, 20h
0x180017bfc  pop     rbp
0x180017bfd  retn
```
