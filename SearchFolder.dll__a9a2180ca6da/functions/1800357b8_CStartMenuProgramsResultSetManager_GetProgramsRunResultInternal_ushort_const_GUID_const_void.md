# CStartMenuProgramsResultSetManager::_GetProgramsRunResultInternal(ushort const *,_GUID const &,void * *)

- ea: `0x1800357b8`
- end: `0x180035a73`
- name: `?_GetProgramsRunResultInternal@CStartMenuProgramsResultSetManager@@AEAAJPEBGAEBU_GUID@@PEAPEAX@Z`
- size: `699`
- prototype: `__int64 __fastcall(CStartMenuProgramsResultSetManager *this, const unsigned __int16 *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800354e8`

## callees

- `0x180005460`
- `0x1800054b0`
- `0x180005c88`
- `0x180006900`
- `0x18000ecc4`
- `0x18000eec0`
- `0x18002eb70`
- `0x1800357b8`
- `0x180036aec`

## import_xrefs

- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800358d2`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800358d2`
- `SHELL32!SHCreateItemFromParsingName` at `0x18003585b`
- `SHELL32!SHCreateItemFromParsingName` at `0x18003597e`
- `SHELL32!SHCreateItemFromParsingName` at `0x18003585b`
- `SHELL32!SHCreateItemFromParsingName` at `0x18003597e`
- `SHELL32!SHEvaluateSystemCommandTemplate` at `0x18003582f`
- `SHELL32!SHEvaluateSystemCommandTemplate` at `0x18003582f`
- `SHELL32!SHGetKnownFolderPath` at `0x180035912`
- `SHELL32!SHGetKnownFolderPath` at `0x180035912`
- `SHELL32!__imp_PathResolve` at `0x180035953`
- `SHELL32!__imp_PathResolve` at `0x180035953`
- `SHLWAPI!PathGetArgsW` at `0x1800358c4`
- `SHLWAPI!PathGetArgsW` at `0x1800358c4`
- `SHLWAPI!PathRemoveArgsW` at `0x1800358eb`
- `SHLWAPI!PathRemoveArgsW` at `0x1800358eb`
- `SHLWAPI!PathQuoteSpacesW` at `0x180035992`
- `SHLWAPI!PathQuoteSpacesW` at `0x180035992`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CStartMenuProgramsResultSetManager::_GetProgramsRunResultInternal(
        CStartMenuProgramsResultSetManager *this,
        const unsigned __int16 *a2,
        const struct _GUID *a3,
        void **a4)
{
  HRESULT v6; // ebx
  CStartMenuProgramsResultSetManager *v7; // rcx
  __int64 v8; // r8
  const WCHAR *ArgsW; // rax
  HRESULT v10; // eax
  PCWSTR *v11; // rcx
  CStartMenuProgramsResultSetManager *v12; // rcx
  __int64 v13; // r8
  void *ppv; // [rsp+40h] [rbp-C0h] BYREF
  PWSTR ppszParameters; // [rsp+48h] [rbp-B8h] BYREF
  PWSTR ppszPath; // [rsp+50h] [rbp-B0h] BYREF
  PWSTR ppszCommandLine; // [rsp+58h] [rbp-A8h] BYREF
  PWSTR ppszApplication; // [rsp+60h] [rbp-A0h] BYREF
  PCWSTR dirs[3]; // [rsp+68h] [rbp-98h] BYREF
  WCHAR pszCmdTemplate[264]; // [rsp+80h] [rbp-80h] BYREF

  *a4 = 0;
  v6 = StringCchCopyW(pszCmdTemplate, 0x104u, a2);
  if ( v6 >= 0 )
  {
    ppszApplication = 0;
    ppszCommandLine = 0;
    ppszParameters = 0;
    if ( SHEvaluateSystemCommandTemplate(pszCmdTemplate, &ppszApplication, &ppszCommandLine, &ppszParameters) < 0 )
    {
      ArgsW = PathGetArgsW(pszCmdTemplate);
      v6 = SHStrDupW(ArgsW, &ppszParameters);
      if ( v6 >= 0 )
      {
        v6 = -2147467259;
        PathRemoveArgsW(pszCmdTemplate);
        ppszPath = 0;
        *(_OWORD *)dirs = 0;
        v10 = SHGetKnownFolderPath(&FOLDERID_Profile, 0x1000u, 0, &ppszPath);
        if ( v10 >= 0 )
          dirs[0] = ppszPath;
        v11 = dirs;
        if ( v10 >= 0 )
          v11 = &dirs[1];
        *v11 = 0;
        if ( dirs[0] && PathResolve(pszCmdTemplate, dirs, 3u) )
        {
          ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&ppv);
          v6 = SHCreateItemFromParsingName(pszCmdTemplate, 0, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &ppv);
          if ( v6 >= 0 )
          {
            PathQuoteSpacesW(pszCmdTemplate);
            if ( (unsigned int)CStartMenuProgramsResultSetManager::_IsItemApproved(
                                 v12,
                                 (struct IShellItem *)ppv,
                                 ppszParameters) )
            {
              if ( !ppszParameters
                || !*ppszParameters
                || (v6 = StringCchPrintfW(pszCmdTemplate, 0x104u, L"%s %s", pszCmdTemplate, ppszParameters), v6 >= 0) )
              {
                v6 = PropertyStoreFromItem(
                       ppv,
                       500,
                       v13,
                       a2,
                       pszCmdTemplate,
                       &GUID_3017056d_9a91_4e90_937d_746c72abbf4f,
                       a4);
              }
            }
            else
            {
              v6 = -2147467259;
            }
          }
          ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(&ppv);
        }
        CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&ppszPath);
      }
    }
    else
    {
      ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&ppv);
      v6 = SHCreateItemFromParsingName(ppszApplication, 0, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &ppv);
      if ( v6 >= 0 )
      {
        if ( (unsigned int)CStartMenuProgramsResultSetManager::_IsItemApproved(
                             v7,
                             (struct IShellItem *)ppv,
                             ppszParameters) )
          v6 = PropertyStoreFromItem(
                 ppv,
                 500,
                 v8,
                 pszCmdTemplate,
                 ppszCommandLine,
                 &GUID_3017056d_9a91_4e90_937d_746c72abbf4f,
                 a4);
        else
          v6 = -2147467259;
      }
      ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(&ppv);
    }
    CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&ppszParameters);
    CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&ppszCommandLine);
    CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&ppszApplication);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800357b8  mov     [rsp-8+arg_0], rbx
0x1800357bd  mov     [rsp-8+arg_10], rsi
0x1800357c2  push    rbp
0x1800357c3  push    rdi
0x1800357c4  push    r14
0x1800357c6  lea     rbp, [rsp-1A0h]
0x1800357ce  sub     rsp, 2A0h
0x1800357d5  mov     rax, cs:__security_cookie
0x1800357dc  xor     rax, rsp
0x1800357df  mov     [rbp+1B0h+var_20], rax
0x1800357e6  mov     rdi, r9
0x1800357e9  mov     rsi, rdx
0x1800357ec  xor     r14d, r14d
0x1800357ef  mov     [r9], r14
0x1800357f2  mov     r8, rdx; unsigned __int16 *
0x1800357f5  mov     edx, 104h; unsigned __int64
0x1800357fa  lea     rcx, [rbp+1B0h+pszCmdTemplate]; unsigned __int16 *
0x1800357fe  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180035803  mov     ebx, eax
0x180035805  test    eax, eax
0x180035807  js      loc_180035A4A
0x18003580d  mov     [rsp+2B0h+ppszApplication], r14
0x180035812  mov     [rsp+2B0h+ppszCommandLine], r14
0x180035817  mov     [rsp+2B0h+ppszParameters], r14
0x18003581c  lea     r9, [rsp+2B0h+ppszParameters]; ppszParameters
0x180035821  lea     r8, [rsp+2B0h+ppszCommandLine]; ppszCommandLine
0x180035826  lea     rdx, [rsp+2B0h+ppszApplication]; ppszApplication
0x18003582b  lea     rcx, [rbp+1B0h+pszCmdTemplate]; pszCmdTemplate
0x18003582f  call    cs:__imp_SHEvaluateSystemCommandTemplate
0x180035835  test    eax, eax
0x180035837  js      loc_1800358C0
0x18003583d  lea     rcx, [rsp+2B0h+ppv]; void *
0x180035842  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180035847  nop
0x180035848  lea     r9, [rsp+2B0h+ppv]; ppv
0x18003584d  lea     r8, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x180035854  xor     edx, edx; pbc
0x180035856  mov     rcx, [rsp+2B0h+ppszApplication]; pszPath
0x18003585b  call    cs:__imp_SHCreateItemFromParsingName
0x180035861  mov     ebx, eax
0x180035863  test    eax, eax
0x180035865  js      short loc_1800358B1
0x180035867  mov     r8, [rsp+2B0h+ppszParameters]; unsigned __int16 *
0x18003586c  mov     rdx, [rsp+2B0h+ppv]; struct IShellItem *
0x180035871  call    ?_IsItemApproved@CStartMenuProgramsResultSetManager@@AEAAHPEAUIShellItem@@PEBG@Z; CStartMenuProgramsResultSetManager::_IsItemApproved(IShellItem *,ushort const *)
0x180035876  test    eax, eax
0x180035878  jnz     short loc_180035881
0x18003587a  mov     ebx, 80004005h
0x18003587f  jmp     short loc_1800358B1
0x180035881  mov     rax, [rsp+2B0h+ppszCommandLine]
0x180035886  mov     [rsp+2B0h+var_280], rdi
0x18003588b  lea     rcx, _GUID_3017056d_9a91_4e90_937d_746c72abbf4f
0x180035892  mov     [rsp+2B0h+var_288], rcx
0x180035897  mov     [rsp+2B0h+var_290], rax
0x18003589c  lea     r9, [rbp+1B0h+pszCmdTemplate]
0x1800358a0  mov     edx, 1F4h
0x1800358a5  mov     rcx, [rsp+2B0h+ppv]
0x1800358aa  call    ?PropertyStoreFromItem@@YAJPEAUIShellItem2@@W4tagSM_GROUP_ID@@HPEBG2AEBU_GUID@@PEAPEAX@Z; PropertyStoreFromItem(IShellItem2 *,tagSM_GROUP_ID,int,ushort const *,ushort const *,_GUID const &,void * *)
0x1800358af  mov     ebx, eax
0x1800358b1  lea     rcx, [rsp+2B0h+ppv]
0x1800358b6  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x1800358bb  jmp     loc_180035A2A
0x1800358c0  lea     rcx, [rbp+1B0h+pszCmdTemplate]; pszPath
0x1800358c4  call    cs:__imp_PathGetArgsW
0x1800358ca  lea     rdx, [rsp+2B0h+ppszParameters]; ppwsz
0x1800358cf  mov     rcx, rax; psz
0x1800358d2  call    cs:__imp_SHStrDupW
0x1800358d8  mov     ebx, eax
0x1800358da  test    eax, eax
0x1800358dc  js      loc_180035A2A
0x1800358e2  mov     ebx, 80004005h
0x1800358e7  lea     rcx, [rbp+1B0h+pszCmdTemplate]; pszPath
0x1800358eb  call    cs:__imp_PathRemoveArgsW
0x1800358f1  mov     [rsp+2B0h+ppszPath], r14
0x1800358f6  xorps   xmm0, xmm0
0x1800358f9  movups  xmmword ptr [rsp+2B0h+dirs], xmm0
0x1800358fe  lea     r9, [rsp+2B0h+ppszPath]; ppszPath
0x180035903  xor     r8d, r8d; hToken
0x180035906  mov     edx, 1000h; dwFlags
0x18003590b  lea     rcx, FOLDERID_Profile; rfid
0x180035912  call    cs:__imp_SHGetKnownFolderPath
0x180035918  test    eax, eax
0x18003591a  js      short loc_180035926
0x18003591c  mov     rcx, [rsp+2B0h+ppszPath]
0x180035921  mov     [rsp+2B0h+dirs], rcx
0x180035926  lea     rcx, [rsp+2B0h+dirs]
0x18003592b  lea     rdx, [rsp+2B0h+dirs+8]
0x180035930  test    eax, eax
0x180035932  cmovns  rcx, rdx
0x180035936  mov     [rcx], r14
0x180035939  cmp     [rsp+2B0h+dirs], r14
0x18003593e  jz      loc_180035A1F
0x180035944  mov     r8d, 3; fFlags
0x18003594a  lea     rdx, [rsp+2B0h+dirs]; dirs
0x18003594f  lea     rcx, [rbp+1B0h+pszCmdTemplate]; pszPath
0x180035953  call    cs:__imp_PathResolve
0x180035959  test    eax, eax
0x18003595b  jz      loc_180035A1F
0x180035961  lea     rcx, [rsp+2B0h+ppv]; void *
0x180035966  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18003596b  nop
0x18003596c  lea     r9, [rsp+2B0h+ppv]; ppv
0x180035971  lea     r8, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x180035978  xor     edx, edx; pbc
0x18003597a  lea     rcx, [rbp+1B0h+pszCmdTemplate]; pszPath
0x18003597e  call    cs:__imp_SHCreateItemFromParsingName
0x180035984  mov     ebx, eax
0x180035986  test    eax, eax
0x180035988  js      loc_180035A14
0x18003598e  lea     rcx, [rbp+1B0h+pszCmdTemplate]; lpsz
0x180035992  call    cs:__imp_PathQuoteSpacesW
0x180035998  mov     r8, [rsp+2B0h+ppszParameters]; unsigned __int16 *
0x18003599d  mov     rdx, [rsp+2B0h+ppv]; struct IShellItem *
0x1800359a2  call    ?_IsItemApproved@CStartMenuProgramsResultSetManager@@AEAAHPEAUIShellItem@@PEBG@Z; CStartMenuProgramsResultSetManager::_IsItemApproved(IShellItem *,ushort const *)
0x1800359a7  test    eax, eax
0x1800359a9  jnz     short loc_1800359B2
0x1800359ab  mov     ebx, 80004005h
0x1800359b0  jmp     short loc_180035A14
0x1800359b2  mov     rax, [rsp+2B0h+ppszParameters]
0x1800359b7  test    rax, rax
0x1800359ba  jz      short loc_1800359E6
0x1800359bc  cmp     [rax], r14w
0x1800359c0  jz      short loc_1800359E6
0x1800359c2  mov     [rsp+2B0h+var_290], rax
0x1800359c7  lea     r9, [rbp+1B0h+pszCmdTemplate]
0x1800359cb  lea     r8, aSS_0; "%s %s"
0x1800359d2  mov     edx, 104h; unsigned __int64
0x1800359d7  lea     rcx, [rbp+1B0h+pszCmdTemplate]; unsigned __int16 *
0x1800359db  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800359e0  mov     ebx, eax
0x1800359e2  test    eax, eax
0x1800359e4  js      short loc_180035A14
0x1800359e6  mov     [rsp+2B0h+var_280], rdi
0x1800359eb  lea     rcx, _GUID_3017056d_9a91_4e90_937d_746c72abbf4f
0x1800359f2  mov     [rsp+2B0h+var_288], rcx
0x1800359f7  lea     rax, [rbp+1B0h+pszCmdTemplate]
0x1800359fb  mov     [rsp+2B0h+var_290], rax
0x180035a00  mov     r9, rsi
0x180035a03  mov     edx, 1F4h
0x180035a08  mov     rcx, [rsp+2B0h+ppv]
0x180035a0d  call    ?PropertyStoreFromItem@@YAJPEAUIShellItem2@@W4tagSM_GROUP_ID@@HPEBG2AEBU_GUID@@PEAPEAX@Z; PropertyStoreFromItem(IShellItem2 *,tagSM_GROUP_ID,int,ushort const *,ushort const *,_GUID const &,void * *)
0x180035a12  mov     ebx, eax
0x180035a14  lea     rcx, [rsp+2B0h+ppv]
0x180035a19  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180035a1e  nop
0x180035a1f  lea     rcx, [rsp+2B0h+ppszPath]; void *
0x180035a24  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180035a29  nop
0x180035a2a  lea     rcx, [rsp+2B0h+ppszParameters]; void *
0x180035a2f  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180035a34  nop
0x180035a35  lea     rcx, [rsp+2B0h+ppszCommandLine]; void *
0x180035a3a  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180035a3f  nop
0x180035a40  lea     rcx, [rsp+2B0h+ppszApplication]; void *
0x180035a45  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180035a4a  mov     eax, ebx
0x180035a4c  mov     rcx, [rbp+1B0h+var_20]
0x180035a53  xor     rcx, rsp; StackCookie
0x180035a56  call    __security_check_cookie
0x180035a5b  lea     r11, [rsp+2B0h+var_10]
0x180035a63  mov     rbx, [r11+20h]
0x180035a67  mov     rsi, [r11+30h]
0x180035a6b  mov     rsp, r11
0x180035a6e  pop     r14
0x180035a70  pop     rdi
0x180035a71  pop     rbp
0x180035a72  retn
```
