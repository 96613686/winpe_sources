# StorageService::ProvisionForAppInstall(_STORAGE_DEVICE_TYPE,ulong)

- ea: `0x180027858`
- end: `0x180027b25`
- name: `?ProvisionForAppInstall@StorageService@@QEAAJW4_STORAGE_DEVICE_TYPE@@K@Z`
- size: `717`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, reparse_path, registry_config, service_task, installer_update`

## callers

- `0x1800378b0`

## callees

- `0x180001548`
- `0x18000d030`
- `0x180012c9c`
- `0x180012ce0`
- `0x18001bb98`
- `0x18001fcf8`
- `0x18001fdd8`
- `0x18001ff14`
- `0x180020450`
- `0x18002113c`
- `0x180022de0`
- `0x180022eec`
- `0x180023bac`
- `0x180027858`
- `0x180029494`
- `0x1800298cc`
- `0x180029ee4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800279a4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800279a4`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180027981`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180027981`
- `FLTLIB!FilterAttach` at `0x180027a1a`
- `FLTLIB!FilterAttach` at `0x180027a1a`

## pseudocode

```c
__int64 __fastcall StorageService::ProvisionForAppInstall(__int64 a1, unsigned int a2, __int64 a3)
{
  __int64 v3; // rdi
  int ActiveDeviceInstance; // ebx
  __int64 v5; // rsi
  char AppPairingStatus; // al
  StorageService *v7; // rcx
  __int64 v8; // r14
  unsigned int v9; // r11d
  StorageService *v10; // rcx
  int v11; // r9d
  __int64 v12; // rcx
  StorageService *v13; // rcx
  bool v14; // r8
  _DWORD v16[4]; // [rsp+40h] [rbp-C0h] BYREF
  GUID rguid; // [rsp+50h] [rbp-B0h] BYREF
  struct _GUID v18; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR pszPath[264]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v20[264]; // [rsp+280h] [rbp+180h] BYREF

  v3 = (int)a2;
  v16[0] = a3;
  v18 = 0;
  ActiveDeviceInstance = StorageService::GetActiveDeviceInstance(&g_StorageService, a2, a3, v16);
  if ( ActiveDeviceInstance < 0 )
    return (unsigned int)ActiveDeviceInstance;
  v5 = v16[0];
  ActiveDeviceInstance = StorageService::CheckDeviceId(&g_StorageService, (unsigned int)v3, v16[0]);
  if ( ActiveDeviceInstance < 0 )
    return (unsigned int)ActiveDeviceInstance;
  if ( !(_DWORD)v3 && !(_DWORD)v5 )
    return (unsigned int)-2147024809;
  AppPairingStatus = StorageService::GetAppPairingStatus(&g_StorageService, (unsigned int)v3, (unsigned int)v5);
  if ( (AppPairingStatus & 1) != 0 )
  {
    ActiveDeviceInstance = StorageService::CleanUpDifferentPairedDevice(
                             &g_StorageService,
                             (unsigned int)v3,
                             (unsigned int)v5);
    if ( ActiveDeviceInstance < 0 )
      return (unsigned int)ActiveDeviceInstance;
LABEL_10:
    ActiveDeviceInstance = StorageService::GetDeviceAppPairingId(v7, &v18);
    if ( ActiveDeviceInstance < 0 )
      return (unsigned int)ActiveDeviceInstance;
    ActiveDeviceInstance = StorageService::SetStorageCardAppMetadata(
                             &g_StorageService,
                             (unsigned int)v3,
                             (unsigned int)v5,
                             &v18);
    if ( ActiveDeviceInstance < 0 )
      return (unsigned int)ActiveDeviceInstance;
    goto LABEL_12;
  }
  if ( (AppPairingStatus & 4) != 0 )
    goto LABEL_10;
LABEL_12:
  v8 = 1112 * v5;
  ActiveDeviceInstance = StringCchCopyW(
                           pszPath,
                           0x104u,
                           (const wchar_t *)(*((_QWORD *)&g_StorageService + v3 + 5) + 1112 * v5 + 4));
  if ( ActiveDeviceInstance >= 0 )
  {
    ActiveDeviceInstance = PathCchAppend(pszPath, v9, L"WindowsApps");
    if ( ActiveDeviceInstance >= 0 )
    {
      if ( !StorageService::DirectoryIsReparsePoint(v10, pszPath) || DeleteFileW(pszPath) )
      {
        ActiveDeviceInstance = StorageService::CreateStorageCardDirectory(
                                 (StorageService *)&g_StorageService,
                                 v3,
                                 v5,
                                 (__int64)L"WindowsApps",
                                 1,
                                 0,
                                 0,
                                 0);
        if ( ActiveDeviceInstance >= 0 )
        {
          ActiveDeviceInstance = FilterAttach(
                                   L"Filecrypt",
                                   (LPCWSTR)(v8 + *((_QWORD *)&g_StorageService + v3 + 5) + 4LL),
                                   0,
                                   0,
                                   0);
          if ( (int)(ActiveDeviceInstance + 0x80000000) < 0 || ActiveDeviceInstance == -2145452014 )
          {
            StorageService::SetAppPairingStatus(&g_StorageService, (unsigned int)v3, (unsigned int)v5, 2);
            StorageService::SetStorageCardPowerPolicy(&g_StorageService, (unsigned int)v3, (unsigned int)v5);
            ActiveDeviceInstance = StringCchPrintfW(
                                     v20,
                                     0x104u,
                                     L"\\\\.\\%c:",
                                     *(unsigned __int16 *)(*((_QWORD *)&g_StorageService + v3 + 5) + v8 + 4));
            if ( ActiveDeviceInstance >= 0 )
            {
              rguid = *(GUID *)(*((_QWORD *)&g_StorageService + v3 + 5) + v8 + 548);
              SetStorageCardWriteBackCache(v20, &rguid, v14);
            }
            StorageService::ChangeServiceStartSettings(v13);
          }
          else if ( (unsigned int)dword_1800BF000 > 5 )
          {
            v12 = *((_QWORD *)&g_StorageService + v3 + 5) + 4LL;
            v16[0] = ActiveDeviceInstance;
            *(_QWORD *)&rguid.Data1 = v8 + v12;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_1800BF000,
              (unsigned int)byte_1800A5BC3,
              0,
              v11,
              (__int64)&rguid,
              (__int64)v16);
          }
        }
      }
      else
      {
        return (unsigned int)-2147024814;
      }
    }
  }
  return (unsigned int)ActiveDeviceInstance;
}

```

## disassembly

```asm
0x180027858  mov     [rsp-8+arg_0], rbx
0x18002785d  mov     [rsp-8+arg_18], rsi
0x180027862  push    rbp
0x180027863  push    rdi
0x180027864  push    r13
0x180027866  push    r14
0x180027868  push    r15
0x18002786a  lea     rbp, [rsp-3A0h]
0x180027872  sub     rsp, 4A0h
0x180027879  mov     rax, cs:__security_cookie
0x180027880  xor     rax, rsp
0x180027883  mov     [rbp+3C0h+var_30], rax
0x18002788a  movsxd  rdi, edx
0x18002788d  lea     r13, ?g_StorageService@@3VStorageService@@A; StorageService g_StorageService
0x180027894  xorps   xmm0, xmm0
0x180027897  mov     [rsp+4C0h+var_480], r8d
0x18002789c  mov     edx, edi
0x18002789e  lea     r9, [rsp+4C0h+var_480]
0x1800278a3  mov     rcx, r13
0x1800278a6  movups  xmmword ptr [rsp+4C0h+var_460.Data1], xmm0
0x1800278ab  call    ?GetActiveDeviceInstance@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@KPEAK@Z; StorageService::GetActiveDeviceInstance(_STORAGE_DEVICE_TYPE,ulong,ulong *)
0x1800278b0  mov     ebx, eax
0x1800278b2  test    eax, eax
0x1800278b4  js      loc_180027AF8
0x1800278ba  mov     esi, [rsp+4C0h+var_480]
0x1800278be  mov     edx, edi
0x1800278c0  mov     r8d, esi
0x1800278c3  mov     rcx, r13
0x1800278c6  call    ?CheckDeviceId@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@K@Z; StorageService::CheckDeviceId(_STORAGE_DEVICE_TYPE,ulong)
0x1800278cb  mov     ebx, eax
0x1800278cd  test    eax, eax
0x1800278cf  js      loc_180027AF8
0x1800278d5  test    edi, edi
0x1800278d7  jnz     short loc_1800278E7
0x1800278d9  test    esi, esi
0x1800278db  jnz     short loc_1800278E7
0x1800278dd  mov     ebx, 80070057h
0x1800278e2  jmp     loc_180027AF8
0x1800278e7  mov     r8d, esi
0x1800278ea  mov     edx, edi
0x1800278ec  mov     rcx, r13
0x1800278ef  call    ?GetAppPairingStatus@StorageService@@IEAAKW4_STORAGE_DEVICE_TYPE@@K@Z; StorageService::GetAppPairingStatus(_STORAGE_DEVICE_TYPE,ulong)
0x1800278f4  test    al, 1
0x1800278f6  jz      short loc_180027911
0x1800278f8  mov     r8d, esi
0x1800278fb  mov     edx, edi
0x1800278fd  mov     rcx, r13
0x180027900  call    ?CleanUpDifferentPairedDevice@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@K@Z; StorageService::CleanUpDifferentPairedDevice(_STORAGE_DEVICE_TYPE,ulong)
0x180027905  mov     ebx, eax
0x180027907  test    eax, eax
0x180027909  js      loc_180027AF8
0x18002790f  jmp     short loc_180027915
0x180027911  test    al, 4
0x180027913  jz      short loc_180027945
0x180027915  lea     rdx, [rsp+4C0h+var_460]; struct _GUID *
0x18002791a  call    ?GetDeviceAppPairingId@StorageService@@IEAAJPEAU_GUID@@@Z; StorageService::GetDeviceAppPairingId(_GUID *)
0x18002791f  mov     ebx, eax
0x180027921  test    eax, eax
0x180027923  js      loc_180027AF8
0x180027929  lea     r9, [rsp+4C0h+var_460]
0x18002792e  mov     r8d, esi
0x180027931  mov     edx, edi
0x180027933  mov     rcx, r13
0x180027936  call    ?SetStorageCardAppMetadata@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@KPEAU_GUID@@@Z; StorageService::SetStorageCardAppMetadata(_STORAGE_DEVICE_TYPE,ulong,_GUID *)
0x18002793b  mov     ebx, eax
0x18002793d  test    eax, eax
0x18002793f  js      loc_180027AF8
0x180027945  imul    r14, rsi, 458h
0x18002794c  mov     r11d, 104h
0x180027952  lea     rcx, [rsp+4C0h+pszPath]; wchar_t *
0x180027957  mov     edx, r11d; unsigned __int64
0x18002795a  lea     r8, [r14+4]
0x18002795e  add     r8, [r13+rdi*8+28h]; wchar_t *
0x180027963  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180027968  mov     ebx, eax
0x18002796a  test    eax, eax
0x18002796c  js      loc_180027AF8
0x180027972  lea     r8, aWindowsapps; "WindowsApps"
0x180027979  mov     edx, r11d; cchPath
0x18002797c  lea     rcx, [rsp+4C0h+pszPath]; pszPath
0x180027981  call    cs:__imp_PathCchAppend
0x180027987  mov     ebx, eax
0x180027989  test    eax, eax
0x18002798b  js      loc_180027AF8
0x180027991  lea     rdx, [rsp+4C0h+pszPath]; unsigned __int16 *
0x180027996  call    ?DirectoryIsReparsePoint@StorageService@@AEAAHPEBG@Z; StorageService::DirectoryIsReparsePoint(ushort const *)
0x18002799b  test    eax, eax
0x18002799d  jz      short loc_1800279B8
0x18002799f  lea     rcx, [rsp+4C0h+pszPath]; lpFileName
0x1800279a4  call    cs:__imp_DeleteFileW
0x1800279aa  test    eax, eax
0x1800279ac  jnz     short loc_1800279B8
0x1800279ae  mov     ebx, 80070052h
0x1800279b3  jmp     loc_180027AF8
0x1800279b8  mov     [rsp+4C0h+var_488], 0
0x1800279c0  lea     r9, aWindowsapps; "WindowsApps"
0x1800279c7  mov     [rsp+4C0h+var_490], 0
0x1800279d0  mov     r8d, esi
0x1800279d3  mov     [rsp+4C0h+var_498], 0
0x1800279dc  mov     edx, edi
0x1800279de  mov     rcx, r13
0x1800279e1  mov     dword ptr [rsp+4C0h+lpCreatedInstanceName], 1
0x1800279e9  call    ?CreateStorageCardDirectory@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@KPEBGKPEAU_SECURITY_ATTRIBUTES@@PEAU_ACL@@H@Z; StorageService::CreateStorageCardDirectory(_STORAGE_DEVICE_TYPE,ulong,ushort const *,ulong,_SECURITY_ATTRIBUTES *,_ACL *,int)
0x1800279ee  mov     ebx, eax
0x1800279f0  test    eax, eax
0x1800279f2  js      loc_180027AF8
0x1800279f8  mov     rdx, [r13+rdi*8+28h]
0x1800279fd  lea     rcx, FilterName; "Filecrypt"
0x180027a04  add     rdx, 4
0x180027a08  mov     [rsp+4C0h+lpCreatedInstanceName], 0; lpCreatedInstanceName
0x180027a11  add     rdx, r14; lpVolumeName
0x180027a14  xor     r9d, r9d; dwCreatedInstanceNameLength
0x180027a17  xor     r8d, r8d; lpInstanceName
0x180027a1a  call    cs:__imp_FilterAttach
0x180027a20  mov     ecx, 80000000h
0x180027a25  mov     ebx, eax
0x180027a27  add     eax, ecx
0x180027a29  test    ecx, eax
0x180027a2b  jnz     short loc_180027A85
0x180027a2d  cmp     ebx, 801F0012h
0x180027a33  jz      short loc_180027A85
0x180027a35  mov     eax, cs:dword_1800BF000
0x180027a3b  cmp     eax, 5
0x180027a3e  jbe     loc_180027AF8
0x180027a44  mov     rcx, [r13+rdi*8+28h]
0x180027a49  lea     rax, [rsp+4C0h+var_480]
0x180027a4e  add     rcx, 4
0x180027a52  mov     [rsp+4C0h+var_498], rax
0x180027a57  add     rcx, r14
0x180027a5a  mov     [rsp+4C0h+var_480], ebx
0x180027a5e  mov     qword ptr [rsp+4C0h+rguid.Data1], rcx
0x180027a63  lea     rax, [rsp+4C0h+rguid]
0x180027a68  lea     rcx, dword_1800BF000
0x180027a6f  mov     [rsp+4C0h+lpCreatedInstanceName], rax
0x180027a74  xor     r8d, r8d
0x180027a77  lea     rdx, byte_1800A5BC3
0x180027a7e  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180027a83  jmp     short loc_180027AF8
0x180027a85  mov     r9d, 2
0x180027a8b  mov     r8d, esi
0x180027a8e  mov     edx, edi
0x180027a90  mov     rcx, r13
0x180027a93  call    ?SetAppPairingStatus@StorageService@@IEAAXW4_STORAGE_DEVICE_TYPE@@KK@Z; StorageService::SetAppPairingStatus(_STORAGE_DEVICE_TYPE,ulong,ulong)
0x180027a98  mov     r8d, esi
0x180027a9b  mov     edx, edi
0x180027a9d  mov     rcx, r13
0x180027aa0  call    ?SetStorageCardPowerPolicy@StorageService@@IEAAXW4_STORAGE_DEVICE_TYPE@@K@Z; StorageService::SetStorageCardPowerPolicy(_STORAGE_DEVICE_TYPE,ulong)
0x180027aa5  mov     rax, [r13+rdi*8+28h]
0x180027aaa  lea     r8, aC; "\\\\.\\%c:"
0x180027ab1  mov     edx, 104h; unsigned __int64
0x180027ab6  lea     rcx, [rbp+3C0h+var_240]; unsigned __int16 *
0x180027abd  movzx   r9d, word ptr [rax+r14+4]
0x180027ac3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180027ac8  mov     ebx, eax
0x180027aca  test    eax, eax
0x180027acc  js      short loc_180027AF3
0x180027ace  mov     rax, [r13+rdi*8+28h]
0x180027ad3  lea     rdx, [rsp+4C0h+rguid]; rguid
0x180027ad8  lea     rcx, [rbp+3C0h+var_240]; unsigned __int16 *
0x180027adf  movups  xmm0, xmmword ptr [rax+r14+224h]
0x180027ae8  movdqu  xmmword ptr [rsp+4C0h+rguid.Data1], xmm0
0x180027aee  call    ?SetStorageCardWriteBackCache@@YAJPEBGU_GUID@@_N@Z; SetStorageCardWriteBackCache(ushort const *,_GUID,bool)
0x180027af3  call    ?ChangeServiceStartSettings@StorageService@@IEAAXXZ; StorageService::ChangeServiceStartSettings(void)
0x180027af8  mov     eax, ebx
0x180027afa  mov     rcx, [rbp+3C0h+var_30]
0x180027b01  xor     rcx, rsp; StackCookie
0x180027b04  call    __security_check_cookie
0x180027b09  lea     r11, [rsp+4C0h+var_20]
0x180027b11  mov     rbx, [r11+30h]
0x180027b15  mov     rsi, [r11+48h]
0x180027b19  mov     rsp, r11
0x180027b1c  pop     r15
0x180027b1e  pop     r14
0x180027b20  pop     r13
0x180027b22  pop     rdi
0x180027b23  pop     rbp
0x180027b24  retn
```
