# CCorpDeviceAdminHelper::EnableDeviceManagement(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong,int *,int *,ushort const *,ushort const *,_CorpDeviceResult *)

- ea: `0x1400583c0`
- end: `0x140058893`
- name: `?EnableDeviceManagement@CCorpDeviceAdminHelper@@UEAAJPEBG0000KKPEAH100PEAW4_CorpDeviceResult@@@Z`
- size: `1235`
- prototype: `int(CCorpDeviceAdminHelper *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, int *, int *, const unsigned __int16 *, const unsigned __int16 *, enum _CorpDeviceResult *)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140005f30`
- `0x14001a2a0`
- `0x14001f3d4`
- `0x140025324`
- `0x14005773c`
- `0x140057a50`
- `0x140057b48`
- `0x140057da0`
- `0x140057f48`
- `0x1400583c0`
- `0x140058dcc`
- `0x140058f24`
- `0x14007d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400587b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400587c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400587d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400587e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400587f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140058801`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140058811`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400587b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400587c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400587d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400587e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400587f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140058801`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140058811`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CCorpDeviceAdminHelper::EnableDeviceManagement(
        CCorpDeviceAdminHelper *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned int a7,
        unsigned int a8,
        int *a9,
        int *a10,
        const unsigned __int16 *a11,
        const unsigned __int16 *a12,
        enum _CorpDeviceResult *a13)
{
  int v16; // esi
  int v17; // eax
  unsigned int v18; // ebx
  __int64 v19; // rdx
  __int64 v20; // rbx
  __int64 v21; // r8
  int v22; // eax
  int v23; // edi
  __int64 v24; // r8
  int v25; // edi
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r8
  int v29; // eax
  __int64 v30; // rdi
  __int64 (__fastcall *v31)(__int64, _OWORD *, int *); // rbx
  int v32; // eax
  int v33; // edx
  __int64 v34; // r8
  __int64 v35; // rdx
  __int64 v36; // rdi
  __int64 (__fastcall *v37)(__int64, __int64 *); // rbx
  int v39[2]; // [rsp+20h] [rbp-E0h] BYREF
  HSTRING v40; // [rsp+28h] [rbp-D8h] BYREF
  HSTRING string; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING v42; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING v43; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING v44; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING v45; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING v46; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v47; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v48; // [rsp+68h] [rbp-98h] BYREF
  __int64 v49; // [rsp+70h] [rbp-90h] BYREF
  const unsigned __int16 *v50; // [rsp+78h] [rbp-88h] BYREF
  const unsigned __int16 *v51; // [rsp+80h] [rbp-80h] BYREF
  enum _CorpDeviceResult *v52; // [rsp+88h] [rbp-78h]
  __int128 v53; // [rsp+90h] [rbp-70h]
  __int128 v54; // [rsp+A0h] [rbp-60h]
  __int128 v55; // [rsp+B0h] [rbp-50h]
  _BYTE v56[24]; // [rsp+C0h] [rbp-40h]
  _OWORD v57[4]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v58; // [rsp+120h] [rbp+20h]
  _QWORD v59[42]; // [rsp+130h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  v51 = a11;
  v50 = a12;
  v52 = a13;
  wil::ActivityBase<CorpDeviceManagementSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CorpDeviceManagementSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v59);
  v59[0] = &CorpDeviceManagementSettingsTelemetry::Enrollment::`vftable';
  CorpDeviceManagementSettingsTelemetry::Enrollment::StartActivity((CorpDeviceManagementSettingsTelemetry::Enrollment *)v59);
  if ( !a7 )
  {
    v16 = 0;
    goto LABEL_7;
  }
  v16 = 1;
  if ( a7 == 1 || (v16 = 2, a7 == 2) )
  {
LABEL_7:
    v49 = 0;
    v48 = 0;
    HIDWORD(v54) = 0;
    *(_QWORD *)&v56[12] = 0;
    *(_DWORD *)&v56[20] = 0;
    v46 = 0;
    v40 = 0;
    v45 = 0;
    v44 = 0;
    v43 = 0;
    v42 = 0;
    v47 = 0;
    string = 0;
    v17 = Microsoft::WRL::Wrappers::HString::Set(
            (Microsoft::WRL::Wrappers::HString *)&v46,
            L"Windows.Internal.Management.Enrollment.Enroller",
            0x2Fu);
    v18 = v17;
    if ( v17 < 0 )
    {
      v19 = 87;
LABEL_11:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\corpdevicesettings\\corpdeviceadminhelper\\corpdeviceadminhelper.cpp",
        (const char *)(unsigned int)v17,
        v39[0]);
      goto LABEL_47;
    }
    v17 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>>(
            (__int64)v46,
            &v49);
    v18 = v17;
    if ( v17 < 0 )
    {
      v19 = 89;
      goto LABEL_11;
    }
    v20 = -1;
    if ( *a9 )
    {
      Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(&v40, &v50);
      *(_QWORD *)&v54 = v40;
      Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(&string, &v51);
      *(_QWORD *)&v55 = string;
    }
    else
    {
      v21 = -1;
      do
        ++v21;
      while ( a3[v21] );
      v22 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&v40, a3, (int)v21 + 1);
      v23 = v22;
      if ( v22 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5D,
          (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\corpdevicesettings\\corpdeviceadminhelper\\corpdevic"
                        "eadminhelper.cpp",
          (const char *)(unsigned int)v22,
          v39[0]);
        v18 = v23;
LABEL_47:
        WindowsDeleteString(string);
        string = 0;
        WindowsDeleteString(v42);
        v42 = 0;
        WindowsDeleteString(v43);
        v43 = 0;
        WindowsDeleteString(v44);
        v44 = 0;
        WindowsDeleteString(v45);
        v45 = 0;
        WindowsDeleteString(v40);
        v40 = 0;
        WindowsDeleteString(v46);
        v46 = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v48);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
        CorpDeviceManagementSettingsTelemetry::Enrollment::~Enrollment((CorpDeviceManagementSettingsTelemetry::Enrollment *)v59);
        return v18;
      }
      *(_QWORD *)&v54 = v40;
      *(_QWORD *)&v55 = 0;
    }
    v24 = -1;
    do
      ++v24;
    while ( a4[v24] );
    v25 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&v45, a4, (int)v24 + 1);
    if ( v25 < 0 )
    {
      v26 = 110;
LABEL_24:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v26,
        (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\corpdevicesettings\\corpdeviceadminhelper\\corpdeviceadminhelper.cpp",
        (const char *)(unsigned int)v25,
        v39[0]);
      v18 = v25;
      goto LABEL_47;
    }
    *((_QWORD *)&v53 + 1) = v45;
    v27 = -1;
    do
      ++v27;
    while ( a2[v27] );
    v25 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&v44, a2, (int)v27 + 1);
    if ( v25 < 0 )
    {
      v26 = 112;
      goto LABEL_24;
    }
    *(_QWORD *)&v53 = v44;
    v28 = -1;
    do
      ++v28;
    while ( a5[v28] );
    v25 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&v43, a5, (int)v28 + 1);
    if ( v25 < 0 )
    {
      v26 = 114;
      goto LABEL_24;
    }
    *(_QWORD *)v56 = v43;
    do
      ++v20;
    while ( a6[v20] );
    v29 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&v42, a6, (int)v20 + 1);
    v18 = v29;
    if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x74,
        (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\corpdevicesettings\\corpdeviceadminhelper\\corpdeviceadminhelper.cpp",
        (const char *)(unsigned int)v29,
        v39[0]);
      goto LABEL_47;
    }
    *((_QWORD *)&v55 + 1) = v42;
    DWORD2(v54) = v16;
    *(_DWORD *)&v56[8] = a8;
    *(_QWORD *)v39 = 0;
    v30 = v49;
    v31 = *(__int64 (__fastcall **)(__int64, _OWORD *, int *))(*(_QWORD *)v49 + 56LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v39);
    v57[0] = v53;
    v57[1] = v54;
    v57[2] = v55;
    v57[3] = *(_OWORD *)v56;
    v58 = *(_QWORD *)&v56[16];
    v32 = v31(v30, v57, v39);
    v18 = v32;
    if ( v32 >= 0 )
    {
      v32 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *>>(
              *(int (__fastcall ****)(_QWORD, GUID *, __int64 *))v39,
              v33,
              v34);
      v18 = v32;
      if ( v32 >= 0 )
      {
        v36 = *(_QWORD *)v39;
        v37 = *(__int64 (__fastcall **)(__int64, __int64 *))(**(_QWORD **)v39 + 64LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v48);
        v32 = v37(v36, &v48);
        v18 = v32;
        if ( v32 >= 0 )
        {
          v32 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v48 + 64LL))(v48, &v47);
          v18 = v32;
          if ( v32 >= 0 )
          {
            *(_DWORD *)v52 = 3;
            wil::ActivityBase<CorpDeviceManagementSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v59);
            v18 = v47;
            goto LABEL_46;
          }
          v35 = 124;
        }
        else
        {
          v35 = 123;
        }
      }
      else
      {
        v35 = 122;
      }
    }
    else
    {
      v35 = 121;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v35,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\corpdevicesettings\\corpdeviceadminhelper\\corpdeviceadminhelper.cpp",
      (const char *)(unsigned int)v32,
      v39[0]);
LABEL_46:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v39);
    goto LABEL_47;
  }
  if ( a7 == 3 )
  {
    v16 = 3;
    goto LABEL_7;
  }
  CorpDeviceManagementSettingsTelemetry::Enrollment::~Enrollment((CorpDeviceManagementSettingsTelemetry::Enrollment *)v59);
  return 2147942487LL;
}

```

## disassembly

```asm
0x1400583c0  mov     [rsp-8+arg_0], rbx
0x1400583c5  push    rbp
0x1400583c6  push    rsi
0x1400583c7  push    rdi
0x1400583c8  push    r12
0x1400583ca  push    r13
0x1400583cc  push    r14
0x1400583ce  push    r15
0x1400583d0  lea     rbp, [rsp-190h]
0x1400583d8  sub     rsp, 290h
0x1400583df  mov     rax, cs:__security_cookie
0x1400583e6  xor     rax, rsp
0x1400583e9  mov     [rbp+1C0h+var_40], rax
0x1400583f0  mov     r14, r9
0x1400583f3  mov     rdi, r8
0x1400583f6  mov     r15, rdx
0x1400583f9  mov     r12, [rbp+1C0h+arg_20]
0x140058400  mov     r13, [rbp+1C0h+arg_28]
0x140058407  mov     rax, [rbp+1C0h+arg_50]
0x14005840e  mov     [rbp+1C0h+var_240], rax
0x140058412  mov     rax, [rbp+1C0h+arg_58]
0x140058419  mov     [rsp+2C0h+var_248], rax
0x14005841e  mov     rax, [rbp+1C0h+arg_60]
0x140058425  mov     [rbp+1C0h+var_238], rax
0x140058429  lea     rdx, aEnrollment; "Enrollment"
0x140058430  lea     rcx, [rbp+1C0h+var_190]; struct wil::details::IFailureCallback *
0x140058434  call    ??0?$ActivityBase@VCorpDeviceManagementSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CorpDeviceManagementSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CorpDeviceManagementSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140058439  lea     rax, ??_7Enrollment@CorpDeviceManagementSettingsTelemetry@@6B@; const CorpDeviceManagementSettingsTelemetry::Enrollment::`vftable'
0x140058440  mov     [rbp+1C0h+var_190], rax
0x140058444  lea     rcx, [rbp+1C0h+var_190]; this
0x140058448  call    ?StartActivity@Enrollment@CorpDeviceManagementSettingsTelemetry@@QEAAXXZ; CorpDeviceManagementSettingsTelemetry::Enrollment::StartActivity(void)
0x14005844d  nop
0x14005844e  mov     eax, [rbp+1C0h+arg_30]
0x140058454  xor     ecx, ecx
0x140058456  test    eax, eax
0x140058458  jnz     short loc_14005845E
0x14005845a  mov     esi, ecx
0x14005845c  jmp     short loc_14005847B
0x14005845e  mov     esi, 1
0x140058463  cmp     eax, esi
0x140058465  jz      short loc_14005847B
0x140058467  mov     esi, 2
0x14005846c  cmp     eax, esi
0x14005846e  jz      short loc_14005847B
0x140058470  cmp     eax, 3
0x140058473  jnz     loc_14005885B
0x140058479  mov     esi, eax
0x14005847b  mov     [rsp+2C0h+var_250], rcx
0x140058480  mov     [rsp+2C0h+var_258], rcx
0x140058485  mov     dword ptr [rbp+1C0h+var_220+0Ch], ecx
0x140058488  mov     qword ptr [rbp+1C0h+var_200+0Ch], rcx
0x14005848c  mov     [rbp+1C0h+var_1EC], ecx
0x14005848f  mov     [rsp+2C0h+var_268], rcx
0x140058494  mov     [rsp+2C0h+var_298], rcx
0x140058499  mov     [rsp+2C0h+var_270], rcx
0x14005849e  mov     [rsp+2C0h+var_278], rcx
0x1400584a3  mov     [rsp+2C0h+var_280], rcx
0x1400584a8  mov     [rsp+2C0h+var_288], rcx
0x1400584ad  mov     [rsp+2C0h+var_260], ecx
0x1400584b1  mov     [rsp+2C0h+string], rcx
0x1400584b6  mov     r8d, 2Fh ; '/'; unsigned int
0x1400584bc  lea     rdx, ?RuntimeClass_Windows_Internal_Management_Enrollment_Enroller@@3QBGB; "Windows.Internal.Management.Enrollment."...
0x1400584c3  lea     rcx, [rsp+2C0h+var_268]; this
0x1400584c8  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x1400584cd  mov     ebx, eax
0x1400584cf  test    eax, eax
0x1400584d1  jns     short loc_1400584DA
0x1400584d3  mov     edx, 57h ; 'W'
0x1400584d8  jmp     short loc_1400584F4
0x1400584da  lea     rdx, [rsp+2C0h+var_250]
0x1400584df  mov     rcx, [rsp+2C0h+var_268]
0x1400584e4  call    ??$ActivateInstance@V?$ComPtr@UIEnrollment@Enrollment@Management@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIEnrollment@Enrollment@Management@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>>)
0x1400584e9  mov     ebx, eax
0x1400584eb  xor     ecx, ecx
0x1400584ed  test    eax, eax
0x1400584ef  jns     short loc_140058512
0x1400584f1  lea     edx, [rcx+59h]; void *
0x1400584f4  lea     r8, aPcshellShellSy_23; "pcshell\\shell\\systemsettings\\adminfl"...
0x1400584fb  mov     r9d, eax; char *
0x1400584fe  mov     rcx, [rbp+1C8h]; this
0x140058505  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005850a  xor     r14d, r14d
0x14005850d  jmp     loc_1400587AC
0x140058512  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140058516  mov     rax, [rbp+1C0h+arg_40]
0x14005851d  cmp     [rax], ecx
0x14005851f  jnz     short loc_140058574
0x140058521  mov     r8, rbx
0x140058524  inc     r8
0x140058527  cmp     [rdi+r8*2], cx
0x14005852c  jnz     short loc_140058524
0x14005852e  inc     r8d; unsigned int
0x140058531  mov     rdx, rdi; unsigned __int16 *
0x140058534  lea     rcx, [rsp+2C0h+var_298]; this
0x140058539  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x14005853e  mov     edi, eax
0x140058540  xor     ecx, ecx
0x140058542  test    eax, eax
0x140058544  jns     short loc_140058565
0x140058546  mov     rcx, [rbp+1C8h]; this
0x14005854d  mov     r9d, eax; char *
0x140058550  lea     r8, aPcshellShellSy_23; "pcshell\\shell\\systemsettings\\adminfl"...
0x140058557  mov     edx, 5Dh ; ']'; void *
0x14005855c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140058561  mov     ebx, edi
0x140058563  jmp     short loc_14005850A
0x140058565  mov     rax, [rsp+2C0h+var_298]
0x14005856a  mov     qword ptr [rbp+1C0h+var_220], rax
0x14005856e  mov     qword ptr [rbp+1C0h+var_210], rcx
0x140058572  jmp     short loc_1400585A5
0x140058574  lea     rdx, [rsp+2C0h+var_248]
0x140058579  lea     rcx, [rsp+2C0h+var_298]
0x14005857e  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x140058583  mov     rax, [rsp+2C0h+var_298]
0x140058588  mov     qword ptr [rbp+1C0h+var_220], rax
0x14005858c  lea     rdx, [rbp+1C0h+var_240]
0x140058590  lea     rcx, [rsp+2C0h+string]
0x140058595  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x14005859a  mov     rax, [rsp+2C0h+string]
0x14005859f  mov     qword ptr [rbp+1C0h+var_210], rax
0x1400585a3  xor     ecx, ecx
0x1400585a5  mov     r8, rbx
0x1400585a8  inc     r8
0x1400585ab  cmp     [r14+r8*2], cx
0x1400585b0  jnz     short loc_1400585A8
0x1400585b2  inc     r8d; unsigned int
0x1400585b5  mov     rdx, r14; unsigned __int16 *
0x1400585b8  lea     rcx, [rsp+2C0h+var_270]; this
0x1400585bd  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x1400585c2  mov     edi, eax
0x1400585c4  xor     r14d, r14d
0x1400585c7  test    eax, eax
0x1400585c9  jns     short loc_1400585EC
0x1400585cb  lea     edx, [r14+6Eh]; void *
0x1400585cf  mov     rcx, [rbp+1C8h]; this
0x1400585d6  mov     r9d, edi; char *
0x1400585d9  lea     r8, aPcshellShellSy_23; "pcshell\\shell\\systemsettings\\adminfl"...
0x1400585e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400585e5  mov     ebx, edi
0x1400585e7  jmp     loc_1400587AC
0x1400585ec  mov     rax, [rsp+2C0h+var_270]
0x1400585f1  mov     qword ptr [rbp+1C0h+var_230+8], rax
0x1400585f5  mov     r8, rbx
0x1400585f8  inc     r8
0x1400585fb  cmp     [r15+r8*2], r14w
0x140058600  jnz     short loc_1400585F8
0x140058602  inc     r8d; unsigned int
0x140058605  mov     rdx, r15; unsigned __int16 *
0x140058608  lea     rcx, [rsp+2C0h+var_278]; this
0x14005860d  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x140058612  mov     edi, eax
0x140058614  test    eax, eax
0x140058616  jns     short loc_14005861F
0x140058618  mov     edx, 70h ; 'p'
0x14005861d  jmp     short loc_1400585CF
0x14005861f  mov     rax, [rsp+2C0h+var_278]
0x140058624  mov     qword ptr [rbp+1C0h+var_230], rax
0x140058628  mov     r8, rbx
0x14005862b  inc     r8
0x14005862e  cmp     [r12+r8*2], r14w
0x140058633  jnz     short loc_14005862B
0x140058635  inc     r8d; unsigned int
0x140058638  mov     rdx, r12; unsigned __int16 *
0x14005863b  lea     rcx, [rsp+2C0h+var_280]; this
0x140058640  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x140058645  mov     edi, eax
0x140058647  test    eax, eax
0x140058649  jns     short loc_140058655
0x14005864b  mov     edx, 72h ; 'r'
0x140058650  jmp     loc_1400585CF
0x140058655  mov     rax, [rsp+2C0h+var_280]
0x14005865a  mov     qword ptr [rbp+1C0h+var_200], rax
0x14005865e  inc     rbx
0x140058661  cmp     [r13+rbx*2+0], r14w
0x140058667  jnz     short loc_14005865E
0x140058669  lea     r8d, [rbx+1]; unsigned int
0x14005866d  mov     rdx, r13; unsigned __int16 *
0x140058670  lea     rcx, [rsp+2C0h+var_288]; this
0x140058675  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x14005867a  mov     ebx, eax
0x14005867c  test    eax, eax
0x14005867e  jns     short loc_1400586A0
0x140058680  mov     rcx, [rbp+1C8h]; this
0x140058687  mov     r9d, eax; char *
0x14005868a  lea     r8, aPcshellShellSy_23; "pcshell\\shell\\systemsettings\\adminfl"...
0x140058691  mov     edx, 74h ; 't'; void *
0x140058696  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005869b  jmp     loc_1400587AC
0x1400586a0  mov     rax, [rsp+2C0h+var_288]
0x1400586a5  mov     qword ptr [rbp+1C0h+var_210+8], rax
0x1400586a9  mov     dword ptr [rbp+1C0h+var_220+8], esi
0x1400586ac  mov     eax, [rbp+1C0h+arg_38]
0x1400586b2  mov     dword ptr [rbp+1C0h+var_200+8], eax
0x1400586b5  mov     qword ptr [rsp+2C0h+var_2A0], r14; int
0x1400586ba  mov     rdi, [rsp+2C0h+var_250]
0x1400586bf  mov     rax, [rdi]
0x1400586c2  mov     rbx, [rax+38h]
0x1400586c6  lea     rcx, [rsp+2C0h+var_2A0]
0x1400586cb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400586d0  movaps  xmm0, [rbp+1C0h+var_230]
0x1400586d4  movaps  [rbp+1C0h+var_1E0], xmm0
0x1400586d8  movaps  xmm1, [rbp+1C0h+var_220]
0x1400586dc  movaps  [rbp+1C0h+var_1D0], xmm1
0x1400586e0  movaps  xmm0, [rbp+1C0h+var_210]
0x1400586e4  movaps  [rbp+1C0h+var_1C0], xmm0
0x1400586e8  movaps  xmm1, [rbp+1C0h+var_200]
0x1400586ec  movaps  [rbp+1C0h+var_1B0], xmm1
0x1400586f0  movsd   xmm0, qword ptr [rbp-30h]
0x1400586f5  movsd   [rbp+1C0h+var_1A0], xmm0
0x1400586fa  lea     r8, [rsp+2C0h+var_2A0]
0x1400586ff  lea     rdx, [rbp+1C0h+var_1E0]
0x140058703  mov     rcx, rdi
0x140058706  mov     rax, rbx
0x140058709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005870e  mov     ebx, eax
0x140058710  test    eax, eax
0x140058712  jns     short loc_14005871B
0x140058714  mov     edx, 79h ; 'y'
0x140058719  jmp     short loc_14005878A
0x14005871b  mov     rcx, qword ptr [rsp+2C0h+var_2A0]
0x140058720  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *> *,tagCOWAIT_FLAGS,void *)
0x140058725  mov     ebx, eax
0x140058727  test    eax, eax
0x140058729  jns     short loc_140058732
0x14005872b  mov     edx, 7Ah ; 'z'
0x140058730  jmp     short loc_14005878A
0x140058732  mov     rdi, qword ptr [rsp+2C0h+var_2A0]
0x140058737  mov     rax, [rdi]
0x14005873a  mov     rbx, [rax+40h]
0x14005873e  lea     rcx, [rsp+2C0h+var_258]
0x140058743  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140058748  lea     rdx, [rsp+2C0h+var_258]
0x14005874d  mov     rcx, rdi
0x140058750  mov     rax, rbx
0x140058753  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140058758  mov     ebx, eax
0x14005875a  test    eax, eax
0x14005875c  jns     short loc_140058765
0x14005875e  mov     edx, 7Bh ; '{'
0x140058763  jmp     short loc_14005878A
0x140058765  mov     rcx, [rsp+2C0h+var_258]
0x14005876a  mov     rax, [rcx]
0x14005876d  lea     rdx, [rsp+2C0h+var_260]
0x140058772  mov     rax, [rax+40h]
0x140058776  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005877b  mov     ebx, eax
0x14005877d  test    eax, eax
0x14005877f  jns     loc_14005883F
0x140058785  mov     edx, 7Ch ; '|'; void *
0x14005878a  mov     r9d, eax; char *
0x14005878d  lea     r8, aPcshellShellSy_23; "pcshell\\shell\\systemsettings\\adminfl"...
0x140058794  mov     rcx, [rbp+1C8h]; this
0x14005879b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400587a0  nop
0x1400587a1  lea     rcx, [rsp+2C0h+var_2A0]
0x1400587a6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400587ab  nop
0x1400587ac  mov     rcx, [rsp+2C0h+string]; string
0x1400587b1  call    cs:__imp_WindowsDeleteString
0x1400587b7  mov     [rsp+2C0h+string], r14
0x1400587bc  mov     rcx, [rsp+2C0h+var_288]; string
0x1400587c1  call    cs:__imp_WindowsDeleteString
0x1400587c7  mov     [rsp+2C0h+var_288], r14
0x1400587cc  mov     rcx, [rsp+2C0h+var_280]; string
0x1400587d1  call    cs:__imp_WindowsDeleteString
0x1400587d7  mov     [rsp+2C0h+var_280], r14
0x1400587dc  mov     rcx, [rsp+2C0h+var_278]; string
0x1400587e1  call    cs:__imp_WindowsDeleteString
0x1400587e7  mov     [rsp+2C0h+var_278], r14
0x1400587ec  mov     rcx, [rsp+2C0h+var_270]; string
0x1400587f1  call    cs:__imp_WindowsDeleteString
0x1400587f7  mov     [rsp+2C0h+var_270], r14
0x1400587fc  mov     rcx, [rsp+2C0h+var_298]; string
0x140058801  call    cs:__imp_WindowsDeleteString
0x140058807  mov     [rsp+2C0h+var_298], r14
0x14005880c  mov     rcx, [rsp+2C0h+var_268]; string
0x140058811  call    cs:__imp_WindowsDeleteString
0x140058817  mov     [rsp+2C0h+var_268], r14
0x14005881c  lea     rcx, [rsp+2C0h+var_258]
0x140058821  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140058826  nop
0x140058827  lea     rcx, [rsp+2C0h+var_250]
0x14005882c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140058831  nop
0x140058832  lea     rcx, [rbp+1C0h+var_190]; this
0x140058836  call    ??1Enrollment@CorpDeviceManagementSettingsTelemetry@@QEAA@XZ; CorpDeviceManagementSettingsTelemetry::Enrollment::~Enrollment(void)
0x14005883b  mov     eax, ebx
0x14005883d  jmp     short loc_140058869
0x14005883f  mov     rax, [rbp+1C0h+var_238]
0x140058843  mov     dword ptr [rax], 3
0x140058849  lea     rcx, [rbp+1C0h+var_190]
0x14005884d  call    ?Stop@?$ActivityBase@VCorpDeviceManagementSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CorpDeviceManagementSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140058852  mov     ebx, [rsp+2C0h+var_260]
0x140058856  jmp     loc_1400587A1
0x14005885b  lea     rcx, [rbp+1C0h+var_190]; this
0x14005885f  call    ??1Enrollment@CorpDeviceManagementSettingsTelemetry@@QEAA@XZ; CorpDeviceManagementSettingsTelemetry::Enrollment::~Enrollment(void)
0x140058864  mov     eax, 80070057h
0x140058869  mov     rcx, [rbp+1C0h+var_40]
0x140058870  xor     rcx, rsp; StackCookie
0x140058873  call    __security_check_cookie
  ... truncated ...
```
