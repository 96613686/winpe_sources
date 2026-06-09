# SystemSettings::WorkAccess::MamUpgradeToMdmLink::IsApplicable(uchar *)

- ea: `0x180026be8`
- end: `0x180026fde`
- name: `?IsApplicable@MamUpgradeToMdmLink@WorkAccess@SystemSettings@@AEAAJPEAE@Z`
- size: `1014`
- prototype: `__int64 __fastcall(SystemSettings::WorkAccess::MamUpgradeToMdmLink *__hidden this, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180029660`

## callees

- `0x180005490`
- `0x1800096ec`
- `0x180009eac`
- `0x1800208f8`
- `0x1800236d8`
- `0x1800236fc`
- `0x180025450`
- `0x1800257a4`
- `0x180026be8`
- `0x180027a58`
- `0x180029708`
- `0x180029764`
- `0x180029e2c`
- `0x1800433e8`
- `0x18004862c`
- `0x18004e190`
- `0x180052010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180026e3c`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180026e3c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180026e66`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180026e66`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026e4f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026e4f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180026da2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180026da2`
- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x180026c6c`
- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x180026c6c`
- `MDMRegistration!IsMdmUxWithoutAadAllowed` at `0x180026f15`
- `MDMRegistration!IsMdmUxWithoutAadAllowed` at `0x180026f15`

## string_xrefs

- `0x180026c16`: `shellcommon\shell\settingshandlers\workaccess\lib\connectworkschoolaccountsetting.cpp`
- `0x180026cfc`: `shellcommon\shell\settingshandlers\workaccess\lib\connectworkschoolaccountsetting.cpp`
- `0x180026d55`: `shellcommon\shell\settingshandlers\workaccess\lib\connectworkschoolaccountsetting.cpp`
- `0x180026ddd`: `shellcommon\shell\settingshandlers\workaccess\lib\connectworkschoolaccountsetting.cpp`
- `0x180026eab`: `shellcommon\shell\settingshandlers\workaccess\lib\connectworkschoolaccountsetting.cpp`
- `0x180026f2f`: `shellcommon\shell\settingshandlers\workaccess\lib\connectworkschoolaccountsetting.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::WorkAccess::MamUpgradeToMdmLink::IsApplicable(
        SystemSettings::WorkAccess::MamUpgradeToMdmLink *this,
        bool *a2)
{
  SystemSettings::WorkAccess *v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // rdx
  int v8; // eax
  __int64 DatabaseManagerInstance; // rbx
  __int64 (__fastcall *v10)(__int64, __int64, __int64 *); // rdi
  int v11; // eax
  __int64 v12; // rdx
  __int64 (__fastcall *v13)(__int64, __int64 *); // rdi
  __int64 v14; // rbx
  __int64 (__fastcall *v15)(__int64, LPCWCH *); // rdi
  int CurrentUserSidString; // eax
  __int64 v17; // rdx
  int ConfigManagerData; // eax
  __int64 v19; // rdx
  size_t v20; // rdx
  size_t v21; // r15
  int v22; // edi
  size_t v23; // rdx
  size_t v24; // r15
  size_t v25; // r15
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v27; // rax
  unsigned __int16 *v28; // rbx
  int v29; // eax
  unsigned int v30; // edi
  int v31; // eax
  __int64 v32; // rdx
  int bIgnoreCase; // [rsp+20h] [rbp-40h]
  int bIgnoreCasea; // [rsp+20h] [rbp-40h]
  int bIgnoreCaseb; // [rsp+20h] [rbp-40h]
  wchar_t *Source; // [rsp+30h] [rbp-30h] BYREF
  wchar_t *v37; // [rsp+38h] [rbp-28h] BYREF
  __int64 v38; // [rsp+40h] [rbp-20h] BYREF
  __int64 v39; // [rsp+48h] [rbp-18h] BYREF
  _QWORD v40[2]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  int v42; // [rsp+A8h] [rbp+48h] BYREF
  LPCWCH lpString1; // [rsp+B0h] [rbp+50h] BYREF
  LPCWCH lpString2; // [rsp+B8h] [rbp+58h] BYREF

  *a2 = 0;
  v5 = SystemSettings::WorkAccess::CEnrollmentHelper::PopulateIDs();
  if ( (v5 & 0x80000000) != 0 )
  {
    v6 = 522;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\connectworkschoolaccountsetting.cpp",
      (const char *)v5,
      bIgnoreCase);
    return v5;
  }
  v42 = 1;
  if ( !SystemSettings::WorkAccess::IsDesktopSKU(v4) )
    goto LABEL_9;
  v8 = LUAIsUserUACAdmin(&v42);
  v5 = v8 | 0x10000000;
  if ( v8 < 0 )
  {
    v6 = 528;
    goto LABEL_3;
  }
  if ( v42 )
  {
LABEL_9:
    v39 = 0;
    v38 = 0;
    DatabaseManagerInstance = GetDatabaseManagerInstance();
    v10 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)DatabaseManagerInstance + 16LL);
    v39 = 0;
    v11 = v10(DatabaseManagerInstance, 5, &v39);
    v5 = v11;
    if ( v11 < 0 )
    {
      v12 = 537;
LABEL_13:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\connectworkschoolaccountsetting.cpp",
        (const char *)(unsigned int)v11,
        bIgnoreCase);
LABEL_36:
      wil::com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>::~com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>(&v38);
      wil::com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>::~com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>(&v39);
      return v5;
    }
    v13 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v39 + 24LL);
    v38 = 0;
    v11 = v13(v39, &v38);
    v5 = v11;
    if ( v11 < 0 )
    {
      v12 = 538;
      goto LABEL_13;
    }
    v14 = v38;
    if ( v38 )
    {
      lpString2 = 0;
      lpString1 = 0;
      v15 = *(__int64 (__fastcall **)(__int64, LPCWCH *))(*(_QWORD *)v38 + 112LL);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &lpString1,
        0);
      CurrentUserSidString = v15(v14, &lpString1);
      v5 = CurrentUserSidString;
      if ( CurrentUserSidString < 0 )
      {
        v17 = 544;
LABEL_17:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v17,
          (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\connectworkschoolaccountsetting.cpp",
          (const char *)(unsigned int)CurrentUserSidString,
          bIgnoreCase);
LABEL_35:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpString1);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpString2);
        goto LABEL_36;
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &lpString2,
        0);
      CurrentUserSidString = GetCurrentUserSidString((LPWSTR *)&lpString2);
      v5 = CurrentUserSidString;
      if ( CurrentUserSidString < 0 )
      {
        v17 = 545;
        goto LABEL_17;
      }
      if ( CompareStringOrdinal(lpString1, -1, lpString2, -1, 0) == 2 )
      {
        Source = 0;
        v37 = 0;
        ConfigManagerData = SystemSettings::WorkAccess::MamUpgradeToMdmLink::GetConfigManagerData(
                              this,
                              L"./Vendor/MSFT/DMClient/Provider/%s/UPN",
                              &Source);
        v5 = ConfigManagerData;
        if ( ConfigManagerData < 0 )
        {
          v19 = 551;
LABEL_23:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v19,
            (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\connectworkschoolaccountsetting.cpp",
            (const char *)(unsigned int)ConfigManagerData,
            bIgnoreCasea);
LABEL_34:
          CTSmartObj<unsigned short *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(&v37);
          CTSmartObj<unsigned short *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(&Source);
          goto LABEL_35;
        }
        ConfigManagerData = SystemSettings::WorkAccess::MamUpgradeToMdmLink::GetConfigManagerData(
                              this,
                              L"./Vendor/MSFT/DMClient/Provider/%s/ManagementServerToUpgradeTo",
                              &v37);
        v5 = ConfigManagerData;
        if ( ConfigManagerData < 0 )
        {
          v19 = 552;
          goto LABEL_23;
        }
        v21 = wcsnlen_s(Source, v20);
        v22 = (int)v37;
        v24 = wcsnlen_s(v37, v23) + v21;
        v25 = wcsnlen(L"ms-cxh://mosetmamconnecttowork?mode=mdm&username=%s&servername=%s", 0x7FFFFFFFu) + v24;
        ProcessHeap = GetProcessHeap();
        v27 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 2 * v25);
        v28 = v27;
        v40[0] = v27;
        if ( v27 )
        {
          bIgnoreCaseb = v22;
          v29 = StringCchPrintfW(
                  v27,
                  v25 + 1,
                  L"ms-cxh://mosetmamconnecttowork?mode=mdm&username=%s&servername=%s",
                  Source);
          v30 = v29;
          if ( v29 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x230,
              (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\connectworkschoolaccountsetting.cpp",
              (const char *)(unsigned int)v29,
              bIgnoreCaseb);
            CTSmartObj<unsigned short *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(v40);
            CTSmartObj<unsigned short *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(&v37);
            CTSmartObj<unsigned short *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(&Source);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpString1);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpString2);
            v5 = v30;
            goto LABEL_36;
          }
          v31 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                  (char *)this + 256,
                  v28,
                  -1);
          v5 = v31;
          if ( v31 < 0 )
          {
            v32 = 561;
LABEL_33:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v32,
              (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\connectworkschoolaccountsetting.cpp",
              (const char *)(unsigned int)v31,
              bIgnoreCaseb);
            CTSmartObj<unsigned short *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(v40);
            goto LABEL_34;
          }
          v42 = 0;
          v31 = IsMdmUxWithoutAadAllowed(&v42);
          v5 = v31;
          if ( v31 < 0 )
          {
            v32 = 564;
            goto LABEL_33;
          }
          *a2 = v42 != 0;
        }
        CTSmartObj<unsigned short *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(v40);
        CTSmartObj<unsigned short *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(&v37);
        CTSmartObj<unsigned short *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(&Source);
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpString1);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpString2);
    }
    wil::com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>::~com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>(&v38);
    wil::com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>::~com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>(&v39);
  }
  return 0;
}

```

## disassembly

```asm
0x180026be8  push    rbp
0x180026bea  push    rbx
0x180026beb  push    rsi
0x180026bec  push    rdi
0x180026bed  push    r12
0x180026bef  push    r14
0x180026bf1  push    r15
0x180026bf3  mov     rbp, rsp
0x180026bf6  sub     rsp, 60h
0x180026bfa  mov     r14, rdx
0x180026bfd  mov     rsi, rcx
0x180026c00  xor     r12d, r12d
0x180026c03  mov     [rdx], r12b
0x180026c06  call    ?PopulateIDs@CEnrollmentHelper@WorkAccess@SystemSettings@@SAJXZ; SystemSettings::WorkAccess::CEnrollmentHelper::PopulateIDs(void)
0x180026c0b  mov     ebx, eax
0x180026c0d  test    eax, eax
0x180026c0f  jns     short loc_180026C30
0x180026c11  mov     edx, 20Ah; void *
0x180026c16  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\settingshandlers\\w"...
0x180026c1d  mov     r9d, ebx; char *
0x180026c20  mov     rcx, [rbp+38h]; this
0x180026c24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026c29  mov     eax, ebx
0x180026c2b  jmp     loc_180026FCE
0x180026c30  mov     [rbp+arg_8], 1
0x180026c37  call    ?IsDesktopSKU@WorkAccess@SystemSettings@@YA_NXZ; SystemSettings::WorkAccess::IsDesktopSKU(void)
0x180026c3c  test    al, al
0x180026c3e  jz      short loc_180026C64
0x180026c40  lea     rcx, [rbp+arg_8]
0x180026c44  call    LUAIsUserUACAdmin
0x180026c49  mov     ebx, eax
0x180026c4b  or      ebx, 10000000h
0x180026c51  jge     short loc_180026C5A
0x180026c53  mov     edx, 210h
0x180026c58  jmp     short loc_180026C16
0x180026c5a  cmp     [rbp+arg_8], r12d
0x180026c5e  jz      loc_180026FCC
0x180026c64  mov     [rbp+var_18], r12
0x180026c68  mov     [rbp+var_20], r12
0x180026c6c  call    cs:__imp_GetDatabaseManagerInstance
0x180026c73  nop     dword ptr [rax+rax+00h]
0x180026c78  mov     rbx, rax
0x180026c7b  mov     rcx, [rax]
0x180026c7e  mov     rdi, [rcx+10h]
0x180026c82  mov     rcx, [rbp+var_18]
0x180026c86  mov     [rbp+var_18], r12
0x180026c8a  test    rcx, rcx
0x180026c8d  jz      short loc_180026C9C
0x180026c8f  mov     rdx, [rcx]
0x180026c92  mov     rax, [rdx+10h]
0x180026c96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c9b  nop
0x180026c9c  lea     r8, [rbp+var_18]
0x180026ca0  mov     edx, 5
0x180026ca5  mov     rcx, rbx
0x180026ca8  mov     rax, rdi
0x180026cab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026cb0  mov     ebx, eax
0x180026cb2  test    eax, eax
0x180026cb4  jns     short loc_180026CBD
0x180026cb6  mov     edx, 219h
0x180026cbb  jmp     short loc_180026CFC
0x180026cbd  mov     rbx, [rbp+var_18]
0x180026cc1  mov     rax, [rbx]
0x180026cc4  mov     rdi, [rax+18h]
0x180026cc8  mov     rcx, [rbp+var_20]
0x180026ccc  mov     [rbp+var_20], r12
0x180026cd0  test    rcx, rcx
0x180026cd3  jz      short loc_180026CE2
0x180026cd5  mov     rdx, [rcx]
0x180026cd8  mov     rax, [rdx+10h]
0x180026cdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ce1  nop
0x180026ce2  lea     rdx, [rbp+var_20]
0x180026ce6  mov     rcx, rbx
0x180026ce9  mov     rax, rdi
0x180026cec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026cf1  mov     ebx, eax
0x180026cf3  test    eax, eax
0x180026cf5  jns     short loc_180026D14
0x180026cf7  mov     edx, 21Ah; void *
0x180026cfc  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\settingshandlers\\w"...
0x180026d03  mov     r9d, eax; char *
0x180026d06  mov     rcx, [rbp+38h]; this
0x180026d0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026d0f  jmp     loc_180026F6C
0x180026d14  mov     rbx, [rbp+var_20]
0x180026d18  test    rbx, rbx
0x180026d1b  jz      loc_180026FBA
0x180026d21  mov     [rbp+lpString2], r12
0x180026d25  mov     [rbp+lpString1], r12
0x180026d29  mov     rax, [rbx]
0x180026d2c  mov     rdi, [rax+70h]
0x180026d30  xor     edx, edx
0x180026d32  lea     rcx, [rbp+lpString1]
0x180026d36  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180026d3b  lea     rdx, [rbp+lpString1]
0x180026d3f  mov     rcx, rbx
0x180026d42  mov     rax, rdi
0x180026d45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d4a  mov     ebx, eax
0x180026d4c  test    eax, eax
0x180026d4e  jns     short loc_180026D6D
0x180026d50  mov     edx, 220h; void *
0x180026d55  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\settingshandlers\\w"...
0x180026d5c  mov     r9d, eax; char *
0x180026d5f  mov     rcx, [rbp+38h]; this
0x180026d63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026d68  jmp     loc_180026F5A
0x180026d6d  xor     edx, edx
0x180026d6f  lea     rcx, [rbp+lpString2]
0x180026d73  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180026d78  lea     rcx, [rbp+lpString2]; StringSid
0x180026d7c  call    ?GetCurrentUserSidString@@YAJPEAPEAG@Z; GetCurrentUserSidString(ushort * *)
0x180026d81  mov     ebx, eax
0x180026d83  test    eax, eax
0x180026d85  jns     short loc_180026D8E
0x180026d87  mov     edx, 221h
0x180026d8c  jmp     short loc_180026D55
0x180026d8e  mov     [rsp+60h+bIgnoreCase], r12d; int
0x180026d93  or      r9d, 0FFFFFFFFh; cchCount2
0x180026d97  mov     r8, [rbp+lpString2]; lpString2
0x180026d9b  or      edx, r9d; cchCount1
0x180026d9e  mov     rcx, [rbp+lpString1]; lpString1
0x180026da2  call    cs:__imp_CompareStringOrdinal
0x180026da9  nop     dword ptr [rax+rax+00h]
0x180026dae  cmp     eax, 2
0x180026db1  jnz     loc_180026FA8
0x180026db7  mov     [rbp+Source], r12
0x180026dbb  mov     [rbp+var_28], r12
0x180026dbf  lea     r8, [rbp+Source]; unsigned __int16 **
0x180026dc3  lea     rdx, aVendorMsftDmcl_0; "./Vendor/MSFT/DMClient/Provider/%s/UPN"
0x180026dca  mov     rcx, rsi; this
0x180026dcd  call    ?GetConfigManagerData@MamUpgradeToMdmLink@WorkAccess@SystemSettings@@QEAAJPEBGPEAPEAG@Z; SystemSettings::WorkAccess::MamUpgradeToMdmLink::GetConfigManagerData(ushort const *,ushort * *)
0x180026dd2  mov     ebx, eax
0x180026dd4  test    eax, eax
0x180026dd6  jns     short loc_180026DF5
0x180026dd8  mov     edx, 227h; void *
0x180026ddd  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\settingshandlers\\w"...
0x180026de4  mov     r9d, eax; char *
0x180026de7  mov     rcx, [rbp+38h]; this
0x180026deb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026df0  jmp     loc_180026F48
0x180026df5  lea     r8, [rbp+var_28]; unsigned __int16 **
0x180026df9  lea     rdx, aVendorMsftDmcl_4; "./Vendor/MSFT/DMClient/Provider/%s/Mana"...
0x180026e00  mov     rcx, rsi; this
0x180026e03  call    ?GetConfigManagerData@MamUpgradeToMdmLink@WorkAccess@SystemSettings@@QEAAJPEBGPEAPEAG@Z; SystemSettings::WorkAccess::MamUpgradeToMdmLink::GetConfigManagerData(ushort const *,ushort * *)
0x180026e08  mov     ebx, eax
0x180026e0a  test    eax, eax
0x180026e0c  jns     short loc_180026E15
0x180026e0e  mov     edx, 228h
0x180026e13  jmp     short loc_180026DDD
0x180026e15  mov     rcx, [rbp+Source]; Source
0x180026e19  call    wcsnlen_s
0x180026e1e  mov     r15, rax
0x180026e21  mov     rdi, [rbp+var_28]
0x180026e25  mov     rcx, rdi; Source
0x180026e28  call    wcsnlen_s
0x180026e2d  add     r15, rax
0x180026e30  mov     edx, 7FFFFFFFh; MaxCount
0x180026e35  lea     rcx, aMsCxhMosetmamc; "ms-cxh://mosetmamconnecttowork?mode=mdm"...
0x180026e3c  call    cs:__imp_wcsnlen
0x180026e43  nop     dword ptr [rax+rax+00h]
0x180026e48  add     r15, rax
0x180026e4b  lea     rbx, [r15+r15]
0x180026e4f  call    cs:__imp_GetProcessHeap
0x180026e56  nop     dword ptr [rax+rax+00h]
0x180026e5b  mov     rcx, rax; hHeap
0x180026e5e  mov     r8, rbx; dwBytes
0x180026e61  mov     edx, 8; dwFlags
0x180026e66  call    cs:__imp_HeapAlloc
0x180026e6d  nop     dword ptr [rax+rax+00h]
0x180026e72  mov     rbx, rax
0x180026e75  mov     [rbp+var_10], rax
0x180026e79  test    rax, rax
0x180026e7c  jz      loc_180026F8D
0x180026e82  lea     rdx, [r15+1]; unsigned __int64
0x180026e86  mov     qword ptr [rsp+60h+bIgnoreCase], rdi; int
0x180026e8b  mov     r9, [rbp+Source]
0x180026e8f  lea     r8, aMsCxhMosetmamc; "ms-cxh://mosetmamconnecttowork?mode=mdm"...
0x180026e96  mov     rcx, rax; unsigned __int16 *
0x180026e99  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026e9e  mov     edi, eax
0x180026ea0  test    eax, eax
0x180026ea2  jns     short loc_180026EED
0x180026ea4  mov     rcx, [rbp+38h]; this
0x180026ea8  mov     r9d, eax; char *
0x180026eab  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\settingshandlers\\w"...
0x180026eb2  mov     edx, 230h; void *
0x180026eb7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026ebc  lea     rcx, [rbp+var_10]
0x180026ec0  call    ?Release@?$CTSmartObj@PEAGV?$CTSmartPtr_PolicyComplete@VCTContainer_PolicyHeapMem@@@@@@QEAAXXZ; CTSmartObj<ushort *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(void)
0x180026ec5  lea     rcx, [rbp+var_28]
0x180026ec9  call    ?Release@?$CTSmartObj@PEAGV?$CTSmartPtr_PolicyComplete@VCTContainer_PolicyHeapMem@@@@@@QEAAXXZ; CTSmartObj<ushort *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(void)
0x180026ece  lea     rcx, [rbp+Source]
0x180026ed2  call    ?Release@?$CTSmartObj@PEAGV?$CTSmartPtr_PolicyComplete@VCTContainer_PolicyHeapMem@@@@@@QEAAXXZ; CTSmartObj<ushort *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(void)
0x180026ed7  lea     rcx, [rbp+lpString1]
0x180026edb  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180026ee0  lea     rcx, [rbp+lpString2]
0x180026ee4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180026ee9  mov     ebx, edi
0x180026eeb  jmp     short loc_180026F6C
0x180026eed  lea     rcx, [rsi+100h]
0x180026ef4  or      r8, 0FFFFFFFFFFFFFFFFh
0x180026ef8  mov     rdx, rbx
0x180026efb  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180026f00  mov     ebx, eax
0x180026f02  test    eax, eax
0x180026f04  jns     short loc_180026F0D
0x180026f06  mov     edx, 231h
0x180026f0b  jmp     short loc_180026F2C
0x180026f0d  mov     [rbp+arg_8], r12d
0x180026f11  lea     rcx, [rbp+arg_8]
0x180026f15  call    cs:__imp_IsMdmUxWithoutAadAllowed
0x180026f1c  nop     dword ptr [rax+rax+00h]
0x180026f21  mov     ebx, eax
0x180026f23  test    eax, eax
0x180026f25  jns     short loc_180026F83
0x180026f27  mov     edx, 234h; void *
0x180026f2c  mov     r9d, eax; char *
0x180026f2f  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\settingshandlers\\w"...
0x180026f36  mov     rcx, [rbp+38h]; this
0x180026f3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026f3f  lea     rcx, [rbp+var_10]
0x180026f43  call    ?Release@?$CTSmartObj@PEAGV?$CTSmartPtr_PolicyComplete@VCTContainer_PolicyHeapMem@@@@@@QEAAXXZ; CTSmartObj<ushort *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(void)
0x180026f48  lea     rcx, [rbp+var_28]
0x180026f4c  call    ?Release@?$CTSmartObj@PEAGV?$CTSmartPtr_PolicyComplete@VCTContainer_PolicyHeapMem@@@@@@QEAAXXZ; CTSmartObj<ushort *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(void)
0x180026f51  lea     rcx, [rbp+Source]
0x180026f55  call    ?Release@?$CTSmartObj@PEAGV?$CTSmartPtr_PolicyComplete@VCTContainer_PolicyHeapMem@@@@@@QEAAXXZ; CTSmartObj<ushort *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(void)
0x180026f5a  lea     rcx, [rbp+lpString1]
0x180026f5e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180026f63  lea     rcx, [rbp+lpString2]
0x180026f67  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180026f6c  lea     rcx, [rbp+var_20]
0x180026f70  call    ??1?$com_ptr_t@UIEnrollmentInfoEnumerator@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>::~com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>(void)
0x180026f75  lea     rcx, [rbp+var_18]
0x180026f79  call    ??1?$com_ptr_t@UIEnrollmentInfoEnumerator@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>::~com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>(void)
0x180026f7e  jmp     loc_180026C29
0x180026f83  cmp     [rbp+arg_8], r12d
0x180026f87  setnz   al
0x180026f8a  mov     [r14], al
0x180026f8d  lea     rcx, [rbp+var_10]
0x180026f91  call    ?Release@?$CTSmartObj@PEAGV?$CTSmartPtr_PolicyComplete@VCTContainer_PolicyHeapMem@@@@@@QEAAXXZ; CTSmartObj<ushort *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(void)
0x180026f96  lea     rcx, [rbp+var_28]
0x180026f9a  call    ?Release@?$CTSmartObj@PEAGV?$CTSmartPtr_PolicyComplete@VCTContainer_PolicyHeapMem@@@@@@QEAAXXZ; CTSmartObj<ushort *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(void)
0x180026f9f  lea     rcx, [rbp+Source]
0x180026fa3  call    ?Release@?$CTSmartObj@PEAGV?$CTSmartPtr_PolicyComplete@VCTContainer_PolicyHeapMem@@@@@@QEAAXXZ; CTSmartObj<ushort *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(void)
0x180026fa8  lea     rcx, [rbp+lpString1]
0x180026fac  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180026fb1  lea     rcx, [rbp+lpString2]
0x180026fb5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180026fba  lea     rcx, [rbp+var_20]
0x180026fbe  call    ??1?$com_ptr_t@UIEnrollmentInfoEnumerator@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>::~com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>(void)
0x180026fc3  lea     rcx, [rbp+var_18]
0x180026fc7  call    ??1?$com_ptr_t@UIEnrollmentInfoEnumerator@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>::~com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>(void)
0x180026fcc  xor     eax, eax
0x180026fce  add     rsp, 60h
0x180026fd2  pop     r15
0x180026fd4  pop     r14
0x180026fd6  pop     r12
0x180026fd8  pop     rdi
0x180026fd9  pop     rsi
0x180026fda  pop     rbx
0x180026fdb  pop     rbp
0x180026fdc  retn
```
