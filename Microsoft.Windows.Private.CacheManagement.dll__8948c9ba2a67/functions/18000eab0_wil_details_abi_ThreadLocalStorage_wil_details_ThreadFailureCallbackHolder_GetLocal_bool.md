# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000eab0`
- end: `0x18000eb74`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `196`
- prototype: `signed __int64 __fastcall(__int64, char)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800095d0`
- `0x18000eb80`

## callees

- `0x18000eab0`
- `0x180012e70`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000eacf`
- `KERNEL32!GetCurrentThreadId` at `0x18000eacf`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
signed __int64 __fastcall wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
        __int64 a1,
        char a2)
{
  __int64 v2; // rsi
  DWORD CurrentThreadId; // ebx
  unsigned __int64 v5; // r8
  __int64 v6; // r14
  __int64 v7; // rax
  _QWORD *v8; // rax
  signed __int64 v9; // rcx
  signed __int64 v10; // rax

  v2 = wil::details::g_pThreadFailureCallbacks;
  CurrentThreadId = GetCurrentThreadId();
  v5 = CurrentThreadId % 0xAuLL;
  v6 = 8 * v5;
  v7 = *(_QWORD *)(8 * v5 + v2);
  if ( v7 )
  {
    while ( *(_DWORD *)v7 != CurrentThreadId )
    {
      v7 = *(_QWORD *)(v7 + 8);
      if ( !v7 )
        goto LABEL_4;
    }
    return v7 + 16;
  }
  else
  {
LABEL_4:
    if ( a2 && (v8 = wil::details::ProcessHeapAlloc(0, 0x18u, v5), (v9 = (signed __int64)v8) != 0) )
    {
      *(_DWORD *)v8 = CurrentThreadId;
      v8[1] = 0;
      v8[2] = 0;
      do
      {
        v10 = *(_QWORD *)(v6 + v2);
        *(_QWORD *)(v9 + 8) = v10;
      }
      while ( v10 != _InterlockedCompareExchange64((volatile signed __int64 *)(v6 + v2), v9, v10) );
      return v9 + 16;
    }
    else
    {
      return 0;
    }
  }
}

```

## disassembly

```asm
0x18000eab0  mov     [rsp+arg_0], rbx
0x18000eab5  mov     [rsp+arg_8], rsi
0x18000eaba  mov     [rsp+arg_10], rdi
0x18000eabf  push    r14
0x18000eac1  sub     rsp, 20h
0x18000eac5  mov     rsi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000eacc  movzx   edi, dl
0x18000eacf  call    cs:__imp_GetCurrentThreadId
0x18000ead5  mov     r8d, eax
0x18000ead8  mov     ebx, eax
0x18000eada  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000eae4  mul     rbx
0x18000eae7  shr     rdx, 3
0x18000eaeb  lea     rcx, [rdx+rdx*4]
0x18000eaef  add     rcx, rcx
0x18000eaf2  sub     r8, rcx; unsigned __int64
0x18000eaf5  lea     r14, ds:0[r8*8]
0x18000eafd  mov     rax, [r14+rsi]
0x18000eb01  test    rax, rax
0x18000eb04  jz      short loc_18000EB13
0x18000eb06  cmp     [rax], ebx
0x18000eb08  jz      short loc_18000EB56
0x18000eb0a  mov     rax, [rax+8]
0x18000eb0e  test    rax, rax
0x18000eb11  jnz     short loc_18000EB06
0x18000eb13  test    dil, dil
0x18000eb16  jz      short loc_18000EB5C
0x18000eb18  mov     edx, 18h; dwBytes
0x18000eb1d  xor     ecx, ecx; dwFlags
0x18000eb1f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000eb24  mov     rcx, rax
0x18000eb27  test    rax, rax
0x18000eb2a  jz      short loc_18000EB5C
0x18000eb2c  mov     [rax], ebx
0x18000eb2e  xor     eax, eax
0x18000eb30  mov     [rcx+8], rax
0x18000eb34  mov     [rcx+10h], rax
0x18000eb38  nop     dword ptr [rax+rax+00000000h]
0x18000eb40  mov     rax, [r14+rsi]
0x18000eb44  mov     [rcx+8], rax
0x18000eb48  lock cmpxchg [r14+rsi], rcx
0x18000eb4e  jnz     short loc_18000EB40
0x18000eb50  lea     rax, [rcx+10h]
0x18000eb54  jmp     short loc_18000EB5E
0x18000eb56  add     rax, 10h
0x18000eb5a  jmp     short loc_18000EB5E
0x18000eb5c  xor     eax, eax
0x18000eb5e  mov     rbx, [rsp+28h+arg_0]
0x18000eb63  mov     rsi, [rsp+28h+arg_8]
0x18000eb68  mov     rdi, [rsp+28h+arg_10]
0x18000eb6d  add     rsp, 20h
0x18000eb71  pop     r14
0x18000eb73  retn
```
