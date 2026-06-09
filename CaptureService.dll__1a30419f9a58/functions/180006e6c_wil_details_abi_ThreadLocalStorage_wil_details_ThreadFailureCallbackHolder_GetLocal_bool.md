# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180006e6c`
- end: `0x180006f0a`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `158`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006974`
- `0x180015070`

## callees

- `0x180006e6c`
- `0x18000819c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006e7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006e7f`

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
0x180006e6c  push    rbx
0x180006e6e  push    rbp
0x180006e6f  push    rsi
0x180006e70  push    rdi
0x180006e71  sub     rsp, 28h
0x180006e75  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180006e7c  mov     bpl, dl
0x180006e7f  call    cs:__imp_GetCurrentThreadId
0x180006e85  mov     ebx, eax
0x180006e87  mov     esi, eax
0x180006e89  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006e93  shr     rbx, 2
0x180006e97  mul     rbx
0x180006e9a  shr     rdx, 3
0x180006e9e  lea     rcx, [rdx+rdx*4]
0x180006ea2  add     rcx, rcx
0x180006ea5  sub     rbx, rcx
0x180006ea8  mov     rax, [rdi+rbx*8]
0x180006eac  test    rax, rax
0x180006eaf  jz      short loc_180006EC1
0x180006eb1  cmp     [rax], esi
0x180006eb3  jz      short loc_180006EBB
0x180006eb5  mov     rax, [rax+8]
0x180006eb9  jmp     short loc_180006EAC
0x180006ebb  add     rax, 10h
0x180006ebf  jmp     short loc_180006F01
0x180006ec1  test    bpl, bpl
0x180006ec4  jz      short loc_180006EFF
0x180006ec6  mov     edx, 18h; dwBytes
0x180006ecb  xor     ecx, ecx; dwFlags
0x180006ecd  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006ed2  mov     rcx, rax
0x180006ed5  test    rax, rax
0x180006ed8  jz      short loc_180006EFF
0x180006eda  mov     [rax], esi
0x180006edc  xor     eax, eax
0x180006ede  mov     [rcx+4], eax
0x180006ee1  mov     [rcx+8], rax
0x180006ee5  mov     [rcx+10h], rax
0x180006ee9  mov     rax, [rdi+rbx*8]
0x180006eed  mov     [rcx+8], rax
0x180006ef1  lock cmpxchg [rdi+rbx*8], rcx
0x180006ef7  jnz     short loc_180006EE9
0x180006ef9  lea     rax, [rcx+10h]
0x180006efd  jmp     short loc_180006F01
0x180006eff  xor     eax, eax
0x180006f01  add     rsp, 28h
0x180006f05  pop     rdi
0x180006f06  pop     rsi
0x180006f07  pop     rbp
0x180006f08  pop     rbx
0x180006f09  retn
```
