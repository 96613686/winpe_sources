# Common::RepairUserMutablePackage(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,void *,ushort const *)

- ea: `0x18006b848`
- end: `0x18006bd87`
- name: `?RepairUserMutablePackage@Common@@YAJPEBG0000PEAX0@Z`
- size: `1343`
- prototype: `int(Common *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, void *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180117ba0`

## callees

- `0x180005e08`
- `0x18000669c`
- `0x180012fc8`
- `0x18001adb4`
- `0x180069eb4`
- `0x18006b848`
- `0x18006bd90`
- `0x18006c314`
- `0x18006c574`
- `0x18006d6f8`
- `0x180074ef0`
- `0x1800aed10`
- `0x1800af1bc`
- `0x18011733c`
- `0x180117710`
- `0x18017f7e4`
- `0x180185cbc`
- `0x180188fa4`
- `0x18018a36c`
- `0x18018a560`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18006bc5a`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18006bc5a`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18006bc1d`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18006bc1d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18006bb3a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18006bb3a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x18006bae8`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x18006bae8`

## string_xrefs

- `0x18006b8bd`: `onecore\admin\appmodel\common\mutabledirectoryhelper.cpp`
- `0x18006b909`: `onecore\admin\appmodel\common\mutabledirectoryhelper.cpp`
- `0x18006b960`: `onecore\admin\appmodel\common\mutabledirectoryhelper.cpp`
- `0x18006b983`: `onecore\admin\appmodel\common\mutabledirectoryhelper.cpp`

## pseudocode

```c
__int64 __fastcall Common::RepairUserMutablePackage(
        Common *this,
        unsigned __int16 *a2,
        struct Common::StringBuffer *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *Sid,
        unsigned __int16 *a7)
{
  unsigned __int16 *v9; // r15
  char v10; // r14
  int UserMutablePath; // eax
  struct Common::StringBuffer *v12; // r8
  int v13; // ebx
  const struct std::nothrow_t *v14; // rdx
  int UserMutableBackupPath; // eax
  __int64 v17; // rax
  bool *v18; // r8
  __int64 v19; // rdx
  int v20; // eax
  bool *v21; // r8
  WCHAR *v22; // rbx
  int LayerIdFromScratchRoot; // esi
  struct _GUID *v24; // r8
  __int64 v25; // rdx
  const struct std::nothrow_t *v26; // rdx
  bool *v27; // r8
  int v28; // edx
  unsigned int v29; // eax
  unsigned int LastError; // eax
  unsigned int v31; // edi
  const struct std::nothrow_t *v32; // rdx
  const char *v33; // r9
  const unsigned __int16 *v34; // r9
  const char *v35; // r9
  int v36; // eax
  const struct std::nothrow_t *v37; // rdx
  WCHAR *v38; // rsi
  HRESULT v39; // r14d
  __int64 v40; // rdx
  const struct std::nothrow_t *v41; // rdx
  const struct std::nothrow_t *v42; // rdx
  const char *v43; // r9
  const struct std::nothrow_t *v44; // rdx
  const struct std::nothrow_t *v45; // rdx
  int v46; // eax
  __int64 v47; // rdx
  const struct std::nothrow_t *v48; // rdx
  unsigned __int16 *p_pguid; // [rsp+20h] [rbp-A1h]
  int v50; // [rsp+20h] [rbp-A1h]
  struct _GUID *v51; // [rsp+30h] [rbp-91h] BYREF
  LPCWSTR lpNewFileName[2]; // [rsp+38h] [rbp-89h] BYREF
  int v53; // [rsp+48h] [rbp-79h]
  unsigned __int16 *v54; // [rsp+50h] [rbp-71h] BYREF
  LPCWSTR lpExistingFileName[2]; // [rsp+58h] [rbp-69h] BYREF
  int v56; // [rsp+68h] [rbp-59h]
  _BYTE v57[32]; // [rsp+70h] [rbp-51h] BYREF
  unsigned __int16 *v58; // [rsp+90h] [rbp-31h]
  unsigned __int16 *v59; // [rsp+98h] [rbp-29h]
  _BYTE v60[24]; // [rsp+A0h] [rbp-21h] BYREF
  GUID pguid; // [rsp+B8h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+47h]
  const unsigned __int16 *v63; // [rsp+128h] [rbp+67h] BYREF

  v63 = a4;
  v54 = a2;
  v59 = a5;
  v9 = Sid;
  v58 = a7;
  v10 = 0;
  LOWORD(v51) = 0;
  *(_OWORD *)lpExistingFileName = 0;
  v56 = 0;
  UserMutablePath = StatePaths::GetUserMutablePath(this, (Common::StringBuffer *)lpExistingFileName, a3);
  v13 = UserMutablePath;
  if ( UserMutablePath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x706,
      (unsigned int)"onecore\\admin\\appmodel\\common\\mutabledirectoryhelper.cpp",
      (const char *)(unsigned int)UserMutablePath,
      (int)p_pguid);
LABEL_3:
    if ( lpExistingFileName[1] )
      operator delete((void *)lpExistingFileName[1], v14);
    return (unsigned int)v13;
  }
  *(_OWORD *)lpNewFileName = 0;
  v53 = 0;
  UserMutableBackupPath = Common::GetUserMutableBackupPath(this, (Common::StringBuffer *)lpNewFileName, v12);
  v13 = UserMutableBackupPath;
  if ( UserMutableBackupPath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x709,
      (unsigned int)"onecore\\admin\\appmodel\\common\\mutabledirectoryhelper.cpp",
      (const char *)(unsigned int)UserMutableBackupPath,
      (int)p_pguid);
    goto LABEL_8;
  }
  v17 = _lambda_454331550775a661471245d7d7e1e5b3_::_lambda_454331550775a661471245d7d7e1e5b3_(
          v60,
          lpNewFileName,
          &v54,
          &v63);
  wil::scope_exit__lambda_2cd8e12b7ad9e4bcf4ed46c08921b0d7___(v57, v17);
  v13 = Common::DirectoryExists(a3, (const unsigned __int16 *)&v51, v18);
  if ( v13 < 0 )
  {
    v19 = 1817;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecore\\admin\\appmodel\\common\\mutabledirectoryhelper.cpp",
      (const char *)(unsigned int)v13,
      (int)p_pguid);
    wil::details::lambda_call__lambda_2cd8e12b7ad9e4bcf4ed46c08921b0d7___::_lambda_call__lambda_2cd8e12b7ad9e4bcf4ed46c08921b0d7___(v57);
LABEL_8:
    if ( lpNewFileName[1] )
      operator delete((void *)lpNewFileName[1], v14);
    goto LABEL_3;
  }
  p_pguid = 0;
  v20 = Common::ConfigureFilterDriverForPerUserMutablePackage(a3, 0, v9, 3);
  if ( (_BYTE)v51 )
  {
    v13 = v20;
    if ( v20 < 0 )
    {
      v19 = 1821;
      goto LABEL_12;
    }
  }
  else if ( v20 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x721,
      (unsigned int)"onecore\\admin\\appmodel\\common\\mutabledirectoryhelper.cpp",
      (const char *)(unsigned int)v20,
      0);
  }
  v22 = (WCHAR *)lpExistingFileName[1];
  LayerIdFromScratchRoot = Common::DirectoryExists(
                             (Common *)lpExistingFileName[1],
                             (const unsigned __int16 *)((char *)&v51 + 1),
                             v21);
  if ( LayerIdFromScratchRoot < 0 )
  {
    v25 = 1828;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"onecore\\admin\\appmodel\\common\\mutabledirectoryhelper.cpp",
      (const char *)(unsigned int)LayerIdFromScratchRoot,
      (int)p_pguid);
LABEL_21:
    wil::details::lambda_call__lambda_2cd8e12b7ad9e4bcf4ed46c08921b0d7___::_lambda_call__lambda_2cd8e12b7ad9e4bcf4ed46c08921b0d7___(v57);
    if ( lpNewFileName[1] )
      operator delete((void *)lpNewFileName[1], v26);
    if ( v22 )
      operator delete(v22, v26);
    return (unsigned int)LayerIdFromScratchRoot;
  }
  if ( BYTE1(v51) )
  {
    p_pguid = 0;
    LayerIdFromScratchRoot = Common::ConfigureFilterDriverForPerUserMutablePackage(v22, v54, v9, 1);
    if ( LayerIdFromScratchRoot < 0 )
    {
      v25 = 1832;
      goto LABEL_20;
    }
    LOBYTE(v51) = 0;
    LayerIdFromScratchRoot = Common::DirectoryExists((Common *)lpNewFileName[1], (const unsigned __int16 *)&v51, v27);
    if ( LayerIdFromScratchRoot < 0 )
    {
      v25 = 1836;
      goto LABEL_20;
    }
    if ( (_BYTE)v51 )
    {
      v29 = RemoveDirectoryTree(lpNewFileName[1], v28, 0, 0, 0);
      if ( v29 )
      {
        LastError = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x730,
                      (unsigned int)"onecore\\admin\\appmodel\\common\\mutabledirectoryhelper.cpp",
                      (const char *)v29,
                      (unsigned int)p_pguid);
LABEL_34:
        v31 = LastError;
LABEL_35:
        wil::details::lambda_call__lambda_2cd8e12b7ad9e4bcf4ed46c08921b0d7___::_lambda_call__lambda_2cd8e12b7ad9e4bcf4ed46c08921b0d7___(v57);
        if ( lpNewFileName[1] )
          operator delete((void *)lpNewFileName[1], v32);
        if ( v22 )
          operator delete(v22, v32);
        return v31;
      }
    }
    if ( !MoveFileW(v22, lpNewFileName[1]) )
    {
      wil::details::in1diag3::Log_GetLastError(
        retaddr,
        (void *)0x736,
        (unsigned int)"onecore\\admin\\appmodel\\common\\mutabledirectoryhelper.cpp",
        v33);
      v10 = 1;
    }
  }
  pguid = 0;
  if ( !v10 )
  {
    if ( !CreateDirectoryW(v22, 0) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x743,
                    (unsigned int)"onecore\\admin\\appmodel\\common\\mutabledirectoryhelper.cpp",
                    v35);
      goto LABEL_34;
    }
    *(_OWORD *)lpExistingFileName = 0;
    v56 = 0;
    v36 = Common::SidHelper::ConvertSidToString(v9, (struct Common::StringBuffer *)lpExistingFileName);
    LayerIdFromScratchRoot = v36;
    if ( v36 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x745,
        (unsigned int)"onecore\\admin\\appmodel\\common\\mutabledirectoryhelper.cpp",
        (const char *)(unsigned int)v36,
        (int)p_pguid);
      if ( lpExistingFileName[1] )
        operator delete((void *)lpExistingFileName[1], v37);
      goto LABEL_21;
    }
    v38 = (WCHAR *)lpExistingFileName[1];
    v39 = DirectoryACLs::ApplyUserMutableDirectoryACLs((DirectoryACLs *)v22, v59, lpExistingFileName[1], v58, p_pguid);
    if ( v39 >= 0 )
    {
      if ( !SetFileAttributesW(v22, 0x80u) )
      {
        v31 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x747,
                (unsigned int)"onecore\\admin\\appmodel\\common\\mutabledirectoryhelper.cpp",
                v43);
        if ( v38 )
          operator delete(v38, v44);
        goto LABEL_35;
      }
      v39 = CoCreateGuid(&pguid);
      if ( v39 >= 0 )
      {
        if ( v38 )
          operator delete(v38, v45);
        goto LABEL_66;
      }
      v40 = 1864;
    }
    else
    {
      v40 = 1862;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v40,
      (unsigned int)"onecore\\admin\\appmodel\\common\\mutabledirectoryhelper.cpp",
      (const char *)(unsigned int)v39,
      (int)p_pguid);
    if ( v38 )
      operator delete(v38, v41);
    wil::details::lambda_call__lambda_2cd8e12b7ad9e4bcf4ed46c08921b0d7___::_lambda_call__lambda_2cd8e12b7ad9e4bcf4ed46c08921b0d7___(v57);
    if ( lpNewFileName[1] )
      operator delete((void *)lpNewFileName[1], v42);
    if ( v22 )
      operator delete(v22, v42);
    return (unsigned int)v39;
  }
  LayerIdFromScratchRoot = Common::GetLayerIdFromScratchRoot((Common *)v22, (const unsigned __int16 *)&pguid, v24);
  if ( LayerIdFromScratchRoot < 0 )
  {
    v25 = 1854;
    goto LABEL_20;
  }
LABEL_66:
  if ( BYTE1(v51) )
  {
    LOBYTE(v34) = 1;
    v46 = Common::RestoreFilesToMutableDirectory(
            (Common *)lpNewFileName[1],
            v22,
            v54,
            v34,
            (bool)p_pguid,
            (bool)&pguid,
            v51);
    if ( v46 < 0 )
    {
      v47 = 1870;
LABEL_71:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v47,
        (unsigned int)"onecore\\admin\\appmodel\\common\\mutabledirectoryhelper.cpp",
        (const char *)(unsigned int)v46,
        v50);
    }
  }
  else
  {
    v50 = 0;
    v46 = Common::ConfigureFilterDriverForPerUserMutablePackage(v22, v54, v9, 1);
    if ( v46 < 0 )
    {
      v47 = 1876;
      goto LABEL_71;
    }
  }
  p_pguid = (unsigned __int16 *)&pguid;
  LayerIdFromScratchRoot = Common::ConfigureFilterDriverForPerUserMutablePackage(v22, v54, v9, 0);
  if ( LayerIdFromScratchRoot < 0 )
  {
    v25 = 1879;
    goto LABEL_20;
  }
  LODWORD(p_pguid) = 0;
  LayerIdFromScratchRoot = Common::ConfigureFilterDriverForPerUserMutablePackage(a3, v22, v9, 2);
  if ( LayerIdFromScratchRoot < 0 )
  {
    v25 = 1880;
    goto LABEL_20;
  }
  wil::details::lambda_call__lambda_2cd8e12b7ad9e4bcf4ed46c08921b0d7___::_lambda_call__lambda_2cd8e12b7ad9e4bcf4ed46c08921b0d7___(v57);
  if ( lpNewFileName[1] )
    operator delete((void *)lpNewFileName[1], v48);
  if ( v22 )
    operator delete(v22, v48);
  return 0;
}

```

## disassembly

```asm
0x18006b848  mov     [rsp-8+arg_18], r9
0x18006b84d  push    rbp
0x18006b84e  push    rbx
0x18006b84f  push    rsi
0x18006b850  push    rdi
0x18006b851  push    r13
0x18006b853  push    r14
0x18006b855  push    r15
0x18006b857  lea     rbp, [rsp-0Fh]
0x18006b85c  sub     rsp, 0D0h
0x18006b863  mov     rax, cs:__security_cookie
0x18006b86a  xor     rax, rsp
0x18006b86d  mov     [rbp+3Fh+var_38], rax
0x18006b871  mov     r13, r8
0x18006b874  mov     rdi, rcx
0x18006b877  mov     [rbp+3Fh+var_B0], rdx
0x18006b87b  mov     rax, [rbp+3Fh+arg_20]
0x18006b87f  mov     [rbp+3Fh+var_68], rax
0x18006b883  mov     r15, [rbp+3Fh+Sid]
0x18006b887  mov     rax, [rbp+3Fh+arg_30]
0x18006b88b  mov     [rbp+3Fh+var_70], rax
0x18006b88f  xor     r14d, r14d
0x18006b892  mov     byte ptr [rsp+100h+var_D0], r14b
0x18006b897  mov     byte ptr [rsp+100h+var_D0+1], r14b
0x18006b89c  xorps   xmm0, xmm0
0x18006b89f  movups  xmmword ptr [rbp+3Fh+lpExistingFileName], xmm0
0x18006b8a3  mov     [rbp+3Fh+var_98], r14d
0x18006b8a7  lea     rdx, [rbp+3Fh+lpExistingFileName]; Common::StringBuffer *
0x18006b8ab  call    ?GetUserMutablePath@StatePaths@@YAJPEBGAEAVStringBuffer@Common@@@Z; StatePaths::GetUserMutablePath(ushort const *,Common::StringBuffer &)
0x18006b8b0  mov     ebx, eax
0x18006b8b2  test    eax, eax
0x18006b8b4  jns     short loc_18006B8E3
0x18006b8b6  mov     rcx, [rbp+47h]; this
0x18006b8ba  mov     r9d, eax; char *
0x18006b8bd  lea     r8, aOnecoreAdminAp_117; "onecore\\admin\\appmodel\\common\\mutab"...
0x18006b8c4  mov     edx, 706h; void *
0x18006b8c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006b8ce  mov     rcx, [rbp+3Fh+lpExistingFileName+8]; void *
0x18006b8d2  test    rcx, rcx
0x18006b8d5  jz      short loc_18006B8DC
0x18006b8d7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006b8dc  mov     eax, ebx
0x18006b8de  jmp     loc_18006BD68
0x18006b8e3  xorps   xmm0, xmm0
0x18006b8e6  movups  xmmword ptr [rsp+100h+lpNewFileName], xmm0
0x18006b8eb  mov     [rbp+3Fh+var_B8], r14d
0x18006b8ef  lea     rdx, [rsp+100h+lpNewFileName]; Common::StringBuffer *
0x18006b8f4  mov     rcx, rdi; this
0x18006b8f7  call    ?GetUserMutableBackupPath@Common@@YAJPEBGAEAVStringBuffer@1@@Z; Common::GetUserMutableBackupPath(ushort const *,Common::StringBuffer &)
0x18006b8fc  mov     ebx, eax
0x18006b8fe  test    eax, eax
0x18006b900  jns     short loc_18006B92B
0x18006b902  mov     rcx, [rbp+47h]; this
0x18006b906  mov     r9d, eax; char *
0x18006b909  lea     r8, aOnecoreAdminAp_117; "onecore\\admin\\appmodel\\common\\mutab"...
0x18006b910  mov     edx, 709h; void *
0x18006b915  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006b91a  mov     rcx, [rsp+100h+lpNewFileName+8]; void *
0x18006b91f  test    rcx, rcx
0x18006b922  jz      short loc_18006B8CE
0x18006b924  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006b929  jmp     short loc_18006B8CE
0x18006b92b  lea     r9, [rbp+3Fh+arg_18]
0x18006b92f  lea     r8, [rbp+3Fh+var_B0]
0x18006b933  lea     rdx, [rsp+100h+lpNewFileName]
0x18006b938  lea     rcx, [rbp+3Fh+var_60]
0x18006b93c  call    ??0_lambda_454331550775a661471245d7d7e1e5b3_@@QEAA@AEAPEAV?$Array@VContentTypeHelper@Internal@DEH@OSIntegration@@V?$ContainerOperations@VContentTypeHelper@Internal@DEH@OSIntegration@@V1234@@Common@@VNoKey@6@V?$ContainerOperations@VNoKey@Common@@VContentTypeHelper@Internal@DEH@OSIntegration@@@6@V?$ArrayOperations@VContentTypeHelper@Internal@DEH@OSIntegration@@VNoKey@Common@@@6@@Common@@0PEAV?$BaseLastOrFirstWriterWinsHandler@VContentTypeHandler@DEH@OSIntegration@@VContentTypeHelper@Internal@23@$0A@@Internal@DEH@OSIntegration@@@Z; _lambda_454331550775a661471245d7d7e1e5b3_::_lambda_454331550775a661471245d7d7e1e5b3_(Common::Array<OSIntegration::DEH::Internal::ContentTypeHelper,Common::ContainerOperations<OSIntegration::DEH::Internal::ContentTypeHelper,OSIntegration::DEH::Internal::ContentTypeHelper>,Common::NoKey,Common::ContainerOperations<Common::NoKey,OSIntegration::DEH::Internal::ContentTypeHelper>,Common::ArrayOperations<OSIntegration::DEH::Internal::ContentTypeHelper,Common::NoKey>> * &,Common::Array<OSIntegration::DEH::Internal::ContentTypeHelper,Common::ContainerOperations<OSIntegration::DEH::Internal::ContentTypeHelper,OSIntegration::DEH::Internal::ContentTypeHelper>,Common::NoKey,Common::ContainerOperations<Common::NoKey,OSIntegration::DEH::Internal::ContentTypeHelper>,Common::ArrayOperations<OSIntegration::DEH::Internal::ContentTypeHelper,Common::NoKey>> * &,OSIntegration::DEH::Internal::BaseLastOrFirstWriterWinsHandler<OSIntegration::DEH::ContentTypeHandler,OSIntegration::DEH::Internal::ContentTypeHelper,0> *)
0x18006b941  mov     rdx, rax
0x18006b944  lea     rcx, [rbp+3Fh+var_90]
0x18006b948  call    wil__scope_exit__lambda_2cd8e12b7ad9e4bcf4ed46c08921b0d7___
0x18006b94d  lea     rdx, [rsp+100h+var_D0]; unsigned __int16 *
0x18006b952  mov     rcx, r13; this
0x18006b955  call    ?DirectoryExists@Common@@YAJPEBGPEA_N@Z; Common::DirectoryExists(ushort const *,bool *)
0x18006b95a  mov     ebx, eax
0x18006b95c  test    eax, eax
0x18006b95e  jns     short loc_18006B983
0x18006b960  lea     r8, aOnecoreAdminAp_117; "onecore\\admin\\appmodel\\common\\mutab"...
0x18006b967  mov     edx, 719h; void *
0x18006b96c  mov     r9d, ebx; char *
0x18006b96f  mov     rcx, [rbp+47h]; this
0x18006b973  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006b978  lea     rcx, [rbp+3Fh+var_90]
0x18006b97c  call    wil__details__lambda_call__lambda_2cd8e12b7ad9e4bcf4ed46c08921b0d7______lambda_call__lambda_2cd8e12b7ad9e4bcf4ed46c08921b0d7___
0x18006b981  jmp     short loc_18006B91A
0x18006b983  lea     rdi, aOnecoreAdminAp_117; "onecore\\admin\\appmodel\\common\\mutab"...
0x18006b98a  mov     [rsp+100h+var_E0], r14; int
0x18006b98f  mov     r9d, 3
0x18006b995  mov     r8, r15
0x18006b998  xor     edx, edx
0x18006b99a  mov     rcx, r13
0x18006b99d  call    ?ConfigureFilterDriverForPerUserMutablePackage@Common@@YAJPEBG0PEAXW4UserFilterDriverCommand@1@PEAU_GUID@@@Z; Common::ConfigureFilterDriverForPerUserMutablePackage(ushort const *,ushort const *,void *,Common::UserFilterDriverCommand,_GUID *)
0x18006b9a2  cmp     byte ptr [rsp+100h+var_D0], r14b
0x18006b9a7  jz      short loc_18006B9B9
0x18006b9a9  mov     ebx, eax
0x18006b9ab  test    eax, eax
0x18006b9ad  jns     short loc_18006B9D1
0x18006b9af  mov     r8, rdi
0x18006b9b2  mov     edx, 71Dh
0x18006b9b7  jmp     short loc_18006B96C
0x18006b9b9  test    eax, eax
0x18006b9bb  jns     short loc_18006B9D1
0x18006b9bd  mov     rcx, [rbp+47h]; this
0x18006b9c1  mov     r9d, eax; char *
0x18006b9c4  mov     r8, rdi; unsigned int
0x18006b9c7  mov     edx, 721h; void *
0x18006b9cc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006b9d1  mov     rbx, [rbp+3Fh+lpExistingFileName+8]
0x18006b9d5  lea     rdx, [rsp+100h+var_D0+1]; unsigned __int16 *
0x18006b9da  mov     rcx, rbx; this
0x18006b9dd  call    ?DirectoryExists@Common@@YAJPEBGPEA_N@Z; Common::DirectoryExists(ushort const *,bool *)
0x18006b9e2  mov     esi, eax
0x18006b9e4  test    eax, eax
0x18006b9e6  jns     short loc_18006BA28
0x18006b9e8  mov     edx, 724h; void *
0x18006b9ed  mov     rcx, [rbp+47h]; this
0x18006b9f1  mov     r9d, esi; char *
0x18006b9f4  mov     r8, rdi; unsigned int
0x18006b9f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006b9fc  lea     rcx, [rbp+3Fh+var_90]
0x18006ba00  call    wil__details__lambda_call__lambda_2cd8e12b7ad9e4bcf4ed46c08921b0d7______lambda_call__lambda_2cd8e12b7ad9e4bcf4ed46c08921b0d7___
0x18006ba05  mov     rcx, [rsp+100h+lpNewFileName+8]; void *
0x18006ba0a  test    rcx, rcx
0x18006ba0d  jz      short loc_18006BA14
0x18006ba0f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006ba14  test    rbx, rbx
0x18006ba17  jz      short loc_18006BA21
0x18006ba19  mov     rcx, rbx; void *
0x18006ba1c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006ba21  mov     eax, esi
0x18006ba23  jmp     loc_18006BD68
0x18006ba28  cmp     byte ptr [rsp+100h+var_D0+1], r14b
0x18006ba2d  jz      loc_18006BB0C
0x18006ba33  mov     [rsp+100h+var_E0], r14; bool
0x18006ba38  mov     r9d, 1
0x18006ba3e  mov     r8, r15
0x18006ba41  mov     rdx, [rbp+3Fh+var_B0]
0x18006ba45  mov     rcx, rbx
0x18006ba48  call    ?ConfigureFilterDriverForPerUserMutablePackage@Common@@YAJPEBG0PEAXW4UserFilterDriverCommand@1@PEAU_GUID@@@Z; Common::ConfigureFilterDriverForPerUserMutablePackage(ushort const *,ushort const *,void *,Common::UserFilterDriverCommand,_GUID *)
0x18006ba4d  mov     esi, eax
0x18006ba4f  test    eax, eax
0x18006ba51  jns     short loc_18006BA5A
0x18006ba53  mov     edx, 728h
0x18006ba58  jmp     short loc_18006B9ED
0x18006ba5a  mov     byte ptr [rsp+100h+var_D0], r14b; struct _GUID *
0x18006ba5f  lea     rdx, [rsp+100h+var_D0]; unsigned __int16 *
0x18006ba64  mov     rcx, [rsp+100h+lpNewFileName+8]; this
0x18006ba69  call    ?DirectoryExists@Common@@YAJPEBGPEA_N@Z; Common::DirectoryExists(ushort const *,bool *)
0x18006ba6e  mov     esi, eax
0x18006ba70  test    eax, eax
0x18006ba72  jns     short loc_18006BA7E
0x18006ba74  mov     edx, 72Ch
0x18006ba79  jmp     loc_18006B9ED
0x18006ba7e  cmp     byte ptr [rsp+100h+var_D0], r14b
0x18006ba83  jz      short loc_18006BAE0
0x18006ba85  mov     [rsp+100h+var_E0], r14; unsigned int
0x18006ba8a  xor     r9d, r9d
0x18006ba8d  xor     r8d, r8d
0x18006ba90  mov     rcx, [rsp+100h+lpNewFileName+8]
0x18006ba95  call    RemoveDirectoryTree
0x18006ba9a  test    eax, eax
0x18006ba9c  jz      short loc_18006BAE0
0x18006ba9e  mov     rcx, [rbp+47h]; this
0x18006baa2  mov     r9d, eax; char *
0x18006baa5  mov     r8, rdi; unsigned int
0x18006baa8  mov     edx, 730h; void *
0x18006baad  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18006bab2  mov     edi, eax
0x18006bab4  lea     rcx, [rbp+3Fh+var_90]
0x18006bab8  call    wil__details__lambda_call__lambda_2cd8e12b7ad9e4bcf4ed46c08921b0d7______lambda_call__lambda_2cd8e12b7ad9e4bcf4ed46c08921b0d7___
0x18006babd  mov     rcx, [rsp+100h+lpNewFileName+8]; void *
0x18006bac2  test    rcx, rcx
0x18006bac5  jz      short loc_18006BACC
0x18006bac7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006bacc  test    rbx, rbx
0x18006bacf  jz      short loc_18006BAD9
0x18006bad1  mov     rcx, rbx; void *
0x18006bad4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006bad9  mov     eax, edi
0x18006badb  jmp     loc_18006BD68
0x18006bae0  mov     rdx, [rsp+100h+lpNewFileName+8]; lpNewFileName
0x18006bae5  mov     rcx, rbx; lpExistingFileName
0x18006bae8  call    cs:__imp_MoveFileW
0x18006baef  nop     dword ptr [rax+rax+00h]
0x18006baf4  test    eax, eax
0x18006baf6  jnz     short loc_18006BB0C
0x18006baf8  mov     rcx, [rbp+47h]; this
0x18006bafc  mov     r8, rdi; unsigned int
0x18006baff  mov     edx, 736h; void *
0x18006bb04  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x18006bb09  mov     r14b, 1
0x18006bb0c  xorps   xmm0, xmm0
0x18006bb0f  movups  xmmword ptr [rbp+3Fh+pguid.Data1], xmm0
0x18006bb13  mov     rcx, rbx; this
0x18006bb16  test    r14b, r14b
0x18006bb19  jz      short loc_18006BB38
0x18006bb1b  lea     rdx, [rbp+3Fh+pguid]; unsigned __int16 *
0x18006bb1f  call    ?GetLayerIdFromScratchRoot@Common@@YAJPEBGAEAU_GUID@@@Z; Common::GetLayerIdFromScratchRoot(ushort const *,_GUID &)
0x18006bb24  mov     esi, eax
0x18006bb26  test    eax, eax
0x18006bb28  jns     loc_18006BC84
0x18006bb2e  mov     edx, 73Eh
0x18006bb33  jmp     loc_18006B9ED
0x18006bb38  xor     edx, edx; lpSecurityAttributes
0x18006bb3a  call    cs:__imp_CreateDirectoryW
0x18006bb41  nop     dword ptr [rax+rax+00h]
0x18006bb46  test    eax, eax
0x18006bb48  jnz     short loc_18006BB60
0x18006bb4a  mov     rcx, [rbp+47h]; this
0x18006bb4e  mov     r8, rdi; unsigned int
0x18006bb51  mov     edx, 743h; void *
0x18006bb56  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18006bb5b  jmp     loc_18006BAB2
0x18006bb60  xor     eax, eax
0x18006bb62  xorps   xmm0, xmm0
0x18006bb65  movups  xmmword ptr [rbp+3Fh+lpExistingFileName], xmm0
0x18006bb69  mov     [rbp+3Fh+var_98], eax
0x18006bb6c  lea     rdx, [rbp+3Fh+lpExistingFileName]; struct Common::StringBuffer *
0x18006bb70  mov     rcx, r15; Sid
0x18006bb73  call    ?ConvertSidToString@SidHelper@Common@@SAJQEAXPEAVStringBuffer@2@@Z; Common::SidHelper::ConvertSidToString(void * const,Common::StringBuffer *)
0x18006bb78  mov     esi, eax
0x18006bb7a  test    eax, eax
0x18006bb7c  jns     short loc_18006BBA9
0x18006bb7e  mov     rcx, [rbp+47h]; this
0x18006bb82  mov     r9d, eax; char *
0x18006bb85  mov     r8, rdi; unsigned int
0x18006bb88  mov     edx, 745h; void *
0x18006bb8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006bb92  mov     rcx, [rbp+3Fh+lpExistingFileName+8]; void *
0x18006bb96  test    rcx, rcx
0x18006bb99  jz      loc_18006B9FC
0x18006bb9f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006bba4  jmp     loc_18006B9FC
0x18006bba9  mov     rsi, [rbp+3Fh+lpExistingFileName+8]
0x18006bbad  mov     r9, [rbp+3Fh+var_70]; unsigned __int16 *
0x18006bbb1  mov     r8, rsi; unsigned __int16 *
0x18006bbb4  mov     rdx, [rbp+3Fh+var_68]; unsigned __int16 *
0x18006bbb8  mov     rcx, rbx; this
0x18006bbbb  call    ?ApplyUserMutableDirectoryACLs@DirectoryACLs@@YAJPEBG000@Z; DirectoryACLs::ApplyUserMutableDirectoryACLs(ushort const *,ushort const *,ushort const *,ushort const *)
0x18006bbc0  mov     r14d, eax
0x18006bbc3  test    eax, eax
0x18006bbc5  jns     short loc_18006BC15
0x18006bbc7  mov     edx, 746h; void *
0x18006bbcc  mov     r9d, r14d; char *
0x18006bbcf  mov     r8, rdi; unsigned int
0x18006bbd2  mov     rcx, [rbp+47h]; this
0x18006bbd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006bbdb  test    rsi, rsi
0x18006bbde  jz      short loc_18006BBE8
0x18006bbe0  mov     rcx, rsi; void *
0x18006bbe3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006bbe8  lea     rcx, [rbp+3Fh+var_90]
0x18006bbec  call    wil__details__lambda_call__lambda_2cd8e12b7ad9e4bcf4ed46c08921b0d7______lambda_call__lambda_2cd8e12b7ad9e4bcf4ed46c08921b0d7___
0x18006bbf1  mov     rcx, [rsp+100h+lpNewFileName+8]; void *
0x18006bbf6  test    rcx, rcx
0x18006bbf9  jz      short loc_18006BC00
0x18006bbfb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006bc00  test    rbx, rbx
0x18006bc03  jz      short loc_18006BC0D
0x18006bc05  mov     rcx, rbx; void *
0x18006bc08  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006bc0d  mov     eax, r14d
0x18006bc10  jmp     loc_18006BD68
0x18006bc15  mov     edx, 80h; dwFileAttributes
0x18006bc1a  mov     rcx, rbx; lpFileName
0x18006bc1d  call    cs:__imp_SetFileAttributesW
0x18006bc24  nop     dword ptr [rax+rax+00h]
0x18006bc29  test    eax, eax
0x18006bc2b  jnz     short loc_18006BC56
0x18006bc2d  mov     rcx, [rbp+47h]; this
0x18006bc31  mov     r8, rdi; unsigned int
0x18006bc34  mov     edx, 747h; void *
0x18006bc39  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18006bc3e  mov     edi, eax
0x18006bc40  test    rsi, rsi
0x18006bc43  jz      loc_18006BAB4
0x18006bc49  mov     rcx, rsi; void *
0x18006bc4c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006bc51  jmp     loc_18006BAB4
0x18006bc56  lea     rcx, [rbp+3Fh+pguid]; pguid
0x18006bc5a  call    cs:__imp_CoCreateGuid
0x18006bc61  nop     dword ptr [rax+rax+00h]
0x18006bc66  mov     r14d, eax
0x18006bc69  test    eax, eax
0x18006bc6b  jns     short loc_18006BC77
0x18006bc6d  mov     edx, 748h
0x18006bc72  jmp     loc_18006BBCC
0x18006bc77  test    rsi, rsi
0x18006bc7a  jz      short loc_18006BC84
0x18006bc7c  mov     rcx, rsi; void *
0x18006bc7f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006bc84  cmp     byte ptr [rsp+100h+var_D0+1], 0
0x18006bc89  jz      short loc_18006BCB3
0x18006bc8b  lea     rax, [rbp+3Fh+pguid]
0x18006bc8f  mov     qword ptr [rsp+100h+var_D8], rax; bool
0x18006bc94  mov     r9b, 1; unsigned __int16 *
0x18006bc97  mov     r8, [rbp+3Fh+var_B0]; unsigned __int16 *
0x18006bc9b  mov     rdx, rbx; unsigned __int16 *
0x18006bc9e  mov     rcx, [rsp+100h+lpNewFileName+8]; this
0x18006bca3  call    ?RestoreFilesToMutableDirectory@Common@@YAJPEBG00_N1AEBU_GUID@@@Z; Common::RestoreFilesToMutableDirectory(ushort const *,ushort const *,ushort const *,bool,bool,_GUID const &)
0x18006bca8  test    eax, eax
  ... truncated ...
```
