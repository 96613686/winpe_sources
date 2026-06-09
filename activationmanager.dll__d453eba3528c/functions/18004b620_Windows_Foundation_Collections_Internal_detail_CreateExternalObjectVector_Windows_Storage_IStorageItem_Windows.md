# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Storage::IStorageItem,Windows::Foundation::Collections::Internal::AgileVector<Windows::Storage::IStorageItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Storage::IStorageItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::IStorageItem *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Storage::IStorageItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Storage::IStorageItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::IStorageItem *>,0> * *)

- ea: `0x18004b620`
- end: `0x18004b86d`
- name: `??$CreateExternalObjectVector@UIStorageItem@Storage@Windows@@V?$AgileVector@PEAUIStorageItem@Storage@Windows@@U?$DefaultEqualityPredicate@PEAUIStorageItem@Storage@Windows@@@Internal@Collections@Foundation@3@U?$DefaultLifetimeTraits@PEAUIStorageItem@Storage@Windows@@@5673@$0A@@Internal@Collections@Foundation@3@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAUIStorageItem@Storage@Windows@@U?$DefaultEqualityPredicate@PEAUIStorageItem@Storage@Windows@@@Internal@Collections@Foundation@3@U?$DefaultLifetimeTraits@PEAUIStorageItem@Storage@Windows@@@5673@$0A@@1234@@Z`
- size: `589`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180023334`

## callees

- `0x180011328`
- `0x180029028`
- `0x18004b620`
- `0x18005ae90`
- `0x1800642ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004b688`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004b6cf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004b716`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004b7bd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004b688`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004b6cf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004b716`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004b7bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004b673`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004b6ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004b701`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004b7a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004b673`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004b6ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004b701`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004b7a7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004b7d4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004b7d4`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Storage::IStorageItem,Windows::Foundation::Collections::Internal::AgileVector<Windows::Storage::IStorageItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Storage::IStorageItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::IStorageItem *>,0>>(
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
  __int64 v15; // rbx
  __int64 v16; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v17; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v18[3]; // [rsp+30h] [rbp-D0h] BYREF
  GUID v19; // [rsp+48h] [rbp-B8h]
  GUID v20; // [rsp+58h] [rbp-A8h]
  GUID v21; // [rsp+68h] [rbp-98h]
  GUID v22; // [rsp+78h] [rbp-88h]
  GUID v23; // [rsp+88h] [rbp-78h]
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING string; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING_HEADER v26; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING v27; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING_HEADER v28; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING v29; // [rsp+F8h] [rbp-8h] BYREF
  HSTRING_HEADER v30; // [rsp+100h] [rbp+0h] BYREF
  HSTRING v31; // [rsp+118h] [rbp+18h] BYREF

  string = 0;
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x46u);
  v4 = v3 - 1;
  if ( v3 > 0x46 )
    v4 = 70;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Storage.IStorageItem>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v27 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x4Au);
  v7 = v6 - 1;
  if ( v6 > 0x4A )
    v7 = 74;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Storage.IStorageItem>",
         v7,
         &v26,
         &v27);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v29 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x48u);
  v10 = v9 - 1;
  if ( v9 > 0x48 )
    v10 = 72;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.Storage.IStorageItem>",
          v10,
          &v28,
          &v29);
  if ( v11 < 0 )
  {
    RaiseException(v11, 1u, 0, 0);
    __debugbreak();
  }
  v18[0] = string;
  v19 = GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30;
  v18[1] = v27;
  v20 = GUID_802508e2_9c2c_5b91_89a8_39bcf7223344;
  v18[2] = v29;
  v17 = 0;
  v21 = GUID_85575a41_06cb_58d0_b98a_7c8f06e6e9d7;
  v22 = GUID_bb8b8418_65d1_544b_b083_6d172f568c73;
  v23 = GUID_05b487c2_3830_5d3c_98da_25fa11542dbd;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v17);
  v31 = 0;
  v12 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v30, &v31);
  if ( v12 < 0 )
  {
    RaiseException(v12, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(v31, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v17);
  if ( ActivationFactory < 0 )
    goto LABEL_16;
  v15 = v17;
  v16 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v16);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}(v15, v18, &v16);
  if ( ActivationFactory < 0 )
  {
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v16);
LABEL_16:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v17);
    return (unsigned int)ActivationFactory;
  }
  *a2 = v16;
  v16 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v16);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v17);
  return 0;
}

```

## disassembly

```asm
0x18004b620  mov     [rsp-8+arg_0], rbx
0x18004b625  mov     [rsp-8+arg_10], rdi
0x18004b62a  push    rbp
0x18004b62b  lea     rbp, [rsp-30h]
0x18004b630  sub     rsp, 130h
0x18004b637  mov     rax, cs:__security_cookie
0x18004b63e  xor     rax, rsp
0x18004b641  mov     [rbp+30h+var_10], rax
0x18004b645  mov     ebx, 46h ; 'F'
0x18004b64a  mov     [rbp+30h+string], 0
0x18004b652  mov     ecx, ebx; unsigned int
0x18004b654  mov     rdi, rdx
0x18004b657  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18004b65c  cmp     eax, ebx
0x18004b65e  lea     r9, [rbp+30h+string]; string
0x18004b662  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x18004b666  lea     rcx, aWindowsFoundat_3; "Windows.Foundation.Collections.IVector`"...
0x18004b66d  lea     edx, [rax-1]
0x18004b670  cmova   edx, ebx; length
0x18004b673  call    cs:__imp_WindowsCreateStringReference
0x18004b679  test    eax, eax
0x18004b67b  jns     short loc_18004B68F
0x18004b67d  xor     r9d, r9d; lpArguments
0x18004b680  lea     edx, [rbx-45h]; dwExceptionFlags
0x18004b683  xor     r8d, r8d; nNumberOfArguments
0x18004b686  mov     ecx, eax; dwExceptionCode
0x18004b688  call    cs:__imp_RaiseException
0x18004b68e  int     3; Trap to Debugger
0x18004b68f  mov     ebx, 4Ah ; 'J'
0x18004b694  mov     [rbp+30h+var_58], 0
0x18004b69c  mov     ecx, ebx; unsigned int
0x18004b69e  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18004b6a3  cmp     eax, ebx
0x18004b6a5  lea     r9, [rbp+30h+var_58]; string
0x18004b6a9  lea     r8, [rbp+30h+var_70]; hstringHeader
0x18004b6ad  lea     rcx, aWindowsFoundat_0; "Windows.Foundation.Collections.IVectorV"...
0x18004b6b4  lea     edx, [rax-1]
0x18004b6b7  cmova   edx, ebx; length
0x18004b6ba  call    cs:__imp_WindowsCreateStringReference
0x18004b6c0  test    eax, eax
0x18004b6c2  jns     short loc_18004B6D6
0x18004b6c4  xor     r9d, r9d; lpArguments
0x18004b6c7  lea     edx, [rbx-49h]; dwExceptionFlags
0x18004b6ca  xor     r8d, r8d; nNumberOfArguments
0x18004b6cd  mov     ecx, eax; dwExceptionCode
0x18004b6cf  call    cs:__imp_RaiseException
0x18004b6d5  int     3; Trap to Debugger
0x18004b6d6  mov     ebx, 48h ; 'H'
0x18004b6db  mov     [rbp+30h+var_38], 0
0x18004b6e3  mov     ecx, ebx; unsigned int
0x18004b6e5  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18004b6ea  cmp     eax, ebx
0x18004b6ec  lea     r9, [rbp+30h+var_38]; string
0x18004b6f0  lea     r8, [rbp+30h+var_50]; hstringHeader
0x18004b6f4  lea     rcx, aWindowsFoundat_4; "Windows.Foundation.Collections.IIterato"...
0x18004b6fb  lea     edx, [rax-1]
0x18004b6fe  cmova   edx, ebx; length
0x18004b701  call    cs:__imp_WindowsCreateStringReference
0x18004b707  test    eax, eax
0x18004b709  jns     short loc_18004B71D
0x18004b70b  xor     r9d, r9d; lpArguments
0x18004b70e  lea     edx, [rbx-47h]; dwExceptionFlags
0x18004b711  xor     r8d, r8d; nNumberOfArguments
0x18004b714  mov     ecx, eax; dwExceptionCode
0x18004b716  call    cs:__imp_RaiseException
0x18004b71c  int     3; Trap to Debugger
0x18004b71d  movups  xmm0, xmmword ptr cs:_GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30.Data1
0x18004b724  mov     rax, [rbp+30h+string]
0x18004b728  lea     rcx, [rsp+130h+var_108]
0x18004b72d  movups  xmm1, xmmword ptr cs:_GUID_802508e2_9c2c_5b91_89a8_39bcf7223344.Data1
0x18004b734  mov     [rsp+130h+var_100], rax
0x18004b739  mov     rax, [rbp+30h+var_58]
0x18004b73d  movdqu  [rsp+130h+var_E8], xmm0
0x18004b743  mov     [rsp+130h+var_F8], rax
0x18004b748  movups  xmm0, xmmword ptr cs:_GUID_85575a41_06cb_58d0_b98a_7c8f06e6e9d7.Data1
0x18004b74f  mov     rax, [rbp+30h+var_38]
0x18004b753  movdqu  [rsp+130h+var_D8], xmm1
0x18004b759  mov     [rsp+130h+var_F0], rax
0x18004b75e  movups  xmm1, xmmword ptr cs:_GUID_bb8b8418_65d1_544b_b083_6d172f568c73.Data1
0x18004b765  mov     [rsp+130h+var_108], 0
0x18004b76e  movdqu  [rsp+130h+var_C8], xmm0
0x18004b774  movups  xmm0, xmmword ptr cs:_GUID_05b487c2_3830_5d3c_98da_25fa11542dbd.Data1
0x18004b77b  movdqu  [rsp+130h+var_B8], xmm1
0x18004b781  movdqu  [rbp+30h+var_A8], xmm0
0x18004b786  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18004b78b  lea     r9, [rbp+30h+var_18]; string
0x18004b78f  mov     [rbp+30h+var_18], 0
0x18004b797  lea     r8, [rbp+30h+var_30]; hstringHeader
0x18004b79b  mov     edx, 2Ch ; ','; length
0x18004b7a0  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x18004b7a7  call    cs:__imp_WindowsCreateStringReference
0x18004b7ad  test    eax, eax
0x18004b7af  jns     short loc_18004B7C4
0x18004b7b1  xor     r9d, r9d; lpArguments
0x18004b7b4  xor     r8d, r8d; nNumberOfArguments
0x18004b7b7  mov     ecx, eax; dwExceptionCode
0x18004b7b9  lea     edx, [r9+1]; dwExceptionFlags
0x18004b7bd  call    cs:__imp_RaiseException
0x18004b7c3  int     3; Trap to Debugger
0x18004b7c4  mov     rcx, [rbp+30h+var_18]
0x18004b7c8  lea     r8, [rsp+130h+var_108]
0x18004b7cd  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x18004b7d4  call    cs:__imp_RoGetActivationFactory
0x18004b7da  mov     ebx, eax
0x18004b7dc  test    eax, eax
0x18004b7de  jns     short loc_18004B7EE
0x18004b7e0  lea     rcx, [rsp+130h+var_108]
0x18004b7e5  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18004b7ea  mov     eax, ebx
0x18004b7ec  jmp     short loc_18004B84C
0x18004b7ee  mov     rbx, [rsp+130h+var_108]
0x18004b7f3  lea     rcx, [rsp+130h+var_110]
0x18004b7f8  mov     [rsp+130h+var_110], 0
0x18004b801  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18004b806  lea     r8, [rsp+130h+var_110]
0x18004b80b  mov     rcx, rbx
0x18004b80e  lea     rdx, [rsp+130h+var_100]
0x18004b813  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x18004b818  lea     rcx, [rsp+130h+var_110]
0x18004b81d  mov     ebx, eax
0x18004b81f  test    eax, eax
0x18004b821  jns     short loc_18004B82A
0x18004b823  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18004b828  jmp     short loc_18004B7E0
0x18004b82a  mov     rax, [rsp+130h+var_110]
0x18004b82f  mov     [rdi], rax
0x18004b832  mov     [rsp+130h+var_110], 0
0x18004b83b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18004b840  lea     rcx, [rsp+130h+var_108]
0x18004b845  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18004b84a  xor     eax, eax
0x18004b84c  mov     rcx, [rbp+30h+var_10]
0x18004b850  xor     rcx, rsp; StackCookie
0x18004b853  call    __security_check_cookie
0x18004b858  lea     r11, [rsp+130h+var_s0]
0x18004b860  mov     rbx, [r11+10h]
0x18004b864  mov     rdi, [r11+20h]
0x18004b868  mov     rsp, r11
0x18004b86b  pop     rbp
0x18004b86c  retn
```
