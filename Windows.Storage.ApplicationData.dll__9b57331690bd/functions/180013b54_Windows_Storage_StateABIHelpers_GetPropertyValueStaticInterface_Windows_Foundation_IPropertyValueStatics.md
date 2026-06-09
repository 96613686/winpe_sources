# Windows::Storage::StateABIHelpers::GetPropertyValueStaticInterface(Windows::Foundation::IPropertyValueStatics * *)

- ea: `0x180013b54`
- end: `0x180013d27`
- name: `?GetPropertyValueStaticInterface@StateABIHelpers@Storage@Windows@@YAJPEAPEAUIPropertyValueStatics@Foundation@3@@Z`
- size: `467`
- prototype: `HRESULT __fastcall(Windows::Foundation::IPropertyValueStatics **propertyValueStaticInterface)`
- caller_count: `6`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180013730`
- `0x1800137d0`
- `0x1800138c0`
- `0x180035c28`
- `0x180036abc`
- `0x180037c60`

## callees

- `0x180003820`
- `0x1800093d0`
- `0x180009778`
- `0x180013b54`
- `0x180041620`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180013ce4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180013ce4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013b9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013b9c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180013bd9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180013bd9`

## string_xrefs

- `0x180013c86`: `onecoreuap\base\appmodel\statemanager\winrt\lib\stateabicommonhelpers.cpp`
- `0x180013d02`: `onecoreuap\base\appmodel\statemanager\winrt\lib\stateabicommonhelpers.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Storage::StateABIHelpers::GetPropertyValueStaticInterface(
        Windows::Foundation::IPropertyValueStatics **propertyValueStaticInterface)
{
  HRESULT ActivationFactory; // ebx
  IActivationFactory *v3; // rbx
  Windows::Foundation::IPropertyValueStatics *v4; // rcx
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rsi
  Windows::Foundation::IPropertyValueStatics *v6; // rax
  IActivationFactory *v7; // rcx
  Windows::Foundation::IPropertyValueStatics *ptr; // rcx
  IActivationFactory *v10; // rcx
  Microsoft::WRL::ComPtr<IActivationFactory> genericActivationFactoryInterface; // [rsp+30h] [rbp-48h] BYREF
  Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics> propertyValueFactoryInterface; // [rsp+38h] [rbp-40h] BYREF
  HSTRING string; // [rsp+40h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-30h] BYREF
  void *retaddr; // [rsp+98h] [rbp+20h]

  *propertyValueStaticInterface = 0;
  genericActivationFactoryInterface.ptr_ = 0;
  propertyValueFactoryInterface.ptr_ = 0;
  if ( WindowsCreateStringReference(RuntimeClass_Windows_Foundation_PropertyValue, 0x20u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  ActivationFactory = RoGetActivationFactory(
                        string,
                        &GUID_00000035_0000_0000_c000_000000000046,
                        &genericActivationFactoryInterface);
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x62u,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabicommonhelpers.cpp",
      ActivationFactory,
      "GetActivationFactory");
    ptr = propertyValueFactoryInterface.ptr_;
    if ( propertyValueFactoryInterface.ptr_ )
    {
      propertyValueFactoryInterface.ptr_ = 0;
      ptr->Release(ptr);
    }
    v10 = genericActivationFactoryInterface.ptr_;
    if ( genericActivationFactoryInterface.ptr_ )
    {
      genericActivationFactoryInterface.ptr_ = 0;
      v10->Release(v10);
    }
    return (unsigned int)ActivationFactory;
  }
  v3 = genericActivationFactoryInterface.ptr_;
  v4 = propertyValueFactoryInterface.ptr_;
  QueryInterface = genericActivationFactoryInterface.ptr_->QueryInterface;
  if ( propertyValueFactoryInterface.ptr_ )
  {
    propertyValueFactoryInterface.ptr_ = 0;
    v4->Release(v4);
  }
  ActivationFactory = QueryInterface(
                        v3,
                        &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858,
                        (void **)&propertyValueFactoryInterface.ptr_);
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x65u,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabicommonhelpers.cpp",
      ActivationFactory,
      "As");
    Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Storage::IApplicationDataContainer> *)&propertyValueFactoryInterface);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)&genericActivationFactoryInterface);
    return (unsigned int)ActivationFactory;
  }
  v6 = propertyValueFactoryInterface.ptr_;
  v7 = genericActivationFactoryInterface.ptr_;
  propertyValueFactoryInterface.ptr_ = 0;
  *propertyValueStaticInterface = v6;
  if ( v7 )
  {
    genericActivationFactoryInterface.ptr_ = 0;
    v7->Release(v7);
  }
  return 0;
}

```

## disassembly

```asm
0x180013b54  push    rbp
0x180013b56  push    rbx
0x180013b57  push    rsi
0x180013b58  push    rdi
0x180013b59  mov     rbp, rsp
0x180013b5c  sub     rsp, 78h
0x180013b60  mov     rax, cs:__security_cookie
0x180013b67  xor     rax, rsp
0x180013b6a  mov     [rbp+var_18], rax
0x180013b6e  mov     rdi, propertyValueStaticInterface
0x180013b71  mov     qword ptr [propertyValueStaticInterface], 0
0x180013b78  lea     propertyValueStaticInterface, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; sourceString
0x180013b7f  mov     [rbp+genericActivationFactoryInterface.ptr_], 0
0x180013b87  lea     r9, [rbp+string]; string
0x180013b8b  mov     [rbp+propertyValueFactoryInterface.ptr_], 0
0x180013b93  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180013b97  mov     edx, 20h ; ' '; length
0x180013b9c  call    cs:__imp_WindowsCreateStringReference
0x180013ba2  test    eax, eax
0x180013ba4  js      loc_180013CD5
0x180013baa  mov     propertyValueStaticInterface, [rbp+genericActivationFactoryInterface.ptr_]
0x180013bae  mov     rbx, [rbp+string]
0x180013bb2  test    propertyValueStaticInterface, propertyValueStaticInterface
0x180013bb5  jz      short loc_180013BCB
0x180013bb7  mov     [rbp+genericActivationFactoryInterface.ptr_], 0
0x180013bbf  mov     rax, [propertyValueStaticInterface]
0x180013bc2  mov     rax, [rax+10h]
0x180013bc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013bcb  lea     r8, [rbp+genericActivationFactoryInterface]
0x180013bcf  mov     propertyValueStaticInterface, rbx
0x180013bd2  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x180013bd9  call    cs:__imp_RoGetActivationFactory
0x180013bdf  mov     ebx, eax
0x180013be1  test    eax, eax
0x180013be3  js      loc_180013C73
0x180013be9  mov     rbx, [rbp+genericActivationFactoryInterface.ptr_]
0x180013bed  mov     propertyValueStaticInterface, [rbp+propertyValueFactoryInterface.ptr_]
0x180013bf1  mov     rax, [rbx]
0x180013bf4  mov     rsi, [rax]
0x180013bf7  test    propertyValueStaticInterface, propertyValueStaticInterface
0x180013bfa  jz      short loc_180013C10
0x180013bfc  mov     [rbp+propertyValueFactoryInterface.ptr_], 0
0x180013c04  mov     rdx, [propertyValueStaticInterface]
0x180013c07  mov     rax, [rdx+10h]
0x180013c0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c10  lea     r8, [rbp+propertyValueFactoryInterface]
0x180013c14  mov     propertyValueStaticInterface, rbx
0x180013c17  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x180013c1e  mov     rax, rsi
0x180013c21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c26  mov     ebx, eax
0x180013c28  test    eax, eax
0x180013c2a  js      loc_180013CEF
0x180013c30  mov     rax, [rbp+propertyValueFactoryInterface.ptr_]
0x180013c34  mov     propertyValueStaticInterface, [rbp+genericActivationFactoryInterface.ptr_]
0x180013c38  mov     [rbp+propertyValueFactoryInterface.ptr_], 0
0x180013c40  mov     [rdi], rax
0x180013c43  test    propertyValueStaticInterface, propertyValueStaticInterface
0x180013c46  jz      short loc_180013C5C
0x180013c48  mov     [rbp+genericActivationFactoryInterface.ptr_], 0
0x180013c50  mov     rax, [propertyValueStaticInterface]
0x180013c53  mov     rax, [rax+10h]
0x180013c57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c5c  xor     eax, eax
0x180013c5e  mov     propertyValueStaticInterface, [rbp+var_18]
0x180013c62  xor     propertyValueStaticInterface, rsp; StackCookie
0x180013c65  call    __security_check_cookie
0x180013c6a  add     rsp, 78h
0x180013c6e  pop     rdi
0x180013c6f  pop     rsi
0x180013c70  pop     rbx
0x180013c71  pop     rbp
0x180013c72  retn
0x180013c73  mov     propertyValueStaticInterface, [rbp+20h]; callerReturnAddress
0x180013c77  lea     rax, aGetactivationf_0; "GetActivationFactory"
0x180013c7e  mov     r9d, ebx; hr
0x180013c81  mov     [rsp+78h+formatString], rax; formatString
0x180013c86  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\appmodel\\statemanage"...
0x180013c8d  mov     edx, 62h ; 'b'; lineNumber
0x180013c92  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180013c97  mov     propertyValueStaticInterface, [rbp+propertyValueFactoryInterface.ptr_]
0x180013c9b  test    propertyValueStaticInterface, propertyValueStaticInterface
0x180013c9e  jz      short loc_180013CB4
0x180013ca0  mov     [rbp+propertyValueFactoryInterface.ptr_], 0
0x180013ca8  mov     rax, [propertyValueStaticInterface]
0x180013cab  mov     rax, [rax+10h]
0x180013caf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013cb4  mov     propertyValueStaticInterface, [rbp+genericActivationFactoryInterface.ptr_]
0x180013cb8  test    propertyValueStaticInterface, propertyValueStaticInterface
0x180013cbb  jz      short loc_180013CD1
0x180013cbd  mov     [rbp+genericActivationFactoryInterface.ptr_], 0
0x180013cc5  mov     rax, [propertyValueStaticInterface]
0x180013cc8  mov     rax, [rax+10h]
0x180013ccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013cd1  mov     eax, ebx
0x180013cd3  jmp     short loc_180013C5E
0x180013cd5  xor     r9d, r9d; lpArguments
0x180013cd8  xor     r8d, r8d; nNumberOfArguments
0x180013cdb  mov     ecx, 0C000000Dh; dwExceptionCode
0x180013ce0  lea     edx, [r9+1]; dwExceptionFlags
0x180013ce4  call    cs:__imp_RaiseException
0x180013cea  jmp     loc_180013BAA
0x180013cef  mov     propertyValueStaticInterface, [rbp+20h]; callerReturnAddress
0x180013cf3  lea     rax, aAs; "As"
0x180013cfa  mov     r9d, ebx; hr
0x180013cfd  mov     [rsp+78h+formatString], rax; formatString
0x180013d02  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\appmodel\\statemanage"...
0x180013d09  mov     edx, 65h ; 'e'; lineNumber
0x180013d0e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180013d13  lea     propertyValueStaticInterface, [rbp+propertyValueFactoryInterface]; this
0x180013d17  call    ?InternalRelease@?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>::InternalRelease(void)
0x180013d1c  lea     propertyValueStaticInterface, [rbp+genericActivationFactoryInterface]; this
0x180013d20  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180013d25  jmp     short loc_180013CD1
```
