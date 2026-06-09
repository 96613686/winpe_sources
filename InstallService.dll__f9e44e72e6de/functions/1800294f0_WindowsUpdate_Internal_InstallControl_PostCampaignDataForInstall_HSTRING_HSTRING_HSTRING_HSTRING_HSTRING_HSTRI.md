# WindowsUpdate::Internal::InstallControl::PostCampaignDataForInstall(HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *)

- ea: `0x1800294f0`
- end: `0x1800298cf`
- name: `?PostCampaignDataForInstall@InstallControl@Internal@WindowsUpdate@@UEAAJPEAUHSTRING__@@000000@Z`
- size: `991`
- prototype: `__int64 __fastcall(WindowsUpdate::Internal::InstallControl *__hidden this, HSTRING, HSTRING, HSTRING, HSTRING, HSTRING, HSTRING, HSTRING)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18001fa6c`
- `0x18001ff68`
- `0x180020274`
- `0x180021ae8`
- `0x18002212c`
- `0x1800294f0`
- `0x18002c310`
- `0x18002e09c`
- `0x18002ec2c`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800297e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800297f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029803`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029813`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029823`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029833`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029843`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029852`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029864`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029874`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029884`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029894`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800298a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800298b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800297e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800297f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029803`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029813`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029823`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029833`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029843`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029852`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029864`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029874`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029884`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029894`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800298a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800298b4`

## string_xrefs

- `0x180029550`: `onecoreuap\enduser\winstore\installservice\lib\installcontrol.cpp`
- `0x180029583`: `onecoreuap\enduser\winstore\installservice\lib\installcontrol.cpp`
- `0x1800295b6`: `onecoreuap\enduser\winstore\installservice\lib\installcontrol.cpp`
- `0x1800295e9`: `onecoreuap\enduser\winstore\installservice\lib\installcontrol.cpp`
- `0x18002961c`: `onecoreuap\enduser\winstore\installservice\lib\installcontrol.cpp`
- `0x18002964f`: `onecoreuap\enduser\winstore\installservice\lib\installcontrol.cpp`
- `0x180029682`: `onecoreuap\enduser\winstore\installservice\lib\installcontrol.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall WindowsUpdate::Internal::InstallControl::PostCampaignDataForInstall(
        WindowsUpdate::Internal::InstallControl *this,
        HSTRING a2,
        HSTRING a3,
        HSTRING a4,
        HSTRING a5,
        HSTRING a6,
        HSTRING a7,
        HSTRING a8)
{
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  __int64 v16; // rax
  const char *v17; // r9
  __int64 result; // rax
  HSTRING string; // [rsp+20h] [rbp-F8h] BYREF
  HSTRING v20; // [rsp+28h] [rbp-F0h] BYREF
  HSTRING v21; // [rsp+30h] [rbp-E8h] BYREF
  HSTRING v22; // [rsp+38h] [rbp-E0h] BYREF
  HSTRING v23; // [rsp+40h] [rbp-D8h] BYREF
  HSTRING v24; // [rsp+48h] [rbp-D0h] BYREF
  WindowsUpdate::Internal::InstallControl *v25; // [rsp+50h] [rbp-C8h] BYREF
  HSTRING newString; // [rsp+58h] [rbp-C0h] BYREF
  __int64 v27; // [rsp+60h] [rbp-B8h] BYREF
  char v28; // [rsp+68h] [rbp-B0h]
  char v29; // [rsp+70h] [rbp-A8h]
  __int64 v30; // [rsp+78h] [rbp-A0h] BYREF
  char v31; // [rsp+80h] [rbp-98h]
  _BYTE v32[8]; // [rsp+88h] [rbp-90h] BYREF
  HSTRING v33; // [rsp+90h] [rbp-88h]
  HSTRING v34; // [rsp+98h] [rbp-80h]
  HSTRING v35; // [rsp+A0h] [rbp-78h]
  HSTRING v36; // [rsp+A8h] [rbp-70h]
  HSTRING v37; // [rsp+B0h] [rbp-68h]
  HSTRING v38; // [rsp+B8h] [rbp-60h]
  HSTRING v39; // [rsp+C0h] [rbp-58h]
  _BYTE v40[80]; // [rsp+C8h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]
  HSTRING v42; // [rsp+128h] [rbp+10h] BYREF
  HSTRING v43; // [rsp+130h] [rbp+18h] BYREF
  HSTRING v44; // [rsp+138h] [rbp+20h] BYREF

  v44 = a4;
  v43 = a3;
  v42 = a2;
  newString = 0;
  v24 = 0;
  v23 = 0;
  v22 = 0;
  v21 = 0;
  v20 = 0;
  string = 0;
  v9 = Microsoft::WRL::Wrappers::HString::Set(&newString, &v42);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x282,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installcontrol.cpp",
      (const char *)(unsigned int)v9,
      (int)string);
  v10 = Microsoft::WRL::Wrappers::HString::Set(&v24, &v43);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x283,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installcontrol.cpp",
      (const char *)(unsigned int)v10,
      (int)string);
  v11 = Microsoft::WRL::Wrappers::HString::Set(&v23, &v44);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x284,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installcontrol.cpp",
      (const char *)(unsigned int)v11,
      (int)string);
  v12 = Microsoft::WRL::Wrappers::HString::Set(&v22, &a5);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x285,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installcontrol.cpp",
      (const char *)(unsigned int)v12,
      (int)string);
  v13 = Microsoft::WRL::Wrappers::HString::Set(&v21, &a6);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x286,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installcontrol.cpp",
      (const char *)(unsigned int)v13,
      (int)string);
  v14 = Microsoft::WRL::Wrappers::HString::Set(&v20, &a7);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x287,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installcontrol.cpp",
      (const char *)(unsigned int)v14,
      (int)string);
  v15 = Microsoft::WRL::Wrappers::HString::Set(&string, &a8);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x288,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installcontrol.cpp",
      (const char *)(unsigned int)v15,
      (int)string);
  try
  {
    v25 = this;
    if ( this )
      (*(void (__fastcall **)(WindowsUpdate::Internal::InstallControl *))(*(_QWORD *)this + 8LL))(this);
    Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl>::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl>(
      v32,
      &v25);
    v33 = newString;
    newString = 0;
    v34 = v24;
    v24 = 0;
    v35 = v23;
    v23 = 0;
    v36 = v22;
    v22 = 0;
    v37 = v21;
    v21 = 0;
    v38 = v20;
    v20 = 0;
    v39 = string;
    string = 0;
    _lambda_d85f620be08a66f39adc08fd647ba759_::_lambda_d85f620be08a66f39adc08fd647ba759_(v40, v32);
    v27 = std::_Get_associated_state<void,std::_Fake_no_copy_callable_adapter<_lambda_d85f620be08a66f39adc08fd647ba759_>>(
            3,
            v40);
    v28 = 0;
    v29 = 0;
    _lambda_d85f620be08a66f39adc08fd647ba759_::~_lambda_d85f620be08a66f39adc08fd647ba759_((_lambda_d85f620be08a66f39adc08fd647ba759_ *)v40);
    v16 = *(_QWORD *)std::_Promise<int>::_Get_state_for_future(&v27);
    v30 = v16;
    v31 = 1;
    if ( v16 )
      _InterlockedIncrement((volatile signed __int32 *)(v16 + 8));
    std::_State_manager<int>::~_State_manager<int>(&v27);
    _lambda_d85f620be08a66f39adc08fd647ba759_::~_lambda_d85f620be08a66f39adc08fd647ba759_((_lambda_d85f620be08a66f39adc08fd647ba759_ *)v32);
    if ( v25 )
      (*(void (__fastcall **)(WindowsUpdate::Internal::InstallControl *))(*(_QWORD *)v25 + 16LL))(v25);
    std::_State_manager<int>::~_State_manager<int>(&v30);
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v20);
    v20 = 0;
    WindowsDeleteString(v21);
    v21 = 0;
    WindowsDeleteString(v22);
    v22 = 0;
    WindowsDeleteString(v23);
    v23 = 0;
    WindowsDeleteString(v24);
    v24 = 0;
    WindowsDeleteString(newString);
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(v25) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x29B,
                     (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installcontrol.cpp",
                     v17);
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v20);
    v20 = 0;
    WindowsDeleteString(v21);
    v21 = 0;
    WindowsDeleteString(v22);
    v22 = 0;
    WindowsDeleteString(v23);
    v23 = 0;
    WindowsDeleteString(v24);
    v24 = 0;
    WindowsDeleteString(newString);
    return (unsigned int)v25;
  }
  return result;
}

```

## disassembly

```asm
0x1800294f0  mov     rax, rsp
0x1800294f3  mov     [rax+8], rbx
0x1800294f7  mov     [rax+20h], r9
0x1800294fb  mov     [rax+18h], r8
0x1800294ff  mov     [rax+10h], rdx
0x180029503  push    rdi
0x180029504  sub     rsp, 110h
0x18002950b  mov     rdi, rcx
0x18002950e  xor     ebx, ebx
0x180029510  mov     [rsp+118h+newString], rbx
0x180029515  mov     [rsp+118h+var_D0], rbx
0x18002951a  mov     [rsp+118h+var_D8], rbx
0x18002951f  mov     [rsp+118h+var_E0], rbx
0x180029524  mov     [rsp+118h+var_E8], rbx
0x180029529  mov     [rsp+118h+var_F0], rbx
0x18002952e  mov     [rsp+118h+string], rbx; int
0x180029533  lea     rdx, [rax+10h]; HSTRING *
0x180029537  lea     rcx, [rsp+118h+newString]; newString
0x18002953c  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180029541  mov     rcx, [rsp+118h]; this
0x180029549  test    eax, eax
0x18002954b  jns     short loc_180029562
0x18002954d  mov     r9d, eax; char *
0x180029550  lea     r8, aOnecoreuapEndu_49; "onecoreuap\\enduser\\winstore\\installs"...
0x180029557  mov     edx, 282h; void *
0x18002955c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180029562  lea     rdx, [rsp+118h+arg_10]; HSTRING *
0x18002956a  lea     rcx, [rsp+118h+var_D0]; newString
0x18002956f  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180029574  mov     rcx, [rsp+118h]; this
0x18002957c  test    eax, eax
0x18002957e  jns     short loc_180029595
0x180029580  mov     r9d, eax; char *
0x180029583  lea     r8, aOnecoreuapEndu_49; "onecoreuap\\enduser\\winstore\\installs"...
0x18002958a  mov     edx, 283h; void *
0x18002958f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180029595  lea     rdx, [rsp+118h+arg_18]; HSTRING *
0x18002959d  lea     rcx, [rsp+118h+var_D8]; newString
0x1800295a2  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1800295a7  mov     rcx, [rsp+118h]; this
0x1800295af  test    eax, eax
0x1800295b1  jns     short loc_1800295C8
0x1800295b3  mov     r9d, eax; char *
0x1800295b6  lea     r8, aOnecoreuapEndu_49; "onecoreuap\\enduser\\winstore\\installs"...
0x1800295bd  mov     edx, 284h; void *
0x1800295c2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800295c8  lea     rdx, [rsp+118h+arg_20]; HSTRING *
0x1800295d0  lea     rcx, [rsp+118h+var_E0]; newString
0x1800295d5  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1800295da  mov     rcx, [rsp+118h]; this
0x1800295e2  test    eax, eax
0x1800295e4  jns     short loc_1800295FB
0x1800295e6  mov     r9d, eax; char *
0x1800295e9  lea     r8, aOnecoreuapEndu_49; "onecoreuap\\enduser\\winstore\\installs"...
0x1800295f0  mov     edx, 285h; void *
0x1800295f5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800295fb  lea     rdx, [rsp+118h+arg_28]; HSTRING *
0x180029603  lea     rcx, [rsp+118h+var_E8]; newString
0x180029608  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18002960d  mov     rcx, [rsp+118h]; this
0x180029615  test    eax, eax
0x180029617  jns     short loc_18002962E
0x180029619  mov     r9d, eax; char *
0x18002961c  lea     r8, aOnecoreuapEndu_49; "onecoreuap\\enduser\\winstore\\installs"...
0x180029623  mov     edx, 286h; void *
0x180029628  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002962e  lea     rdx, [rsp+118h+arg_30]; HSTRING *
0x180029636  lea     rcx, [rsp+118h+var_F0]; newString
0x18002963b  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180029640  mov     rcx, [rsp+118h]; this
0x180029648  test    eax, eax
0x18002964a  jns     short loc_180029661
0x18002964c  mov     r9d, eax; char *
0x18002964f  lea     r8, aOnecoreuapEndu_49; "onecoreuap\\enduser\\winstore\\installs"...
0x180029656  mov     edx, 287h; void *
0x18002965b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180029661  lea     rdx, [rsp+118h+arg_38]; HSTRING *
0x180029669  lea     rcx, [rsp+118h+string]; newString
0x18002966e  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180029673  mov     rcx, [rsp+118h]; this
0x18002967b  test    eax, eax
0x18002967d  jns     short loc_180029694
0x18002967f  mov     r9d, eax; char *
0x180029682  lea     r8, aOnecoreuapEndu_49; "onecoreuap\\enduser\\winstore\\installs"...
0x180029689  mov     edx, 288h; void *
0x18002968e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180029694  mov     [rsp+118h+var_C8], rdi
0x180029699  test    rdi, rdi
0x18002969c  jz      short loc_1800296AE
0x18002969e  mov     rax, [rdi]
0x1800296a1  mov     rcx, rdi
0x1800296a4  mov     rax, [rax+8]
0x1800296a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800296ad  nop
0x1800296ae  lea     rdx, [rsp+118h+var_C8]
0x1800296b3  lea     rcx, [rsp+118h+var_90]
0x1800296bb  call    ??0?$ComPtr@VAppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@QEAA@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl>::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl>(Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl> &&)
0x1800296c0  mov     rcx, [rsp+118h+newString]
0x1800296c5  mov     [rsp+118h+var_88], rcx
0x1800296cd  mov     [rsp+118h+newString], rbx
0x1800296d2  mov     rax, [rsp+118h+var_D0]
0x1800296d7  mov     [rsp+118h+var_80], rax
0x1800296df  mov     [rsp+118h+var_D0], rbx
0x1800296e4  mov     rax, [rsp+118h+var_D8]
0x1800296e9  mov     [rsp+118h+var_78], rax
0x1800296f1  mov     [rsp+118h+var_D8], rbx
0x1800296f6  mov     rax, [rsp+118h+var_E0]
0x1800296fb  mov     [rsp+118h+var_70], rax
0x180029703  mov     [rsp+118h+var_E0], rbx
0x180029708  mov     rax, [rsp+118h+var_E8]
0x18002970d  mov     [rsp+118h+var_68], rax
0x180029715  mov     [rsp+118h+var_E8], rbx
0x18002971a  mov     rax, [rsp+118h+var_F0]
0x18002971f  mov     [rsp+118h+var_60], rax
0x180029727  mov     [rsp+118h+var_F0], rbx
0x18002972c  mov     rax, [rsp+118h+string]
0x180029731  mov     [rsp+118h+var_58], rax
0x180029739  mov     [rsp+118h+string], rbx
0x18002973e  lea     rdx, [rsp+118h+var_90]
0x180029746  lea     rcx, [rsp+118h+var_50]
0x18002974e  call    ??0_lambda_d85f620be08a66f39adc08fd647ba759_@@QEAA@$$QEAV0@@Z; _lambda_d85f620be08a66f39adc08fd647ba759_::_lambda_d85f620be08a66f39adc08fd647ba759_(_lambda_d85f620be08a66f39adc08fd647ba759_ &&)
0x180029753  nop
0x180029754  lea     rdx, [rsp+118h+var_50]
0x18002975c  mov     ecx, 3
0x180029761  call    ??$_Get_associated_state@XV?$_Fake_no_copy_callable_adapter@V_lambda_d85f620be08a66f39adc08fd647ba759_@@@std@@@std@@YAPEAV?$_Associated_state@H@0@W4launch@0@$$QEAV?$_Fake_no_copy_callable_adapter@V_lambda_d85f620be08a66f39adc08fd647ba759_@@@0@@Z; std::_Get_associated_state<void,std::_Fake_no_copy_callable_adapter<_lambda_d85f620be08a66f39adc08fd647ba759_>>(std::launch,std::_Fake_no_copy_callable_adapter<_lambda_d85f620be08a66f39adc08fd647ba759_> &&)
0x180029766  mov     [rsp+118h+var_B8], rax
0x18002976b  mov     [rsp+118h+var_B0], bl
0x18002976f  mov     [rsp+118h+var_A8], bl
0x180029773  lea     rcx, [rsp+118h+var_50]; this
0x18002977b  call    ??1_lambda_d85f620be08a66f39adc08fd647ba759_@@QEAA@XZ; _lambda_d85f620be08a66f39adc08fd647ba759_::~_lambda_d85f620be08a66f39adc08fd647ba759_(void)
0x180029780  lea     rcx, [rsp+118h+var_B8]
0x180029785  call    ?_Get_state_for_future@?$_Promise@H@std@@QEAAAEAV?$_State_manager@H@2@XZ; std::_Promise<int>::_Get_state_for_future(void)
0x18002978a  mov     rax, [rax]
0x18002978d  mov     [rsp+118h+var_A0], rax
0x180029792  mov     [rsp+118h+var_98], 1
0x18002979a  test    rax, rax
0x18002979d  jz      short loc_1800297A3
0x18002979f  lock inc dword ptr [rax+8]
0x1800297a3  lea     rcx, [rsp+118h+var_B8]
0x1800297a8  call    ??1?$_State_manager@H@std@@QEAA@XZ; std::_State_manager<int>::~_State_manager<int>(void)
0x1800297ad  nop
0x1800297ae  lea     rcx, [rsp+118h+var_90]; this
0x1800297b6  call    ??1_lambda_d85f620be08a66f39adc08fd647ba759_@@QEAA@XZ; _lambda_d85f620be08a66f39adc08fd647ba759_::~_lambda_d85f620be08a66f39adc08fd647ba759_(void)
0x1800297bb  nop
0x1800297bc  mov     rcx, [rsp+118h+var_C8]
0x1800297c1  test    rcx, rcx
0x1800297c4  jz      short loc_1800297D3
0x1800297c6  mov     rax, [rcx]
0x1800297c9  mov     rax, [rax+10h]
0x1800297cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800297d2  nop
0x1800297d3  lea     rcx, [rsp+118h+var_A0]
0x1800297d8  call    ??1?$_State_manager@H@std@@QEAA@XZ; std::_State_manager<int>::~_State_manager<int>(void)
0x1800297dd  nop
0x1800297de  mov     rcx, [rsp+118h+string]; string
0x1800297e3  call    cs:__imp_WindowsDeleteString
0x1800297e9  mov     [rsp+118h+string], rbx
0x1800297ee  mov     rcx, [rsp+118h+var_F0]; string
0x1800297f3  call    cs:__imp_WindowsDeleteString
0x1800297f9  mov     [rsp+118h+var_F0], rbx
0x1800297fe  mov     rcx, [rsp+118h+var_E8]; string
0x180029803  call    cs:__imp_WindowsDeleteString
0x180029809  mov     [rsp+118h+var_E8], rbx
0x18002980e  mov     rcx, [rsp+118h+var_E0]; string
0x180029813  call    cs:__imp_WindowsDeleteString
0x180029819  mov     [rsp+118h+var_E0], rbx
0x18002981e  mov     rcx, [rsp+118h+var_D8]; string
0x180029823  call    cs:__imp_WindowsDeleteString
0x180029829  mov     [rsp+118h+var_D8], rbx
0x18002982e  mov     rcx, [rsp+118h+var_D0]; string
0x180029833  call    cs:__imp_WindowsDeleteString
0x180029839  mov     [rsp+118h+var_D0], rbx
0x18002983e  mov     rcx, [rsp+118h+newString]; string
0x180029843  call    cs:__imp_WindowsDeleteString
0x180029849  xor     eax, eax
0x18002984b  jmp     short loc_1800298BE
0x18002984d  mov     rcx, [rsp+118h+string]; string
0x180029852  call    cs:__imp_WindowsDeleteString
0x180029858  xor     ebx, ebx
0x18002985a  mov     [rsp+118h+string], rbx
0x18002985f  mov     rcx, [rsp+118h+var_F0]; string
0x180029864  call    cs:__imp_WindowsDeleteString
0x18002986a  mov     [rsp+118h+var_F0], rbx
0x18002986f  mov     rcx, [rsp+118h+var_E8]; string
0x180029874  call    cs:__imp_WindowsDeleteString
0x18002987a  mov     [rsp+118h+var_E8], rbx
0x18002987f  mov     rcx, [rsp+118h+var_E0]; string
0x180029884  call    cs:__imp_WindowsDeleteString
0x18002988a  mov     [rsp+118h+var_E0], rbx
0x18002988f  mov     rcx, [rsp+118h+var_D8]; string
0x180029894  call    cs:__imp_WindowsDeleteString
0x18002989a  mov     [rsp+118h+var_D8], rbx
0x18002989f  mov     rcx, [rsp+118h+var_D0]; string
0x1800298a4  call    cs:__imp_WindowsDeleteString
0x1800298aa  mov     [rsp+118h+var_D0], rbx
0x1800298af  mov     rcx, [rsp+118h+newString]; string
0x1800298b4  call    cs:__imp_WindowsDeleteString
0x1800298ba  mov     eax, dword ptr [rsp+118h+var_C8]
0x1800298be  mov     rbx, [rsp+118h+arg_0]
0x1800298c6  add     rsp, 110h
0x1800298cd  pop     rdi
0x1800298ce  retn
```
