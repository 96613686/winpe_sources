# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1400068f0`
- end: `0x14000698c`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `156`
- prototype: `signed __int64 __fastcall(__int64, char)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140014c1c`
- `0x140014f68`
- `0x14001582c`
- `0x140018dc4`

## callees

- `0x1400068f0`
- `0x14000770c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006903`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006903`

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
0x1400068f0  push    rbx
0x1400068f2  push    rbp
0x1400068f3  push    rsi
0x1400068f4  push    rdi
0x1400068f5  sub     rsp, 28h
0x1400068f9  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140006900  mov     bpl, dl
0x140006903  call    cs:__imp_GetCurrentThreadId
0x140006909  mov     ebx, eax
0x14000690b  mov     esi, eax
0x14000690d  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140006917  shr     rbx, 2
0x14000691b  mul     rbx
0x14000691e  shr     rdx, 3
0x140006922  lea     rcx, [rdx+rdx*4]
0x140006926  add     rcx, rcx
0x140006929  sub     rbx, rcx
0x14000692c  mov     rax, [rdi+rbx*8]
0x140006930  jmp     short loc_14000693A
0x140006932  cmp     [rax], esi
0x140006934  jz      short loc_14000697B
0x140006936  mov     rax, [rax+8]
0x14000693a  test    rax, rax
0x14000693d  jnz     short loc_140006932
0x14000693f  test    bpl, bpl
0x140006942  jz      short loc_140006981
0x140006944  lea     edx, [rax+18h]; dwBytes
0x140006947  xor     ecx, ecx; dwFlags
0x140006949  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000694e  mov     rcx, rax
0x140006951  test    rax, rax
0x140006954  jz      short loc_140006981
0x140006956  mov     [rax], esi
0x140006958  xor     eax, eax
0x14000695a  mov     [rcx+4], eax
0x14000695d  mov     [rcx+8], rax
0x140006961  mov     [rcx+10h], rax
0x140006965  mov     rax, [rdi+rbx*8]
0x140006969  mov     [rcx+8], rax
0x14000696d  lock cmpxchg [rdi+rbx*8], rcx
0x140006973  jnz     short loc_140006965
0x140006975  lea     rax, [rcx+10h]
0x140006979  jmp     short loc_140006983
0x14000697b  add     rax, 10h
0x14000697f  jmp     short loc_140006983
0x140006981  xor     eax, eax
0x140006983  add     rsp, 28h
0x140006987  pop     rdi
0x140006988  pop     rsi
0x140006989  pop     rbp
0x14000698a  pop     rbx
0x14000698b  retn
```
