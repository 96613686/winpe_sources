# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::ApplicationExtension,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::ApplicationExtension *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::ApplicationExtension *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::ApplicationExtension *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::ApplicationExtension *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::ApplicationExtension *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::ApplicationExtension *>,0> * *)

- ea: `0x18003058c`
- end: `0x18003084b`
- name: `??$CreateExternalObjectVector@VApplicationExtension@StateRepository@Internal@Windows@@V?$AgileVector@PEAVApplicationExtension@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVApplicationExtension@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVApplicationExtension@StateRepository@Internal@Windows@@@3674@$0A@@3Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVApplicationExtension@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVApplicationExtension@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVApplicationExtension@StateRepository@Internal@Windows@@@3674@$0A@@1234@@Z`
- size: `703`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180030448`
- `0x180082744`

## callees

- `0x180003e54`
- `0x180013ddc`
- `0x18003058c`
- `0x18018f650`
- `0x1801a5ba0`
- `0x18027e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003080b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003081e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180030831`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180030844`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003080b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003081e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180030831`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180030844`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180030705`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180030705`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800305df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180030618`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180030651`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800306e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800305df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180030618`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180030651`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800306e7`

## string_xrefs

- `0x18003064a`: `Windows.Foundation.Collections.IIterator`1<Windows.Internal.StateRepository.ApplicationExtension>`
- `0x1800305d8`: `Windows.Foundation.Collections.IVector`1<Windows.Internal.StateRepository.ApplicationExtension>`
- `0x180030611`: `Windows.Foundation.Collections.IVectorView`1<Windows.Internal.StateRepository.ApplicationExtension>`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::ApplicationExtension,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::ApplicationExtension *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::ApplicationExtension *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::ApplicationExtension *>,0>>(
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
  __int64 v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v22; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v23[3]; // [rsp+30h] [rbp-D0h] BYREF
  GUID v24; // [rsp+48h] [rbp-B8h]
  GUID v25; // [rsp+58h] [rbp-A8h]
  GUID v26; // [rsp+68h] [rbp-98h]
  GUID v27; // [rsp+78h] [rbp-88h]
  GUID v28; // [rsp+88h] [rbp-78h]
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING string; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING_HEADER v31; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING v32; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING_HEADER v33; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING v34; // [rsp+F8h] [rbp-8h] BYREF
  HSTRING_HEADER v35; // [rsp+100h] [rbp+0h] BYREF
  HSTRING v36; // [rsp+118h] [rbp+18h] BYREF

  string = 0;
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x5Fu);
  v4 = v3 - 1;
  if ( v3 > 0x5F )
    v4 = 95;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Internal.StateRepository.ApplicationExtension>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v32 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x63u);
  v7 = v6 - 1;
  if ( v6 > 0x63 )
    v7 = 99;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Internal.StateRepository.ApplicationExtension>",
         v7,
         &v31,
         &v32);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v34 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x61u);
  v10 = v9 - 1;
  if ( v9 > 0x61 )
    v10 = 97;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.Internal.StateRepository.ApplicationExtension>",
          v10,
          &v33,
          &v34);
  if ( v11 < 0 )
  {
    RaiseException(v11, 1u, 0, 0);
    __debugbreak();
  }
  v23[0] = string;
  v23[1] = v32;
  v23[2] = v34;
  v24 = GUID_d2aa7210_c0c4_44cb_8090_3fcd77fdf3d5;
  v25 = GUID_2727e162_4c4c_58f0_961a_a7a68d539eb7;
  v26 = GUID_547539fd_5a6b_51cf_b4cd_3f4fa6005838;
  v27 = GUID_1c1b406a_70fa_5d89_b904_9567c3f15bd0;
  v28 = GUID_812b6913_b1b4_5cb1_afc4_3e9af8e4e173;
  v21 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  v36 = 0;
  v12 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v35, &v36);
  if ( v12 < 0 )
  {
    RaiseException(v12, 1u, 0, 0);
    JUMPOUT(0x18003084ALL);
  }
  ActivationFactory = RoGetActivationFactory(v36, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v21);
  if ( ActivationFactory < 0 )
  {
    v18 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    return (unsigned int)ActivationFactory;
  }
  v22 = 0;
  v14 = v21;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}(v14, v23, &v22);
  if ( ActivationFactory < 0 )
  {
    v19 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    v20 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    return (unsigned int)ActivationFactory;
  }
  v15 = v22;
  v22 = 0;
  *a2 = v15;
  v16 = v21;
  if ( v21 )
  {
    v21 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  return 0;
}

```

## disassembly

```asm
0x18003058c  mov     [rsp-8+arg_0], rbx
0x180030591  mov     [rsp-8+arg_10], rdi
0x180030596  push    rbp
0x180030597  lea     rbp, [rsp-30h]
0x18003059c  sub     rsp, 130h
0x1800305a3  mov     rax, cs:__security_cookie
0x1800305aa  xor     rax, rsp
0x1800305ad  mov     [rbp+30h+var_10], rax
0x1800305b1  mov     rdi, rdx
0x1800305b4  mov     [rbp+30h+string], 0
0x1800305bc  mov     ebx, 5Fh ; '_'
0x1800305c1  mov     ecx, ebx; unsigned int
0x1800305c3  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800305c8  lea     edx, [rax-1]
0x1800305cb  cmp     eax, ebx
0x1800305cd  cmova   edx, ebx; length
0x1800305d0  lea     r9, [rbp+30h+string]; string
0x1800305d4  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x1800305d8  lea     rcx, aWindowsFoundat_190; "Windows.Foundation.Collections.IVector`"...
0x1800305df  call    cs:__imp_WindowsCreateStringReference
0x1800305e5  test    eax, eax
0x1800305e7  js      loc_1800307FF
0x1800305ed  mov     [rbp+30h+var_58], 0
0x1800305f5  mov     ebx, 63h ; 'c'
0x1800305fa  mov     ecx, ebx; unsigned int
0x1800305fc  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180030601  lea     edx, [rax-1]
0x180030604  cmp     eax, ebx
0x180030606  cmova   edx, ebx; length
0x180030609  lea     r9, [rbp+30h+var_58]; string
0x18003060d  lea     r8, [rbp+30h+var_70]; hstringHeader
0x180030611  lea     rcx, aWindowsFoundat_42; "Windows.Foundation.Collections.IVectorV"...
0x180030618  call    cs:__imp_WindowsCreateStringReference
0x18003061e  test    eax, eax
0x180030620  js      loc_180030812
0x180030626  mov     [rbp+30h+var_38], 0
0x18003062e  mov     ebx, 61h ; 'a'
0x180030633  mov     ecx, ebx; unsigned int
0x180030635  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18003063a  lea     edx, [rax-1]
0x18003063d  cmp     eax, ebx
0x18003063f  cmova   edx, ebx; length
0x180030642  lea     r9, [rbp+30h+var_38]; string
0x180030646  lea     r8, [rbp+30h+var_50]; hstringHeader
0x18003064a  lea     rcx, aWindowsFoundat_132; "Windows.Foundation.Collections.IIterato"...
0x180030651  call    cs:__imp_WindowsCreateStringReference
0x180030657  test    eax, eax
0x180030659  js      loc_180030825
0x18003065f  mov     rax, [rbp+30h+string]
0x180030663  mov     [rsp+130h+var_100], rax
0x180030668  mov     rax, [rbp+30h+var_58]
0x18003066c  mov     [rsp+130h+var_F8], rax
0x180030671  mov     rax, [rbp+30h+var_38]
0x180030675  mov     [rsp+130h+var_F0], rax
0x18003067a  movups  xmm0, xmmword ptr cs:_GUID_d2aa7210_c0c4_44cb_8090_3fcd77fdf3d5.Data1
0x180030681  movdqu  [rsp+130h+var_E8], xmm0
0x180030687  movups  xmm1, xmmword ptr cs:_GUID_2727e162_4c4c_58f0_961a_a7a68d539eb7.Data1
0x18003068e  movdqu  [rsp+130h+var_D8], xmm1
0x180030694  movups  xmm0, xmmword ptr cs:_GUID_547539fd_5a6b_51cf_b4cd_3f4fa6005838.Data1
0x18003069b  movdqu  [rsp+130h+var_C8], xmm0
0x1800306a1  movups  xmm1, xmmword ptr cs:_GUID_1c1b406a_70fa_5d89_b904_9567c3f15bd0.Data1
0x1800306a8  movdqu  [rsp+130h+var_B8], xmm1
0x1800306ae  movups  xmm0, xmmword ptr cs:_GUID_812b6913_b1b4_5cb1_afc4_3e9af8e4e173.Data1
0x1800306b5  movdqu  [rbp+30h+var_A8], xmm0
0x1800306ba  mov     [rsp+130h+var_110], 0
0x1800306c3  lea     rcx, [rsp+130h+var_110]
0x1800306c8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800306cd  mov     [rbp+30h+var_18], 0
0x1800306d5  lea     r9, [rbp+30h+var_18]; string
0x1800306d9  lea     r8, [rbp+30h+var_30]; hstringHeader
0x1800306dd  lea     edx, [rbx-35h]; length
0x1800306e0  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x1800306e7  call    cs:__imp_WindowsCreateStringReference
0x1800306ed  test    eax, eax
0x1800306ef  js      loc_180030838
0x1800306f5  lea     r8, [rsp+130h+var_110]
0x1800306fa  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x180030701  mov     rcx, [rbp+30h+var_18]
0x180030705  call    cs:__imp_RoGetActivationFactory
0x18003070b  mov     ebx, eax
0x18003070d  test    eax, eax
0x18003070f  js      loc_180030799
0x180030715  mov     [rsp+130h+var_108], 0
0x18003071e  mov     rbx, [rsp+130h+var_110]
0x180030723  lea     rcx, [rsp+130h+var_108]
0x180030728  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003072d  lea     r8, [rsp+130h+var_108]
0x180030732  lea     rdx, [rsp+130h+var_100]
0x180030737  mov     rcx, rbx
0x18003073a  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x18003073f  mov     ebx, eax
0x180030741  test    eax, eax
0x180030743  js      short loc_1800307BD
0x180030745  mov     rax, [rsp+130h+var_108]
0x18003074a  mov     [rsp+130h+var_108], 0
0x180030753  mov     [rdi], rax
0x180030756  mov     rcx, [rsp+130h+var_110]
0x18003075b  test    rcx, rcx
0x18003075e  jz      short loc_180030776
0x180030760  mov     [rsp+130h+var_110], 0
0x180030769  mov     rax, [rcx]
0x18003076c  mov     rax, [rax+10h]
0x180030770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030775  nop
0x180030776  xor     eax, eax
0x180030778  mov     rcx, [rbp+30h+var_10]
0x18003077c  xor     rcx, rsp; StackCookie
0x18003077f  call    __security_check_cookie
0x180030784  lea     r11, [rsp+130h+var_s0]
0x18003078c  mov     rbx, [r11+10h]
0x180030790  mov     rdi, [r11+20h]
0x180030794  mov     rsp, r11
0x180030797  pop     rbp
0x180030798  retn
0x180030799  mov     rcx, [rsp+130h+var_110]
0x18003079e  test    rcx, rcx
0x1800307a1  jz      short loc_1800307B9
0x1800307a3  mov     [rsp+130h+var_110], 0
0x1800307ac  mov     rdx, [rcx]
0x1800307af  mov     rax, [rdx+10h]
0x1800307b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800307b8  nop
0x1800307b9  mov     eax, ebx
0x1800307bb  jmp     short loc_180030778
0x1800307bd  mov     rcx, [rsp+130h+var_108]
0x1800307c2  test    rcx, rcx
0x1800307c5  jz      short loc_1800307DD
0x1800307c7  mov     [rsp+130h+var_108], 0
0x1800307d0  mov     rdx, [rcx]
0x1800307d3  mov     rax, [rdx+10h]
0x1800307d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800307dc  nop
0x1800307dd  mov     rcx, [rsp+130h+var_110]
0x1800307e2  test    rcx, rcx
0x1800307e5  jz      short loc_1800307FD
0x1800307e7  mov     [rsp+130h+var_110], 0
0x1800307f0  mov     rax, [rcx]
0x1800307f3  mov     rax, [rax+10h]
0x1800307f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800307fc  nop
0x1800307fd  jmp     short loc_1800307B9
0x1800307ff  xor     r9d, r9d; lpArguments
0x180030802  xor     r8d, r8d; nNumberOfArguments
0x180030805  lea     edx, [r9+1]; dwExceptionFlags
0x180030809  mov     ecx, eax; dwExceptionCode
0x18003080b  call    cs:__imp_RaiseException
0x180030811  int     3; Trap to Debugger
0x180030812  xor     r9d, r9d; lpArguments
0x180030815  xor     r8d, r8d; nNumberOfArguments
0x180030818  lea     edx, [r9+1]; dwExceptionFlags
0x18003081c  mov     ecx, eax; dwExceptionCode
0x18003081e  call    cs:__imp_RaiseException
0x180030824  int     3; Trap to Debugger
0x180030825  xor     r9d, r9d; lpArguments
0x180030828  xor     r8d, r8d; nNumberOfArguments
0x18003082b  lea     edx, [r9+1]; dwExceptionFlags
0x18003082f  mov     ecx, eax; dwExceptionCode
0x180030831  call    cs:__imp_RaiseException
0x180030837  int     3; Trap to Debugger
0x180030838  xor     r9d, r9d; lpArguments
0x18003083b  xor     r8d, r8d; nNumberOfArguments
0x18003083e  lea     edx, [r9+1]; dwExceptionFlags
0x180030842  mov     ecx, eax; dwExceptionCode
0x180030844  call    cs:__imp_RaiseException
```
