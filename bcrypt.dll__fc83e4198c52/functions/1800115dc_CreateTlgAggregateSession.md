# CreateTlgAggregateSession

- ea: `0x1800115dc`
- end: `0x1800116b2`
- name: `CreateTlgAggregateSession`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800114c4`

## callees

- `0x1800115dc`
- `0x18001175c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180011630`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180011630`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011610`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011610`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800115f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800115f6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180011658`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180011658`

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
    if ( !a1 || !dword_180024B08 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x1800115dc  mov     [rsp+arg_0], rbx
0x1800115e1  mov     [rsp+arg_18], rsi
0x1800115e6  push    rdi
0x1800115e7  sub     rsp, 20h
0x1800115eb  mov     sil, cl
0x1800115ee  xor     dil, dil
0x1800115f1  mov     [rsp+28h+arg_8], dil
0x1800115f6  call    cs:__imp_GetProcessHeap
0x1800115fd  nop     dword ptr [rax+rax+00h]
0x180011602  mov     rcx, rax; hHeap
0x180011605  mov     edx, 8; dwFlags
0x18001160a  mov     r8d, 168h; dwBytes
0x180011610  call    cs:__imp_HeapAlloc
0x180011617  nop     dword ptr [rax+rax+00h]
0x18001161c  mov     rbx, rax
0x18001161f  mov     [rsp+28h+arg_10], rax
0x180011624  test    rax, rax
0x180011627  jz      short loc_18001168F
0x180011629  lea     rcx, [rax+108h]; SRWLock
0x180011630  call    cs:__imp_InitializeSRWLock
0x180011637  nop     dword ptr [rax+rax+00h]
0x18001163c  test    sil, sil
0x18001163f  jz      short loc_18001168C
0x180011641  mov     ecx, cs:dword_180024B08
0x180011647  test    ecx, ecx
0x180011649  jnz     short loc_18001168F
0x18001164b  xor     r8d, r8d; pcbe
0x18001164e  mov     rdx, rbx; pv
0x180011651  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x180011658  call    cs:__imp_CreateThreadpoolTimer
0x18001165f  nop     dword ptr [rax+rax+00h]
0x180011664  mov     [rbx+158h], rax
0x18001166b  jmp     short loc_180011682
0x18001166d  mov     eax, 1
0x180011672  xchg    eax, cs:dword_180024B08
0x180011678  mov     dil, [rsp+28h+arg_8]
0x18001167d  mov     rbx, [rsp+28h+arg_10]
0x180011682  cmp     qword ptr [rbx+158h], 0
0x18001168a  jz      short loc_18001168F
0x18001168c  mov     dil, 1
0x18001168f  test    dil, dil
0x180011692  jnz     short loc_18001169E
0x180011694  mov     rcx, rbx; lpMem
0x180011697  call    DestroyAggregateSession
0x18001169c  xor     ebx, ebx
0x18001169e  mov     rax, rbx
0x1800116a1  mov     rbx, [rsp+28h+arg_0]
0x1800116a6  mov     rsi, [rsp+28h+arg_18]
0x1800116ab  add     rsp, 20h
0x1800116af  pop     rdi
0x1800116b0  retn
0x18001b91d  push    rbp
0x18001b91f  sub     rsp, 20h
0x18001b923  mov     rbp, rdx
0x18001b926  mov     rax, [rcx]
0x18001b929  xor     ecx, ecx
0x18001b92b  cmp     dword ptr [rax], 0C000000Dh
0x18001b931  setz    cl
0x18001b934  mov     eax, ecx
0x18001b936  add     rsp, 20h
0x18001b93a  pop     rbp
0x18001b93b  retn
```
