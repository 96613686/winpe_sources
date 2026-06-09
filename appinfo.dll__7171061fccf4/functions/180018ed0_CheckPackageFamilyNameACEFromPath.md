# CheckPackageFamilyNameACEFromPath

- ea: `0x180018ed0`
- end: `0x18001920a`
- name: `CheckPackageFamilyNameACEFromPath`
- size: `826`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const wchar_t *, _BYTE *)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180018228`
- `0x18003b9ec`

## callees

- `0x18000720c`
- `0x18000c410`
- `0x180011414`
- `0x180018dbc`
- `0x180018ed0`
- `0x18001a0d4`
- `0x18001d350`
- `0x18002a314`
- `0x18002b020`
- `0x180033f64`
- `0x18003b370`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800190e9`
- `msvcrt!_wcsnicmp` at `0x1800190e9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180018f43`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180018f43`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18001907e`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18001907e`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18001905a`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18001905a`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x180018fe1`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x180018fe1`

## string_xrefs

- `0x180018f05`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180018f71`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180018ffa`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180019020`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18001913a`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18001915d`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18001918b`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800191cc`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

## pseudocode

```c
__int64 __fastcall CheckPackageFamilyNameACEFromPath(const unsigned __int16 *a1, const wchar_t *a2, _BYTE *a3)
{
  int v5; // eax
  WCHAR *hTemplateFile; // r8
  const WCHAR *v7; // r11
  unsigned int LastError; // ebx
  char *FileW; // rax
  const char *v10; // r9
  int v11; // eax
  DWORD NamedSecurityInfoW; // ebx
  unsigned int v13; // eax
  struct _ACL *v14; // rcx
  DWORD AceCount; // esi
  DWORD i; // ebx
  const char *v17; // r9
  int ConditionalAce; // eax
  unsigned int v19; // edi
  int PackageFamilyNameFromConditionalAce; // eax
  int dwCreationDisposition; // [rsp+20h] [rbp-60h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-60h]
  unsigned int dwCreationDispositionb; // [rsp+20h] [rbp-60h]
  wchar_t *String1; // [rsp+40h] [rbp-40h] BYREF
  LPCWSTR pObjectName; // [rsp+48h] [rbp-38h] BYREF
  LPVOID pAce; // [rsp+50h] [rbp-30h] BYREF
  PACL ppDacl; // [rsp+58h] [rbp-28h] BYREF
  char *v29; // [rsp+60h] [rbp-20h] BYREF
  __int64 *v30; // [rsp+68h] [rbp-18h] BYREF
  PSECURITY_DESCRIPTOR ppSecurityDescriptor; // [rsp+70h] [rbp-10h] BYREF
  char v32; // [rsp+78h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  __int64 v34; // [rsp+C0h] [rbp+40h] BYREF
  __int64 v35; // [rsp+C8h] [rbp+48h] BYREF

  *a3 = 0;
  v5 = StringCchLengthW(a1, (unsigned __int64)a2, 0);
  LastError = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B24,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)v5,
      dwCreationDisposition);
    return LastError;
  }
  pObjectName = hTemplateFile;
  FileW = (char *)CreateFileW(v7, 0, 7u, 0, 3u, 0x2000000u, hTemplateFile);
  v29 = FileW;
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1B28,
                  (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                  v10);
    goto LABEL_31;
  }
  v11 = wil::GetFinalPathNameByHandleW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
          FileW,
          &pObjectName);
  LastError = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B29,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)v11,
      dwCreationDispositiona);
LABEL_31:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v29);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pObjectName);
    return LastError;
  }
  v30 = &v34;
  ppDacl = 0;
  v34 = 0;
  ppSecurityDescriptor = 0;
  v32 = 1;
  NamedSecurityInfoW = GetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 4u, 0, 0, &ppDacl, 0, &ppSecurityDescriptor);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&v30);
  if ( NamedSecurityInfoW )
  {
    v13 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x1B2E,
            (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
            (const char *)NamedSecurityInfoW,
            dwCreationDispositionb);
LABEL_27:
    LastError = v13;
    goto LABEL_28;
  }
  v14 = ppDacl;
  if ( !ppDacl )
  {
    LastError = -2147023728;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B30,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)0x80070490LL,
      dwCreationDispositionb);
LABEL_28:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v34);
    goto LABEL_31;
  }
  AceCount = ppDacl->AceCount;
  for ( i = 0; i < AceCount; ++i )
  {
    pAce = 0;
    if ( !GetAce(v14, i, &pAce) )
    {
      v13 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x1B37,
              (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
              v17);
      goto LABEL_27;
    }
    if ( *(_BYTE *)pAce == 9
      && IsWellKnownSid((char *)pAce + 8, WinBuiltinUsersSid)
      && (*((_DWORD *)pAce + 1) & 0x1200A0) == 0x1200A0 )
    {
      v35 = 0;
      ConditionalAce = GetConditionalAce(&pAce, &v35);
      v19 = ConditionalAce;
      if ( ConditionalAce < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1B44,
          (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
          (const char *)(unsigned int)ConditionalAce,
          dwCreationDispositionb);
        goto LABEL_25;
      }
      String1 = 0;
      PackageFamilyNameFromConditionalAce = GetPackageFamilyNameFromConditionalAce(v35, &String1);
      v19 = PackageFamilyNameFromConditionalAce;
      if ( PackageFamilyNameFromConditionalAce < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1B48,
          (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
          (const char *)(unsigned int)PackageFamilyNameFromConditionalAce,
          dwCreationDispositionb);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&String1);
LABEL_25:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v35);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v34);
        LastError = v19;
        goto LABEL_31;
      }
      if ( String1 && !_wcsnicmp(String1, a2, 0x41u) )
      {
        *a3 = 1;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&String1);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v35);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v34);
        LastError = 0;
        goto LABEL_31;
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&String1);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v35);
    }
    v14 = ppDacl;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v34);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v29);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pObjectName);
  return 0;
}

```

## disassembly

```asm
0x180018ed0  mov     [rsp-28h+arg_0], rbx
0x180018ed5  push    rbp
0x180018ed6  push    rsi
0x180018ed7  push    rdi
0x180018ed8  push    r14
0x180018eda  push    r15
0x180018edc  mov     rbp, rsp
0x180018edf  sub     rsp, 80h
0x180018ee6  mov     byte ptr [r8], 0
0x180018eea  mov     r14, r8
0x180018eed  xor     r8d, r8d; unsigned __int64 *
0x180018ef0  mov     r15, rdx
0x180018ef3  mov     r11, rcx
0x180018ef6  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180018efb  mov     ebx, eax
0x180018efd  test    eax, eax
0x180018eff  jns     short loc_180018F1E
0x180018f01  mov     rcx, [rbp+28h]; this
0x180018f05  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180018f0c  mov     r9d, eax; char *
0x180018f0f  mov     edx, 1B24h; void *
0x180018f14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018f19  jmp     loc_1800191F1
0x180018f1e  mov     [rsp+80h+hTemplateFile], r8; hTemplateFile
0x180018f23  xor     r9d, r9d; lpSecurityAttributes
0x180018f26  mov     [rbp+pObjectName], r8
0x180018f2a  xor     edx, edx; dwDesiredAccess
0x180018f2c  mov     [rsp+80h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180018f34  mov     rcx, r11; lpFileName
0x180018f37  mov     [rsp+80h+dwCreationDisposition], 3; int
0x180018f3f  lea     r8d, [r9+7]; dwShareMode
0x180018f43  call    cs:__imp_CreateFileW
0x180018f49  mov     [rbp+var_20], rax
0x180018f4d  lea     rcx, [rax-1]
0x180018f51  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180018f55  ja      loc_1800191C8
0x180018f5b  lea     rdx, [rbp+pObjectName]
0x180018f5f  mov     rcx, rax
0x180018f62  call    ??$GetFinalPathNameByHandleW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@W4VolumePrefix@0@W4PathOptions@0@@Z; wil::GetFinalPathNameByHandleW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wil::VolumePrefix,wil::PathOptions)
0x180018f67  mov     ebx, eax
0x180018f69  test    eax, eax
0x180018f6b  jns     short loc_180018F8A
0x180018f6d  mov     rcx, [rbp+28h]; this
0x180018f71  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180018f78  mov     r9d, eax; char *
0x180018f7b  mov     edx, 1B29h; void *
0x180018f80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018f85  jmp     loc_1800191DF
0x180018f8a  mov     rcx, [rbp+pObjectName]; pObjectName
0x180018f8e  lea     rax, [rbp+arg_10]
0x180018f92  mov     [rbp+var_18], rax
0x180018f96  xor     r9d, r9d; ppsidOwner
0x180018f99  lea     rax, [rbp+var_10]
0x180018f9d  mov     [rbp+ppDacl], 0
0x180018fa5  mov     [rsp+80h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x180018faa  lea     rax, [rbp+ppDacl]
0x180018fae  mov     [rsp+80h+hTemplateFile], 0; ppSacl
0x180018fb7  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], rax; ppDacl
0x180018fbc  lea     edx, [r9+1]; ObjectType
0x180018fc0  lea     r8d, [r9+4]; SecurityInfo
0x180018fc4  mov     qword ptr [rsp+80h+dwCreationDisposition], 0; int
0x180018fcd  mov     [rbp+arg_10], 0
0x180018fd5  mov     [rbp+var_10], 0
0x180018fdd  mov     [rbp+var_8], 1
0x180018fe1  call    cs:__imp_GetNamedSecurityInfoW
0x180018fe7  lea     rcx, [rbp+var_18]
0x180018feb  mov     ebx, eax
0x180018fed  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x180018ff2  test    ebx, ebx
0x180018ff4  jz      short loc_180019013
0x180018ff6  mov     rcx, [rbp+28h]; this
0x180018ffa  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180019001  mov     r9d, ebx; char *
0x180019004  mov     edx, 1B2Eh; void *
0x180019009  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001900e  jmp     loc_18001919C
0x180019013  mov     rcx, [rbp+ppDacl]; pAcl
0x180019017  test    rcx, rcx
0x18001901a  jnz     short loc_18001903E
0x18001901c  mov     rcx, [rbp+28h]; this
0x180019020  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180019027  mov     ebx, 80070490h
0x18001902c  mov     edx, 1B30h; void *
0x180019031  mov     r9d, ebx; char *
0x180019034  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019039  jmp     loc_18001919E
0x18001903e  movzx   esi, word ptr [rcx+4]
0x180019042  xor     ebx, ebx
0x180019044  cmp     ebx, esi
0x180019046  jnb     loc_1800191A9
0x18001904c  lea     r8, [rbp+pAce]; pAce
0x180019050  mov     [rbp+pAce], 0
0x180019058  mov     edx, ebx; dwAceIndex
0x18001905a  call    cs:__imp_GetAce
0x180019060  test    eax, eax
0x180019062  jz      loc_180019187
0x180019068  mov     rcx, [rbp+pAce]
0x18001906c  cmp     byte ptr [rcx], 9
0x18001906f  jnz     loc_180019105
0x180019075  add     rcx, 8; pSid
0x180019079  mov     edx, 1Bh; WellKnownSidType
0x18001907e  call    cs:__imp_IsWellKnownSid
0x180019084  test    eax, eax
0x180019086  jz      short loc_180019105
0x180019088  mov     rax, [rbp+pAce]
0x18001908c  mov     ecx, [rax+4]
0x18001908f  and     ecx, 1200A0h
0x180019095  cmp     ecx, 1200A0h
0x18001909b  jnz     short loc_180019105
0x18001909d  lea     rdx, [rbp+arg_18]
0x1800190a1  mov     [rbp+arg_18], 0
0x1800190a9  lea     rcx, [rbp+pAce]
0x1800190ad  call    GetConditionalAce
0x1800190b2  mov     edi, eax
0x1800190b4  test    eax, eax
0x1800190b6  js      loc_180019159
0x1800190bc  mov     rcx, [rbp+arg_18]
0x1800190c0  lea     rdx, [rbp+String1]
0x1800190c4  mov     [rbp+String1], 0
0x1800190cc  call    GetPackageFamilyNameFromConditionalAce
0x1800190d1  mov     edi, eax
0x1800190d3  test    eax, eax
0x1800190d5  js      short loc_180019136
0x1800190d7  mov     rcx, [rbp+String1]; String1
0x1800190db  test    rcx, rcx
0x1800190de  jz      short loc_1800190F3
0x1800190e0  mov     r8d, 41h ; 'A'; MaxCount
0x1800190e6  mov     rdx, r15; String2
0x1800190e9  call    cs:__imp__wcsnicmp
0x1800190ef  test    eax, eax
0x1800190f1  jz      short loc_180019110
0x1800190f3  lea     rcx, [rbp+String1]
0x1800190f7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800190fc  lea     rcx, [rbp+arg_18]
0x180019100  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180019105  mov     rcx, [rbp+ppDacl]
0x180019109  inc     ebx
0x18001910b  jmp     loc_180019044
0x180019110  lea     rcx, [rbp+String1]
0x180019114  mov     byte ptr [r14], 1
0x180019118  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001911d  lea     rcx, [rbp+arg_18]
0x180019121  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180019126  lea     rcx, [rbp+arg_10]
0x18001912a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001912f  xor     ebx, ebx
0x180019131  jmp     loc_1800191DF
0x180019136  mov     rcx, [rbp+28h]; this
0x18001913a  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180019141  mov     r9d, edi; char *
0x180019144  mov     edx, 1B48h; void *
0x180019149  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001914e  lea     rcx, [rbp+String1]
0x180019152  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180019157  jmp     short loc_180019171
0x180019159  mov     rcx, [rbp+28h]; this
0x18001915d  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180019164  mov     r9d, edi; char *
0x180019167  mov     edx, 1B44h; void *
0x18001916c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019171  lea     rcx, [rbp+arg_18]
0x180019175  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001917a  lea     rcx, [rbp+arg_10]
0x18001917e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180019183  mov     ebx, edi
0x180019185  jmp     short loc_1800191DF
0x180019187  mov     rcx, [rbp+28h]; this
0x18001918b  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180019192  mov     edx, 1B37h; void *
0x180019197  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001919c  mov     ebx, eax
0x18001919e  lea     rcx, [rbp+arg_10]
0x1800191a2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800191a7  jmp     short loc_1800191DF
0x1800191a9  lea     rcx, [rbp+arg_10]
0x1800191ad  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800191b2  lea     rcx, [rbp+var_20]
0x1800191b6  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800191bb  lea     rcx, [rbp+pObjectName]
0x1800191bf  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800191c4  xor     eax, eax
0x1800191c6  jmp     short loc_1800191F3
0x1800191c8  mov     rcx, [rbp+28h]; this
0x1800191cc  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800191d3  mov     edx, 1B28h; void *
0x1800191d8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800191dd  mov     ebx, eax
0x1800191df  lea     rcx, [rbp+var_20]
0x1800191e3  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800191e8  lea     rcx, [rbp+pObjectName]
0x1800191ec  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800191f1  mov     eax, ebx
0x1800191f3  mov     rbx, [rsp+80h+arg_0]
0x1800191fb  add     rsp, 80h
0x180019202  pop     r15
0x180019204  pop     r14
0x180019206  pop     rdi
0x180019207  pop     rsi
0x180019208  pop     rbp
0x180019209  retn
```
