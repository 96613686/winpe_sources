# Windows::Management::Setup::DeploymentWorkload::~DeploymentWorkload(void)

- ea: `0x1800f7b40`
- end: `0x1800f7c18`
- name: `??1DeploymentWorkload@Setup@Management@Windows@@UEAA@XZ`
- size: `216`
- prototype: `void(Windows::Management::Setup::DeploymentWorkload *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18006f030`

## callees

- `0x18006de18`
- `0x18006e6f8`
- `0x18007748c`
- `0x1800f7b40`
- `0x1800f7fd0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f7b8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f7ba3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f7bbb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f7bd0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f7be2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f7bf4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f7b8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f7ba3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f7bbb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f7bd0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f7be2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f7bf4`

## string_xrefs

- `0x1800f7b73`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\deploymentworkload.cpp`

## pseudocode

```c
void __fastcall Windows::Management::Setup::DeploymentWorkload::~DeploymentWorkload(
        Windows::Management::Setup::DeploymentWorkload *this)
{
  int v2; // eax
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *(_QWORD *)this = &Windows::Management::Setup::DeploymentWorkload::`vftable'{for `Windows::Management::Setup::IDeploymentWorkload'};
  *((_QWORD *)this + 1) = &Windows::Management::Setup::DeploymentWorkload::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<9>,1,IWeakReferenceSource>'};
  v2 = Windows::Management::Setup::DeploymentWorkloadIdUniquenessMap::RemoveWorkloadId(this, *((HSTRING *)this + 8));
  if ( v2 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x6C,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\deploymentworkload.cpp",
      (const char *)(unsigned int)v2,
      v3);
  WindowsDeleteString(*((HSTRING *)this + 19));
  *((_QWORD *)this + 19) = 0;
  WindowsDeleteString(*((HSTRING *)this + 18));
  *((_QWORD *)this + 18) = 0;
  WindowsDeleteString(*((HSTRING *)this + 17));
  *((_QWORD *)this + 17) = 0;
  WindowsDeleteString(*((HSTRING *)this + 11));
  *((_QWORD *)this + 11) = 0;
  WindowsDeleteString(*((HSTRING *)this + 9));
  *((_QWORD *)this + 9) = 0;
  WindowsDeleteString(*((HSTRING *)this + 8));
  *((_QWORD *)this + 8) = 0;
  ModernDeployment::Autopilot::Core::ShareLockOverwriteBuffer::~ShareLockOverwriteBuffer((Windows::Management::Setup::DeploymentWorkload *)((char *)this + 40));
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<9>,1,1,0,ModernDeployment::Autopilot::Core::IDeviceManagementUtilities>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<9>,1,1,0,ModernDeployment::Autopilot::Core::IDeviceManagementUtilities>(this);
}

```

## disassembly

```asm
0x1800f7b40  push    rbx; int
0x1800f7b42  sub     rsp, 20h
0x1800f7b46  mov     rbx, rcx
0x1800f7b49  lea     rax, ??_7DeploymentWorkload@Setup@Management@Windows@@6BIDeploymentWorkload@123@@; const Windows::Management::Setup::DeploymentWorkload::`vftable'{for `Windows::Management::Setup::IDeploymentWorkload'}
0x1800f7b50  mov     [rcx], rax
0x1800f7b53  lea     rax, ??_7DeploymentWorkload@Setup@Management@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$08@WRL@Microsoft@@$00UIWeakReferenceSource@@@Details@WRL@Microsoft@@@; const Windows::Management::Setup::DeploymentWorkload::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<9>,1,IWeakReferenceSource>'}
0x1800f7b5a  mov     [rcx+8], rax
0x1800f7b5e  mov     rdx, [rcx+40h]; HSTRING
0x1800f7b62  call    ?RemoveWorkloadId@DeploymentWorkloadIdUniquenessMap@Setup@Management@Windows@@QEAAJPEAUHSTRING__@@@Z; Windows::Management::Setup::DeploymentWorkloadIdUniquenessMap::RemoveWorkloadId(HSTRING__ *)
0x1800f7b67  test    eax, eax
0x1800f7b69  jns     short loc_1800F7B84
0x1800f7b6b  mov     rcx, [rsp+28h]; this
0x1800f7b70  mov     r9d, eax; char *
0x1800f7b73  lea     r8, aOnecoreuapAdmi_115; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800f7b7a  mov     edx, 6Ch ; 'l'; void *
0x1800f7b7f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800f7b84  mov     rcx, [rbx+98h]; string
0x1800f7b8b  call    cs:__imp_WindowsDeleteString
0x1800f7b91  mov     qword ptr [rbx+98h], 0
0x1800f7b9c  mov     rcx, [rbx+90h]; string
0x1800f7ba3  call    cs:__imp_WindowsDeleteString
0x1800f7ba9  mov     qword ptr [rbx+90h], 0
0x1800f7bb4  mov     rcx, [rbx+88h]; string
0x1800f7bbb  call    cs:__imp_WindowsDeleteString
0x1800f7bc1  mov     qword ptr [rbx+88h], 0
0x1800f7bcc  mov     rcx, [rbx+58h]; string
0x1800f7bd0  call    cs:__imp_WindowsDeleteString
0x1800f7bd6  mov     qword ptr [rbx+58h], 0
0x1800f7bde  mov     rcx, [rbx+48h]; string
0x1800f7be2  call    cs:__imp_WindowsDeleteString
0x1800f7be8  mov     qword ptr [rbx+48h], 0
0x1800f7bf0  mov     rcx, [rbx+40h]; string
0x1800f7bf4  call    cs:__imp_WindowsDeleteString
0x1800f7bfa  mov     qword ptr [rbx+40h], 0
0x1800f7c02  lea     rcx, [rbx+28h]; this
0x1800f7c06  call    ??1ShareLockOverwriteBuffer@Core@Autopilot@ModernDeployment@@QEAA@XZ; ModernDeployment::Autopilot::Core::ShareLockOverwriteBuffer::~ShareLockOverwriteBuffer(void)
0x1800f7c0b  mov     rcx, rbx
0x1800f7c0e  add     rsp, 20h
0x1800f7c12  pop     rbx
0x1800f7c13  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$08@WRL@Microsoft@@$00$00$0A@UIDeviceManagementUtilities@Core@Autopilot@ModernDeployment@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<9>,1,1,0,ModernDeployment::Autopilot::Core::IDeviceManagementUtilities>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<9>,1,1,0,ModernDeployment::Autopilot::Core::IDeviceManagementUtilities>(void)
```
