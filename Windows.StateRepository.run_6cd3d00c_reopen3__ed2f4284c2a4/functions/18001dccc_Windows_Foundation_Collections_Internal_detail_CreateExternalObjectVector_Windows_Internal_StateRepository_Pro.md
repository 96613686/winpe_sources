# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::ProtocolLauncherInfo,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::ProtocolLauncherInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::ProtocolLauncherInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::ProtocolLauncherInfo *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::ProtocolLauncherInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::ProtocolLauncherInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::ProtocolLauncherInfo *>,0> * *)

- ea: `0x18001dccc`
- end: `0x18001df6d`
- name: `??$CreateExternalObjectVector@VProtocolLauncherInfo@StateRepository@Internal@Windows@@V?$AgileVector@PEAVProtocolLauncherInfo@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVProtocolLauncherInfo@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVProtocolLauncherInfo@StateRepository@Internal@Windows@@@3674@$0A@@3Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVProtocolLauncherInfo@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVProtocolLauncherInfo@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVProtocolLauncherInfo@StateRepository@Internal@Windows@@@3674@$0A@@1234@@Z`
- size: `673`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001db70`
- `0x1801e82dc`

## callees

- `0x180003e54`
- `0x180013ddc`
- `0x18001dccc`
- `0x18018f650`
- `0x1801a5ba0`
- `0x18027e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001dd34`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001dd7b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001ddc2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001de69`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001dd34`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001dd7b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001ddc2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001de69`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001de80`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001de80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001dd1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001dd66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001ddad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001de53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001dd1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001dd66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001ddad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001de53`

## string_xrefs

- `0x18001dd5f`: `Windows.Foundation.Collections.IVectorView`1<Windows.Internal.StateRepository.ProtocolLauncherInfo>`
- `0x18001dd18`: `Windows.Foundation.Collections.IVector`1<Windows.Internal.StateRepository.ProtocolLauncherInfo>`
- `0x18001dda6`: `Windows.Foundation.Collections.IIterator`1<Windows.Internal.StateRepository.ProtocolLauncherInfo>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::ProtocolLauncherInfo,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::ProtocolLauncherInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::ProtocolLauncherInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::ProtocolLauncherInfo *>,0>>(
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
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v21; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v22[3]; // [rsp+30h] [rbp-D0h] BYREF
  GUID v23; // [rsp+48h] [rbp-B8h]
  GUID v24; // [rsp+58h] [rbp-A8h]
  GUID v25; // [rsp+68h] [rbp-98h]
  GUID v26; // [rsp+78h] [rbp-88h]
  GUID v27; // [rsp+88h] [rbp-78h]
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING string; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING_HEADER v30; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING v31; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING_HEADER v32; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING v33; // [rsp+F8h] [rbp-8h] BYREF
  HSTRING_HEADER v34; // [rsp+100h] [rbp+0h] BYREF
  HSTRING v35; // [rsp+118h] [rbp+18h] BYREF

  string = 0;
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x5Fu);
  v4 = v3 - 1;
  if ( v3 > 0x5F )
    v4 = 95;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Internal.StateRepository.ProtocolLauncherInfo>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v31 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x63u);
  v7 = v6 - 1;
  if ( v6 > 0x63 )
    v7 = 99;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Internal.StateRepository.ProtocolLauncherInfo>",
         v7,
         &v30,
         &v31);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v33 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x61u);
  v10 = v9 - 1;
  if ( v9 > 0x61 )
    v10 = 97;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.Internal.StateRepository.ProtocolLauncherInfo>",
          v10,
          &v32,
          &v33);
  if ( v11 < 0 )
  {
    RaiseException(v11, 1u, 0, 0);
    __debugbreak();
  }
  v22[0] = string;
  v22[1] = v31;
  v22[2] = v33;
  v23 = GUID_219c82b0_40f6_4f7e_a532_4373bb075ed7;
  v24 = GUID_a52273c5_909f_5299_849e_faeebbc04f27;
  v25 = GUID_04222ebf_3c08_5a6f_b227_d886a2b52873;
  v26 = GUID_6b8e18cc_33ef_57f4_b0ad_ce845b38de88;
  v27 = GUID_2d08b82e_1c97_50c6_96b5_53cf0f4a1d85;
  v20 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  v35 = 0;
  v12 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v34, &v35);
  if ( v12 < 0 )
  {
    RaiseException(v12, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(v35, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v20);
  if ( ActivationFactory < 0 )
  {
    v14 = v20;
    if ( v20 )
    {
      v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    return (unsigned int)ActivationFactory;
  }
  v21 = 0;
  v16 = v20;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}(v16, v22, &v21);
  if ( ActivationFactory < 0 )
  {
    v17 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    v18 = v20;
    if ( v20 )
    {
      v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    return (unsigned int)ActivationFactory;
  }
  v19 = v21;
  v21 = 0;
  *a2 = v19;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  return 0;
}

```

## disassembly

```asm
0x18001dccc  mov     [rsp-8+arg_0], rbx
0x18001dcd1  mov     [rsp-8+arg_10], rdi
0x18001dcd6  push    rbp
0x18001dcd7  lea     rbp, [rsp-30h]
0x18001dcdc  sub     rsp, 130h
0x18001dce3  mov     rax, cs:__security_cookie
0x18001dcea  xor     rax, rsp
0x18001dced  mov     [rbp+30h+var_10], rax
0x18001dcf1  mov     rdi, rdx
0x18001dcf4  mov     [rbp+30h+string], 0
0x18001dcfc  mov     ebx, 5Fh ; '_'
0x18001dd01  mov     ecx, ebx; unsigned int
0x18001dd03  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18001dd08  lea     edx, [rax-1]
0x18001dd0b  cmp     eax, ebx
0x18001dd0d  cmova   edx, ebx; length
0x18001dd10  lea     r9, [rbp+30h+string]; string
0x18001dd14  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x18001dd18  lea     rcx, aWindowsFoundat_11; "Windows.Foundation.Collections.IVector`"...
0x18001dd1f  call    cs:__imp_WindowsCreateStringReference
0x18001dd25  test    eax, eax
0x18001dd27  jns     short loc_18001DD3B
0x18001dd29  xor     r9d, r9d; lpArguments
0x18001dd2c  xor     r8d, r8d; nNumberOfArguments
0x18001dd2f  lea     edx, [rbx-5Eh]; dwExceptionFlags
0x18001dd32  mov     ecx, eax; dwExceptionCode
0x18001dd34  call    cs:__imp_RaiseException
0x18001dd3a  int     3; Trap to Debugger
0x18001dd3b  mov     [rbp+30h+var_58], 0
0x18001dd43  mov     ebx, 63h ; 'c'
0x18001dd48  mov     ecx, ebx; unsigned int
0x18001dd4a  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18001dd4f  lea     edx, [rax-1]
0x18001dd52  cmp     eax, ebx
0x18001dd54  cmova   edx, ebx; length
0x18001dd57  lea     r9, [rbp+30h+var_58]; string
0x18001dd5b  lea     r8, [rbp+30h+var_70]; hstringHeader
0x18001dd5f  lea     rcx, aWindowsFoundat_208; "Windows.Foundation.Collections.IVectorV"...
0x18001dd66  call    cs:__imp_WindowsCreateStringReference
0x18001dd6c  test    eax, eax
0x18001dd6e  jns     short loc_18001DD82
0x18001dd70  xor     r9d, r9d; lpArguments
0x18001dd73  xor     r8d, r8d; nNumberOfArguments
0x18001dd76  lea     edx, [rbx-62h]; dwExceptionFlags
0x18001dd79  mov     ecx, eax; dwExceptionCode
0x18001dd7b  call    cs:__imp_RaiseException
0x18001dd81  int     3; Trap to Debugger
0x18001dd82  mov     [rbp+30h+var_38], 0
0x18001dd8a  mov     ebx, 61h ; 'a'
0x18001dd8f  mov     ecx, ebx; unsigned int
0x18001dd91  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18001dd96  lea     edx, [rax-1]
0x18001dd99  cmp     eax, ebx
0x18001dd9b  cmova   edx, ebx; length
0x18001dd9e  lea     r9, [rbp+30h+var_38]; string
0x18001dda2  lea     r8, [rbp+30h+var_50]; hstringHeader
0x18001dda6  lea     rcx, aWindowsFoundat_186; "Windows.Foundation.Collections.IIterato"...
0x18001ddad  call    cs:__imp_WindowsCreateStringReference
0x18001ddb3  test    eax, eax
0x18001ddb5  jns     short loc_18001DDC9
0x18001ddb7  xor     r9d, r9d; lpArguments
0x18001ddba  xor     r8d, r8d; nNumberOfArguments
0x18001ddbd  lea     edx, [rbx-60h]; dwExceptionFlags
0x18001ddc0  mov     ecx, eax; dwExceptionCode
0x18001ddc2  call    cs:__imp_RaiseException
0x18001ddc8  int     3; Trap to Debugger
0x18001ddc9  mov     rax, [rbp+30h+string]
0x18001ddcd  mov     [rsp+130h+var_100], rax
0x18001ddd2  mov     rax, [rbp+30h+var_58]
0x18001ddd6  mov     [rsp+130h+var_F8], rax
0x18001dddb  mov     rax, [rbp+30h+var_38]
0x18001dddf  mov     [rsp+130h+var_F0], rax
0x18001dde4  movups  xmm0, xmmword ptr cs:_GUID_219c82b0_40f6_4f7e_a532_4373bb075ed7.Data1
0x18001ddeb  movdqu  [rsp+130h+var_E8], xmm0
0x18001ddf1  movups  xmm1, xmmword ptr cs:_GUID_a52273c5_909f_5299_849e_faeebbc04f27.Data1
0x18001ddf8  movdqu  [rsp+130h+var_D8], xmm1
0x18001ddfe  movups  xmm0, xmmword ptr cs:_GUID_04222ebf_3c08_5a6f_b227_d886a2b52873.Data1
0x18001de05  movdqu  [rsp+130h+var_C8], xmm0
0x18001de0b  movups  xmm1, xmmword ptr cs:_GUID_6b8e18cc_33ef_57f4_b0ad_ce845b38de88.Data1
0x18001de12  movdqu  [rsp+130h+var_B8], xmm1
0x18001de18  movups  xmm0, xmmword ptr cs:_GUID_2d08b82e_1c97_50c6_96b5_53cf0f4a1d85.Data1
0x18001de1f  movdqu  [rbp+30h+var_A8], xmm0
0x18001de24  mov     [rsp+130h+var_110], 0
0x18001de2d  lea     rcx, [rsp+130h+var_110]
0x18001de32  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001de37  mov     [rbp+30h+var_18], 0
0x18001de3f  lea     r9, [rbp+30h+var_18]; string
0x18001de43  lea     r8, [rbp+30h+var_30]; hstringHeader
0x18001de47  mov     edx, 2Ch ; ','; length
0x18001de4c  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x18001de53  call    cs:__imp_WindowsCreateStringReference
0x18001de59  test    eax, eax
0x18001de5b  jns     short loc_18001DE70
0x18001de5d  xor     r9d, r9d; lpArguments
0x18001de60  xor     r8d, r8d; nNumberOfArguments
0x18001de63  lea     edx, [r9+1]; dwExceptionFlags
0x18001de67  mov     ecx, eax; dwExceptionCode
0x18001de69  call    cs:__imp_RaiseException
0x18001de6f  int     3; Trap to Debugger
0x18001de70  lea     r8, [rsp+130h+var_110]
0x18001de75  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x18001de7c  mov     rcx, [rbp+30h+var_18]
0x18001de80  call    cs:__imp_RoGetActivationFactory
0x18001de86  mov     ebx, eax
0x18001de88  test    eax, eax
0x18001de8a  jns     short loc_18001DEB3
0x18001de8c  mov     rcx, [rsp+130h+var_110]
0x18001de91  test    rcx, rcx
0x18001de94  jz      short loc_18001DEAC
0x18001de96  mov     [rsp+130h+var_110], 0
0x18001de9f  mov     rdx, [rcx]
0x18001dea2  mov     rax, [rdx+10h]
0x18001dea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001deab  nop
0x18001deac  mov     eax, ebx
0x18001deae  jmp     loc_18001DF4C
0x18001deb3  mov     [rsp+130h+var_108], 0
0x18001debc  mov     rbx, [rsp+130h+var_110]
0x18001dec1  lea     rcx, [rsp+130h+var_108]
0x18001dec6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001decb  lea     r8, [rsp+130h+var_108]
0x18001ded0  lea     rdx, [rsp+130h+var_100]
0x18001ded5  mov     rcx, rbx
0x18001ded8  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x18001dedd  mov     ebx, eax
0x18001dedf  test    eax, eax
0x18001dee1  jns     short loc_18001DF25
0x18001dee3  mov     rcx, [rsp+130h+var_108]
0x18001dee8  test    rcx, rcx
0x18001deeb  jz      short loc_18001DF03
0x18001deed  mov     [rsp+130h+var_108], 0
0x18001def6  mov     rdx, [rcx]
0x18001def9  mov     rax, [rdx+10h]
0x18001defd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df02  nop
0x18001df03  mov     rcx, [rsp+130h+var_110]
0x18001df08  test    rcx, rcx
0x18001df0b  jz      short loc_18001DF23
0x18001df0d  mov     [rsp+130h+var_110], 0
0x18001df16  mov     rax, [rcx]
0x18001df19  mov     rax, [rax+10h]
0x18001df1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df22  nop
0x18001df23  jmp     short loc_18001DEAC
0x18001df25  mov     rax, [rsp+130h+var_108]
0x18001df2a  mov     [rsp+130h+var_108], 0
0x18001df33  mov     [rdi], rax
0x18001df36  lea     rcx, [rsp+130h+var_108]
0x18001df3b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001df40  lea     rcx, [rsp+130h+var_110]
0x18001df45  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001df4a  xor     eax, eax
0x18001df4c  mov     rcx, [rbp+30h+var_10]
0x18001df50  xor     rcx, rsp; StackCookie
0x18001df53  call    __security_check_cookie
0x18001df58  lea     r11, [rsp+130h+var_s0]
0x18001df60  mov     rbx, [r11+10h]
0x18001df64  mov     rdi, [r11+20h]
0x18001df68  mov     rsp, r11
0x18001df6b  pop     rbp
0x18001df6c  retn
```
