# Windows::Internal::AssignedAccess::AppxPackageDataManager::FindPackagesByUser(Windows::Internal::StateRepository::IUser *,Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::Package *> * *)

- ea: `0x180054058`
- end: `0x180054149`
- name: `?FindPackagesByUser@AppxPackageDataManager@AssignedAccess@Internal@Windows@@AEAAJPEAUIUser@StateRepository@34@PEAPEAU?$IVectorView@PEAVPackage@StateRepository@Internal@Windows@@@Collections@Foundation@4@@Z`
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
- `0x180054058`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800540b9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800540b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800540a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800540a0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800540d0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800540d0`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AssignedAccess::AppxPackageDataManager::FindPackagesByUser(
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
  if ( WindowsCreateStringReference(L"Windows.Internal.StateRepository.Package", 0x28u, &v11, &v10) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  ActivationFactory = RoGetActivationFactory(v10, &GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419, &v9);
  v6 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD *))(*(_QWORD *)v9 + 432LL))(v9, a2, a3);
    v6 = ActivationFactory;
    if ( ActivationFactory >= 0 )
    {
      v6 = 0;
      goto LABEL_9;
    }
    v7 = 76;
  }
  else
  {
    v7 = 75;
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
0x180054058  mov     r11, rsp
0x18005405b  mov     [r11+8], rbx
0x18005405f  mov     [r11+20h], rsi
0x180054063  push    rdi
0x180054064  sub     rsp, 50h
0x180054068  mov     rax, cs:__security_cookie
0x18005406f  xor     rax, rsp
0x180054072  mov     [rsp+58h+var_10], rax
0x180054077  mov     rdi, r8
0x18005407a  mov     rsi, rdx
0x18005407d  mov     qword ptr [r8], 0
0x180054084  mov     qword ptr [r11-38h], 0
0x18005408c  lea     r9, [r11-30h]; string
0x180054090  lea     r8, [r11-28h]; hstringHeader
0x180054094  mov     edx, 28h ; '('; length
0x180054099  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Package@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x1800540a0  call    cs:__imp_WindowsCreateStringReference
0x1800540a6  test    eax, eax
0x1800540a8  jns     short loc_1800540BF
0x1800540aa  xor     r9d, r9d; lpArguments
0x1800540ad  xor     r8d, r8d; nNumberOfArguments
0x1800540b0  lea     edx, [r9+1]; dwExceptionFlags
0x1800540b4  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800540b9  call    cs:__imp_RaiseException
0x1800540bf  lea     r8, [rsp+58h+var_38]
0x1800540c4  lea     rdx, _GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419
0x1800540cb  mov     rcx, [rsp+58h+var_30]
0x1800540d0  call    cs:__imp_RoGetActivationFactory
0x1800540d6  mov     ebx, eax
0x1800540d8  test    eax, eax
0x1800540da  jns     short loc_1800540E3
0x1800540dc  mov     edx, 4Bh ; 'K'
0x1800540e1  jmp     short loc_180054108
0x1800540e3  mov     rcx, [rsp+58h+var_38]
0x1800540e8  mov     rax, [rcx]
0x1800540eb  mov     r8, rdi
0x1800540ee  mov     rdx, rsi
0x1800540f1  mov     rax, [rax+1B0h]
0x1800540f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800540fd  mov     ebx, eax
0x1800540ff  test    eax, eax
0x180054101  jns     short loc_18005411E
0x180054103  mov     edx, 4Ch ; 'L'; void *
0x180054108  lea     r8, aOnecoreuapBase_63; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005410f  mov     r9d, eax; char *
0x180054112  mov     rcx, [rsp+58h]; this
0x180054117  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005411c  jmp     short loc_180054120
0x18005411e  xor     ebx, ebx
0x180054120  lea     rcx, [rsp+58h+var_38]
0x180054125  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18005412a  mov     eax, ebx
0x18005412c  mov     rcx, [rsp+58h+var_10]
0x180054131  xor     rcx, rsp; StackCookie
0x180054134  call    __security_check_cookie
0x180054139  mov     rbx, [rsp+58h+arg_0]
0x18005413e  mov     rsi, [rsp+58h+arg_18]
0x180054143  add     rsp, 50h
0x180054147  pop     rdi
0x180054148  retn
```
