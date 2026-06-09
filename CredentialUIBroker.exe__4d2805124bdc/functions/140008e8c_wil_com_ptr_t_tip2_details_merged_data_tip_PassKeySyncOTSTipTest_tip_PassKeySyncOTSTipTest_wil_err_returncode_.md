# wil::com_ptr_t<tip2::details::merged_data<_tip_PassKeySyncOTSTipTest,_tip_PassKeySyncOTSTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PassKeySyncOTSTipTest,_tip_PassKeySyncOTSTipTest>,wil::err_returncode_policy>(void)

- ea: `0x140008e8c`
- end: `0x140008ea2`
- name: `??1?$com_ptr_t@V?$merged_data@U_tip_PassKeySyncOTSTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ`
- size: `22`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140009004`
- `0x14000903c`
- `0x140010be0`
- `0x14001bb28`

## callees

- `0x140008e8c`
- `0x140012e88`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<tip2::details::merged_data<_tip_PassKeySyncOTSTipTest,_tip_PassKeySyncOTSTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PassKeySyncOTSTipTest,_tip_PassKeySyncOTSTipTest>,wil::err_returncode_policy>(
        void **a1)
{
  void *v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return tip2::details::merged_data<_tip_PassKeySyncOTSTipTest,_tip_PassKeySyncOTSTipTest>::Release(v1);
  return result;
}

```

## disassembly

```asm
0x140008e8c  sub     rsp, 28h
0x140008e90  mov     rcx, [rcx]; pv
0x140008e93  test    rcx, rcx
0x140008e96  jz      short loc_140008E9D
0x140008e98  call    ?Release@?$merged_data@U_tip_PassKeySyncOTSTipTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_PassKeySyncOTSTipTest,_tip_PassKeySyncOTSTipTest>::Release(void)
0x140008e9d  add     rsp, 28h
0x140008ea1  retn
```
