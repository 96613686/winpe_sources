# Windows::Management::Setup::DeploymentWorkload::~DeploymentWorkload(void)

- ea: `0x1800faa7c`
- end: `0x1800fab78`
- name: `??1DeploymentWorkload@Setup@Management@Windows@@UEAA@XZ`
- size: `252`
- prototype: `void(Windows::Management::Setup::DeploymentWorkload *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18006f5d0`

## callees

- `0x18006e34c`
- `0x18006ec84`
- `0x180077d0c`
- `0x1800faa7c`
- `0x1800faf44`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800faac7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800faae5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fab03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fab1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fab36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fab4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800faac7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800faae5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fab03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fab1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fab36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fab4e`

## string_xrefs

- `0x1800faaaf`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\deploymentworkload.cpp`

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
0x1800faa7c  push    rbx; int
0x1800faa7e  sub     rsp, 20h
0x1800faa82  mov     rbx, rcx
0x1800faa85  lea     rax, ??_7DeploymentWorkload@Setup@Management@Windows@@6BIDeploymentWorkload@123@@; const Windows::Management::Setup::DeploymentWorkload::`vftable'{for `Windows::Management::Setup::IDeploymentWorkload'}
0x1800faa8c  mov     [rcx], rax
0x1800faa8f  lea     rax, ??_7DeploymentWorkload@Setup@Management@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$08@WRL@Microsoft@@$00UIWeakReferenceSource@@@Details@WRL@Microsoft@@@; const Windows::Management::Setup::DeploymentWorkload::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<9>,1,IWeakReferenceSource>'}
0x1800faa96  mov     [rcx+8], rax
0x1800faa9a  mov     rdx, [rcx+40h]; HSTRING
0x1800faa9e  call    ?RemoveWorkloadId@DeploymentWorkloadIdUniquenessMap@Setup@Management@Windows@@QEAAJPEAUHSTRING__@@@Z; Windows::Management::Setup::DeploymentWorkloadIdUniquenessMap::RemoveWorkloadId(HSTRING__ *)
0x1800faaa3  test    eax, eax
0x1800faaa5  jns     short loc_1800FAAC0
0x1800faaa7  mov     rcx, [rsp+28h]; this
0x1800faaac  mov     r9d, eax; char *
0x1800faaaf  lea     r8, aOnecoreuapAdmi_115; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800faab6  mov     edx, 6Ch ; 'l'; void *
0x1800faabb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800faac0  mov     rcx, [rbx+98h]; string
0x1800faac7  call    cs:__imp_WindowsDeleteString
0x1800faace  nop     dword ptr [rax+rax+00h]
0x1800faad3  mov     qword ptr [rbx+98h], 0
0x1800faade  mov     rcx, [rbx+90h]; string
0x1800faae5  call    cs:__imp_WindowsDeleteString
0x1800faaec  nop     dword ptr [rax+rax+00h]
0x1800faaf1  mov     qword ptr [rbx+90h], 0
0x1800faafc  mov     rcx, [rbx+88h]; string
0x1800fab03  call    cs:__imp_WindowsDeleteString
0x1800fab0a  nop     dword ptr [rax+rax+00h]
0x1800fab0f  mov     qword ptr [rbx+88h], 0
0x1800fab1a  mov     rcx, [rbx+58h]; string
0x1800fab1e  call    cs:__imp_WindowsDeleteString
0x1800fab25  nop     dword ptr [rax+rax+00h]
0x1800fab2a  mov     qword ptr [rbx+58h], 0
0x1800fab32  mov     rcx, [rbx+48h]; string
0x1800fab36  call    cs:__imp_WindowsDeleteString
0x1800fab3d  nop     dword ptr [rax+rax+00h]
0x1800fab42  mov     qword ptr [rbx+48h], 0
0x1800fab4a  mov     rcx, [rbx+40h]; string
0x1800fab4e  call    cs:__imp_WindowsDeleteString
0x1800fab55  nop     dword ptr [rax+rax+00h]
0x1800fab5a  mov     qword ptr [rbx+40h], 0
0x1800fab62  lea     rcx, [rbx+28h]; this
0x1800fab66  call    ??1ShareLockOverwriteBuffer@Core@Autopilot@ModernDeployment@@QEAA@XZ; ModernDeployment::Autopilot::Core::ShareLockOverwriteBuffer::~ShareLockOverwriteBuffer(void)
0x1800fab6b  mov     rcx, rbx
0x1800fab6e  add     rsp, 20h
0x1800fab72  pop     rbx
0x1800fab73  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$08@WRL@Microsoft@@$00$00$0A@UIDeviceManagementUtilities@Core@Autopilot@ModernDeployment@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<9>,1,1,0,ModernDeployment::Autopilot::Core::IDeviceManagementUtilities>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<9>,1,1,0,ModernDeployment::Autopilot::Core::IDeviceManagementUtilities>(void)
```
