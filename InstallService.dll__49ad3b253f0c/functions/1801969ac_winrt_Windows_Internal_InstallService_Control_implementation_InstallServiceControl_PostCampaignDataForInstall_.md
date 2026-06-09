# winrt::Windows::Internal::InstallService::Control::implementation::InstallServiceControl::PostCampaignDataForInstall(winrt::hstring const &,winrt::hstring const &,winrt::hstring const &,winrt::hstring const &,winrt::hstring const &,winrt::hstring const &,winrt::hstring const &)

- ea: `0x1801969ac`
- end: `0x180196e70`
- name: `?PostCampaignDataForInstall@InstallServiceControl@implementation@Control@InstallService@Internal@Windows@winrt@@QEAAXAEBUhstring@7@000000@Z`
- size: `1220`
- prototype: `void(winrt::Windows::Internal::InstallService::Control::implementation::InstallServiceControl *__hidden this, const struct winrt::hstring *, const struct winrt::hstring *, const struct winrt::hstring *, const struct winrt::hstring *, const struct winrt::hstring *, const struct winrt::hstring *, const struct winrt::hstring *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18013ae90`

## callees

- `0x180031d3c`
- `0x1800453a0`
- `0x1800453bc`
- `0x180083240`
- `0x18012e730`
- `0x18013bd68`
- `0x180193b0c`
- `0x180194ff4`
- `0x1801953c0`
- `0x1801969ac`
- `0x18019808c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180196b40`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180196b53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180196b63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180196b73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180196b83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180196b93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180196dfa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180196e0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180196e1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180196e2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180196e3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180196e4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180196e5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180196b40`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180196b53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180196b63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180196b73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180196b83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180196b93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180196dfa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180196e0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180196e1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180196e2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180196e3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180196e4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180196e5d`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
void __fastcall winrt::Windows::Internal::InstallService::Control::implementation::InstallServiceControl::PostCampaignDataForInstall(
        winrt::Windows::Internal::InstallService::Control::implementation::InstallServiceControl *this,
        const struct winrt::hstring *a2,
        const struct winrt::hstring *a3,
        const struct winrt::hstring *a4,
        const struct winrt::hstring *a5,
        const struct winrt::hstring *a6,
        const struct winrt::hstring *a7,
        const struct winrt::hstring *a8)
{
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  std::thread *v18; // rcx
  const char *v19; // r9
  HSTRING v20; // rcx
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  HSTRING v28; // [rsp+40h] [rbp-B8h] BYREF
  HSTRING v29; // [rsp+48h] [rbp-B0h] BYREF
  HSTRING v30; // [rsp+50h] [rbp-A8h] BYREF
  HSTRING v31; // [rsp+58h] [rbp-A0h] BYREF
  HSTRING v32; // [rsp+60h] [rbp-98h] BYREF
  HSTRING v33; // [rsp+68h] [rbp-90h] BYREF
  int v34; // [rsp+70h] [rbp-88h] BYREF
  __int128 v35; // [rsp+78h] [rbp-80h]
  HSTRING v36[2]; // [rsp+88h] [rbp-70h] BYREF
  _QWORD v37[12]; // [rsp+98h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]
  HSTRING string; // [rsp+100h] [rbp+8h] BYREF

  string = (HSTRING)this;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PostCampaignDataAsync>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PostCampaignDataAsync>::GetImpl'::`2'::impl) )
  {
    v33 = 0;
    v32 = 0;
    v31 = 0;
    v30 = 0;
    v29 = 0;
    v28 = 0;
    string = 0;
    lambda_3bd83dbb61532010bb51b9280b0db596_::operator()(v11, &v33, a2);
    lambda_3bd83dbb61532010bb51b9280b0db596_::operator()(v12, &v32, a3);
    lambda_3bd83dbb61532010bb51b9280b0db596_::operator()(v13, &v31, a4);
    lambda_3bd83dbb61532010bb51b9280b0db596_::operator()(v14, &v30, a5);
    lambda_3bd83dbb61532010bb51b9280b0db596_::operator()(v15, &v29, a6);
    lambda_3bd83dbb61532010bb51b9280b0db596_::operator()(v16, &v28, a7);
    lambda_3bd83dbb61532010bb51b9280b0db596_::operator()(v17, &string, a8);
    try
    {
      v37[0] = v33;
      v33 = 0;
      v37[1] = v32;
      v32 = 0;
      v37[2] = v31;
      v31 = 0;
      v37[3] = v30;
      v30 = 0;
      v37[4] = v29;
      v29 = 0;
      v37[5] = v28;
      v28 = 0;
      v37[6] = string;
      string = 0;
      v18 = (std::thread *)std::thread::thread__lambda_c688dce83f8d69990b2f440a6a213ee3__0_(v36, v37);
      std::thread::detach(v18);
      std::thread::~thread((std::thread *)v36);
      lambda_c688dce83f8d69990b2f440a6a213ee3_::__lambda_c688dce83f8d69990b2f440a6a213ee3_(v37);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x113,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\windows.internal.installservice.control."
                      "installservicecontrol.cpp",
        v19);
    }
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v28);
    v28 = 0;
    WindowsDeleteString(v29);
    v29 = 0;
    WindowsDeleteString(v30);
    v30 = 0;
    WindowsDeleteString(v31);
    v31 = 0;
    WindowsDeleteString(v32);
    v32 = 0;
    v20 = v33;
  }
  else
  {
    v36[0] = 0;
    v28 = 0;
    v29 = 0;
    v30 = 0;
    v31 = 0;
    v32 = 0;
    v33 = 0;
    v34 = 0;
    v35 = 0;
    string = (HSTRING)winrt::hstring::c_str(a2);
    v21 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(v36, &string);
    winrt::check_hresult(&string, v21, &v34);
    v34 = 0;
    v35 = 0;
    string = (HSTRING)winrt::hstring::c_str(a3);
    v22 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(&v28, &string);
    winrt::check_hresult(&string, v22, &v34);
    v34 = 0;
    v35 = 0;
    string = (HSTRING)winrt::hstring::c_str(a4);
    v23 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(&v29, &string);
    winrt::check_hresult(&string, v23, &v34);
    v34 = 0;
    v35 = 0;
    string = (HSTRING)winrt::hstring::c_str(a5);
    v24 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(&v30, &string);
    winrt::check_hresult(&string, v24, &v34);
    v34 = 0;
    v35 = 0;
    string = (HSTRING)winrt::hstring::c_str(a6);
    v25 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(&v31, &string);
    winrt::check_hresult(&string, v25, &v34);
    v34 = 0;
    v35 = 0;
    string = (HSTRING)winrt::hstring::c_str(a7);
    v26 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(&v32, &string);
    winrt::check_hresult(&string, v26, &v34);
    v34 = 0;
    v35 = 0;
    string = (HSTRING)winrt::hstring::c_str(a8);
    v27 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(&v33, &string);
    winrt::check_hresult(&string, v27, &v34);
    PostCampaignData(
      (const struct Microsoft::WRL::Wrappers::HString *)v36,
      (const struct Microsoft::WRL::Wrappers::HString *)&v28,
      (const struct Microsoft::WRL::Wrappers::HString *)&v29,
      (const struct Microsoft::WRL::Wrappers::HString *)&v30,
      (const struct Microsoft::WRL::Wrappers::HString *)&v31,
      (const struct Microsoft::WRL::Wrappers::HString *)&v32,
      (const struct Microsoft::WRL::Wrappers::HString *)&v33);
    WindowsDeleteString(v33);
    v33 = 0;
    WindowsDeleteString(v32);
    v32 = 0;
    WindowsDeleteString(v31);
    v31 = 0;
    WindowsDeleteString(v30);
    v30 = 0;
    WindowsDeleteString(v29);
    v29 = 0;
    WindowsDeleteString(v28);
    v28 = 0;
    v20 = v36[0];
  }
  WindowsDeleteString(v20);
}

```

## disassembly

```asm
0x1801969ac  mov     [rsp+string], rcx
0x1801969b1  push    rbx
0x1801969b2  push    rsi
0x1801969b3  push    rdi
0x1801969b4  push    r14
0x1801969b6  sub     rsp, 0D8h
0x1801969bd  mov     rdi, r9
0x1801969c0  mov     rsi, r8
0x1801969c3  mov     r14, rdx
0x1801969c6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PostCampaignDataAsync@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PostCampaignDataAsync@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PostCampaignDataAsync> `wil::Feature<__WilFeatureTraits_Feature_PostCampaignDataAsync>::GetImpl(void)'::`2'::impl
0x1801969cd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PostCampaignDataAsync@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PostCampaignDataAsync>::__private_IsEnabled(void)
0x1801969d2  xor     ebx, ebx
0x1801969d4  test    al, al
0x1801969d6  jz      loc_180196BA8
0x1801969dc  mov     [rsp+0F8h+var_90], rbx
0x1801969e1  mov     [rsp+0F8h+var_98], rbx
0x1801969e6  mov     [rsp+0F8h+var_A0], rbx
0x1801969eb  mov     [rsp+0F8h+var_A8], rbx
0x1801969f0  mov     [rsp+0F8h+var_B0], rbx
0x1801969f5  mov     [rsp+0F8h+var_B8], rbx
0x1801969fa  mov     [rsp+0F8h+string], rbx
0x180196a02  mov     r8, r14
0x180196a05  lea     rdx, [rsp+0F8h+var_90]
0x180196a0a  call    _lambda_3bd83dbb61532010bb51b9280b0db596___operator__
0x180196a0f  mov     r8, rsi
0x180196a12  lea     rdx, [rsp+0F8h+var_98]
0x180196a17  call    _lambda_3bd83dbb61532010bb51b9280b0db596___operator__
0x180196a1c  mov     r8, rdi
0x180196a1f  lea     rdx, [rsp+0F8h+var_A0]
0x180196a24  call    _lambda_3bd83dbb61532010bb51b9280b0db596___operator__
0x180196a29  mov     r8, [rsp+0F8h+arg_20]
0x180196a31  lea     rdx, [rsp+0F8h+var_A8]
0x180196a36  call    _lambda_3bd83dbb61532010bb51b9280b0db596___operator__
0x180196a3b  mov     r8, [rsp+0F8h+arg_28]
0x180196a43  lea     rdx, [rsp+0F8h+var_B0]
0x180196a48  call    _lambda_3bd83dbb61532010bb51b9280b0db596___operator__
0x180196a4d  mov     r8, [rsp+0F8h+arg_30]
0x180196a55  lea     rdx, [rsp+0F8h+var_B8]
0x180196a5a  call    _lambda_3bd83dbb61532010bb51b9280b0db596___operator__
0x180196a5f  mov     r8, [rsp+0F8h+arg_38]
0x180196a67  lea     rdx, [rsp+0F8h+string]
0x180196a6f  call    _lambda_3bd83dbb61532010bb51b9280b0db596___operator__
0x180196a74  nop
0x180196a75  mov     rax, [rsp+0F8h+var_90]
0x180196a7a  mov     [rsp+0F8h+var_60], rax
0x180196a82  mov     [rsp+0F8h+var_90], rbx
0x180196a87  mov     rax, [rsp+0F8h+var_98]
0x180196a8c  mov     [rsp+0F8h+var_58], rax
0x180196a94  mov     [rsp+0F8h+var_98], rbx
0x180196a99  mov     rax, [rsp+0F8h+var_A0]
0x180196a9e  mov     [rsp+0F8h+var_50], rax
0x180196aa6  mov     [rsp+0F8h+var_A0], rbx
0x180196aab  mov     rax, [rsp+0F8h+var_A8]
0x180196ab0  mov     [rsp+0F8h+var_48], rax
0x180196ab8  mov     [rsp+0F8h+var_A8], rbx
0x180196abd  mov     rax, [rsp+0F8h+var_B0]
0x180196ac2  mov     [rsp+0F8h+var_40], rax
0x180196aca  mov     [rsp+0F8h+var_B0], rbx
0x180196acf  mov     rax, [rsp+0F8h+var_B8]
0x180196ad4  mov     [rsp+0F8h+var_38], rax
0x180196adc  mov     [rsp+0F8h+var_B8], rbx
0x180196ae1  mov     rax, [rsp+0F8h+string]
0x180196ae9  mov     [rsp+0F8h+var_30], rax
0x180196af1  mov     [rsp+0F8h+string], rbx
0x180196af9  lea     rdx, [rsp+0F8h+var_60]
0x180196b01  lea     rcx, [rsp+0F8h+var_70]
0x180196b09  call    std__thread__thread__lambda_c688dce83f8d69990b2f440a6a213ee3__0_
0x180196b0e  nop
0x180196b0f  mov     rcx, rax; this
0x180196b12  call    ?detach@thread@std@@QEAAXXZ; std::thread::detach(void)
0x180196b17  nop
0x180196b18  lea     rcx, [rsp+0F8h+var_70]; this
0x180196b20  call    ??1thread@std@@QEAA@XZ; std::thread::~thread(void)
0x180196b25  nop
0x180196b26  lea     rcx, [rsp+0F8h+var_60]
0x180196b2e  call    _lambda_c688dce83f8d69990b2f440a6a213ee3_____lambda_c688dce83f8d69990b2f440a6a213ee3_
0x180196b33  nop
0x180196b34  jmp     short loc_180196B38
0x180196b36  xor     ebx, ebx
0x180196b38  mov     rcx, [rsp+0F8h+string]; string
0x180196b40  call    cs:__imp_WindowsDeleteString
0x180196b46  mov     [rsp+0F8h+string], rbx
0x180196b4e  mov     rcx, [rsp+0F8h+var_B8]; string
0x180196b53  call    cs:__imp_WindowsDeleteString
0x180196b59  mov     [rsp+0F8h+var_B8], rbx
0x180196b5e  mov     rcx, [rsp+0F8h+var_B0]; string
0x180196b63  call    cs:__imp_WindowsDeleteString
0x180196b69  mov     [rsp+0F8h+var_B0], rbx
0x180196b6e  mov     rcx, [rsp+0F8h+var_A8]; string
0x180196b73  call    cs:__imp_WindowsDeleteString
0x180196b79  mov     [rsp+0F8h+var_A8], rbx
0x180196b7e  mov     rcx, [rsp+0F8h+var_A0]; string
0x180196b83  call    cs:__imp_WindowsDeleteString
0x180196b89  mov     [rsp+0F8h+var_A0], rbx
0x180196b8e  mov     rcx, [rsp+0F8h+var_98]; string
0x180196b93  call    cs:__imp_WindowsDeleteString
0x180196b99  mov     [rsp+0F8h+var_98], rbx
0x180196b9e  mov     rcx, [rsp+0F8h+var_90]
0x180196ba3  jmp     loc_180196E5D
0x180196ba8  mov     [rsp+0F8h+var_70], rbx
0x180196bb0  mov     [rsp+0F8h+var_B8], rbx
0x180196bb5  mov     [rsp+0F8h+var_B0], rbx
0x180196bba  mov     [rsp+0F8h+var_A8], rbx
0x180196bbf  mov     [rsp+0F8h+var_A0], rbx
0x180196bc4  mov     [rsp+0F8h+var_98], rbx
0x180196bc9  mov     [rsp+0F8h+var_90], rbx
0x180196bce  mov     [rsp+0F8h+var_88], ebx
0x180196bd2  xorps   xmm0, xmm0
0x180196bd5  movdqu  [rsp+0F8h+var_80], xmm0
0x180196bdb  mov     rcx, r14; this
0x180196bde  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180196be3  mov     [rsp+0F8h+string], rax
0x180196beb  lea     rdx, [rsp+0F8h+string]
0x180196bf3  lea     rcx, [rsp+0F8h+var_70]
0x180196bfb  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x180196c00  lea     r8, [rsp+0F8h+var_88]
0x180196c05  mov     edx, eax
0x180196c07  lea     rcx, [rsp+0F8h+string]
0x180196c0f  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180196c14  mov     [rsp+0F8h+var_88], ebx
0x180196c18  xorps   xmm0, xmm0
0x180196c1b  movdqu  [rsp+0F8h+var_80], xmm0
0x180196c21  mov     rcx, rsi; this
0x180196c24  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180196c29  mov     [rsp+0F8h+string], rax
0x180196c31  lea     rdx, [rsp+0F8h+string]
0x180196c39  lea     rcx, [rsp+0F8h+var_B8]
0x180196c3e  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x180196c43  lea     r8, [rsp+0F8h+var_88]
0x180196c48  mov     edx, eax
0x180196c4a  lea     rcx, [rsp+0F8h+string]
0x180196c52  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180196c57  mov     [rsp+0F8h+var_88], ebx
0x180196c5b  xorps   xmm0, xmm0
0x180196c5e  movdqu  [rsp+0F8h+var_80], xmm0
0x180196c64  mov     rcx, rdi; this
0x180196c67  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180196c6c  mov     [rsp+0F8h+string], rax
0x180196c74  lea     rdx, [rsp+0F8h+string]
0x180196c7c  lea     rcx, [rsp+0F8h+var_B0]
0x180196c81  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x180196c86  lea     r8, [rsp+0F8h+var_88]
0x180196c8b  mov     edx, eax
0x180196c8d  lea     rcx, [rsp+0F8h+string]
0x180196c95  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180196c9a  mov     [rsp+0F8h+var_88], ebx
0x180196c9e  xorps   xmm0, xmm0
0x180196ca1  movdqu  [rsp+0F8h+var_80], xmm0
0x180196ca7  mov     rcx, [rsp+0F8h+arg_20]; this
0x180196caf  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180196cb4  mov     [rsp+0F8h+string], rax
0x180196cbc  lea     rdx, [rsp+0F8h+string]
0x180196cc4  lea     rcx, [rsp+0F8h+var_A8]
0x180196cc9  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x180196cce  lea     r8, [rsp+0F8h+var_88]
0x180196cd3  mov     edx, eax
0x180196cd5  lea     rcx, [rsp+0F8h+string]
0x180196cdd  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180196ce2  mov     [rsp+0F8h+var_88], ebx
0x180196ce6  xorps   xmm0, xmm0
0x180196ce9  movdqu  [rsp+0F8h+var_80], xmm0
0x180196cef  mov     rcx, [rsp+0F8h+arg_28]; this
0x180196cf7  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180196cfc  mov     [rsp+0F8h+string], rax
0x180196d04  lea     rdx, [rsp+0F8h+string]
0x180196d0c  lea     rcx, [rsp+0F8h+var_A0]
0x180196d11  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x180196d16  lea     r8, [rsp+0F8h+var_88]
0x180196d1b  mov     edx, eax
0x180196d1d  lea     rcx, [rsp+0F8h+string]
0x180196d25  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180196d2a  mov     [rsp+0F8h+var_88], ebx
0x180196d2e  xorps   xmm0, xmm0
0x180196d31  movdqu  [rsp+0F8h+var_80], xmm0
0x180196d37  mov     rcx, [rsp+0F8h+arg_30]; this
0x180196d3f  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180196d44  mov     [rsp+0F8h+string], rax
0x180196d4c  lea     rdx, [rsp+0F8h+string]
0x180196d54  lea     rcx, [rsp+0F8h+var_98]
0x180196d59  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x180196d5e  lea     r8, [rsp+0F8h+var_88]
0x180196d63  mov     edx, eax
0x180196d65  lea     rcx, [rsp+0F8h+string]
0x180196d6d  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180196d72  mov     [rsp+0F8h+var_88], ebx
0x180196d76  xorps   xmm0, xmm0
0x180196d79  movdqu  [rsp+0F8h+var_80], xmm0
0x180196d7f  mov     rcx, [rsp+0F8h+arg_38]; this
0x180196d87  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180196d8c  mov     [rsp+0F8h+string], rax
0x180196d94  lea     rdx, [rsp+0F8h+string]
0x180196d9c  lea     rcx, [rsp+0F8h+var_90]
0x180196da1  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x180196da6  lea     r8, [rsp+0F8h+var_88]
0x180196dab  mov     edx, eax
0x180196dad  lea     rcx, [rsp+0F8h+string]
0x180196db5  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180196dba  lea     rax, [rsp+0F8h+var_90]
0x180196dbf  mov     [rsp+0F8h+var_C8], rax; struct Microsoft::WRL::Wrappers::HString *
0x180196dc4  lea     rax, [rsp+0F8h+var_98]
0x180196dc9  mov     [rsp+0F8h+var_D0], rax; struct Microsoft::WRL::Wrappers::HString *
0x180196dce  lea     rax, [rsp+0F8h+var_A0]
0x180196dd3  mov     [rsp+0F8h+var_D8], rax; struct Microsoft::WRL::Wrappers::HString *
0x180196dd8  lea     r9, [rsp+0F8h+var_A8]; struct Microsoft::WRL::Wrappers::HString *
0x180196ddd  lea     r8, [rsp+0F8h+var_B0]; struct Microsoft::WRL::Wrappers::HString *
0x180196de2  lea     rdx, [rsp+0F8h+var_B8]; struct Microsoft::WRL::Wrappers::HString *
0x180196de7  lea     rcx, [rsp+0F8h+var_70]; struct Microsoft::WRL::Wrappers::HString *
0x180196def  call    ?PostCampaignData@@YAJAEBVHString@Wrappers@WRL@Microsoft@@000000@Z; PostCampaignData(Microsoft::WRL::Wrappers::HString const &,Microsoft::WRL::Wrappers::HString const &,Microsoft::WRL::Wrappers::HString const &,Microsoft::WRL::Wrappers::HString const &,Microsoft::WRL::Wrappers::HString const &,Microsoft::WRL::Wrappers::HString const &,Microsoft::WRL::Wrappers::HString const &)
0x180196df4  nop
0x180196df5  mov     rcx, [rsp+0F8h+var_90]; string
0x180196dfa  call    cs:__imp_WindowsDeleteString
0x180196e00  mov     [rsp+0F8h+var_90], rbx
0x180196e05  mov     rcx, [rsp+0F8h+var_98]; string
0x180196e0a  call    cs:__imp_WindowsDeleteString
0x180196e10  mov     [rsp+0F8h+var_98], rbx
0x180196e15  mov     rcx, [rsp+0F8h+var_A0]; string
0x180196e1a  call    cs:__imp_WindowsDeleteString
0x180196e20  mov     [rsp+0F8h+var_A0], rbx
0x180196e25  mov     rcx, [rsp+0F8h+var_A8]; string
0x180196e2a  call    cs:__imp_WindowsDeleteString
0x180196e30  mov     [rsp+0F8h+var_A8], rbx
0x180196e35  mov     rcx, [rsp+0F8h+var_B0]; string
0x180196e3a  call    cs:__imp_WindowsDeleteString
0x180196e40  mov     [rsp+0F8h+var_B0], rbx
0x180196e45  mov     rcx, [rsp+0F8h+var_B8]; string
0x180196e4a  call    cs:__imp_WindowsDeleteString
0x180196e50  mov     [rsp+0F8h+var_B8], rbx
0x180196e55  mov     rcx, [rsp+0F8h+var_70]; string
0x180196e5d  call    cs:__imp_WindowsDeleteString
0x180196e63  add     rsp, 0D8h
0x180196e6a  pop     r14
0x180196e6c  pop     rdi
0x180196e6d  pop     rsi
0x180196e6e  pop     rbx
0x180196e6f  retn
```
