# CRemoveDeviceFlyout::RemoveHandler(IPopupWindow *,IPopupCommand *)

- ea: `0x140035b6c`
- end: `0x140035d34`
- name: `?RemoveHandler@CRemoveDeviceFlyout@@QEAAJPEAUIPopupWindow@@PEAUIPopupCommand@@@Z`
- size: `456`
- prototype: `__int64 __fastcall(CRemoveDeviceFlyout *__hidden this, struct IPopupWindow *, struct IPopupCommand *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400360f8`

## callees

- `0x140005f30`
- `0x14001a2a0`
- `0x1400341e0`
- `0x1400343ec`
- `0x1400354c0`
- `0x140035b6c`
- `0x140035f60`
- `0x140036198`
- `0x140036308`
- `0x140036958`
- `0x14007d010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140035c65`
- `KERNEL32!GetLastError` at `0x140035c65`
- `newdev!DiUninstallDevice` at `0x140035c4c`
- `newdev!DiUninstallDevice` at `0x140035c4c`
- `ole32!CoCreateInstance` at `0x140035cad`
- `ole32!CoCreateInstance` at `0x140035cad`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x140035be4`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x140035be4`
- `SETUPAPI!SetupDiOpenDeviceInfoW` at `0x140035c25`
- `SETUPAPI!SetupDiOpenDeviceInfoW` at `0x140035c25`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x140035c57`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x140035c57`
- `USER32!PostQuitMessage` at `0x140035cfa`
- `USER32!PostQuitMessage` at `0x140035cfa`

## string_xrefs

- `0x140035b94`: `RemoveHandlerActivity`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CRemoveDeviceFlyout::RemoveHandler(
        const unsigned __int16 **this,
        struct IPopupWindow *a2,
        struct IPopupCommand *a3)
{
  HDEVINFO DeviceInfoList; // rbx
  BOOL v5; // esi
  __int64 v6; // rdx
  int Instance; // ebx
  signed int LastError; // eax
  WINBOOL NeedReboot[2]; // [rsp+30h] [rbp-D0h] BYREF
  struct _SP_DEVINFO_DATA DeviceInfoData; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v12[42]; // [rsp+60h] [rbp-A0h] BYREF

  wil::ActivityBase<SettingsAdminFlowLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SettingsAdminFlowLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v12);
  v12[0] = &RemoveDeviceAdminFlowTelemetry::RemoveHandlerActivity::`vftable';
  RemoveDeviceAdminFlowTelemetry::RemoveHandlerActivity::StartActivity(
    (RemoveDeviceAdminFlowTelemetry::RemoveHandlerActivity *)v12,
    this[2]);
  if ( *((_BYTE *)this + 536) )
    LogRemainingPrintJobs(this[2]);
  if ( *this[2] == 64 )
  {
    DeviceInfoList = SetupDiCreateDeviceInfoList(0, 0);
    if ( DeviceInfoList == (HDEVINFO)-1LL )
      goto LABEL_9;
    v5 = 0;
    memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
    DeviceInfoData.cbSize = 32;
    if ( SetupDiOpenDeviceInfoW(DeviceInfoList, this[2] + 1, 0, 0, &DeviceInfoData) )
    {
      NeedReboot[0] = 0;
      v5 = DiUninstallDevice(HWND_MESSAGE|0x2LL, DeviceInfoList, &DeviceInfoData, 0, NeedReboot);
    }
    SetupDiDestroyDeviceInfoList(DeviceInfoList);
    if ( !v5 )
    {
LABEL_9:
      LastError = GetLastError();
      Instance = LastError;
      if ( LastError > 0 )
        Instance = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      Instance = 0;
    }
  }
  else
  {
    *(_QWORD *)NeedReboot = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(NeedReboot);
    Instance = CoCreateInstance(
                 &GUID_a5065670_136d_4fd6_a45f_00c85b90359c,
                 0,
                 1u,
                 &GUID_5f35421f_3313_4ad6_a3d9_dc4cd7db4bed,
                 (LPVOID *)NeedReboot);
    if ( Instance >= 0 )
      Instance = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *))(**(_QWORD **)NeedReboot + 32LL))(
                   *(_QWORD *)NeedReboot,
                   this[2]);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(NeedReboot);
  }
  LOBYTE(v6) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_RemoveDeviceConfirmatorDeprecation>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_RemoveDeviceConfirmatorDeprecation>::GetImpl'::`2'::impl,
    v6);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59215879>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59215879>::GetImpl'::`2'::impl) )
    PostQuitMessage(0);
  wil::ActivityBase<SettingsAdminFlowLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v12,
    (unsigned int)Instance);
  RemoveDeviceAdminFlowTelemetry::RemoveHandlerActivity::~RemoveHandlerActivity((RemoveDeviceAdminFlowTelemetry::RemoveHandlerActivity *)v12);
  return 0;
}

```

## disassembly

```asm
0x140035b6c  push    rbp
0x140035b6e  push    rbx
0x140035b6f  push    rsi
0x140035b70  push    rdi
0x140035b71  lea     rbp, [rsp-0C8h]
0x140035b79  sub     rsp, 1C8h
0x140035b80  mov     rax, cs:__security_cookie
0x140035b87  xor     rax, rsp
0x140035b8a  mov     [rbp+0E0h+var_30], rax
0x140035b91  mov     rdi, rcx
0x140035b94  lea     rdx, aRemovehandlera; "RemoveHandlerActivity"
0x140035b9b  lea     rcx, [rsp+1E0h+var_180]; struct wil::details::IFailureCallback *
0x140035ba0  call    ??0?$ActivityBase@VSettingsAdminFlowLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<SettingsAdminFlowLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SettingsAdminFlowLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140035ba5  lea     rax, ??_7RemoveHandlerActivity@RemoveDeviceAdminFlowTelemetry@@6B@; const RemoveDeviceAdminFlowTelemetry::RemoveHandlerActivity::`vftable'
0x140035bac  mov     [rsp+1E0h+var_180], rax
0x140035bb1  mov     rdx, [rdi+10h]; unsigned __int16 *
0x140035bb5  lea     rcx, [rsp+1E0h+var_180]; this
0x140035bba  call    ?StartActivity@RemoveHandlerActivity@RemoveDeviceAdminFlowTelemetry@@QEAAXPEBG@Z; RemoveDeviceAdminFlowTelemetry::RemoveHandlerActivity::StartActivity(ushort const *)
0x140035bbf  nop
0x140035bc0  cmp     byte ptr [rdi+218h], 0
0x140035bc7  jz      short loc_140035BD2
0x140035bc9  mov     rcx, [rdi+10h]; unsigned __int16 *
0x140035bcd  call    ?LogRemainingPrintJobs@@YAJPEBG@Z; LogRemainingPrintJobs(ushort const *)
0x140035bd2  mov     rax, [rdi+10h]
0x140035bd6  cmp     word ptr [rax], 40h ; '@'
0x140035bda  jnz     loc_140035C7C
0x140035be0  xor     edx, edx; hwndParent
0x140035be2  xor     ecx, ecx; ClassGuid
0x140035be4  call    cs:__imp_SetupDiCreateDeviceInfoList
0x140035bea  mov     rbx, rax
0x140035bed  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140035bf1  jz      short loc_140035C65
0x140035bf3  xor     esi, esi
0x140035bf5  xorps   xmm0, xmm0
0x140035bf8  movups  xmmword ptr [rsp+1E0h+var_1A8.cbSize], xmm0
0x140035bfd  movups  xmmword ptr [rsp+1E0h+var_1A8.ClassGuid.Data4+4], xmm0
0x140035c02  mov     [rsp+1E0h+var_1A8.cbSize], 20h ; ' '
0x140035c0a  mov     rdx, [rdi+10h]
0x140035c0e  add     rdx, 2; DeviceInstanceId
0x140035c12  lea     rax, [rsp+1E0h+var_1A8]
0x140035c17  mov     [rsp+1E0h+DeviceInfoData], rax; DeviceInfoData
0x140035c1c  xor     r9d, r9d; OpenFlags
0x140035c1f  xor     r8d, r8d; hwndParent
0x140035c22  mov     rcx, rbx; DeviceInfoSet
0x140035c25  call    cs:__imp_SetupDiOpenDeviceInfoW
0x140035c2b  test    eax, eax
0x140035c2d  jz      short loc_140035C54
0x140035c2f  mov     [rsp+1E0h+NeedReboot], esi
0x140035c33  lea     rax, [rsp+1E0h+NeedReboot]
0x140035c38  mov     [rsp+1E0h+DeviceInfoData], rax; NeedReboot
0x140035c3d  xor     r9d, r9d; Flags
0x140035c40  lea     r8, [rsp+1E0h+var_1A8]; DeviceInfoData
0x140035c45  mov     rdx, rbx; DeviceInfoSet
0x140035c48  or      rcx, 0FFFFFFFFFFFFFFFFh; hwndParent
0x140035c4c  call    cs:__imp_DiUninstallDevice
0x140035c52  mov     esi, eax
0x140035c54  mov     rcx, rbx; DeviceInfoSet
0x140035c57  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x140035c5d  test    esi, esi
0x140035c5f  jz      short loc_140035C65
0x140035c61  xor     ebx, ebx
0x140035c63  jmp     short loc_140035CDA
0x140035c65  call    cs:__imp_GetLastError
0x140035c6b  mov     ebx, eax
0x140035c6d  test    eax, eax
0x140035c6f  jle     short loc_140035CDA
0x140035c71  movzx   ebx, ax
0x140035c74  or      ebx, 80070000h
0x140035c7a  jmp     short loc_140035CDA
0x140035c7c  mov     qword ptr [rsp+1E0h+NeedReboot], 0
0x140035c85  lea     rcx, [rsp+1E0h+NeedReboot]
0x140035c8a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140035c8f  lea     rax, [rsp+1E0h+NeedReboot]
0x140035c94  mov     [rsp+1E0h+DeviceInfoData], rax; ppv
0x140035c99  lea     r9, _GUID_5f35421f_3313_4ad6_a3d9_dc4cd7db4bed; riid
0x140035ca0  xor     edx, edx; pUnkOuter
0x140035ca2  lea     r8d, [rdx+1]; dwClsContext
0x140035ca6  lea     rcx, _GUID_a5065670_136d_4fd6_a45f_00c85b90359c; rclsid
0x140035cad  call    cs:__imp_CoCreateInstance
0x140035cb3  mov     ebx, eax
0x140035cb5  test    eax, eax
0x140035cb7  js      short loc_140035CD0
0x140035cb9  mov     rcx, qword ptr [rsp+1E0h+NeedReboot]
0x140035cbe  mov     rax, [rcx]
0x140035cc1  mov     rdx, [rdi+10h]
0x140035cc5  mov     rax, [rax+20h]
0x140035cc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035cce  mov     ebx, eax
0x140035cd0  lea     rcx, [rsp+1E0h+NeedReboot]
0x140035cd5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140035cda  mov     dl, 1
0x140035cdc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RemoveDeviceConfirmatorDeprecation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RemoveDeviceConfirmatorDeprecation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RemoveDeviceConfirmatorDeprecation> `wil::Feature<__WilFeatureTraits_Feature_RemoveDeviceConfirmatorDeprecation>::GetImpl(void)'::`2'::impl
0x140035ce3  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_RemoveDeviceConfirmatorDeprecation@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RemoveDeviceConfirmatorDeprecation>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x140035ce8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59215879@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59215879@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59215879> `wil::Feature<__WilFeatureTraits_Feature_59215879>::GetImpl(void)'::`2'::impl
0x140035cef  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59215879@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59215879>::__private_IsEnabled(void)
0x140035cf4  test    al, al
0x140035cf6  jz      short loc_140035D00
0x140035cf8  xor     ecx, ecx; nExitCode
0x140035cfa  call    cs:__imp_PostQuitMessage
0x140035d00  mov     edx, ebx
0x140035d02  lea     rcx, [rsp+1E0h+var_180]
0x140035d07  call    ?Stop@?$ActivityBase@VSettingsAdminFlowLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<SettingsAdminFlowLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140035d0c  nop
0x140035d0d  lea     rcx, [rsp+1E0h+var_180]; this
0x140035d12  call    ??1RemoveHandlerActivity@RemoveDeviceAdminFlowTelemetry@@QEAA@XZ; RemoveDeviceAdminFlowTelemetry::RemoveHandlerActivity::~RemoveHandlerActivity(void)
0x140035d17  xor     eax, eax
0x140035d19  mov     rcx, [rbp+0E0h+var_30]
0x140035d20  xor     rcx, rsp; StackCookie
0x140035d23  call    __security_check_cookie
0x140035d28  add     rsp, 1C8h
0x140035d2f  pop     rdi
0x140035d30  pop     rsi
0x140035d31  pop     rbx
0x140035d32  pop     rbp
0x140035d33  retn
```
