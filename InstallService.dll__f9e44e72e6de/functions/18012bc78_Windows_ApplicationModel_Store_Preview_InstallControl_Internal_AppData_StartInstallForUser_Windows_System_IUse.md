# Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData::StartInstallForUser(Windows::System::IUser *,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallType,ulong,HSTRING__ *,HSTRING__ *,TraceLoggingCorrelationVector *,Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> * *)

- ea: `0x18012bc78`
- end: `0x18012c1d1`
- name: `?StartInstallForUser@AppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@QEAAJPEAUIUser@System@7@W4AppInstallType@34567@KPEAUHSTRING__@@2PEAVTraceLoggingCorrelationVector@@PEAPEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@7@@Z`
- size: `1369`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18009dc80`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x18001c414`
- `0x18001c844`
- `0x18001ddb0`
- `0x18003f884`
- `0x18008babc`
- `0x1800a86bc`
- `0x1800c7538`
- `0x1800d6a24`
- `0x18012bc78`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012beee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012c063`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012c12d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012c17d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012beee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012c063`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012c12d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012c17d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18012bd4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18012bdda`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18012bd4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18012bdda`

## string_xrefs

- `0x18012bd7a`: `onecoreuap\enduser\winstore\installservice\lib\appdata.cpp`
- `0x18012be11`: `onecoreuap\enduser\winstore\installservice\lib\appdata.cpp`
- `0x18012be83`: `onecoreuap\enduser\winstore\installservice\lib\appdata.cpp`
- `0x18012bf93`: `onecoreuap\enduser\winstore\installservice\lib\appdata.cpp`
- `0x18012bffb`: `onecoreuap\enduser\winstore\installservice\lib\appdata.cpp`
- `0x18012c116`: `onecoreuap\enduser\winstore\installservice\lib\appdata.cpp`
- `0x18012be62`: `Trying to install %d products`
- `0x18012bd6d`: `Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData::StartInstallForUser`
- `0x18012be04`: `Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData::StartInstallForUser`
- `0x18012be76`: `Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData::StartInstallForUser`
- `0x18012bf87`: `Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData::StartInstallForUser`
- `0x18012bfee`: `Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData::StartInstallForUser`
- `0x18012c109`: `Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData::StartInstallForUser`
- `0x18012bd19`: `Cannot Install %s .Failure Processing FulfillmentData`
- `0x18012bd99`: `Cannot Install %s .Failure Processing FulfillmentData`
- `0x18012bf80`: `InstallAgent_InstallProducts( user, spProductFulfillmentDataView.Get(), Internal::InstallTypeFromAppInstallType(installType), installAgentFlags, identityData.Get(), volumePath, callerApplicationId, szCV, &spView)`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData::StartInstallForUser(
        __int64 a1,
        UserHelpers *a2,
        __int64 a3,
        unsigned int a4,
        HSTRING a5,
        struct Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *a6,
        TraceLoggingCorrelationVector *a7,
        _QWORD *a8)
{
  __int64 v10; // rcx
  int v11; // esi
  __int64 v12; // rcx
  PCWSTR StringRawBuffer; // rax
  __int64 v14; // rbx
  __int64 v15; // rdi
  PCWSTR v16; // rax
  _QWORD *v17; // r12
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, _QWORD **); // rbx
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, HSTRING *); // rbx
  int v22; // eax
  unsigned int i; // r15d
  __int64 v24; // rdi
  int (__fastcall *v25)(__int64, _QWORD, TraceLoggingCorrelationVector **); // rbx
  TraceLoggingCorrelationVector *v26; // rdi
  int (__fastcall *v27)(TraceLoggingCorrelationVector *, HSTRING *); // rbx
  Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl *v28; // rbx
  Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl *v29; // rbx
  int v31; // [rsp+28h] [rbp-D8h]
  __int64 v32; // [rsp+40h] [rbp-C0h]
  __int64 v33; // [rsp+40h] [rbp-C0h]
  __int64 v34; // [rsp+40h] [rbp-C0h]
  unsigned int v35; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING string; // [rsp+58h] [rbp-A8h] BYREF
  struct Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *v37; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v38; // [rsp+68h] [rbp-98h] BYREF
  TraceLoggingCorrelationVector *v39; // [rsp+70h] [rbp-90h] BYREF
  int v40; // [rsp+78h] [rbp-88h]
  _QWORD *v41; // [rsp+80h] [rbp-80h] BYREF
  int v42; // [rsp+88h] [rbp-78h] BYREF
  HSTRING v43; // [rsp+90h] [rbp-70h] BYREF
  __int64 v44; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v45[2]; // [rsp+A0h] [rbp-60h] BYREF
  char v46[144]; // [rsp+B0h] [rbp-50h] BYREF

  v35 = a4;
  string = a5;
  v37 = a6;
  v39 = a7;
  v41 = a8;
  *a8 = 0;
  v45[0] = 0;
  v38 = 0;
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(v45);
  v11 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem,Windows::Foundation::Collections::Internal::AgileVector<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>,0>>(
          v10,
          v45);
  if ( v11 >= 0 )
  {
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v38);
    v11 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<WindowsUpdate::Internal::IFulfillmentDataInfo,Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IFulfillmentDataInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IFulfillmentDataInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IFulfillmentDataInfo *>,0>>(
            v12,
            &v38);
  }
  if ( *(int *)(a1 + 208) >= 0
    && (*(int (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v38 + 104LL))(v38, *(_QWORD *)(a1 + 88)) < 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 176), 0);
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\appdata.cpp",
      0x314u,
      "Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData::StartInstallForUser",
      -1,
      L"Cannot Install %s .Failure Processing FulfillmentData",
      0,
      0,
      StringRawBuffer);
  }
  v14 = *(_QWORD *)(a1 + 144);
  v15 = *(_QWORD *)(a1 + 152);
  while ( v14 != v15 )
  {
    if ( *(int *)(*(_QWORD *)v14 + 208LL) >= 0
      && (*(int (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v38 + 104LL))(v38, *(_QWORD *)(*(_QWORD *)v14 + 88LL)) < 0 )
    {
      v16 = WindowsGetStringRawBuffer(*(HSTRING *)(*(_QWORD *)v14 + 176LL), 0);
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\appdata.cpp",
        0x320u,
        "Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData::StartInstallForUser",
        -1,
        L"Cannot Install %s .Failure Processing FulfillmentData",
        0,
        0,
        v16);
    }
    v14 += 8;
  }
  v17 = v41;
  if ( v11 >= 0 )
  {
    v42 = 0;
    (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v38 + 56LL))(v38, &v42);
    LODWORD(v32) = v42;
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\appdata.cpp",
      0x329u,
      "Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData::StartInstallForUser",
      -1,
      L"Trying to install %d products",
      0,
      0,
      v32);
    v41 = 0;
    v44 = 0;
    v18 = v38;
    v19 = *(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v38 + 64LL);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v41);
    v11 = v19(v18, &v41);
    TraceLoggingCorrelationVector::Increment(v39, v46);
    v43 = 0;
    if ( v11 >= 0 )
    {
      v20 = *(_QWORD *)(a1 + 72);
      v21 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v20 + 128LL);
      WindowsDeleteString(0);
      v43 = 0;
      v11 = v21(v20, &v43);
      if ( v11 >= 0 )
      {
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v44);
        v39 = (TraceLoggingCorrelationVector *)0x100000000LL;
        v40 = 3;
        v22 = InstallAgent_InstallProducts(a2, (__int64)v43, (__int64)string, (HSTRING)v37, (__int64)v46, (__int64)&v44);
        v11 = TraceHR(
                "onecoreuap\\enduser\\winstore\\installservice\\lib\\appdata.cpp",
                0x341u,
                "Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData::StartInstallForUser",
                "InstallAgent_InstallProducts( user, spProductFulfillmentDataView.Get(), Internal::InstallTypeFromAppInst"
                "allType(installType), installAgentFlags, identityData.Get(), volumePath, callerApplicationId, szCV, &spView)",
                v22,
                v31);
        if ( v11 >= 0 )
        {
          v35 = 0;
          v11 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v44 + 56LL))(v44, &v35);
          LODWORD(v33) = v35;
          LogMessage(
            3u,
            "onecoreuap\\enduser\\winstore\\installservice\\lib\\appdata.cpp",
            0x347u,
            "Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData::StartInstallForUser",
            -1,
            L"Succesfully queued  %d products",
            0,
            0,
            v33);
          for ( i = 0; i < v35; ++i )
          {
            v39 = 0;
            v37 = 0;
            string = 0;
            v24 = v44;
            v25 = *(int (__fastcall **)(__int64, _QWORD, TraceLoggingCorrelationVector **))(*(_QWORD *)v44 + 48LL);
            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v39);
            if ( v25(v24, i, &v39) < 0
              || (v26 = v39,
                  v27 = *(int (__fastcall **)(TraceLoggingCorrelationVector *, HSTRING *))(*(_QWORD *)v39 + 48LL),
                  WindowsDeleteString(string),
                  string = 0,
                  v27(v26, &string) < 0)
              || (v28 = *(Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl **)(a1 + 72),
                  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v37),
                  (int)Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_FindInstallItem(
                         v28,
                         string,
                         1,
                         &v37) < 0) )
            {
              v29 = *(Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl **)(a1 + 72);
              Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v37);
              v11 = Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::FindOrCreateInstallItem(
                      v29,
                      v39,
                      &v37);
              if ( v11 < 0 )
                goto LABEL_22;
            }
            v11 = (*(__int64 (__fastcall **)(_QWORD, struct Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *))(*(_QWORD *)v45[0] + 104LL))(
                    v45[0],
                    v37);
            if ( v11 < 0 )
            {
LABEL_22:
              LODWORD(v34) = i;
              LogMessage(
                2u,
                "onecoreuap\\enduser\\winstore\\installservice\\lib\\appdata.cpp",
                0x361u,
                "Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData::StartInstallForUser",
                v11,
                L"Failure trying to query queued product. index = %d",
                0,
                0,
                v34);
            }
            WindowsDeleteString(string);
            string = 0;
            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v37);
            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v39);
          }
          if ( v11 >= 0 )
            v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)v45[0] + 64LL))(v45[0], v17);
        }
      }
    }
    WindowsDeleteString(v43);
    v43 = 0;
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v44);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v41);
  }
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v38);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(v45);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18012bc78  push    rbp
0x18012bc7a  push    rbx
0x18012bc7b  push    rsi
0x18012bc7c  push    rdi
0x18012bc7d  push    r12
0x18012bc7f  push    r13
0x18012bc81  push    r14
0x18012bc83  push    r15
0x18012bc85  lea     rbp, [rsp-58h]
0x18012bc8a  sub     rsp, 158h
0x18012bc91  mov     rax, cs:__security_cookie
0x18012bc98  xor     rax, rsp
0x18012bc9b  mov     [rbp+90h+var_50], rax
0x18012bc9f  mov     [rsp+190h+var_140], r9d
0x18012bca4  movsxd  r13, r8d
0x18012bca7  mov     r15, rdx
0x18012bcaa  mov     r14, rcx
0x18012bcad  mov     rax, [rbp+90h+arg_20]
0x18012bcb4  mov     [rsp+190h+string], rax
0x18012bcb9  mov     rax, [rbp+90h+arg_28]
0x18012bcc0  mov     [rsp+190h+var_130], rax
0x18012bcc5  mov     rax, [rbp+90h+arg_30]
0x18012bccc  mov     [rsp+190h+var_120], rax
0x18012bcd1  mov     r12, [rbp+90h+arg_38]
0x18012bcd8  mov     [rbp+90h+var_110], r12
0x18012bcdc  xor     ebx, ebx
0x18012bcde  mov     [r12], rbx
0x18012bce2  mov     [rbp+90h+var_F0], rbx
0x18012bce6  mov     [rsp+190h+var_128], rbx
0x18012bceb  lea     rcx, [rbp+90h+var_F0]
0x18012bcef  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18012bcf4  lea     rdx, [rbp+90h+var_F0]
0x18012bcf8  call    ??$CreateExternalObjectVector@VAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@V?$AgileVector@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@U?$DefaultEqualityPredicate@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Internal@Collections@Foundation@6@U?$DefaultLifetimeTraits@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@89Foundation@6@$0A@@Internal@Collections@Foundation@6@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@U?$DefaultEqualityPredicate@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Internal@Collections@Foundation@6@U?$DefaultLifetimeTraits@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@89Foundation@6@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem,Windows::Foundation::Collections::Internal::AgileVector<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>,0> * *)
0x18012bcfd  mov     esi, eax
0x18012bcff  test    eax, eax
0x18012bd01  js      short loc_18012BD19
0x18012bd03  lea     rcx, [rsp+190h+var_128]
0x18012bd08  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18012bd0d  lea     rdx, [rsp+190h+var_128]
0x18012bd12  call    ??$CreateExternalObjectVector@UIFulfillmentDataInfo@Internal@WindowsUpdate@@V?$AgileVector@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@U?$DefaultEqualityPredicate@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@2Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@2567@$0A@@2Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@U?$DefaultEqualityPredicate@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@2Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@2567@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<WindowsUpdate::Internal::IFulfillmentDataInfo,Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IFulfillmentDataInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IFulfillmentDataInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IFulfillmentDataInfo *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IFulfillmentDataInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IFulfillmentDataInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IFulfillmentDataInfo *>,0> * *)
0x18012bd17  mov     esi, eax
0x18012bd19  lea     rdi, aCannotInstallS; "Cannot Install %s .Failure Processing F"...
0x18012bd20  cmp     [r14+0D0h], ebx
0x18012bd27  jl      short loc_18012BD8B
0x18012bd29  mov     rcx, [rsp+190h+var_128]
0x18012bd2e  mov     rax, [rcx]
0x18012bd31  mov     rdx, [r14+58h]
0x18012bd35  mov     rax, [rax+68h]
0x18012bd39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012bd3e  test    eax, eax
0x18012bd40  jns     short loc_18012BD8B
0x18012bd42  xor     edx, edx; length
0x18012bd44  mov     rcx, [r14+0B0h]; string
0x18012bd4b  call    cs:__imp_WindowsGetStringRawBuffer
0x18012bd51  mov     [rsp+190h+var_150], rax
0x18012bd56  mov     [rsp+190h+var_158], rbx; unsigned __int16 *
0x18012bd5b  mov     [rsp+190h+var_160], rbx; char *
0x18012bd60  mov     [rsp+190h+var_168], rdi; unsigned __int16 *
0x18012bd65  mov     [rsp+190h+var_170], 0FFFFFFFFh; int
0x18012bd6d  lea     r9, aWindowsApplica_45; "Windows::ApplicationModel::Store::Previ"...
0x18012bd74  mov     r8d, 314h; unsigned int
0x18012bd7a  lea     rdx, aOnecoreuapEndu_64; "onecoreuap\\enduser\\winstore\\installs"...
0x18012bd81  mov     ecx, 3; unsigned int
0x18012bd86  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x18012bd8b  mov     rbx, [r14+90h]
0x18012bd92  mov     rdi, [r14+98h]
0x18012bd99  lea     r12, aCannotInstallS; "Cannot Install %s .Failure Processing F"...
0x18012bda0  cmp     rbx, rdi
0x18012bda3  jz      loc_18012BE2B
0x18012bda9  mov     rdx, [rbx]
0x18012bdac  cmp     dword ptr [rdx+0D0h], 0
0x18012bdb3  jl      short loc_18012BE22
0x18012bdb5  mov     rcx, [rsp+190h+var_128]
0x18012bdba  mov     rax, [rcx]
0x18012bdbd  mov     rdx, [rdx+58h]
0x18012bdc1  mov     rax, [rax+68h]
0x18012bdc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012bdca  test    eax, eax
0x18012bdcc  jns     short loc_18012BE22
0x18012bdce  mov     rcx, [rbx]
0x18012bdd1  xor     edx, edx; length
0x18012bdd3  mov     rcx, [rcx+0B0h]; string
0x18012bdda  call    cs:__imp_WindowsGetStringRawBuffer
0x18012bde0  mov     [rsp+190h+var_150], rax
0x18012bde5  mov     [rsp+190h+var_158], 0; unsigned __int16 *
0x18012bdee  mov     [rsp+190h+var_160], 0; char *
0x18012bdf7  mov     [rsp+190h+var_168], r12; unsigned __int16 *
0x18012bdfc  mov     [rsp+190h+var_170], 0FFFFFFFFh; int
0x18012be04  lea     r9, aWindowsApplica_45; "Windows::ApplicationModel::Store::Previ"...
0x18012be0b  mov     r8d, 320h; unsigned int
0x18012be11  lea     rdx, aOnecoreuapEndu_64; "onecoreuap\\enduser\\winstore\\installs"...
0x18012be18  mov     ecx, 3; unsigned int
0x18012be1d  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x18012be22  add     rbx, 8
0x18012be26  jmp     loc_18012BDA0
0x18012be2b  xor     ebx, ebx
0x18012be2d  test    esi, esi
0x18012be2f  mov     r12, [rbp+90h+var_110]
0x18012be33  js      loc_18012C19B
0x18012be39  mov     [rbp+90h+var_108], ebx
0x18012be3c  mov     rcx, [rsp+190h+var_128]
0x18012be41  mov     rax, [rcx]
0x18012be44  lea     rdx, [rbp+90h+var_108]
0x18012be48  mov     rax, [rax+38h]
0x18012be4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012be51  mov     eax, [rbp+90h+var_108]
0x18012be54  mov     dword ptr [rsp+190h+var_150], eax
0x18012be58  mov     [rsp+190h+var_158], rbx; unsigned __int16 *
0x18012be5d  mov     [rsp+190h+var_160], rbx; char *
0x18012be62  lea     rax, aTryingToInstal; "Trying to install %d products"
0x18012be69  mov     [rsp+190h+var_168], rax; unsigned __int16 *
0x18012be6e  mov     [rsp+190h+var_170], 0FFFFFFFFh; int
0x18012be76  lea     r9, aWindowsApplica_45; "Windows::ApplicationModel::Store::Previ"...
0x18012be7d  mov     r8d, 329h; unsigned int
0x18012be83  lea     rdx, aOnecoreuapEndu_64; "onecoreuap\\enduser\\winstore\\installs"...
0x18012be8a  lea     ecx, [rbx+3]; unsigned int
0x18012be8d  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x18012be92  mov     [rbp+90h+var_110], rbx
0x18012be96  mov     [rbp+90h+var_F8], rbx
0x18012be9a  mov     rdi, [rsp+190h+var_128]
0x18012be9f  mov     rax, [rdi]
0x18012bea2  mov     rbx, [rax+40h]
0x18012bea6  lea     rcx, [rbp+90h+var_110]
0x18012beaa  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18012beaf  lea     rdx, [rbp+90h+var_110]
0x18012beb3  mov     rcx, rdi
0x18012beb6  mov     rax, rbx
0x18012beb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012bebe  mov     esi, eax
0x18012bec0  lea     rdx, [rbp+90h+var_E0]; char *
0x18012bec4  mov     rcx, [rsp+190h+var_120]; this
0x18012bec9  call    ?Increment@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::Increment(char *)
0x18012bece  mov     [rbp+90h+var_100], 0
0x18012bed6  test    esi, esi
0x18012bed8  js      loc_18012C176
0x18012bede  mov     rdi, [r14+48h]
0x18012bee2  mov     rax, [rdi]
0x18012bee5  mov     rbx, [rax+80h]
0x18012beec  xor     ecx, ecx; string
0x18012beee  call    cs:__imp_WindowsDeleteString
0x18012bef4  mov     [rbp+90h+var_100], 0
0x18012befc  lea     rdx, [rbp+90h+var_100]
0x18012bf00  mov     rcx, rdi
0x18012bf03  mov     rax, rbx
0x18012bf06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012bf0b  mov     esi, eax
0x18012bf0d  test    eax, eax
0x18012bf0f  js      loc_18012C176
0x18012bf15  lea     rcx, [rbp+90h+var_F8]
0x18012bf19  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18012bf1e  mov     rax, [rbp+90h+var_100]
0x18012bf22  mov     dword ptr [rsp+190h+var_120], 0
0x18012bf2a  mov     dword ptr [rsp+190h+var_120+4], 1
0x18012bf32  mov     ebx, 3
0x18012bf37  mov     [rsp+190h+var_118], ebx
0x18012bf3b  lea     rcx, [rbp+90h+var_F8]
0x18012bf3f  mov     [rsp+190h+var_150], rcx
0x18012bf44  lea     rcx, [rbp+90h+var_E0]
0x18012bf48  mov     [rsp+190h+var_158], rcx
0x18012bf4d  mov     rcx, [rsp+190h+var_130]
0x18012bf52  mov     [rsp+190h+var_160], rcx
0x18012bf57  mov     rcx, [rsp+190h+string]
0x18012bf5c  mov     [rsp+190h+var_168], rcx; int
0x18012bf61  mov     qword ptr [rsp+190h+var_170], rax
0x18012bf66  mov     r9d, [rsp+190h+var_140]
0x18012bf6b  mov     r8d, dword ptr [rsp+r13*4+190h+var_120]
0x18012bf70  mov     rdx, [rbp+90h+var_110]
0x18012bf74  mov     rcx, r15
0x18012bf77  call    ?InstallAgent_InstallProducts@@YAJPEAUIUser@System@Windows@@PEAU?$IVectorView@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@Collections@Foundation@3@W4InstallType@Internal@WindowsUpdate@@KPEAUHSTRING__@@33PEBDPEAPEAU?$IVectorView@PEAUIInstallItem@Internal@WindowsUpdate@@@563@@Z; InstallAgent_InstallProducts(Windows::System::IUser *,Windows::Foundation::Collections::IVectorView<WindowsUpdate::Internal::IFulfillmentDataInfo *> *,WindowsUpdate::Internal::InstallType,ulong,HSTRING__ *,HSTRING__ *,HSTRING__ *,char const *,Windows::Foundation::Collections::IVectorView<WindowsUpdate::Internal::IInstallItem *> * *)
0x18012bf7c  mov     [rsp+190h+var_170], eax; int
0x18012bf80  lea     r9, aInstallagentIn; "InstallAgent_InstallProducts( user, spP"...
0x18012bf87  lea     r8, aWindowsApplica_45; "Windows::ApplicationModel::Store::Previ"...
0x18012bf8e  mov     edx, 341h; unsigned int
0x18012bf93  lea     rcx, aOnecoreuapEndu_64; "onecoreuap\\enduser\\winstore\\installs"...
0x18012bf9a  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x18012bf9f  mov     esi, eax
0x18012bfa1  xor     r13d, r13d
0x18012bfa4  test    eax, eax
0x18012bfa6  js      loc_18012C179
0x18012bfac  mov     [rsp+190h+var_140], r13d
0x18012bfb1  mov     rcx, [rbp+90h+var_F8]
0x18012bfb5  mov     rax, [rcx]
0x18012bfb8  lea     rdx, [rsp+190h+var_140]
0x18012bfbd  mov     rax, [rax+38h]
0x18012bfc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012bfc6  mov     esi, eax
0x18012bfc8  mov     eax, [rsp+190h+var_140]
0x18012bfcc  mov     dword ptr [rsp+190h+var_150], eax
0x18012bfd0  mov     [rsp+190h+var_158], r13; unsigned __int16 *
0x18012bfd5  mov     [rsp+190h+var_160], r13; char *
0x18012bfda  lea     rax, aSuccesfullyQue; "Succesfully queued  %d products"
0x18012bfe1  mov     [rsp+190h+var_168], rax; unsigned __int16 *
0x18012bfe6  mov     [rsp+190h+var_170], 0FFFFFFFFh; int
0x18012bfee  lea     r9, aWindowsApplica_45; "Windows::ApplicationModel::Store::Previ"...
0x18012bff5  mov     r8d, 347h; unsigned int
0x18012bffb  lea     rdx, aOnecoreuapEndu_64; "onecoreuap\\enduser\\winstore\\installs"...
0x18012c002  mov     ecx, ebx; unsigned int
0x18012c004  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x18012c009  mov     r15d, r13d
0x18012c00c  cmp     [rsp+190h+var_140], r13d
0x18012c011  jbe     loc_18012C15B
0x18012c017  mov     [rsp+190h+var_120], r13
0x18012c01c  mov     [rsp+190h+var_130], r13
0x18012c021  mov     [rsp+190h+string], r13
0x18012c026  mov     rdi, [rbp+90h+var_F8]
0x18012c02a  mov     rax, [rdi]
0x18012c02d  mov     rbx, [rax+30h]
0x18012c031  lea     rcx, [rsp+190h+var_120]
0x18012c036  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18012c03b  lea     r8, [rsp+190h+var_120]
0x18012c040  mov     edx, r15d
0x18012c043  mov     rcx, rdi
0x18012c046  mov     rax, rbx
0x18012c049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012c04e  test    eax, eax
0x18012c050  js      short loc_18012C0A9
0x18012c052  mov     rdi, [rsp+190h+var_120]
0x18012c057  mov     rax, [rdi]
0x18012c05a  mov     rbx, [rax+30h]
0x18012c05e  mov     rcx, [rsp+190h+string]; string
0x18012c063  call    cs:__imp_WindowsDeleteString
0x18012c069  mov     [rsp+190h+string], r13
0x18012c06e  lea     rdx, [rsp+190h+string]
0x18012c073  mov     rcx, rdi
0x18012c076  mov     rax, rbx
0x18012c079  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012c07e  test    eax, eax
0x18012c080  js      short loc_18012C0A9
0x18012c082  mov     rbx, [r14+48h]
0x18012c086  lea     rcx, [rsp+190h+var_130]
0x18012c08b  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18012c090  lea     r9, [rsp+190h+var_130]; struct Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem **
0x18012c095  mov     r8b, 1; bool
0x18012c098  mov     rdx, [rsp+190h+string]; HSTRING
0x18012c09d  mov     rcx, rbx; this
0x18012c0a0  call    ?_FindInstallItem@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAAJPEAUHSTRING__@@_NPEAPEAVAppInstallItem@23456@@Z; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_FindInstallItem(HSTRING__ *,bool,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem * *)
0x18012c0a5  test    eax, eax
0x18012c0a7  jns     short loc_18012C0CF
0x18012c0a9  mov     rbx, [r14+48h]
0x18012c0ad  lea     rcx, [rsp+190h+var_130]
0x18012c0b2  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18012c0b7  lea     r8, [rsp+190h+var_130]; struct Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem **
0x18012c0bc  mov     rdx, [rsp+190h+var_120]; struct WindowsUpdate::Internal::IInstallItem *
0x18012c0c1  mov     rcx, rbx; this
0x18012c0c4  call    ?FindOrCreateInstallItem@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@QEAAJPEAUIInstallItem@Internal@WindowsUpdate@@PEAPEAVAppInstallItem@23456@@Z; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::FindOrCreateInstallItem(WindowsUpdate::Internal::IInstallItem *,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem * *)
0x18012c0c9  mov     esi, eax
0x18012c0cb  test    eax, eax
0x18012c0cd  js      short loc_18012C0EA
0x18012c0cf  mov     rcx, [rbp+90h+var_F0]
0x18012c0d3  mov     rax, [rcx]
0x18012c0d6  mov     rdx, [rsp+190h+var_130]
0x18012c0db  mov     rax, [rax+68h]
0x18012c0df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012c0e4  mov     esi, eax
0x18012c0e6  test    eax, eax
0x18012c0e8  jns     short loc_18012C128
0x18012c0ea  mov     dword ptr [rsp+190h+var_150], r15d
0x18012c0ef  mov     [rsp+190h+var_158], r13; unsigned __int16 *
0x18012c0f4  mov     [rsp+190h+var_160], r13; char *
0x18012c0f9  lea     rax, aFailureTryingT; "Failure trying to query queued product."...
0x18012c100  mov     [rsp+190h+var_168], rax; unsigned __int16 *
0x18012c105  mov     [rsp+190h+var_170], esi; int
0x18012c109  lea     r9, aWindowsApplica_45; "Windows::ApplicationModel::Store::Previ"...
0x18012c110  mov     r8d, 361h; unsigned int
0x18012c116  lea     rdx, aOnecoreuapEndu_64; "onecoreuap\\enduser\\winstore\\installs"...
0x18012c11d  mov     ecx, 2; unsigned int
0x18012c122  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x18012c127  nop
0x18012c128  mov     rcx, [rsp+190h+string]; string
0x18012c12d  call    cs:__imp_WindowsDeleteString
0x18012c133  mov     [rsp+190h+string], r13
0x18012c138  lea     rcx, [rsp+190h+var_130]
0x18012c13d  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18012c142  nop
0x18012c143  lea     rcx, [rsp+190h+var_120]
0x18012c148  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18012c14d  inc     r15d
0x18012c150  cmp     r15d, [rsp+190h+var_140]
0x18012c155  jb      loc_18012C017
0x18012c15b  test    esi, esi
0x18012c15d  js      short loc_18012C179
0x18012c15f  mov     rcx, [rbp+90h+var_F0]
0x18012c163  mov     rax, [rcx]
0x18012c166  mov     rdx, r12
0x18012c169  mov     rax, [rax+40h]
0x18012c16d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012c172  mov     esi, eax
0x18012c174  jmp     short loc_18012C179
0x18012c176  xor     r13d, r13d
0x18012c179  mov     rcx, [rbp+90h+var_100]; string
0x18012c17d  call    cs:__imp_WindowsDeleteString
0x18012c183  mov     [rbp+90h+var_100], r13
0x18012c187  lea     rcx, [rbp+90h+var_F8]
0x18012c18b  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18012c190  nop
0x18012c191  lea     rcx, [rbp+90h+var_110]
0x18012c195  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18012c19a  nop
0x18012c19b  lea     rcx, [rsp+190h+var_128]
0x18012c1a0  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
  ... truncated ...
```
