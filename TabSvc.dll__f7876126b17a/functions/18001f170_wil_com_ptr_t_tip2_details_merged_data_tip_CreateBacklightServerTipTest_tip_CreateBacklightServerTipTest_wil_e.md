# wil::com_ptr_t<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>,wil::err_returncode_policy>(void)

- ea: `0x18001f170`
- end: `0x18001f186`
- name: `??1?$com_ptr_t@V?$merged_data@U_tip_CreateBacklightServerTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ`
- size: `22`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800194b0`
- `0x1800197b4`
- `0x18001f1b0`
- `0x18002ab14`

## callees

- `0x18001f170`
- `0x180024ed4`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>,wil::err_returncode_policy>(
        void **a1)
{
  void *v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>::Release(v1);
  return result;
}

```

## disassembly

```asm
0x18001f170  sub     rsp, 28h
0x18001f174  mov     rcx, [rcx]; pv
0x18001f177  test    rcx, rcx
0x18001f17a  jz      short loc_18001F181
0x18001f17c  call    ?Release@?$merged_data@U_tip_CreateBacklightServerTipTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>::Release(void)
0x18001f181  add     rsp, 28h
0x18001f185  retn
```
