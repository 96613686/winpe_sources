# _Microsoft::WRL::Details::Make_MapsBrokerAsyncOperation_long_(__cdecl_)(_RPC_ASYNC_STATE__)__::_1_::dtor$0

- ea: `0x180011259`
- end: `0x18001127f`
- name: `_Microsoft::WRL::Details::Make_MapsBrokerAsyncOperation_long_(__cdecl_)(_RPC_ASYNC_STATE__)__::_1_::dtor$0`
- size: `38`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180008fb0`
- `0x180011259`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::Make_MapsBrokerAsyncOperation_long____cdecl____RPC_ASYNC_STATE_____::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 32) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    return Microsoft::WRL::ComPtr<MapsBrokerAsyncOperation>::~ComPtr<MapsBrokerAsyncOperation>(*(__int64 **)(a2 + 64));
  }
  return result;
}

```

## disassembly

```asm
0x180011259  push    rbp
0x18001125b  sub     rsp, 20h
0x18001125f  mov     rbp, rdx
0x180011262  mov     eax, [rbp+20h]
0x180011265  and     eax, 1
0x180011268  test    eax, eax
0x18001126a  jz      short loc_180011279
0x18001126c  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x180011270  mov     rcx, [rbp+40h]
0x180011274  call    ??1?$ComPtr@VMapsBrokerAsyncOperation@@@WRL@Microsoft@@QEAA@XZ
0x180011279  add     rsp, 20h
0x18001127d  pop     rbp
0x18001127e  retn
```
