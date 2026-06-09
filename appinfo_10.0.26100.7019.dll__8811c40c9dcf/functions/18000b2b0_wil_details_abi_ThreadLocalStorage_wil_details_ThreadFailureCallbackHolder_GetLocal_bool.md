# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000b2b0`
- end: `0x18000b371`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800190f4`

## callees

- `0x18000b2b0`
- `0x180019798`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b2ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b2ce`

## pseudocode

```c
signed __int64 __fastcall wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
        __int64 a1,
        char a2)
{
  __int64 v2; // rdi
  DWORD CurrentThreadId; // ebx
  unsigned __int64 v5; // r8
  __int64 v6; // rsi
  __int64 i; // rax
  DWORD *v9; // rax
  signed __int64 v10; // rcx
  signed __int64 v11; // rax

  v2 = wil::details::g_pThreadFailureCallbacks;
  CurrentThreadId = GetCurrentThreadId();
  v5 = CurrentThreadId % 0xAuLL;
  v6 = 8 * v5;
  for ( i = *(_QWORD *)(8 * v5 + v2); i; i = *(_QWORD *)(i + 8) )
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
    v11 = *(_QWORD *)(v6 + v2);
    *(_QWORD *)(v10 + 8) = v11;
  }
  while ( v11 != _InterlockedCompareExchange64((volatile signed __int64 *)(v6 + v2), v10, v11) );
  return v10 + 16;
}

```

## disassembly

```asm
0x18000b2b0  mov     [rsp+arg_0], rbx
0x18000b2b5  mov     [rsp+arg_8], rbp
0x18000b2ba  mov     [rsp+arg_10], rsi
0x18000b2bf  push    rdi
0x18000b2c0  sub     rsp, 20h
0x18000b2c4  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000b2cb  movzx   ebp, dl
0x18000b2ce  call    cs:__imp_GetCurrentThreadId
0x18000b2d5  nop     dword ptr [rax+rax+00h]
0x18000b2da  mov     r8d, eax
0x18000b2dd  mov     ebx, eax
0x18000b2df  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000b2e9  mul     rbx
0x18000b2ec  shr     rdx, 3
0x18000b2f0  lea     rcx, [rdx+rdx*4]
0x18000b2f4  add     rcx, rcx
0x18000b2f7  sub     r8, rcx; unsigned __int64
0x18000b2fa  lea     rsi, ds:0[r8*8]
0x18000b302  mov     rax, [rsi+rdi]
0x18000b306  test    rax, rax
0x18000b309  jz      short loc_18000B32F
0x18000b30b  cmp     [rax], ebx
0x18000b30d  jz      short loc_18000B315
0x18000b30f  mov     rax, [rax+8]
0x18000b313  jmp     short loc_18000B306
0x18000b315  add     rax, 10h
0x18000b319  mov     rbx, [rsp+28h+arg_0]
0x18000b31e  mov     rbp, [rsp+28h+arg_8]
0x18000b323  mov     rsi, [rsp+28h+arg_10]
0x18000b328  add     rsp, 20h
0x18000b32c  pop     rdi
0x18000b32d  retn
0x18000b32f  test    bpl, bpl
0x18000b332  jz      short loc_18000B36D
0x18000b334  mov     edx, 18h; dwBytes
0x18000b339  xor     ecx, ecx; dwFlags
0x18000b33b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000b340  mov     rcx, rax
0x18000b343  test    rax, rax
0x18000b346  jz      short loc_18000B36D
0x18000b348  mov     [rax], ebx
0x18000b34a  xor     eax, eax
0x18000b34c  mov     [rcx+4], eax
0x18000b34f  mov     [rcx+8], rax
0x18000b353  mov     [rcx+10h], rax
0x18000b357  mov     rax, [rsi+rdi]
0x18000b35b  mov     [rcx+8], rax
0x18000b35f  lock cmpxchg [rsi+rdi], rcx
0x18000b365  jnz     short loc_18000B357
0x18000b367  lea     rax, [rcx+10h]
0x18000b36b  jmp     short loc_18000B319
0x18000b36d  xor     eax, eax
0x18000b36f  jmp     short loc_18000B319
```
