# winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem,winrt::Windows::Foundation::IInspectable>::~TypedEventHandler<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem,winrt::Windows::Foundation::IInspectable>(void)

- ea: `0x18000bdb4`
- end: `0x18000bdc8`
- name: `??1?$TypedEventHandler@UAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@UIInspectable@Foundation@67@@Foundation@Windows@winrt@@QEAA@XZ`
- size: `20`
- prototype: ``
- caller_count: `35`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18005d54a`
- `0x18005d55c`
- `0x18005d580`
- `0x18005d9e9`
- `0x18005d9fb`
- `0x18005da0d`
- `0x18005da1f`
- `0x18005da55`
- `0x18005daf8`
- `0x18005db48`
- `0x18005db5a`
- `0x18005db6c`
- `0x18005db7e`
- `0x18005dba2`
- `0x18005dbb4`
- `0x18005dbc6`
- `0x18005dbea`
- `0x18005dc3d`
- `0x18005ddab`
- `0x18005ddcf`
- `0x18005dde1`
- `0x18005ddf3`
- `0x18005df32`
- `0x18005df7a`
- `0x18005df8c`
- `0x18005df9e`
- `0x18005dfcd`
- `0x180060594`
- `0x18006063b`
- `0x180060739`
- `0x18006074b`
- `0x18006079b`
- `0x1800607f6`
- `0x18006088d`
- `0x180060d91`

## callees

- `0x18000bdb4`
- `0x18002d1a4`

## pseudocode

```c
__int64 __fastcall winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem,winrt::Windows::Foundation::IInspectable>::~TypedEventHandler<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem,winrt::Windows::Foundation::IInspectable>(
        _QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1);
  return result;
}

```

## disassembly

```asm
0x18000bdb4  sub     rsp, 28h
0x18000bdb8  cmp     qword ptr [rcx], 0
0x18000bdbc  jz      short loc_18000BDC3
0x18000bdbe  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000bdc3  add     rsp, 28h
0x18000bdc7  retn
```
