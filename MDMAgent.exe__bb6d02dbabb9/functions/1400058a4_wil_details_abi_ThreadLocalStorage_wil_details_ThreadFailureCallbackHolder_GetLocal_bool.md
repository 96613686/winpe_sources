# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1400058a4`
- end: `0x140005949`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `165`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400053a4`
- `0x1400177fc`

## callees

- `0x1400058a4`
- `0x140006798`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400058b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400058b7`

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
0x1400058a4  push    rbx
0x1400058a6  push    rbp
0x1400058a7  push    rsi
0x1400058a8  push    rdi
0x1400058a9  sub     rsp, 28h
0x1400058ad  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1400058b4  mov     bpl, dl
0x1400058b7  call    cs:__imp_GetCurrentThreadId
0x1400058be  nop     dword ptr [rax+rax+00h]
0x1400058c3  mov     ebx, eax
0x1400058c5  mov     esi, eax
0x1400058c7  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400058d1  shr     rbx, 2
0x1400058d5  mul     rbx
0x1400058d8  shr     rdx, 3
0x1400058dc  lea     rcx, [rdx+rdx*4]
0x1400058e0  add     rcx, rcx
0x1400058e3  sub     rbx, rcx
0x1400058e6  mov     rax, [rdi+rbx*8]
0x1400058ea  test    rax, rax
0x1400058ed  jz      short loc_1400058FF
0x1400058ef  cmp     [rax], esi
0x1400058f1  jz      short loc_1400058F9
0x1400058f3  mov     rax, [rax+8]
0x1400058f7  jmp     short loc_1400058EA
0x1400058f9  add     rax, 10h
0x1400058fd  jmp     short loc_14000593F
0x1400058ff  test    bpl, bpl
0x140005902  jz      short loc_14000593D
0x140005904  mov     edx, 18h; dwBytes
0x140005909  xor     ecx, ecx; dwFlags
0x14000590b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140005910  mov     rcx, rax
0x140005913  test    rax, rax
0x140005916  jz      short loc_14000593D
0x140005918  mov     [rax], esi
0x14000591a  xor     eax, eax
0x14000591c  mov     [rcx+4], eax
0x14000591f  mov     [rcx+8], rax
0x140005923  mov     [rcx+10h], rax
0x140005927  mov     rax, [rdi+rbx*8]
0x14000592b  mov     [rcx+8], rax
0x14000592f  lock cmpxchg [rdi+rbx*8], rcx
0x140005935  jnz     short loc_140005927
0x140005937  lea     rax, [rcx+10h]
0x14000593b  jmp     short loc_14000593F
0x14000593d  xor     eax, eax
0x14000593f  add     rsp, 28h
0x140005943  pop     rdi
0x140005944  pop     rsi
0x140005945  pop     rbp
0x140005946  pop     rbx
0x140005947  retn
```
