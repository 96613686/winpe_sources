# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18002ab00`
- end: `0x18002ab9c`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `156`
- prototype: `signed __int64 __fastcall(__int64, char)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002e574`

## callees

- `0x18002ab00`
- `0x18002bdbc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ab13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ab13`

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
0x18002ab00  push    rbx
0x18002ab02  push    rbp
0x18002ab03  push    rsi
0x18002ab04  push    rdi
0x18002ab05  sub     rsp, 28h
0x18002ab09  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18002ab10  mov     bpl, dl
0x18002ab13  call    cs:__imp_GetCurrentThreadId
0x18002ab19  mov     ebx, eax
0x18002ab1b  mov     esi, eax
0x18002ab1d  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18002ab27  shr     rbx, 2
0x18002ab2b  mul     rbx
0x18002ab2e  shr     rdx, 3
0x18002ab32  lea     rcx, [rdx+rdx*4]
0x18002ab36  add     rcx, rcx
0x18002ab39  sub     rbx, rcx
0x18002ab3c  mov     rax, [rdi+rbx*8]
0x18002ab40  jmp     short loc_18002AB4A
0x18002ab42  cmp     [rax], esi
0x18002ab44  jz      short loc_18002AB8B
0x18002ab46  mov     rax, [rax+8]
0x18002ab4a  test    rax, rax
0x18002ab4d  jnz     short loc_18002AB42
0x18002ab4f  test    bpl, bpl
0x18002ab52  jz      short loc_18002AB91
0x18002ab54  lea     edx, [rax+18h]; dwBytes
0x18002ab57  xor     ecx, ecx; dwFlags
0x18002ab59  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18002ab5e  mov     rcx, rax
0x18002ab61  test    rax, rax
0x18002ab64  jz      short loc_18002AB91
0x18002ab66  mov     [rax], esi
0x18002ab68  xor     eax, eax
0x18002ab6a  mov     [rcx+4], eax
0x18002ab6d  mov     [rcx+8], rax
0x18002ab71  mov     [rcx+10h], rax
0x18002ab75  mov     rax, [rdi+rbx*8]
0x18002ab79  mov     [rcx+8], rax
0x18002ab7d  lock cmpxchg [rdi+rbx*8], rcx
0x18002ab83  jnz     short loc_18002AB75
0x18002ab85  lea     rax, [rcx+10h]
0x18002ab89  jmp     short loc_18002AB93
0x18002ab8b  add     rax, 10h
0x18002ab8f  jmp     short loc_18002AB93
0x18002ab91  xor     eax, eax
0x18002ab93  add     rsp, 28h
0x18002ab97  pop     rdi
0x18002ab98  pop     rsi
0x18002ab99  pop     rbp
0x18002ab9a  pop     rbx
0x18002ab9b  retn
```
