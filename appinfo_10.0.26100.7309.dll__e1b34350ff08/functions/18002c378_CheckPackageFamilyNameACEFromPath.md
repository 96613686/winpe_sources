# CheckPackageFamilyNameACEFromPath

- ea: `0x18002c378`
- end: `0x18002c724`
- name: `CheckPackageFamilyNameACEFromPath`
- size: `940`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180038cac`
- `0x180038de0`

## callees

- `0x180007c78`
- `0x18000f9e0`
- `0x180012634`
- `0x180018400`
- `0x180018530`
- `0x180025bd4`
- `0x180025d3c`
- `0x180026af0`
- `0x180027174`
- `0x18002c378`
- `0x18003024c`
- `0x180033400`
- `0x1800385f4`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18002c5ee`
- `msvcrt!_wcsnicmp` at `0x18002c5ee`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18002c558`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18002c558`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18002c583`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18002c583`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002c3f6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002c3f6`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18002c4d6`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18002c4d6`

## string_xrefs

- `0x18002c3b7`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002c472`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002c4f6`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002c51d`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002c647`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002c66a`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002c699`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002c6de`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

## pseudocode

```c
__int64 __fastcall CheckPackageFamilyNameACEFromPath(const unsigned __int16 *a1, const wchar_t *a2, _BYTE *a3)
{
  int v5; // eax
  const WCHAR *v6; // r11
  unsigned int LastError; // ebx
  char *FileW; // rax
  const char *v9; // r9
  _lambda_4d5a3fb5a3947e505c389e0b77bfed2e_ *v10; // rax
  __int64 v11; // xmm1_8
  __int64 v12; // rax
  int v13; // eax
  DWORD NamedSecurityInfoW; // ebx
  unsigned int v15; // eax
  struct _ACL *v16; // rcx
  DWORD AceCount; // r14d
  DWORD i; // ebx
  const char *v19; // r9
  int ConditionalAce; // eax
  unsigned int v21; // edi
  int PackageFamilyNameFromConditionalAce; // eax
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  unsigned int dwCreationDispositionb; // [rsp+20h] [rbp-E0h]
  __int64 v27; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID pAce; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR pObjectName; // [rsp+50h] [rbp-B0h] BYREF
  PACL ppDacl; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v31[2]; // [rsp+60h] [rbp-A0h] BYREF
  PSECURITY_DESCRIPTOR ppSecurityDescriptor[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v33; // [rsp+80h] [rbp-80h]
  _BYTE v34[24]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v35[120]; // [rsp+A8h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]
  __int64 v37; // [rsp+160h] [rbp+60h] BYREF
  wchar_t *String1; // [rsp+168h] [rbp+68h] BYREF

  *a3 = 0;
  v5 = StringCchLengthW(a1, (unsigned __int64)a2, 0);
  LastError = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18A5,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)v5,
      dwCreationDisposition);
    return LastError;
  }
  pObjectName = 0;
  FileW = (char *)CreateFileW(v6, 0, 7u, 0, 3u, 0x2000000u, 0);
  v31[0] = FileW;
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x18A9,
                  (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                  v9);
    goto LABEL_31;
  }
  LODWORD(v37) = 0;
  LODWORD(String1) = 1;
  pAce = FileW;
  v10 = _lambda_4d5a3fb5a3947e505c389e0b77bfed2e_::_lambda_4d5a3fb5a3947e505c389e0b77bfed2e_(
          (_lambda_4d5a3fb5a3947e505c389e0b77bfed2e_ *)v34,
          &pAce,
          (enum wil::VolumePrefix *)&String1,
          (enum wil::PathOptions *)&v37);
  v11 = *((_QWORD *)v10 + 2);
  *(_OWORD *)ppSecurityDescriptor = *(_OWORD *)v10;
  v33 = v11;
  v12 = wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>(
          v35,
          ppSecurityDescriptor);
  v13 = wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
          &pObjectName,
          v12);
  LastError = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18AA,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)v13,
      dwCreationDispositiona);
LABEL_31:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v31);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pObjectName);
    return LastError;
  }
  ppSecurityDescriptor[0] = &v27;
  ppDacl = 0;
  v27 = 0;
  ppSecurityDescriptor[1] = 0;
  LOBYTE(v33) = 1;
  NamedSecurityInfoW = GetNamedSecurityInfoW(
                         pObjectName,
                         SE_FILE_OBJECT,
                         4u,
                         0,
                         0,
                         &ppDacl,
                         0,
                         &ppSecurityDescriptor[1]);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(ppSecurityDescriptor);
  if ( NamedSecurityInfoW )
  {
    v15 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x18AF,
            (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
            (const char *)NamedSecurityInfoW,
            dwCreationDispositionb);
LABEL_27:
    LastError = v15;
    goto LABEL_28;
  }
  v16 = ppDacl;
  if ( !ppDacl )
  {
    LastError = -2147023728;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18B1,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)0x80070490LL,
      dwCreationDispositionb);
LABEL_28:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
    goto LABEL_31;
  }
  AceCount = ppDacl->AceCount;
  for ( i = 0; i < AceCount; ++i )
  {
    pAce = 0;
    if ( !GetAce(v16, i, &pAce) )
    {
      v15 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x18B8,
              (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
              v19);
      goto LABEL_27;
    }
    if ( *(_BYTE *)pAce == 9
      && IsWellKnownSid((char *)pAce + 8, WinBuiltinUsersSid)
      && (*((_DWORD *)pAce + 1) & 0x1200A0) == 0x1200A0 )
    {
      v37 = 0;
      ConditionalAce = GetConditionalAce((__int64 *)&pAce, (__int64)&v37);
      v21 = ConditionalAce;
      if ( ConditionalAce < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x18C5,
          (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
          (const char *)(unsigned int)ConditionalAce,
          dwCreationDispositionb);
        goto LABEL_25;
      }
      String1 = 0;
      PackageFamilyNameFromConditionalAce = GetPackageFamilyNameFromConditionalAce(v37, &String1);
      v21 = PackageFamilyNameFromConditionalAce;
      if ( PackageFamilyNameFromConditionalAce < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x18C9,
          (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
          (const char *)(unsigned int)PackageFamilyNameFromConditionalAce,
          dwCreationDispositionb);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&String1);
LABEL_25:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v37);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
        LastError = v21;
        goto LABEL_31;
      }
      if ( String1 && !_wcsnicmp(String1, a2, 0x41u) )
      {
        *a3 = 1;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&String1);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v37);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
        LastError = 0;
        goto LABEL_31;
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&String1);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v37);
    }
    v16 = ppDacl;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v31);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pObjectName);
  return 0;
}

```

## disassembly

```asm
0x18002c378  mov     [rsp-8+arg_0], rbx
0x18002c37d  mov     [rsp-8+arg_8], rsi
0x18002c382  push    rbp
0x18002c383  push    rdi
0x18002c384  push    r12
0x18002c386  push    r14
0x18002c388  push    r15
0x18002c38a  lea     rbp, [rsp-20h]
0x18002c38f  sub     rsp, 120h
0x18002c396  xor     r12d, r12d
0x18002c399  mov     rsi, r8
0x18002c39c  mov     [r8], r12b
0x18002c39f  mov     r15, rdx
0x18002c3a2  xor     r8d, r8d; unsigned __int64 *
0x18002c3a5  mov     r11, rcx
0x18002c3a8  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18002c3ad  mov     ebx, eax
0x18002c3af  test    eax, eax
0x18002c3b1  jns     short loc_18002C3D0
0x18002c3b3  mov     rcx, [rbp+48h]; this
0x18002c3b7  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18002c3be  mov     r9d, eax; char *
0x18002c3c1  mov     edx, 18A5h; void *
0x18002c3c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c3cb  jmp     loc_18002C705
0x18002c3d0  xor     r9d, r9d; lpSecurityAttributes
0x18002c3d3  mov     [rsp+140h+hTemplateFile], r12; hTemplateFile
0x18002c3d8  mov     [rsp+140h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18002c3e0  xor     edx, edx; dwDesiredAccess
0x18002c3e2  mov     rcx, r11; lpFileName
0x18002c3e5  mov     [rsp+140h+pObjectName], r12
0x18002c3ea  mov     [rsp+140h+dwCreationDisposition], 3; int
0x18002c3f2  lea     r8d, [r9+7]; dwShareMode
0x18002c3f6  call    cs:__imp_CreateFileW
0x18002c3fd  nop     dword ptr [rax+rax+00h]
0x18002c402  mov     [rsp+140h+var_E0], rax
0x18002c407  lea     rcx, [rax-1]
0x18002c40b  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002c40f  ja      loc_18002C6DA
0x18002c415  lea     r9, [rbp+40h+arg_10]; enum wil::PathOptions *
0x18002c419  mov     dword ptr [rbp+40h+arg_10], r12d
0x18002c41d  lea     r8, [rbp+40h+String1]; enum wil::VolumePrefix *
0x18002c421  mov     dword ptr [rbp+40h+String1], 1
0x18002c428  lea     rdx, [rsp+140h+pAce]; void **
0x18002c42d  mov     [rsp+140h+pAce], rax
0x18002c432  lea     rcx, [rbp+40h+var_B0]; this
0x18002c436  call    ??0_lambda_4d5a3fb5a3947e505c389e0b77bfed2e_@@QEAA@AEAPEAXAEAW4VolumePrefix@wil@@AEAW4PathOptions@2@@Z; _lambda_4d5a3fb5a3947e505c389e0b77bfed2e_::_lambda_4d5a3fb5a3947e505c389e0b77bfed2e_(void * &,wil::VolumePrefix &,wil::PathOptions &)
0x18002c43b  lea     rdx, [rsp+140h+var_D0]
0x18002c440  lea     rcx, [rbp+40h+var_98]
0x18002c444  movups  xmm0, xmmword ptr [rax]
0x18002c447  movsd   xmm1, qword ptr [rax+10h]
0x18002c44c  movaps  xmmword ptr [rsp+140h+var_D0], xmm0
0x18002c451  movsd   [rbp+40h+var_C0], xmm1
0x18002c456  call    ??$?0V_lambda_4d5a3fb5a3947e505c389e0b77bfed2e_@@X@?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEAA@V_lambda_4d5a3fb5a3947e505c389e0b77bfed2e_@@@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::function<long (ushort *,unsigned __int64,unsigned __int64 *)>(_lambda_4d5a3fb5a3947e505c389e0b77bfed2e_)
0x18002c45b  mov     rdx, rax
0x18002c45e  lea     rcx, [rsp+140h+pObjectName]
0x18002c463  call    ??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@V?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z; wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>)
0x18002c468  mov     ebx, eax
0x18002c46a  test    eax, eax
0x18002c46c  jns     short loc_18002C48B
0x18002c46e  mov     rcx, [rbp+48h]; this
0x18002c472  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18002c479  mov     r9d, eax; char *
0x18002c47c  mov     edx, 18AAh; void *
0x18002c481  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c486  jmp     loc_18002C6F1
0x18002c48b  mov     rcx, [rsp+140h+pObjectName]; pObjectName
0x18002c490  lea     rax, [rsp+140h+var_100]
0x18002c495  mov     [rsp+140h+var_D0], rax
0x18002c49a  xor     r9d, r9d; ppsidOwner
0x18002c49d  lea     rax, [rsp+140h+var_D0+8]
0x18002c4a2  mov     [rsp+140h+ppDacl], r12
0x18002c4a7  mov     [rsp+140h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18002c4ac  lea     rax, [rsp+140h+ppDacl]
0x18002c4b1  mov     [rsp+140h+hTemplateFile], r12; ppSacl
0x18002c4b6  mov     qword ptr [rsp+140h+dwFlagsAndAttributes], rax; ppDacl
0x18002c4bb  lea     edx, [r9+1]; ObjectType
0x18002c4bf  lea     r8d, [r9+4]; SecurityInfo
0x18002c4c3  mov     qword ptr [rsp+140h+dwCreationDisposition], r12; int
0x18002c4c8  mov     [rsp+140h+var_100], r12
0x18002c4cd  mov     [rsp+140h+var_D0+8], r12
0x18002c4d2  mov     byte ptr [rbp+40h+var_C0], 1
0x18002c4d6  call    cs:__imp_GetNamedSecurityInfoW
0x18002c4dd  nop     dword ptr [rax+rax+00h]
0x18002c4e2  lea     rcx, [rsp+140h+var_D0]
0x18002c4e7  mov     ebx, eax
0x18002c4e9  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x18002c4ee  test    ebx, ebx
0x18002c4f0  jz      short loc_18002C50F
0x18002c4f2  mov     rcx, [rbp+48h]; this
0x18002c4f6  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18002c4fd  mov     r9d, ebx; char *
0x18002c500  mov     edx, 18AFh; void *
0x18002c505  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002c50a  jmp     loc_18002C6AA
0x18002c50f  mov     rcx, [rsp+140h+ppDacl]; pAcl
0x18002c514  test    rcx, rcx
0x18002c517  jnz     short loc_18002C53B
0x18002c519  mov     rcx, [rbp+48h]; this
0x18002c51d  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18002c524  mov     ebx, 80070490h
0x18002c529  mov     edx, 18B1h; void *
0x18002c52e  mov     r9d, ebx; char *
0x18002c531  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c536  jmp     loc_18002C6AC
0x18002c53b  movzx   r14d, word ptr [rcx+4]
0x18002c540  mov     ebx, r12d
0x18002c543  cmp     ebx, r14d
0x18002c546  jnb     loc_18002C6B8
0x18002c54c  lea     r8, [rsp+140h+pAce]; pAce
0x18002c551  mov     [rsp+140h+pAce], r12
0x18002c556  mov     edx, ebx; dwAceIndex
0x18002c558  call    cs:__imp_GetAce
0x18002c55f  nop     dword ptr [rax+rax+00h]
0x18002c564  test    eax, eax
0x18002c566  jz      loc_18002C695
0x18002c56c  mov     rcx, [rsp+140h+pAce]
0x18002c571  cmp     byte ptr [rcx], 9
0x18002c574  jnz     loc_18002C610
0x18002c57a  add     rcx, 8; pSid
0x18002c57e  mov     edx, 1Bh; WellKnownSidType
0x18002c583  call    cs:__imp_IsWellKnownSid
0x18002c58a  nop     dword ptr [rax+rax+00h]
0x18002c58f  test    eax, eax
0x18002c591  jz      short loc_18002C610
0x18002c593  mov     rax, [rsp+140h+pAce]
0x18002c598  mov     ecx, [rax+4]
0x18002c59b  and     ecx, 1200A0h
0x18002c5a1  cmp     ecx, 1200A0h
0x18002c5a7  jnz     short loc_18002C610
0x18002c5a9  lea     rdx, [rbp+40h+arg_10]
0x18002c5ad  mov     [rbp+40h+arg_10], r12
0x18002c5b1  lea     rcx, [rsp+140h+pAce]
0x18002c5b6  call    GetConditionalAce
0x18002c5bb  mov     edi, eax
0x18002c5bd  test    eax, eax
0x18002c5bf  js      loc_18002C666
0x18002c5c5  mov     rcx, [rbp+40h+arg_10]
0x18002c5c9  lea     rdx, [rbp+40h+String1]
0x18002c5cd  mov     [rbp+40h+String1], r12
0x18002c5d1  call    GetPackageFamilyNameFromConditionalAce
0x18002c5d6  mov     edi, eax
0x18002c5d8  test    eax, eax
0x18002c5da  js      short loc_18002C643
0x18002c5dc  mov     rcx, [rbp+40h+String1]; String1
0x18002c5e0  test    rcx, rcx
0x18002c5e3  jz      short loc_18002C5FE
0x18002c5e5  mov     r8d, 41h ; 'A'; MaxCount
0x18002c5eb  mov     rdx, r15; String2
0x18002c5ee  call    cs:__imp__wcsnicmp
0x18002c5f5  nop     dword ptr [rax+rax+00h]
0x18002c5fa  test    eax, eax
0x18002c5fc  jz      short loc_18002C61C
0x18002c5fe  lea     rcx, [rbp+40h+String1]
0x18002c602  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002c607  lea     rcx, [rbp+40h+arg_10]
0x18002c60b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002c610  mov     rcx, [rsp+140h+ppDacl]
0x18002c615  inc     ebx
0x18002c617  jmp     loc_18002C543
0x18002c61c  lea     rcx, [rbp+40h+String1]
0x18002c620  mov     byte ptr [rsi], 1
0x18002c623  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002c628  lea     rcx, [rbp+40h+arg_10]
0x18002c62c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002c631  lea     rcx, [rsp+140h+var_100]
0x18002c636  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002c63b  mov     ebx, r12d
0x18002c63e  jmp     loc_18002C6F1
0x18002c643  mov     rcx, [rbp+48h]; this
0x18002c647  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18002c64e  mov     r9d, edi; char *
0x18002c651  mov     edx, 18C9h; void *
0x18002c656  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c65b  lea     rcx, [rbp+40h+String1]
0x18002c65f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002c664  jmp     short loc_18002C67E
0x18002c666  mov     rcx, [rbp+48h]; this
0x18002c66a  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18002c671  mov     r9d, edi; char *
0x18002c674  mov     edx, 18C5h; void *
0x18002c679  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c67e  lea     rcx, [rbp+40h+arg_10]
0x18002c682  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002c687  lea     rcx, [rsp+140h+var_100]
0x18002c68c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002c691  mov     ebx, edi
0x18002c693  jmp     short loc_18002C6F1
0x18002c695  mov     rcx, [rbp+48h]; this
0x18002c699  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18002c6a0  mov     edx, 18B8h; void *
0x18002c6a5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002c6aa  mov     ebx, eax
0x18002c6ac  lea     rcx, [rsp+140h+var_100]
0x18002c6b1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002c6b6  jmp     short loc_18002C6F1
0x18002c6b8  lea     rcx, [rsp+140h+var_100]
0x18002c6bd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002c6c2  lea     rcx, [rsp+140h+var_E0]
0x18002c6c7  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002c6cc  lea     rcx, [rsp+140h+pObjectName]
0x18002c6d1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002c6d6  xor     eax, eax
0x18002c6d8  jmp     short loc_18002C707
0x18002c6da  mov     rcx, [rbp+48h]; this
0x18002c6de  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18002c6e5  mov     edx, 18A9h; void *
0x18002c6ea  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002c6ef  mov     ebx, eax
0x18002c6f1  lea     rcx, [rsp+140h+var_E0]
0x18002c6f6  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002c6fb  lea     rcx, [rsp+140h+pObjectName]
0x18002c700  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002c705  mov     eax, ebx
0x18002c707  lea     r11, [rsp+140h+var_20]
0x18002c70f  mov     rbx, [r11+30h]
0x18002c713  mov     rsi, [r11+38h]
0x18002c717  mov     rsp, r11
0x18002c71a  pop     r15
0x18002c71c  pop     r14
0x18002c71e  pop     r12
0x18002c720  pop     rdi
0x18002c721  pop     rbp
0x18002c722  retn
```
