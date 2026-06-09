# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000966c`
- end: `0x18000970a`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `158`
- prototype: `signed __int64 __fastcall(__int64, char)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800090e8`
- `0x18001bfe4`

## callees

- `0x18000966c`
- `0x18000b030`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000967f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000967f`

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
0x18000966c  push    rbx
0x18000966e  push    rbp
0x18000966f  push    rsi
0x180009670  push    rdi
0x180009671  sub     rsp, 28h
0x180009675  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000967c  mov     bpl, dl
0x18000967f  call    cs:__imp_GetCurrentThreadId
0x180009685  mov     ebx, eax
0x180009687  mov     esi, eax
0x180009689  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180009693  shr     rbx, 2
0x180009697  mul     rbx
0x18000969a  shr     rdx, 3
0x18000969e  lea     rcx, [rdx+rdx*4]
0x1800096a2  add     rcx, rcx
0x1800096a5  sub     rbx, rcx
0x1800096a8  mov     rax, [rdi+rbx*8]
0x1800096ac  test    rax, rax
0x1800096af  jz      short loc_1800096C1
0x1800096b1  cmp     [rax], esi
0x1800096b3  jz      short loc_1800096BB
0x1800096b5  mov     rax, [rax+8]
0x1800096b9  jmp     short loc_1800096AC
0x1800096bb  add     rax, 10h
0x1800096bf  jmp     short loc_180009701
0x1800096c1  test    bpl, bpl
0x1800096c4  jz      short loc_1800096FF
0x1800096c6  mov     edx, 18h; dwBytes
0x1800096cb  xor     ecx, ecx; dwFlags
0x1800096cd  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800096d2  mov     rcx, rax
0x1800096d5  test    rax, rax
0x1800096d8  jz      short loc_1800096FF
0x1800096da  mov     [rax], esi
0x1800096dc  xor     eax, eax
0x1800096de  mov     [rcx+4], eax
0x1800096e1  mov     [rcx+8], rax
0x1800096e5  mov     [rcx+10h], rax
0x1800096e9  mov     rax, [rdi+rbx*8]
0x1800096ed  mov     [rcx+8], rax
0x1800096f1  lock cmpxchg [rdi+rbx*8], rcx
0x1800096f7  jnz     short loc_1800096E9
0x1800096f9  lea     rax, [rcx+10h]
0x1800096fd  jmp     short loc_180009701
0x1800096ff  xor     eax, eax
0x180009701  add     rsp, 28h
0x180009705  pop     rdi
0x180009706  pop     rsi
0x180009707  pop     rbp
0x180009708  pop     rbx
0x180009709  retn
```
