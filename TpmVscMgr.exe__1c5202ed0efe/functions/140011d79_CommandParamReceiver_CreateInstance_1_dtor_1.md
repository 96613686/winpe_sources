# _CommandParamReceiver::CreateInstance_::_1_::dtor$1

- ea: `0x140011d79`
- end: `0x140011da8`
- name: `_CommandParamReceiver::CreateInstance_::_1_::dtor$1`
- size: `47`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400082e4`
- `0x140011d79`

## pseudocode

```c
__int64 __fastcall CommandParamReceiver::CreateInstance_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 136) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 136) &= ~1u;
    return wil::com_ptr_t<ITpmVirtualSmartCardManager,wil::err_exception_policy>::~com_ptr_t<ITpmVirtualSmartCardManager,wil::err_exception_policy>(*(__int64 **)(a2 + 440));
  }
  return result;
}

```

## disassembly

```asm
0x140011d79  push    rbp
0x140011d7b  sub     rsp, 20h
0x140011d7f  mov     rbp, rdx
0x140011d82  mov     eax, [rbp+88h]
0x140011d88  and     eax, 1
0x140011d8b  test    eax, eax
0x140011d8d  jz      short loc_140011DA2
0x140011d8f  and     dword ptr [rbp+88h], 0FFFFFFFEh
0x140011d96  mov     rcx, [rbp+1B8h]
0x140011d9d  call    ??1?$com_ptr_t@UITpmVirtualSmartCardManager@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ITpmVirtualSmartCardManager,wil::err_exception_policy>::~com_ptr_t<ITpmVirtualSmartCardManager,wil::err_exception_policy>(void)
0x140011da2  add     rsp, 20h
0x140011da6  pop     rbp
0x140011da7  retn
```
