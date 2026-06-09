# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1800058fc`
- end: `0x180005998`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180019810`

## callees

- `0x1800058fc`
- `0x1800065d8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000590f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000590f`

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
0x1800058fc  push    rbx
0x1800058fe  push    rbp
0x1800058ff  push    rsi
0x180005900  push    rdi
0x180005901  sub     rsp, 28h
0x180005905  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000590c  mov     bpl, dl
0x18000590f  call    cs:__imp_GetCurrentThreadId
0x180005915  mov     ebx, eax
0x180005917  mov     esi, eax
0x180005919  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005923  shr     rbx, 2
0x180005927  mul     rbx
0x18000592a  shr     rdx, 3
0x18000592e  lea     rcx, [rdx+rdx*4]
0x180005932  add     rcx, rcx
0x180005935  sub     rbx, rcx
0x180005938  mov     rax, [rdi+rbx*8]
0x18000593c  jmp     short loc_180005946
0x18000593e  cmp     [rax], esi
0x180005940  jz      short loc_180005987
0x180005942  mov     rax, [rax+8]
0x180005946  test    rax, rax
0x180005949  jnz     short loc_18000593E
0x18000594b  test    bpl, bpl
0x18000594e  jz      short loc_18000598D
0x180005950  lea     edx, [rax+18h]; dwBytes
0x180005953  xor     ecx, ecx; dwFlags
0x180005955  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000595a  mov     rcx, rax
0x18000595d  test    rax, rax
0x180005960  jz      short loc_18000598D
0x180005962  mov     [rax], esi
0x180005964  xor     eax, eax
0x180005966  mov     [rcx+4], eax
0x180005969  mov     [rcx+8], rax
0x18000596d  mov     [rcx+10h], rax
0x180005971  mov     rax, [rdi+rbx*8]
0x180005975  mov     [rcx+8], rax
0x180005979  lock cmpxchg [rdi+rbx*8], rcx
0x18000597f  jnz     short loc_180005971
0x180005981  lea     rax, [rcx+10h]
0x180005985  jmp     short loc_18000598F
0x180005987  add     rax, 10h
0x18000598b  jmp     short loc_18000598F
0x18000598d  xor     eax, eax
0x18000598f  add     rsp, 28h
0x180005993  pop     rdi
0x180005994  pop     rsi
0x180005995  pop     rbp
0x180005996  pop     rbx
0x180005997  retn
```
