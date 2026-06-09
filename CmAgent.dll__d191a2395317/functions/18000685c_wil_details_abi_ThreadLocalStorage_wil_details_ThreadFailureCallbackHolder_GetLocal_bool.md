# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000685c`
- end: `0x1800068ff`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `163`
- prototype: `signed __int64 __fastcall(__int64, char)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800088b0`

## callees

- `0x18000685c`
- `0x18000753c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000686f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000686f`

## pseudocode

```c
signed __int64 __fastcall wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
        __int64 a1,
        char a2)
{
  __int64 v2; // rdi
  DWORD CurrentThreadId; // esi
  unsigned __int64 v5; // r8
  unsigned __int64 v6; // rbx
  __int64 i; // rax
  DWORD *v8; // rax
  signed __int64 v9; // rcx
  signed __int64 v10; // rax

  v2 = wil::details::g_pThreadFailureCallbacks;
  CurrentThreadId = GetCurrentThreadId();
  v6 = ((unsigned __int64)CurrentThreadId >> 2) % 0xA;
  for ( i = *(_QWORD *)(v2 + 8 * v6); i; i = *(_QWORD *)(i + 8) )
  {
    if ( *(_DWORD *)i == CurrentThreadId )
      return i + 16;
  }
  if ( !a2 )
    return 0;
  v8 = (DWORD *)wil::details::ProcessHeapAlloc(0, 0x18u, v5);
  v9 = (signed __int64)v8;
  if ( !v8 )
    return 0;
  *v8 = CurrentThreadId;
  v8[1] = 0;
  *((_QWORD *)v8 + 1) = 0;
  *((_QWORD *)v8 + 2) = 0;
  do
  {
    v10 = *(_QWORD *)(v2 + 8 * v6);
    *(_QWORD *)(v9 + 8) = v10;
  }
  while ( v10 != _InterlockedCompareExchange64((volatile signed __int64 *)(v2 + 8 * v6), v9, v10) );
  return v9 + 16;
}

```

## disassembly

```asm
0x18000685c  push    rbx
0x18000685e  push    rbp
0x18000685f  push    rsi
0x180006860  push    rdi
0x180006861  sub     rsp, 28h
0x180006865  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000686c  mov     bpl, dl
0x18000686f  call    cs:__imp_GetCurrentThreadId
0x180006876  nop     dword ptr [rax+rax+00h]
0x18000687b  mov     ebx, eax
0x18000687d  mov     esi, eax
0x18000687f  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006889  shr     rbx, 2
0x18000688d  mul     rbx
0x180006890  shr     rdx, 3
0x180006894  lea     rcx, [rdx+rdx*4]
0x180006898  add     rcx, rcx
0x18000689b  sub     rbx, rcx
0x18000689e  mov     rax, [rdi+rbx*8]
0x1800068a2  jmp     short loc_1800068AC
0x1800068a4  cmp     [rax], esi
0x1800068a6  jz      short loc_1800068ED
0x1800068a8  mov     rax, [rax+8]
0x1800068ac  test    rax, rax
0x1800068af  jnz     short loc_1800068A4
0x1800068b1  test    bpl, bpl
0x1800068b4  jz      short loc_1800068F3
0x1800068b6  lea     edx, [rax+18h]; dwBytes
0x1800068b9  xor     ecx, ecx; dwFlags
0x1800068bb  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800068c0  mov     rcx, rax
0x1800068c3  test    rax, rax
0x1800068c6  jz      short loc_1800068F3
0x1800068c8  mov     [rax], esi
0x1800068ca  xor     eax, eax
0x1800068cc  mov     [rcx+4], eax
0x1800068cf  mov     [rcx+8], rax
0x1800068d3  mov     [rcx+10h], rax
0x1800068d7  mov     rax, [rdi+rbx*8]
0x1800068db  mov     [rcx+8], rax
0x1800068df  lock cmpxchg [rdi+rbx*8], rcx
0x1800068e5  jnz     short loc_1800068D7
0x1800068e7  lea     rax, [rcx+10h]
0x1800068eb  jmp     short loc_1800068F5
0x1800068ed  add     rax, 10h
0x1800068f1  jmp     short loc_1800068F5
0x1800068f3  xor     eax, eax
0x1800068f5  add     rsp, 28h
0x1800068f9  pop     rdi
0x1800068fa  pop     rsi
0x1800068fb  pop     rbp
0x1800068fc  pop     rbx
0x1800068fd  retn
```
