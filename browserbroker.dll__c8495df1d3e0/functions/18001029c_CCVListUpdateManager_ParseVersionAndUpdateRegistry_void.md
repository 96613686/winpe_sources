# CCVListUpdateManager::ParseVersionAndUpdateRegistry(void)

- ea: `0x18001029c`
- end: `0x180010538`
- name: `?ParseVersionAndUpdateRegistry@CCVListUpdateManager@@AEAAJXZ`
- size: `668`
- prototype: `__int64 __fastcall(CCVListUpdateManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000fad8`

## callees

- `0x180002ce0`
- `0x180006cc4`
- `0x18001029c`
- `0x1800105e0`
- `0x18002d010`

## import_xrefs

- `iertutil!__imp_SetValue` at `0x1800104cc`
- `iertutil!__imp_SetValue` at `0x1800104fa`
- `iertutil!__imp_SetValue` at `0x1800104cc`
- `iertutil!__imp_SetValue` at `0x1800104fa`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToInt64ExW` at `0x18001049f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToInt64ExW` at `0x18001049f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800103db`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180010480`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800103db`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180010480`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateStreamOnFileW` at `0x1800102fb`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateStreamOnFileW` at `0x1800102fb`
- `urlmon!__imp_GetIEBrowserModeFilterSpartanMediumILPath` at `0x1800102e3`
- `urlmon!__imp_GetIEBrowserModeFilterSpartanMediumILPath` at `0x1800102e3`
- `XmlLite!CreateXmlReader` at `0x180010323`
- `XmlLite!CreateXmlReader` at `0x180010323`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CCVListUpdateManager::ParseVersionAndUpdateRegistry(CCVListUpdateManager *this)
{
  HRESULT IEBrowserModeFilterSpartanMediumILPath; // ebx
  void *ppvObject; // [rsp+30h] [rbp-D0h] BYREF
  int v4; // [rsp+38h] [rbp-C8h] BYREF
  int v5; // [rsp+3Ch] [rbp-C4h] BYREF
  int v6; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR pszStr1; // [rsp+48h] [rbp-B8h] BYREF
  HRESULT v8; // [rsp+50h] [rbp-B0h] BYREF
  LONGLONG pllRet; // [rsp+58h] [rbp-A8h] BYREF
  IStream *ppstm; // [rsp+60h] [rbp-A0h] BYREF
  PCWSTR pszString; // [rsp+68h] [rbp-98h] BYREF
  WCHAR pszFile[264]; // [rsp+70h] [rbp-90h] BYREF

  pszFile[0] = 0;
  ppstm = 0;
  IEBrowserModeFilterSpartanMediumILPath = GetIEBrowserModeFilterSpartanMediumILPath(1, &pszSubkey, pszFile, 260);
  if ( IEBrowserModeFilterSpartanMediumILPath >= 0 )
    IEBrowserModeFilterSpartanMediumILPath = SHCreateStreamOnFileW(pszFile, 0, &ppstm);
  if ( !IEBrowserModeFilterSpartanMediumILPath )
  {
    ppvObject = 0;
    IEBrowserModeFilterSpartanMediumILPath = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
    if ( !IEBrowserModeFilterSpartanMediumILPath )
    {
      IEBrowserModeFilterSpartanMediumILPath = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)ppvObject + 40LL))(
                                                 ppvObject,
                                                 1,
                                                 2);
      if ( !IEBrowserModeFilterSpartanMediumILPath )
      {
        v5 = 0;
        IEBrowserModeFilterSpartanMediumILPath = (*(__int64 (__fastcall **)(void *, IStream *))(*(_QWORD *)ppvObject
                                                                                              + 24LL))(
                                                   ppvObject,
                                                   ppstm);
        while ( !(*(unsigned int (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v5) )
        {
          if ( v5 == 1 )
          {
            pszStr1 = 0;
            v4 = 0;
            IEBrowserModeFilterSpartanMediumILPath = (*(__int64 (__fastcall **)(void *, LPCWSTR *, int *))(*(_QWORD *)ppvObject + 112LL))(
                                                       ppvObject,
                                                       &pszStr1,
                                                       &v4);
            if ( !IEBrowserModeFilterSpartanMediumILPath && v4 == 7 && !StrCmpNICW(pszStr1, L"version", 7) )
            {
              SkipWhitespace(ppvObject);
              pszString = 0;
              v8 = IEBrowserModeFilterSpartanMediumILPath;
              IEBrowserModeFilterSpartanMediumILPath = (*(__int64 (__fastcall **)(void *, PCWSTR *, HRESULT *))(*(_QWORD *)ppvObject + 128LL))(
                                                         ppvObject,
                                                         &pszString,
                                                         &v8);
              if ( !IEBrowserModeFilterSpartanMediumILPath )
              {
                v5 = 13;
                IEBrowserModeFilterSpartanMediumILPath = SkipWhitespace(ppvObject);
                if ( !IEBrowserModeFilterSpartanMediumILPath )
                {
                  IEBrowserModeFilterSpartanMediumILPath = (*(__int64 (__fastcall **)(void *, LPCWSTR *, int *))(*(_QWORD *)ppvObject + 112LL))(
                                                             ppvObject,
                                                             &pszStr1,
                                                             &v4);
                  if ( !IEBrowserModeFilterSpartanMediumILPath && v4 == 7 && !StrCmpNICW(pszStr1, L"version", 7) )
                  {
                    pllRet = 0;
                    if ( StrToInt64ExW(pszString, 0, &pllRet) )
                    {
                      v6 = pllRet;
                      SetValue(
                        (__int64 *)SettingStore::IEVALUE_BrowserEmulation_CVListXMLVersionLow[0],
                        (unsigned int)(IEBrowserModeFilterSpartanMediumILPath + 2),
                        (unsigned int)(IEBrowserModeFilterSpartanMediumILPath + 1),
                        &v6,
                        4);
                      v6 = HIDWORD(pllRet);
                      SetValue(
                        (__int64 *)SettingStore::IEVALUE_BrowserEmulation_CVListXMLVersionHigh[0],
                        (unsigned int)(IEBrowserModeFilterSpartanMediumILPath + 2),
                        (unsigned int)(IEBrowserModeFilterSpartanMediumILPath + 1),
                        &v6,
                        4);
                    }
                  }
                }
              }
              break;
            }
          }
        }
      }
    }
    ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>((__int64 *)&ppvObject);
  }
  ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>((__int64 *)&ppstm);
  return (unsigned int)IEBrowserModeFilterSpartanMediumILPath;
}

```

## disassembly

```asm
0x18001029c  mov     [rsp-8+arg_0], rbx
0x1800102a1  push    rbp
0x1800102a2  lea     rbp, [rsp-190h]
0x1800102aa  sub     rsp, 290h
0x1800102b1  mov     rax, cs:__security_cookie
0x1800102b8  xor     rax, rsp
0x1800102bb  mov     [rbp+190h+var_10], rax
0x1800102c2  xor     eax, eax
0x1800102c4  mov     [rsp+290h+pszFile], ax
0x1800102c9  mov     [rsp+290h+ppstm], rax
0x1800102ce  mov     r9d, 104h
0x1800102d4  lea     r8, [rsp+290h+pszFile]
0x1800102d9  lea     rdx, pszSubkey
0x1800102e0  lea     ecx, [rax+1]
0x1800102e3  call    cs:__imp_GetIEBrowserModeFilterSpartanMediumILPath
0x1800102e9  mov     ebx, eax
0x1800102eb  test    eax, eax
0x1800102ed  js      short loc_180010303
0x1800102ef  lea     r8, [rsp+290h+ppstm]; ppstm
0x1800102f4  xor     edx, edx; grfMode
0x1800102f6  lea     rcx, [rsp+290h+pszFile]; pszFile
0x1800102fb  call    cs:__imp_SHCreateStreamOnFileW
0x180010301  mov     ebx, eax
0x180010303  test    ebx, ebx
0x180010305  jnz     loc_18001050C
0x18001030b  mov     [rsp+290h+ppvObject], 0
0x180010314  xor     r8d, r8d; pMalloc
0x180010317  lea     rdx, [rsp+290h+ppvObject]; ppvObject
0x18001031c  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x180010323  call    cs:__imp_CreateXmlReader
0x180010329  mov     ebx, eax
0x18001032b  test    eax, eax
0x18001032d  jnz     loc_180010501
0x180010333  mov     rcx, [rsp+290h+ppvObject]
0x180010338  mov     rax, [rcx]
0x18001033b  lea     edx, [rbx+1]
0x18001033e  lea     r8d, [rbx+2]
0x180010342  mov     rax, [rax+28h]
0x180010346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001034b  mov     ebx, eax
0x18001034d  test    eax, eax
0x18001034f  jnz     loc_180010501
0x180010355  mov     [rsp+290h+var_254], eax
0x180010359  mov     rcx, [rsp+290h+ppvObject]
0x18001035e  mov     rax, [rcx]
0x180010361  mov     rdx, [rsp+290h+ppstm]
0x180010366  mov     rax, [rax+18h]
0x18001036a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001036f  mov     ebx, eax
0x180010371  mov     rcx, [rsp+290h+ppvObject]
0x180010376  mov     rax, [rcx]
0x180010379  lea     rdx, [rsp+290h+var_254]
0x18001037e  mov     rax, [rax+30h]
0x180010382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010387  test    eax, eax
0x180010389  jnz     loc_180010501
0x18001038f  cmp     [rsp+290h+var_254], 1
0x180010394  jnz     short loc_180010371
0x180010396  mov     [rsp+290h+pszStr1], 0
0x18001039f  mov     [rsp+290h+var_258], eax
0x1800103a3  mov     rcx, [rsp+290h+ppvObject]
0x1800103a8  mov     rax, [rcx]
0x1800103ab  lea     r8, [rsp+290h+var_258]
0x1800103b0  lea     rdx, [rsp+290h+pszStr1]
0x1800103b5  mov     rax, [rax+70h]
0x1800103b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103be  mov     ebx, eax
0x1800103c0  test    eax, eax
0x1800103c2  jnz     short loc_180010371
0x1800103c4  cmp     [rsp+290h+var_258], 7
0x1800103c9  jnz     short loc_180010371
0x1800103cb  lea     r8d, [rax+7]; nChar
0x1800103cf  lea     rdx, aVersion; "version"
0x1800103d6  mov     rcx, [rsp+290h+pszStr1]; pszStr1
0x1800103db  call    cs:__imp_StrCmpNICW
0x1800103e1  test    eax, eax
0x1800103e3  jnz     short loc_180010371
0x1800103e5  mov     rcx, [rsp+290h+ppvObject]
0x1800103ea  call    SkipWhitespace
0x1800103ef  mov     [rsp+290h+pszString], 0
0x1800103f8  mov     [rsp+290h+var_240], ebx
0x1800103fc  mov     rcx, [rsp+290h+ppvObject]
0x180010401  mov     rax, [rcx]
0x180010404  lea     r8, [rsp+290h+var_240]
0x180010409  lea     rdx, [rsp+290h+pszString]
0x18001040e  mov     rax, [rax+80h]
0x180010415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001041a  mov     ebx, eax
0x18001041c  test    eax, eax
0x18001041e  jnz     loc_180010501
0x180010424  mov     [rsp+290h+var_254], 0Dh
0x18001042c  mov     rcx, [rsp+290h+ppvObject]
0x180010431  call    SkipWhitespace
0x180010436  mov     ebx, eax
0x180010438  test    eax, eax
0x18001043a  jnz     loc_180010501
0x180010440  mov     rcx, [rsp+290h+ppvObject]
0x180010445  mov     rax, [rcx]
0x180010448  lea     r8, [rsp+290h+var_258]
0x18001044d  lea     rdx, [rsp+290h+pszStr1]
0x180010452  mov     rax, [rax+70h]
0x180010456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001045b  mov     ebx, eax
0x18001045d  test    eax, eax
0x18001045f  jnz     loc_180010501
0x180010465  cmp     [rsp+290h+var_258], 7
0x18001046a  jnz     loc_180010501
0x180010470  lea     r8d, [rax+7]; nChar
0x180010474  lea     rdx, aVersion; "version"
0x18001047b  mov     rcx, [rsp+290h+pszStr1]; pszStr1
0x180010480  call    cs:__imp_StrCmpNICW
0x180010486  test    eax, eax
0x180010488  jnz     short loc_180010501
0x18001048a  mov     [rsp+290h+pllRet], 0
0x180010493  lea     r8, [rsp+290h+pllRet]; pllRet
0x180010498  xor     edx, edx; dwFlags
0x18001049a  mov     rcx, [rsp+290h+pszString]; pszString
0x18001049f  call    cs:__imp_StrToInt64ExW
0x1800104a5  test    eax, eax
0x1800104a7  jz      short loc_180010501
0x1800104a9  mov     eax, dword ptr [rsp+290h+pllRet]
0x1800104ad  mov     [rsp+290h+var_250], eax
0x1800104b1  mov     [rsp+290h+var_270], 4
0x1800104b9  lea     r9, [rsp+290h+var_250]
0x1800104be  lea     edx, [rbx+2]
0x1800104c1  lea     r8d, [rbx+1]
0x1800104c5  mov     rcx, cs:?IEVALUE_BrowserEmulation_CVListXMLVersionLow@SettingStore@@3U?$VALUEID@K@1@B; SettingStore::VALUEID<ulong> const SettingStore::IEVALUE_BrowserEmulation_CVListXMLVersionLow
0x1800104cc  call    cs:__imp_SetValue
0x1800104d2  mov     rax, [rsp+290h+pllRet]
0x1800104d7  sar     rax, 20h
0x1800104db  mov     [rsp+290h+var_250], eax
0x1800104df  mov     [rsp+290h+var_270], 4
0x1800104e7  lea     r9, [rsp+290h+var_250]
0x1800104ec  lea     edx, [rbx+2]
0x1800104ef  lea     r8d, [rbx+1]
0x1800104f3  mov     rcx, cs:?IEVALUE_BrowserEmulation_CVListXMLVersionHigh@SettingStore@@3U?$VALUEID@K@1@B; SettingStore::VALUEID<ulong> const SettingStore::IEVALUE_BrowserEmulation_CVListXMLVersionHigh
0x1800104fa  call    cs:__imp_SetValue
0x180010500  nop
0x180010501  lea     rcx, [rsp+290h+ppvObject]
0x180010506  call    ??1?$CComPtrBase@UIExtractIconW@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>(void)
0x18001050b  nop
0x18001050c  lea     rcx, [rsp+290h+ppstm]
0x180010511  call    ??1?$CComPtrBase@UIExtractIconW@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>(void)
0x180010516  mov     eax, ebx
0x180010518  mov     rcx, [rbp+190h+var_10]
0x18001051f  xor     rcx, rsp; StackCookie
0x180010522  call    __security_check_cookie
0x180010527  mov     rbx, [rsp+290h+arg_0]
0x18001052f  add     rsp, 290h
0x180010536  pop     rbp
0x180010537  retn
```
