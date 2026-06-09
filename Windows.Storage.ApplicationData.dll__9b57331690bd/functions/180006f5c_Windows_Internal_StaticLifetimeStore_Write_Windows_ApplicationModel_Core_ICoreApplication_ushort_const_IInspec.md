# Windows::Internal::StaticLifetimeStore::Write(Windows::ApplicationModel::Core::ICoreApplication *,ushort const *,IInspectable *,uchar)

- ea: `0x180006f5c`
- end: `0x18000709f`
- name: `?Write@StaticLifetimeStore@Internal@Windows@@SAJPEAUICoreApplication@Core@ApplicationModel@3@PEBGPEAUIInspectable@@E@Z`
- size: `323`
- prototype: `HRESULT __fastcall(Windows::ApplicationModel::Core::ICoreApplication *coreApp, const wchar_t *propName, IInspectable *pInspectable, unsigned __int8 coreApp)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001e9b4`

## callees

- `0x180003820`
- `0x180006f5c`
- `0x180007440`
- `0x180041620`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000701b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000701b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000702e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000702e`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StaticLifetimeStore::Write(
        Windows::ApplicationModel::Core::ICoreApplication *coreApp,
        const wchar_t *propName,
        IInspectable *pInspectable,
        unsigned __int8 a4)
{
  unsigned __int8 v7; // dl
  int PropertyBagForThread; // eax
  Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *ptr; // rdi
  int v10; // ebx
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rbx
  Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *v12; // rsi
  unsigned __int64 v13; // rbx
  HRESULT (__fastcall *Insert)(Windows::Foundation::Collections::IMap_impl<HSTRING__ *,IInspectable *> *, HSTRING__ *, IInspectable *, unsigned __int8 *); // r15
  Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *v15; // rcx
  unsigned __int8 replaced[8]; // [rsp+30h] [rbp-40h] BYREF
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> > spMap; // [rsp+38h] [rbp-38h] BYREF
  HSTRING string; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF

  spMap.ptr_ = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)&spMap);
  PropertyBagForThread = Windows::Internal::StaticLifetimeStore::GetPropertyBagForThread(
                           coreApp,
                           v7,
                           (Windows::Foundation::Collections::IPropertySet **)&spMap);
  ptr = spMap.ptr_;
  v10 = PropertyBagForThread;
  if ( PropertyBagForThread >= 0 )
  {
    spMap.ptr_ = 0;
    QueryInterface = ptr->QueryInterface;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)&spMap);
    v10 = QueryInterface(ptr, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, (void **)&spMap.ptr_);
    if ( v10 >= 0 )
    {
      v12 = spMap.ptr_;
      v13 = -1;
      replaced[0] = 0;
      Insert = spMap.ptr_->Insert;
      do
        ++v13;
      while ( propName[v13] );
      if ( v13 > 0xFFFFFFFF )
      {
        LODWORD(v13) = -1;
        RaiseException(0xC000000D, 1u, 0, 0);
      }
      WindowsCreateStringReference(propName, v13, &hstringHeader, &string);
      v10 = Insert(v12, string, pInspectable, replaced);
    }
    v15 = spMap.ptr_;
    if ( spMap.ptr_ )
    {
      spMap.ptr_ = 0;
      v15->Release(v15);
    }
  }
  if ( ptr )
    ptr->Release(ptr);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180006f5c  mov     [rsp-38h+arg_18], rbx
0x180006f61  push    rbp
0x180006f62  push    rsi
0x180006f63  push    rdi
0x180006f64  push    r12
0x180006f66  push    r13
0x180006f68  push    r14
0x180006f6a  push    r15
0x180006f6c  mov     rbp, rsp
0x180006f6f  sub     rsp, 70h
0x180006f73  mov     rax, cs:__security_cookie
0x180006f7a  xor     rax, rsp
0x180006f7d  mov     [rbp+var_10], rax
0x180006f81  mov     rbx, coreApp
0x180006f84  xor     r13d, r13d
0x180006f87  lea     coreApp, [rbp+spMap]; this
0x180006f8b  mov     [rbp+spMap.ptr_], r13
0x180006f8f  mov     r12, pInspectable
0x180006f92  mov     r14, propName
0x180006f95  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180006f9a  lea     pInspectable, [rbp+spMap]; coreApp
0x180006f9e  mov     coreApp, rbx; coreApp
0x180006fa1  call    ?GetPropertyBagForThread@StaticLifetimeStore@Internal@Windows@@CAJPEAUICoreApplication@Core@ApplicationModel@3@EPEAPEAUIPropertySet@Collections@Foundation@3@@Z; Windows::Internal::StaticLifetimeStore::GetPropertyBagForThread(Windows::ApplicationModel::Core::ICoreApplication *,uchar,Windows::Foundation::Collections::IPropertySet * *)
0x180006fa6  mov     rdi, [rbp+spMap.ptr_]
0x180006faa  mov     ebx, eax
0x180006fac  test    eax, eax
0x180006fae  js      loc_180007065
0x180006fb4  mov     [rbp+spMap.ptr_], r13
0x180006fb8  lea     coreApp, [rbp+spMap]; this
0x180006fbc  mov     rax, [rdi]
0x180006fbf  mov     rbx, [rax]
0x180006fc2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180006fc7  lea     pInspectable, [rbp+spMap]
0x180006fcb  mov     coreApp, rdi
0x180006fce  lea     propName, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180006fd5  mov     rax, rbx
0x180006fd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fdd  mov     ebx, eax
0x180006fdf  test    eax, eax
0x180006fe1  js      short loc_18000704C
0x180006fe3  mov     rsi, [rbp+spMap.ptr_]
0x180006fe7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180006feb  mov     [rbp+replaced], r13b
0x180006fef  mov     rax, [rsi]
0x180006ff2  mov     r15, [rax+50h]
0x180006ff6  inc     rbx
0x180006ff9  cmp     [r14+rbx*2], r13w
0x180006ffe  jnz     short loc_180006FF6
0x180007000  mov     eax, 0FFFFFFFFh
0x180007005  cmp     rbx, rax
0x180007008  jbe     short loc_180007021
0x18000700a  xor     r9d, r9d; lpArguments
0x18000700d  xor     r8d, r8d; nNumberOfArguments
0x180007010  mov     ecx, 0C000000Dh; dwExceptionCode
0x180007015  mov     ebx, eax
0x180007017  lea     edx, [r9+1]; dwExceptionFlags
0x18000701b  call    cs:__imp_RaiseException
0x180007021  lea     r9, [rbp+string]; string
0x180007025  mov     edx, ebx; length
0x180007027  lea     pInspectable, [rbp+hstringHeader]; hstringHeader
0x18000702b  mov     coreApp, r14; sourceString
0x18000702e  call    cs:__imp_WindowsCreateStringReference
0x180007034  mov     propName, [rbp+string]
0x180007038  lea     r9, [rbp+replaced]
0x18000703c  mov     pInspectable, r12
0x18000703f  mov     coreApp, rsi
0x180007042  mov     rax, r15
0x180007045  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000704a  mov     ebx, eax
0x18000704c  mov     coreApp, [rbp+spMap.ptr_]
0x180007050  test    coreApp, coreApp
0x180007053  jz      short loc_180007065
0x180007055  mov     [rbp+spMap.ptr_], r13
0x180007059  mov     rax, [coreApp]
0x18000705c  mov     rax, [rax+10h]
0x180007060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007065  test    rdi, rdi
0x180007068  jz      short loc_180007079
0x18000706a  mov     rax, [rdi]
0x18000706d  mov     coreApp, rdi
0x180007070  mov     rax, [rax+10h]
0x180007074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007079  mov     eax, ebx
0x18000707b  mov     coreApp, [rbp+var_10]
0x18000707f  xor     coreApp, rsp; StackCookie
0x180007082  call    __security_check_cookie
0x180007087  mov     rbx, [rsp+70h+arg_18]
0x18000708f  add     rsp, 70h
0x180007093  pop     r15
0x180007095  pop     r14
0x180007097  pop     r13
0x180007099  pop     r12
0x18000709b  pop     rdi
0x18000709c  pop     rsi
0x18000709d  pop     rbp
0x18000709e  retn
```
