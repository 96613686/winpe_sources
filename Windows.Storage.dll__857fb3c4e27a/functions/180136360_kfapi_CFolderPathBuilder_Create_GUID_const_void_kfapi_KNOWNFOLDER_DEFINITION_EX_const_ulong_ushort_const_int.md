# kfapi::CFolderPathBuilder::_Create(_GUID const &,void *,kfapi::KNOWNFOLDER_DEFINITION_EX const &,ulong,ushort const *,int *)

- ea: `0x180136360`
- end: `0x180136862`
- name: `?_Create@CFolderPathBuilder@kfapi@@CAJAEBU_GUID@@PEAXAEBUKNOWNFOLDER_DEFINITION_EX@2@KPEBGPEAH@Z`
- size: `1282`
- prototype: `__int64 __fastcall(const struct _GUID *, void *, const struct kfapi::KNOWNFOLDER_DEFINITION_EX *, unsigned int, LPCWSTR pszPath, int *)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180044240`
- `0x180136130`

## callees

- `0x18001a000`
- `0x180045540`
- `0x1800a759c`
- `0x1800d13a0`
- `0x180136360`
- `0x1801368b8`
- `0x180136974`
- `0x180136998`
- `0x18036a6fc`
- `0x1803a4cb0`
- `0x18065a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x18013683c`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x18013683c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013677c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013677c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x180136699`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x1801366bb`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x180136699`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x1801366bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18064853b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18064853b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1806484dd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1806484dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013652a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013652a`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18013684a`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18013684a`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18013676e`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18013676e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18013654b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18013654b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x1801367dd`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x1801367dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180136435`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801365c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180136435`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801365c7`
- `SHCORE!__imp_SHWindowsPolicy` at `0x1801363c4`
- `SHCORE!__imp_SHWindowsPolicy` at `0x1801363c4`
- `SHCORE!__imp_GUIDFromStringW` at `0x1801366dc`
- `SHCORE!__imp_GUIDFromStringW` at `0x1801366dc`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x180136614`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x180136614`
- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectoryExW` at `0x1801364f4`
- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectoryExW` at `0x1801364f4`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18013672e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18013672e`
- `api-ms-win-shcore-registry-l1-1-0!SHQueryValueExW` at `0x180648504`
- `api-ms-win-shcore-registry-l1-1-0!SHQueryValueExW` at `0x180648527`
- `api-ms-win-shcore-registry-l1-1-0!SHQueryValueExW` at `0x180648504`
- `api-ms-win-shcore-registry-l1-1-0!SHQueryValueExW` at `0x180648527`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHStringFromGUIDW` at `0x1806484a9`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHStringFromGUIDW` at `0x1806484a9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall kfapi::CFolderPathBuilder::_Create(
        const struct _GUID *a1,
        void *a2,
        const struct kfapi::KNOWNFOLDER_DEFINITION_EX *a3,
        int a4,
        WCHAR *pszPath,
        int *a6)
{
  const struct _GUID *v7; // r15
  const WCHAR *i; // rsi
  signed int Error; // ebx
  __int64 v10; // rax
  WCHAR *v11; // rcx
  _QWORD *v12; // rdx
  const WCHAR *v13; // r14
  const WCHAR *v14; // rcx
  int v15; // eax
  void *v16; // r8
  void *v17; // rcx
  DWORD FileAttributesW; // ebx
  int v19; // eax
  PWSTR *v21; // rax
  PWSTR v22; // rax
  PWSTR v23; // rax
  signed int LastError; // eax
  bool v25; // [rsp+30h] [rbp-D0h] BYREF
  int v26; // [rsp+34h] [rbp-CCh] BYREF
  int v27; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  PCWSTR pszStart; // [rsp+48h] [rbp-B8h] BYREF
  const struct _GUID *v30; // [rsp+50h] [rbp-B0h]
  void *v31; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v32[7]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v33; // [rsp+98h] [rbp-68h]
  _QWORD *v34; // [rsp+A0h] [rbp-60h]
  PSECURITY_DESCRIPTOR pSecurityDescriptor[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v36; // [rsp+B8h] [rbp-48h]
  WCHAR pszValue[40]; // [rsp+C0h] [rbp-40h] BYREF

  v7 = a1;
  v30 = a1;
  v31 = a2;
  v27 = a4;
  i = 0;
  *a6 = 0;
  Error = 0;
  if ( (unsigned int)(*(_DWORD *)a3 - 3) <= 1 )
  {
    if ( (unsigned int)SHWindowsPolicy(&POLID_DisableKnownFolders) )
    {
      if ( (int)SHStringFromGUIDW(v7, pszValue, 39) >= 0 )
      {
        pv = 0;
        if ( !RegOpenKeyExW(
                HKEY_CURRENT_USER,
                L"Software\\Policies\\Microsoft\\Windows\\Explorer\\DisableKnownFolders",
                0,
                0x20019u,
                (PHKEY)&pv) )
        {
          if ( !SHQueryValueExW((HKEY)pv, pszValue, 0, 0, 0, 0)
            || !SHQueryValueExW((HKEY)pv, *((LPCWSTR *)a3 + 1), 0, 0, 0, 0) )
          {
            Error = -2147023636;
          }
          RegCloseKey((HKEY)pv);
        }
      }
    }
  }
  v26 = Error;
  if ( Error < 0 )
    goto LABEL_70;
  v10 = *((_QWORD *)a3 + 3) - *(_QWORD *)&GUID_NULL.Data1;
  if ( !v10 )
    v10 = *((_QWORD *)a3 + 4) - *(_QWORD *)GUID_NULL.Data4;
  if ( v10 )
  {
    pv = 0;
    Error = SHGetKnownFolderPath_Internal(
              (struct _GUID *)((char *)a3 + 24),
              v27 & 0xEFFFF7FF,
              v31,
              (unsigned __int16 **)&pv);
    v26 = Error;
    if ( (v27 & 0x20000000) != 0 )
      CZeroInitNew::operator delete(pv);
    else
      CoTaskMemFree(pv);
  }
  v32[0] = off_180671710;
  v32[1] = &v27;
  v32[2] = &v31;
  v33 = v32;
  v34 = v32;
  if ( (v27 & 0x20000000) == 0 )
  {
    v11 = 0;
    pszStart = 0;
    if ( *((_QWORD *)a3 + 19) )
    {
      v21 = (PWSTR *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pszStart);
      if ( PSPropertyBag_ReadStrAlloc(*((IPropertyBag **)a3 + 19), L"FoldersDependentOn", v21) >= 0 )
      {
        for ( i = pszStart; ; i = v13 )
        {
          if ( !i || !*i )
            goto LABEL_54;
          v22 = StrChrW(i, 0x3Bu);
          v13 = v22;
          if ( v22 )
          {
            *v22 = 0;
            v13 = v22 + 1;
          }
          v7 = 0;
          v23 = StrChrW(i, 0x2Cu);
          if ( v23 )
          {
            *v23 = 0;
            v7 = (const struct _GUID *)(unsigned int)wcstol(v23 + 1, 0, 16);
          }
          *(GUID *)pSecurityDescriptor = GUID_NULL;
          if ( !(unsigned int)GUIDFromStringW(i) )
          {
LABEL_54:
            v7 = v30;
            i = 0;
            goto LABEL_37;
          }
          LODWORD(pv) = (_DWORD)v7;
          if ( !v33 )
            break;
          (*(void (__fastcall **)(_QWORD *, PSECURITY_DESCRIPTOR *, LPVOID *))(*v33 + 16LL))(
            v33,
            pSecurityDescriptor,
            &pv);
        }
        std::_Xbad_function_call();
        goto LABEL_75;
      }
LABEL_37:
      v11 = (WCHAR *)pszStart;
    }
    if ( v11 )
      CoTaskMemFree(v11);
  }
  if ( v33 )
  {
    v12 = v32;
    LOBYTE(v12) = v33 != v32;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v33 + 32LL))(v33, v12);
  }
  if ( Error < 0 )
    goto LABEL_70;
  if ( (*((_BYTE *)a3 + 92) & 0x10) == 0 )
  {
    LODWORD(v13) = v27;
    pv = 0;
    *(_OWORD *)pSecurityDescriptor = 0;
    v36 = 0;
    v14 = (const WCHAR *)*((_QWORD *)a3 + 10);
    if ( v14 )
    {
      if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v14, 1u, &pv, 0) )
      {
        LODWORD(pSecurityDescriptor[0]) = 24;
        LODWORD(v36) = 0;
        pSecurityDescriptor[1] = pv;
        i = (const WCHAR *)pSecurityDescriptor;
      }
      else
      {
        Error = ResultFromLastError();
        if ( Error < 0 )
          goto LABEL_22;
      }
    }
    v15 = SHCreateDirectoryExW(0, pszPath, (const SECURITY_ATTRIBUTES *)i);
    Error = v15;
    if ( v15 > 0 )
      Error = (unsigned __int16)v15 | 0x80070000;
    if ( Error == -2147024713 )
      goto LABEL_21;
LABEL_75:
    if ( Error == -2147024816 )
    {
LABEL_21:
      if ( i && ((unsigned int)v13 & 0x10000000) != 0 )
        Error = kfapi::_ApplyAces(pszPath, pSecurityDescriptor[1], v16);
    }
LABEL_22:
    v17 = pv;
    pv = 0;
    LocalFree(v17);
    goto LABEL_23;
  }
  Error = kfapi::_CreateFile(a3, (const struct kfapi::KNOWNFOLDER_DEFINITION_EX *)pszPath, (const unsigned __int16 *)a3);
LABEL_23:
  v26 = Error;
  if ( Error < 0 )
  {
    if ( Error != -2147024713 && Error != -2147024816 && (Error != -2147024891 || !PathIsRootW(pszPath)) )
      goto LABEL_32;
    FileAttributesW = GetFileAttributesW(pszPath);
    if ( FileAttributesW == -1 )
    {
      v19 = ResultFromLastError();
      if ( v19 < 0 )
        goto LABEL_28;
    }
    else
    {
      v19 = 0;
    }
    if ( ((*((_BYTE *)a3 + 92) | (unsigned __int8)FileAttributesW) & 0x10) == 0 )
    {
      v19 = -2147024816;
      Error = -2147024816;
      v26 = -2147024816;
LABEL_29:
      if ( v19 < 0 )
        goto LABEL_32;
      goto LABEL_30;
    }
LABEL_28:
    Error = v19;
    v26 = v19;
    v25 = 0;
    if ( v19 == -2147024891 )
    {
      if ( IsRunningInAppContainer(v31, &v25) < 0 || !v25 )
        goto LABEL_32;
      Error = 0;
      v26 = 0;
      goto LABEL_30;
    }
    goto LABEL_29;
  }
  *a6 = 1;
  DataLayerTelemetry::CreateKnownFolder<_GUID const &,unsigned long &,long &>(v7, &v27, &v26);
LABEL_30:
  if ( (*a6 || (v27 & 0x10000000) != 0)
    && (*((_DWORD *)a3 + 22) & 0x182027) != 0
    && !SetFileAttributesW(pszPath, *((_DWORD *)a3 + 22) & 0x182027) )
  {
    LastError = GetLastError();
    Error = LastError;
    if ( LastError > 0 )
      Error = (unsigned __int16)LastError | 0x80070000;
    if ( Error >= 0 )
      Error = -2147467259;
    v26 = Error;
  }
LABEL_32:
  if ( Error < 0 )
LABEL_70:
    DataLayerTelemetry::CreateKnownFolder<_GUID const &,unsigned long &,long &>(v7, &v27, &v26);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180136360  push    rbp
0x180136362  push    rbx
0x180136363  push    rsi
0x180136364  push    rdi
0x180136365  push    r12
0x180136367  push    r13
0x180136369  push    r14
0x18013636b  push    r15
0x18013636d  lea     rbp, [rsp-28h]
0x180136372  sub     rsp, 128h
0x180136379  mov     rax, cs:__security_cookie
0x180136380  xor     rax, rsp
0x180136383  mov     [rbp+60h+var_50], rax
0x180136387  mov     rdi, r8
0x18013638a  mov     r15, rcx
0x18013638d  mov     [rsp+160h+var_110], rcx
0x180136392  mov     [rsp+160h+var_108], rdx
0x180136397  mov     [rsp+160h+var_128], r9d
0x18013639c  mov     r12, [rbp+60h+pszPath]
0x1801363a3  mov     r13, [rbp+60h+arg_28]
0x1801363aa  xor     esi, esi
0x1801363ac  mov     [r13+0], esi
0x1801363b0  mov     ebx, esi
0x1801363b2  mov     eax, [r8]
0x1801363b5  sub     eax, 3
0x1801363b8  cmp     eax, 1
0x1801363bb  ja      short loc_1801363D2
0x1801363bd  lea     rcx, POLID_DisableKnownFolders
0x1801363c4  call    cs:__imp_SHWindowsPolicy
0x1801363ca  test    eax, eax
0x1801363cc  jnz     loc_18064849C
0x1801363d2  mov     [rsp+160h+var_12C], ebx
0x1801363d6  test    ebx, ebx
0x1801363d8  js      loc_1801367F0
0x1801363de  lea     rcx, [rdi+18h]; struct _GUID *
0x1801363e2  mov     rax, [rcx]
0x1801363e5  sub     rax, qword ptr cs:GUID_NULL.Data1
0x1801363ec  jnz     short loc_1801363F9
0x1801363ee  mov     rax, [rcx+8]
0x1801363f2  sub     rax, qword ptr cs:GUID_NULL.Data4
0x1801363f9  test    rax, rax
0x1801363fc  jz      short loc_18013643B
0x1801363fe  mov     [rsp+160h+pv], rsi
0x180136403  mov     edx, [rsp+160h+var_128]
0x180136407  and     edx, 0EFFFF7FFh; unsigned int
0x18013640d  lea     r9, [rsp+160h+pv]; unsigned __int16 **
0x180136412  mov     r8, [rsp+160h+var_108]; void *
0x180136417  call    SHGetKnownFolderPath_Internal
0x18013641c  mov     ebx, eax
0x18013641e  mov     [rsp+160h+var_12C], eax
0x180136422  mov     rcx, [rsp+160h+pv]; lpMem
0x180136427  test    [rsp+160h+var_128], 20000000h
0x18013642f  jnz     loc_1801365D3
0x180136435  call    cs:__imp_CoTaskMemFree
0x18013643b  lea     rax, off_180671710
0x180136442  mov     [rsp+160h+var_100], rax
0x180136447  lea     rax, [rsp+160h+var_128]
0x18013644c  mov     [rsp+160h+var_F8], rax
0x180136451  lea     rax, [rsp+160h+var_108]
0x180136456  mov     [rsp+160h+var_F0], rax
0x18013645b  lea     rax, [rsp+160h+var_100]
0x180136460  mov     [rbp+60h+var_C8], rax
0x180136464  lea     rax, [rsp+160h+var_100]
0x180136469  mov     [rbp+60h+var_C0], rax
0x18013646d  test    [rsp+160h+var_128], 20000000h
0x180136475  jnz     short loc_180136496
0x180136477  mov     rcx, rsi; pv
0x18013647a  mov     [rsp+160h+pszStart], rcx
0x18013647f  cmp     qword ptr [rdi+98h], 0
0x180136487  jnz     loc_1801365F9
0x18013648d  test    rcx, rcx
0x180136490  jnz     loc_1801365C7
0x180136496  mov     rcx, [rbp+60h+var_C8]
0x18013649a  test    rcx, rcx
0x18013649d  jz      short loc_1801364B6
0x18013649f  mov     rax, [rcx]
0x1801364a2  lea     rdx, [rsp+160h+var_100]
0x1801364a7  cmp     rcx, rdx
0x1801364aa  setnz   dl
0x1801364ad  mov     rax, [rax+20h]
0x1801364b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801364b6  test    ebx, ebx
0x1801364b8  js      loc_1801367F0
0x1801364be  test    byte ptr [rdi+5Ch], 10h
0x1801364c2  jnz     loc_18013663A
0x1801364c8  mov     r14d, [rsp+160h+var_128]
0x1801364cd  mov     [rsp+160h+pv], rsi
0x1801364d2  xorps   xmm0, xmm0
0x1801364d5  xor     eax, eax
0x1801364d7  movups  xmmword ptr [rbp+60h+pSecurityDescriptor], xmm0
0x1801364db  mov     [rbp+60h+var_A8], rax
0x1801364df  mov     rcx, [rdi+50h]; StringSecurityDescriptor
0x1801364e3  test    rcx, rcx
0x1801364e6  jnz     loc_180136721
0x1801364ec  mov     r8, rsi; psa
0x1801364ef  mov     rdx, r12; pszPath
0x1801364f2  xor     ecx, ecx; hwnd
0x1801364f4  call    cs:__imp_SHCreateDirectoryExW
0x1801364fa  mov     ebx, eax
0x1801364fc  test    eax, eax
0x1801364fe  jle     short loc_180136509
0x180136500  movzx   ebx, ax
0x180136503  or      ebx, 80070000h
0x180136509  cmp     ebx, 800700B7h
0x18013650f  jnz     loc_180136851
0x180136515  test    rsi, rsi
0x180136518  jnz     loc_1801367A4
0x18013651e  mov     rcx, [rsp+160h+pv]; hMem
0x180136523  xor     esi, esi
0x180136525  mov     [rsp+160h+pv], rsi
0x18013652a  call    cs:__imp_LocalFree
0x180136530  mov     [rsp+160h+var_12C], ebx
0x180136534  test    ebx, ebx
0x180136536  jns     loc_1801365DD
0x18013653c  cmp     ebx, 800700B7h
0x180136542  jnz     loc_1801367C2
0x180136548  mov     rcx, r12; lpFileName
0x18013654b  call    cs:__imp_GetFileAttributesW
0x180136551  mov     ebx, eax
0x180136553  cmp     eax, 0FFFFFFFFh
0x180136556  jz      loc_180136628
0x18013655c  mov     eax, esi
0x18013655e  or      ebx, [rdi+5Ch]
0x180136561  test    bl, 10h
0x180136564  jz      loc_180136807
0x18013656a  mov     ebx, eax
0x18013656c  mov     [rsp+160h+var_12C], eax
0x180136570  mov     [rsp+160h+var_130], 0
0x180136575  cmp     eax, 80070005h
0x18013657a  jz      loc_18013664C
0x180136580  test    eax, eax
0x180136582  js      short loc_18013659D
0x180136584  cmp     dword ptr [r13+0], 0
0x180136589  jnz     loc_18013675C
0x18013658f  test    [rsp+160h+var_128], 10000000h
0x180136597  jnz     loc_18013675C
0x18013659d  test    ebx, ebx
0x18013659f  js      loc_1801367F0
0x1801365a5  mov     eax, ebx
0x1801365a7  mov     rcx, [rbp+60h+var_50]
0x1801365ab  xor     rcx, rsp; StackCookie
0x1801365ae  call    __security_check_cookie
0x1801365b3  add     rsp, 128h
0x1801365ba  pop     r15
0x1801365bc  pop     r14
0x1801365be  pop     r13
0x1801365c0  pop     r12
0x1801365c2  pop     rdi
0x1801365c3  pop     rsi
0x1801365c4  pop     rbx
0x1801365c5  pop     rbp
0x1801365c6  retn
0x1801365c7  call    cs:__imp_CoTaskMemFree
0x1801365cd  nop
0x1801365ce  jmp     loc_180136496
0x1801365d3  call    ??3CZeroInitNew@@SAXPEAX@Z; CZeroInitNew::operator delete(void *)
0x1801365d8  jmp     loc_18013643B
0x1801365dd  mov     dword ptr [r13+0], 1
0x1801365e5  lea     r8, [rsp+160h+var_12C]
0x1801365ea  lea     rdx, [rsp+160h+var_128]
0x1801365ef  mov     rcx, r15
0x1801365f2  call    ??$CreateKnownFolder@AEBU_GUID@@AEAKAEAJ@DataLayerTelemetry@@SAXAEBU_GUID@@AEAKAEAJ@Z; DataLayerTelemetry::CreateKnownFolder<_GUID const &,ulong &,long &>(_GUID const &,ulong &,long &)
0x1801365f7  jmp     short loc_180136584
0x1801365f9  lea     rcx, [rsp+160h+pszStart]
0x1801365fe  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x180136603  mov     r8, rax; value
0x180136606  lea     rdx, aFoldersdepende; "FoldersDependentOn"
0x18013660d  mov     rcx, [rdi+98h]; propBag
0x180136614  call    cs:__imp_PSPropertyBag_ReadStrAlloc
0x18013661a  test    eax, eax
0x18013661c  jns     short loc_180136679
0x18013661e  mov     rcx, [rsp+160h+pszStart]
0x180136623  jmp     loc_18013648D
0x180136628  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18013662d  test    eax, eax
0x18013662f  jns     loc_18013655E
0x180136635  jmp     loc_18013656A
0x18013663a  mov     rdx, r12; struct kfapi::KNOWNFOLDER_DEFINITION_EX *
0x18013663d  mov     rcx, rdi; this
0x180136640  call    ?_CreateFile@kfapi@@YAJAEBUKNOWNFOLDER_DEFINITION_EX@1@PEBG@Z; kfapi::_CreateFile(kfapi::KNOWNFOLDER_DEFINITION_EX const &,ushort const *)
0x180136645  mov     ebx, eax
0x180136647  jmp     loc_180136530
0x18013664c  lea     rdx, [rsp+160h+var_130]; bool *
0x180136651  mov     rcx, [rsp+160h+var_108]; void *
0x180136656  call    ?IsRunningInAppContainer@@YAJPEAXPEA_N@Z; IsRunningInAppContainer(void *,bool *)
0x18013665b  test    eax, eax
0x18013665d  js      loc_18013659D
0x180136663  cmp     [rsp+160h+var_130], 0
0x180136668  jz      loc_18013659D
0x18013666e  mov     ebx, esi
0x180136670  mov     [rsp+160h+var_12C], ebx
0x180136674  jmp     loc_180136584
0x180136679  mov     rsi, [rsp+160h+pszStart]
0x18013667e  test    rsi, rsi
0x180136681  jz      loc_180136715
0x180136687  cmp     word ptr [rsi], 0
0x18013668b  jz      loc_180136715
0x180136691  mov     edx, 3Bh ; ';'; wMatch
0x180136696  mov     rcx, rsi; pszStart
0x180136699  call    cs:__imp_StrChrW
0x18013669f  mov     r14, rax
0x1801366a2  test    rax, rax
0x1801366a5  jz      short loc_1801366B0
0x1801366a7  xor     ecx, ecx
0x1801366a9  mov     [rax], cx
0x1801366ac  add     r14, 2
0x1801366b0  xor     r15d, r15d
0x1801366b3  mov     edx, 2Ch ; ','; wMatch
0x1801366b8  mov     rcx, rsi; pszStart
0x1801366bb  call    cs:__imp_StrChrW
0x1801366c1  test    rax, rax
0x1801366c4  jnz     loc_18013682B
0x1801366ca  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1801366d1  movups  xmmword ptr [rbp+60h+pSecurityDescriptor], xmm0
0x1801366d5  lea     rdx, [rbp+60h+pSecurityDescriptor]
0x1801366d9  mov     rcx, rsi
0x1801366dc  call    cs:__imp_GUIDFromStringW
0x1801366e2  test    eax, eax
0x1801366e4  jz      short loc_180136715
0x1801366e6  mov     dword ptr [rsp+160h+pv], r15d
0x1801366eb  mov     rcx, [rbp+60h+var_C8]
0x1801366ef  test    rcx, rcx
0x1801366f2  jz      loc_18013684A
0x1801366f8  mov     rax, [rcx]
0x1801366fb  lea     r8, [rsp+160h+pv]
0x180136700  lea     rdx, [rbp+60h+pSecurityDescriptor]
0x180136704  mov     rax, [rax+10h]
0x180136708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013670d  mov     rsi, r14
0x180136710  jmp     loc_18013667E
0x180136715  mov     r15, [rsp+160h+var_110]
0x18013671a  xor     esi, esi
0x18013671c  jmp     loc_18013661E
0x180136721  xor     r9d, r9d; SecurityDescriptorSize
0x180136724  lea     r8, [rsp+160h+pv]; SecurityDescriptor
0x180136729  mov     edx, 1; StringSDRevision
0x18013672e  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180136734  test    eax, eax
0x180136736  jz      loc_180136817
0x18013673c  mov     dword ptr [rbp+60h+pSecurityDescriptor], 18h
0x180136743  mov     dword ptr [rbp+60h+var_A8], 0
0x18013674a  mov     rax, [rsp+160h+pv]
0x18013674f  mov     [rbp+60h+pSecurityDescriptor+8], rax
0x180136753  lea     rsi, [rbp+60h+pSecurityDescriptor]
0x180136757  jmp     loc_1801364EC
0x18013675c  mov     edx, [rdi+58h]
0x18013675f  and     edx, 182027h; dwFileAttributes
0x180136765  jz      loc_18013659D
0x18013676b  mov     rcx, r12; lpFileName
0x18013676e  call    cs:__imp_SetFileAttributesW
0x180136774  test    eax, eax
0x180136776  jnz     loc_18013659D
0x18013677c  call    cs:__imp_GetLastError
0x180136782  mov     ebx, eax
0x180136784  test    eax, eax
0x180136786  jle     short loc_180136791
0x180136788  movzx   ebx, ax
0x18013678b  or      ebx, 80070000h
0x180136791  mov     eax, 80004005h
0x180136796  test    ebx, ebx
0x180136798  cmovns  ebx, eax
0x18013679b  mov     [rsp+160h+var_12C], ebx
0x18013679f  jmp     loc_18013659D
0x1801367a4  bt      r14d, 1Ch
0x1801367a9  jnb     loc_18013651E
0x1801367af  mov     rdx, [rbp+60h+pSecurityDescriptor+8]; pSecurityDescriptor
0x1801367b3  mov     rcx, r12; pObjectName
0x1801367b6  call    ?_ApplyAces@kfapi@@YAJPEBGPEAX@Z; kfapi::_ApplyAces(ushort const *,void *)
0x1801367bb  mov     ebx, eax
0x1801367bd  jmp     loc_18013651E
0x1801367c2  cmp     ebx, 80070050h
0x1801367c8  jz      loc_180136548
0x1801367ce  cmp     ebx, 80070005h
0x1801367d4  jnz     loc_18013659D
0x1801367da  mov     rcx, r12; pszPath
0x1801367dd  call    cs:__imp_PathIsRootW
0x1801367e3  test    eax, eax
0x1801367e5  jz      loc_18013659D
0x1801367eb  jmp     loc_180136548
0x1801367f0  lea     r8, [rsp+160h+var_12C]
0x1801367f5  lea     rdx, [rsp+160h+var_128]
0x1801367fa  mov     rcx, r15
0x1801367fd  call    ??$CreateKnownFolder@AEBU_GUID@@AEAKAEAJ@DataLayerTelemetry@@SAXAEBU_GUID@@AEAKAEAJ@Z; DataLayerTelemetry::CreateKnownFolder<_GUID const &,ulong &,long &>(_GUID const &,ulong &,long &)
0x180136802  jmp     loc_1801365A5
0x180136807  mov     eax, 80070050h
0x18013680c  mov     ebx, eax
0x18013680e  mov     [rsp+160h+var_12C], eax
0x180136812  jmp     loc_180136580
0x180136817  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18013681c  mov     ebx, eax
0x18013681e  test    eax, eax
0x180136820  jns     loc_1801364EC
0x180136826  jmp     loc_18013651E
0x18013682b  xor     ecx, ecx
0x18013682d  mov     [rax], cx
0x180136830  lea     rcx, [rax+2]; String
0x180136834  xor     edx, edx; EndPtr
0x180136836  mov     r8d, 10h; Radix
0x18013683c  call    cs:__imp_wcstol
0x180136842  mov     r15d, eax
  ... truncated ...
```
