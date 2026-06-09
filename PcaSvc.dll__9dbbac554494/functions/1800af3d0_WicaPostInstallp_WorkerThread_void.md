# WicaPostInstallp_WorkerThread(void *)

- ea: `0x1800af3d0`
- end: `0x1800af62d`
- name: `?WicaPostInstallp_WorkerThread@@YAKPEAX@Z`
- size: `605`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180012920`
- `0x18001b320`
- `0x18005190c`
- `0x1800aea50`
- `0x1800af3d0`
- `0x1800f1f10`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800af431`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800af431`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800af607`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800af607`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800af505`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800af505`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800af5f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800af5f5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800af594`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800af594`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800af465`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800af465`

## string_xrefs

- `0x1800af5a3`: `RegDeleteKeyEx Failed [%d]`
- `0x1800af4be`: `WicaPostInstallp_PopulateExeInfo Failed [%d]`
- `0x1800af50f`: `Populated %d exe entries in registry.`
- `0x1800af457`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\UpgradeCompatibility`
- `0x1800af580`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\UpgradeCompatibility`
- `0x1800af47a`: `RegOpenKeyEx Failed [%d]`
- `0x1800af402`: `In worker thread. Initializing...`
- `0x1800af3fb`: `WicaPostInstallp_WorkerThread`
- `0x1800af5b5`: `Deleted upgrade compatibility root key as it has no subkeys.`
- `0x1800af5cc`: `Created upgrade notifications,%d`
- `0x1800af541`: `WicaPostInstallp_SetupNotifications Failed [%d]`

## pseudocode

```c
__int64 __fastcall WicaPostInstallp_WorkerThread(PVOID Parameter)
{
  unsigned int v1; // ebx
  __int64 v2; // rdx
  __int64 v3; // r8
  LSTATUS v4; // eax
  const char *v5; // r9
  int v6; // r8d
  DWORD v7; // esi
  DWORD i; // edx
  int v9; // eax
  int v10; // edx
  unsigned int v11; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+20h] [rbp-E0h]
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF

  hKey = 0;
  cchName = 0;
  v1 = 1359;
  AslLogCallPrintf(
    3,
    (unsigned int)"WicaPostInstallp_WorkerThread",
    1065,
    (unsigned int)"In worker thread. Initializing...");
  RtlAcquireSRWLockExclusive(&WicaGlobals, v2, v3);
  if ( !dword_1801598B8 )
  {
    v4 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\UpgradeCompatibility",
           0,
           0x2001Fu,
           &hKey);
    v1 = v4;
    if ( v4 )
    {
      if ( v4 == 2 )
        goto LABEL_18;
      v5 = "RegOpenKeyEx Failed [%d]";
      v6 = 1089;
      goto LABEL_5;
    }
    v7 = 0;
    for ( i = 0; ; i = v7 )
    {
      cchName = 260;
      if ( RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0) )
        break;
      ++v7;
      v9 = WicaPostInstallp_PopulateExeInfo(hKey, Name);
      if ( v9 )
      {
        LODWORD(phkResulta) = v9;
        AslLogCallPrintf(
          1,
          (unsigned int)"WicaPostInstallp_WorkerThread",
          1111,
          (unsigned int)"WicaPostInstallp_PopulateExeInfo Failed [%d]",
          phkResulta);
      }
    }
    LODWORD(phkResulta) = v7;
    AslLogCallPrintf(
      3,
      (unsigned int)"WicaPostInstallp_WorkerThread",
      1120,
      (unsigned int)"Populated %d exe entries in registry.",
      phkResulta);
    v11 = WicaPostInstallp_SetupNotifications(hKey, v10, 1);
    if ( v11 )
    {
      LODWORD(phkResult) = v11;
      AslLogCallPrintf(
        1,
        (unsigned int)"WicaPostInstallp_WorkerThread",
        1124,
        (unsigned int)"WicaPostInstallp_SetupNotifications Failed [%d]",
        phkResult);
    }
    AslLogCallPrintf(
      3,
      (unsigned int)"WicaPostInstallp_WorkerThread",
      1130,
      (unsigned int)"Setup notifications for EXEs.");
    if ( !v7 )
    {
      v4 = RegDeleteKeyExW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\UpgradeCompatibility",
             0x100u,
             0);
      v1 = v4;
      if ( v4 )
      {
        v5 = "RegDeleteKeyEx Failed [%d]";
        v6 = 1141;
LABEL_5:
        LODWORD(phkResult) = v4;
        AslLogCallPrintf(1, (unsigned int)"WicaPostInstallp_WorkerThread", v6, (_DWORD)v5, phkResult);
        goto LABEL_18;
      }
      AslLogCallPrintf(
        3,
        (unsigned int)"WicaPostInstallp_WorkerThread",
        1145,
        (unsigned int)"Deleted upgrade compatibility root key as it has no subkeys.");
    }
    PcaTracePrintf("WicaPostUpgrade", 0, 0, "Created upgrade notifications,%d", v7);
    v1 = 0;
  }
LABEL_18:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  RtlReleaseSRWLockExclusive(&WicaGlobals);
  return v1;
}

```

## disassembly

```asm
0x1800af3d0  push    rbp
0x1800af3d2  push    rbx
0x1800af3d3  push    rsi
0x1800af3d4  push    r14
0x1800af3d6  push    r15
0x1800af3d8  lea     rbp, [rsp-170h]
0x1800af3e0  sub     rsp, 270h
0x1800af3e7  mov     rax, cs:__security_cookie
0x1800af3ee  xor     rax, rsp
0x1800af3f1  mov     [rbp+190h+var_30], rax
0x1800af3f8  xor     r14d, r14d
0x1800af3fb  lea     r15, aWicapostinstal_3; "WicaPostInstallp_WorkerThread"
0x1800af402  lea     r9, aInWorkerThread; "In worker thread. Initializing..."
0x1800af409  mov     [rsp+290h+hKey], r14
0x1800af40e  mov     r8d, 429h
0x1800af414  mov     [rsp+290h+cchName], r14d
0x1800af419  mov     rdx, r15
0x1800af41c  mov     ebx, 54Fh
0x1800af421  lea     ecx, [r14+3]
0x1800af425  call    AslLogCallPrintf
0x1800af42a  lea     rcx, ?WicaGlobals@@3U_WicaGlobals@@A; _WicaGlobals WicaGlobals
0x1800af431  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800af437  cmp     cs:dword_1801598B8, r14d
0x1800af43e  jnz     loc_1800AF5EB
0x1800af444  lea     rax, [rsp+290h+hKey]
0x1800af449  mov     r9d, 2001Fh; samDesired
0x1800af44f  xor     r8d, r8d; ulOptions
0x1800af452  mov     [rsp+290h+phkResult], rax; phkResult
0x1800af457  lea     rdx, aSoftwareMicros_13; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800af45e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800af465  call    cs:__imp_RegOpenKeyExW
0x1800af46b  mov     ebx, eax
0x1800af46d  test    eax, eax
0x1800af46f  jz      short loc_1800AF49D
0x1800af471  cmp     eax, 2
0x1800af474  jz      loc_1800AF5EB
0x1800af47a  lea     r9, aRegopenkeyexFa; "RegOpenKeyEx Failed [%d]"
0x1800af481  mov     r8d, 441h
0x1800af487  mov     rdx, r15
0x1800af48a  mov     ecx, 1
0x1800af48f  mov     dword ptr [rsp+290h+phkResult], eax
0x1800af493  call    AslLogCallPrintf
0x1800af498  jmp     loc_1800AF5EB
0x1800af49d  mov     esi, r14d
0x1800af4a0  mov     ebx, 104h
0x1800af4a5  xor     edx, edx
0x1800af4a7  jmp     short loc_1800AF4DE
0x1800af4a9  mov     rcx, [rsp+290h+hKey]; HKEY
0x1800af4ae  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x1800af4b3  inc     esi
0x1800af4b5  call    ?WicaPostInstallp_PopulateExeInfo@@YAKPEAUHKEY__@@PEBG@Z; WicaPostInstallp_PopulateExeInfo(HKEY__ *,ushort const *)
0x1800af4ba  test    eax, eax
0x1800af4bc  jz      short loc_1800AF4DC
0x1800af4be  lea     r9, aWicapostinstal_11; "WicaPostInstallp_PopulateExeInfo Failed"...
0x1800af4c5  mov     dword ptr [rsp+290h+phkResult], eax
0x1800af4c9  mov     r8d, 457h
0x1800af4cf  mov     rdx, r15
0x1800af4d2  mov     ecx, 1
0x1800af4d7  call    AslLogCallPrintf
0x1800af4dc  mov     edx, esi; dwIndex
0x1800af4de  mov     rcx, [rsp+290h+hKey]; hKey
0x1800af4e3  lea     r9, [rsp+290h+cchName]; lpcchName
0x1800af4e8  mov     [rsp+290h+lpftLastWriteTime], r14; lpftLastWriteTime
0x1800af4ed  lea     r8, [rsp+290h+Name]; lpName
0x1800af4f2  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x1800af4f7  mov     [rsp+290h+lpClass], r14; lpClass
0x1800af4fc  mov     [rsp+290h+phkResult], r14; lpReserved
0x1800af501  mov     [rsp+290h+cchName], ebx
0x1800af505  call    cs:__imp_RegEnumKeyExW
0x1800af50b  test    eax, eax
0x1800af50d  jz      short loc_1800AF4A9
0x1800af50f  lea     r9, aPopulatedDExeE; "Populated %d exe entries in registry."
0x1800af516  mov     dword ptr [rsp+290h+phkResult], esi
0x1800af51a  mov     r8d, 460h
0x1800af520  mov     rdx, r15
0x1800af523  mov     ecx, 3
0x1800af528  call    AslLogCallPrintf
0x1800af52d  mov     rcx, [rsp+290h+hKey]; hkey
0x1800af532  mov     r8d, 1; int
0x1800af538  call    ?WicaPostInstallp_SetupNotifications@@YAKPEAUHKEY__@@HH@Z; WicaPostInstallp_SetupNotifications(HKEY__ *,int,int)
0x1800af53d  test    eax, eax
0x1800af53f  jz      short loc_1800AF55F
0x1800af541  lea     r9, aWicapostinstal_4; "WicaPostInstallp_SetupNotifications Fai"...
0x1800af548  mov     dword ptr [rsp+290h+phkResult], eax
0x1800af54c  mov     r8d, 464h
0x1800af552  mov     rdx, r15
0x1800af555  mov     ecx, 1
0x1800af55a  call    AslLogCallPrintf
0x1800af55f  lea     r9, aSetupNotificat; "Setup notifications for EXEs."
0x1800af566  mov     r8d, 46Ah
0x1800af56c  mov     rdx, r15
0x1800af56f  mov     ecx, 3
0x1800af574  call    AslLogCallPrintf
0x1800af579  test    esi, esi
0x1800af57b  jnz     short loc_1800AF5CC
0x1800af57d  xor     r9d, r9d; Reserved
0x1800af580  lea     rdx, aSoftwareMicros_13; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800af587  mov     r8d, 100h; samDesired
0x1800af58d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800af594  call    cs:__imp_RegDeleteKeyExW
0x1800af59a  mov     ebx, eax
0x1800af59c  mov     rdx, r15
0x1800af59f  test    eax, eax
0x1800af5a1  jz      short loc_1800AF5B5
0x1800af5a3  lea     r9, aRegdeletekeyex; "RegDeleteKeyEx Failed [%d]"
0x1800af5aa  mov     r8d, 475h
0x1800af5b0  jmp     loc_1800AF48A
0x1800af5b5  lea     r9, aDeletedUpgrade; "Deleted upgrade compatibility root key "...
0x1800af5bc  mov     r8d, 479h
0x1800af5c2  mov     ecx, 3
0x1800af5c7  call    AslLogCallPrintf
0x1800af5cc  lea     r9, aCreatedUpgrade; "Created upgrade notifications,%d"
0x1800af5d3  mov     dword ptr [rsp+290h+phkResult], esi
0x1800af5d7  xor     r8d, r8d; unsigned int
0x1800af5da  lea     rcx, aWicapostupgrad; "WicaPostUpgrade"
0x1800af5e1  xor     edx, edx; unsigned int
0x1800af5e3  call    ?PcaTracePrintf@@YAXPEBDIK0ZZ; PcaTracePrintf(char const *,uint,ulong,char const *,...)
0x1800af5e8  mov     ebx, r14d
0x1800af5eb  mov     rcx, [rsp+290h+hKey]; hKey
0x1800af5f0  test    rcx, rcx
0x1800af5f3  jz      short loc_1800AF600
0x1800af5f5  call    cs:__imp_RegCloseKey
0x1800af5fb  mov     [rsp+290h+hKey], r14
0x1800af600  lea     rcx, ?WicaGlobals@@3U_WicaGlobals@@A; _WicaGlobals WicaGlobals
0x1800af607  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800af60d  mov     eax, ebx
0x1800af60f  mov     rcx, [rbp+190h+var_30]
0x1800af616  xor     rcx, rsp; StackCookie
0x1800af619  call    __security_check_cookie
0x1800af61e  add     rsp, 270h
0x1800af625  pop     r15
0x1800af627  pop     r14
0x1800af629  pop     rsi
0x1800af62a  pop     rbx
0x1800af62b  pop     rbp
0x1800af62c  retn
```
