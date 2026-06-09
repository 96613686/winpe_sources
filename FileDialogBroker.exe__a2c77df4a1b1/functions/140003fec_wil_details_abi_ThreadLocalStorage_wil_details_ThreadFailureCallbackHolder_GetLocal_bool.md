# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x140003fec`
- end: `0x14000408a`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `158`
- prototype: `signed __int64 __fastcall(__int64, char)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140003b14`
- `0x14000f8d0`

## callees

- `0x140003fec`
- `0x140004c68`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003fff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003fff`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x140003fec  push    rbx
0x140003fee  push    rbp
0x140003fef  push    rsi
0x140003ff0  push    rdi
0x140003ff1  sub     rsp, 28h
0x140003ff5  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140003ffc  mov     bpl, dl
0x140003fff  call    cs:__imp_GetCurrentThreadId
0x140004005  mov     ebx, eax
0x140004007  mov     esi, eax
0x140004009  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140004013  shr     rbx, 2
0x140004017  mul     rbx
0x14000401a  shr     rdx, 3
0x14000401e  lea     rcx, [rdx+rdx*4]
0x140004022  add     rcx, rcx
0x140004025  sub     rbx, rcx
0x140004028  mov     rax, [rdi+rbx*8]
0x14000402c  test    rax, rax
0x14000402f  jz      short loc_140004041
0x140004031  cmp     [rax], esi
0x140004033  jz      short loc_14000403B
0x140004035  mov     rax, [rax+8]
0x140004039  jmp     short loc_14000402C
0x14000403b  add     rax, 10h
0x14000403f  jmp     short loc_140004081
0x140004041  test    bpl, bpl
0x140004044  jz      short loc_14000407F
0x140004046  mov     edx, 18h; dwBytes
0x14000404b  xor     ecx, ecx; dwFlags
0x14000404d  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140004052  mov     rcx, rax
0x140004055  test    rax, rax
0x140004058  jz      short loc_14000407F
0x14000405a  mov     [rax], esi
0x14000405c  xor     eax, eax
0x14000405e  mov     [rcx+4], eax
0x140004061  mov     [rcx+8], rax
0x140004065  mov     [rcx+10h], rax
0x140004069  mov     rax, [rdi+rbx*8]
0x14000406d  mov     [rcx+8], rax
0x140004071  lock cmpxchg [rdi+rbx*8], rcx
0x140004077  jnz     short loc_140004069
0x140004079  lea     rax, [rcx+10h]
0x14000407d  jmp     short loc_140004081
0x14000407f  xor     eax, eax
0x140004081  add     rsp, 28h
0x140004085  pop     rdi
0x140004086  pop     rsi
0x140004087  pop     rbp
0x140004088  pop     rbx
0x140004089  retn
```
