# CheckPackageFamilyNameACEFromPath

- ea: `0x18002c448`
- end: `0x18002c7f4`
- name: `CheckPackageFamilyNameACEFromPath`
- size: `940`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180038fec`
- `0x180039120`

## callees

- `0x180007c78`
- `0x18000f9e0`
- `0x180012634`
- `0x180018400`
- `0x180018530`
- `0x180025bd4`
- `0x180025d3c`
- `0x180026b8c`
- `0x180027244`
- `0x18002c448`
- `0x180030448`
- `0x1800336c0`
- `0x180038934`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18002c6be`
- `msvcrt!_wcsnicmp` at `0x18002c6be`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18002c628`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18002c628`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18002c653`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18002c653`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002c4c6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002c4c6`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18002c5a6`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18002c5a6`

## string_xrefs

- `0x18002c487`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002c542`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002c5c6`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002c5ed`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002c717`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002c73a`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002c769`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002c7ae`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

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
      (void *)0x18DC,
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
                  (void *)0x18E0,
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
      (void *)0x18E1,
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
            (void *)0x18E6,
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
      (void *)0x18E8,
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
              (void *)0x18EF,
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
          (void *)0x18FC,
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
          (void *)0x1900,
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
0x18002c448  mov     [rsp-8+arg_0], rbx
0x18002c44d  mov     [rsp-8+arg_8], rsi
0x18002c452  push    rbp
0x18002c453  push    rdi
0x18002c454  push    r12
0x18002c456  push    r14
0x18002c458  push    r15
0x18002c45a  lea     rbp, [rsp-20h]
0x18002c45f  sub     rsp, 120h
0x18002c466  xor     r12d, r12d
0x18002c469  mov     rsi, r8
0x18002c46c  mov     [r8], r12b
0x18002c46f  mov     r15, rdx
0x18002c472  xor     r8d, r8d; unsigned __int64 *
0x18002c475  mov     r11, rcx
0x18002c478  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18002c47d  mov     ebx, eax
0x18002c47f  test    eax, eax
0x18002c481  jns     short loc_18002C4A0
0x18002c483  mov     rcx, [rbp+48h]; this
0x18002c487  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18002c48e  mov     r9d, eax; char *
0x18002c491  mov     edx, 18DCh; void *
0x18002c496  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c49b  jmp     loc_18002C7D5
0x18002c4a0  xor     r9d, r9d; lpSecurityAttributes
0x18002c4a3  mov     [rsp+140h+hTemplateFile], r12; hTemplateFile
0x18002c4a8  mov     [rsp+140h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18002c4b0  xor     edx, edx; dwDesiredAccess
0x18002c4b2  mov     rcx, r11; lpFileName
0x18002c4b5  mov     [rsp+140h+pObjectName], r12
0x18002c4ba  mov     [rsp+140h+dwCreationDisposition], 3; int
0x18002c4c2  lea     r8d, [r9+7]; dwShareMode
0x18002c4c6  call    cs:__imp_CreateFileW
0x18002c4cd  nop     dword ptr [rax+rax+00h]
0x18002c4d2  mov     [rsp+140h+var_E0], rax
0x18002c4d7  lea     rcx, [rax-1]
0x18002c4db  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002c4df  ja      loc_18002C7AA
0x18002c4e5  lea     r9, [rbp+40h+arg_10]; enum wil::PathOptions *
0x18002c4e9  mov     dword ptr [rbp+40h+arg_10], r12d
0x18002c4ed  lea     r8, [rbp+40h+String1]; enum wil::VolumePrefix *
0x18002c4f1  mov     dword ptr [rbp+40h+String1], 1
0x18002c4f8  lea     rdx, [rsp+140h+pAce]; void **
0x18002c4fd  mov     [rsp+140h+pAce], rax
0x18002c502  lea     rcx, [rbp+40h+var_B0]; this
0x18002c506  call    ??0_lambda_4d5a3fb5a3947e505c389e0b77bfed2e_@@QEAA@AEAPEAXAEAW4VolumePrefix@wil@@AEAW4PathOptions@2@@Z; _lambda_4d5a3fb5a3947e505c389e0b77bfed2e_::_lambda_4d5a3fb5a3947e505c389e0b77bfed2e_(void * &,wil::VolumePrefix &,wil::PathOptions &)
0x18002c50b  lea     rdx, [rsp+140h+var_D0]
0x18002c510  lea     rcx, [rbp+40h+var_98]
0x18002c514  movups  xmm0, xmmword ptr [rax]
0x18002c517  movsd   xmm1, qword ptr [rax+10h]
0x18002c51c  movaps  xmmword ptr [rsp+140h+var_D0], xmm0
0x18002c521  movsd   [rbp+40h+var_C0], xmm1
0x18002c526  call    ??$?0V_lambda_4d5a3fb5a3947e505c389e0b77bfed2e_@@X@?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEAA@V_lambda_4d5a3fb5a3947e505c389e0b77bfed2e_@@@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::function<long (ushort *,unsigned __int64,unsigned __int64 *)>(_lambda_4d5a3fb5a3947e505c389e0b77bfed2e_)
0x18002c52b  mov     rdx, rax
0x18002c52e  lea     rcx, [rsp+140h+pObjectName]
0x18002c533  call    ??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@V?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z; wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>)
0x18002c538  mov     ebx, eax
0x18002c53a  test    eax, eax
0x18002c53c  jns     short loc_18002C55B
0x18002c53e  mov     rcx, [rbp+48h]; this
0x18002c542  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18002c549  mov     r9d, eax; char *
0x18002c54c  mov     edx, 18E1h; void *
0x18002c551  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c556  jmp     loc_18002C7C1
0x18002c55b  mov     rcx, [rsp+140h+pObjectName]; pObjectName
0x18002c560  lea     rax, [rsp+140h+var_100]
0x18002c565  mov     [rsp+140h+var_D0], rax
0x18002c56a  xor     r9d, r9d; ppsidOwner
0x18002c56d  lea     rax, [rsp+140h+var_D0+8]
0x18002c572  mov     [rsp+140h+ppDacl], r12
0x18002c577  mov     [rsp+140h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18002c57c  lea     rax, [rsp+140h+ppDacl]
0x18002c581  mov     [rsp+140h+hTemplateFile], r12; ppSacl
0x18002c586  mov     qword ptr [rsp+140h+dwFlagsAndAttributes], rax; ppDacl
0x18002c58b  lea     edx, [r9+1]; ObjectType
0x18002c58f  lea     r8d, [r9+4]; SecurityInfo
0x18002c593  mov     qword ptr [rsp+140h+dwCreationDisposition], r12; int
0x18002c598  mov     [rsp+140h+var_100], r12
0x18002c59d  mov     [rsp+140h+var_D0+8], r12
0x18002c5a2  mov     byte ptr [rbp+40h+var_C0], 1
0x18002c5a6  call    cs:__imp_GetNamedSecurityInfoW
0x18002c5ad  nop     dword ptr [rax+rax+00h]
0x18002c5b2  lea     rcx, [rsp+140h+var_D0]
0x18002c5b7  mov     ebx, eax
0x18002c5b9  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x18002c5be  test    ebx, ebx
0x18002c5c0  jz      short loc_18002C5DF
0x18002c5c2  mov     rcx, [rbp+48h]; this
0x18002c5c6  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18002c5cd  mov     r9d, ebx; char *
0x18002c5d0  mov     edx, 18E6h; void *
0x18002c5d5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002c5da  jmp     loc_18002C77A
0x18002c5df  mov     rcx, [rsp+140h+ppDacl]; pAcl
0x18002c5e4  test    rcx, rcx
0x18002c5e7  jnz     short loc_18002C60B
0x18002c5e9  mov     rcx, [rbp+48h]; this
0x18002c5ed  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18002c5f4  mov     ebx, 80070490h
0x18002c5f9  mov     edx, 18E8h; void *
0x18002c5fe  mov     r9d, ebx; char *
0x18002c601  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c606  jmp     loc_18002C77C
0x18002c60b  movzx   r14d, word ptr [rcx+4]
0x18002c610  mov     ebx, r12d
0x18002c613  cmp     ebx, r14d
0x18002c616  jnb     loc_18002C788
0x18002c61c  lea     r8, [rsp+140h+pAce]; pAce
0x18002c621  mov     [rsp+140h+pAce], r12
0x18002c626  mov     edx, ebx; dwAceIndex
0x18002c628  call    cs:__imp_GetAce
0x18002c62f  nop     dword ptr [rax+rax+00h]
0x18002c634  test    eax, eax
0x18002c636  jz      loc_18002C765
0x18002c63c  mov     rcx, [rsp+140h+pAce]
0x18002c641  cmp     byte ptr [rcx], 9
0x18002c644  jnz     loc_18002C6E0
0x18002c64a  add     rcx, 8; pSid
0x18002c64e  mov     edx, 1Bh; WellKnownSidType
0x18002c653  call    cs:__imp_IsWellKnownSid
0x18002c65a  nop     dword ptr [rax+rax+00h]
0x18002c65f  test    eax, eax
0x18002c661  jz      short loc_18002C6E0
0x18002c663  mov     rax, [rsp+140h+pAce]
0x18002c668  mov     ecx, [rax+4]
0x18002c66b  and     ecx, 1200A0h
0x18002c671  cmp     ecx, 1200A0h
0x18002c677  jnz     short loc_18002C6E0
0x18002c679  lea     rdx, [rbp+40h+arg_10]
0x18002c67d  mov     [rbp+40h+arg_10], r12
0x18002c681  lea     rcx, [rsp+140h+pAce]
0x18002c686  call    GetConditionalAce
0x18002c68b  mov     edi, eax
0x18002c68d  test    eax, eax
0x18002c68f  js      loc_18002C736
0x18002c695  mov     rcx, [rbp+40h+arg_10]
0x18002c699  lea     rdx, [rbp+40h+String1]
0x18002c69d  mov     [rbp+40h+String1], r12
0x18002c6a1  call    GetPackageFamilyNameFromConditionalAce
0x18002c6a6  mov     edi, eax
0x18002c6a8  test    eax, eax
0x18002c6aa  js      short loc_18002C713
0x18002c6ac  mov     rcx, [rbp+40h+String1]; String1
0x18002c6b0  test    rcx, rcx
0x18002c6b3  jz      short loc_18002C6CE
0x18002c6b5  mov     r8d, 41h ; 'A'; MaxCount
0x18002c6bb  mov     rdx, r15; String2
0x18002c6be  call    cs:__imp__wcsnicmp
0x18002c6c5  nop     dword ptr [rax+rax+00h]
0x18002c6ca  test    eax, eax
0x18002c6cc  jz      short loc_18002C6EC
0x18002c6ce  lea     rcx, [rbp+40h+String1]
0x18002c6d2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002c6d7  lea     rcx, [rbp+40h+arg_10]
0x18002c6db  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002c6e0  mov     rcx, [rsp+140h+ppDacl]
0x18002c6e5  inc     ebx
0x18002c6e7  jmp     loc_18002C613
0x18002c6ec  lea     rcx, [rbp+40h+String1]
0x18002c6f0  mov     byte ptr [rsi], 1
0x18002c6f3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002c6f8  lea     rcx, [rbp+40h+arg_10]
0x18002c6fc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002c701  lea     rcx, [rsp+140h+var_100]
0x18002c706  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002c70b  mov     ebx, r12d
0x18002c70e  jmp     loc_18002C7C1
0x18002c713  mov     rcx, [rbp+48h]; this
0x18002c717  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18002c71e  mov     r9d, edi; char *
0x18002c721  mov     edx, 1900h; void *
0x18002c726  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c72b  lea     rcx, [rbp+40h+String1]
0x18002c72f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002c734  jmp     short loc_18002C74E
0x18002c736  mov     rcx, [rbp+48h]; this
0x18002c73a  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18002c741  mov     r9d, edi; char *
0x18002c744  mov     edx, 18FCh; void *
0x18002c749  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c74e  lea     rcx, [rbp+40h+arg_10]
0x18002c752  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002c757  lea     rcx, [rsp+140h+var_100]
0x18002c75c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002c761  mov     ebx, edi
0x18002c763  jmp     short loc_18002C7C1
0x18002c765  mov     rcx, [rbp+48h]; this
0x18002c769  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18002c770  mov     edx, 18EFh; void *
0x18002c775  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002c77a  mov     ebx, eax
0x18002c77c  lea     rcx, [rsp+140h+var_100]
0x18002c781  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002c786  jmp     short loc_18002C7C1
0x18002c788  lea     rcx, [rsp+140h+var_100]
0x18002c78d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002c792  lea     rcx, [rsp+140h+var_E0]
0x18002c797  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002c79c  lea     rcx, [rsp+140h+pObjectName]
0x18002c7a1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002c7a6  xor     eax, eax
0x18002c7a8  jmp     short loc_18002C7D7
0x18002c7aa  mov     rcx, [rbp+48h]; this
0x18002c7ae  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18002c7b5  mov     edx, 18E0h; void *
0x18002c7ba  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002c7bf  mov     ebx, eax
0x18002c7c1  lea     rcx, [rsp+140h+var_E0]
0x18002c7c6  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002c7cb  lea     rcx, [rsp+140h+pObjectName]
0x18002c7d0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002c7d5  mov     eax, ebx
0x18002c7d7  lea     r11, [rsp+140h+var_20]
0x18002c7df  mov     rbx, [r11+30h]
0x18002c7e3  mov     rsi, [r11+38h]
0x18002c7e7  mov     rsp, r11
0x18002c7ea  pop     r15
0x18002c7ec  pop     r14
0x18002c7ee  pop     r12
0x18002c7f0  pop     rdi
0x18002c7f1  pop     rbp
0x18002c7f2  retn
```
