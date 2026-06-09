# _wil::CoCreateInstance_IAppVisibility_wil::err_exception_policy__::_1_::dtor$0

- ea: `0x14000edd6`
- end: `0x14000edfc`
- name: `_wil::CoCreateInstance_IAppVisibility_wil::err_exception_policy__::_1_::dtor$0`
- size: `38`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000c628`
- `0x14000edd6`

## pseudocode

```c
__int64 __fastcall wil::CoCreateInstance_IAppVisibility_wil::err_exception_policy__::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 48) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 48) &= ~1u;
    return wil::com_ptr_t<IAppVisibility,wil::err_exception_policy>::~com_ptr_t<IAppVisibility,wil::err_exception_policy>(*(__int64 **)(a2 + 80));
  }
  return result;
}

```

## disassembly

```asm
0x14000edd6  push    rbp
0x14000edd8  sub     rsp, 20h
0x14000eddc  mov     rbp, rdx
0x14000eddf  mov     eax, [rbp+30h]
0x14000ede2  and     eax, 1
0x14000ede5  test    eax, eax
0x14000ede7  jz      short loc_14000EDF6
0x14000ede9  and     dword ptr [rbp+30h], 0FFFFFFFEh
0x14000eded  mov     rcx, [rbp+50h]
0x14000edf1  call    ??1?$com_ptr_t@UIAppVisibility@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAppVisibility,wil::err_exception_policy>::~com_ptr_t<IAppVisibility,wil::err_exception_policy>(void)
0x14000edf6  add     rsp, 20h
0x14000edfa  pop     rbp
0x14000edfb  retn
```
