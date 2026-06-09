# Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::ResolveBubbleHeadsFromSMTPAliasAsync(HSTRING__ *,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Internal::UI::ApplicationSettings::BubbleHeadData *> *> * *)

- ea: `0x180015b70`
- end: `0x180015c5a`
- name: `?ResolveBubbleHeadsFromSMTPAliasAsync@AccountsControlBroker@ApplicationSettings@UI@Internal@Windows@@UEAAJPEAUHSTRING__@@PEAPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVBubbleHeadData@ApplicationSettings@UI@Internal@Windows@@@Collections@Foundation@Windows@@@Foundation@5@@Z`
- size: `234`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180006eac`
- `0x180009a40`
- `0x180009b18`
- `0x18000aa2c`
- `0x180011f88`
- `0x180012028`
- `0x180015b70`
- `0x1800165e4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015c1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015c31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015c1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015c31`

## string_xrefs

- `0x180015bc6`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::ResolveBubbleHeadsFromSMTPAliasAsync(
        __int64 a1,
        HSTRING a2,
        _QWORD *a3)
{
  int v3; // edi
  __int64 v4; // rsi
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rax
  __int64 v8; // rax
  int v9; // r9d
  int v11; // [rsp+20h] [rbp-50h]
  int v12; // [rsp+30h] [rbp-40h] BYREF
  __int64 v13; // [rsp+34h] [rbp-3Ch]
  HSTRING newString; // [rsp+40h] [rbp-30h] BYREF
  char v15; // [rsp+48h] [rbp-28h]
  _BYTE v16[8]; // [rsp+50h] [rbp-20h] BYREF
  HSTRING string; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  __int64 v19; // [rsp+90h] [rbp+20h] BYREF
  HSTRING v20; // [rsp+98h] [rbp+28h] BYREF

  v20 = a2;
  v3 = (int)a3;
  *a3 = 0;
  v4 = a1 - 16;
  v19 = a1 - 16;
  Microsoft::WRL::ComPtr<Windows::Internal::UI::ApplicationSettings::AccountsControlBroker>::InternalAddRef(&v19);
  newString = 0;
  v15 = 0;
  v5 = Microsoft::WRL::Wrappers::HString::Set(&newString, &v20);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v7 = lambda_5b81ec1d3f0d6906e5c37f74949de221_::_lambda_5b81ec1d3f0d6906e5c37f74949de221_(v16, v4, &newString);
    v12 = 3;
    v13 = 128;
    v8 = Windows::Internal::MakeOpLambda_0_Windows::Internal::CMarshaledInterfaceResult_Windows::Foundation::Collections::IVectorView_Windows::Internal::UI::ApplicationSettings::BubbleHeadData_______lambda_5b81ec1d3f0d6906e5c37f74949de221___(v7);
    v6 = Windows::Internal::MakeAsyncHelper<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Internal::UI::ApplicationSettings::BubbleHeadData *> *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Internal::UI::ApplicationSettings::BubbleHeadData *> *>,Windows::Internal::INilDelegate,Windows::Internal::CMarshaledInterfaceResult<Windows::Foundation::Collections::IVectorView<Windows::Internal::UI::ApplicationSettings::BubbleHeadData *>>,Windows::Internal::ComTaskPoolHandler,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(
           v3,
           (unsigned int)&v12,
           (unsigned int)L"Windows.Foundation.IAsyncOperation`1<Windows.Foundation.Collections.IVectorView`1<Windows.Inter"
                          "nal.UI.ApplicationSettings.BubbleHeadData>>",
           v9,
           v8);
    WindowsDeleteString(string);
    string = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F5,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
      (const char *)(unsigned int)v5,
      v11);
  }
  WindowsDeleteString(newString);
  newString = 0;
  Microsoft::WRL::ComPtr<Windows::Internal::UI::ApplicationSettings::AccountsControlBroker>::InternalRelease(&v19);
  return v6;
}

```

## disassembly

```asm
0x180015b70  mov     [rsp-18h+arg_10], rbx
0x180015b75  mov     [rsp-18h+arg_8], rdx
0x180015b7a  push    rbp
0x180015b7b  push    rsi
0x180015b7c  push    rdi
0x180015b7d  mov     rbp, rsp
0x180015b80  sub     rsp, 70h
0x180015b84  mov     rdi, r8
0x180015b87  mov     qword ptr [r8], 0
0x180015b8e  lea     rsi, [rcx-10h]
0x180015b92  mov     [rbp+arg_0], rsi
0x180015b96  lea     rcx, [rbp+arg_0]
0x180015b9a  call    ?InternalAddRef@?$ComPtr@VAccountsControlBroker@ApplicationSettings@UI@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::ApplicationSettings::AccountsControlBroker>::InternalAddRef(void)
0x180015b9f  nop
0x180015ba0  mov     [rbp+newString], 0
0x180015ba8  mov     [rbp+var_28], 0
0x180015bac  lea     rdx, [rbp+arg_8]; HSTRING *
0x180015bb0  lea     rcx, [rbp+newString]; newString
0x180015bb4  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180015bb9  mov     ebx, eax
0x180015bbb  test    eax, eax
0x180015bbd  jns     short loc_180015BD9
0x180015bbf  mov     rcx, [rbp+18h]; this
0x180015bc3  mov     r9d, eax; char *
0x180015bc6  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x180015bcd  mov     edx, 1F5h; void *
0x180015bd2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015bd7  jmp     short loc_180015C2D
0x180015bd9  lea     r8, [rbp+newString]
0x180015bdd  mov     rdx, rsi
0x180015be0  lea     rcx, [rbp+var_20]
0x180015be4  call    _lambda_5b81ec1d3f0d6906e5c37f74949de221____lambda_5b81ec1d3f0d6906e5c37f74949de221_
0x180015be9  nop
0x180015bea  mov     [rbp+var_40], 3
0x180015bf1  mov     [rbp+var_3C], 80h
0x180015bf9  mov     rcx, rax
0x180015bfc  call    Windows__Internal__MakeOpLambda_0_Windows__Internal__CMarshaledInterfaceResult_Windows__Foundation__Collections__IVectorView_Windows__Internal__UI__ApplicationSettings__BubbleHeadData_______lambda_5b81ec1d3f0d6906e5c37f74949de221___
0x180015c01  mov     qword ptr [rsp+70h+var_50], rax
0x180015c06  lea     r8, aWindowsFoundat_36; "Windows.Foundation.IAsyncOperation`1<Wi"...
0x180015c0d  lea     rdx, [rbp+var_40]
0x180015c11  mov     rcx, rdi
0x180015c14  call    ??$MakeAsyncHelper@U?$IAsyncOperation@PEAU?$IVectorView@PEAVBubbleHeadData@ApplicationSettings@UI@Internal@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVBubbleHeadData@ApplicationSettings@UI@Internal@Windows@@@Collections@Foundation@Windows@@@23@UINilDelegate@Internal@3@V?$CMarshaledInterfaceResult@U?$IVectorView@PEAVBubbleHeadData@ApplicationSettings@UI@Internal@Windows@@@Collections@Foundation@Windows@@@63@VComTaskPoolHandler@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@YAJPEAPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVBubbleHeadData@ApplicationSettings@UI@Internal@Windows@@@Collections@Foundation@Windows@@@Foundation@1@$$QEAVComTaskPoolHandler@01@QEBGW4TrustLevel@@PEAV?$AsyncCallbackBase@V?$CMarshaledInterfaceResult@U?$IVectorView@PEAVBubbleHeadData@ApplicationSettings@UI@Internal@Windows@@@Collections@Foundation@Windows@@@Internal@Windows@@@01@@Z; Windows::Internal::MakeAsyncHelper<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Internal::UI::ApplicationSettings::BubbleHeadData *> *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Internal::UI::ApplicationSettings::BubbleHeadData *> *>,Windows::Internal::INilDelegate,Windows::Internal::CMarshaledInterfaceResult<Windows::Foundation::Collections::IVectorView<Windows::Internal::UI::ApplicationSettings::BubbleHeadData *>>,Windows::Internal::ComTaskPoolHandler,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Internal::UI::ApplicationSettings::BubbleHeadData *> *> * *,Windows::Internal::ComTaskPoolHandler &&,ushort const * const,TrustLevel,Windows::Internal::AsyncCallbackBase<Windows::Internal::CMarshaledInterfaceResult<Windows::Foundation::Collections::IVectorView<Windows::Internal::UI::ApplicationSettings::BubbleHeadData *>>> *)
0x180015c19  mov     ebx, eax
0x180015c1b  mov     rcx, [rbp+string]; string
0x180015c1f  call    cs:__imp_WindowsDeleteString
0x180015c25  mov     [rbp+string], 0
0x180015c2d  mov     rcx, [rbp+newString]; string
0x180015c31  call    cs:__imp_WindowsDeleteString
0x180015c37  mov     [rbp+newString], 0
0x180015c3f  lea     rcx, [rbp+arg_0]
0x180015c43  call    ?InternalRelease@?$ComPtr@VAccountsControlBroker@ApplicationSettings@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::ApplicationSettings::AccountsControlBroker>::InternalRelease(void)
0x180015c48  mov     eax, ebx
0x180015c4a  mov     rbx, [rsp+70h+arg_10]
0x180015c52  add     rsp, 70h
0x180015c56  pop     rdi
0x180015c57  pop     rsi
0x180015c58  pop     rbp
0x180015c59  retn
```
