# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Media::Internal::VolumeGroup,Windows::Foundation::Collections::Internal::AgileVector<Windows::Media::Internal::VolumeGroup *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Media::Internal::VolumeGroup *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Media::Internal::VolumeGroup *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Media::Internal::VolumeGroup *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Media::Internal::VolumeGroup *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Media::Internal::VolumeGroup *>,0> * *)

- ea: `0x18007416c`
- end: `0x1800743d9`
- name: `??$CreateExternalObjectVector@VVolumeGroup@Internal@Media@Windows@@V?$AgileVector@PEAVVolumeGroup@Internal@Media@Windows@@U?$DefaultEqualityPredicate@PEAVVolumeGroup@Internal@Media@Windows@@@2Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVVolumeGroup@Internal@Media@Windows@@@2674@$0A@@2Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVVolumeGroup@Internal@Media@Windows@@U?$DefaultEqualityPredicate@PEAVVolumeGroup@Internal@Media@Windows@@@2Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVVolumeGroup@Internal@Media@Windows@@@2674@$0A@@1234@@Z`
- size: `621`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180026860`

## callees

- `0x18000d11c`
- `0x18002b5d0`
- `0x18007416c`
- `0x180087e80`
- `0x1800eee20`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800741d4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007421b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180074262`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180074309`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800741d4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007421b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180074262`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180074309`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800741bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180074206`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007424d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800742f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800741bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180074206`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007424d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800742f3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180074320`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180074320`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Media::Internal::VolumeGroup,Windows::Foundation::Collections::Internal::AgileVector<Windows::Media::Internal::VolumeGroup *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Media::Internal::VolumeGroup *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Media::Internal::VolumeGroup *>,0>>(
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
  __int64 v17; // rax
  __int64 v18; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v19; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v20[3]; // [rsp+30h] [rbp-D0h] BYREF
  GUID v21; // [rsp+48h] [rbp-B8h]
  GUID v22; // [rsp+58h] [rbp-A8h]
  GUID v23; // [rsp+68h] [rbp-98h]
  GUID v24; // [rsp+78h] [rbp-88h]
  GUID v25; // [rsp+88h] [rbp-78h]
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING string; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING_HEADER v28; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING v29; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING_HEADER v30; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING v31; // [rsp+F8h] [rbp-8h] BYREF
  HSTRING_HEADER v32; // [rsp+100h] [rbp+0h] BYREF
  HSTRING v33; // [rsp+118h] [rbp+18h] BYREF

  string = 0;
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x4Cu);
  v4 = v3 - 1;
  if ( v3 > 0x4C )
    v4 = 76;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Media.Internal.VolumeGroup>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v29 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x50u);
  v7 = v6 - 1;
  if ( v6 > 0x50 )
    v7 = 80;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Media.Internal.VolumeGroup>",
         v7,
         &v28,
         &v29);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v31 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x4Eu);
  v10 = v9 - 1;
  if ( v9 > 0x4E )
    v10 = 78;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.Media.Internal.VolumeGroup>",
          v10,
          &v30,
          &v31);
  if ( v11 < 0 )
  {
    RaiseException(v11, 1u, 0, 0);
    __debugbreak();
  }
  v20[0] = string;
  v20[1] = v29;
  v20[2] = v31;
  v21 = GUID_87e10743_559f_4bc9_8485_c63bae763ab7;
  v22 = GUID_32bdfbb1_bd1f_5b43_b81e_d07b221f793c;
  v23 = GUID_731946f9_a5a0_5e21_bf18_217c0c5ff8fa;
  v24 = GUID_d92d3af6_eb14_5af5_a744_f32a2cc4296b;
  v25 = GUID_ecaea41e_14fb_51f2_9da5_c502ff6f3824;
  v18 = 0;
  Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v18);
  v33 = 0;
  v12 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v32, &v33);
  if ( v12 < 0 )
  {
    RaiseException(v12, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(v33, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v18);
  if ( ActivationFactory < 0 )
  {
    v14 = v18;
    if ( v18 )
    {
      v18 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    return (unsigned int)ActivationFactory;
  }
  v19 = 0;
  v16 = v18;
  Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v19);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}(v16, v20, &v19);
  if ( ActivationFactory < 0 )
  {
    Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v19);
    Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v18);
    return (unsigned int)ActivationFactory;
  }
  v17 = v19;
  v19 = 0;
  *a2 = v17;
  Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v19);
  Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v18);
  return 0;
}

```

## disassembly

```asm
0x18007416c  mov     [rsp-8+arg_0], rbx
0x180074171  mov     [rsp-8+arg_10], rdi
0x180074176  push    rbp
0x180074177  lea     rbp, [rsp-30h]
0x18007417c  sub     rsp, 130h
0x180074183  mov     rax, cs:__security_cookie
0x18007418a  xor     rax, rsp
0x18007418d  mov     [rbp+30h+var_10], rax
0x180074191  mov     rdi, rdx
0x180074194  mov     [rbp+30h+string], 0
0x18007419c  mov     ebx, 4Ch ; 'L'
0x1800741a1  mov     ecx, ebx; unsigned int
0x1800741a3  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800741a8  lea     edx, [rax-1]
0x1800741ab  cmp     eax, ebx
0x1800741ad  cmova   edx, ebx; length
0x1800741b0  lea     r9, [rbp+30h+string]; string
0x1800741b4  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x1800741b8  lea     rcx, aWindowsFoundat_5; "Windows.Foundation.Collections.IVector`"...
0x1800741bf  call    cs:__imp_WindowsCreateStringReference
0x1800741c5  test    eax, eax
0x1800741c7  jns     short loc_1800741DB
0x1800741c9  xor     r9d, r9d; lpArguments
0x1800741cc  xor     r8d, r8d; nNumberOfArguments
0x1800741cf  lea     edx, [rbx-4Bh]; dwExceptionFlags
0x1800741d2  mov     ecx, eax; dwExceptionCode
0x1800741d4  call    cs:__imp_RaiseException
0x1800741da  int     3; Trap to Debugger
0x1800741db  mov     [rbp+30h+var_58], 0
0x1800741e3  mov     ebx, 50h ; 'P'
0x1800741e8  mov     ecx, ebx; unsigned int
0x1800741ea  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800741ef  lea     edx, [rax-1]
0x1800741f2  cmp     eax, ebx
0x1800741f4  cmova   edx, ebx; length
0x1800741f7  lea     r9, [rbp+30h+var_58]; string
0x1800741fb  lea     r8, [rbp+30h+var_70]; hstringHeader
0x1800741ff  lea     rcx, aWindowsFoundat_7; "Windows.Foundation.Collections.IVectorV"...
0x180074206  call    cs:__imp_WindowsCreateStringReference
0x18007420c  test    eax, eax
0x18007420e  jns     short loc_180074222
0x180074210  xor     r9d, r9d; lpArguments
0x180074213  xor     r8d, r8d; nNumberOfArguments
0x180074216  lea     edx, [rbx-4Fh]; dwExceptionFlags
0x180074219  mov     ecx, eax; dwExceptionCode
0x18007421b  call    cs:__imp_RaiseException
0x180074221  int     3; Trap to Debugger
0x180074222  mov     [rbp+30h+var_38], 0
0x18007422a  mov     ebx, 4Eh ; 'N'
0x18007422f  mov     ecx, ebx; unsigned int
0x180074231  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180074236  lea     edx, [rax-1]
0x180074239  cmp     eax, ebx
0x18007423b  cmova   edx, ebx; length
0x18007423e  lea     r9, [rbp+30h+var_38]; string
0x180074242  lea     r8, [rbp+30h+var_50]; hstringHeader
0x180074246  lea     rcx, aWindowsFoundat_2; "Windows.Foundation.Collections.IIterato"...
0x18007424d  call    cs:__imp_WindowsCreateStringReference
0x180074253  test    eax, eax
0x180074255  jns     short loc_180074269
0x180074257  xor     r9d, r9d; lpArguments
0x18007425a  xor     r8d, r8d; nNumberOfArguments
0x18007425d  lea     edx, [rbx-4Dh]; dwExceptionFlags
0x180074260  mov     ecx, eax; dwExceptionCode
0x180074262  call    cs:__imp_RaiseException
0x180074268  int     3; Trap to Debugger
0x180074269  mov     rax, [rbp+30h+string]
0x18007426d  mov     [rsp+130h+var_100], rax
0x180074272  mov     rax, [rbp+30h+var_58]
0x180074276  mov     [rsp+130h+var_F8], rax
0x18007427b  mov     rax, [rbp+30h+var_38]
0x18007427f  mov     [rsp+130h+var_F0], rax
0x180074284  movups  xmm0, xmmword ptr cs:_GUID_87e10743_559f_4bc9_8485_c63bae763ab7.Data1
0x18007428b  movdqu  [rsp+130h+var_E8], xmm0
0x180074291  movups  xmm1, xmmword ptr cs:_GUID_32bdfbb1_bd1f_5b43_b81e_d07b221f793c.Data1
0x180074298  movdqu  [rsp+130h+var_D8], xmm1
0x18007429e  movups  xmm0, xmmword ptr cs:_GUID_731946f9_a5a0_5e21_bf18_217c0c5ff8fa.Data1
0x1800742a5  movdqu  [rsp+130h+var_C8], xmm0
0x1800742ab  movups  xmm1, xmmword ptr cs:_GUID_d92d3af6_eb14_5af5_a744_f32a2cc4296b.Data1
0x1800742b2  movdqu  [rsp+130h+var_B8], xmm1
0x1800742b8  movups  xmm0, xmmword ptr cs:_GUID_ecaea41e_14fb_51f2_9da5_c502ff6f3824.Data1
0x1800742bf  movdqu  [rbp+30h+var_A8], xmm0
0x1800742c4  mov     [rsp+130h+var_110], 0
0x1800742cd  lea     rcx, [rsp+130h+var_110]
0x1800742d2  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800742d7  mov     [rbp+30h+var_18], 0
0x1800742df  lea     r9, [rbp+30h+var_18]; string
0x1800742e3  lea     r8, [rbp+30h+var_30]; hstringHeader
0x1800742e7  mov     edx, 2Ch ; ','; length
0x1800742ec  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x1800742f3  call    cs:__imp_WindowsCreateStringReference
0x1800742f9  test    eax, eax
0x1800742fb  jns     short loc_180074310
0x1800742fd  xor     r9d, r9d; lpArguments
0x180074300  xor     r8d, r8d; nNumberOfArguments
0x180074303  lea     edx, [r9+1]; dwExceptionFlags
0x180074307  mov     ecx, eax; dwExceptionCode
0x180074309  call    cs:__imp_RaiseException
0x18007430f  int     3; Trap to Debugger
0x180074310  lea     r8, [rsp+130h+var_110]
0x180074315  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x18007431c  mov     rcx, [rbp+30h+var_18]
0x180074320  call    cs:__imp_RoGetActivationFactory
0x180074326  mov     ebx, eax
0x180074328  test    eax, eax
0x18007432a  jns     short loc_180074350
0x18007432c  mov     rcx, [rsp+130h+var_110]
0x180074331  test    rcx, rcx
0x180074334  jz      short loc_18007434C
0x180074336  mov     [rsp+130h+var_110], 0
0x18007433f  mov     rdx, [rcx]
0x180074342  mov     rax, [rdx+10h]
0x180074346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007434b  nop
0x18007434c  mov     eax, ebx
0x18007434e  jmp     short loc_1800743B8
0x180074350  mov     [rsp+130h+var_108], 0
0x180074359  mov     rbx, [rsp+130h+var_110]
0x18007435e  lea     rcx, [rsp+130h+var_108]
0x180074363  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x180074368  lea     r8, [rsp+130h+var_108]
0x18007436d  lea     rdx, [rsp+130h+var_100]
0x180074372  mov     rcx, rbx
0x180074375  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x18007437a  mov     ebx, eax
0x18007437c  lea     rcx, [rsp+130h+var_108]
0x180074381  test    eax, eax
0x180074383  jns     short loc_180074396
0x180074385  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x18007438a  lea     rcx, [rsp+130h+var_110]
0x18007438f  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x180074394  jmp     short loc_18007434C
0x180074396  mov     rax, [rsp+130h+var_108]
0x18007439b  mov     [rsp+130h+var_108], 0
0x1800743a4  mov     [rdi], rax
0x1800743a7  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800743ac  lea     rcx, [rsp+130h+var_110]
0x1800743b1  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800743b6  xor     eax, eax
0x1800743b8  mov     rcx, [rbp+30h+var_10]
0x1800743bc  xor     rcx, rsp; StackCookie
0x1800743bf  call    __security_check_cookie
0x1800743c4  lea     r11, [rsp+130h+var_s0]
0x1800743cc  mov     rbx, [r11+10h]
0x1800743d0  mov     rdi, [r11+20h]
0x1800743d4  mov     rsp, r11
0x1800743d7  pop     rbp
0x1800743d8  retn
```
