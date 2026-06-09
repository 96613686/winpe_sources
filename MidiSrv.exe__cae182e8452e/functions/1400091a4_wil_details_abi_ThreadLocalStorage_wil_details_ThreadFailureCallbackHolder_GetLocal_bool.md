# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1400091a4`
- end: `0x140009240`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `156`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14003d0b0`
- `0x14003dae0`

## callees

- `0x1400091a4`
- `0x140009a8c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400091b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400091b7`

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
0x1400091a4  push    rbx
0x1400091a6  push    rbp
0x1400091a7  push    rsi
0x1400091a8  push    rdi
0x1400091a9  sub     rsp, 28h
0x1400091ad  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1400091b4  mov     bpl, dl
0x1400091b7  call    cs:__imp_GetCurrentThreadId
0x1400091bd  mov     ebx, eax
0x1400091bf  mov     esi, eax
0x1400091c1  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400091cb  shr     rbx, 2
0x1400091cf  mul     rbx
0x1400091d2  shr     rdx, 3
0x1400091d6  lea     rcx, [rdx+rdx*4]
0x1400091da  add     rcx, rcx
0x1400091dd  sub     rbx, rcx
0x1400091e0  mov     rax, [rdi+rbx*8]
0x1400091e4  jmp     short loc_1400091EE
0x1400091e6  cmp     [rax], esi
0x1400091e8  jz      short loc_14000922F
0x1400091ea  mov     rax, [rax+8]
0x1400091ee  test    rax, rax
0x1400091f1  jnz     short loc_1400091E6
0x1400091f3  test    bpl, bpl
0x1400091f6  jz      short loc_140009235
0x1400091f8  lea     edx, [rax+18h]; dwBytes
0x1400091fb  xor     ecx, ecx; dwFlags
0x1400091fd  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140009202  mov     rcx, rax
0x140009205  test    rax, rax
0x140009208  jz      short loc_140009235
0x14000920a  mov     [rax], esi
0x14000920c  xor     eax, eax
0x14000920e  mov     [rcx+4], eax
0x140009211  mov     [rcx+8], rax
0x140009215  mov     [rcx+10h], rax
0x140009219  mov     rax, [rdi+rbx*8]
0x14000921d  mov     [rcx+8], rax
0x140009221  lock cmpxchg [rdi+rbx*8], rcx
0x140009227  jnz     short loc_140009219
0x140009229  lea     rax, [rcx+10h]
0x14000922d  jmp     short loc_140009237
0x14000922f  add     rax, 10h
0x140009233  jmp     short loc_140009237
0x140009235  xor     eax, eax
0x140009237  add     rsp, 28h
0x14000923b  pop     rdi
0x14000923c  pop     rsi
0x14000923d  pop     rbp
0x14000923e  pop     rbx
0x14000923f  retn
```
