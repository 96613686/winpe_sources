# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Media::Devices::AudioDeviceModule,Windows::Foundation::Collections::Internal::Vector<Windows::Media::Devices::AudioDeviceModule *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Media::Devices::AudioDeviceModule *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Media::Devices::AudioDeviceModule *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Media::Devices::AudioDeviceModule *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<Windows::Media::Devices::AudioDeviceModule *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Media::Devices::AudioDeviceModule *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Media::Devices::AudioDeviceModule *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Media::Devices::AudioDeviceModule *>> * *)

- ea: `0x1400157a0`
- end: `0x140015a21`
- name: `??$CreateExternalObjectVector@VAudioDeviceModule@Devices@Media@Windows@@V?$Vector@PEAVAudioDeviceModule@Devices@Media@Windows@@U?$DefaultEqualityPredicate@PEAVAudioDeviceModule@Devices@Media@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVAudioDeviceModule@Devices@Media@Windows@@@6784@U?$DefaultVectorOptions@PEAVAudioDeviceModule@Devices@Media@Windows@@@6784@@Internal@Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAVAudioDeviceModule@Devices@Media@Windows@@U?$DefaultEqualityPredicate@PEAVAudioDeviceModule@Devices@Media@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVAudioDeviceModule@Devices@Media@Windows@@@6784@U?$DefaultVectorOptions@PEAVAudioDeviceModule@Devices@Media@Windows@@@6784@@1234@@Z`
- size: `641`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140014a30`
- `0x140086f50`
- `0x140087134`

## callees

- `0x14001431c`
- `0x1400157a0`
- `0x14005d0e0`
- `0x140086104`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1400159d2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1400159e5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1400159f8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140015a0b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1400159d2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1400159e5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1400159f8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140015a0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400157e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14001580e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140015838`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400158d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400157e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14001580e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140015838`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400158d0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1400158ee`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1400158ee`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Media::Devices::AudioDeviceModule,Windows::Foundation::Collections::Internal::Vector<Windows::Media::Devices::AudioDeviceModule *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Media::Devices::AudioDeviceModule *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Media::Devices::AudioDeviceModule *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Media::Devices::AudioDeviceModule *>>>(
        __int64 a1,
        _QWORD *a2)
{
  HRESULT v3; // eax
  HRESULT v4; // eax
  HRESULT v5; // eax
  HRESULT v6; // eax
  int ActivationFactory; // ebx
  __int64 v8; // rbx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v15; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v16[3]; // [rsp+30h] [rbp-D0h] BYREF
  GUID v17; // [rsp+48h] [rbp-B8h]
  GUID v18; // [rsp+58h] [rbp-A8h]
  GUID v19; // [rsp+68h] [rbp-98h]
  GUID v20; // [rsp+78h] [rbp-88h]
  GUID v21; // [rsp+88h] [rbp-78h]
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING string; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING_HEADER v24; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING v25; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING_HEADER v26; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING v27; // [rsp+F8h] [rbp-8h] BYREF
  HSTRING_HEADER v28; // [rsp+100h] [rbp+0h] BYREF
  HSTRING v29; // [rsp+118h] [rbp+18h] BYREF

  string = 0;
  v3 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Media.Devices.AudioDeviceModule>",
         0x51u,
         &hstringHeader,
         &string);
  if ( v3 < 0 )
  {
    RaiseException(v3, 1u, 0, 0);
    __debugbreak();
  }
  v25 = 0;
  v4 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Media.Devices.AudioDeviceModule>",
         0x55u,
         &v24,
         &v25);
  if ( v4 < 0 )
  {
    RaiseException(v4, 1u, 0, 0);
    __debugbreak();
  }
  v27 = 0;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IIterator`1<Windows.Media.Devices.AudioDeviceModule>",
         0x53u,
         &v26,
         &v27);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v16[0] = string;
  v16[1] = v25;
  v16[2] = v27;
  v17 = GUID_86cfac36_47c1_4b33_9852_8773ec4be123;
  v18 = GUID_325cb078_f603_522b_8afe_04b0bfcfa0e9;
  v19 = GUID_b9f55617_48ec_5ad7_95ca_33395284f28b;
  v20 = GUID_7eeb51c3_d70e_548a_85c2_3cf71b4a124c;
  v21 = GUID_b4cbbfb7_9851_56c9_839d_a10a8b1bb234;
  v14 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
  v29 = 0;
  v6 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v28, &v29);
  if ( v6 < 0 )
  {
    RaiseException(v6, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(v29, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v14);
  if ( ActivationFactory < 0 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
    return (unsigned int)ActivationFactory;
  }
  v15 = 0;
  v8 = v14;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{240,{flat}}(v8, v16, &v15);
  if ( ActivationFactory < 0 )
  {
    v9 = v15;
    if ( v15 )
    {
      v15 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    v10 = v14;
    if ( v14 )
    {
      v14 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    return (unsigned int)ActivationFactory;
  }
  v12 = v15;
  v15 = 0;
  *a2 = v12;
  v13 = v14;
  if ( v14 )
  {
    v14 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  return 0;
}

```

## disassembly

```asm
0x1400157a0  mov     [rsp-8+arg_0], rbx
0x1400157a5  mov     [rsp-8+arg_10], rdi
0x1400157aa  push    rbp
0x1400157ab  lea     rbp, [rsp-30h]
0x1400157b0  sub     rsp, 130h
0x1400157b7  mov     rax, cs:__security_cookie
0x1400157be  xor     rax, rsp
0x1400157c1  mov     [rbp+30h+var_10], rax
0x1400157c5  mov     rdi, rdx
0x1400157c8  mov     [rbp+30h+string], 0
0x1400157d0  lea     r9, [rbp+30h+string]; string
0x1400157d4  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x1400157d8  mov     edx, 51h ; 'Q'; length
0x1400157dd  lea     rcx, aWindowsFoundat_5; "Windows.Foundation.Collections.IVector`"...
0x1400157e4  call    cs:__imp_WindowsCreateStringReference
0x1400157ea  test    eax, eax
0x1400157ec  js      loc_1400159C6
0x1400157f2  mov     [rbp+30h+var_58], 0
0x1400157fa  lea     r9, [rbp+30h+var_58]; string
0x1400157fe  lea     r8, [rbp+30h+var_70]; hstringHeader
0x140015802  mov     edx, 55h ; 'U'; length
0x140015807  lea     rcx, aWindowsFoundat; "Windows.Foundation.Collections.IVectorV"...
0x14001580e  call    cs:__imp_WindowsCreateStringReference
0x140015814  test    eax, eax
0x140015816  js      loc_1400159D9
0x14001581c  mov     [rbp+30h+var_38], 0
0x140015824  lea     r9, [rbp+30h+var_38]; string
0x140015828  lea     r8, [rbp+30h+var_50]; hstringHeader
0x14001582c  mov     edx, 53h ; 'S'; length
0x140015831  lea     rcx, aWindowsFoundat_10; "Windows.Foundation.Collections.IIterato"...
0x140015838  call    cs:__imp_WindowsCreateStringReference
0x14001583e  test    eax, eax
0x140015840  js      loc_1400159EC
0x140015846  mov     rax, [rbp+30h+string]
0x14001584a  mov     [rsp+130h+var_100], rax
0x14001584f  mov     rax, [rbp+30h+var_58]
0x140015853  mov     [rsp+130h+var_F8], rax
0x140015858  mov     rax, [rbp+30h+var_38]
0x14001585c  mov     [rsp+130h+var_F0], rax
0x140015861  movups  xmm0, xmmword ptr cs:_GUID_86cfac36_47c1_4b33_9852_8773ec4be123.Data1
0x140015868  movdqu  [rsp+130h+var_E8], xmm0
0x14001586e  movups  xmm1, xmmword ptr cs:_GUID_325cb078_f603_522b_8afe_04b0bfcfa0e9.Data1
0x140015875  movdqu  [rsp+130h+var_D8], xmm1
0x14001587b  movups  xmm0, xmmword ptr cs:_GUID_b9f55617_48ec_5ad7_95ca_33395284f28b.Data1
0x140015882  movdqu  [rsp+130h+var_C8], xmm0
0x140015888  movups  xmm1, xmmword ptr cs:_GUID_7eeb51c3_d70e_548a_85c2_3cf71b4a124c.Data1
0x14001588f  movdqu  [rsp+130h+var_B8], xmm1
0x140015895  movups  xmm0, xmmword ptr cs:_GUID_b4cbbfb7_9851_56c9_839d_a10a8b1bb234.Data1
0x14001589c  movdqu  [rbp+30h+var_A8], xmm0
0x1400158a1  mov     [rsp+130h+var_110], 0
0x1400158aa  lea     rcx, [rsp+130h+var_110]
0x1400158af  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400158b4  mov     [rbp+30h+var_18], 0
0x1400158bc  lea     r9, [rbp+30h+var_18]; string
0x1400158c0  lea     r8, [rbp+30h+var_30]; hstringHeader
0x1400158c4  mov     edx, 2Ch ; ','; length
0x1400158c9  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x1400158d0  call    cs:__imp_WindowsCreateStringReference
0x1400158d6  test    eax, eax
0x1400158d8  js      loc_1400159FF
0x1400158de  lea     r8, [rsp+130h+var_110]
0x1400158e3  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x1400158ea  mov     rcx, [rbp+30h+var_18]
0x1400158ee  call    cs:__imp_RoGetActivationFactory
0x1400158f4  mov     ebx, eax
0x1400158f6  test    eax, eax
0x1400158f8  js      loc_140015A12
0x1400158fe  mov     [rsp+130h+var_108], 0
0x140015907  mov     rbx, [rsp+130h+var_110]
0x14001590c  lea     rcx, [rsp+130h+var_108]
0x140015911  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140015916  lea     r8, [rsp+130h+var_108]
0x14001591b  lea     rdx, [rsp+130h+var_100]
0x140015920  mov     rcx, rbx
0x140015923  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPA@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{240,{flat}}
0x140015928  mov     ebx, eax
0x14001592a  test    eax, eax
0x14001592c  jns     short loc_140015991
0x14001592e  mov     rcx, [rsp+130h+var_108]
0x140015933  test    rcx, rcx
0x140015936  jz      short loc_14001594E
0x140015938  mov     [rsp+130h+var_108], 0
0x140015941  mov     rdx, [rcx]
0x140015944  mov     rax, [rdx+10h]
0x140015948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001594d  nop
0x14001594e  mov     rcx, [rsp+130h+var_110]
0x140015953  test    rcx, rcx
0x140015956  jz      short loc_14001596E
0x140015958  mov     [rsp+130h+var_110], 0
0x140015961  mov     rax, [rcx]
0x140015964  mov     rax, [rax+10h]
0x140015968  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001596d  nop
0x14001596e  mov     eax, ebx
0x140015970  mov     rcx, [rbp+30h+var_10]
0x140015974  xor     rcx, rsp; StackCookie
0x140015977  call    __security_check_cookie
0x14001597c  lea     r11, [rsp+130h+var_s0]
0x140015984  mov     rbx, [r11+10h]
0x140015988  mov     rdi, [r11+20h]
0x14001598c  mov     rsp, r11
0x14001598f  pop     rbp
0x140015990  retn
0x140015991  mov     rax, [rsp+130h+var_108]
0x140015996  mov     [rsp+130h+var_108], 0
0x14001599f  mov     [rdi], rax
0x1400159a2  mov     rcx, [rsp+130h+var_110]
0x1400159a7  test    rcx, rcx
0x1400159aa  jz      short loc_1400159C2
0x1400159ac  mov     [rsp+130h+var_110], 0
0x1400159b5  mov     rax, [rcx]
0x1400159b8  mov     rax, [rax+10h]
0x1400159bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400159c1  nop
0x1400159c2  xor     eax, eax
0x1400159c4  jmp     short loc_140015970
0x1400159c6  xor     r9d, r9d; lpArguments
0x1400159c9  xor     r8d, r8d; nNumberOfArguments
0x1400159cc  lea     edx, [r9+1]; dwExceptionFlags
0x1400159d0  mov     ecx, eax; dwExceptionCode
0x1400159d2  call    cs:__imp_RaiseException
0x1400159d8  int     3; Trap to Debugger
0x1400159d9  xor     r9d, r9d; lpArguments
0x1400159dc  xor     r8d, r8d; nNumberOfArguments
0x1400159df  lea     edx, [r9+1]; dwExceptionFlags
0x1400159e3  mov     ecx, eax; dwExceptionCode
0x1400159e5  call    cs:__imp_RaiseException
0x1400159eb  int     3; Trap to Debugger
0x1400159ec  xor     r9d, r9d; lpArguments
0x1400159ef  xor     r8d, r8d; nNumberOfArguments
0x1400159f2  lea     edx, [r9+1]; dwExceptionFlags
0x1400159f6  mov     ecx, eax; dwExceptionCode
0x1400159f8  call    cs:__imp_RaiseException
0x1400159fe  int     3; Trap to Debugger
0x1400159ff  xor     r9d, r9d; lpArguments
0x140015a02  xor     r8d, r8d; nNumberOfArguments
0x140015a05  lea     edx, [r9+1]; dwExceptionFlags
0x140015a09  mov     ecx, eax; dwExceptionCode
0x140015a0b  call    cs:__imp_RaiseException
0x140015a11  int     3; Trap to Debugger
0x140015a12  lea     rcx, [rsp+130h+var_110]
0x140015a17  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140015a1c  jmp     loc_14001596E
```
