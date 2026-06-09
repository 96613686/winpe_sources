# wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::Internal::FamilySafety::AppLimits::ParentalControlsAppInfo *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::Internal::FamilySafety::AppLimits::ParentalControlsAppInfo *>,wil::err_exception_policy>(void)

- ea: `0x18000ef38`
- end: `0x18000ef56`
- name: `??1?$com_ptr_t@U?$IVectorView@PEAVParentalControlsAppInfo@AppLimits@FamilySafety@Internal@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180029852`
- `0x18002989a`

## callees

- `0x18000ef38`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::Internal::FamilySafety::AppLimits::ParentalControlsAppInfo *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::Internal::FamilySafety::AppLimits::ParentalControlsAppInfo *>,wil::err_exception_policy>(
        __int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x18000ef38  sub     rsp, 28h
0x18000ef3c  mov     rcx, [rcx]
0x18000ef3f  test    rcx, rcx
0x18000ef42  jz      short loc_18000EF51
0x18000ef44  mov     rax, [rcx]
0x18000ef47  mov     rax, [rax+10h]
0x18000ef4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef50  nop
0x18000ef51  add     rsp, 28h
0x18000ef55  retn
```
