# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000bf9c`
- end: `0x18000c03a`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000baac`

## callees

- `0x18000bf9c`
- `0x18000d340`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bfaf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bfaf`

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
0x18000bf9c  push    rbx
0x18000bf9e  push    rbp
0x18000bf9f  push    rsi
0x18000bfa0  push    rdi
0x18000bfa1  sub     rsp, 28h
0x18000bfa5  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000bfac  mov     bpl, dl
0x18000bfaf  call    cs:__imp_GetCurrentThreadId
0x18000bfb5  mov     ebx, eax
0x18000bfb7  mov     esi, eax
0x18000bfb9  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000bfc3  shr     rbx, 2
0x18000bfc7  mul     rbx
0x18000bfca  shr     rdx, 3
0x18000bfce  lea     rcx, [rdx+rdx*4]
0x18000bfd2  add     rcx, rcx
0x18000bfd5  sub     rbx, rcx
0x18000bfd8  mov     rax, [rdi+rbx*8]
0x18000bfdc  test    rax, rax
0x18000bfdf  jz      short loc_18000BFF1
0x18000bfe1  cmp     [rax], esi
0x18000bfe3  jz      short loc_18000BFEB
0x18000bfe5  mov     rax, [rax+8]
0x18000bfe9  jmp     short loc_18000BFDC
0x18000bfeb  add     rax, 10h
0x18000bfef  jmp     short loc_18000C031
0x18000bff1  test    bpl, bpl
0x18000bff4  jz      short loc_18000C02F
0x18000bff6  mov     edx, 18h; dwBytes
0x18000bffb  xor     ecx, ecx; dwFlags
0x18000bffd  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000c002  mov     rcx, rax
0x18000c005  test    rax, rax
0x18000c008  jz      short loc_18000C02F
0x18000c00a  mov     [rax], esi
0x18000c00c  xor     eax, eax
0x18000c00e  mov     [rcx+4], eax
0x18000c011  mov     [rcx+8], rax
0x18000c015  mov     [rcx+10h], rax
0x18000c019  mov     rax, [rdi+rbx*8]
0x18000c01d  mov     [rcx+8], rax
0x18000c021  lock cmpxchg [rdi+rbx*8], rcx
0x18000c027  jnz     short loc_18000C019
0x18000c029  lea     rax, [rcx+10h]
0x18000c02d  jmp     short loc_18000C031
0x18000c02f  xor     eax, eax
0x18000c031  add     rsp, 28h
0x18000c035  pop     rdi
0x18000c036  pop     rsi
0x18000c037  pop     rbp
0x18000c038  pop     rbx
0x18000c039  retn
```
