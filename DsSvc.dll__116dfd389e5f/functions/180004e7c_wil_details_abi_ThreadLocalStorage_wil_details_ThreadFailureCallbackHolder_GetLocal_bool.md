# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180004e7c`
- end: `0x180004f1a`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `158`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800049a4`
- `0x18000ea58`

## callees

- `0x180004e7c`
- `0x180005b7c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004e8f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004e8f`

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
0x180004e7c  push    rbx
0x180004e7e  push    rbp
0x180004e7f  push    rsi
0x180004e80  push    rdi
0x180004e81  sub     rsp, 28h
0x180004e85  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004e8c  mov     bpl, dl
0x180004e8f  call    cs:__imp_GetCurrentThreadId
0x180004e95  mov     ebx, eax
0x180004e97  mov     esi, eax
0x180004e99  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004ea3  shr     rbx, 2
0x180004ea7  mul     rbx
0x180004eaa  shr     rdx, 3
0x180004eae  lea     rcx, [rdx+rdx*4]
0x180004eb2  add     rcx, rcx
0x180004eb5  sub     rbx, rcx
0x180004eb8  mov     rax, [rdi+rbx*8]
0x180004ebc  test    rax, rax
0x180004ebf  jz      short loc_180004ED1
0x180004ec1  cmp     [rax], esi
0x180004ec3  jz      short loc_180004ECB
0x180004ec5  mov     rax, [rax+8]
0x180004ec9  jmp     short loc_180004EBC
0x180004ecb  add     rax, 10h
0x180004ecf  jmp     short loc_180004F11
0x180004ed1  test    bpl, bpl
0x180004ed4  jz      short loc_180004F0F
0x180004ed6  mov     edx, 18h; dwBytes
0x180004edb  xor     ecx, ecx; dwFlags
0x180004edd  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004ee2  mov     rcx, rax
0x180004ee5  test    rax, rax
0x180004ee8  jz      short loc_180004F0F
0x180004eea  mov     [rax], esi
0x180004eec  xor     eax, eax
0x180004eee  mov     [rcx+4], eax
0x180004ef1  mov     [rcx+8], rax
0x180004ef5  mov     [rcx+10h], rax
0x180004ef9  mov     rax, [rdi+rbx*8]
0x180004efd  mov     [rcx+8], rax
0x180004f01  lock cmpxchg [rdi+rbx*8], rcx
0x180004f07  jnz     short loc_180004EF9
0x180004f09  lea     rax, [rcx+10h]
0x180004f0d  jmp     short loc_180004F11
0x180004f0f  xor     eax, eax
0x180004f11  add     rsp, 28h
0x180004f15  pop     rdi
0x180004f16  pop     rsi
0x180004f17  pop     rbp
0x180004f18  pop     rbx
0x180004f19  retn
```
