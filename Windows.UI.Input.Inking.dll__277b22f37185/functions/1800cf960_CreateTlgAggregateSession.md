# CreateTlgAggregateSession

- ea: `0x1800cf960`
- end: `0x1800cfa1d`
- name: `CreateTlgAggregateSession`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800d0540`

## callees

- `0x1800cf960`
- `0x1800cfa24`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800cf9a8`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800cf9a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cf97a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cf97a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800cf98e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800cf98e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800cf9ca`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800cf9ca`

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
    if ( !a1 || !dword_18015BFA0 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x1800cf960  mov     [rsp+arg_0], rbx
0x1800cf965  mov     [rsp+arg_18], rsi
0x1800cf96a  push    rdi
0x1800cf96b  sub     rsp, 20h
0x1800cf96f  mov     sil, cl
0x1800cf972  xor     dil, dil
0x1800cf975  mov     [rsp+28h+arg_8], dil
0x1800cf97a  call    cs:__imp_GetProcessHeap
0x1800cf980  mov     rcx, rax; hHeap
0x1800cf983  mov     edx, 8; dwFlags
0x1800cf988  mov     r8d, 168h; dwBytes
0x1800cf98e  call    cs:__imp_HeapAlloc
0x1800cf994  mov     rbx, rax
0x1800cf997  mov     [rsp+28h+arg_10], rax
0x1800cf99c  test    rax, rax
0x1800cf99f  jz      short loc_1800CF9FB
0x1800cf9a1  lea     rcx, [rax+108h]; SRWLock
0x1800cf9a8  call    cs:__imp_InitializeSRWLock
0x1800cf9ae  test    sil, sil
0x1800cf9b1  jz      short loc_1800CF9F8
0x1800cf9b3  mov     ecx, cs:dword_18015BFA0
0x1800cf9b9  test    ecx, ecx
0x1800cf9bb  jnz     short loc_1800CF9FB
0x1800cf9bd  xor     r8d, r8d; pcbe
0x1800cf9c0  mov     rdx, rbx; pv
0x1800cf9c3  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x1800cf9ca  call    cs:__imp_CreateThreadpoolTimer
0x1800cf9d0  mov     [rbx+158h], rax
0x1800cf9d7  jmp     short loc_1800CF9EE
0x1800cf9d9  mov     eax, 1
0x1800cf9de  xchg    eax, cs:dword_18015BFA0
0x1800cf9e4  mov     dil, [rsp+28h+arg_8]
0x1800cf9e9  mov     rbx, [rsp+28h+arg_10]
0x1800cf9ee  cmp     qword ptr [rbx+158h], 0
0x1800cf9f6  jz      short loc_1800CF9FB
0x1800cf9f8  mov     dil, 1
0x1800cf9fb  test    dil, dil
0x1800cf9fe  jnz     short loc_1800CFA0A
0x1800cfa00  mov     rcx, rbx; lpMem
0x1800cfa03  call    DestroyAggregateSession
0x1800cfa08  xor     ebx, ebx
0x1800cfa0a  mov     rax, rbx
0x1800cfa0d  mov     rbx, [rsp+28h+arg_0]
0x1800cfa12  mov     rsi, [rsp+28h+arg_18]
0x1800cfa17  add     rsp, 20h
0x1800cfa1b  pop     rdi
0x1800cfa1c  retn
0x1800fa45f  push    rbp
0x1800fa461  sub     rsp, 20h
0x1800fa465  mov     rbp, rdx
0x1800fa468  mov     rax, [rcx]
0x1800fa46b  xor     ecx, ecx
0x1800fa46d  cmp     dword ptr [rax], 0C000000Dh
0x1800fa473  setz    cl
0x1800fa476  mov     eax, ecx
0x1800fa478  add     rsp, 20h
0x1800fa47c  pop     rbp
0x1800fa47d  retn
```
