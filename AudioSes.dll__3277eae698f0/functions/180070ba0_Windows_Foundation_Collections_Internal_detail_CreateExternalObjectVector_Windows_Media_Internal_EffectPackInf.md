# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Media::Internal::EffectPackInfo,Windows::Foundation::Collections::Internal::AgileVector<Windows::Media::Internal::EffectPackInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Media::Internal::EffectPackInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Media::Internal::EffectPackInfo *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Media::Internal::EffectPackInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Media::Internal::EffectPackInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Media::Internal::EffectPackInfo *>,0> * *)

- ea: `0x180070ba0`
- end: `0x180070e0d`
- name: `??$CreateExternalObjectVector@VEffectPackInfo@Internal@Media@Windows@@V?$AgileVector@PEAVEffectPackInfo@Internal@Media@Windows@@U?$DefaultEqualityPredicate@PEAVEffectPackInfo@Internal@Media@Windows@@@2Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVEffectPackInfo@Internal@Media@Windows@@@2674@$0A@@2Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVEffectPackInfo@Internal@Media@Windows@@U?$DefaultEqualityPredicate@PEAVEffectPackInfo@Internal@Media@Windows@@@2Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVEffectPackInfo@Internal@Media@Windows@@@2674@$0A@@1234@@Z`
- size: `621`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002a5b0`

## callees

- `0x18000d11c`
- `0x18002b5d0`
- `0x180070ba0`
- `0x180087e80`
- `0x1800eee20`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180070c08`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180070c4f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180070c96`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180070d3d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180070c08`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180070c4f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180070c96`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180070d3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180070bf3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180070c3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180070c81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180070d27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180070bf3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180070c3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180070c81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180070d27`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180070d54`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180070d54`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Media::Internal::EffectPackInfo,Windows::Foundation::Collections::Internal::AgileVector<Windows::Media::Internal::EffectPackInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Media::Internal::EffectPackInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Media::Internal::EffectPackInfo *>,0>>(
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
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x4Fu);
  v4 = v3 - 1;
  if ( v3 > 0x4F )
    v4 = 79;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Media.Internal.EffectPackInfo>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v29 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x53u);
  v7 = v6 - 1;
  if ( v6 > 0x53 )
    v7 = 83;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Media.Internal.EffectPackInfo>",
         v7,
         &v28,
         &v29);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v31 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x51u);
  v10 = v9 - 1;
  if ( v9 > 0x51 )
    v10 = 81;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.Media.Internal.EffectPackInfo>",
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
  v21 = GUID_05684a57_09e3_43db_a870_70f825122c68;
  v22 = GUID_9bbff5c3_da8d_5c50_8f74_42362ba79a68;
  v23 = GUID_d2f60f55_3fed_5eb8_a76e_02f0250ef6b7;
  v24 = GUID_a0d2a394_6055_58c3_b920_ac9e66de02ec;
  v25 = GUID_fdda77ce_6f90_5fec_b3b2_db6fe305081c;
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
0x180070ba0  mov     [rsp-8+arg_0], rbx
0x180070ba5  mov     [rsp-8+arg_10], rdi
0x180070baa  push    rbp
0x180070bab  lea     rbp, [rsp-30h]
0x180070bb0  sub     rsp, 130h
0x180070bb7  mov     rax, cs:__security_cookie
0x180070bbe  xor     rax, rsp
0x180070bc1  mov     [rbp+30h+var_10], rax
0x180070bc5  mov     rdi, rdx
0x180070bc8  mov     [rbp+30h+string], 0
0x180070bd0  mov     ebx, 4Fh ; 'O'
0x180070bd5  mov     ecx, ebx; unsigned int
0x180070bd7  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180070bdc  lea     edx, [rax-1]
0x180070bdf  cmp     eax, ebx
0x180070be1  cmova   edx, ebx; length
0x180070be4  lea     r9, [rbp+30h+string]; string
0x180070be8  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x180070bec  lea     rcx, aWindowsFoundat_3; "Windows.Foundation.Collections.IVector`"...
0x180070bf3  call    cs:__imp_WindowsCreateStringReference
0x180070bf9  test    eax, eax
0x180070bfb  jns     short loc_180070C0F
0x180070bfd  xor     r9d, r9d; lpArguments
0x180070c00  xor     r8d, r8d; nNumberOfArguments
0x180070c03  lea     edx, [rbx-4Eh]; dwExceptionFlags
0x180070c06  mov     ecx, eax; dwExceptionCode
0x180070c08  call    cs:__imp_RaiseException
0x180070c0e  int     3; Trap to Debugger
0x180070c0f  mov     [rbp+30h+var_58], 0
0x180070c17  mov     ebx, 53h ; 'S'
0x180070c1c  mov     ecx, ebx; unsigned int
0x180070c1e  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180070c23  lea     edx, [rax-1]
0x180070c26  cmp     eax, ebx
0x180070c28  cmova   edx, ebx; length
0x180070c2b  lea     r9, [rbp+30h+var_58]; string
0x180070c2f  lea     r8, [rbp+30h+var_70]; hstringHeader
0x180070c33  lea     rcx, aWindowsFoundat_6; "Windows.Foundation.Collections.IVectorV"...
0x180070c3a  call    cs:__imp_WindowsCreateStringReference
0x180070c40  test    eax, eax
0x180070c42  jns     short loc_180070C56
0x180070c44  xor     r9d, r9d; lpArguments
0x180070c47  xor     r8d, r8d; nNumberOfArguments
0x180070c4a  lea     edx, [rbx-52h]; dwExceptionFlags
0x180070c4d  mov     ecx, eax; dwExceptionCode
0x180070c4f  call    cs:__imp_RaiseException
0x180070c55  int     3; Trap to Debugger
0x180070c56  mov     [rbp+30h+var_38], 0
0x180070c5e  mov     ebx, 51h ; 'Q'
0x180070c63  mov     ecx, ebx; unsigned int
0x180070c65  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180070c6a  lea     edx, [rax-1]
0x180070c6d  cmp     eax, ebx
0x180070c6f  cmova   edx, ebx; length
0x180070c72  lea     r9, [rbp+30h+var_38]; string
0x180070c76  lea     r8, [rbp+30h+var_50]; hstringHeader
0x180070c7a  lea     rcx, aWindowsFoundat_16; "Windows.Foundation.Collections.IIterato"...
0x180070c81  call    cs:__imp_WindowsCreateStringReference
0x180070c87  test    eax, eax
0x180070c89  jns     short loc_180070C9D
0x180070c8b  xor     r9d, r9d; lpArguments
0x180070c8e  xor     r8d, r8d; nNumberOfArguments
0x180070c91  lea     edx, [rbx-50h]; dwExceptionFlags
0x180070c94  mov     ecx, eax; dwExceptionCode
0x180070c96  call    cs:__imp_RaiseException
0x180070c9c  int     3; Trap to Debugger
0x180070c9d  mov     rax, [rbp+30h+string]
0x180070ca1  mov     [rsp+130h+var_100], rax
0x180070ca6  mov     rax, [rbp+30h+var_58]
0x180070caa  mov     [rsp+130h+var_F8], rax
0x180070caf  mov     rax, [rbp+30h+var_38]
0x180070cb3  mov     [rsp+130h+var_F0], rax
0x180070cb8  movups  xmm0, xmmword ptr cs:_GUID_05684a57_09e3_43db_a870_70f825122c68.Data1
0x180070cbf  movdqu  [rsp+130h+var_E8], xmm0
0x180070cc5  movups  xmm1, xmmword ptr cs:_GUID_9bbff5c3_da8d_5c50_8f74_42362ba79a68.Data1
0x180070ccc  movdqu  [rsp+130h+var_D8], xmm1
0x180070cd2  movups  xmm0, xmmword ptr cs:_GUID_d2f60f55_3fed_5eb8_a76e_02f0250ef6b7.Data1
0x180070cd9  movdqu  [rsp+130h+var_C8], xmm0
0x180070cdf  movups  xmm1, xmmword ptr cs:_GUID_a0d2a394_6055_58c3_b920_ac9e66de02ec.Data1
0x180070ce6  movdqu  [rsp+130h+var_B8], xmm1
0x180070cec  movups  xmm0, xmmword ptr cs:_GUID_fdda77ce_6f90_5fec_b3b2_db6fe305081c.Data1
0x180070cf3  movdqu  [rbp+30h+var_A8], xmm0
0x180070cf8  mov     [rsp+130h+var_110], 0
0x180070d01  lea     rcx, [rsp+130h+var_110]
0x180070d06  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x180070d0b  mov     [rbp+30h+var_18], 0
0x180070d13  lea     r9, [rbp+30h+var_18]; string
0x180070d17  lea     r8, [rbp+30h+var_30]; hstringHeader
0x180070d1b  mov     edx, 2Ch ; ','; length
0x180070d20  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x180070d27  call    cs:__imp_WindowsCreateStringReference
0x180070d2d  test    eax, eax
0x180070d2f  jns     short loc_180070D44
0x180070d31  xor     r9d, r9d; lpArguments
0x180070d34  xor     r8d, r8d; nNumberOfArguments
0x180070d37  lea     edx, [r9+1]; dwExceptionFlags
0x180070d3b  mov     ecx, eax; dwExceptionCode
0x180070d3d  call    cs:__imp_RaiseException
0x180070d43  int     3; Trap to Debugger
0x180070d44  lea     r8, [rsp+130h+var_110]
0x180070d49  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x180070d50  mov     rcx, [rbp+30h+var_18]
0x180070d54  call    cs:__imp_RoGetActivationFactory
0x180070d5a  mov     ebx, eax
0x180070d5c  test    eax, eax
0x180070d5e  jns     short loc_180070D84
0x180070d60  mov     rcx, [rsp+130h+var_110]
0x180070d65  test    rcx, rcx
0x180070d68  jz      short loc_180070D80
0x180070d6a  mov     [rsp+130h+var_110], 0
0x180070d73  mov     rdx, [rcx]
0x180070d76  mov     rax, [rdx+10h]
0x180070d7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070d7f  nop
0x180070d80  mov     eax, ebx
0x180070d82  jmp     short loc_180070DEC
0x180070d84  mov     [rsp+130h+var_108], 0
0x180070d8d  mov     rbx, [rsp+130h+var_110]
0x180070d92  lea     rcx, [rsp+130h+var_108]
0x180070d97  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x180070d9c  lea     r8, [rsp+130h+var_108]
0x180070da1  lea     rdx, [rsp+130h+var_100]
0x180070da6  mov     rcx, rbx
0x180070da9  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x180070dae  mov     ebx, eax
0x180070db0  lea     rcx, [rsp+130h+var_108]
0x180070db5  test    eax, eax
0x180070db7  jns     short loc_180070DCA
0x180070db9  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x180070dbe  lea     rcx, [rsp+130h+var_110]
0x180070dc3  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x180070dc8  jmp     short loc_180070D80
0x180070dca  mov     rax, [rsp+130h+var_108]
0x180070dcf  mov     [rsp+130h+var_108], 0
0x180070dd8  mov     [rdi], rax
0x180070ddb  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x180070de0  lea     rcx, [rsp+130h+var_110]
0x180070de5  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x180070dea  xor     eax, eax
0x180070dec  mov     rcx, [rbp+30h+var_10]
0x180070df0  xor     rcx, rsp; StackCookie
0x180070df3  call    __security_check_cookie
0x180070df8  lea     r11, [rsp+130h+var_s0]
0x180070e00  mov     rbx, [r11+10h]
0x180070e04  mov     rdi, [r11+20h]
0x180070e08  mov     rsp, r11
0x180070e0b  pop     rbp
0x180070e0c  retn
```
