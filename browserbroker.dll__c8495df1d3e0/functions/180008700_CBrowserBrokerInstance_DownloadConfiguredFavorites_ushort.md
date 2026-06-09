# CBrowserBrokerInstance::DownloadConfiguredFavorites(ushort * *)

- ea: `0x180008700`
- end: `0x18000887e`
- name: `?DownloadConfiguredFavorites@CBrowserBrokerInstance@@UEAAJPEAPEAG@Z`
- size: `382`
- prototype: `int(CBrowserBrokerInstance *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x180002ce0`
- `0x1800037ac`
- `0x180006c90`
- `0x180008700`
- `0x18000e428`
- `0x18001b980`
- `0x18001bc54`
- `0x18001bd78`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z` at `0x1800087bc`
- `iertutil!__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z` at `0x1800087bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000880f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000880f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180008805`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180008805`
- `urlmon!UrlmonCleanupCurrentThread` at `0x1800087a9`
- `urlmon!UrlmonCleanupCurrentThread` at `0x1800087a9`
- `urlmon!URLDownloadToCacheFileW` at `0x1800087a1`
- `urlmon!URLDownloadToCacheFileW` at `0x1800087a1`
- `profapi!__imp_GetAppContainerPath` at `0x1800087d2`
- `profapi!__imp_GetAppContainerPath` at `0x1800087d2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CBrowserBrokerInstance::DownloadConfiguredFavorites(
        CBrowserBrokerInstance *this,
        unsigned __int16 **a2)
{
  int PIC; // ebx
  __int64 String; // rax
  __int64 v5; // r8
  signed int LastError; // eax
  LPCWSTR lpPathName; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR v9; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR ExistingFileName[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pszPathIn[264]; // [rsp+250h] [rbp+150h] BYREF

  LODWORD(lpPathName) = 0;
  PIC = BrokerAuthenticateAttachedCallerGetPIC(1, (unsigned int *)&lpPathName);
  if ( PIC >= 0 )
  {
    v9 = 0;
    PIC = GetProcessedConfiguredFavoritesUrl((LPWSTR *)&v9);
    if ( PIC >= 0 )
    {
      memset_0(ExistingFileName, 0, 0x208u);
      PIC = URLDownloadToCacheFileW(0, v9, ExistingFileName, 0x104u, 0, 0);
      UrlmonCleanupCurrentThread();
      if ( PIC >= 0 )
      {
        String = IEConfiguration_GetString(268435506);
        PIC = GetAppContainerPath(String, pszPathIn, 260);
        if ( PIC >= 0 )
        {
          lpPathName = 0;
          PIC = GetAppContainerPathToProvisionFavorites(pszPathIn, (unsigned __int16 **)&lpPathName);
          if ( PIC >= 0 )
          {
            if ( CreateDirectoryW(lpPathName, 0) )
              goto LABEL_11;
            LastError = GetLastError();
            PIC = LastError;
            if ( LastError == 183 )
              goto LABEL_11;
            if ( LastError > 0 )
              PIC = (unsigned __int16)LastError | 0x80070000;
            if ( PIC >= 0 )
LABEL_11:
              PIC = CopyFiles(ExistingFileName, lpPathName, v5, a2);
          }
          CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((void **)&lpPathName);
        }
      }
    }
    CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((void **)&v9);
  }
  return (unsigned int)PIC;
}

```

## disassembly

```asm
0x180008700  mov     [rsp-8+arg_0], rbx
0x180008705  mov     [rsp-8+arg_10], rdi
0x18000870a  push    rbp
0x18000870b  lea     rbp, [rsp-370h]
0x180008713  sub     rsp, 470h
0x18000871a  mov     rax, cs:__security_cookie
0x180008721  xor     rax, rsp
0x180008724  mov     [rbp+370h+var_10], rax
0x18000872b  mov     rdi, rdx
0x18000872e  mov     dword ptr [rsp+470h+lpPathName], 0
0x180008736  lea     rdx, [rsp+470h+lpPathName]; unsigned int *
0x18000873b  mov     ecx, 1; unsigned int
0x180008740  call    ?BrokerAuthenticateAttachedCallerGetPIC@@YAJKPEAK@Z; BrokerAuthenticateAttachedCallerGetPIC(ulong,ulong *)
0x180008745  mov     ebx, eax
0x180008747  test    eax, eax
0x180008749  js      loc_180008858
0x18000874f  mov     [rsp+470h+var_438], 0
0x180008758  lea     rcx, [rsp+470h+var_438]; ppwsz
0x18000875d  call    ?GetProcessedConfiguredFavoritesUrl@@YAJPEAPEAG@Z; GetProcessedConfiguredFavoritesUrl(ushort * *)
0x180008762  mov     ebx, eax
0x180008764  test    eax, eax
0x180008766  js      loc_18000884E
0x18000876c  xor     edx, edx; Val
0x18000876e  mov     r8d, 208h; Size
0x180008774  lea     rcx, [rsp+470h+ExistingFileName]; void *
0x180008779  call    memset_0
0x18000877e  mov     [rsp+470h+var_448], 0; LPBINDSTATUSCALLBACK
0x180008787  mov     [rsp+470h+var_450], 0; DWORD
0x18000878f  mov     r9d, 104h; cchFileName
0x180008795  lea     r8, [rsp+470h+ExistingFileName]; LPWSTR
0x18000879a  mov     rdx, [rsp+470h+var_438]; LPCWSTR
0x18000879f  xor     ecx, ecx; LPUNKNOWN
0x1800087a1  call    cs:__imp_URLDownloadToCacheFileW
0x1800087a7  mov     ebx, eax
0x1800087a9  call    cs:__imp_UrlmonCleanupCurrentThread
0x1800087af  test    ebx, ebx
0x1800087b1  js      loc_18000884E
0x1800087b7  mov     ecx, 10000032h
0x1800087bc  call    cs:__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z; IEConfiguration_GetString(IEConfigurationID)
0x1800087c2  mov     rcx, rax
0x1800087c5  mov     r8d, 104h
0x1800087cb  lea     rdx, [rbp+370h+pszPathIn]
0x1800087d2  call    cs:__imp_GetAppContainerPath
0x1800087d8  mov     ebx, eax
0x1800087da  test    eax, eax
0x1800087dc  js      short loc_18000884E
0x1800087de  mov     [rsp+470h+lpPathName], 0
0x1800087e7  lea     rdx, [rsp+470h+lpPathName]; unsigned __int16 **
0x1800087ec  lea     rcx, [rbp+370h+pszPathIn]; pszPathIn
0x1800087f3  call    ?GetAppContainerPathToProvisionFavorites@@YAJPEBGPEAPEAG@Z; GetAppContainerPathToProvisionFavorites(ushort const *,ushort * *)
0x1800087f8  mov     ebx, eax
0x1800087fa  test    eax, eax
0x1800087fc  js      short loc_180008843
0x1800087fe  xor     edx, edx; lpSecurityAttributes
0x180008800  mov     rcx, [rsp+470h+lpPathName]; lpPathName
0x180008805  call    cs:__imp_CreateDirectoryW
0x18000880b  test    eax, eax
0x18000880d  jnz     short loc_18000882F
0x18000880f  call    cs:__imp_GetLastError
0x180008815  mov     ebx, eax
0x180008817  cmp     eax, 0B7h
0x18000881c  jz      short loc_18000882F
0x18000881e  test    eax, eax
0x180008820  jle     short loc_18000882B
0x180008822  movzx   ebx, ax
0x180008825  or      ebx, 80070000h
0x18000882b  test    ebx, ebx
0x18000882d  js      short loc_180008843
0x18000882f  mov     r9, rdi; unsigned __int16 **
0x180008832  mov     rdx, [rsp+470h+lpPathName]; lpPathName
0x180008837  lea     rcx, [rsp+470h+ExistingFileName]; lpExistingFileName
0x18000883c  call    ?CopyFiles@@YAJPEBG0KPEAPEAG@Z; CopyFiles(ushort const *,ushort const *,ulong,ushort * *)
0x180008841  mov     ebx, eax
0x180008843  lea     rcx, [rsp+470h+lpPathName]
0x180008848  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18000884d  nop
0x18000884e  lea     rcx, [rsp+470h+var_438]
0x180008853  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180008858  mov     eax, ebx
0x18000885a  mov     rcx, [rbp+370h+var_10]
0x180008861  xor     rcx, rsp; StackCookie
0x180008864  call    __security_check_cookie
0x180008869  lea     r11, [rsp+470h+var_s0]
0x180008871  mov     rbx, [r11+10h]
0x180008875  mov     rdi, [r11+20h]
0x180008879  mov     rsp, r11
0x18000887c  pop     rbp
0x18000887d  retn
```
