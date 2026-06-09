# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1800049bc`
- end: `0x180004a5f`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `163`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009df0`
- `0x180009f44`
- `0x18000a098`
- `0x18000a1ec`
- `0x18000a340`
- `0x18000a494`
- `0x18000a5d4`
- `0x18000a714`
- `0x18000a868`

## callees

- `0x1800049bc`
- `0x1800057b4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800049cf`
- `KERNEL32!GetCurrentThreadId` at `0x1800049cf`

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
0x1800049bc  push    rbx
0x1800049be  push    rbp
0x1800049bf  push    rsi
0x1800049c0  push    rdi
0x1800049c1  sub     rsp, 28h
0x1800049c5  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800049cc  mov     bpl, dl
0x1800049cf  call    cs:__imp_GetCurrentThreadId
0x1800049d6  nop     dword ptr [rax+rax+00h]
0x1800049db  mov     ebx, eax
0x1800049dd  mov     esi, eax
0x1800049df  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800049e9  shr     rbx, 2
0x1800049ed  mul     rbx
0x1800049f0  shr     rdx, 3
0x1800049f4  lea     rcx, [rdx+rdx*4]
0x1800049f8  add     rcx, rcx
0x1800049fb  sub     rbx, rcx
0x1800049fe  mov     rax, [rdi+rbx*8]
0x180004a02  jmp     short loc_180004A0C
0x180004a04  cmp     [rax], esi
0x180004a06  jz      short loc_180004A4D
0x180004a08  mov     rax, [rax+8]
0x180004a0c  test    rax, rax
0x180004a0f  jnz     short loc_180004A04
0x180004a11  test    bpl, bpl
0x180004a14  jz      short loc_180004A53
0x180004a16  lea     edx, [rax+18h]; dwBytes
0x180004a19  xor     ecx, ecx; dwFlags
0x180004a1b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004a20  mov     rcx, rax
0x180004a23  test    rax, rax
0x180004a26  jz      short loc_180004A53
0x180004a28  mov     [rax], esi
0x180004a2a  xor     eax, eax
0x180004a2c  mov     [rcx+4], eax
0x180004a2f  mov     [rcx+8], rax
0x180004a33  mov     [rcx+10h], rax
0x180004a37  mov     rax, [rdi+rbx*8]
0x180004a3b  mov     [rcx+8], rax
0x180004a3f  lock cmpxchg [rdi+rbx*8], rcx
0x180004a45  jnz     short loc_180004A37
0x180004a47  lea     rax, [rcx+10h]
0x180004a4b  jmp     short loc_180004A55
0x180004a4d  add     rax, 10h
0x180004a51  jmp     short loc_180004A55
0x180004a53  xor     eax, eax
0x180004a55  add     rsp, 28h
0x180004a59  pop     rdi
0x180004a5a  pop     rsi
0x180004a5b  pop     rbp
0x180004a5c  pop     rbx
0x180004a5d  retn
```
