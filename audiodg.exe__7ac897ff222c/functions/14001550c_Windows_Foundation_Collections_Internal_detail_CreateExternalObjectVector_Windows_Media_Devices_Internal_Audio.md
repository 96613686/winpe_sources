# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Media::Devices::Internal::AudioDeviceBrokerDevice,Windows::Foundation::Collections::Internal::Vector<Windows::Media::Devices::Internal::AudioDeviceBrokerDevice *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Media::Devices::Internal::AudioDeviceBrokerDevice *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Media::Devices::Internal::AudioDeviceBrokerDevice *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Media::Devices::Internal::AudioDeviceBrokerDevice *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<Windows::Media::Devices::Internal::AudioDeviceBrokerDevice *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Media::Devices::Internal::AudioDeviceBrokerDevice *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Media::Devices::Internal::AudioDeviceBrokerDevice *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Media::Devices::Internal::AudioDeviceBrokerDevice *>> * *)

- ea: `0x14001550c`
- end: `0x14001579a`
- name: `??$CreateExternalObjectVector@VAudioDeviceBrokerDevice@Internal@Devices@Media@Windows@@V?$Vector@PEAVAudioDeviceBrokerDevice@Internal@Devices@Media@Windows@@U?$DefaultEqualityPredicate@PEAVAudioDeviceBrokerDevice@Internal@Devices@Media@Windows@@@2Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVAudioDeviceBrokerDevice@Internal@Devices@Media@Windows@@@2785@U?$DefaultVectorOptions@PEAVAudioDeviceBrokerDevice@Internal@Devices@Media@Windows@@@2785@@2Collections@Foundation@5@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAVAudioDeviceBrokerDevice@Internal@Devices@Media@Windows@@U?$DefaultEqualityPredicate@PEAVAudioDeviceBrokerDevice@Internal@Devices@Media@Windows@@@2Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVAudioDeviceBrokerDevice@Internal@Devices@Media@Windows@@@2785@U?$DefaultVectorOptions@PEAVAudioDeviceBrokerDevice@Internal@Devices@Media@Windows@@@2785@@1234@@Z`
- size: `654`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140015244`

## callees

- `0x14001431c`
- `0x14001550c`
- `0x14005d0e0`
- `0x140086104`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14001572e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140015741`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140015754`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140015767`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14001572e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140015741`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140015754`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140015767`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140015550`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14001557a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400155a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14001563c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140015550`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14001557a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400155a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14001563c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14001565a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14001565a`

## string_xrefs

- `0x140015549`: `Windows.Foundation.Collections.IVector`1<Windows.Media.Devices.Internal.AudioDeviceBrokerDevice>`
- `0x140015573`: `Windows.Foundation.Collections.IVectorView`1<Windows.Media.Devices.Internal.AudioDeviceBrokerDevice>`
- `0x14001559d`: `Windows.Foundation.Collections.IIterator`1<Windows.Media.Devices.Internal.AudioDeviceBrokerDevice>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Media::Devices::Internal::AudioDeviceBrokerDevice,Windows::Foundation::Collections::Internal::Vector<Windows::Media::Devices::Internal::AudioDeviceBrokerDevice *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Media::Devices::Internal::AudioDeviceBrokerDevice *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Media::Devices::Internal::AudioDeviceBrokerDevice *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Media::Devices::Internal::AudioDeviceBrokerDevice *>>>(
        __int64 a1,
        _QWORD *a2)
{
  HRESULT v3; // eax
  HRESULT v4; // eax
  HRESULT v5; // eax
  HRESULT v6; // eax
  int ActivationFactory; // ebx
  __int64 v8; // rcx
  __int64 v10; // rbx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rax
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
         L"Windows.Foundation.Collections.IVector`1<Windows.Media.Devices.Internal.AudioDeviceBrokerDevice>",
         0x60u,
         &hstringHeader,
         &string);
  if ( v3 < 0 )
  {
    RaiseException(v3, 1u, 0, 0);
    __debugbreak();
  }
  v25 = 0;
  v4 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Media.Devices.Internal.AudioDeviceBrokerDevice>",
         0x64u,
         &v24,
         &v25);
  if ( v4 < 0 )
  {
    RaiseException(v4, 1u, 0, 0);
    __debugbreak();
  }
  v27 = 0;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IIterator`1<Windows.Media.Devices.Internal.AudioDeviceBrokerDevice>",
         0x62u,
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
  v17 = GUID_79cc8d75_9666_4c7d_90b9_56de0ec14239;
  v18 = GUID_c8b3e5b9_f098_5761_91d3_fe2593e0be27;
  v19 = GUID_6fbeabae_60e4_5839_b44e_5b46d4d85fa6;
  v20 = GUID_af4c50bf_f8e2_5d7e_a04c_d1dae1b23c36;
  v21 = GUID_1b52cd56_3a61_568f_973a_30a3e653fb18;
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
    v8 = v14;
    if ( v14 )
    {
      v14 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    return (unsigned int)ActivationFactory;
  }
  v15 = 0;
  v10 = v14;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{240,{flat}}(v10, v16, &v15);
  if ( ActivationFactory < 0 )
  {
    v11 = v15;
    if ( v15 )
    {
      v15 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    v12 = v14;
    if ( v14 )
    {
      v14 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    return (unsigned int)ActivationFactory;
  }
  v13 = v15;
  v15 = 0;
  *a2 = v13;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
  return 0;
}

```

## disassembly

```asm
0x14001550c  mov     [rsp-8+arg_0], rbx
0x140015511  mov     [rsp-8+arg_10], rdi
0x140015516  push    rbp
0x140015517  lea     rbp, [rsp-30h]
0x14001551c  sub     rsp, 130h
0x140015523  mov     rax, cs:__security_cookie
0x14001552a  xor     rax, rsp
0x14001552d  mov     [rbp+30h+var_10], rax
0x140015531  mov     rdi, rdx
0x140015534  mov     [rbp+30h+string], 0
0x14001553c  lea     r9, [rbp+30h+string]; string
0x140015540  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x140015544  mov     edx, 60h ; '`'; length
0x140015549  lea     rcx, sourceString; "Windows.Foundation.Collections.IVector`"...
0x140015550  call    cs:__imp_WindowsCreateStringReference
0x140015556  test    eax, eax
0x140015558  js      loc_140015722
0x14001555e  mov     [rbp+30h+var_58], 0
0x140015566  lea     r9, [rbp+30h+var_58]; string
0x14001556a  lea     r8, [rbp+30h+var_70]; hstringHeader
0x14001556e  mov     edx, 64h ; 'd'; length
0x140015573  lea     rcx, aWindowsFoundat_2; "Windows.Foundation.Collections.IVectorV"...
0x14001557a  call    cs:__imp_WindowsCreateStringReference
0x140015580  test    eax, eax
0x140015582  js      loc_140015735
0x140015588  mov     [rbp+30h+var_38], 0
0x140015590  lea     r9, [rbp+30h+var_38]; string
0x140015594  lea     r8, [rbp+30h+var_50]; hstringHeader
0x140015598  mov     edx, 62h ; 'b'; length
0x14001559d  lea     rcx, aWindowsFoundat_1; "Windows.Foundation.Collections.IIterato"...
0x1400155a4  call    cs:__imp_WindowsCreateStringReference
0x1400155aa  test    eax, eax
0x1400155ac  js      loc_140015748
0x1400155b2  mov     rax, [rbp+30h+string]
0x1400155b6  mov     [rsp+130h+var_100], rax
0x1400155bb  mov     rax, [rbp+30h+var_58]
0x1400155bf  mov     [rsp+130h+var_F8], rax
0x1400155c4  mov     rax, [rbp+30h+var_38]
0x1400155c8  mov     [rsp+130h+var_F0], rax
0x1400155cd  movups  xmm0, xmmword ptr cs:_GUID_79cc8d75_9666_4c7d_90b9_56de0ec14239.Data1
0x1400155d4  movdqu  [rsp+130h+var_E8], xmm0
0x1400155da  movups  xmm1, xmmword ptr cs:_GUID_c8b3e5b9_f098_5761_91d3_fe2593e0be27.Data1
0x1400155e1  movdqu  [rsp+130h+var_D8], xmm1
0x1400155e7  movups  xmm0, xmmword ptr cs:_GUID_6fbeabae_60e4_5839_b44e_5b46d4d85fa6.Data1
0x1400155ee  movdqu  [rsp+130h+var_C8], xmm0
0x1400155f4  movups  xmm1, xmmword ptr cs:_GUID_af4c50bf_f8e2_5d7e_a04c_d1dae1b23c36.Data1
0x1400155fb  movdqu  [rsp+130h+var_B8], xmm1
0x140015601  movups  xmm0, xmmword ptr cs:_GUID_1b52cd56_3a61_568f_973a_30a3e653fb18.Data1
0x140015608  movdqu  [rbp+30h+var_A8], xmm0
0x14001560d  mov     [rsp+130h+var_110], 0
0x140015616  lea     rcx, [rsp+130h+var_110]
0x14001561b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140015620  mov     [rbp+30h+var_18], 0
0x140015628  lea     r9, [rbp+30h+var_18]; string
0x14001562c  lea     r8, [rbp+30h+var_30]; hstringHeader
0x140015630  mov     edx, 2Ch ; ','; length
0x140015635  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x14001563c  call    cs:__imp_WindowsCreateStringReference
0x140015642  test    eax, eax
0x140015644  js      loc_14001575B
0x14001564a  lea     r8, [rsp+130h+var_110]
0x14001564f  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x140015656  mov     rcx, [rbp+30h+var_18]
0x14001565a  call    cs:__imp_RoGetActivationFactory
0x140015660  mov     ebx, eax
0x140015662  test    eax, eax
0x140015664  jns     short loc_1400156A9
0x140015666  mov     rcx, [rsp+130h+var_110]
0x14001566b  test    rcx, rcx
0x14001566e  jz      short loc_140015686
0x140015670  mov     [rsp+130h+var_110], 0
0x140015679  mov     rdx, [rcx]
0x14001567c  mov     rax, [rdx+10h]
0x140015680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015685  nop
0x140015686  mov     eax, ebx
0x140015688  mov     rcx, [rbp+30h+var_10]
0x14001568c  xor     rcx, rsp; StackCookie
0x14001568f  call    __security_check_cookie
0x140015694  lea     r11, [rsp+130h+var_s0]
0x14001569c  mov     rbx, [r11+10h]
0x1400156a0  mov     rdi, [r11+20h]
0x1400156a4  mov     rsp, r11
0x1400156a7  pop     rbp
0x1400156a8  retn
0x1400156a9  mov     [rsp+130h+var_108], 0
0x1400156b2  mov     rbx, [rsp+130h+var_110]
0x1400156b7  lea     rcx, [rsp+130h+var_108]
0x1400156bc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400156c1  lea     r8, [rsp+130h+var_108]
0x1400156c6  lea     rdx, [rsp+130h+var_100]
0x1400156cb  mov     rcx, rbx
0x1400156ce  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPA@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{240,{flat}}
0x1400156d3  mov     ebx, eax
0x1400156d5  test    eax, eax
0x1400156d7  jns     loc_14001576E
0x1400156dd  mov     rcx, [rsp+130h+var_108]
0x1400156e2  test    rcx, rcx
0x1400156e5  jz      short loc_1400156FD
0x1400156e7  mov     [rsp+130h+var_108], 0
0x1400156f0  mov     rdx, [rcx]
0x1400156f3  mov     rax, [rdx+10h]
0x1400156f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400156fc  nop
0x1400156fd  mov     rcx, [rsp+130h+var_110]
0x140015702  test    rcx, rcx
0x140015705  jz      short loc_14001571D
0x140015707  mov     [rsp+130h+var_110], 0
0x140015710  mov     rax, [rcx]
0x140015713  mov     rax, [rax+10h]
0x140015717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001571c  nop
0x14001571d  jmp     loc_140015686
0x140015722  xor     r9d, r9d; lpArguments
0x140015725  xor     r8d, r8d; nNumberOfArguments
0x140015728  lea     edx, [r9+1]; dwExceptionFlags
0x14001572c  mov     ecx, eax; dwExceptionCode
0x14001572e  call    cs:__imp_RaiseException
0x140015734  int     3; Trap to Debugger
0x140015735  xor     r9d, r9d; lpArguments
0x140015738  xor     r8d, r8d; nNumberOfArguments
0x14001573b  lea     edx, [r9+1]; dwExceptionFlags
0x14001573f  mov     ecx, eax; dwExceptionCode
0x140015741  call    cs:__imp_RaiseException
0x140015747  int     3; Trap to Debugger
0x140015748  xor     r9d, r9d; lpArguments
0x14001574b  xor     r8d, r8d; nNumberOfArguments
0x14001574e  lea     edx, [r9+1]; dwExceptionFlags
0x140015752  mov     ecx, eax; dwExceptionCode
0x140015754  call    cs:__imp_RaiseException
0x14001575a  int     3; Trap to Debugger
0x14001575b  xor     r9d, r9d; lpArguments
0x14001575e  xor     r8d, r8d; nNumberOfArguments
0x140015761  lea     edx, [r9+1]; dwExceptionFlags
0x140015765  mov     ecx, eax; dwExceptionCode
0x140015767  call    cs:__imp_RaiseException
0x14001576d  int     3; Trap to Debugger
0x14001576e  mov     rax, [rsp+130h+var_108]
0x140015773  mov     [rsp+130h+var_108], 0
0x14001577c  mov     [rdi], rax
0x14001577f  lea     rcx, [rsp+130h+var_108]
0x140015784  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140015789  lea     rcx, [rsp+130h+var_110]
0x14001578e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140015793  xor     eax, eax
0x140015795  jmp     loc_140015688
```
