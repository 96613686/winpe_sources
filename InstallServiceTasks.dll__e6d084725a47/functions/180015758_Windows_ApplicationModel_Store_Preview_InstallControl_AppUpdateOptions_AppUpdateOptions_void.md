# Windows::ApplicationModel::Store::Preview::InstallControl::AppUpdateOptions::~AppUpdateOptions(void)

- ea: `0x180015758`
- end: `0x180015780`
- name: `??1AppUpdateOptions@InstallControl@Preview@Store@ApplicationModel@Windows@@UEAA@XZ`
- size: `40`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800159f0`

## callees

- `0x1800155f4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015765`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015765`

## pseudocode

```c
void __fastcall Windows::ApplicationModel::Store::Preview::InstallControl::AppUpdateOptions::~AppUpdateOptions(
        HSTRING *this)
{
  WindowsDeleteString(this[11]);
  this[11] = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Foundation::ITypedEventHandler<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,IInspectable *>,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Foundation::ITypedEventHandler<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,IInspectable *>,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>((__int64)this);
}

```

## disassembly

```asm
0x180015758  push    rbx
0x18001575a  sub     rsp, 20h
0x18001575e  mov     rbx, rcx
0x180015761  mov     rcx, [rcx+58h]; string
0x180015765  call    cs:__imp_WindowsDeleteString
0x18001576b  mov     rcx, rbx
0x18001576e  mov     qword ptr [rbx+58h], 0
0x180015776  add     rsp, 20h
0x18001577a  pop     rbx
0x18001577b  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$ITypedEventHandler@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@PEAUIInspectable@@@Foundation@Windows@@U?$CloakedIid@UIAgileObject@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Foundation::ITypedEventHandler<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,IInspectable *>,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Foundation::ITypedEventHandler<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,IInspectable *>,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>(void)
```
