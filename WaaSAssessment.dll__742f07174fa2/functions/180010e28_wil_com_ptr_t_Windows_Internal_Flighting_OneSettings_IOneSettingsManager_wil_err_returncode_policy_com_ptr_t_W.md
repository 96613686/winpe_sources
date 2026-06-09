# wil::com_ptr_t<Windows::Internal::Flighting::OneSettings::IOneSettingsManager,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Flighting::OneSettings::IOneSettingsManager,wil::err_returncode_policy>(void)

- ea: `0x180010e28`
- end: `0x180010e46`
- name: `??1?$com_ptr_t@UIOneSettingsManager@OneSettings@Flighting@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019e16`
- `0x180019e28`

## callees

- `0x180010e28`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<Windows::Internal::Flighting::OneSettings::IOneSettingsManager,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Flighting::OneSettings::IOneSettingsManager,wil::err_returncode_policy>(
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
0x180010e28  sub     rsp, 28h
0x180010e2c  mov     rcx, [rcx]
0x180010e2f  test    rcx, rcx
0x180010e32  jz      short loc_180010E41
0x180010e34  mov     rax, [rcx]
0x180010e37  mov     rax, [rax+10h]
0x180010e3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e40  nop
0x180010e41  add     rsp, 28h
0x180010e45  retn
```
