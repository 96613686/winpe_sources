# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1800091b8`
- end: `0x180009267`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180035e54`

## callees

- `0x18000650c`
- `0x1800091b8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800091d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800091d6`

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
  v6 = CurrentThreadId % 0xAuLL;
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
0x1800091b8  mov     [rsp+arg_0], rbx
0x1800091bd  mov     [rsp+arg_8], rbp
0x1800091c2  mov     [rsp+arg_10], rsi
0x1800091c7  push    rdi
0x1800091c8  sub     rsp, 20h
0x1800091cc  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800091d3  mov     bpl, dl
0x1800091d6  call    cs:__imp_GetCurrentThreadId
0x1800091dc  mov     ebx, eax
0x1800091de  mov     esi, eax
0x1800091e0  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800091ea  mul     rsi
0x1800091ed  shr     rdx, 3
0x1800091f1  lea     rcx, [rdx+rdx*4]
0x1800091f5  add     rcx, rcx
0x1800091f8  sub     rbx, rcx
0x1800091fb  mov     rax, [rdi+rbx*8]
0x1800091ff  jmp     short loc_180009209
0x180009201  cmp     [rax], esi
0x180009203  jz      short loc_18000924A
0x180009205  mov     rax, [rax+8]
0x180009209  test    rax, rax
0x18000920c  jnz     short loc_180009201
0x18000920e  test    bpl, bpl
0x180009211  jz      short loc_180009250
0x180009213  lea     edx, [rax+18h]; dwBytes
0x180009216  xor     ecx, ecx; dwFlags
0x180009218  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000921d  mov     rcx, rax
0x180009220  test    rax, rax
0x180009223  jz      short loc_180009250
0x180009225  mov     [rax], esi
0x180009227  xor     eax, eax
0x180009229  mov     [rcx+4], eax
0x18000922c  mov     [rcx+8], rax
0x180009230  mov     [rcx+10h], rax
0x180009234  mov     rax, [rdi+rbx*8]
0x180009238  mov     [rcx+8], rax
0x18000923c  lock cmpxchg [rdi+rbx*8], rcx
0x180009242  jnz     short loc_180009234
0x180009244  lea     rax, [rcx+10h]
0x180009248  jmp     short loc_180009252
0x18000924a  add     rax, 10h
0x18000924e  jmp     short loc_180009252
0x180009250  xor     eax, eax
0x180009252  mov     rbx, [rsp+28h+arg_0]
0x180009257  mov     rbp, [rsp+28h+arg_8]
0x18000925c  mov     rsi, [rsp+28h+arg_10]
0x180009261  add     rsp, 20h
0x180009265  pop     rdi
0x180009266  retn
```
