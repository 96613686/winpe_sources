# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18001a570`
- end: `0x18001a634`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `196`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001a640`
- `0x180052c90`
- `0x180053610`
- `0x1800583b0`
- `0x18005bc90`

## callees

- `0x180006f50`
- `0x18001a570`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001a58f`
- `KERNEL32!GetCurrentThreadId` at `0x18001a58f`

## pseudocode

```c
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
0x18001a570  mov     [rsp+arg_0], rbx
0x18001a575  mov     [rsp+arg_8], rsi
0x18001a57a  mov     [rsp+arg_10], rdi
0x18001a57f  push    r14
0x18001a581  sub     rsp, 20h
0x18001a585  mov     rsi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001a58c  movzx   edi, dl
0x18001a58f  call    cs:__imp_GetCurrentThreadId
0x18001a595  mov     r8d, eax
0x18001a598  mov     ebx, eax
0x18001a59a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001a5a4  mul     rbx
0x18001a5a7  shr     rdx, 3
0x18001a5ab  lea     rcx, [rdx+rdx*4]
0x18001a5af  add     rcx, rcx
0x18001a5b2  sub     r8, rcx; unsigned __int64
0x18001a5b5  lea     r14, ds:0[r8*8]
0x18001a5bd  mov     rax, [r14+rsi]
0x18001a5c1  test    rax, rax
0x18001a5c4  jz      short loc_18001A5D3
0x18001a5c6  cmp     [rax], ebx
0x18001a5c8  jz      short loc_18001A616
0x18001a5ca  mov     rax, [rax+8]
0x18001a5ce  test    rax, rax
0x18001a5d1  jnz     short loc_18001A5C6
0x18001a5d3  test    dil, dil
0x18001a5d6  jz      short loc_18001A61C
0x18001a5d8  mov     edx, 18h; dwBytes
0x18001a5dd  xor     ecx, ecx; dwFlags
0x18001a5df  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18001a5e4  mov     rcx, rax
0x18001a5e7  test    rax, rax
0x18001a5ea  jz      short loc_18001A61C
0x18001a5ec  mov     [rax], ebx
0x18001a5ee  xor     eax, eax
0x18001a5f0  mov     [rcx+8], rax
0x18001a5f4  mov     [rcx+10h], rax
0x18001a5f8  nop     dword ptr [rax+rax+00000000h]
0x18001a600  mov     rax, [r14+rsi]
0x18001a604  mov     [rcx+8], rax
0x18001a608  lock cmpxchg [r14+rsi], rcx
0x18001a60e  jnz     short loc_18001A600
0x18001a610  lea     rax, [rcx+10h]
0x18001a614  jmp     short loc_18001A61E
0x18001a616  add     rax, 10h
0x18001a61a  jmp     short loc_18001A61E
0x18001a61c  xor     eax, eax
0x18001a61e  mov     rbx, [rsp+28h+arg_0]
0x18001a623  mov     rsi, [rsp+28h+arg_8]
0x18001a628  mov     rdi, [rsp+28h+arg_10]
0x18001a62d  add     rsp, 20h
0x18001a631  pop     r14
0x18001a633  retn
```
