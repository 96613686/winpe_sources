# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Storage::Streams::IBuffer,Windows::Foundation::Collections::Internal::Vector<Windows::Storage::Streams::IBuffer *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Storage::Streams::IBuffer *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::Streams::IBuffer *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Storage::Streams::IBuffer *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<Windows::Storage::Streams::IBuffer *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Storage::Streams::IBuffer *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::Streams::IBuffer *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Storage::Streams::IBuffer *>> * *)

- ea: `0x140017ef8`
- end: `0x14001813b`
- name: `??$CreateExternalObjectVector@UIBuffer@Streams@Storage@Windows@@V?$Vector@PEAUIBuffer@Streams@Storage@Windows@@U?$DefaultEqualityPredicate@PEAUIBuffer@Streams@Storage@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAUIBuffer@Streams@Storage@Windows@@@6784@U?$DefaultVectorOptions@PEAUIBuffer@Streams@Storage@Windows@@@6784@@Internal@Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAUIBuffer@Streams@Storage@Windows@@U?$DefaultEqualityPredicate@PEAUIBuffer@Streams@Storage@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAUIBuffer@Streams@Storage@Windows@@@6784@U?$DefaultVectorOptions@PEAUIBuffer@Streams@Storage@Windows@@@6784@@1234@@Z`
- size: `579`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400171a4`

## callees

- `0x14001431c`
- `0x140017ef8`
- `0x14005d0e0`
- `0x140086104`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140017f52`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140017f8b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140017fc4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14001806b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140017f52`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140017f8b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140017fc4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14001806b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140017f3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140017f75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140017fae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140018055`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140017f3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140017f75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140017fae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140018055`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140018082`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140018082`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Storage::Streams::IBuffer,Windows::Foundation::Collections::Internal::Vector<Windows::Storage::Streams::IBuffer *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Storage::Streams::IBuffer *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::Streams::IBuffer *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Storage::Streams::IBuffer *>>>(
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
  __int64 v11; // rax
  __int64 v12; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v13; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v14[3]; // [rsp+30h] [rbp-D0h] BYREF
  GUID v15; // [rsp+48h] [rbp-B8h]
  GUID v16; // [rsp+58h] [rbp-A8h]
  GUID v17; // [rsp+68h] [rbp-98h]
  GUID v18; // [rsp+78h] [rbp-88h]
  GUID v19; // [rsp+88h] [rbp-78h]
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING string; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING_HEADER v22; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING v23; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING_HEADER v24; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING v25; // [rsp+F8h] [rbp-8h] BYREF
  HSTRING_HEADER v26; // [rsp+100h] [rbp+0h] BYREF
  HSTRING v27; // [rsp+118h] [rbp+18h] BYREF

  string = 0;
  v3 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Storage.Streams.IBuffer>",
         0x49u,
         &hstringHeader,
         &string);
  if ( v3 < 0 )
  {
    RaiseException(v3, 1u, 0, 0);
    __debugbreak();
  }
  v23 = 0;
  v4 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Storage.Streams.IBuffer>",
         0x4Du,
         &v22,
         &v23);
  if ( v4 < 0 )
  {
    RaiseException(v4, 1u, 0, 0);
    __debugbreak();
  }
  v25 = 0;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IIterator`1<Windows.Storage.Streams.IBuffer>",
         0x4Bu,
         &v24,
         &v25);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v14[0] = string;
  v14[1] = v23;
  v14[2] = v25;
  v15 = GUID_905a0fe0_bc53_11df_8c49_001e4fc686da;
  v16 = GUID_308fe894_cc06_5007_bc85_cbe94ac1a70c;
  v17 = GUID_fd944562_11d6_5eab_bd72_701993b68fac;
  v18 = GUID_902972bf_a984_5443_b1c5_2f04a99e1fca;
  v19 = GUID_afee38e0_f882_5f10_9655_1fc98cc8cce5;
  v12 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
  v27 = 0;
  v6 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v26, &v27);
  if ( v6 < 0 )
  {
    RaiseException(v6, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(v27, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v12);
  if ( ActivationFactory < 0 )
  {
    v8 = v12;
    if ( v12 )
    {
      v12 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    return (unsigned int)ActivationFactory;
  }
  v13 = 0;
  v10 = v12;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{240,{flat}}(v10, v14, &v13);
  if ( ActivationFactory < 0 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
    return (unsigned int)ActivationFactory;
  }
  v11 = v13;
  v13 = 0;
  *a2 = v11;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
  return 0;
}

```

## disassembly

```asm
0x140017ef8  mov     [rsp-8+arg_0], rbx
0x140017efd  mov     [rsp-8+arg_10], rdi
0x140017f02  push    rbp
0x140017f03  lea     rbp, [rsp-30h]
0x140017f08  sub     rsp, 130h
0x140017f0f  mov     rax, cs:__security_cookie
0x140017f16  xor     rax, rsp
0x140017f19  mov     [rbp+30h+var_10], rax
0x140017f1d  mov     rdi, rdx
0x140017f20  mov     [rbp+30h+string], 0
0x140017f28  lea     r9, [rbp+30h+string]; string
0x140017f2c  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x140017f30  mov     edx, 49h ; 'I'; length
0x140017f35  lea     rcx, aWindowsFoundat_6; "Windows.Foundation.Collections.IVector`"...
0x140017f3c  call    cs:__imp_WindowsCreateStringReference
0x140017f42  test    eax, eax
0x140017f44  jns     short loc_140017F59
0x140017f46  xor     r9d, r9d; lpArguments
0x140017f49  xor     r8d, r8d; nNumberOfArguments
0x140017f4c  lea     edx, [r9+1]; dwExceptionFlags
0x140017f50  mov     ecx, eax; dwExceptionCode
0x140017f52  call    cs:__imp_RaiseException
0x140017f58  int     3; Trap to Debugger
0x140017f59  mov     [rbp+30h+var_58], 0
0x140017f61  lea     r9, [rbp+30h+var_58]; string
0x140017f65  lea     r8, [rbp+30h+var_70]; hstringHeader
0x140017f69  mov     edx, 4Dh ; 'M'; length
0x140017f6e  lea     rcx, aWindowsFoundat_7; "Windows.Foundation.Collections.IVectorV"...
0x140017f75  call    cs:__imp_WindowsCreateStringReference
0x140017f7b  test    eax, eax
0x140017f7d  jns     short loc_140017F92
0x140017f7f  xor     r9d, r9d; lpArguments
0x140017f82  xor     r8d, r8d; nNumberOfArguments
0x140017f85  lea     edx, [r9+1]; dwExceptionFlags
0x140017f89  mov     ecx, eax; dwExceptionCode
0x140017f8b  call    cs:__imp_RaiseException
0x140017f91  int     3; Trap to Debugger
0x140017f92  mov     [rbp+30h+var_38], 0
0x140017f9a  lea     r9, [rbp+30h+var_38]; string
0x140017f9e  lea     r8, [rbp+30h+var_50]; hstringHeader
0x140017fa2  mov     edx, 4Bh ; 'K'; length
0x140017fa7  lea     rcx, aWindowsFoundat_8; "Windows.Foundation.Collections.IIterato"...
0x140017fae  call    cs:__imp_WindowsCreateStringReference
0x140017fb4  test    eax, eax
0x140017fb6  jns     short loc_140017FCB
0x140017fb8  xor     r9d, r9d; lpArguments
0x140017fbb  xor     r8d, r8d; nNumberOfArguments
0x140017fbe  lea     edx, [r9+1]; dwExceptionFlags
0x140017fc2  mov     ecx, eax; dwExceptionCode
0x140017fc4  call    cs:__imp_RaiseException
0x140017fca  int     3; Trap to Debugger
0x140017fcb  mov     rax, [rbp+30h+string]
0x140017fcf  mov     [rsp+130h+var_100], rax
0x140017fd4  mov     rax, [rbp+30h+var_58]
0x140017fd8  mov     [rsp+130h+var_F8], rax
0x140017fdd  mov     rax, [rbp+30h+var_38]
0x140017fe1  mov     [rsp+130h+var_F0], rax
0x140017fe6  movups  xmm0, xmmword ptr cs:_GUID_905a0fe0_bc53_11df_8c49_001e4fc686da.Data1
0x140017fed  movdqu  [rsp+130h+var_E8], xmm0
0x140017ff3  movups  xmm1, xmmword ptr cs:_GUID_308fe894_cc06_5007_bc85_cbe94ac1a70c.Data1
0x140017ffa  movdqu  [rsp+130h+var_D8], xmm1
0x140018000  movups  xmm0, xmmword ptr cs:_GUID_fd944562_11d6_5eab_bd72_701993b68fac.Data1
0x140018007  movdqu  [rsp+130h+var_C8], xmm0
0x14001800d  movups  xmm1, xmmword ptr cs:_GUID_902972bf_a984_5443_b1c5_2f04a99e1fca.Data1
0x140018014  movdqu  [rsp+130h+var_B8], xmm1
0x14001801a  movups  xmm0, xmmword ptr cs:_GUID_afee38e0_f882_5f10_9655_1fc98cc8cce5.Data1
0x140018021  movdqu  [rbp+30h+var_A8], xmm0
0x140018026  mov     [rsp+130h+var_110], 0
0x14001802f  lea     rcx, [rsp+130h+var_110]
0x140018034  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140018039  mov     [rbp+30h+var_18], 0
0x140018041  lea     r9, [rbp+30h+var_18]; string
0x140018045  lea     r8, [rbp+30h+var_30]; hstringHeader
0x140018049  mov     edx, 2Ch ; ','; length
0x14001804e  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x140018055  call    cs:__imp_WindowsCreateStringReference
0x14001805b  test    eax, eax
0x14001805d  jns     short loc_140018072
0x14001805f  xor     r9d, r9d; lpArguments
0x140018062  xor     r8d, r8d; nNumberOfArguments
0x140018065  lea     edx, [r9+1]; dwExceptionFlags
0x140018069  mov     ecx, eax; dwExceptionCode
0x14001806b  call    cs:__imp_RaiseException
0x140018071  int     3; Trap to Debugger
0x140018072  lea     r8, [rsp+130h+var_110]
0x140018077  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x14001807e  mov     rcx, [rbp+30h+var_18]
0x140018082  call    cs:__imp_RoGetActivationFactory
0x140018088  mov     ebx, eax
0x14001808a  test    eax, eax
0x14001808c  jns     short loc_1400180B2
0x14001808e  mov     rcx, [rsp+130h+var_110]
0x140018093  test    rcx, rcx
0x140018096  jz      short loc_1400180AE
0x140018098  mov     [rsp+130h+var_110], 0
0x1400180a1  mov     rdx, [rcx]
0x1400180a4  mov     rax, [rdx+10h]
0x1400180a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400180ad  nop
0x1400180ae  mov     eax, ebx
0x1400180b0  jmp     short loc_14001811A
0x1400180b2  mov     [rsp+130h+var_108], 0
0x1400180bb  mov     rbx, [rsp+130h+var_110]
0x1400180c0  lea     rcx, [rsp+130h+var_108]
0x1400180c5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400180ca  lea     r8, [rsp+130h+var_108]
0x1400180cf  lea     rdx, [rsp+130h+var_100]
0x1400180d4  mov     rcx, rbx
0x1400180d7  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPA@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{240,{flat}}
0x1400180dc  mov     ebx, eax
0x1400180de  lea     rcx, [rsp+130h+var_108]
0x1400180e3  test    eax, eax
0x1400180e5  jns     short loc_1400180F8
0x1400180e7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400180ec  lea     rcx, [rsp+130h+var_110]
0x1400180f1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400180f6  jmp     short loc_1400180AE
0x1400180f8  mov     rax, [rsp+130h+var_108]
0x1400180fd  mov     [rsp+130h+var_108], 0
0x140018106  mov     [rdi], rax
0x140018109  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001810e  lea     rcx, [rsp+130h+var_110]
0x140018113  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140018118  xor     eax, eax
0x14001811a  mov     rcx, [rbp+30h+var_10]
0x14001811e  xor     rcx, rsp; StackCookie
0x140018121  call    __security_check_cookie
0x140018126  lea     r11, [rsp+130h+var_s0]
0x14001812e  mov     rbx, [r11+10h]
0x140018132  mov     rdi, [r11+20h]
0x140018136  mov     rsp, r11
0x140018139  pop     rbp
0x14001813a  retn
```
