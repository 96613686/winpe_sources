# PropertySetHelper::Initialize(void)

- ea: `0x18005b2b4`
- end: `0x18005b3fb`
- name: `?Initialize@PropertySetHelper@@QEAAJXZ`
- size: `327`
- prototype: `__int64 __fastcall(PropertySetHelper *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180099b48`
- `0x1800d5258`

## callees

- `0x180004e38`
- `0x180011618`
- `0x18005b2b4`
- `0x18005b404`
- `0x1800b99f0`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005b305`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005b3a9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005b305`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005b3a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005b2ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005b393`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005b2ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005b393`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005b3cc`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005b3cc`

## string_xrefs

- `0x18005b32c`: `onecoreuap\base\diagnosis\platform\notifications\common\PropertySetHelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PropertySetHelper::Initialize(PropertySetHelper *this)
{
  HRESULT v2; // eax
  int ActivationFactory; // ebx
  __int64 v4; // rdx
  __int64 (__fastcall ***v6)(_QWORD, GUID *, char *); // rdi
  __int64 (__fastcall *v7)(_QWORD, GUID *, char *); // rbx
  HRESULT v8; // eax
  HSTRING v9; // rdi
  HSTRING_HEADER hstringHeader; // [rsp+20h] [rbp-58h] BYREF
  HSTRING string; // [rsp+38h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  string = 0;
  v2 = WindowsCreateStringReference(L"Windows.Foundation.Collections.ValueSet", 0x27u, &hstringHeader, &string);
  if ( v2 < 0 )
  {
    RaiseException(v2, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(
                        (__int64)string,
                        this);
  if ( ActivationFactory < 0 )
  {
    v4 = 18;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\PropertySetHelper.h",
      (const char *)(unsigned int)ActivationFactory,
      (int)hstringHeader.Reserved.Reserved1);
    return (unsigned int)ActivationFactory;
  }
  v6 = *(__int64 (__fastcall ****)(_QWORD, GUID *, char *))this;
  v7 = ***(__int64 (__fastcall ****)(_QWORD, GUID *, char *))this;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 8);
  ActivationFactory = v7(v6, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, (char *)this + 8);
  if ( ActivationFactory < 0 )
  {
    v4 = 19;
    goto LABEL_5;
  }
  string = 0;
  v8 = WindowsCreateStringReference(L"Windows.Foundation.PropertyValue", 0x20u, &hstringHeader, &string);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v9 = string;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 16);
  ActivationFactory = RoGetActivationFactory(v9, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, (char *)this + 16);
  if ( ActivationFactory < 0 )
  {
    v4 = 22;
    goto LABEL_5;
  }
  return 0;
}

```

## disassembly

```asm
0x18005b2b4  push    rbx
0x18005b2b6  push    rsi
0x18005b2b7  push    rdi
0x18005b2b8  push    r14
0x18005b2ba  sub     rsp, 58h
0x18005b2be  mov     rax, cs:__security_cookie
0x18005b2c5  xor     rax, rsp
0x18005b2c8  mov     [rsp+78h+var_38], rax
0x18005b2cd  mov     r14, rcx
0x18005b2d0  mov     [rsp+78h+string], 0
0x18005b2d9  lea     r9, [rsp+78h+string]; string
0x18005b2de  lea     r8, [rsp+78h+hstringHeader]; hstringHeader
0x18005b2e3  mov     edx, 27h ; '''; length
0x18005b2e8  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_ValueSet@@3QBGB; "Windows.Foundation.Collections.ValueSet"
0x18005b2ef  call    cs:__imp_WindowsCreateStringReference
0x18005b2f5  test    eax, eax
0x18005b2f7  jns     short loc_18005B30C
0x18005b2f9  xor     r9d, r9d; lpArguments
0x18005b2fc  xor     r8d, r8d; nNumberOfArguments
0x18005b2ff  lea     edx, [r9+1]; dwExceptionFlags
0x18005b303  mov     ecx, eax; dwExceptionCode
0x18005b305  call    cs:__imp_RaiseException
0x18005b30b  int     3; Trap to Debugger
0x18005b30c  mov     rdx, r14
0x18005b30f  mov     rcx, [rsp+78h+string]
0x18005b314  call    ??$ActivateInstance@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>)
0x18005b319  mov     ebx, eax
0x18005b31b  test    eax, eax
0x18005b31d  jns     short loc_18005B33F
0x18005b31f  mov     edx, 12h; void *
0x18005b324  mov     rcx, [rsp+78h]; this
0x18005b329  mov     r9d, ebx; char *
0x18005b32c  lea     r8, aOnecoreuapBase_48; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18005b333  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b338  mov     eax, ebx
0x18005b33a  jmp     loc_18005B3E4
0x18005b33f  mov     rdi, [r14]
0x18005b342  mov     rax, [rdi]
0x18005b345  mov     rbx, [rax]
0x18005b348  lea     rcx, [r14+8]
0x18005b34c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005b351  lea     r8, [r14+8]
0x18005b355  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18005b35c  mov     rcx, rdi
0x18005b35f  mov     rax, rbx
0x18005b362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b367  mov     ebx, eax
0x18005b369  test    eax, eax
0x18005b36b  jns     short loc_18005B374
0x18005b36d  mov     edx, 13h
0x18005b372  jmp     short loc_18005B324
0x18005b374  mov     [rsp+78h+string], 0
0x18005b37d  lea     r9, [rsp+78h+string]; string
0x18005b382  lea     r8, [rsp+78h+hstringHeader]; hstringHeader
0x18005b387  mov     edx, 20h ; ' '; length
0x18005b38c  lea     rcx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x18005b393  call    cs:__imp_WindowsCreateStringReference
0x18005b399  test    eax, eax
0x18005b39b  jns     short loc_18005B3B0
0x18005b39d  xor     r9d, r9d; lpArguments
0x18005b3a0  xor     r8d, r8d; nNumberOfArguments
0x18005b3a3  lea     edx, [r9+1]; dwExceptionFlags
0x18005b3a7  mov     ecx, eax; dwExceptionCode
0x18005b3a9  call    cs:__imp_RaiseException
0x18005b3af  int     3; Trap to Debugger
0x18005b3b0  mov     rdi, [rsp+78h+string]
0x18005b3b5  lea     rcx, [r14+10h]
0x18005b3b9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005b3be  lea     r8, [r14+10h]
0x18005b3c2  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x18005b3c9  mov     rcx, rdi
0x18005b3cc  call    cs:__imp_RoGetActivationFactory
0x18005b3d2  mov     ebx, eax
0x18005b3d4  test    eax, eax
0x18005b3d6  jns     short loc_18005B3E2
0x18005b3d8  mov     edx, 16h
0x18005b3dd  jmp     loc_18005B324
0x18005b3e2  xor     eax, eax
0x18005b3e4  mov     rcx, [rsp+78h+var_38]
0x18005b3e9  xor     rcx, rsp; StackCookie
0x18005b3ec  call    __security_check_cookie
0x18005b3f1  add     rsp, 58h
0x18005b3f5  pop     r14
0x18005b3f7  pop     rdi
0x18005b3f8  pop     rsi
0x18005b3f9  pop     rbx
0x18005b3fa  retn
```
