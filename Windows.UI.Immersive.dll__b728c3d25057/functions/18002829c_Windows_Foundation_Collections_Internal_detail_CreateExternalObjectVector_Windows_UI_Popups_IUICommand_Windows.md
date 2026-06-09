# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::UI::Popups::IUICommand,Windows::Foundation::Collections::Internal::Vector<Windows::UI::Popups::IUICommand *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Popups::IUICommand *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Popups::IUICommand *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::UI::Popups::IUICommand *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<Windows::UI::Popups::IUICommand *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Popups::IUICommand *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Popups::IUICommand *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::UI::Popups::IUICommand *>> * *)

- ea: `0x18002829c`
- end: `0x180028508`
- name: `??$CreateExternalObjectVector@UIUICommand@Popups@UI@Windows@@V?$Vector@PEAUIUICommand@Popups@UI@Windows@@U?$DefaultEqualityPredicate@PEAUIUICommand@Popups@UI@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAUIUICommand@Popups@UI@Windows@@@6784@U?$DefaultVectorOptions@PEAUIUICommand@Popups@UI@Windows@@@6784@@Internal@Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAUIUICommand@Popups@UI@Windows@@U?$DefaultEqualityPredicate@PEAUIUICommand@Popups@UI@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAUIUICommand@Popups@UI@Windows@@@6784@U?$DefaultVectorOptions@PEAUIUICommand@Popups@UI@Windows@@@6784@@1234@@Z`
- size: `620`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800281e4`
- `0x1800486f4`

## callees

- `0x180013244`
- `0x18002829c`
- `0x1800485b8`
- `0x180050ba0`
- `0x1800716e8`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180028304`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002834b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180028392`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180028439`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180028304`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002834b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180028392`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180028439`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800282ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180028336`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002837d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180028423`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800282ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180028336`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002837d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180028423`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180028450`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180028450`

## string_xrefs

- `0x180028370`: `Windows.Foundation.Collections.IIterator`1<Windows.UI.Popups.IUICommand>`
- `0x1800282e2`: `Windows.Foundation.Collections.IVector`1<Windows.UI.Popups.IUICommand>`
- `0x180028329`: `Windows.Foundation.Collections.IVectorView`1<Windows.UI.Popups.IUICommand>`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::UI::Popups::IUICommand,Windows::Foundation::Collections::Internal::Vector<Windows::UI::Popups::IUICommand *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Popups::IUICommand *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Popups::IUICommand *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::UI::Popups::IUICommand *>>>(
        __int64 a1,
        _QWORD *a2)
{
  unsigned int v3; // eax
  UINT32 v4; // edx
  HRESULT v5; // eax
  unsigned int v6; // eax
  UINT32 v7; // edx
  HRESULT v8; // eax
  unsigned int v9; // eax
  UINT32 v10; // edx
  HRESULT v11; // eax
  HRESULT v12; // eax
  int ActivationFactory; // ebx
  __int64 v14; // rcx
  __int64 v16; // rbx
  __int64 v17; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v18; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v19[3]; // [rsp+30h] [rbp-D0h] BYREF
  GUID v20; // [rsp+48h] [rbp-B8h]
  GUID v21; // [rsp+58h] [rbp-A8h]
  GUID v22; // [rsp+68h] [rbp-98h]
  GUID v23; // [rsp+78h] [rbp-88h]
  GUID v24; // [rsp+88h] [rbp-78h]
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING string; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING_HEADER v27; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING v28; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING_HEADER v29; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING v30; // [rsp+F8h] [rbp-8h] BYREF
  HSTRING_HEADER v31; // [rsp+100h] [rbp+0h] BYREF
  HSTRING v32; // [rsp+118h] [rbp+18h] BYREF

  string = 0;
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x46u);
  v4 = v3 - 1;
  if ( v3 > 0x46 )
    v4 = 70;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.UI.Popups.IUICommand>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v28 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x4Au);
  v7 = v6 - 1;
  if ( v6 > 0x4A )
    v7 = 74;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.UI.Popups.IUICommand>",
         v7,
         &v27,
         &v28);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v30 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x48u);
  v10 = v9 - 1;
  if ( v9 > 0x48 )
    v10 = 72;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.UI.Popups.IUICommand>",
          v10,
          &v29,
          &v30);
  if ( v11 < 0 )
  {
    RaiseException(v11, 1u, 0, 0);
    __debugbreak();
  }
  v19[0] = string;
  v20 = GUID_4ff93a75_4145_47ff_ac7f_dff1c1fa5b0f;
  v19[1] = v28;
  v21 = GUID_105139a1_dcb8_5f65_97ef_cb1bf0b75f9d;
  v19[2] = v30;
  v17 = 0;
  v22 = GUID_ed1165e6_f377_5b00_8172_93c1bd04deb4;
  v23 = GUID_e63de42b_53c3_5e07_90d3_98172d545412;
  v24 = GUID_f45db3d3_7299_57ce_a73e_297cf0af3083;
  Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v17);
  v32 = 0;
  v12 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v31, &v32);
  if ( v12 < 0 )
  {
    RaiseException(v12, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(v32, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v17);
  if ( ActivationFactory < 0 )
  {
    v14 = v17;
    if ( v17 )
    {
      v17 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    return (unsigned int)ActivationFactory;
  }
  v16 = v17;
  v18 = 0;
  Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v18);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{240,{flat}}(v16, v19, &v18);
  if ( ActivationFactory < 0 )
  {
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v18);
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v17);
    return (unsigned int)ActivationFactory;
  }
  *a2 = v18;
  v18 = 0;
  Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v18);
  Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v17);
  return 0;
}

```

## disassembly

```asm
0x18002829c  mov     [rsp-8+arg_0], rbx
0x1800282a1  mov     [rsp-8+arg_10], rdi
0x1800282a6  push    rbp
0x1800282a7  lea     rbp, [rsp-30h]
0x1800282ac  sub     rsp, 130h
0x1800282b3  mov     rax, cs:__security_cookie
0x1800282ba  xor     rax, rsp
0x1800282bd  mov     [rbp+30h+var_10], rax
0x1800282c1  mov     ebx, 46h ; 'F'
0x1800282c6  mov     [rbp+30h+string], 0
0x1800282ce  mov     ecx, ebx; unsigned int
0x1800282d0  mov     rdi, rdx
0x1800282d3  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800282d8  cmp     eax, ebx
0x1800282da  lea     r9, [rbp+30h+string]; string
0x1800282de  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x1800282e2  lea     rcx, aWindowsFoundat_4; "Windows.Foundation.Collections.IVector`"...
0x1800282e9  lea     edx, [rax-1]
0x1800282ec  cmova   edx, ebx; length
0x1800282ef  call    cs:__imp_WindowsCreateStringReference
0x1800282f5  test    eax, eax
0x1800282f7  jns     short loc_18002830B
0x1800282f9  xor     r9d, r9d; lpArguments
0x1800282fc  lea     edx, [rbx-45h]; dwExceptionFlags
0x1800282ff  xor     r8d, r8d; nNumberOfArguments
0x180028302  mov     ecx, eax; dwExceptionCode
0x180028304  call    cs:__imp_RaiseException
0x18002830a  int     3; Trap to Debugger
0x18002830b  mov     ebx, 4Ah ; 'J'
0x180028310  mov     [rbp+30h+var_58], 0
0x180028318  mov     ecx, ebx; unsigned int
0x18002831a  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18002831f  cmp     eax, ebx
0x180028321  lea     r9, [rbp+30h+var_58]; string
0x180028325  lea     r8, [rbp+30h+var_70]; hstringHeader
0x180028329  lea     rcx, aWindowsFoundat_11; "Windows.Foundation.Collections.IVectorV"...
0x180028330  lea     edx, [rax-1]
0x180028333  cmova   edx, ebx; length
0x180028336  call    cs:__imp_WindowsCreateStringReference
0x18002833c  test    eax, eax
0x18002833e  jns     short loc_180028352
0x180028340  xor     r9d, r9d; lpArguments
0x180028343  lea     edx, [rbx-49h]; dwExceptionFlags
0x180028346  xor     r8d, r8d; nNumberOfArguments
0x180028349  mov     ecx, eax; dwExceptionCode
0x18002834b  call    cs:__imp_RaiseException
0x180028351  int     3; Trap to Debugger
0x180028352  mov     ebx, 48h ; 'H'
0x180028357  mov     [rbp+30h+var_38], 0
0x18002835f  mov     ecx, ebx; unsigned int
0x180028361  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180028366  cmp     eax, ebx
0x180028368  lea     r9, [rbp+30h+var_38]; string
0x18002836c  lea     r8, [rbp+30h+var_50]; hstringHeader
0x180028370  lea     rcx, aWindowsFoundat; "Windows.Foundation.Collections.IIterato"...
0x180028377  lea     edx, [rax-1]
0x18002837a  cmova   edx, ebx; length
0x18002837d  call    cs:__imp_WindowsCreateStringReference
0x180028383  test    eax, eax
0x180028385  jns     short loc_180028399
0x180028387  xor     r9d, r9d; lpArguments
0x18002838a  lea     edx, [rbx-47h]; dwExceptionFlags
0x18002838d  xor     r8d, r8d; nNumberOfArguments
0x180028390  mov     ecx, eax; dwExceptionCode
0x180028392  call    cs:__imp_RaiseException
0x180028398  int     3; Trap to Debugger
0x180028399  movups  xmm0, xmmword ptr cs:_GUID_4ff93a75_4145_47ff_ac7f_dff1c1fa5b0f.Data1
0x1800283a0  mov     rax, [rbp+30h+string]
0x1800283a4  lea     rcx, [rsp+130h+var_110]
0x1800283a9  movups  xmm1, xmmword ptr cs:_GUID_105139a1_dcb8_5f65_97ef_cb1bf0b75f9d.Data1
0x1800283b0  mov     [rsp+130h+var_100], rax
0x1800283b5  mov     rax, [rbp+30h+var_58]
0x1800283b9  movdqu  [rsp+130h+var_E8], xmm0
0x1800283bf  mov     [rsp+130h+var_F8], rax
0x1800283c4  movups  xmm0, xmmword ptr cs:_GUID_ed1165e6_f377_5b00_8172_93c1bd04deb4.Data1
0x1800283cb  mov     rax, [rbp+30h+var_38]
0x1800283cf  movdqu  [rsp+130h+var_D8], xmm1
0x1800283d5  mov     [rsp+130h+var_F0], rax
0x1800283da  movups  xmm1, xmmword ptr cs:_GUID_e63de42b_53c3_5e07_90d3_98172d545412.Data1
0x1800283e1  mov     [rsp+130h+var_110], 0
0x1800283ea  movdqu  [rsp+130h+var_C8], xmm0
0x1800283f0  movups  xmm0, xmmword ptr cs:_GUID_f45db3d3_7299_57ce_a73e_297cf0af3083.Data1
0x1800283f7  movdqu  [rsp+130h+var_B8], xmm1
0x1800283fd  movdqu  [rbp+30h+var_A8], xmm0
0x180028402  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180028407  lea     r9, [rbp+30h+var_18]; string
0x18002840b  mov     [rbp+30h+var_18], 0
0x180028413  lea     r8, [rbp+30h+var_30]; hstringHeader
0x180028417  mov     edx, 2Ch ; ','; length
0x18002841c  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x180028423  call    cs:__imp_WindowsCreateStringReference
0x180028429  test    eax, eax
0x18002842b  jns     short loc_180028440
0x18002842d  xor     r9d, r9d; lpArguments
0x180028430  xor     r8d, r8d; nNumberOfArguments
0x180028433  mov     ecx, eax; dwExceptionCode
0x180028435  lea     edx, [r9+1]; dwExceptionFlags
0x180028439  call    cs:__imp_RaiseException
0x18002843f  int     3; Trap to Debugger
0x180028440  mov     rcx, [rbp+30h+var_18]
0x180028444  lea     r8, [rsp+130h+var_110]
0x180028449  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x180028450  call    cs:__imp_RoGetActivationFactory
0x180028456  mov     ebx, eax
0x180028458  test    eax, eax
0x18002845a  jns     short loc_18002847F
0x18002845c  mov     rcx, [rsp+130h+var_110]
0x180028461  test    rcx, rcx
0x180028464  jz      short loc_18002847B
0x180028466  mov     [rsp+130h+var_110], 0
0x18002846f  mov     rdx, [rcx]
0x180028472  mov     rax, [rdx+10h]
0x180028476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002847b  mov     eax, ebx
0x18002847d  jmp     short loc_1800284E7
0x18002847f  mov     rbx, [rsp+130h+var_110]
0x180028484  lea     rcx, [rsp+130h+var_108]
0x180028489  mov     [rsp+130h+var_108], 0
0x180028492  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180028497  lea     r8, [rsp+130h+var_108]
0x18002849c  mov     rcx, rbx
0x18002849f  lea     rdx, [rsp+130h+var_100]
0x1800284a4  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPA@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{240,{flat}}
0x1800284a9  lea     rcx, [rsp+130h+var_108]
0x1800284ae  mov     ebx, eax
0x1800284b0  test    eax, eax
0x1800284b2  jns     short loc_1800284C5
0x1800284b4  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800284b9  lea     rcx, [rsp+130h+var_110]
0x1800284be  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800284c3  jmp     short loc_18002847B
0x1800284c5  mov     rax, [rsp+130h+var_108]
0x1800284ca  mov     [rdi], rax
0x1800284cd  mov     [rsp+130h+var_108], 0
0x1800284d6  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800284db  lea     rcx, [rsp+130h+var_110]
0x1800284e0  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800284e5  xor     eax, eax
0x1800284e7  mov     rcx, [rbp+30h+var_10]
0x1800284eb  xor     rcx, rsp; StackCookie
0x1800284ee  call    __security_check_cookie
0x1800284f3  lea     r11, [rsp+130h+var_s0]
0x1800284fb  mov     rbx, [r11+10h]
0x1800284ff  mov     rdi, [r11+20h]
0x180028503  mov     rsp, r11
0x180028506  pop     rbp
0x180028507  retn
```
