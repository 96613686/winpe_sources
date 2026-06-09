# CloudExperienceHostAPI::HostedApplicationCoreInstance::~HostedApplicationCoreInstance(void)

- ea: `0x1800745e8`
- end: `0x18007462b`
- name: `??1HostedApplicationCoreInstance@CloudExperienceHostAPI@@UEAA@XZ`
- size: `67`
- prototype: `void __fastcall(CloudExperienceHostAPI::HostedApplicationCoreInstance *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800750d0`

## callees

- `0x18000fb58`
- `0x1800744b8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800745fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074610`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800745fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074610`

## pseudocode

```c
void __fastcall CloudExperienceHostAPI::HostedApplicationCoreInstance::~HostedApplicationCoreInstance(HSTRING *this)
{
  wil::com_ptr_t<Windows::Services::Store::IStoreContext3,wil::err_returncode_policy>::~com_ptr_t<Windows::Services::Store::IStoreContext3,wil::err_returncode_policy>(this + 16);
  WindowsDeleteString(this[12]);
  this[12] = 0;
  WindowsDeleteString(this[11]);
  this[11] = 0;
  Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::Implements<CloudExperienceHostAPI::IHostedApplicationManager,CloudExperienceHostAPI::IHostedApplicationManager2,CloudExperienceHostAPI::IHostedApplicationManager3>,Microsoft::WRL::FtmBase>::~RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::Implements<CloudExperienceHostAPI::IHostedApplicationManager,CloudExperienceHostAPI::IHostedApplicationManager2,CloudExperienceHostAPI::IHostedApplicationManager3>,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x1800745e8  push    rbx
0x1800745ea  sub     rsp, 20h
0x1800745ee  mov     rbx, rcx
0x1800745f1  sub     rcx, 0FFFFFFFFFFFFFF80h
0x1800745f5  call    ??1?$com_ptr_t@UIStoreContext3@Store@Services@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Services::Store::IStoreContext3,wil::err_returncode_policy>::~com_ptr_t<Windows::Services::Store::IStoreContext3,wil::err_returncode_policy>(void)
0x1800745fa  mov     rcx, [rbx+60h]; string
0x1800745fe  call    cs:__imp_WindowsDeleteString
0x180074604  mov     qword ptr [rbx+60h], 0
0x18007460c  mov     rcx, [rbx+58h]; string
0x180074610  call    cs:__imp_WindowsDeleteString
0x180074616  mov     rcx, rbx
0x180074619  mov     qword ptr [rbx+58h], 0
0x180074621  add     rsp, 20h
0x180074625  pop     rbx
0x180074626  jmp     ??1?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@U?$Implements@UIHostedApplicationManager@CloudExperienceHostAPI@@UIHostedApplicationManager2@2@UIHostedApplicationManager3@2@@23@VFtmBase@23@@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::Implements<CloudExperienceHostAPI::IHostedApplicationManager,CloudExperienceHostAPI::IHostedApplicationManager2,CloudExperienceHostAPI::IHostedApplicationManager3>,Microsoft::WRL::FtmBase>::~RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::Implements<CloudExperienceHostAPI::IHostedApplicationManager,CloudExperienceHostAPI::IHostedApplicationManager2,CloudExperienceHostAPI::IHostedApplicationManager3>,Microsoft::WRL::FtmBase>(void)
```
