# Windows::Internal::AssignedAccess::AppxPackageDataManager::GetUser(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Windows::Internal::StateRepository::IUser * *)

- ea: `0x180054150`
- end: `0x180054259`
- name: `?GetUser@AppxPackageDataManager@AssignedAccess@Internal@Windows@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAPEAUIUser@StateRepository@34@@Z`
- size: `265`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800539d8`

## callees

- `0x180006640`
- `0x18000b6b4`
- `0x18000cfe4`
- `0x1800116bc`
- `0x18002001c`
- `0x180054150`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800541a8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800541a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005418f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005418f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800541bf`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800541bf`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Internal::AssignedAccess::AppxPackageDataManager::GetUser(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  int ActivationFactory; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, _QWORD, __int64); // rbx
  __int64 v10; // rax
  __int64 v12; // [rsp+20h] [rbp-58h] BYREF
  __int64 v13; // [rsp+28h] [rbp-50h] BYREF
  HSTRING v14; // [rsp+30h] [rbp-48h] BYREF
  HSTRING_HEADER v15; // [rsp+38h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v12 = 0;
  if ( WindowsCreateStringReference(L"Windows.Internal.StateRepository.User", 0x25u, &v15, &v14) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  ActivationFactory = RoGetActivationFactory(v14, &GUID_84103ccb_2fd7_4d6c_962e_5d8582b4c720, &v12);
  v6 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v8 = v12;
    v9 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v12 + 80LL);
    v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
    v10 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v14, &v13);
    ActivationFactory = v9(v8, *(_QWORD *)(v10 + 24), a3);
    v6 = ActivationFactory;
    if ( ActivationFactory >= 0 )
    {
      v6 = 0;
      goto LABEL_9;
    }
    v7 = 66;
  }
  else
  {
    v7 = 65;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\appxpackagedatamanager.cpp",
    (const char *)(unsigned int)ActivationFactory,
    v12);
LABEL_9:
  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v12);
  return v6;
}

```

## disassembly

```asm
0x180054150  mov     r11, rsp
0x180054153  mov     [r11+8], rbx
0x180054157  push    rbp
0x180054158  push    rsi
0x180054159  push    rdi
0x18005415a  sub     rsp, 60h
0x18005415e  mov     rax, cs:__security_cookie
0x180054165  xor     rax, rsp
0x180054168  mov     [rsp+78h+var_28], rax
0x18005416d  mov     rbp, r8
0x180054170  mov     rsi, rdx
0x180054173  mov     qword ptr [r11-58h], 0
0x18005417b  lea     r9, [r11-48h]; string
0x18005417f  lea     r8, [r11-40h]; hstringHeader
0x180054183  mov     edx, 25h ; '%'; length
0x180054188  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_User@@3QBGB; "Windows.Internal.StateRepository.User"
0x18005418f  call    cs:__imp_WindowsCreateStringReference
0x180054195  test    eax, eax
0x180054197  jns     short loc_1800541AE
0x180054199  xor     r9d, r9d; lpArguments
0x18005419c  xor     r8d, r8d; nNumberOfArguments
0x18005419f  lea     edx, [r9+1]; dwExceptionFlags
0x1800541a3  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800541a8  call    cs:__imp_RaiseException
0x1800541ae  lea     r8, [rsp+78h+var_58]
0x1800541b3  lea     rdx, _GUID_84103ccb_2fd7_4d6c_962e_5d8582b4c720
0x1800541ba  mov     rcx, [rsp+78h+var_48]
0x1800541bf  call    cs:__imp_RoGetActivationFactory
0x1800541c5  mov     ebx, eax
0x1800541c7  test    eax, eax
0x1800541c9  jns     short loc_1800541D2
0x1800541cb  mov     edx, 41h ; 'A'
0x1800541d0  jmp     short loc_180054218
0x1800541d2  mov     rdi, [rsp+78h+var_58]
0x1800541d7  mov     rax, [rdi]
0x1800541da  mov     rbx, [rax+50h]
0x1800541de  mov     rcx, rsi
0x1800541e1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800541e6  mov     [rsp+78h+var_50], rax
0x1800541eb  lea     rdx, [rsp+78h+var_50]
0x1800541f0  lea     rcx, [rsp+78h+var_48]
0x1800541f5  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800541fa  nop
0x1800541fb  mov     r8, rbp
0x1800541fe  mov     rdx, [rax+18h]
0x180054202  mov     rcx, rdi
0x180054205  mov     rax, rbx
0x180054208  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005420d  mov     ebx, eax
0x18005420f  test    eax, eax
0x180054211  jns     short loc_18005422E
0x180054213  mov     edx, 42h ; 'B'; void *
0x180054218  lea     r8, aOnecoreuapBase_63; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005421f  mov     r9d, eax; char *
0x180054222  mov     rcx, [rsp+78h]; this
0x180054227  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005422c  jmp     short loc_180054230
0x18005422e  xor     ebx, ebx
0x180054230  lea     rcx, [rsp+78h+var_58]
0x180054235  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18005423a  mov     eax, ebx
0x18005423c  mov     rcx, [rsp+78h+var_28]
0x180054241  xor     rcx, rsp; StackCookie
0x180054244  call    __security_check_cookie
0x180054249  mov     rbx, [rsp+78h+arg_0]
0x180054251  add     rsp, 60h
0x180054255  pop     rdi
0x180054256  pop     rsi
0x180054257  pop     rbp
0x180054258  retn
```
