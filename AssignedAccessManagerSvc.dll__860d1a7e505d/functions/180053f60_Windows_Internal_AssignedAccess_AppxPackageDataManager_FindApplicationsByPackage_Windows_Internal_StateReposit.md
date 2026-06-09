# Windows::Internal::AssignedAccess::AppxPackageDataManager::FindApplicationsByPackage(Windows::Internal::StateRepository::IPackage *,Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::Application *> * *)

- ea: `0x180053f60`
- end: `0x180054051`
- name: `?FindApplicationsByPackage@AppxPackageDataManager@AssignedAccess@Internal@Windows@@AEAAJPEAUIPackage@StateRepository@34@PEAPEAU?$IVectorView@PEAVApplication@StateRepository@Internal@Windows@@@Collections@Foundation@4@@Z`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800539d8`

## callees

- `0x180006640`
- `0x18000b6b4`
- `0x18000cfe4`
- `0x180053f60`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180053fc1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180053fc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180053fa8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180053fa8`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180053fd8`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180053fd8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::AssignedAccess::AppxPackageDataManager::FindApplicationsByPackage(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  int ActivationFactory; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  __int64 v9; // [rsp+20h] [rbp-38h] BYREF
  HSTRING v10; // [rsp+28h] [rbp-30h] BYREF
  HSTRING_HEADER v11; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *a3 = 0;
  v9 = 0;
  if ( WindowsCreateStringReference(L"Windows.Internal.StateRepository.Application", 0x2Cu, &v11, &v10) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  ActivationFactory = RoGetActivationFactory(v10, &GUID_07adcc9a_e505_48c2_b471_45af8561f6af, &v9);
  v6 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD *))(*(_QWORD *)v9 + 144LL))(v9, a2, a3);
    v6 = ActivationFactory;
    if ( ActivationFactory >= 0 )
    {
      v6 = 0;
      goto LABEL_9;
    }
    v7 = 86;
  }
  else
  {
    v7 = 85;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\appxpackagedatamanager.cpp",
    (const char *)(unsigned int)ActivationFactory,
    v9);
LABEL_9:
  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v9);
  return v6;
}

```

## disassembly

```asm
0x180053f60  mov     r11, rsp
0x180053f63  mov     [r11+8], rbx
0x180053f67  mov     [r11+20h], rsi
0x180053f6b  push    rdi
0x180053f6c  sub     rsp, 50h
0x180053f70  mov     rax, cs:__security_cookie
0x180053f77  xor     rax, rsp
0x180053f7a  mov     [rsp+58h+var_10], rax
0x180053f7f  mov     rdi, r8
0x180053f82  mov     rsi, rdx
0x180053f85  mov     qword ptr [r8], 0
0x180053f8c  mov     qword ptr [r11-38h], 0
0x180053f94  lea     r9, [r11-30h]; string
0x180053f98  lea     r8, [r11-28h]; hstringHeader
0x180053f9c  mov     edx, 2Ch ; ','; length
0x180053fa1  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Application@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x180053fa8  call    cs:__imp_WindowsCreateStringReference
0x180053fae  test    eax, eax
0x180053fb0  jns     short loc_180053FC7
0x180053fb2  xor     r9d, r9d; lpArguments
0x180053fb5  xor     r8d, r8d; nNumberOfArguments
0x180053fb8  lea     edx, [r9+1]; dwExceptionFlags
0x180053fbc  mov     ecx, 0C000000Dh; dwExceptionCode
0x180053fc1  call    cs:__imp_RaiseException
0x180053fc7  lea     r8, [rsp+58h+var_38]
0x180053fcc  lea     rdx, _GUID_07adcc9a_e505_48c2_b471_45af8561f6af
0x180053fd3  mov     rcx, [rsp+58h+var_30]
0x180053fd8  call    cs:__imp_RoGetActivationFactory
0x180053fde  mov     ebx, eax
0x180053fe0  test    eax, eax
0x180053fe2  jns     short loc_180053FEB
0x180053fe4  mov     edx, 55h ; 'U'
0x180053fe9  jmp     short loc_180054010
0x180053feb  mov     rcx, [rsp+58h+var_38]
0x180053ff0  mov     rax, [rcx]
0x180053ff3  mov     r8, rdi
0x180053ff6  mov     rdx, rsi
0x180053ff9  mov     rax, [rax+90h]
0x180054000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054005  mov     ebx, eax
0x180054007  test    eax, eax
0x180054009  jns     short loc_180054026
0x18005400b  mov     edx, 56h ; 'V'; void *
0x180054010  lea     r8, aOnecoreuapBase_63; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180054017  mov     r9d, eax; char *
0x18005401a  mov     rcx, [rsp+58h]; this
0x18005401f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054024  jmp     short loc_180054028
0x180054026  xor     ebx, ebx
0x180054028  lea     rcx, [rsp+58h+var_38]
0x18005402d  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180054032  mov     eax, ebx
0x180054034  mov     rcx, [rsp+58h+var_10]
0x180054039  xor     rcx, rsp; StackCookie
0x18005403c  call    __security_check_cookie
0x180054041  mov     rbx, [rsp+58h+arg_0]
0x180054046  mov     rsi, [rsp+58h+arg_18]
0x18005404b  add     rsp, 50h
0x18005404f  pop     rdi
0x180054050  retn
```
