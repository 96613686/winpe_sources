# CCorpDeviceAdminHelper::DisableDeviceManagement(ushort const *)

- ea: `0x140058150`
- end: `0x1400583b9`
- name: `?DisableDeviceManagement@CCorpDeviceAdminHelper@@UEAAJPEBG@Z`
- size: `617`
- prototype: `__int64 __fastcall(CCorpDeviceAdminHelper *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140005f30`
- `0x14001a2a0`
- `0x14001f3d4`
- `0x140025324`
- `0x14003dcb4`
- `0x14005773c`
- `0x140057a50`
- `0x140057ab0`
- `0x140057c74`
- `0x140057da0`
- `0x140057ffc`
- `0x140058150`
- `0x140058e78`
- `0x140058f24`
- `0x14007d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140058260`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140058260`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140058360`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140058370`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140058360`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140058370`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CCorpDeviceAdminHelper::DisableDeviceManagement(
        CCorpDeviceAdminHelper *this,
        const unsigned __int16 *a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdx
  HSTRING v5; // rbx
  int v6; // eax
  int v7; // edi
  PCWSTR StringRawBuffer; // rax
  int v9; // r8d
  int v10; // r9d
  __int64 v11; // rcx
  int v12; // ecx
  __int64 v13; // rsi
  __int64 (__fastcall *v14)(__int64, HSTRING, _QWORD); // rdi
  int v15; // eax
  int v16; // edx
  char *v17; // r8
  __int64 v18; // rdx
  int v20; // [rsp+20h] [rbp-E0h]
  int (__fastcall ***v21)(_QWORD, GUID *, __int64 *); // [rsp+30h] [rbp-D0h] BYREF
  HSTRING string; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING v23; // [rsp+40h] [rbp-C0h] BYREF
  const unsigned __int16 *v24; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v25[2]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v26[42]; // [rsp+60h] [rbp-A0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v27; // [rsp+1B0h] [rbp+B0h] BYREF
  PCWSTR v28; // [rsp+1C0h] [rbp+C0h]
  int v29; // [rsp+1C8h] [rbp+C8h]
  int v30; // [rsp+1CCh] [rbp+CCh]
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  v24 = a2;
  wil::ActivityBase<CorpDeviceManagementSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CorpDeviceManagementSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v26);
  v26[0] = &CorpDeviceManagementSettingsTelemetry::UnEnrollment::`vftable';
  CorpDeviceManagementSettingsTelemetry::UnEnrollment::StartActivity((CorpDeviceManagementSettingsTelemetry::UnEnrollment *)v26);
  v25[0] = 0;
  v23 = 0;
  string = 0;
  v2 = Microsoft::WRL::Wrappers::HString::Set(
         (Microsoft::WRL::Wrappers::HString *)&v23,
         L"Windows.Internal.Management.Enrollment.Enroller",
         0x2Fu);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = 139;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\corpdevicesettings\\corpdeviceadminhelper\\corpdeviceadminhelper.cpp",
      (const char *)(unsigned int)v2,
      v20);
    goto LABEL_21;
  }
  v2 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(&string, &v24);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = 140;
    goto LABEL_5;
  }
  v5 = string;
  v6 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>>(
         (__int64)v23,
         v25);
  v7 = v6;
  if ( v6 >= 0 )
  {
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 2) != 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      if ( StringRawBuffer )
      {
        v11 = -1;
        do
          ++v11;
        while ( StringRawBuffer[v11] );
        v12 = 2 * v11 + 2;
      }
      else
      {
        StringRawBuffer = L"NULL";
        v12 = 10;
      }
      v28 = StringRawBuffer;
      v29 = v12;
      v30 = 0;
      McGenEventWrite_EventWriteTransfer(
        (int)&MDM_ENTERPRISE_DIAGNOSTICS_Context,
        (int)&EnterpriseDiagnosticsUserInitiatedUnEnrollment,
        v9,
        v10,
        &v27);
    }
    v21 = 0;
    v13 = v25[0];
    v14 = *(__int64 (__fastcall **)(__int64, HSTRING, _QWORD))(*(_QWORD *)v25[0] + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
    v15 = v14(v13, v5, &v21);
    v3 = v15;
    if ( v15 >= 0 )
    {
      v15 = WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(
              v21,
              v16,
              v17);
      v3 = v15;
      if ( v15 >= 0 )
      {
        wil::ActivityBase<CorpDeviceManagementSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v26);
        LODWORD(v24) = 0;
        CorpDeviceManagementSettingsTelemetry::UnEnrollmentSuccess<long>(&v24);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
        v3 = 0;
        goto LABEL_21;
      }
      v18 = 147;
    }
    else
    {
      v18 = 146;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\corpdevicesettings\\corpdeviceadminhelper\\corpdeviceadminhelper.cpp",
      (const char *)(unsigned int)v15,
      v20);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8E,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\corpdevicesettings\\corpdeviceadminhelper\\corpdeviceadminhelper.cpp",
      (const char *)(unsigned int)v6,
      v20);
    v3 = v7;
  }
LABEL_21:
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v23);
  v23 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v25);
  CorpDeviceManagementSettingsTelemetry::UnEnrollment::~UnEnrollment((CorpDeviceManagementSettingsTelemetry::UnEnrollment *)v26);
  return v3;
}

```

## disassembly

```asm
0x140058150  mov     [rsp-8+arg_0], rbx
0x140058155  mov     [rsp-8+arg_10], rsi
0x14005815a  push    rbp
0x14005815b  push    rdi
0x14005815c  push    r14
0x14005815e  lea     rbp, [rsp-0E0h]
0x140058166  sub     rsp, 1E0h
0x14005816d  mov     rax, cs:__security_cookie
0x140058174  xor     rax, rsp
0x140058177  mov     [rbp+0F0h+var_20], rax
0x14005817e  mov     [rsp+1F0h+var_1A8], rdx
0x140058183  lea     rdx, aUnenrollment; "UnEnrollment"
0x14005818a  lea     rcx, [rsp+1F0h+var_190]; struct wil::details::IFailureCallback *
0x14005818f  call    ??0?$ActivityBase@VCorpDeviceManagementSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CorpDeviceManagementSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CorpDeviceManagementSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140058194  lea     rax, ??_7UnEnrollment@CorpDeviceManagementSettingsTelemetry@@6B@; const CorpDeviceManagementSettingsTelemetry::UnEnrollment::`vftable'
0x14005819b  mov     [rsp+1F0h+var_190], rax
0x1400581a0  lea     rcx, [rsp+1F0h+var_190]; this
0x1400581a5  call    ?StartActivity@UnEnrollment@CorpDeviceManagementSettingsTelemetry@@QEAAXXZ; CorpDeviceManagementSettingsTelemetry::UnEnrollment::StartActivity(void)
0x1400581aa  nop
0x1400581ab  xor     r14d, r14d
0x1400581ae  mov     [rsp+1F0h+var_1A0], r14
0x1400581b3  mov     [rsp+1F0h+var_1B0], r14
0x1400581b8  mov     [rsp+1F0h+string], r14
0x1400581bd  lea     r8d, [r14+2Fh]; unsigned int
0x1400581c1  lea     rdx, ?RuntimeClass_Windows_Internal_Management_Enrollment_Enroller@@3QBGB; "Windows.Internal.Management.Enrollment."...
0x1400581c8  lea     rcx, [rsp+1F0h+var_1B0]; this
0x1400581cd  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x1400581d2  mov     ebx, eax
0x1400581d4  test    eax, eax
0x1400581d6  jns     short loc_1400581DF
0x1400581d8  mov     edx, 8Bh
0x1400581dd  jmp     short loc_1400581F9
0x1400581df  lea     rdx, [rsp+1F0h+var_1A8]
0x1400581e4  lea     rcx, [rsp+1F0h+string]
0x1400581e9  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x1400581ee  mov     ebx, eax
0x1400581f0  test    eax, eax
0x1400581f2  jns     short loc_140058214
0x1400581f4  mov     edx, 8Ch; void *
0x1400581f9  lea     r8, aPcshellShellSy_23; "pcshell\\shell\\systemsettings\\adminfl"...
0x140058200  mov     r9d, eax; char *
0x140058203  mov     rcx, [rbp+0F8h]; this
0x14005820a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005820f  jmp     loc_14005835B
0x140058214  mov     rbx, [rsp+1F0h+string]
0x140058219  lea     rdx, [rsp+1F0h+var_1A0]
0x14005821e  mov     rcx, [rsp+1F0h+var_1B0]
0x140058223  call    ??$ActivateInstance@V?$ComPtr@UIEnrollment@Enrollment@Management@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIEnrollment@Enrollment@Management@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>>)
0x140058228  mov     edi, eax
0x14005822a  test    eax, eax
0x14005822c  jns     short loc_140058250
0x14005822e  mov     rcx, [rbp+0F8h]; this
0x140058235  mov     r9d, eax; char *
0x140058238  lea     r8, aPcshellShellSy_23; "pcshell\\shell\\systemsettings\\adminfl"...
0x14005823f  mov     edx, 8Eh; void *
0x140058244  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140058249  mov     ebx, edi
0x14005824b  jmp     loc_14005835B
0x140058250  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 2
0x140058257  jz      short loc_1400582C1
0x140058259  xor     edx, edx; length
0x14005825b  mov     rcx, [rsp+1F0h+string]; string
0x140058260  call    cs:__imp_WindowsGetStringRawBuffer
0x140058266  test    rax, rax
0x140058269  jz      short loc_140058282
0x14005826b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14005826f  inc     rcx
0x140058272  cmp     [rax+rcx*2], r14w
0x140058277  jnz     short loc_14005826F
0x140058279  lea     ecx, ds:2[rcx*2]
0x140058280  jmp     short loc_14005828E
0x140058282  lea     rax, aNull_0; "NULL"
0x140058289  mov     ecx, 0Ah
0x14005828e  mov     [rbp+0F0h+var_30], rax
0x140058295  mov     [rbp+0F0h+var_28], ecx
0x14005829b  mov     [rbp+0F0h+var_24], r14d
0x1400582a2  lea     rax, [rbp+0F0h+var_40]
0x1400582a9  mov     qword ptr [rsp+1F0h+var_1D0], rax; int
0x1400582ae  lea     rdx, EnterpriseDiagnosticsUserInitiatedUnEnrollment; int
0x1400582b5  lea     rcx, MDM_ENTERPRISE_DIAGNOSTICS_Context; int
0x1400582bc  call    McGenEventWrite_EventWriteTransfer
0x1400582c1  mov     [rsp+1F0h+var_1C0], r14
0x1400582c6  mov     rsi, [rsp+1F0h+var_1A0]
0x1400582cb  mov     rax, [rsi]
0x1400582ce  mov     rdi, [rax+30h]
0x1400582d2  lea     rcx, [rsp+1F0h+var_1C0]
0x1400582d7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400582dc  lea     r8, [rsp+1F0h+var_1C0]
0x1400582e1  mov     rdx, rbx
0x1400582e4  mov     rcx, rsi
0x1400582e7  mov     rax, rdi
0x1400582ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400582ef  mov     ebx, eax
0x1400582f1  test    eax, eax
0x1400582f3  jns     short loc_14005831D
0x1400582f5  mov     edx, 92h; void *
0x1400582fa  lea     r8, aPcshellShellSy_23; "pcshell\\shell\\systemsettings\\adminfl"...
0x140058301  mov     r9d, eax; char *
0x140058304  mov     rcx, [rbp+0F8h]; this
0x14005830b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140058310  nop
0x140058311  lea     rcx, [rsp+1F0h+var_1C0]
0x140058316  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14005831b  jmp     short loc_14005835B
0x14005831d  mov     rcx, [rsp+1F0h+var_1C0]
0x140058322  call    ??$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)
0x140058327  mov     ebx, eax
0x140058329  test    eax, eax
0x14005832b  jns     short loc_140058334
0x14005832d  mov     edx, 93h
0x140058332  jmp     short loc_1400582FA
0x140058334  lea     rcx, [rsp+1F0h+var_190]
0x140058339  call    ?Stop@?$ActivityBase@VCorpDeviceManagementSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CorpDeviceManagementSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x14005833e  mov     dword ptr [rsp+1F0h+var_1A8], r14d
0x140058343  lea     rcx, [rsp+1F0h+var_1A8]
0x140058348  call    ??$UnEnrollmentSuccess@J@CorpDeviceManagementSettingsTelemetry@@SAX$$QEAJ@Z; CorpDeviceManagementSettingsTelemetry::UnEnrollmentSuccess<long>(long &&)
0x14005834d  nop
0x14005834e  lea     rcx, [rsp+1F0h+var_1C0]
0x140058353  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140058358  mov     ebx, r14d
0x14005835b  mov     rcx, [rsp+1F0h+string]; string
0x140058360  call    cs:__imp_WindowsDeleteString
0x140058366  mov     [rsp+1F0h+string], r14
0x14005836b  mov     rcx, [rsp+1F0h+var_1B0]; string
0x140058370  call    cs:__imp_WindowsDeleteString
0x140058376  mov     [rsp+1F0h+var_1B0], r14
0x14005837b  lea     rcx, [rsp+1F0h+var_1A0]
0x140058380  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140058385  nop
0x140058386  lea     rcx, [rsp+1F0h+var_190]; this
0x14005838b  call    ??1UnEnrollment@CorpDeviceManagementSettingsTelemetry@@QEAA@XZ; CorpDeviceManagementSettingsTelemetry::UnEnrollment::~UnEnrollment(void)
0x140058390  mov     eax, ebx
0x140058392  mov     rcx, [rbp+0F0h+var_20]
0x140058399  xor     rcx, rsp; StackCookie
0x14005839c  call    __security_check_cookie
0x1400583a1  lea     r11, [rsp+1F0h+var_10]
0x1400583a9  mov     rbx, [r11+20h]
0x1400583ad  mov     rsi, [r11+30h]
0x1400583b1  mov     rsp, r11
0x1400583b4  pop     r14
0x1400583b6  pop     rdi
0x1400583b7  pop     rbp
0x1400583b8  retn
```
