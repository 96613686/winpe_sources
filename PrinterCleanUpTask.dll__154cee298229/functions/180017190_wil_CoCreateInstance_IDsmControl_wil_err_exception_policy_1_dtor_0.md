# _wil::CoCreateInstance_IDsmControl_wil::err_exception_policy__::_1_::dtor$0

- ea: `0x180017190`
- end: `0x1800171b6`
- name: `_wil::CoCreateInstance_IDsmControl_wil::err_exception_policy__::_1_::dtor$0`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18001166c`
- `0x180017190`

## pseudocode

```c
__int64 __fastcall wil::CoCreateInstance_IDsmControl_wil::err_exception_policy__::_1_::dtor_0(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 48) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 48) &= ~1u;
    return wil::com_ptr_t<IDsmControl,wil::err_exception_policy>::~com_ptr_t<IDsmControl,wil::err_exception_policy>(*(__int64 **)(a2 + 80));
  }
  return result;
}

```

## disassembly

```asm
0x180017190  push    rbp
0x180017192  sub     rsp, 20h
0x180017196  mov     rbp, rdx
0x180017199  mov     eax, [rbp+30h]
0x18001719c  and     eax, 1
0x18001719f  test    eax, eax
0x1800171a1  jz      short loc_1800171B0
0x1800171a3  and     dword ptr [rbp+30h], 0FFFFFFFEh
0x1800171a7  mov     rcx, [rbp+50h]
0x1800171ab  call    ??1?$com_ptr_t@UIDsmControl@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDsmControl,wil::err_exception_policy>::~com_ptr_t<IDsmControl,wil::err_exception_policy>(void)
0x1800171b0  add     rsp, 20h
0x1800171b4  pop     rbp
0x1800171b5  retn
```
