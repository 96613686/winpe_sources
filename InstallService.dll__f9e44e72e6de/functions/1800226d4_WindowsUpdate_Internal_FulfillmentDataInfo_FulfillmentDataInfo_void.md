# WindowsUpdate::Internal::FulfillmentDataInfo::~FulfillmentDataInfo(void)

- ea: `0x1800226d4`
- end: `0x180022883`
- name: `??1FulfillmentDataInfo@Internal@WindowsUpdate@@UEAA@XZ`
- size: `431`
- prototype: `void __fastcall(WindowsUpdate::Internal::FulfillmentDataInfo *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180023970`

## callees

- `0x1800101f4`
- `0x180021f44`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022718`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002272e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022742`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022756`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002276a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002277e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022792`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800227a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800227ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800227ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800227e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800227f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002280a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002281e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002282f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002283d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002284b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022859`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022867`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022718`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002272e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022742`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022756`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002276a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002277e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022792`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800227a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800227ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800227ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800227e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800227f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002280a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002281e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002282f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002283d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002284b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022859`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022867`

## pseudocode

```c
void __fastcall WindowsUpdate::Internal::FulfillmentDataInfo::~FulfillmentDataInfo(HSTRING *this)
{
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(this + 36);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(this + 35);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(this + 34);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(this + 33);
  WindowsDeleteString(this[30]);
  this[30] = 0;
  WindowsDeleteString(this[28]);
  this[28] = 0;
  WindowsDeleteString(this[27]);
  this[27] = 0;
  WindowsDeleteString(this[26]);
  this[26] = 0;
  WindowsDeleteString(this[25]);
  this[25] = 0;
  WindowsDeleteString(this[24]);
  this[24] = 0;
  WindowsDeleteString(this[23]);
  this[23] = 0;
  WindowsDeleteString(this[22]);
  this[22] = 0;
  WindowsDeleteString(this[21]);
  this[21] = 0;
  WindowsDeleteString(this[20]);
  this[20] = 0;
  WindowsDeleteString(this[19]);
  this[19] = 0;
  WindowsDeleteString(this[18]);
  this[18] = 0;
  WindowsDeleteString(this[17]);
  this[17] = 0;
  WindowsDeleteString(this[16]);
  this[16] = 0;
  WindowsDeleteString(this[15]);
  this[15] = 0;
  WindowsDeleteString(this[14]);
  this[14] = 0;
  WindowsDeleteString(this[13]);
  this[13] = 0;
  WindowsDeleteString(this[12]);
  this[12] = 0;
  WindowsDeleteString(this[11]);
  this[11] = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallOptions,Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallOptions2,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallOptions,Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallOptions2,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x1800226d4  mov     [rsp+arg_0], rbx
0x1800226d9  push    rdi
0x1800226da  sub     rsp, 20h
0x1800226de  mov     rbx, rcx
0x1800226e1  add     rcx, 120h
0x1800226e8  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800226ed  lea     rcx, [rbx+118h]
0x1800226f4  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800226f9  lea     rcx, [rbx+110h]
0x180022700  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180022705  lea     rcx, [rbx+108h]
0x18002270c  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180022711  mov     rcx, [rbx+0F0h]; string
0x180022718  call    cs:__imp_WindowsDeleteString
0x18002271e  xor     edi, edi
0x180022720  mov     [rbx+0F0h], rdi
0x180022727  mov     rcx, [rbx+0E0h]; string
0x18002272e  call    cs:__imp_WindowsDeleteString
0x180022734  mov     [rbx+0E0h], rdi
0x18002273b  mov     rcx, [rbx+0D8h]; string
0x180022742  call    cs:__imp_WindowsDeleteString
0x180022748  mov     [rbx+0D8h], rdi
0x18002274f  mov     rcx, [rbx+0D0h]; string
0x180022756  call    cs:__imp_WindowsDeleteString
0x18002275c  mov     [rbx+0D0h], rdi
0x180022763  mov     rcx, [rbx+0C8h]; string
0x18002276a  call    cs:__imp_WindowsDeleteString
0x180022770  mov     [rbx+0C8h], rdi
0x180022777  mov     rcx, [rbx+0C0h]; string
0x18002277e  call    cs:__imp_WindowsDeleteString
0x180022784  mov     [rbx+0C0h], rdi
0x18002278b  mov     rcx, [rbx+0B8h]; string
0x180022792  call    cs:__imp_WindowsDeleteString
0x180022798  mov     [rbx+0B8h], rdi
0x18002279f  mov     rcx, [rbx+0B0h]; string
0x1800227a6  call    cs:__imp_WindowsDeleteString
0x1800227ac  mov     [rbx+0B0h], rdi
0x1800227b3  mov     rcx, [rbx+0A8h]; string
0x1800227ba  call    cs:__imp_WindowsDeleteString
0x1800227c0  mov     [rbx+0A8h], rdi
0x1800227c7  mov     rcx, [rbx+0A0h]; string
0x1800227ce  call    cs:__imp_WindowsDeleteString
0x1800227d4  mov     [rbx+0A0h], rdi
0x1800227db  mov     rcx, [rbx+98h]; string
0x1800227e2  call    cs:__imp_WindowsDeleteString
0x1800227e8  mov     [rbx+98h], rdi
0x1800227ef  mov     rcx, [rbx+90h]; string
0x1800227f6  call    cs:__imp_WindowsDeleteString
0x1800227fc  mov     [rbx+90h], rdi
0x180022803  mov     rcx, [rbx+88h]; string
0x18002280a  call    cs:__imp_WindowsDeleteString
0x180022810  mov     [rbx+88h], rdi
0x180022817  mov     rcx, [rbx+80h]; string
0x18002281e  call    cs:__imp_WindowsDeleteString
0x180022824  mov     [rbx+80h], rdi
0x18002282b  mov     rcx, [rbx+78h]; string
0x18002282f  call    cs:__imp_WindowsDeleteString
0x180022835  mov     [rbx+78h], rdi
0x180022839  mov     rcx, [rbx+70h]; string
0x18002283d  call    cs:__imp_WindowsDeleteString
0x180022843  mov     [rbx+70h], rdi
0x180022847  mov     rcx, [rbx+68h]; string
0x18002284b  call    cs:__imp_WindowsDeleteString
0x180022851  mov     [rbx+68h], rdi
0x180022855  mov     rcx, [rbx+60h]; string
0x180022859  call    cs:__imp_WindowsDeleteString
0x18002285f  mov     [rbx+60h], rdi
0x180022863  mov     rcx, [rbx+58h]; string
0x180022867  call    cs:__imp_WindowsDeleteString
0x18002286d  mov     rcx, rbx
0x180022870  mov     [rbx+58h], rdi
0x180022874  mov     rbx, [rsp+28h+arg_0]
0x180022879  add     rsp, 20h
0x18002287d  pop     rdi
0x18002287e  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIAppInstallOptions@InstallControl@Preview@Store@ApplicationModel@Windows@@UIAppInstallOptions2@56789@U?$CloakedIid@UIAgileObject@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallOptions,Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallOptions2,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallOptions,Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallOptions2,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>(void)
```
