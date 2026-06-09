# wil::com_ptr_t<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>,wil::err_returncode_policy>(void)

- ea: `0x1800125b0`
- end: `0x1800125c6`
- name: `??1?$com_ptr_t@V?$merged_data@U_tip_ModelInstallationCompletedTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ`
- size: `22`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800127e8`
- `0x180012880`
- `0x1800128b4`
- `0x18001871c`
- `0x18001e14c`

## callees

- `0x1800125b0`
- `0x18001a58c`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>,wil::err_returncode_policy>(
        void **a1)
{
  void *v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>::Release(v1);
  return result;
}

```

## disassembly

```asm
0x1800125b0  sub     rsp, 28h
0x1800125b4  mov     rcx, [rcx]; pv
0x1800125b7  test    rcx, rcx
0x1800125ba  jz      short loc_1800125C1
0x1800125bc  call    ?Release@?$merged_data@U_tip_ModelInstallationCompletedTipTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>::Release(void)
0x1800125c1  add     rsp, 28h
0x1800125c5  retn
```
