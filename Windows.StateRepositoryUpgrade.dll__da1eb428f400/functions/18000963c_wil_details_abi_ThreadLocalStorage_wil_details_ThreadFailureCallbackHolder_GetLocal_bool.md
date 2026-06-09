# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000963c`
- end: `0x1800096da`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `158`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009164`
- `0x180017a50`

## callees

- `0x18000963c`
- `0x18000a1e8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000964f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000964f`

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
0x18000963c  push    rbx
0x18000963e  push    rbp
0x18000963f  push    rsi
0x180009640  push    rdi
0x180009641  sub     rsp, 28h
0x180009645  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000964c  mov     bpl, dl
0x18000964f  call    cs:__imp_GetCurrentThreadId
0x180009655  mov     ebx, eax
0x180009657  mov     esi, eax
0x180009659  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180009663  shr     rbx, 2
0x180009667  mul     rbx
0x18000966a  shr     rdx, 3
0x18000966e  lea     rcx, [rdx+rdx*4]
0x180009672  add     rcx, rcx
0x180009675  sub     rbx, rcx
0x180009678  mov     rax, [rdi+rbx*8]
0x18000967c  test    rax, rax
0x18000967f  jz      short loc_180009691
0x180009681  cmp     [rax], esi
0x180009683  jz      short loc_18000968B
0x180009685  mov     rax, [rax+8]
0x180009689  jmp     short loc_18000967C
0x18000968b  add     rax, 10h
0x18000968f  jmp     short loc_1800096D1
0x180009691  test    bpl, bpl
0x180009694  jz      short loc_1800096CF
0x180009696  mov     edx, 18h; dwBytes
0x18000969b  xor     ecx, ecx; dwFlags
0x18000969d  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800096a2  mov     rcx, rax
0x1800096a5  test    rax, rax
0x1800096a8  jz      short loc_1800096CF
0x1800096aa  mov     [rax], esi
0x1800096ac  xor     eax, eax
0x1800096ae  mov     [rcx+4], eax
0x1800096b1  mov     [rcx+8], rax
0x1800096b5  mov     [rcx+10h], rax
0x1800096b9  mov     rax, [rdi+rbx*8]
0x1800096bd  mov     [rcx+8], rax
0x1800096c1  lock cmpxchg [rdi+rbx*8], rcx
0x1800096c7  jnz     short loc_1800096B9
0x1800096c9  lea     rax, [rcx+10h]
0x1800096cd  jmp     short loc_1800096D1
0x1800096cf  xor     eax, eax
0x1800096d1  add     rsp, 28h
0x1800096d5  pop     rdi
0x1800096d6  pop     rsi
0x1800096d7  pop     rbp
0x1800096d8  pop     rbx
0x1800096d9  retn
```
