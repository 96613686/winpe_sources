# _wil::get_token_information__TOKEN_USER__::_1_::dtor$1

- ea: `0x18000ce04`
- end: `0x18000ce2a`
- name: `_wil::get_token_information__TOKEN_USER__::_1_::dtor$1`
- size: `38`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800099b0`
- `0x18000ce04`

## pseudocode

```c
void __fastcall wil::get_token_information__TOKEN_USER__::_1_::dtor_1(__int64 a1, __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 48) & 2) != 0 )
  {
    *(_DWORD *)(a2 + 48) &= ~2u;
    wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>::~unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>(*(void ***)(a2 + 80));
  }
}

```

## disassembly

```asm
0x18000ce04  push    rbp
0x18000ce06  sub     rsp, 20h
0x18000ce0a  mov     rbp, rdx
0x18000ce0d  mov     eax, [rbp+30h]
0x18000ce10  and     eax, 2
0x18000ce13  test    eax, eax
0x18000ce15  jz      short loc_18000CE24
0x18000ce17  and     dword ptr [rbp+30h], 0FFFFFFFDh
0x18000ce1b  mov     rcx, [rbp+50h]
0x18000ce1f  call    ??1?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>::~unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>(void)
0x18000ce24  add     rsp, 20h
0x18000ce28  pop     rbp
0x18000ce29  retn
```
