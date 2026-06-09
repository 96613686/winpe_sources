# wil::com_ptr_t<IWindowsUpdateAdministration,wil::err_exception_policy>::operator->(void)

- ea: `0x180016c20`
- end: `0x180016c24`
- name: `??C?$com_ptr_t@UIWindowsUpdateAdministration@@Uerr_exception_policy@wil@@@wil@@QEBAPEAUIWindowsUpdateAdministration@@XZ`
- size: `4`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180013000`
- `0x180015920`
- `0x180026068`
- `0x180026230`
- `0x18002648c`
- `0x18002664c`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<IWindowsUpdateAdministration,wil::err_exception_policy>::operator->(__int64 a1)
{
  return *(_QWORD *)a1;
}

```

## disassembly

```asm
0x180016c20  mov     rax, [rcx]
0x180016c23  retn
```
