# UpdateUrlCacheContentPathHelper(ushort const *)

- ea: `0x1801468d0`
- end: `0x180146e08`
- name: `?UpdateUrlCacheContentPathHelper@@YAJPEBG@Z`
- size: `1336`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, reparse_path, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180199b90`

## callees

- `0x18001bc98`
- `0x1800204f8`
- `0x18002086c`
- `0x180025910`
- `0x1800701d0`
- `0x1800a7e28`
- `0x1800a85a8`
- `0x180100434`
- `0x180103998`
- `0x1801468d0`
- `0x18014a7a0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180146996`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180146996`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801469d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180146de4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801469d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180146de4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180146d9b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180146dcd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180146d9b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180146dcd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180146ae6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180146b86`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180146c39`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180146cd8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180146d74`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180146ae6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180146b86`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180146c39`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180146cd8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180146d74`
- `api-ms-win-shell-shellfolders-l1-1-0!SHSetKnownFolderPath` at `0x180146a15`
- `api-ms-win-shell-shellfolders-l1-1-0!SHSetKnownFolderPath` at `0x180146a15`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180146bac`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180146bac`

## string_xrefs

- `0x180146c14`: `DeleteOldCacheCounters`
- `0x180146ac1`: `DeleteOldCacheContainer`
- `0x180146d4f`: `DeleteOldCacheContainerLow2`
- `0x180146b61`: `DeleteOldCacheContainer2`
- `0x180146cb3`: `DeleteOldCacheContainerLow`
- `0x180146a9c`: `"%ComSpec%" /C rd /S /Q "`
- `0x180146b39`: `"%ComSpec%" /C rd /S /Q "`
- `0x180146c8b`: `"%ComSpec%" /C rd /S /Q "`
- `0x180146d2a`: `"%ComSpec%" /C rd /S /Q "`
- `0x180146bec`: `"%ComSpec%" /C del /F /Q "`

## pseudocode

```c
__int64 __fastcall UpdateUrlCacheContentPathHelper(const unsigned __int16 *a1)
{
  int Config; // edi
  HANDLE FileW; // rax
  int LastError; // eax
  LSTATUS v5; // eax
  LSTATUS v6; // eax
  char Bool; // al
  const unsigned __int16 *v8; // r8
  LSTATUS v9; // eax
  LSTATUS v10; // eax
  LSTATUS v11; // eax
  const unsigned __int16 *dwCreationDisposition; // [rsp+20h] [rbp-59h]
  const unsigned __int16 *dwCreationDispositiona; // [rsp+20h] [rbp-59h]
  const unsigned __int16 *dwCreationDispositionb; // [rsp+20h] [rbp-59h]
  const unsigned __int16 *dwCreationDispositionc; // [rsp+20h] [rbp-59h]
  const unsigned __int16 *dwCreationDispositiond; // [rsp+20h] [rbp-59h]
  const unsigned __int16 *dwFlagsAndAttributes; // [rsp+28h] [rbp-51h]
  const unsigned __int16 *dwFlagsAndAttributesa; // [rsp+28h] [rbp-51h]
  const unsigned __int16 *dwFlagsAndAttributesb; // [rsp+28h] [rbp-51h]
  const unsigned __int16 *dwFlagsAndAttributesc; // [rsp+28h] [rbp-51h]
  const unsigned __int16 *dwFlagsAndAttributesd; // [rsp+28h] [rbp-51h]
  const unsigned __int16 *hTemplateFile; // [rsp+30h] [rbp-49h]
  const unsigned __int16 *hTemplateFilea; // [rsp+30h] [rbp-49h]
  const unsigned __int16 *hTemplateFileb; // [rsp+30h] [rbp-49h]
  const unsigned __int16 *hTemplateFilec; // [rsp+30h] [rbp-49h]
  const unsigned __int16 *hTemplateFiled; // [rsp+30h] [rbp-49h]
  const unsigned __int16 *v28; // [rsp+38h] [rbp-41h]
  const unsigned __int16 *v29; // [rsp+38h] [rbp-41h]
  const unsigned __int16 *v30; // [rsp+38h] [rbp-41h]
  const unsigned __int16 *v31; // [rsp+38h] [rbp-41h]
  const unsigned __int16 *v32; // [rsp+38h] [rbp-41h]
  const unsigned __int16 *v33; // [rsp+40h] [rbp-39h]
  const unsigned __int16 *v34; // [rsp+40h] [rbp-39h]
  const unsigned __int16 *v35; // [rsp+40h] [rbp-39h]
  const unsigned __int16 *v36; // [rsp+40h] [rbp-39h]
  const unsigned __int16 *v37; // [rsp+40h] [rbp-39h]
  const unsigned __int16 *v38; // [rsp+48h] [rbp-31h]
  const unsigned __int16 *v39; // [rsp+48h] [rbp-31h]
  const unsigned __int16 *v40; // [rsp+48h] [rbp-31h]
  const unsigned __int16 *v41; // [rsp+48h] [rbp-31h]
  const unsigned __int16 *v42; // [rsp+48h] [rbp-31h]
  const unsigned __int16 *v43; // [rsp+50h] [rbp-29h]
  const unsigned __int16 *v44; // [rsp+50h] [rbp-29h]
  const unsigned __int16 *v45; // [rsp+50h] [rbp-29h]
  const unsigned __int16 *v46; // [rsp+50h] [rbp-29h]
  const unsigned __int16 *v47; // [rsp+50h] [rbp-29h]
  struct CCacheClientConfig *v48; // [rsp+60h] [rbp-19h] BYREF
  BYTE *lpData; // [rsp+68h] [rbp-11h] BYREF
  __int64 v50; // [rsp+70h] [rbp-9h]
  unsigned __int16 *v51[2]; // [rsp+78h] [rbp-1h] BYREF
  PWSTR ppszPath; // [rsp+88h] [rbp+Fh] BYREF
  HKEY hKey; // [rsp+90h] [rbp+17h] BYREF

  lpData = (BYTE *)&Data;
  v51[0] = (unsigned __int16 *)&Data;
  v48 = 0;
  ppszPath = 0;
  hKey = 0;
  v50 = 0;
  v51[1] = 0;
  Config = UrlCacheGetConfig(&v48);
  if ( Config >= 0 )
  {
    Config = WxValidateCacheDirectory(a1);
    if ( Config >= 0 )
    {
      FileW = CreateFileW(a1, 2u, 0, 0, 3u, 0x2000000u, 0);
      if ( FileW == (HANDLE)-1LL )
      {
        LastError = WxGetLastError();
        Config = LastError;
        if ( LastError > 0 )
          Config = (unsigned __int16)LastError | 0x80070000;
        HIDWORD(v48) = 1808;
        if ( Config >= 0 )
          Config = -2147418113;
      }
      else
      {
        CloseHandle(FileW);
        Config = GetKnownFolderPath((KNOWNFOLDERID *)&FOLDERID_InternetCache, 0x4000u, 0, &ppszPath);
        if ( Config >= 0 )
        {
          Config = SHSetKnownFolderPath(&FOLDERID_InternetCache, 0, 0, a1);
          if ( Config >= 0 )
          {
            Config = WxOpenRegistryKey(
                       HKEY_CURRENT_USER,
                       L"Software\\Microsoft\\Windows\\CurrentVersion\\RunOnce",
                       0xFu,
                       1,
                       &hKey);
            if ( Config >= 0 )
            {
              Config = CWxString::SetPath(
                         (CWxString *)v51,
                         ppszPath,
                         L"Content.IE5",
                         0,
                         dwCreationDisposition,
                         dwFlagsAndAttributes,
                         hTemplateFile,
                         v28,
                         v33,
                         v38,
                         v43);
              if ( Config >= 0 )
              {
                Config = CWxString::Set((CWxString *)&lpData, L"\"%ComSpec%\" /C rd /S /Q \"", v51[0], L"\"");
                if ( Config >= 0 )
                {
                  v5 = RegSetValueExW(hKey, L"DeleteOldCacheContainer", 0, 2u, lpData, 2 * v50 + 2);
                  Config = v5;
                  if ( v5 > 0 )
                    Config = (unsigned __int16)v5 | 0x80070000;
                  if ( Config >= 0 )
                  {
                    Config = CWxString::SetPath(
                               (CWxString *)v51,
                               ppszPath,
                               L"IE",
                               0,
                               dwCreationDispositiona,
                               dwFlagsAndAttributesa,
                               hTemplateFilea,
                               v29,
                               v34,
                               v39,
                               v44);
                    if ( Config >= 0 )
                    {
                      Config = CWxString::Set((CWxString *)&lpData, L"\"%ComSpec%\" /C rd /S /Q \"", v51[0], L"\"");
                      if ( Config >= 0 )
                      {
                        v6 = RegSetValueExW(hKey, L"DeleteOldCacheContainer2", 0, 2u, lpData, 2 * v50 + 2);
                        Config = v6;
                        if ( v6 > 0 )
                          Config = (unsigned __int16)v6 | 0x80070000;
                        if ( Config >= 0 )
                        {
                          Bool = IEConfiguration_GetBool(268435505);
                          v8 = L"counters_devprev.dat";
                          if ( !Bool )
                            v8 = L"counters.dat";
                          Config = CWxString::SetPath(
                                     (CWxString *)v51,
                                     ppszPath,
                                     v8,
                                     0,
                                     dwCreationDispositionb,
                                     dwFlagsAndAttributesb,
                                     hTemplateFileb,
                                     v30,
                                     v35,
                                     v40,
                                     v45);
                          if ( Config >= 0 )
                          {
                            Config = CWxString::Set(
                                       (CWxString *)&lpData,
                                       L"\"%ComSpec%\" /C del /F /Q \"",
                                       v51[0],
                                       L"\"");
                            if ( Config >= 0 )
                            {
                              v9 = RegSetValueExW(hKey, L"DeleteOldCacheCounters", 0, 2u, lpData, 2 * v50 + 2);
                              Config = v9;
                              if ( v9 > 0 )
                                Config = (unsigned __int16)v9 | 0x80070000;
                              if ( Config >= 0 )
                              {
                                Config = CWxString::SetPath(
                                           (CWxString *)v51,
                                           ppszPath,
                                           L"Low",
                                           L"Content.IE5",
                                           dwCreationDispositionc,
                                           dwFlagsAndAttributesc,
                                           hTemplateFilec,
                                           v31,
                                           v36,
                                           v41,
                                           v46);
                                if ( Config >= 0 )
                                {
                                  Config = CWxString::Set(
                                             (CWxString *)&lpData,
                                             L"\"%ComSpec%\" /C rd /S /Q \"",
                                             v51[0],
                                             L"\"");
                                  if ( Config >= 0 )
                                  {
                                    v10 = RegSetValueExW(
                                            hKey,
                                            L"DeleteOldCacheContainerLow",
                                            0,
                                            2u,
                                            lpData,
                                            2 * v50 + 2);
                                    Config = v10;
                                    if ( v10 > 0 )
                                      Config = (unsigned __int16)v10 | 0x80070000;
                                    if ( Config >= 0 )
                                    {
                                      Config = CWxString::SetPath(
                                                 (CWxString *)v51,
                                                 ppszPath,
                                                 L"Low",
                                                 L"IE",
                                                 dwCreationDispositiond,
                                                 dwFlagsAndAttributesd,
                                                 hTemplateFiled,
                                                 v32,
                                                 v37,
                                                 v42,
                                                 v47);
                                      if ( Config >= 0 )
                                      {
                                        Config = CWxString::Set(
                                                   (CWxString *)&lpData,
                                                   L"\"%ComSpec%\" /C rd /S /Q \"",
                                                   v51[0],
                                                   L"\"");
                                        if ( Config >= 0 )
                                        {
                                          v11 = RegSetValueExW(
                                                  hKey,
                                                  L"DeleteOldCacheContainerLow2",
                                                  0,
                                                  2u,
                                                  lpData,
                                                  2 * v50 + 2);
                                          Config = v11;
                                          if ( v11 > 0 )
                                            Config = (unsigned __int16)v11 | 0x80070000;
                                          if ( Config >= 0 )
                                          {
                                            if ( hKey )
                                            {
                                              RegCloseKey(hKey);
                                              hKey = 0;
                                            }
                                          }
                                          else
                                          {
                                            HIDWORD(v48) = 1869;
                                          }
                                        }
                                        else
                                        {
                                          HIDWORD(v48) = 1863;
                                        }
                                      }
                                      else
                                      {
                                        HIDWORD(v48) = 1862;
                                      }
                                    }
                                    else
                                    {
                                      HIDWORD(v48) = 1860;
                                    }
                                  }
                                  else
                                  {
                                    HIDWORD(v48) = 1854;
                                  }
                                }
                                else
                                {
                                  HIDWORD(v48) = 1853;
                                }
                              }
                              else
                              {
                                HIDWORD(v48) = 1851;
                              }
                            }
                            else
                            {
                              HIDWORD(v48) = 1845;
                            }
                          }
                          else
                          {
                            HIDWORD(v48) = 1844;
                          }
                        }
                        else
                        {
                          HIDWORD(v48) = 1842;
                        }
                      }
                      else
                      {
                        HIDWORD(v48) = 1836;
                      }
                    }
                    else
                    {
                      HIDWORD(v48) = 1835;
                    }
                  }
                  else
                  {
                    HIDWORD(v48) = 1833;
                  }
                }
                else
                {
                  HIDWORD(v48) = 1827;
                }
              }
              else
              {
                HIDWORD(v48) = 1826;
              }
            }
            else
            {
              HIDWORD(v48) = 1824;
            }
          }
          else
          {
            HIDWORD(v48) = 1819;
          }
        }
        else
        {
          HIDWORD(v48) = 1814;
        }
      }
    }
    else
    {
      HIDWORD(v48) = 1806;
    }
  }
  else
  {
    HIDWORD(v48) = 1801;
  }
  WxCoTaskMemFree<unsigned short>(&ppszPath);
  CWxString::_Release((CWxString *)v51);
  CWxString::_Release((CWxString *)&lpData);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  return (unsigned int)Config;
}

```

## disassembly

```asm
0x1801468d0  push    rbp
0x1801468d2  push    rbx
0x1801468d3  push    rsi
0x1801468d4  push    rdi
0x1801468d5  push    r12
0x1801468d7  push    r15
0x1801468d9  lea     rbp, [rsp-2Fh]
0x1801468de  sub     rsp, 0A8h
0x1801468e5  mov     rax, cs:__security_cookie
0x1801468ec  xor     rax, rsp
0x1801468ef  mov     [rbp+57h+var_38], rax
0x1801468f3  lea     rax, Data
0x1801468fa  mov     dword ptr [rbp+57h+var_70+4], 0
0x180146901  mov     rsi, rcx
0x180146904  mov     [rbp+57h+lpData], rax
0x180146908  lea     rcx, [rbp+57h+var_70]; struct CCacheClientConfig **
0x18014690c  mov     [rbp+57h+var_58], rax
0x180146910  mov     [rbp+57h+var_70], 0
0x180146918  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18014691c  mov     [rbp+57h+ppszPath], 0
0x180146924  mov     [rbp+57h+hKey], 0
0x18014692c  mov     [rbp+57h+var_60], 0
0x180146934  mov     [rbp+57h+var_50], 0
0x18014693c  call    ?UrlCacheGetConfig@@YAJPEAPEAVCCacheClientConfig@@@Z; UrlCacheGetConfig(CCacheClientConfig * *)
0x180146941  mov     edi, eax
0x180146943  test    eax, eax
0x180146945  jns     short loc_180146953
0x180146947  mov     dword ptr [rbp+57h+var_70+4], 709h
0x18014694e  jmp     loc_180146DA9
0x180146953  mov     rcx, rsi; unsigned __int16 *
0x180146956  call    ?WxValidateCacheDirectory@@YAJPEBG@Z; WxValidateCacheDirectory(ushort const *)
0x18014695b  mov     edi, eax
0x18014695d  test    eax, eax
0x18014695f  jns     short loc_18014696D
0x180146961  mov     dword ptr [rbp+57h+var_70+4], 70Eh
0x180146968  jmp     loc_180146DA9
0x18014696d  xor     r9d, r9d; lpSecurityAttributes
0x180146970  mov     [rsp+0D0h+hTemplateFile], 0; unsigned __int16 *
0x180146979  mov     dword ptr [rsp+0D0h+dwFlagsAndAttributes], 2000000h; unsigned __int16 *
0x180146981  xor     r8d, r8d; dwShareMode
0x180146984  mov     rcx, rsi; lpFileName
0x180146987  mov     [rsp+0D0h+dwCreationDisposition], 3; dwCreationDisposition
0x18014698f  lea     r12d, [r9+2]
0x180146993  mov     edx, r12d; dwDesiredAccess
0x180146996  call    cs:__imp_CreateFileW
0x18014699c  mov     rbx, rax
0x18014699f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801469a3  jnz     short loc_1801469CF
0x1801469a5  call    WxGetLastError
0x1801469aa  mov     edi, eax
0x1801469ac  test    eax, eax
0x1801469ae  jle     short loc_1801469B9
0x1801469b0  movzx   edi, ax
0x1801469b3  or      edi, 80070000h
0x1801469b9  test    edi, edi
0x1801469bb  mov     dword ptr [rbp+57h+var_70+4], 710h
0x1801469c2  mov     eax, 8000FFFFh
0x1801469c7  cmovns  edi, eax
0x1801469ca  jmp     loc_180146DA9
0x1801469cf  mov     rcx, rax; hObject
0x1801469d2  call    cs:__imp_CloseHandle
0x1801469d8  lea     r9, [rbp+57h+ppszPath]; ppszPath
0x1801469dc  xor     r8d, r8d; hToken
0x1801469df  mov     edx, 4000h; dwFlags
0x1801469e4  lea     rcx, FOLDERID_InternetCache; rfid
0x1801469eb  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1801469ef  call    ?GetKnownFolderPath@@YAJAEBU_GUID@@KPEAXPEAPEAG@Z; GetKnownFolderPath(_GUID const &,ulong,void *,ushort * *)
0x1801469f4  mov     edi, eax
0x1801469f6  test    eax, eax
0x1801469f8  jns     short loc_180146A06
0x1801469fa  mov     dword ptr [rbp+57h+var_70+4], 716h
0x180146a01  jmp     loc_180146DA9
0x180146a06  mov     r9, rsi; pszPath
0x180146a09  lea     rcx, FOLDERID_InternetCache; rfid
0x180146a10  xor     r8d, r8d; hToken
0x180146a13  xor     edx, edx; dwFlags
0x180146a15  call    cs:__imp_SHSetKnownFolderPath
0x180146a1b  mov     edi, eax
0x180146a1d  test    eax, eax
0x180146a1f  jns     short loc_180146A2D
0x180146a21  mov     dword ptr [rbp+57h+var_70+4], 71Bh
0x180146a28  jmp     loc_180146DA9
0x180146a2d  mov     r9d, 1; int
0x180146a33  lea     rax, [rbp+57h+hKey]
0x180146a37  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180146a3e  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rax; unsigned __int16 *
0x180146a43  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180146a4a  lea     r8d, [r9+0Eh]; samDesired
0x180146a4e  call    ?WxOpenRegistryKey@@YAJPEAUHKEY__@@PEBGKHPEAPEAU1@@Z; WxOpenRegistryKey(HKEY__ *,ushort const *,ulong,int,HKEY__ * *)
0x180146a53  mov     edi, eax
0x180146a55  test    eax, eax
0x180146a57  jns     short loc_180146A65
0x180146a59  mov     dword ptr [rbp+57h+var_70+4], 720h
0x180146a60  jmp     loc_180146DA9
0x180146a65  mov     rdx, [rbp+57h+ppszPath]; unsigned __int16 *
0x180146a69  lea     r8, aContentIe5; "Content.IE5"
0x180146a70  xor     r9d, r9d; unsigned __int16 *
0x180146a73  lea     rcx, [rbp+57h+var_58]; this
0x180146a77  call    ?SetPath@CWxString@@QEAAJPEBG000000000@Z; CWxString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180146a7c  mov     edi, eax
0x180146a7e  test    eax, eax
0x180146a80  jns     short loc_180146A8E
0x180146a82  mov     dword ptr [rbp+57h+var_70+4], 722h
0x180146a89  jmp     loc_180146DA9
0x180146a8e  mov     r8, [rbp+57h+var_58]; unsigned __int16 *
0x180146a92  lea     r15, asc_180238C6C; "\""
0x180146a99  mov     r9, r15; unsigned __int16 *
0x180146a9c  lea     rdx, aComspecCRdSQ; "\"%ComSpec%\" /C rd /S /Q \""
0x180146aa3  lea     rcx, [rbp+57h+lpData]; this
0x180146aa7  call    ?Set@CWxString@@QEAAJPEBG00@Z; CWxString::Set(ushort const *,ushort const *,ushort const *)
0x180146aac  mov     edi, eax
0x180146aae  test    eax, eax
0x180146ab0  jns     short loc_180146ABE
0x180146ab2  mov     dword ptr [rbp+57h+var_70+4], 723h
0x180146ab9  jmp     loc_180146DA9
0x180146abe  mov     eax, dword ptr [rbp+57h+var_60]
0x180146ac1  lea     rdx, aDeleteoldcache_3; "DeleteOldCacheContainer"
0x180146ac8  mov     rcx, [rbp+57h+hKey]; hKey
0x180146acc  mov     r9d, r12d; dwType
0x180146acf  xor     r8d, r8d; Reserved
0x180146ad2  lea     eax, ds:2[rax*2]
0x180146ad9  mov     dword ptr [rsp+0D0h+dwFlagsAndAttributes], eax; unsigned __int16 *
0x180146add  mov     rax, [rbp+57h+lpData]
0x180146ae1  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rax; unsigned __int16 *
0x180146ae6  call    cs:__imp_RegSetValueExW
0x180146aec  mov     edi, eax
0x180146aee  mov     esi, 80070000h
0x180146af3  test    eax, eax
0x180146af5  jle     short loc_180146AFC
0x180146af7  movzx   edi, ax
0x180146afa  or      edi, esi
0x180146afc  test    edi, edi
0x180146afe  jns     short loc_180146B0C
0x180146b00  mov     dword ptr [rbp+57h+var_70+4], 729h
0x180146b07  jmp     loc_180146DA9
0x180146b0c  mov     rdx, [rbp+57h+ppszPath]; unsigned __int16 *
0x180146b10  lea     r8, aIe; "IE"
0x180146b17  xor     r9d, r9d; unsigned __int16 *
0x180146b1a  lea     rcx, [rbp+57h+var_58]; this
0x180146b1e  call    ?SetPath@CWxString@@QEAAJPEBG000000000@Z; CWxString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180146b23  mov     edi, eax
0x180146b25  test    eax, eax
0x180146b27  jns     short loc_180146B35
0x180146b29  mov     dword ptr [rbp+57h+var_70+4], 72Bh
0x180146b30  jmp     loc_180146DA9
0x180146b35  mov     r8, [rbp+57h+var_58]; unsigned __int16 *
0x180146b39  lea     rdx, aComspecCRdSQ; "\"%ComSpec%\" /C rd /S /Q \""
0x180146b40  mov     r9, r15; unsigned __int16 *
0x180146b43  lea     rcx, [rbp+57h+lpData]; this
0x180146b47  call    ?Set@CWxString@@QEAAJPEBG00@Z; CWxString::Set(ushort const *,ushort const *,ushort const *)
0x180146b4c  mov     edi, eax
0x180146b4e  test    eax, eax
0x180146b50  jns     short loc_180146B5E
0x180146b52  mov     dword ptr [rbp+57h+var_70+4], 72Ch
0x180146b59  jmp     loc_180146DA9
0x180146b5e  mov     eax, dword ptr [rbp+57h+var_60]
0x180146b61  lea     rdx, aDeleteoldcache_0; "DeleteOldCacheContainer2"
0x180146b68  mov     rcx, [rbp+57h+hKey]; hKey
0x180146b6c  mov     r9d, r12d; dwType
0x180146b6f  xor     r8d, r8d; Reserved
0x180146b72  lea     eax, ds:2[rax*2]
0x180146b79  mov     dword ptr [rsp+0D0h+dwFlagsAndAttributes], eax; unsigned __int16 *
0x180146b7d  mov     rax, [rbp+57h+lpData]
0x180146b81  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rax; unsigned __int16 *
0x180146b86  call    cs:__imp_RegSetValueExW
0x180146b8c  mov     edi, eax
0x180146b8e  test    eax, eax
0x180146b90  jle     short loc_180146B97
0x180146b92  movzx   edi, ax
0x180146b95  or      edi, esi
0x180146b97  test    edi, edi
0x180146b99  jns     short loc_180146BA7
0x180146b9b  mov     dword ptr [rbp+57h+var_70+4], 732h
0x180146ba2  jmp     loc_180146DA9
0x180146ba7  mov     ecx, 10000031h
0x180146bac  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180146bb2  mov     rdx, [rbp+57h+ppszPath]; unsigned __int16 *
0x180146bb6  lea     rcx, aCountersDat; "counters.dat"
0x180146bbd  test    al, al
0x180146bbf  lea     r8, aCountersDevpre; "counters_devprev.dat"
0x180146bc6  cmovz   r8, rcx; unsigned __int16 *
0x180146bca  xor     r9d, r9d; unsigned __int16 *
0x180146bcd  lea     rcx, [rbp+57h+var_58]; this
0x180146bd1  call    ?SetPath@CWxString@@QEAAJPEBG000000000@Z; CWxString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180146bd6  mov     edi, eax
0x180146bd8  test    eax, eax
0x180146bda  jns     short loc_180146BE8
0x180146bdc  mov     dword ptr [rbp+57h+var_70+4], 734h
0x180146be3  jmp     loc_180146DA9
0x180146be8  mov     r8, [rbp+57h+var_58]; unsigned __int16 *
0x180146bec  lea     rdx, aComspecCDelFQ; "\"%ComSpec%\" /C del /F /Q \""
0x180146bf3  mov     r9, r15; unsigned __int16 *
0x180146bf6  lea     rcx, [rbp+57h+lpData]; this
0x180146bfa  call    ?Set@CWxString@@QEAAJPEBG00@Z; CWxString::Set(ushort const *,ushort const *,ushort const *)
0x180146bff  mov     edi, eax
0x180146c01  test    eax, eax
0x180146c03  jns     short loc_180146C11
0x180146c05  mov     dword ptr [rbp+57h+var_70+4], 735h
0x180146c0c  jmp     loc_180146DA9
0x180146c11  mov     eax, dword ptr [rbp+57h+var_60]
0x180146c14  lea     rdx, aDeleteoldcache_2; "DeleteOldCacheCounters"
0x180146c1b  mov     rcx, [rbp+57h+hKey]; hKey
0x180146c1f  mov     r9d, r12d; dwType
0x180146c22  xor     r8d, r8d; Reserved
0x180146c25  lea     eax, ds:2[rax*2]
0x180146c2c  mov     dword ptr [rsp+0D0h+dwFlagsAndAttributes], eax; unsigned __int16 *
0x180146c30  mov     rax, [rbp+57h+lpData]
0x180146c34  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rax; unsigned __int16 *
0x180146c39  call    cs:__imp_RegSetValueExW
0x180146c3f  mov     edi, eax
0x180146c41  test    eax, eax
0x180146c43  jle     short loc_180146C4A
0x180146c45  movzx   edi, ax
0x180146c48  or      edi, esi
0x180146c4a  test    edi, edi
0x180146c4c  jns     short loc_180146C5A
0x180146c4e  mov     dword ptr [rbp+57h+var_70+4], 73Bh
0x180146c55  jmp     loc_180146DA9
0x180146c5a  mov     rdx, [rbp+57h+ppszPath]; unsigned __int16 *
0x180146c5e  lea     r9, aContentIe5; "Content.IE5"
0x180146c65  lea     r8, String1; "Low"
0x180146c6c  lea     rcx, [rbp+57h+var_58]; this
0x180146c70  call    ?SetPath@CWxString@@QEAAJPEBG000000000@Z; CWxString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180146c75  mov     edi, eax
0x180146c77  test    eax, eax
0x180146c79  jns     short loc_180146C87
0x180146c7b  mov     dword ptr [rbp+57h+var_70+4], 73Dh
0x180146c82  jmp     loc_180146DA9
0x180146c87  mov     r8, [rbp+57h+var_58]; unsigned __int16 *
0x180146c8b  lea     rdx, aComspecCRdSQ; "\"%ComSpec%\" /C rd /S /Q \""
0x180146c92  mov     r9, r15; unsigned __int16 *
0x180146c95  lea     rcx, [rbp+57h+lpData]; this
0x180146c99  call    ?Set@CWxString@@QEAAJPEBG00@Z; CWxString::Set(ushort const *,ushort const *,ushort const *)
0x180146c9e  mov     edi, eax
0x180146ca0  test    eax, eax
0x180146ca2  jns     short loc_180146CB0
0x180146ca4  mov     dword ptr [rbp+57h+var_70+4], 73Eh
0x180146cab  jmp     loc_180146DA9
0x180146cb0  mov     eax, dword ptr [rbp+57h+var_60]
0x180146cb3  lea     rdx, aDeleteoldcache; "DeleteOldCacheContainerLow"
0x180146cba  mov     rcx, [rbp+57h+hKey]; hKey
0x180146cbe  mov     r9d, r12d; dwType
0x180146cc1  xor     r8d, r8d; Reserved
0x180146cc4  lea     eax, ds:2[rax*2]
0x180146ccb  mov     dword ptr [rsp+0D0h+dwFlagsAndAttributes], eax; unsigned __int16 *
0x180146ccf  mov     rax, [rbp+57h+lpData]
0x180146cd3  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rax; unsigned __int16 *
0x180146cd8  call    cs:__imp_RegSetValueExW
0x180146cde  mov     edi, eax
0x180146ce0  test    eax, eax
0x180146ce2  jle     short loc_180146CE9
0x180146ce4  movzx   edi, ax
0x180146ce7  or      edi, esi
0x180146ce9  test    edi, edi
0x180146ceb  jns     short loc_180146CF9
0x180146ced  mov     dword ptr [rbp+57h+var_70+4], 744h
0x180146cf4  jmp     loc_180146DA9
0x180146cf9  mov     rdx, [rbp+57h+ppszPath]; unsigned __int16 *
0x180146cfd  lea     r9, aIe; "IE"
0x180146d04  lea     r8, String1; "Low"
0x180146d0b  lea     rcx, [rbp+57h+var_58]; this
0x180146d0f  call    ?SetPath@CWxString@@QEAAJPEBG000000000@Z; CWxString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180146d14  mov     edi, eax
0x180146d16  test    eax, eax
0x180146d18  jns     short loc_180146D26
0x180146d1a  mov     dword ptr [rbp+57h+var_70+4], 746h
0x180146d21  jmp     loc_180146DA9
0x180146d26  mov     r8, [rbp+57h+var_58]; unsigned __int16 *
0x180146d2a  lea     rdx, aComspecCRdSQ; "\"%ComSpec%\" /C rd /S /Q \""
0x180146d31  mov     r9, r15; unsigned __int16 *
0x180146d34  lea     rcx, [rbp+57h+lpData]; this
0x180146d38  call    ?Set@CWxString@@QEAAJPEBG00@Z; CWxString::Set(ushort const *,ushort const *,ushort const *)
0x180146d3d  mov     edi, eax
0x180146d3f  test    eax, eax
0x180146d41  jns     short loc_180146D4C
0x180146d43  mov     dword ptr [rbp+57h+var_70+4], 747h
0x180146d4a  jmp     short loc_180146DA9
0x180146d4c  mov     eax, dword ptr [rbp+57h+var_60]
0x180146d4f  lea     rdx, aDeleteoldcache_1; "DeleteOldCacheContainerLow2"
0x180146d56  mov     rcx, [rbp+57h+hKey]; hKey
0x180146d5a  mov     r9d, r12d; dwType
0x180146d5d  xor     r8d, r8d; Reserved
0x180146d60  lea     eax, ds:2[rax*2]
0x180146d67  mov     dword ptr [rsp+0D0h+dwFlagsAndAttributes], eax; cbData
0x180146d6b  mov     rax, [rbp+57h+lpData]
0x180146d6f  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rax; lpData
0x180146d74  call    cs:__imp_RegSetValueExW
0x180146d7a  mov     edi, eax
0x180146d7c  test    eax, eax
0x180146d7e  jle     short loc_180146D85
0x180146d80  movzx   edi, ax
0x180146d83  or      edi, esi
0x180146d85  test    edi, edi
0x180146d87  jns     short loc_180146D92
0x180146d89  mov     dword ptr [rbp+57h+var_70+4], 74Dh
0x180146d90  jmp     short loc_180146DA9
0x180146d92  mov     rcx, [rbp+57h+hKey]; hKey
0x180146d96  test    rcx, rcx
0x180146d99  jz      short loc_180146DA9
0x180146d9b  call    cs:__imp_RegCloseKey
  ... truncated ...
```
