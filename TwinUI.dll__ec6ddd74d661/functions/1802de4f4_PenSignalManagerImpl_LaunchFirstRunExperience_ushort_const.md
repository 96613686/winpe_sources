# PenSignalManagerImpl::LaunchFirstRunExperience(ushort const *)

- ea: `0x1802de4f4`
- end: `0x1802de93e`
- name: `?LaunchFirstRunExperience@PenSignalManagerImpl@@AEAAJPEBG@Z`
- size: `1098`
- prototype: `__int64 __fastcall(PenSignalManagerImpl *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1802df3d0`

## callees

- `0x180009dfc`
- `0x18001c710`
- `0x1800378dc`
- `0x180040d18`
- `0x180053740`
- `0x1800ab120`
- `0x18010ed34`
- `0x180142e10`
- `0x18020119c`
- `0x180212ab0`
- `0x1802dd850`
- `0x1802dd900`
- `0x1802dd940`
- `0x1802ddf38`
- `0x1802de4f4`
- `0x1802de944`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802de68a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802de72a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802de79d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802de8ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802de68a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802de72a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802de79d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802de8ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802de758`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802de787`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802de88a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802de758`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802de787`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802de88a`

## string_xrefs

- `0x1802de52e`: `PenDetachFREComplete`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall PenSignalManagerImpl::LaunchFirstRunExperience(
        PenSignalManagerImpl *this,
        const unsigned __int16 *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, _QWORD, __int64 *); // rbx
  __int64 v9; // rax
  int v10; // eax
  __int64 v11; // rdx
  PenSignalManagerImpl *v12; // rcx
  unsigned int v13; // esi
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, _QWORD, __int64 *); // rbx
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, HSTRING *); // rbx
  __int64 v19; // rdx
  __int64 v20; // rdi
  __int64 v21; // rbx
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rdx
  const unsigned __int16 *StringRawBuffer; // rax
  PenSignalManagerImpl *v28; // rcx
  const unsigned __int16 *v29; // rdx
  int v30; // eax
  HSTRING string; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v32; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v33; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v34; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v35; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v36; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v37[4]; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-90h] BYREF
  __int64 v39; // [rsp+88h] [rbp-78h]
  _BYTE v40[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v41[32]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v42[32]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v43[32]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  if ( IsUserOOBEOrCredentialReset() )
    return 0;
  v3 = SHRegSetBOOL(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\PenWorkspace",
         L"PenDetachFREComplete",
         1);
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4C,
      (unsigned int)"shell\\twinui\\pensignalmanager\\lib\\pensignalmanagerimpl.cpp",
      (const char *)(unsigned int)v3,
      (int)string);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAB,
      (unsigned int)"shell\\twinui\\pensignalmanager\\lib\\pensignalmanagerimpl.cpp",
      (const char *)v4,
      (int)string);
    return v4;
  }
  v35 = 0;
  v36 = 0;
  v34 = 0;
  v39 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Windows.System.Launcher", 0x18u, 0x17u);
  v5 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::ILauncherStatics2>>(v39, &v36);
  v4 = v5;
  if ( v5 < 0 )
  {
    v6 = 178;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"shell\\twinui\\pensignalmanager\\lib\\pensignalmanagerimpl.cpp",
      (const char *)(unsigned int)v5,
      (int)string);
    goto LABEL_38;
  }
  v7 = v36;
  v8 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v36 + 104LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
  v9 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v40, off_1803FA378);
  v5 = v8(v7, *(_QWORD *)(v9 + 24), &v34);
  v4 = v5;
  if ( v5 < 0 )
  {
    v6 = 179;
    goto LABEL_9;
  }
  v5 = BlockOnCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *>,Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *>(
         v34,
         &v35);
  v4 = v5;
  if ( v5 < 0 )
  {
    v6 = 180;
    goto LABEL_9;
  }
  v32 = 0;
  string = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v35 + 56LL))(v35, &v32);
  v4 = v10;
  if ( v10 < 0 )
  {
    v11 = 186;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"shell\\twinui\\pensignalmanager\\lib\\pensignalmanagerimpl.cpp",
      (const char *)(unsigned int)v10,
      (int)string);
    goto LABEL_15;
  }
  if ( !v32 )
  {
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_51575997>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_51575997>::GetImpl'::`2'::impl) )
    {
      v10 = PenSignalManagerImpl::LaunchUri(v12, L"ms-get-started://redirect?id=penfre", 0);
      v4 = v10;
      if ( v10 < 0 )
      {
        v11 = 192;
        goto LABEL_14;
      }
    }
LABEL_36:
    WindowsDeleteString(string);
    v4 = 0;
    goto LABEL_37;
  }
  v13 = 0;
  while ( 1 )
  {
    v33 = 0;
    v14 = v35;
    v15 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v35 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
    v16 = v15(v14, v13, &v33);
    v4 = v16;
    if ( v16 < 0 )
    {
      v19 = 201;
      goto LABEL_29;
    }
    v17 = v33;
    v18 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v33 + 72LL);
    WindowsDeleteString(string);
    string = 0;
    v16 = v18(v17, &string);
    v4 = v16;
    if ( v16 < 0 )
    {
      v19 = 202;
LABEL_29:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"shell\\twinui\\pensignalmanager\\lib\\pensignalmanagerimpl.cpp",
        (const char *)(unsigned int)v16,
        (int)string);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
      goto LABEL_15;
    }
    if ( WindowsGetStringRawBuffer(string, 0) )
      break;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
    if ( ++v13 >= v32 )
      goto LABEL_25;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
LABEL_25:
  if ( !WindowsGetStringRawBuffer(string, 0) )
  {
    WindowsDeleteString(string);
    v4 = -2147418113;
    goto LABEL_37;
  }
  v20 = std::wstring::wstring(v40, L"undocked");
  v21 = std::wstring::wstring(v43, L"source=");
  v22 = std::wstring::wstring(v42, L"://?");
  v24 = std::operator+<unsigned short>(v41, v23, v22);
  std::wstring::wstring(&hstringHeader, v25, v24, v21);
  std::wstring::wstring(v37, v26, &hstringHeader, v20);
  std::wstring::_Tidy_deallocate(&hstringHeader);
  std::wstring::_Tidy_deallocate(v41);
  std::wstring::_Tidy_deallocate(v42);
  std::wstring::_Tidy_deallocate(v43);
  std::wstring::_Tidy_deallocate(v40);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v29 = (const unsigned __int16 *)v37;
  if ( v37[3] > (unsigned __int16 *)7 )
    v29 = v37[0];
  v30 = PenSignalManagerImpl::LaunchUri(v28, v29, StringRawBuffer);
  v4 = v30;
  if ( v30 >= 0 )
  {
    std::wstring::_Tidy_deallocate(v37);
    goto LABEL_36;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xE0,
    (unsigned int)"shell\\twinui\\pensignalmanager\\lib\\pensignalmanagerimpl.cpp",
    (const char *)(unsigned int)v30,
    (int)string);
  std::wstring::_Tidy_deallocate(v37);
LABEL_15:
  WindowsDeleteString(string);
LABEL_37:
  string = 0;
LABEL_38:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
  return v4;
}

```

## disassembly

```asm
0x1802de4f4  push    rbp
0x1802de4f6  push    rbx
0x1802de4f7  push    rsi
0x1802de4f8  push    rdi
0x1802de4f9  push    r14
0x1802de4fb  lea     rbp, [rsp-20h]
0x1802de500  sub     rsp, 120h
0x1802de507  mov     rax, cs:__security_cookie
0x1802de50e  xor     rax, rsp
0x1802de511  mov     [rbp+40h+var_30], rax
0x1802de515  xor     r14d, r14d
0x1802de518  call    ?IsUserOOBEOrCredentialReset@@YA_NXZ; IsUserOOBEOrCredentialReset(void)
0x1802de51d  test    al, al
0x1802de51f  jz      short loc_1802DE528
0x1802de521  xor     eax, eax
0x1802de523  jmp     loc_1802DE923
0x1802de528  mov     r9d, 1; int
0x1802de52e  lea     r8, aPendetachfreco; "PenDetachFREComplete"
0x1802de535  lea     rdx, aSoftwareMicros_75; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1802de53c  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x1802de543  call    ?SHRegSetBOOL@@YAJPEAUHKEY__@@PEBG1H@Z; SHRegSetBOOL(HKEY__ *,ushort const *,ushort const *,int)
0x1802de548  mov     ebx, eax
0x1802de54a  test    eax, eax
0x1802de54c  jns     short loc_1802DE583
0x1802de54e  mov     rcx, [rbp+48h]; this
0x1802de552  mov     r9d, eax; char *
0x1802de555  lea     r8, aShellTwinuiPen_1; "shell\\twinui\\pensignalmanager\\lib\\p"...
0x1802de55c  mov     edx, 4Ch ; 'L'; void *
0x1802de561  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802de566  mov     rcx, [rbp+48h]; this
0x1802de56a  mov     r9d, ebx; char *
0x1802de56d  lea     r8, aShellTwinuiPen_1; "shell\\twinui\\pensignalmanager\\lib\\p"...
0x1802de574  mov     edx, 0ABh; void *
0x1802de579  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802de57e  jmp     loc_1802DE921
0x1802de583  mov     [rsp+140h+var_100], r14
0x1802de588  mov     [rsp+140h+var_F8], r14
0x1802de58d  mov     [rsp+140h+var_108], r14
0x1802de592  mov     [rbp+40h+var_B8], r14
0x1802de596  mov     r9d, 17h; unsigned int
0x1802de59c  lea     r8d, [r9+1]; unsigned int
0x1802de5a0  lea     rdx, ?RuntimeClass_Windows_System_Launcher@@3QBGB; "Windows.System.Launcher"
0x1802de5a7  lea     rcx, [rsp+140h+hstringHeader]; hstringHeader
0x1802de5ac  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1802de5b1  lea     rdx, [rsp+140h+var_F8]
0x1802de5b6  mov     rcx, [rbp+40h+var_B8]
0x1802de5ba  call    ??$GetActivationFactory@V?$ComPtr@UILauncherStatics2@System@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UILauncherStatics2@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::ILauncherStatics2>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::ILauncherStatics2>>)
0x1802de5bf  mov     ebx, eax
0x1802de5c1  test    eax, eax
0x1802de5c3  jns     short loc_1802DE5CC
0x1802de5c5  mov     edx, 0B2h
0x1802de5ca  jmp     short loc_1802DE612
0x1802de5cc  mov     rdi, [rsp+140h+var_F8]
0x1802de5d1  mov     rax, [rdi]
0x1802de5d4  mov     rbx, [rax+68h]
0x1802de5d8  lea     rcx, [rsp+140h+var_108]
0x1802de5dd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802de5e2  lea     rdx, off_1803FA378; "first-run-pen-experience"
0x1802de5e9  lea     rcx, [rbp+40h+var_B0]
0x1802de5ed  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1802de5f2  nop
0x1802de5f3  lea     r8, [rsp+140h+var_108]
0x1802de5f8  mov     rdx, [rax+18h]
0x1802de5fc  mov     rcx, rdi
0x1802de5ff  mov     rax, rbx
0x1802de602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802de607  mov     ebx, eax
0x1802de609  test    eax, eax
0x1802de60b  jns     short loc_1802DE62A
0x1802de60d  mov     edx, 0B3h; void *
0x1802de612  mov     rcx, [rbp+48h]; this
0x1802de616  mov     r9d, eax; char *
0x1802de619  lea     r8, aShellTwinuiPen_1; "shell\\twinui\\pensignalmanager\\lib\\p"...
0x1802de620  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802de625  jmp     loc_1802DE901
0x1802de62a  lea     rdx, [rsp+140h+var_100]
0x1802de62f  mov     rcx, [rsp+140h+var_108]
0x1802de634  call    ??$BlockOnCompletionAndGetResults@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppInfo@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInfo@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@23@PEAU?$IVectorView@PEAVAppInfo@ApplicationModel@Windows@@@Collections@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInfo@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@PEAPEAU?$IVectorView@PEAVAppInfo@ApplicationModel@Windows@@@Collections@12@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *>,Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *> *,Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> * *,tagCOWAIT_FLAGS,void *)
0x1802de639  mov     ebx, eax
0x1802de63b  test    eax, eax
0x1802de63d  jns     short loc_1802DE646
0x1802de63f  mov     edx, 0B4h
0x1802de644  jmp     short loc_1802DE612
0x1802de646  mov     [rsp+140h+var_118], r14d
0x1802de64b  mov     [rsp+140h+string], r14; int
0x1802de650  mov     rcx, [rsp+140h+var_100]
0x1802de655  mov     rax, [rcx]
0x1802de658  lea     rdx, [rsp+140h+var_118]
0x1802de65d  mov     rax, [rax+38h]
0x1802de661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802de666  mov     ebx, eax
0x1802de668  test    eax, eax
0x1802de66a  jns     short loc_1802DE69B
0x1802de66c  mov     edx, 0BAh; void *
0x1802de671  lea     r8, aShellTwinuiPen_1; "shell\\twinui\\pensignalmanager\\lib\\p"...
0x1802de678  mov     r9d, eax; char *
0x1802de67b  mov     rcx, [rbp+48h]; this
0x1802de67f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802de684  nop
0x1802de685  mov     rcx, [rsp+140h+string]; string
0x1802de68a  call    cs:__imp_WindowsDeleteString
0x1802de691  nop     dword ptr [rax+rax+00h]
0x1802de696  jmp     loc_1802DE8FC
0x1802de69b  mov     eax, [rsp+140h+var_118]
0x1802de69f  test    eax, eax
0x1802de6a1  jnz     short loc_1802DE6D7
0x1802de6a3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_51575997@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_51575997@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_51575997> `wil::Feature<__WilFeatureTraits_Feature_51575997>::GetImpl(void)'::`2'::impl
0x1802de6aa  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_51575997@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_51575997>::__private_IsEnabled(void)
0x1802de6af  test    al, al
0x1802de6b1  jnz     loc_1802DE8E8
0x1802de6b7  xor     r8d, r8d; unsigned __int16 *
0x1802de6ba  lea     rdx, aMsGetStartedRe; "ms-get-started://redirect?id=penfre"
0x1802de6c1  call    ?LaunchUri@PenSignalManagerImpl@@AEAAJPEBG0@Z; PenSignalManagerImpl::LaunchUri(ushort const *,ushort const *)
0x1802de6c6  mov     ebx, eax
0x1802de6c8  test    eax, eax
0x1802de6ca  jns     loc_1802DE8E8
0x1802de6d0  mov     edx, 0C0h
0x1802de6d5  jmp     short loc_1802DE671
0x1802de6d7  mov     esi, r14d
0x1802de6da  test    eax, eax
0x1802de6dc  jz      loc_1802DE780
0x1802de6e2  mov     [rsp+140h+var_110], r14
0x1802de6e7  mov     rdi, [rsp+140h+var_100]
0x1802de6ec  mov     rax, [rdi]
0x1802de6ef  mov     rbx, [rax+30h]
0x1802de6f3  lea     rcx, [rsp+140h+var_110]
0x1802de6f8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802de6fd  lea     r8, [rsp+140h+var_110]
0x1802de702  mov     edx, esi
0x1802de704  mov     rcx, rdi
0x1802de707  mov     rax, rbx
0x1802de70a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802de70f  mov     ebx, eax
0x1802de711  test    eax, eax
0x1802de713  js      loc_1802DE7E2
0x1802de719  mov     rdi, [rsp+140h+var_110]
0x1802de71e  mov     rax, [rdi]
0x1802de721  mov     rbx, [rax+48h]
0x1802de725  mov     rcx, [rsp+140h+string]; string
0x1802de72a  call    cs:__imp_WindowsDeleteString
0x1802de731  nop     dword ptr [rax+rax+00h]
0x1802de736  mov     [rsp+140h+string], r14; int
0x1802de73b  lea     rdx, [rsp+140h+string]
0x1802de740  mov     rcx, rdi
0x1802de743  mov     rax, rbx
0x1802de746  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802de74b  mov     ebx, eax
0x1802de74d  test    eax, eax
0x1802de74f  js      short loc_1802DE7BA
0x1802de751  xor     edx, edx; length
0x1802de753  mov     rcx, [rsp+140h+string]; string
0x1802de758  call    cs:__imp_WindowsGetStringRawBuffer
0x1802de75f  nop     dword ptr [rax+rax+00h]
0x1802de764  nop
0x1802de765  lea     rcx, [rsp+140h+var_110]
0x1802de76a  test    rax, rax
0x1802de76d  jnz     short loc_1802DE7B3
0x1802de76f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802de774  inc     esi
0x1802de776  cmp     esi, [rsp+140h+var_118]
0x1802de77a  jb      loc_1802DE6E2
0x1802de780  xor     edx, edx; length
0x1802de782  mov     rcx, [rsp+140h+string]; string
0x1802de787  call    cs:__imp_WindowsGetStringRawBuffer
0x1802de78e  nop     dword ptr [rax+rax+00h]
0x1802de793  test    rax, rax
0x1802de796  jnz     short loc_1802DE7E9
0x1802de798  mov     rcx, [rsp+140h+string]; string
0x1802de79d  call    cs:__imp_WindowsDeleteString
0x1802de7a4  nop     dword ptr [rax+rax+00h]
0x1802de7a9  mov     ebx, 8000FFFFh
0x1802de7ae  jmp     loc_1802DE8FC
0x1802de7b3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802de7b8  jmp     short loc_1802DE780
0x1802de7ba  mov     edx, 0CAh; void *
0x1802de7bf  lea     r8, aShellTwinuiPen_1; "shell\\twinui\\pensignalmanager\\lib\\p"...
0x1802de7c6  mov     r9d, eax; char *
0x1802de7c9  mov     rcx, [rbp+48h]; this
0x1802de7cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802de7d2  nop
0x1802de7d3  lea     rcx, [rsp+140h+var_110]
0x1802de7d8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802de7dd  jmp     loc_1802DE685
0x1802de7e2  mov     edx, 0C9h
0x1802de7e7  jmp     short loc_1802DE7BF
0x1802de7e9  lea     rdx, aUndocked; "undocked"
0x1802de7f0  lea     rcx, [rbp+40h+var_B0]
0x1802de7f4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1802de7f9  mov     rdi, rax
0x1802de7fc  lea     rdx, aSource; "source="
0x1802de803  lea     rcx, [rbp+40h+var_50]
0x1802de807  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1802de80c  mov     rbx, rax
0x1802de80f  lea     rdx, asc_1804391F0; "://?"
0x1802de816  lea     rcx, [rbp+40h+var_70]
0x1802de81a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1802de81f  nop
0x1802de820  mov     r8, rax
0x1802de823  lea     rcx, [rbp+40h+var_90]
0x1802de827  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG$$QEAV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring &&)
0x1802de82c  nop
0x1802de82d  mov     r9, rbx
0x1802de830  mov     r8, rax
0x1802de833  lea     rcx, [rsp+140h+hstringHeader]
0x1802de838  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring &,std::wstring &)
0x1802de83d  nop
0x1802de83e  mov     r9, rdi
0x1802de841  lea     r8, [rsp+140h+hstringHeader]
0x1802de846  lea     rcx, [rsp+140h+var_F0]
0x1802de84b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring &,std::wstring &)
0x1802de850  nop
0x1802de851  lea     rcx, [rsp+140h+hstringHeader]
0x1802de856  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1802de85b  nop
0x1802de85c  lea     rcx, [rbp+40h+var_90]
0x1802de860  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1802de865  nop
0x1802de866  lea     rcx, [rbp+40h+var_70]
0x1802de86a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1802de86f  nop
0x1802de870  lea     rcx, [rbp+40h+var_50]
0x1802de874  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1802de879  nop
0x1802de87a  lea     rcx, [rbp+40h+var_B0]
0x1802de87e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1802de883  xor     edx, edx; length
0x1802de885  mov     rcx, [rsp+140h+string]; string
0x1802de88a  call    cs:__imp_WindowsGetStringRawBuffer
0x1802de891  nop     dword ptr [rax+rax+00h]
0x1802de896  lea     rdx, [rsp+140h+var_F0]
0x1802de89b  cmp     [rsp+140h+var_D8], 7
0x1802de8a1  cmova   rdx, [rsp+140h+var_F0]; unsigned __int16 *
0x1802de8a7  mov     r8, rax; unsigned __int16 *
0x1802de8aa  call    ?LaunchUri@PenSignalManagerImpl@@AEAAJPEBG0@Z; PenSignalManagerImpl::LaunchUri(ushort const *,ushort const *)
0x1802de8af  mov     ebx, eax
0x1802de8b1  test    eax, eax
0x1802de8b3  jns     short loc_1802DE8DD
0x1802de8b5  mov     rcx, [rbp+48h]; this
0x1802de8b9  mov     r9d, eax; char *
0x1802de8bc  lea     r8, aShellTwinuiPen_1; "shell\\twinui\\pensignalmanager\\lib\\p"...
0x1802de8c3  mov     edx, 0E0h; void *
0x1802de8c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802de8cd  nop
0x1802de8ce  lea     rcx, [rsp+140h+var_F0]
0x1802de8d3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1802de8d8  jmp     loc_1802DE685
0x1802de8dd  lea     rcx, [rsp+140h+var_F0]
0x1802de8e2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1802de8e7  nop
0x1802de8e8  mov     rcx, [rsp+140h+string]; string
0x1802de8ed  call    cs:__imp_WindowsDeleteString
0x1802de8f4  nop     dword ptr [rax+rax+00h]
0x1802de8f9  mov     ebx, r14d
0x1802de8fc  mov     [rsp+140h+string], r14
0x1802de901  lea     rcx, [rsp+140h+var_108]
0x1802de906  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802de90b  nop
0x1802de90c  lea     rcx, [rsp+140h+var_F8]
0x1802de911  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802de916  nop
0x1802de917  lea     rcx, [rsp+140h+var_100]
0x1802de91c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802de921  mov     eax, ebx
0x1802de923  mov     rcx, [rbp+40h+var_30]
0x1802de927  xor     rcx, rsp; StackCookie
0x1802de92a  call    __security_check_cookie
0x1802de92f  add     rsp, 120h
0x1802de936  pop     r14
0x1802de938  pop     rdi
0x1802de939  pop     rsi
0x1802de93a  pop     rbx
0x1802de93b  pop     rbp
0x1802de93c  retn
```
