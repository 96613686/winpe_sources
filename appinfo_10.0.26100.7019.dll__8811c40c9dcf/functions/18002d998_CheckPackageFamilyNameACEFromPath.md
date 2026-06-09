# CheckPackageFamilyNameACEFromPath

- ea: `0x18002d998`
- end: `0x18002dd44`
- name: `CheckPackageFamilyNameACEFromPath`
- size: `940`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18003860c`
- `0x180038740`

## callees

- `0x180007c78`
- `0x18000f8b0`
- `0x1800124f4`
- `0x180018150`
- `0x180018280`
- `0x180027214`
- `0x18002737c`
- `0x180028084`
- `0x1800287b4`
- `0x18002d998`
- `0x180030a5c`
- `0x180033390`
- `0x180037f54`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18002dc0e`
- `msvcrt!_wcsnicmp` at `0x18002dc0e`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18002dba3`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18002dba3`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18002db78`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18002db78`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002da16`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002da16`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18002daf6`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18002daf6`

## string_xrefs

- `0x18002d9d7`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002da92`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002db16`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002db3d`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002dc67`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002dc8a`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002dcb9`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002dcfe`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

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
      (void *)0x17D8,
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
                  (void *)0x17DC,
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
      (void *)0x17DD,
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
            (void *)0x17E2,
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
      (void *)0x17E4,
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
              (void *)0x17EB,
              (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
              v19);
      goto LABEL_27;
    }
    if ( *(_BYTE *)pAce == 9
      && IsWellKnownSid((char *)pAce + 8, WinBuiltinUsersSid)
      && (*((_DWORD *)pAce + 1) & 0x1200A0) == 0x1200A0 )
    {
      v37 = 0;
      ConditionalAce = GetConditionalAce(&pAce, &v37);
      v21 = ConditionalAce;
      if ( ConditionalAce < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x17F8,
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
          (void *)0x17FC,
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
0x18002d998  mov     [rsp-8+arg_0], rbx
0x18002d99d  mov     [rsp-8+arg_8], rsi
0x18002d9a2  push    rbp
0x18002d9a3  push    rdi
0x18002d9a4  push    r12
0x18002d9a6  push    r14
0x18002d9a8  push    r15
0x18002d9aa  lea     rbp, [rsp-20h]
0x18002d9af  sub     rsp, 120h
0x18002d9b6  xor     r12d, r12d
0x18002d9b9  mov     rsi, r8
0x18002d9bc  mov     [r8], r12b
0x18002d9bf  mov     r15, rdx
0x18002d9c2  xor     r8d, r8d; unsigned __int64 *
0x18002d9c5  mov     r11, rcx
0x18002d9c8  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18002d9cd  mov     ebx, eax
0x18002d9cf  test    eax, eax
0x18002d9d1  jns     short loc_18002D9F0
0x18002d9d3  mov     rcx, [rbp+48h]; this
0x18002d9d7  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18002d9de  mov     r9d, eax; char *
0x18002d9e1  mov     edx, 17D8h; void *
0x18002d9e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d9eb  jmp     loc_18002DD25
0x18002d9f0  xor     r9d, r9d; lpSecurityAttributes
0x18002d9f3  mov     [rsp+140h+hTemplateFile], r12; hTemplateFile
0x18002d9f8  mov     [rsp+140h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18002da00  xor     edx, edx; dwDesiredAccess
0x18002da02  mov     rcx, r11; lpFileName
0x18002da05  mov     [rsp+140h+pObjectName], r12
0x18002da0a  mov     [rsp+140h+dwCreationDisposition], 3; int
0x18002da12  lea     r8d, [r9+7]; dwShareMode
0x18002da16  call    cs:__imp_CreateFileW
0x18002da1d  nop     dword ptr [rax+rax+00h]
0x18002da22  mov     [rsp+140h+var_E0], rax
0x18002da27  lea     rcx, [rax-1]
0x18002da2b  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002da2f  ja      loc_18002DCFA
0x18002da35  lea     r9, [rbp+40h+arg_10]; enum wil::PathOptions *
0x18002da39  mov     dword ptr [rbp+40h+arg_10], r12d
0x18002da3d  lea     r8, [rbp+40h+String1]; enum wil::VolumePrefix *
0x18002da41  mov     dword ptr [rbp+40h+String1], 1
0x18002da48  lea     rdx, [rsp+140h+pAce]; void **
0x18002da4d  mov     [rsp+140h+pAce], rax
0x18002da52  lea     rcx, [rbp+40h+var_B0]; this
0x18002da56  call    ??0_lambda_4d5a3fb5a3947e505c389e0b77bfed2e_@@QEAA@AEAPEAXAEAW4VolumePrefix@wil@@AEAW4PathOptions@2@@Z; _lambda_4d5a3fb5a3947e505c389e0b77bfed2e_::_lambda_4d5a3fb5a3947e505c389e0b77bfed2e_(void * &,wil::VolumePrefix &,wil::PathOptions &)
0x18002da5b  lea     rdx, [rsp+140h+var_D0]
0x18002da60  lea     rcx, [rbp+40h+var_98]
0x18002da64  movups  xmm0, xmmword ptr [rax]
0x18002da67  movsd   xmm1, qword ptr [rax+10h]
0x18002da6c  movaps  xmmword ptr [rsp+140h+var_D0], xmm0
0x18002da71  movsd   [rbp+40h+var_C0], xmm1
0x18002da76  call    ??$?0V_lambda_4d5a3fb5a3947e505c389e0b77bfed2e_@@X@?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEAA@V_lambda_4d5a3fb5a3947e505c389e0b77bfed2e_@@@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::function<long (ushort *,unsigned __int64,unsigned __int64 *)>(_lambda_4d5a3fb5a3947e505c389e0b77bfed2e_)
0x18002da7b  mov     rdx, rax
0x18002da7e  lea     rcx, [rsp+140h+pObjectName]
0x18002da83  call    ??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@V?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z; wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>)
0x18002da88  mov     ebx, eax
0x18002da8a  test    eax, eax
0x18002da8c  jns     short loc_18002DAAB
0x18002da8e  mov     rcx, [rbp+48h]; this
0x18002da92  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18002da99  mov     r9d, eax; char *
0x18002da9c  mov     edx, 17DDh; void *
0x18002daa1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002daa6  jmp     loc_18002DD11
0x18002daab  mov     rcx, [rsp+140h+pObjectName]; pObjectName
0x18002dab0  lea     rax, [rsp+140h+var_100]
0x18002dab5  mov     [rsp+140h+var_D0], rax
0x18002daba  xor     r9d, r9d; ppsidOwner
0x18002dabd  lea     rax, [rsp+140h+var_D0+8]
0x18002dac2  mov     [rsp+140h+ppDacl], r12
0x18002dac7  mov     [rsp+140h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18002dacc  lea     rax, [rsp+140h+ppDacl]
0x18002dad1  mov     [rsp+140h+hTemplateFile], r12; ppSacl
0x18002dad6  mov     qword ptr [rsp+140h+dwFlagsAndAttributes], rax; ppDacl
0x18002dadb  lea     edx, [r9+1]; ObjectType
0x18002dadf  lea     r8d, [r9+4]; SecurityInfo
0x18002dae3  mov     qword ptr [rsp+140h+dwCreationDisposition], r12; int
0x18002dae8  mov     [rsp+140h+var_100], r12
0x18002daed  mov     [rsp+140h+var_D0+8], r12
0x18002daf2  mov     byte ptr [rbp+40h+var_C0], 1
0x18002daf6  call    cs:__imp_GetNamedSecurityInfoW
0x18002dafd  nop     dword ptr [rax+rax+00h]
0x18002db02  lea     rcx, [rsp+140h+var_D0]
0x18002db07  mov     ebx, eax
0x18002db09  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x18002db0e  test    ebx, ebx
0x18002db10  jz      short loc_18002DB2F
0x18002db12  mov     rcx, [rbp+48h]; this
0x18002db16  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18002db1d  mov     r9d, ebx; char *
0x18002db20  mov     edx, 17E2h; void *
0x18002db25  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002db2a  jmp     loc_18002DCCA
0x18002db2f  mov     rcx, [rsp+140h+ppDacl]; pAcl
0x18002db34  test    rcx, rcx
0x18002db37  jnz     short loc_18002DB5B
0x18002db39  mov     rcx, [rbp+48h]; this
0x18002db3d  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18002db44  mov     ebx, 80070490h
0x18002db49  mov     edx, 17E4h; void *
0x18002db4e  mov     r9d, ebx; char *
0x18002db51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002db56  jmp     loc_18002DCCC
0x18002db5b  movzx   r14d, word ptr [rcx+4]
0x18002db60  mov     ebx, r12d
0x18002db63  cmp     ebx, r14d
0x18002db66  jnb     loc_18002DCD8
0x18002db6c  lea     r8, [rsp+140h+pAce]; pAce
0x18002db71  mov     [rsp+140h+pAce], r12
0x18002db76  mov     edx, ebx; dwAceIndex
0x18002db78  call    cs:__imp_GetAce
0x18002db7f  nop     dword ptr [rax+rax+00h]
0x18002db84  test    eax, eax
0x18002db86  jz      loc_18002DCB5
0x18002db8c  mov     rcx, [rsp+140h+pAce]
0x18002db91  cmp     byte ptr [rcx], 9
0x18002db94  jnz     loc_18002DC30
0x18002db9a  add     rcx, 8; pSid
0x18002db9e  mov     edx, 1Bh; WellKnownSidType
0x18002dba3  call    cs:__imp_IsWellKnownSid
0x18002dbaa  nop     dword ptr [rax+rax+00h]
0x18002dbaf  test    eax, eax
0x18002dbb1  jz      short loc_18002DC30
0x18002dbb3  mov     rax, [rsp+140h+pAce]
0x18002dbb8  mov     ecx, [rax+4]
0x18002dbbb  and     ecx, 1200A0h
0x18002dbc1  cmp     ecx, 1200A0h
0x18002dbc7  jnz     short loc_18002DC30
0x18002dbc9  lea     rdx, [rbp+40h+arg_10]
0x18002dbcd  mov     [rbp+40h+arg_10], r12
0x18002dbd1  lea     rcx, [rsp+140h+pAce]
0x18002dbd6  call    GetConditionalAce
0x18002dbdb  mov     edi, eax
0x18002dbdd  test    eax, eax
0x18002dbdf  js      loc_18002DC86
0x18002dbe5  mov     rcx, [rbp+40h+arg_10]
0x18002dbe9  lea     rdx, [rbp+40h+String1]
0x18002dbed  mov     [rbp+40h+String1], r12
0x18002dbf1  call    GetPackageFamilyNameFromConditionalAce
0x18002dbf6  mov     edi, eax
0x18002dbf8  test    eax, eax
0x18002dbfa  js      short loc_18002DC63
0x18002dbfc  mov     rcx, [rbp+40h+String1]; String1
0x18002dc00  test    rcx, rcx
0x18002dc03  jz      short loc_18002DC1E
0x18002dc05  mov     r8d, 41h ; 'A'; MaxCount
0x18002dc0b  mov     rdx, r15; String2
0x18002dc0e  call    cs:__imp__wcsnicmp
0x18002dc15  nop     dword ptr [rax+rax+00h]
0x18002dc1a  test    eax, eax
0x18002dc1c  jz      short loc_18002DC3C
0x18002dc1e  lea     rcx, [rbp+40h+String1]
0x18002dc22  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002dc27  lea     rcx, [rbp+40h+arg_10]
0x18002dc2b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002dc30  mov     rcx, [rsp+140h+ppDacl]
0x18002dc35  inc     ebx
0x18002dc37  jmp     loc_18002DB63
0x18002dc3c  lea     rcx, [rbp+40h+String1]
0x18002dc40  mov     byte ptr [rsi], 1
0x18002dc43  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002dc48  lea     rcx, [rbp+40h+arg_10]
0x18002dc4c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002dc51  lea     rcx, [rsp+140h+var_100]
0x18002dc56  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002dc5b  mov     ebx, r12d
0x18002dc5e  jmp     loc_18002DD11
0x18002dc63  mov     rcx, [rbp+48h]; this
0x18002dc67  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18002dc6e  mov     r9d, edi; char *
0x18002dc71  mov     edx, 17FCh; void *
0x18002dc76  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002dc7b  lea     rcx, [rbp+40h+String1]
0x18002dc7f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002dc84  jmp     short loc_18002DC9E
0x18002dc86  mov     rcx, [rbp+48h]; this
0x18002dc8a  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18002dc91  mov     r9d, edi; char *
0x18002dc94  mov     edx, 17F8h; void *
0x18002dc99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002dc9e  lea     rcx, [rbp+40h+arg_10]
0x18002dca2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002dca7  lea     rcx, [rsp+140h+var_100]
0x18002dcac  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002dcb1  mov     ebx, edi
0x18002dcb3  jmp     short loc_18002DD11
0x18002dcb5  mov     rcx, [rbp+48h]; this
0x18002dcb9  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18002dcc0  mov     edx, 17EBh; void *
0x18002dcc5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002dcca  mov     ebx, eax
0x18002dccc  lea     rcx, [rsp+140h+var_100]
0x18002dcd1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002dcd6  jmp     short loc_18002DD11
0x18002dcd8  lea     rcx, [rsp+140h+var_100]
0x18002dcdd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002dce2  lea     rcx, [rsp+140h+var_E0]
0x18002dce7  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002dcec  lea     rcx, [rsp+140h+pObjectName]
0x18002dcf1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002dcf6  xor     eax, eax
0x18002dcf8  jmp     short loc_18002DD27
0x18002dcfa  mov     rcx, [rbp+48h]; this
0x18002dcfe  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18002dd05  mov     edx, 17DCh; void *
0x18002dd0a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002dd0f  mov     ebx, eax
0x18002dd11  lea     rcx, [rsp+140h+var_E0]
0x18002dd16  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002dd1b  lea     rcx, [rsp+140h+pObjectName]
0x18002dd20  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002dd25  mov     eax, ebx
0x18002dd27  lea     r11, [rsp+140h+var_20]
0x18002dd2f  mov     rbx, [r11+30h]
0x18002dd33  mov     rsi, [r11+38h]
0x18002dd37  mov     rsp, r11
0x18002dd3a  pop     r15
0x18002dd3c  pop     r14
0x18002dd3e  pop     r12
0x18002dd40  pop     rdi
0x18002dd41  pop     rbp
0x18002dd42  retn
```
