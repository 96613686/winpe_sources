# OSIntegration::DEH::Internal::AppExecutionAliasHelper::WriteChanges(void)

- ea: `0x18015f3c0`
- end: `0x18015f8d7`
- name: `?WriteChanges@AppExecutionAliasHelper@Internal@DEH@OSIntegration@@UEAAJXZ`
- size: `1303`
- prototype: `__int64 __fastcall(OSIntegration::DEH::Internal::AppExecutionAliasHelper *this, __int64, __int64, bool *)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000e6e0`
- `0x180027e88`
- `0x18002ece0`
- `0x180052e28`
- `0x180070b78`
- `0x180087238`
- `0x1800926d4`
- `0x180098bf4`
- `0x1800a219c`
- `0x1800a2854`
- `0x1800b657c`
- `0x18015d56c`
- `0x18015d7d0`
- `0x18015f0b0`
- `0x18015f3c0`
- `0x1801e32c4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18015f6cc`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18015f6cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015f4f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015f54a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015f55d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015f5a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015f5b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015f5ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015f5ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015f69b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015f6aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015f4f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015f54a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015f55d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015f5a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015f5b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015f5ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015f5ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015f69b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015f6aa`
- `AppXAllUserStore!GetPackageSetupPhase` at `0x18015f61d`
- `AppXAllUserStore!GetPackageSetupPhase` at `0x18015f61d`
- `AppXAllUserStore!SetPackageOverrideSetupPhase` at `0x18015f654`
- `AppXAllUserStore!SetPackageOverrideSetupPhase` at `0x18015f654`

## pseudocode

```c
__int64 __fastcall OSIntegration::DEH::Internal::AppExecutionAliasHelper::WriteChanges(
        OSIntegration::DEH::Internal::AppExecutionAliasHelper *this,
        __int64 a2,
        __int64 a3,
        bool *a4)
{
  char v5; // bl
  int v6; // eax
  unsigned int v7; // ebx
  int ShouldCreateAliasFileAndAppExecutionAliasUser; // eax
  __int64 v10; // rdx
  struct Common::StringBuffer *v11; // r9
  unsigned int v12; // edi
  int v13; // eax
  void *v14; // rbx
  int v15; // eax
  bool *v16; // r8
  Common *v17; // rdi
  int v18; // r14d
  __int64 v19; // rdx
  int PackageSetupPhase; // eax
  int v21; // eax
  unsigned int v22; // esi
  HKEY *v23; // rax
  unsigned int v24; // eax
  int v25; // eax
  int v26; // eax
  __int64 v27; // rcx
  __int64 v28; // rdx
  int v29; // r12d
  char *v30; // r13
  Common::StringBuffer *v31; // rcx
  int DirectoryIfNecessary; // eax
  const unsigned __int16 *v33; // rdx
  __int64 v34; // rdx
  __int64 v35; // rcx
  int v36; // [rsp+20h] [rbp-59h]
  int v37; // [rsp+20h] [rbp-59h]
  Common *v38; // [rsp+50h] [rbp-29h] BYREF
  LPVOID v39; // [rsp+58h] [rbp-21h] BYREF
  __int128 v40; // [rsp+60h] [rbp-19h] BYREF
  int v41; // [rsp+70h] [rbp-9h]
  __int128 v42; // [rsp+78h] [rbp-1h] BYREF
  int v43; // [rsp+88h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  bool v45; // [rsp+E0h] [rbp+67h] BYREF
  HKEY hKey; // [rsp+E8h] [rbp+6Fh] BYREF
  bool v47; // [rsp+F0h] [rbp+77h] BYREF
  LPVOID pv; // [rsp+F8h] [rbp+7Fh] BYREF

  if ( *(_BYTE *)(*((_QWORD *)this + 3) + 403LL) )
    return 0;
  v5 = 0;
  LOBYTE(hKey) = 0;
  if ( !*((_BYTE *)this + 436) )
  {
    v6 = Common::Deployment::PathEndsWithFileName(
           *((Common::Deployment **)this + 31),
           (OSIntegration::DEH::Internal::AppExecutionAliasHelper *)((char *)this + 136),
           (const struct Common::COMMON_STRING *)&hKey,
           a4);
    v7 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x252,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\appexecutionalias\\appexecutionaliashelper.cpp",
        (const char *)(unsigned int)v6,
        v36);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x30D,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\appexecutionalias\\appexecutionaliashelper.cpp",
        (const char *)v7,
        v37);
      return v7;
    }
    v5 = (char)hKey;
  }
  v45 = 0;
  v47 = 0;
  ShouldCreateAliasFileAndAppExecutionAliasUser = OSIntegration::DEH::Internal::AppExecutionAliasHelper::ShouldCreateAliasFileAndAppExecutionAliasUser(
                                                    this,
                                                    &v45,
                                                    &v47);
  v12 = ShouldCreateAliasFileAndAppExecutionAliasUser;
  if ( ShouldCreateAliasFileAndAppExecutionAliasUser < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x311,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\appexecutionalias\\appexecutionaliashelper.cpp",
      (const char *)(unsigned int)ShouldCreateAliasFileAndAppExecutionAliasUser,
      v36);
    return v12;
  }
  if ( !v5 || !v45 )
  {
LABEL_50:
    if ( *((_BYTE *)this + 437) )
    {
      if ( v45 )
      {
        v40 = 0;
        v41 = 0;
        v26 = OSIntegration::Tools::ConcatenatePaths(
                (OSIntegration::DEH::Internal::AppExecutionAliasHelper *)((char *)this + 312),
                (OSIntegration::DEH::Internal::AppExecutionAliasHelper *)((char *)this + 136),
                (const struct Common::COMMON_STRING *)&v40,
                v11);
        v7 = v26;
        if ( v26 < 0 )
        {
          v28 = 850;
LABEL_56:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v28,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\appexecutionalias\\appexecutionaliashelper.cpp",
            (const char *)(unsigned int)v26,
            v36);
          v31 = (Common::StringBuffer *)&v40;
LABEL_57:
          Common::StringBuffer::~StringBuffer(v31);
          return v7;
        }
        v29 = (_DWORD)this + 240;
        v30 = (char *)this + 216;
        v36 = (_DWORD)this + 240;
        v26 = OSIntegration::DEH::Internal::AppExecutionAliasHelper::WriteAppExecAliasFile(
                v27,
                &v40,
                (char *)this + 192,
                (char *)this + 216);
        v7 = v26;
        if ( v26 < 0 )
        {
          v28 = 853;
          goto LABEL_56;
        }
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v40);
      }
      else
      {
        v29 = (_DWORD)this + 240;
        v30 = (char *)this + 216;
      }
      v42 = 0;
      v43 = 0;
      DirectoryIfNecessary = OSIntegration::Tools::ConcatenatePaths(
                               (OSIntegration::DEH::Internal::AppExecutionAliasHelper *)((char *)this + 336),
                               (OSIntegration::DEH::Internal::AppExecutionAliasHelper *)((char *)this + 136),
                               (const struct Common::COMMON_STRING *)&v42,
                               v11);
      v7 = DirectoryIfNecessary;
      if ( DirectoryIfNecessary >= 0 )
      {
        DirectoryIfNecessary = Common::CreateDirectoryIfNecessary(*((Common **)this + 43), v33);
        v7 = DirectoryIfNecessary;
        if ( DirectoryIfNecessary >= 0 )
        {
          v36 = v29;
          DirectoryIfNecessary = OSIntegration::DEH::Internal::AppExecutionAliasHelper::WriteAppExecAliasFile(
                                   v35,
                                   &v42,
                                   (char *)this + 192,
                                   v30);
          v7 = DirectoryIfNecessary;
          if ( DirectoryIfNecessary >= 0 )
          {
            v7 = 0;
            goto LABEL_68;
          }
          v34 = 860;
        }
        else
        {
          v34 = 859;
        }
      }
      else
      {
        v34 = 857;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v34,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\appexecutionalias\\appexecutionaliashelper.cpp",
        (const char *)(unsigned int)DirectoryIfNecessary,
        v36);
LABEL_68:
      v31 = (Common::StringBuffer *)&v42;
      goto LABEL_57;
    }
    return 0;
  }
  if ( !*(_BYTE *)(*((_QWORD *)this + 3) + 406LL) )
  {
    hKey = 0;
    v23 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
    v24 = RegOpenCurrentUser(0xF003Fu, v23);
    if ( v24 )
    {
      v7 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x342,
             (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\appexecutionalias\\appexecutionaliashelper.cpp",
             (const char *)v24,
             v36);
    }
    else
    {
      v25 = OSIntegration::DEH::Internal::AppExecutionAliasHelper::WriteAppPaths(this, hKey);
      v7 = v25;
      if ( v25 >= 0 )
      {
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        goto LABEL_50;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x343,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\appexecutionalias\\appexecutionaliashelper.cpp",
        (const char *)(unsigned int)v25,
        v36);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v7;
  }
  pv = 0;
  v38 = 0;
  v13 = wil::GetSystemDirectoryW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
          &pv,
          v10);
  v7 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x31E,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\appexecutionalias\\appexecutionaliashelper.cpp",
      (const char *)(unsigned int)v13,
      v36);
    if ( pv )
      CoTaskMemFree(pv);
    return v7;
  }
  hKey = (HKEY)*((_QWORD *)this + 18);
  v14 = pv;
  v39 = pv;
  v15 = wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,unsigned short *,unsigned short *>(
          &v38,
          &v39,
          &hKey);
  v12 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x31F,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\appexecutionalias\\appexecutionaliashelper.cpp",
      (const char *)(unsigned int)v15,
      v36);
    if ( v38 )
      CoTaskMemFree(v38);
    if ( v14 )
      CoTaskMemFree(v14);
    return v12;
  }
  LOBYTE(hKey) = 0;
  v17 = v38;
  v18 = Common::FileExists(v38, (const unsigned __int16 *)&hKey, v16);
  if ( v18 < 0 )
  {
    v19 = 802;
LABEL_23:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\appexecutionalias\\appexecutionaliashelper.cpp",
      (const char *)(unsigned int)v18,
      v36);
    if ( v17 )
      CoTaskMemFree(v17);
    if ( v14 )
      CoTaskMemFree(v14);
    return (unsigned int)v18;
  }
  if ( !(_BYTE)hKey )
  {
    v18 = OSIntegration::DEH::Internal::AppExecutionAliasHelper::WriteAppPaths(this, HKEY_LOCAL_MACHINE);
    if ( v18 < 0 )
    {
      v19 = 805;
      goto LABEL_23;
    }
    if ( v17 )
      CoTaskMemFree(v17);
    if ( v14 )
      CoTaskMemFree(v14);
    goto LABEL_50;
  }
  LODWORD(hKey) = 0;
  PackageSetupPhase = GetPackageSetupPhase(*(_QWORD *)(*((_QWORD *)this + 3) + 248LL), &hKey);
  if ( PackageSetupPhase < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x331,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\appexecutionalias\\appexecutionaliashelper.cpp",
      (const char *)(unsigned int)PackageSetupPhase,
      v36);
  LODWORD(hKey) = (unsigned int)hKey & 0xFFFFFBFF;
  v21 = SetPackageOverrideSetupPhase(*(_QWORD *)(*((_QWORD *)this + 3) + 248LL));
  if ( v21 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x335,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\appexecutionalias\\appexecutionaliashelper.cpp",
      (const char *)(unsigned int)v21,
      v36);
  v22 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0x337,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\appexecutionalias\\appexecutionaliashelper.cpp",
          (const char *)0x3D01,
          v36);
  if ( v17 )
    CoTaskMemFree(v17);
  if ( v14 )
    CoTaskMemFree(v14);
  return v22;
}

```

## disassembly

```asm
0x18015f3c0  push    rbp
0x18015f3c2  push    rbx
0x18015f3c3  push    rsi
0x18015f3c4  push    rdi
0x18015f3c5  push    r12
0x18015f3c7  push    r13
0x18015f3c9  push    r14
0x18015f3cb  push    r15
0x18015f3cd  lea     rbp, [rsp-1Fh]
0x18015f3d2  sub     rsp, 98h
0x18015f3d9  mov     rsi, rcx
0x18015f3dc  mov     rax, [rcx+18h]
0x18015f3e0  xor     r15d, r15d
0x18015f3e3  cmp     [rax+193h], r15b
0x18015f3ea  jnz     loc_18015F8C1
0x18015f3f0  mov     bl, r15b
0x18015f3f3  mov     byte ptr [rbp+57h+hKey], bl
0x18015f3f6  cmp     [rcx+1B4h], r15b
0x18015f3fd  jnz     short loc_18015F456
0x18015f3ff  lea     rdx, [rcx+88h]; struct Common::COMMON_STRING *
0x18015f406  lea     r8, [rbp+57h+hKey]; struct Common::COMMON_STRING *
0x18015f40a  mov     rcx, [rcx+0F8h]; this
0x18015f411  call    ?PathEndsWithFileName@Deployment@Common@@YAJPEBGPEBUCOMMON_STRING@2@PEA_N@Z; Common::Deployment::PathEndsWithFileName(ushort const *,Common::COMMON_STRING const *,bool *)
0x18015f416  mov     ebx, eax
0x18015f418  test    eax, eax
0x18015f41a  jns     short loc_18015F453
0x18015f41c  mov     rcx, [rbp+5Fh]; this
0x18015f420  mov     r9d, eax; char *
0x18015f423  lea     r8, aOnecoreAdminAp_90; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18015f42a  mov     edx, 252h; void *
0x18015f42f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015f434  mov     rcx, [rbp+5Fh]; this
0x18015f438  mov     r9d, ebx; char *
0x18015f43b  lea     r8, aOnecoreAdminAp_90; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18015f442  mov     edx, 30Dh; void *
0x18015f447  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015f44c  mov     eax, ebx
0x18015f44e  jmp     loc_18015F8C3
0x18015f453  mov     bl, byte ptr [rbp+57h+hKey]
0x18015f456  mov     [rbp+57h+arg_0], r15b
0x18015f45a  mov     [rbp+57h+arg_10], r15b
0x18015f45e  lea     r8, [rbp+57h+arg_10]; bool *
0x18015f462  lea     rdx, [rbp+57h+arg_0]; bool *
0x18015f466  mov     rcx, rsi; this
0x18015f469  call    ?ShouldCreateAliasFileAndAppExecutionAliasUser@AppExecutionAliasHelper@Internal@DEH@OSIntegration@@AEAAJAEA_N0@Z; OSIntegration::DEH::Internal::AppExecutionAliasHelper::ShouldCreateAliasFileAndAppExecutionAliasUser(bool &,bool &)
0x18015f46e  mov     edi, eax
0x18015f470  test    eax, eax
0x18015f472  jns     short loc_18015F493
0x18015f474  mov     rcx, [rbp+5Fh]; this
0x18015f478  mov     r9d, eax; char *
0x18015f47b  lea     r8, aOnecoreAdminAp_90; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18015f482  mov     edx, 311h; void *
0x18015f487  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015f48c  mov     eax, edi
0x18015f48e  jmp     loc_18015F8C3
0x18015f493  test    bl, bl
0x18015f495  jz      loc_18015F734
0x18015f49b  cmp     [rbp+57h+arg_0], r15b
0x18015f49f  jz      loc_18015F734
0x18015f4a5  mov     rax, [rsi+18h]
0x18015f4a9  cmp     [rax+196h], r15b
0x18015f4b0  jz      loc_18015F6B7
0x18015f4b6  mov     [rbp+57h+pv], r15
0x18015f4ba  mov     [rbp+57h+var_80], r15
0x18015f4be  lea     rcx, [rbp+57h+pv]
0x18015f4c2  call    ??$GetSystemDirectoryW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::GetSystemDirectoryW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18015f4c7  mov     ebx, eax
0x18015f4c9  test    eax, eax
0x18015f4cb  jns     short loc_18015F4FE
0x18015f4cd  mov     rcx, [rbp+5Fh]; this
0x18015f4d1  mov     r9d, eax; char *
0x18015f4d4  lea     r8, aOnecoreAdminAp_90; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18015f4db  mov     edx, 31Eh; void *
0x18015f4e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015f4e5  nop
0x18015f4e6  mov     rcx, [rbp+57h+pv]; pv
0x18015f4ea  test    rcx, rcx
0x18015f4ed  jz      loc_18015F44C
0x18015f4f3  call    cs:__imp_CoTaskMemFree
0x18015f4f9  jmp     loc_18015F44C
0x18015f4fe  mov     rax, [rsi+90h]
0x18015f505  mov     [rbp+57h+hKey], rax
0x18015f509  mov     rbx, [rbp+57h+pv]
0x18015f50d  mov     [rbp+57h+var_78], rbx
0x18015f511  lea     r8, [rbp+57h+hKey]
0x18015f515  lea     rdx, [rbp+57h+var_78]
0x18015f519  lea     rcx, [rbp+57h+var_80]
0x18015f51d  call    ??$str_concat_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAGPEAG@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBQEAG1@Z; wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,ushort *,ushort *>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort * const &,ushort * const &)
0x18015f522  mov     edi, eax
0x18015f524  test    eax, eax
0x18015f526  jns     short loc_18015F568
0x18015f528  mov     rcx, [rbp+5Fh]; this
0x18015f52c  mov     r9d, eax; char *
0x18015f52f  lea     r8, aOnecoreAdminAp_90; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18015f536  mov     edx, 31Fh; void *
0x18015f53b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015f540  nop
0x18015f541  mov     rcx, [rbp+57h+var_80]; pv
0x18015f545  test    rcx, rcx
0x18015f548  jz      short loc_18015F551
0x18015f54a  call    cs:__imp_CoTaskMemFree
0x18015f550  nop
0x18015f551  test    rbx, rbx
0x18015f554  jz      loc_18015F48C
0x18015f55a  mov     rcx, rbx; pv
0x18015f55d  call    cs:__imp_CoTaskMemFree
0x18015f563  jmp     loc_18015F48C
0x18015f568  mov     byte ptr [rbp+57h+hKey], r15b
0x18015f56c  lea     rdx, [rbp+57h+hKey]; unsigned __int16 *
0x18015f570  mov     rdi, [rbp+57h+var_80]
0x18015f574  mov     rcx, rdi; this
0x18015f577  call    ?FileExists@Common@@YAJPEBGPEA_N@Z; Common::FileExists(ushort const *,bool *)
0x18015f57c  mov     r14d, eax
0x18015f57f  test    eax, eax
0x18015f581  jns     short loc_18015F5C1
0x18015f583  mov     edx, 322h; void *
0x18015f588  mov     r9d, r14d; char *
0x18015f58b  lea     r8, aOnecoreAdminAp_90; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18015f592  mov     rcx, [rbp+5Fh]; this
0x18015f596  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015f59b  nop
0x18015f59c  test    rdi, rdi
0x18015f59f  jz      short loc_18015F5AB
0x18015f5a1  mov     rcx, rdi; pv
0x18015f5a4  call    cs:__imp_CoTaskMemFree
0x18015f5aa  nop
0x18015f5ab  test    rbx, rbx
0x18015f5ae  jz      short loc_18015F5B9
0x18015f5b0  mov     rcx, rbx; pv
0x18015f5b3  call    cs:__imp_CoTaskMemFree
0x18015f5b9  mov     eax, r14d
0x18015f5bc  jmp     loc_18015F8C3
0x18015f5c1  cmp     byte ptr [rbp+57h+hKey], r15b
0x18015f5c5  jnz     short loc_18015F60A
0x18015f5c7  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18015f5ce  mov     rcx, rsi; this
0x18015f5d1  call    ?WriteAppPaths@AppExecutionAliasHelper@Internal@DEH@OSIntegration@@AEAAJPEAUHKEY__@@@Z; OSIntegration::DEH::Internal::AppExecutionAliasHelper::WriteAppPaths(HKEY__ *)
0x18015f5d6  mov     r14d, eax
0x18015f5d9  test    eax, eax
0x18015f5db  jns     short loc_18015F5E4
0x18015f5dd  mov     edx, 325h
0x18015f5e2  jmp     short loc_18015F588
0x18015f5e4  test    rdi, rdi
0x18015f5e7  jz      short loc_18015F5F3
0x18015f5e9  mov     rcx, rdi; pv
0x18015f5ec  call    cs:__imp_CoTaskMemFree
0x18015f5f2  nop
0x18015f5f3  test    rbx, rbx
0x18015f5f6  jz      loc_18015F734
0x18015f5fc  mov     rcx, rbx; pv
0x18015f5ff  call    cs:__imp_CoTaskMemFree
0x18015f605  jmp     loc_18015F734
0x18015f60a  mov     dword ptr [rbp+57h+hKey], r15d
0x18015f60e  mov     rcx, [rsi+18h]
0x18015f612  lea     rdx, [rbp+57h+hKey]
0x18015f616  mov     rcx, [rcx+0F8h]
0x18015f61d  call    cs:__imp_GetPackageSetupPhase
0x18015f623  mov     rcx, [rbp+5Fh]; this
0x18015f627  test    eax, eax
0x18015f629  jns     short loc_18015F63F
0x18015f62b  mov     r9d, eax; char *
0x18015f62e  lea     r8, aOnecoreAdminAp_90; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18015f635  mov     edx, 331h; void *
0x18015f63a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18015f63f  mov     edx, dword ptr [rbp+57h+hKey]
0x18015f642  btr     edx, 0Ah
0x18015f646  mov     dword ptr [rbp+57h+hKey], edx
0x18015f649  mov     rcx, [rsi+18h]
0x18015f64d  mov     rcx, [rcx+0F8h]
0x18015f654  call    cs:__imp_SetPackageOverrideSetupPhase
0x18015f65a  mov     rcx, [rbp+5Fh]; this
0x18015f65e  test    eax, eax
0x18015f660  jns     short loc_18015F676
0x18015f662  mov     r9d, eax; char *
0x18015f665  lea     r8, aOnecoreAdminAp_90; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18015f66c  mov     edx, 335h; void *
0x18015f671  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18015f676  mov     rcx, [rbp+5Fh]; this
0x18015f67a  mov     r9d, 3D01h; char *
0x18015f680  lea     r8, aOnecoreAdminAp_90; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18015f687  mov     edx, 337h; void *
0x18015f68c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18015f691  mov     esi, eax
0x18015f693  test    rdi, rdi
0x18015f696  jz      short loc_18015F6A2
0x18015f698  mov     rcx, rdi; pv
0x18015f69b  call    cs:__imp_CoTaskMemFree
0x18015f6a1  nop
0x18015f6a2  test    rbx, rbx
0x18015f6a5  jz      short loc_18015F6B0
0x18015f6a7  mov     rcx, rbx; pv
0x18015f6aa  call    cs:__imp_CoTaskMemFree
0x18015f6b0  mov     eax, esi
0x18015f6b2  jmp     loc_18015F8C3
0x18015f6b7  mov     [rbp+57h+hKey], r15
0x18015f6bb  lea     rcx, [rbp+57h+hKey]
0x18015f6bf  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18015f6c4  mov     rdx, rax; phkResult
0x18015f6c7  mov     ecx, 0F003Fh; samDesired
0x18015f6cc  call    cs:__imp_RegOpenCurrentUser
0x18015f6d2  test    eax, eax
0x18015f6d4  jz      short loc_18015F6F2
0x18015f6d6  mov     rcx, [rbp+5Fh]; this
0x18015f6da  mov     r9d, eax; char *
0x18015f6dd  lea     r8, aOnecoreAdminAp_90; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18015f6e4  mov     edx, 342h; void *
0x18015f6e9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18015f6ee  mov     ebx, eax
0x18015f6f0  jmp     short loc_18015F71D
0x18015f6f2  mov     rdx, [rbp+57h+hKey]; hKey
0x18015f6f6  mov     rcx, rsi; this
0x18015f6f9  call    ?WriteAppPaths@AppExecutionAliasHelper@Internal@DEH@OSIntegration@@AEAAJPEAUHKEY__@@@Z; OSIntegration::DEH::Internal::AppExecutionAliasHelper::WriteAppPaths(HKEY__ *)
0x18015f6fe  mov     ebx, eax
0x18015f700  test    eax, eax
0x18015f702  jns     short loc_18015F72B
0x18015f704  mov     rcx, [rbp+5Fh]; this
0x18015f708  mov     r9d, eax; char *
0x18015f70b  lea     r8, aOnecoreAdminAp_90; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18015f712  mov     edx, 343h; void *
0x18015f717  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015f71c  nop
0x18015f71d  lea     rcx, [rbp+57h+hKey]
0x18015f721  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18015f726  jmp     loc_18015F44C
0x18015f72b  lea     rcx, [rbp+57h+hKey]
0x18015f72f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18015f734  cmp     [rsi+1B5h], r15b
0x18015f73b  jz      loc_18015F8C1
0x18015f741  lea     rdi, [rsi+88h]
0x18015f748  cmp     [rbp+57h+arg_0], r15b
0x18015f74c  jz      loc_18015F804
0x18015f752  xorps   xmm0, xmm0
0x18015f755  movups  [rbp+57h+var_70], xmm0
0x18015f759  mov     [rbp+57h+var_60], r15d
0x18015f75d  lea     rcx, [rsi+138h]; this
0x18015f764  lea     r8, [rbp+57h+var_70]; struct Common::COMMON_STRING *
0x18015f768  mov     rdx, rdi; struct Common::COMMON_STRING *
0x18015f76b  call    ?ConcatenatePaths@Tools@OSIntegration@@YAJPEBUCOMMON_STRING@Common@@0AEAVStringBuffer@4@@Z; OSIntegration::Tools::ConcatenatePaths(Common::COMMON_STRING const *,Common::COMMON_STRING const *,Common::StringBuffer &)
0x18015f770  mov     ebx, eax
0x18015f772  test    eax, eax
0x18015f774  jns     short loc_18015F77D
0x18015f776  mov     edx, 352h
0x18015f77b  jmp     short loc_18015F7D7
0x18015f77d  lea     r14, [rsi+198h]
0x18015f784  lea     r15, [rsi+180h]
0x18015f78b  lea     r12, [rsi+0F0h]
0x18015f792  lea     r13, [rsi+0D8h]
0x18015f799  lea     r8, [rsi+0C0h]
0x18015f7a0  mov     [rsp+0D0h+var_90], r14
0x18015f7a5  mov     [rsp+0D0h+var_98], r15
0x18015f7aa  mov     al, [rbp+57h+arg_10]
0x18015f7ad  mov     [rsp+0D0h+var_A0], al
0x18015f7b1  mov     eax, [rsi+1B0h]
0x18015f7b7  mov     [rsp+0D0h+var_A8], eax
0x18015f7bb  mov     qword ptr [rsp+0D0h+var_B0], r12; int
0x18015f7c0  mov     r9, r13
0x18015f7c3  lea     rdx, [rbp+57h+var_70]
0x18015f7c7  call    ?WriteAppExecAliasFile@AppExecutionAliasHelper@Internal@DEH@OSIntegration@@AEAAJAEBVStringBuffer@Common@@000W4AppExecutionAliasType@@_N00@Z; OSIntegration::DEH::Internal::AppExecutionAliasHelper::WriteAppExecAliasFile(Common::StringBuffer const &,Common::StringBuffer const &,Common::StringBuffer const &,Common::StringBuffer const &,AppExecutionAliasType,bool,Common::StringBuffer const &,Common::StringBuffer const &)
0x18015f7cc  mov     ebx, eax
0x18015f7ce  test    eax, eax
0x18015f7d0  jns     short loc_18015F7F9
0x18015f7d2  mov     edx, 355h; void *
0x18015f7d7  mov     r9d, eax; char *
0x18015f7da  lea     r8, aOnecoreAdminAp_90; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18015f7e1  mov     rcx, [rbp+5Fh]; this
0x18015f7e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015f7ea  nop
0x18015f7eb  lea     rcx, [rbp+57h+var_70]; this
0x18015f7ef  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18015f7f4  jmp     loc_18015F44C
0x18015f7f9  lea     rcx, [rbp+57h+var_70]; this
0x18015f7fd  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18015f802  jmp     short loc_18015F820
0x18015f804  lea     r14, [rsi+198h]
0x18015f80b  lea     r15, [rsi+180h]
0x18015f812  lea     r12, [rsi+0F0h]
0x18015f819  lea     r13, [rsi+0D8h]
0x18015f820  xor     eax, eax
0x18015f822  xorps   xmm0, xmm0
0x18015f825  movups  [rbp+57h+var_58], xmm0
0x18015f829  mov     [rbp+57h+var_48], eax
0x18015f82c  lea     rcx, [rsi+150h]; this
0x18015f833  lea     r8, [rbp+57h+var_58]; struct Common::COMMON_STRING *
0x18015f837  mov     rdx, rdi; struct Common::COMMON_STRING *
0x18015f83a  call    ?ConcatenatePaths@Tools@OSIntegration@@YAJPEBUCOMMON_STRING@Common@@0AEAVStringBuffer@4@@Z; OSIntegration::Tools::ConcatenatePaths(Common::COMMON_STRING const *,Common::COMMON_STRING const *,Common::StringBuffer &)
0x18015f83f  mov     ebx, eax
0x18015f841  test    eax, eax
0x18015f843  jns     short loc_18015F84C
0x18015f845  mov     edx, 359h
0x18015f84a  jmp     short loc_18015F863
0x18015f84c  mov     rcx, [rsi+158h]; this
0x18015f853  call    ?CreateDirectoryIfNecessary@Common@@YAJPEBG@Z; Common::CreateDirectoryIfNecessary(ushort const *)
0x18015f858  mov     ebx, eax
0x18015f85a  test    eax, eax
0x18015f85c  jns     short loc_18015F878
0x18015f85e  mov     edx, 35Bh; void *
0x18015f863  mov     rcx, [rbp+5Fh]; this
0x18015f867  mov     r9d, eax; char *
0x18015f86a  lea     r8, aOnecoreAdminAp_90; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18015f871  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
  ... truncated ...
```
