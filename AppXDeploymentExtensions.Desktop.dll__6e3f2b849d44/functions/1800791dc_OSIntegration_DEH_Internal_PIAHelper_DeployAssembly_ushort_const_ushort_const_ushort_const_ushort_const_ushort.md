# OSIntegration::DEH::Internal::PIAHelper::DeployAssembly(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x1800791dc`
- end: `0x18007967d`
- name: `?DeployAssembly@PIAHelper@Internal@DEH@OSIntegration@@AEAAJPEBG0000@Z`
- size: `1185`
- prototype: `__int64 __fastcall(OSIntegration::DEH::Internal::PIAHelper *this, const unsigned __int16 *, bool *, Common *, Common *lpNewFileName, const unsigned __int16 *lpExistingFileName)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180078df0`

## callees

- `0x18000669c`
- `0x180012fc8`
- `0x180015590`
- `0x18001adb4`
- `0x18003f888`
- `0x180050884`
- `0x1800546d8`
- `0x180055418`
- `0x180069eb4`
- `0x180074248`
- `0x1800791dc`
- `0x180099b44`
- `0x1800aa820`
- `0x1800aed10`
- `0x1800af1bc`
- `0x1800af6f8`
- `0x1800d6fe0`
- `0x1800e5b78`
- `0x1800e5e28`
- `0x180184c80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800793b7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800793b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800793f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800793f0`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x1800793dc`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x1800793dc`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x180079631`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x180079631`

## string_xrefs

- `0x180079566`: `Deletefile Failed with 0x%X`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OSIntegration::DEH::Internal::PIAHelper::DeployAssembly(
        OSIntegration::DEH::Internal::PIAHelper *this,
        const unsigned __int16 *a2,
        bool *a3,
        Common *a4,
        Common *lpNewFileName,
        const unsigned __int16 *lpExistingFileName)
{
  int DirectoryTree; // ebx
  __int64 v10; // rdx
  bool PackageVersionFromGACHardLink; // al
  bool *v13; // r8
  UINT64 Version; // rbx
  __int64 v15; // rax
  int v16; // ecx
  __int64 v17; // rdx
  const unsigned __int16 *v18; // rdx
  enum _SE_OBJECT_TYPE v19; // r8d
  DWORD LastError; // r13d
  __int64 v21; // rcx
  __int64 v22; // rax
  unsigned __int64 v23; // rbx
  unsigned __int16 *v24; // r14
  int v25; // eax
  const struct std::nothrow_t *v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // rcx
  const struct std::nothrow_t *v29; // rdx
  int v30; // eax
  int v31; // eax
  unsigned int v32; // r14d
  __int64 v33; // rdx
  __int64 v34; // rcx
  const char *v35; // r9
  unsigned int pbCancel; // [rsp+20h] [rbp-E0h]
  int pbCancela; // [rsp+20h] [rbp-E0h]
  unsigned __int16 v38; // [rsp+40h] [rbp-C0h] BYREF
  struct PACKAGE_VERSION v39; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v40; // [rsp+50h] [rbp-B0h] BYREF
  UINT64 v41; // [rsp+58h] [rbp-A8h] BYREF
  int v42[2]; // [rsp+60h] [rbp-A0h]
  bool *v43; // [rsp+68h] [rbp-98h]
  unsigned __int16 v44[256]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  v43 = a3;
  *(_QWORD *)v42 = lpExistingFileName;
  LOBYTE(v38) = 0;
  DirectoryTree = Common::FileExists(a4, &v38, a3);
  if ( DirectoryTree < 0 )
  {
    v10 = 490;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\pia\\piahelper.cpp",
      (const char *)(unsigned int)DirectoryTree,
      pbCancel);
    return (unsigned int)DirectoryTree;
  }
  if ( (_BYTE)v38 )
  {
    v39.Version = 0;
    PackageVersionFromGACHardLink = OSIntegration::DEH::Internal::PIAHelper::GetPackageVersionFromGACHardLink(
                                      this,
                                      (const unsigned __int16 *)a4,
                                      &v39);
    Version = v39.Version;
    if ( PackageVersionFromGACHardLink )
    {
      v15 = *((_QWORD *)this + 3);
      if ( *(_QWORD *)(v15 + 464) == v39.Version && !*(_BYTE *)(v15 + 403) )
      {
        LOBYTE(v13) = 1;
        DirectoryTree = OSIntegration::DEH::Internal::PIAHelper::AddCurrentUserToACL(this, lpNewFileName, v13);
        if ( DirectoryTree < 0 )
        {
          v10 = 503;
          goto LABEL_3;
        }
        return 0;
      }
    }
    if ( v39.Version > *(_QWORD *)(*((_QWORD *)this + 3) + 464LL) )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x209,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\pia\\piahelper.cpp",
        (const char *)0x80004005LL,
        pbCancel);
      if ( (byte_18024560A & 0x20) != 0 )
        McTemplateU0zxx_EventWriteTransfer(
          v16,
          (unsigned int)&PIADEHVersionDowngrade,
          *(_QWORD *)(*((_QWORD *)this + 3) + 224LL),
          Version,
          *(_QWORD *)(*((_QWORD *)this + 3) + 464LL));
      v17 = *((_QWORD *)this + 3);
      v39.Version = *(_QWORD *)(v17 + 464);
      v41 = Version;
      v40 = *(unsigned __int16 **)(v17 + 224);
      SetAppXErrorFromLogMessage(
        -2147467259,
        &APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID,
        &PIADEHVersionDowngrade,
        3u,
        &v40,
        &v41,
        &v39);
    }
  }
  if ( !*(_BYTE *)(*((_QWORD *)this + 3) + 403LL) )
    return 0;
  DirectoryTree = CreateDirectoryTree(a2);
  if ( DirectoryTree < 0 )
  {
    v10 = 532;
    goto LABEL_3;
  }
  SetLastError(0);
  if ( !CopyFileExW(lpExistingFileName, (LPCWSTR)lpNewFileName, 0, 0, 0, 8u) )
  {
    LastError = GetLastError();
    v21 = -1;
    do
      ++v21;
    while ( *((_WORD *)lpNewFileName + v21) );
    v22 = -1;
    do
      ++v22;
    while ( lpExistingFileName[v22] );
    v23 = v21 + v22 + 32;
    v24 = (unsigned __int16 *)operator new[](saturated_mul(v23, 2u));
    v40 = v24;
    pbCancela = v42[0];
    v25 = StringCchPrintfW(v24, v23, L"LastError=%d, source=%s, dest=%s", LastError);
    DirectoryTree = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x223,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\pia\\piahelper.cpp",
        (const char *)(unsigned int)v25,
        pbCancela);
LABEL_29:
      operator delete(v24, v26);
      return (unsigned int)DirectoryTree;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x229,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\pia\\piahelper.cpp",
      (const char *)0x8000FFFFLL,
      pbCancela);
    if ( (byte_18024560A & 0x10) != 0 )
      McTemplateU0zz_EventWriteTransfer(v28, PIACopyFileFailure, *(_QWORD *)(*((_QWORD *)this + 3) + 224LL), v24);
    details::appxLog<unsigned short *,unsigned short *>(
      2147549183LL,
      v27,
      PIACopyFileFailure,
      *(_QWORD *)(*((_QWORD *)this + 3) + 224LL),
      (_DWORD)v24);
    if ( LastError )
    {
      DirectoryTree = wil::details::in1diag3::Return_Win32(
                        retaddr,
                        (void *)0x22A,
                        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\pia\\piahelper.cpp",
                        (const char *)LastError,
                        pbCancel);
      goto LABEL_29;
    }
    operator delete(v24, v29);
  }
  DirectoryTree = OSIntegration::DEH::Internal::SetInitialDACL((WCHAR *)lpNewFileName, v18, v19);
  if ( DirectoryTree < 0 )
  {
    v10 = 556;
    goto LABEL_3;
  }
  DirectoryTree = CreateDirectoryTree(v43);
  if ( DirectoryTree < 0 )
  {
    v10 = 559;
    goto LABEL_3;
  }
  if ( !(_BYTE)v38 || (v30 = AppXDeleteHardlinkSafely((LPCWSTR)a4), DirectoryTree = v30, v30 >= 0) )
  {
    if ( !CreateHardLinkW((LPCWSTR)a4, (LPCWSTR)lpNewFileName, 0) )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x249,
               (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\pia\\piahelper.cpp",
               v35);
    return 0;
  }
  v31 = StringCchPrintfW(v44, 0x100u, L"Deletefile Failed with 0x%X", (unsigned int)v30);
  v32 = v31;
  if ( v31 >= 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x23E,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\pia\\piahelper.cpp",
      (const char *)0x8000FFFFLL,
      pbCancel);
    if ( (byte_18024560A & 0x20) != 0 )
      McTemplateU0zz_EventWriteTransfer(v34, PIADEHPreexistingAssembly, *(_QWORD *)(*((_QWORD *)this + 3) + 224LL), v44);
    details::appxLog<unsigned short *,unsigned short *>(
      2147549183LL,
      v33,
      PIADEHPreexistingAssembly,
      *(_QWORD *)(*((_QWORD *)this + 3) + 224LL),
      (unsigned int)v44);
    if ( DirectoryTree == -2147024864 || DirectoryTree == -2147024891 )
      Common::Deployment::LogFileInUse<DesktopAppXProvider::FileInUse>((LPCWSTR)a4);
    return (unsigned int)DirectoryTree;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x238,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\pia\\piahelper.cpp",
    (const char *)(unsigned int)v31,
    pbCancel);
  return v32;
}

```

## disassembly

```asm
0x1800791dc  push    rbp
0x1800791de  push    rbx
0x1800791df  push    rsi
0x1800791e0  push    rdi
0x1800791e1  push    r12
0x1800791e3  push    r13
0x1800791e5  push    r14
0x1800791e7  push    r15
0x1800791e9  lea     rbp, [rsp-188h]
0x1800791f1  sub     rsp, 288h
0x1800791f8  mov     rax, cs:__security_cookie
0x1800791ff  xor     rax, rsp
0x180079202  mov     [rbp+1C0h+var_50], rax
0x180079209  mov     r12, r9
0x18007920c  mov     [rsp+2C0h+var_258], r8
0x180079211  mov     r13, rdx
0x180079214  mov     rsi, rcx
0x180079217  mov     r15, [rbp+1C0h+lpNewFileName]
0x18007921e  mov     r14, [rbp+1C0h+lpExistingFileName]
0x180079225  mov     qword ptr [rsp+2C0h+var_260], r14
0x18007922a  xor     edi, edi
0x18007922c  mov     byte ptr [rsp+2C0h+var_280], dil
0x180079231  lea     rdx, [rsp+2C0h+var_280]; unsigned __int16 *
0x180079236  mov     rcx, r9; this
0x180079239  call    ?FileExists@Common@@YAJPEBGPEA_N@Z; Common::FileExists(ushort const *,bool *)
0x18007923e  mov     ebx, eax
0x180079240  test    eax, eax
0x180079242  jns     short loc_180079266
0x180079244  lea     r8, aOnecoreAdminAp_29; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18007924b  mov     edx, 1EAh; void *
0x180079250  mov     rcx, [rbp+1C8h]; this
0x180079257  mov     r9d, ebx; char *
0x18007925a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007925f  mov     eax, ebx
0x180079261  jmp     loc_180079659
0x180079266  lea     rdi, aOnecoreAdminAp_29; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18007926d  xor     eax, eax
0x18007926f  cmp     byte ptr [rsp+2C0h+var_280], al
0x180079273  jz      loc_180079386
0x180079279  mov     qword ptr [rsp+2C0h+var_278], rax
0x18007927e  lea     r8, [rsp+2C0h+var_278]; struct PACKAGE_VERSION *
0x180079283  mov     rdx, r12; unsigned __int16 *
0x180079286  mov     rcx, rsi; this
0x180079289  call    ?GetPackageVersionFromGACHardLink@PIAHelper@Internal@DEH@OSIntegration@@AEAA_NPEBGAEAUPACKAGE_VERSION@@@Z; OSIntegration::DEH::Internal::PIAHelper::GetPackageVersionFromGACHardLink(ushort const *,PACKAGE_VERSION &)
0x18007928e  mov     rbx, qword ptr [rsp+2C0h+var_278]
0x180079293  test    al, al
0x180079295  jz      short loc_1800792CF
0x180079297  mov     rax, [rsi+18h]
0x18007929b  cmp     [rax+1D0h], rbx
0x1800792a2  jnz     short loc_1800792CF
0x1800792a4  cmp     byte ptr [rax+193h], 0
0x1800792ab  jnz     short loc_1800792CF
0x1800792ad  mov     r8b, 1; bool
0x1800792b0  mov     rdx, r15; unsigned __int16 *
0x1800792b3  mov     rcx, rsi; this
0x1800792b6  call    ?AddCurrentUserToACL@PIAHelper@Internal@DEH@OSIntegration@@AEAAJPEBG_N@Z; OSIntegration::DEH::Internal::PIAHelper::AddCurrentUserToACL(ushort const *,bool)
0x1800792bb  mov     ebx, eax
0x1800792bd  test    eax, eax
0x1800792bf  jns     loc_180079657
0x1800792c5  mov     r8, rdi
0x1800792c8  mov     edx, 1F7h
0x1800792cd  jmp     short loc_180079250
0x1800792cf  mov     rax, [rsi+18h]
0x1800792d3  cmp     rbx, [rax+1D0h]
0x1800792da  jbe     loc_180079386
0x1800792e0  mov     rcx, [rbp+1C8h]; this
0x1800792e7  mov     r9d, 80004005h; char *
0x1800792ed  mov     r8, rdi; unsigned int
0x1800792f0  mov     edx, 209h; void *
0x1800792f5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800792fa  test    cs:byte_18024560A, 20h
0x180079301  jz      short loc_180079329
0x180079303  mov     r8, [rsi+18h]
0x180079307  mov     rax, [r8+1D0h]
0x18007930e  mov     [rsp+2C0h+pbCancel], rax
0x180079313  mov     r9, rbx
0x180079316  mov     r8, [r8+0E0h]
0x18007931d  lea     rdx, PIADEHVersionDowngrade
0x180079324  call    McTemplateU0zxx_EventWriteTransfer
0x180079329  mov     rdx, [rsi+18h]
0x18007932d  mov     rax, [rdx+1D0h]
0x180079334  mov     qword ptr [rsp+2C0h+var_278], rax
0x180079339  mov     [rsp+2C0h+var_268], rbx
0x18007933e  mov     rax, [rdx+0E0h]
0x180079345  mov     [rsp+2C0h+var_270], rax
0x18007934a  lea     rax, [rsp+2C0h+var_278]
0x18007934f  mov     [rsp+2C0h+var_290], rax
0x180079354  lea     rax, [rsp+2C0h+var_268]
0x180079359  mov     qword ptr [rsp+2C0h+dwCopyFlags], rax
0x18007935e  lea     rax, [rsp+2C0h+var_270]
0x180079363  mov     [rsp+2C0h+pbCancel], rax
0x180079368  mov     r9d, 3; unsigned int
0x18007936e  lea     r8, PIADEHVersionDowngrade; struct _EVENT_DESCRIPTOR *
0x180079375  lea     rdx, APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID; struct _GUID *
0x18007937c  mov     ecx, 80004005h; int
0x180079381  call    ?SetAppXErrorFromLogMessage@@YAJJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@KZZ; SetAppXErrorFromLogMessage(long,_GUID const &,_EVENT_DESCRIPTOR const &,ulong,...)
0x180079386  mov     rax, [rsi+18h]
0x18007938a  cmp     byte ptr [rax+193h], 0
0x180079391  jz      loc_180079657
0x180079397  mov     rcx, r13
0x18007939a  call    CreateDirectoryTree
0x18007939f  mov     ebx, eax
0x1800793a1  xor     r13d, r13d
0x1800793a4  test    eax, eax
0x1800793a6  jns     short loc_1800793B5
0x1800793a8  mov     r8, rdi
0x1800793ab  mov     edx, 214h
0x1800793b0  jmp     loc_180079250
0x1800793b5  xor     ecx, ecx; dwErrCode
0x1800793b7  call    cs:__imp_SetLastError
0x1800793be  nop     dword ptr [rax+rax+00h]
0x1800793c3  mov     [rsp+2C0h+dwCopyFlags], 8; dwCopyFlags
0x1800793cb  mov     [rsp+2C0h+pbCancel], r13; pbCancel
0x1800793d0  xor     r9d, r9d; lpData
0x1800793d3  xor     r8d, r8d; lpProgressRoutine
0x1800793d6  mov     rdx, r15; lpNewFileName
0x1800793d9  mov     rcx, r14; lpExistingFileName
0x1800793dc  call    cs:__imp_CopyFileExW
0x1800793e3  nop     dword ptr [rax+rax+00h]
0x1800793e8  test    eax, eax
0x1800793ea  jnz     loc_18007950E
0x1800793f0  call    cs:__imp_GetLastError
0x1800793f7  nop     dword ptr [rax+rax+00h]
0x1800793fc  mov     r13d, eax
0x1800793ff  or      r8, 0FFFFFFFFFFFFFFFFh
0x180079403  mov     rcx, r8
0x180079406  xor     edx, edx
0x180079408  inc     rcx
0x18007940b  cmp     [r15+rcx*2], dx
0x180079410  jnz     short loc_180079408
0x180079412  mov     rax, r8
0x180079415  inc     rax
0x180079418  cmp     [r14+rax*2], dx
0x18007941d  jnz     short loc_180079415
0x18007941f  lea     rbx, [rax+20h]
0x180079423  add     rbx, rcx
0x180079426  mov     eax, 2
0x18007942b  mul     rbx
0x18007942e  cmovb   rax, r8
0x180079432  mov     rcx, rax; unsigned __int64
0x180079435  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18007943a  mov     r14, rax
0x18007943d  mov     [rsp+2C0h+var_270], rax
0x180079442  mov     qword ptr [rsp+2C0h+dwCopyFlags], r15
0x180079447  mov     rax, qword ptr [rsp+2C0h+var_260]
0x18007944c  mov     [rsp+2C0h+pbCancel], rax; int
0x180079451  mov     r9d, r13d
0x180079454  lea     r8, aLasterrorDSour; "LastError=%d, source=%s, dest=%s"
0x18007945b  mov     rdx, rbx; unsigned __int64
0x18007945e  mov     rcx, r14; unsigned __int16 *
0x180079461  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180079466  mov     ebx, eax
0x180079468  mov     rcx, [rbp+1C8h]; this
0x18007946f  mov     r8, rdi; unsigned int
0x180079472  test    eax, eax
0x180079474  jns     short loc_180079485
0x180079476  mov     r9d, eax; char *
0x180079479  mov     edx, 223h; void *
0x18007947e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079483  jmp     short loc_1800794F6
0x180079485  mov     ebx, 8000FFFFh
0x18007948a  mov     r9d, ebx; char *
0x18007948d  mov     edx, 229h; void *
0x180079492  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180079497  test    cs:byte_18024560A, 10h
0x18007949e  jz      short loc_1800794BA
0x1800794a0  mov     r8, [rsi+18h]
0x1800794a4  mov     r9, r14
0x1800794a7  mov     r8, [r8+0E0h]
0x1800794ae  lea     rdx, PIACopyFileFailure
0x1800794b5  call    McTemplateU0zz_EventWriteTransfer
0x1800794ba  mov     r9, [rsi+18h]
0x1800794be  mov     [rsp+2C0h+pbCancel], r14; int
0x1800794c3  mov     r9, [r9+0E0h]
0x1800794ca  lea     r8, PIACopyFileFailure
0x1800794d1  mov     ecx, ebx
0x1800794d3  call    ??$appxLog@PEAGPEAG@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@PEAG2@Z; details::appxLog<ushort *,ushort *>(long,_GUID const &,_EVENT_DESCRIPTOR const &,ushort *,ushort *)
0x1800794d8  test    r13d, r13d
0x1800794db  jz      short loc_180079503
0x1800794dd  mov     rcx, [rbp+1C8h]; this
0x1800794e4  mov     r9d, r13d; char *
0x1800794e7  mov     r8, rdi; unsigned int
0x1800794ea  mov     edx, 22Ah; void *
0x1800794ef  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800794f4  mov     ebx, eax
0x1800794f6  mov     rcx, r14; void *
0x1800794f9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800794fe  jmp     loc_18007925F
0x180079503  mov     rcx, r14; void *
0x180079506  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007950b  xor     r13d, r13d
0x18007950e  mov     rcx, r15; this
0x180079511  call    ?SetInitialDACL@Internal@DEH@OSIntegration@@YAJPEBG@Z; OSIntegration::DEH::Internal::SetInitialDACL(ushort const *)
0x180079516  mov     ebx, eax
0x180079518  test    eax, eax
0x18007951a  jns     short loc_180079529
0x18007951c  mov     r8, rdi
0x18007951f  mov     edx, 22Ch
0x180079524  jmp     loc_180079250
0x180079529  mov     rcx, [rsp+2C0h+var_258]
0x18007952e  call    CreateDirectoryTree
0x180079533  mov     ebx, eax
0x180079535  test    eax, eax
0x180079537  jns     short loc_180079546
0x180079539  mov     r8, rdi
0x18007953c  mov     edx, 22Fh
0x180079541  jmp     loc_180079250
0x180079546  cmp     byte ptr [rsp+2C0h+var_280], r13b
0x18007954b  jz      loc_180079628
0x180079551  mov     rcx, r12; lpExistingFileName
0x180079554  call    ?AppXDeleteHardlinkSafely@@YAJPEBG@Z; AppXDeleteHardlinkSafely(ushort const *)
0x180079559  mov     ebx, eax
0x18007955b  test    eax, eax
0x18007955d  jns     loc_180079628
0x180079563  mov     r9d, eax
0x180079566  lea     r8, aDeletefileFail; "Deletefile Failed with 0x%X"
0x18007956d  mov     edx, 100h; unsigned __int64
0x180079572  lea     rcx, [rsp+2C0h+var_250]; unsigned __int16 *
0x180079577  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007957c  mov     r14d, eax
0x18007957f  mov     rcx, [rbp+1C8h]; this
0x180079586  mov     r8, rdi; unsigned int
0x180079589  test    eax, eax
0x18007958b  jns     short loc_1800795A2
0x18007958d  mov     r9d, eax; char *
0x180079590  mov     edx, 238h; void *
0x180079595  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007959a  mov     eax, r14d
0x18007959d  jmp     loc_180079659
0x1800795a2  mov     r14d, 8000FFFFh
0x1800795a8  mov     r9d, r14d; char *
0x1800795ab  mov     edx, 23Eh; void *
0x1800795b0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800795b5  test    cs:byte_18024560A, 20h
0x1800795bc  jz      short loc_1800795DA
0x1800795be  mov     r8, [rsi+18h]
0x1800795c2  lea     r9, [rsp+2C0h+var_250]
0x1800795c7  mov     r8, [r8+0E0h]
0x1800795ce  lea     rdx, PIADEHPreexistingAssembly
0x1800795d5  call    McTemplateU0zz_EventWriteTransfer
0x1800795da  mov     r9, [rsi+18h]
0x1800795de  lea     rax, [rsp+2C0h+var_250]
0x1800795e3  mov     [rsp+2C0h+pbCancel], rax
0x1800795e8  mov     r9, [r9+0E0h]
0x1800795ef  lea     r8, PIADEHPreexistingAssembly
0x1800795f6  mov     ecx, r14d
0x1800795f9  call    ??$appxLog@PEAGPEAG@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@PEAG2@Z; details::appxLog<ushort *,ushort *>(long,_GUID const &,_EVENT_DESCRIPTOR const &,ushort *,ushort *)
0x1800795fe  cmp     ebx, 80070020h
0x180079604  jz      short loc_180079612
0x180079606  cmp     ebx, 80070005h
0x18007960c  jnz     loc_18007925F
0x180079612  lea     r8, aPiahelper; "PIAHelper"
0x180079619  mov     edx, ebx
0x18007961b  mov     rcx, r12; lpFileName
0x18007961e  call    ??$LogFileInUse@VFileInUse@DesktopAppXProvider@@@Deployment@Common@@YAXPEBGJ0_N@Z; Common::Deployment::LogFileInUse<DesktopAppXProvider::FileInUse>(ushort const *,long,ushort const *,bool)
0x180079623  jmp     loc_18007925F
0x180079628  xor     r8d, r8d; lpSecurityAttributes
0x18007962b  mov     rdx, r15; lpExistingFileName
0x18007962e  mov     rcx, r12; lpFileName
0x180079631  call    cs:__imp_CreateHardLinkW
0x180079638  nop     dword ptr [rax+rax+00h]
0x18007963d  test    eax, eax
0x18007963f  jnz     short loc_180079657
0x180079641  mov     rcx, [rbp+1C8h]; this
0x180079648  mov     r8, rdi; unsigned int
0x18007964b  mov     edx, 249h; void *
0x180079650  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180079655  jmp     short loc_180079659
0x180079657  xor     eax, eax
0x180079659  mov     rcx, [rbp+1C0h+var_50]
0x180079660  xor     rcx, rsp; StackCookie
0x180079663  call    __security_check_cookie
0x180079668  add     rsp, 288h
0x18007966f  pop     r15
0x180079671  pop     r14
0x180079673  pop     r13
0x180079675  pop     r12
0x180079677  pop     rdi
0x180079678  pop     rsi
0x180079679  pop     rbx
0x18007967a  pop     rbp
0x18007967b  retn
```
