# Windows::Graphics::Capture::Server::CapturableItemStatics::PickAsync(Windows::Internal::ApplicationModel::WindowManagement::WindowId,Windows::Foundation::IAsyncOperation<Windows::Graphics::Capture::Server::CapturableItem *> * *)

- ea: `0x180012f30`
- end: `0x180013108`
- name: `?PickAsync@CapturableItemStatics@Server@Capture@Graphics@Windows@@UEAAJUWindowId@WindowManagement@ApplicationModel@Internal@5@PEAPEAU?$IAsyncOperation@PEAVCapturableItem@Server@Capture@Graphics@Windows@@@Foundation@5@@Z`
- size: `472`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002e60`
- `0x18000907c`
- `0x18000c7ec`
- `0x18000cfc0`
- `0x18000d800`
- `0x18000ddc4`
- `0x18000f7b4`
- `0x180012444`
- `0x180012f30`
- `0x180015d0c`
- `0x180020000`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetObjectContext` at `0x180013059`
- `api-ms-win-core-com-l1-1-0!CoGetObjectContext` at `0x180013059`

## string_xrefs

- `0x180012f6b`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x180012fe6`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x180013027`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x18001306c`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x180012fce`: `onecoreuap\internal\shell\inc\platformextensiontools.h`

## pseudocode

```c
__int64 __fastcall Windows::Graphics::Capture::Server::CapturableItemStatics::PickAsync(
        Windows::Graphics::Capture::Server *a1,
        unsigned int a2,
        _QWORD *a3)
{
  int v5; // eax
  unsigned int v6; // edi
  int v7; // eax
  int v8; // eax
  HRESULT ObjectContext; // eax
  __int64 v10; // rax
  __int64 v11; // r8
  int v12; // ebx
  __int64 v14; // [rsp+20h] [rbp-50h] BYREF
  LPVOID ppv; // [rsp+28h] [rbp-48h] BYREF
  __int64 v16; // [rsp+30h] [rbp-40h] BYREF
  int v17; // [rsp+38h] [rbp-38h] BYREF
  __int64 v18; // [rsp+3Ch] [rbp-34h]
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  __int64 v20; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  *a3 = 0;
  v5 = Windows::Graphics::Capture::Server::CheckMDMPolicyAllowsCapture(a1);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v16 = 0;
    v20 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.CapturePickerExperience",
      0x29u,
      0x28u);
    v7 = Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(
           v20,
           a2,
           &GUID_c9c49885_46e5_423c_be32_4902cb8a76af,
           &v16);
    v6 = v7;
    if ( v7 >= 0 )
    {
      v14 = 0;
      v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v16 + 48LL))(v16, a2, &v14);
      v6 = v8;
      if ( v8 >= 0 )
      {
        ppv = 0;
        ObjectContext = CoGetObjectContext(&IID_IContextCallback, &ppv);
        v6 = ObjectContext;
        if ( ObjectContext >= 0 )
        {
          v10 = lambda_b505ef1f8418cadf1b666e845785b169_::_lambda_b505ef1f8418cadf1b666e845785b169_(
                  &hstringHeader,
                  &v16,
                  &v14,
                  &ppv);
          v17 = 0;
          v18 = 128;
          v12 = Windows::Internal::MakeAsyncOperation_Windows::Internal::CMarshaledInterfaceResult_Windows::Graphics::Capture::Server::ICapturableItem__Windows::Graphics::Capture::Server::CapturableItem___Windows::Internal::ComTaskPoolHandler__lambda_b505ef1f8418cadf1b666e845785b169___(
                  &v17,
                  a3,
                  v11,
                  v10);
          lambda_b505ef1f8418cadf1b666e845785b169_::__lambda_b505ef1f8418cadf1b666e845785b169_(&hstringHeader);
          Windows::Graphics::Capture::GraphicsCaptureProvider::LogPicker(v12);
          wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&ppv);
          wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v14);
          v6 = v12;
          goto LABEL_11;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2E8,
          (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
          (const char *)(unsigned int)ObjectContext,
          v14);
        wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&ppv);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2E4,
          (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
          (const char *)(unsigned int)v8,
          v14);
      }
      wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v14);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x299,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
        (const char *)(unsigned int)v7,
        v14);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2E0,
        (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
        (const char *)v6,
        v14);
    }
LABEL_11:
    wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v16);
    return v6;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2D8,
    (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
    (const char *)(unsigned int)v5,
    v14);
  return v6;
}

```

## disassembly

```asm
0x180012f30  mov     [rsp-18h+arg_0], rbx
0x180012f35  push    rbp
0x180012f36  push    rsi
0x180012f37  push    rdi
0x180012f38  mov     rbp, rsp
0x180012f3b  sub     rsp, 70h
0x180012f3f  mov     rax, cs:__security_cookie
0x180012f46  xor     rax, rsp
0x180012f49  mov     [rbp+var_8], rax
0x180012f4d  mov     rsi, r8
0x180012f50  mov     ebx, edx
0x180012f52  mov     qword ptr [r8], 0
0x180012f59  call    ?CheckMDMPolicyAllowsCapture@Server@Capture@Graphics@Windows@@YAJXZ; Windows::Graphics::Capture::Server::CheckMDMPolicyAllowsCapture(void)
0x180012f5e  mov     edi, eax
0x180012f60  test    eax, eax
0x180012f62  jns     short loc_180012F81
0x180012f64  mov     rcx, [rbp+18h]; this
0x180012f68  mov     r9d, eax; char *
0x180012f6b  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x180012f72  mov     edx, 2D8h; void *
0x180012f77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012f7c  jmp     loc_1800130EA
0x180012f81  mov     [rbp+var_40], 0
0x180012f89  mov     [rbp+var_10], 0
0x180012f91  mov     r9d, 28h ; '('; unsigned int
0x180012f97  lea     r8d, [r9+1]; unsigned int
0x180012f9b  lea     rdx, sourceString; "Windows.Internal.CapturePickerExperienc"...
0x180012fa2  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180012fa6  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180012fab  lea     r9, [rbp+var_40]
0x180012faf  lea     r8, _GUID_c9c49885_46e5_423c_be32_4902cb8a76af
0x180012fb6  mov     edx, ebx
0x180012fb8  mov     rcx, [rbp+var_10]
0x180012fbc  call    ?TryActivateContractExtensionInternal@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@34@AEBU_GUID@@PEAPEAX@Z; Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &,void * *)
0x180012fc1  mov     edi, eax
0x180012fc3  test    eax, eax
0x180012fc5  jns     short loc_180012FFC
0x180012fc7  mov     rcx, [rbp+18h]; this
0x180012fcb  mov     r9d, eax; char *
0x180012fce  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x180012fd5  mov     edx, 299h; void *
0x180012fda  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012fdf  mov     rcx, [rbp+18h]; this
0x180012fe3  mov     r9d, edi; char *
0x180012fe6  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x180012fed  mov     edx, 2E0h; void *
0x180012ff2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012ff7  jmp     loc_1800130E1
0x180012ffc  mov     [rbp+var_50], 0
0x180013004  mov     rcx, [rbp+var_40]
0x180013008  mov     rax, [rcx]
0x18001300b  lea     r8, [rbp+var_50]
0x18001300f  mov     edx, ebx
0x180013011  mov     rax, [rax+30h]
0x180013015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001301a  mov     edi, eax
0x18001301c  test    eax, eax
0x18001301e  jns     short loc_180013046
0x180013020  mov     rcx, [rbp+18h]; this
0x180013024  mov     r9d, eax; char *
0x180013027  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001302e  mov     edx, 2E4h; void *
0x180013033  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013038  lea     rcx, [rbp+var_50]
0x18001303c  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180013041  jmp     loc_1800130E1
0x180013046  mov     [rbp+ppv], 0
0x18001304e  lea     rdx, [rbp+ppv]; ppv
0x180013052  lea     rcx, IID_IContextCallback; riid
0x180013059  call    cs:__imp_CoGetObjectContext
0x18001305f  mov     edi, eax
0x180013061  test    eax, eax
0x180013063  jns     short loc_180013088
0x180013065  mov     rcx, [rbp+18h]; this
0x180013069  mov     r9d, eax; char *
0x18001306c  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x180013073  mov     edx, 2E8h; void *
0x180013078  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001307d  lea     rcx, [rbp+ppv]
0x180013081  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180013086  jmp     short loc_180013038
0x180013088  lea     r9, [rbp+ppv]
0x18001308c  lea     r8, [rbp+var_50]
0x180013090  lea     rdx, [rbp+var_40]
0x180013094  lea     rcx, [rbp+hstringHeader]
0x180013098  call    _lambda_b505ef1f8418cadf1b666e845785b169____lambda_b505ef1f8418cadf1b666e845785b169_
0x18001309d  mov     [rbp+var_38], 0
0x1800130a4  mov     [rbp+var_34], 80h
0x1800130ac  mov     r9, rax
0x1800130af  mov     rdx, rsi
0x1800130b2  lea     rcx, [rbp+var_38]
0x1800130b6  call    Windows__Internal__MakeAsyncOperation_Windows__Internal__CMarshaledInterfaceResult_Windows__Graphics__Capture__Server__ICapturableItem__Windows__Graphics__Capture__Server__CapturableItem___Windows__Internal__ComTaskPoolHandler__lambda_b505ef1f8418cadf1b666e845785b169___
0x1800130bb  mov     ebx, eax
0x1800130bd  lea     rcx, [rbp+hstringHeader]
0x1800130c1  call    _lambda_b505ef1f8418cadf1b666e845785b169_____lambda_b505ef1f8418cadf1b666e845785b169_
0x1800130c6  mov     ecx, ebx; int
0x1800130c8  call    ?LogPicker@GraphicsCaptureProvider@Capture@Graphics@Windows@@SAXJ@Z; Windows::Graphics::Capture::GraphicsCaptureProvider::LogPicker(long)
0x1800130cd  lea     rcx, [rbp+ppv]
0x1800130d1  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x1800130d6  lea     rcx, [rbp+var_50]
0x1800130da  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x1800130df  mov     edi, ebx
0x1800130e1  lea     rcx, [rbp+var_40]
0x1800130e5  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x1800130ea  mov     eax, edi
0x1800130ec  mov     rcx, [rbp+var_8]
0x1800130f0  xor     rcx, rsp; StackCookie
0x1800130f3  call    __security_check_cookie
0x1800130f8  mov     rbx, [rsp+70h+arg_0]
0x180013100  add     rsp, 70h
0x180013104  pop     rdi
0x180013105  pop     rsi
0x180013106  pop     rbp
0x180013107  retn
```
