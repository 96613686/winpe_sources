# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x14000576c`
- end: `0x14000580a`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `158`
- prototype: `signed __int64 __fastcall(__int64, char)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140005234`
- `0x14000e2d4`

## callees

- `0x14000576c`
- `0x140006638`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000577f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000577f`

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
  DWORD *v9; // rax
  signed __int64 v10; // rcx
  signed __int64 v11; // rax

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
  v9 = (DWORD *)wil::details::ProcessHeapAlloc(0, 0x18u, v5);
  v10 = (signed __int64)v9;
  if ( !v9 )
    return 0;
  *v9 = CurrentThreadId;
  v9[1] = 0;
  *((_QWORD *)v9 + 1) = 0;
  *((_QWORD *)v9 + 2) = 0;
  do
  {
    v11 = *(_QWORD *)(v2 + 8 * v6);
    *(_QWORD *)(v10 + 8) = v11;
  }
  while ( v11 != _InterlockedCompareExchange64((volatile signed __int64 *)(v2 + 8 * v6), v10, v11) );
  return v10 + 16;
}

```

## disassembly

```asm
0x14000576c  push    rbx
0x14000576e  push    rbp
0x14000576f  push    rsi
0x140005770  push    rdi
0x140005771  sub     rsp, 28h
0x140005775  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x14000577c  mov     bpl, dl
0x14000577f  call    cs:__imp_GetCurrentThreadId
0x140005785  mov     ebx, eax
0x140005787  mov     esi, eax
0x140005789  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140005793  shr     rbx, 2
0x140005797  mul     rbx
0x14000579a  shr     rdx, 3
0x14000579e  lea     rcx, [rdx+rdx*4]
0x1400057a2  add     rcx, rcx
0x1400057a5  sub     rbx, rcx
0x1400057a8  mov     rax, [rdi+rbx*8]
0x1400057ac  test    rax, rax
0x1400057af  jz      short loc_1400057C1
0x1400057b1  cmp     [rax], esi
0x1400057b3  jz      short loc_1400057BB
0x1400057b5  mov     rax, [rax+8]
0x1400057b9  jmp     short loc_1400057AC
0x1400057bb  add     rax, 10h
0x1400057bf  jmp     short loc_140005801
0x1400057c1  test    bpl, bpl
0x1400057c4  jz      short loc_1400057FF
0x1400057c6  mov     edx, 18h; dwBytes
0x1400057cb  xor     ecx, ecx; dwFlags
0x1400057cd  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400057d2  mov     rcx, rax
0x1400057d5  test    rax, rax
0x1400057d8  jz      short loc_1400057FF
0x1400057da  mov     [rax], esi
0x1400057dc  xor     eax, eax
0x1400057de  mov     [rcx+4], eax
0x1400057e1  mov     [rcx+8], rax
0x1400057e5  mov     [rcx+10h], rax
0x1400057e9  mov     rax, [rdi+rbx*8]
0x1400057ed  mov     [rcx+8], rax
0x1400057f1  lock cmpxchg [rdi+rbx*8], rcx
0x1400057f7  jnz     short loc_1400057E9
0x1400057f9  lea     rax, [rcx+10h]
0x1400057fd  jmp     short loc_140005801
0x1400057ff  xor     eax, eax
0x140005801  add     rsp, 28h
0x140005805  pop     rdi
0x140005806  pop     rsi
0x140005807  pop     rbp
0x140005808  pop     rbx
0x140005809  retn
```
