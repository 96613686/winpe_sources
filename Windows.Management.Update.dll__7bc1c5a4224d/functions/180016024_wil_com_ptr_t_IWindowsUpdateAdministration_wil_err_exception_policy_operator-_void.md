# wil::com_ptr_t<IWindowsUpdateAdministration,wil::err_exception_policy>::operator->(void)

- ea: `0x180016024`
- end: `0x180016028`
- name: `??C?$com_ptr_t@UIWindowsUpdateAdministration@@Uerr_exception_policy@wil@@@wil@@QEBAPEAUIWindowsUpdateAdministration@@XZ`
- size: `4`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `6`
- callee_count: `0`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180012430`
- `0x180014d10`
- `0x180024ca8`
- `0x180024e64`
- `0x1800250cc`
- `0x180025290`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<IWindowsUpdateAdministration,wil::err_exception_policy>::operator->(__int64 a1)
{
  return *(_QWORD *)a1;
}

```

## disassembly

```asm
0x180016024  mov     rax, [rcx]
0x180016027  retn
```
