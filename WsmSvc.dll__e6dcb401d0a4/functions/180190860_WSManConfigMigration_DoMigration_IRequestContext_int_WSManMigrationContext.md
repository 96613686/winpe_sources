# WSManConfigMigration::DoMigration(IRequestContext *,int,WSManMigrationContext *)

- ea: `0x180190860`
- end: `0x180190f28`
- name: `?DoMigration@WSManConfigMigration@@YAHPEAVIRequestContext@@HPEAVWSManMigrationContext@@@Z`
- size: `1736`
- prototype: `__int64 __fastcall(WSManConfigMigration *__hidden this, struct IRequestContext *, int, struct WSManMigrationContext *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180191490`

## callees

- `0x1800a901c`
- `0x1800bac30`
- `0x1800e8a50`
- `0x1800ed980`
- `0x180103db8`
- `0x180122180`
- `0x180190860`
- `0x180191878`
- `0x180192198`
- `0x180192430`
- `0x1801926c4`
- `0x180192de0`
- `0x1801930d0`
- `0x18019b1d8`
- `0x18019e470`
- `0x1801ba1b0`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180190909`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180190963`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801909be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180190a15`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180190a69`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180190909`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180190963`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801909be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180190a15`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180190a69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801908d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801908eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180190931`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019094b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019098c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801909a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801909e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801909fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180190a3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180190a54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180190e80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801908d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801908eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180190931`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019094b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019098c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801909a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801909e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801909fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180190a3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180190a54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180190e80`

## string_xrefs

- `0x18019093a`: `No Service key found for migration. Return Code: %lu`
- `0x1801909ec`: `No Plugin key found for migration. Return Code: %lu`
- `0x180190a88`: `No Client, Service or Listener key for migration.`
- `0x180190b0f`: `Failed to create config update object.Error: %lu`
- `0x180190b93`: `Migrating Listeners was successful. Compat HTTP/HTTPS staus is: %d, %d`
- `0x180190c95`: `MigrateSecuritySettingsUnencrypted returned failure. Error Code: %lu`
- `0x180190cae`: `Migrating Security Settings successful.`
- `0x180190d01`: `Migrating Security Settings successful.`
- `0x180190cf8`: `MigrateClientServiceConfigSettings returned failure. Error Code: %lu`
- `0x180190d33`: `DoMigration failed while finally applying common config changes. Error Code: %lu`
- `0x180190d3f`: `Finally applying common config changes was successful.`
- `0x180190d79`: `Migrating Plugin & CertMapping returned failure. Error Code: %lu`
- `0x180190d85`: `Migrating Plugin & CertMapping was successful.`
- `0x180190dc7`: `EnableCompatibilityHttpListener`
- `0x180190de4`: `Event logged for HTTP compatibility listener.`
- `0x180190e1b`: `EnableCompatibilityHttpsListener`
- `0x180190e3a`: `Event logged for HTTPS compatibility listener.`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall WSManConfigMigration::DoMigration(
        WSManConfigMigration *this,
        struct IRequestContext *a2,
        __int64 *a3,
        struct WSManMigrationContext *a4)
{
  DWORD LastError; // eax
  unsigned int v8; // r14d
  DWORD v9; // eax
  DWORD v10; // eax
  DWORD v11; // eax
  DWORD v12; // eax
  HKEY hKey; // [rsp+40h] [rbp-89h] BYREF
  HKEY v14; // [rsp+50h] [rbp-79h] BYREF
  HKEY v15; // [rsp+60h] [rbp-69h] BYREF
  HKEY v16; // [rsp+70h] [rbp-59h] BYREF
  HKEY v17; // [rsp+78h] [rbp-51h] BYREF

  anonymous_namespace_::LogMigrationMessage(a3, 0, L"Entered DoMigration", a4);
  hKey = 0;
  if ( !(unsigned int)anonymous_namespace_::OpenRegKey(this, 131097) )
  {
    LastError = GetLastError();
    anonymous_namespace_::LogMigrationMessage(a3, 0, L"No Client key found for migration. Return Code: %lu", LastError);
    if ( GetLastError() != 2 )
    {
LABEL_3:
      AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(&hKey);
      return 0;
    }
    SetLastError(0);
  }
  v14 = 0;
  v8 = 1;
  if ( !(unsigned int)anonymous_namespace_::OpenRegKey(this, 131097) )
  {
    v9 = GetLastError();
    anonymous_namespace_::LogMigrationMessage(a3, 0, L"No Service key found for migration. Return Code: %lu", v9);
    if ( GetLastError() != 2 )
    {
LABEL_7:
      AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(&v14);
      goto LABEL_3;
    }
    SetLastError(0);
  }
  v15 = 0;
  if ( !(unsigned int)anonymous_namespace_::OpenRegKey(this, 8) )
  {
    v10 = GetLastError();
    anonymous_namespace_::LogMigrationMessage(a3, 0, L"No Listener key found for migration. Return Code: %lu", v10);
    if ( GetLastError() != 2 )
    {
LABEL_11:
      AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(&v15);
      goto LABEL_7;
    }
    SetLastError(0);
  }
  v16 = 0;
  if ( !(unsigned int)anonymous_namespace_::OpenRegKey(this, 131097) )
  {
    v11 = GetLastError();
    anonymous_namespace_::LogMigrationMessage(a3, 0, L"No Plugin key found for migration. Return Code: %lu", v11);
    if ( GetLastError() != 2 )
    {
      AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(&v16);
      goto LABEL_11;
    }
    SetLastError(0);
  }
  v17 = 0;
  if ( (unsigned int)anonymous_namespace_::OpenRegKey(this, 131097) )
    goto LABEL_21;
  v12 = GetLastError();
  anonymous_namespace_::LogMigrationMessage(a3, 0, L"No CertMapping key found for migration. Return Code: %lu", v12);
  if ( GetLastError() == 2 )
  {
    SetLastError(0);
LABEL_21:
    anonymous_namespace_::LogMigrationMessage(a3, 0, L"No Client, Service or Listener key for migration.");
    goto LABEL_22;
  }
  v8 = 0;
LABEL_22:
  AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(&v17);
  AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(&v16);
  AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(&v15);
  AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(&v14);
  AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(&hKey);
  return v8;
}

```

## disassembly

```asm
0x180190860  mov     [rsp-8+arg_18], rbx
0x180190865  push    rbp
0x180190866  push    rsi
0x180190867  push    rdi
0x180190868  push    r12
0x18019086a  push    r13
0x18019086c  push    r14
0x18019086e  push    r15
0x180190870  lea     rbp, [rsp-27h]
0x180190875  sub     rsp, 0F0h
0x18019087c  mov     rax, cs:__security_cookie
0x180190883  xor     rax, rsp
0x180190886  mov     [rbp+57h+var_40], rax
0x18019088a  mov     rdi, r8
0x18019088d  mov     r15d, edx
0x180190890  mov     rbx, rcx
0x180190893  lea     r8, aEnteredDomigra; "Entered DoMigration"
0x18019089a  xor     edx, edx
0x18019089c  mov     rcx, rdi
0x18019089f  call    _anonymous_namespace___LogMigrationMessage
0x1801908a4  xor     r12d, r12d
0x1801908a7  mov     [rsp+120h+hKey], r12
0x1801908ac  mov     esi, 20019h
0x1801908b1  mov     [rsp+120h+var_100], esi; int
0x1801908b5  xor     r9d, r9d
0x1801908b8  lea     r8, [rsp+120h+hKey]
0x1801908bd  lea     r13d, [r12+2]
0x1801908c2  mov     edx, r13d
0x1801908c5  mov     rcx, rbx; struct IRequestContext *
0x1801908c8  call    _anonymous_namespace___OpenRegKey
0x1801908cd  test    eax, eax
0x1801908cf  jnz     short loc_18019090F
0x1801908d1  call    cs:__imp_GetLastError
0x1801908d7  mov     r9d, eax
0x1801908da  lea     r8, aNoClientKeyFou; "No Client key found for migration. Retu"...
0x1801908e1  xor     edx, edx
0x1801908e3  mov     rcx, rdi
0x1801908e6  call    _anonymous_namespace___LogMigrationMessage
0x1801908eb  call    cs:__imp_GetLastError
0x1801908f1  cmp     eax, r13d
0x1801908f4  jz      short loc_180190907
0x1801908f6  lea     rcx, [rsp+120h+hKey]
0x1801908fb  call    ??1?$AutoCleanup@VAutoRegKey@@PEAUHKEY__@@@@QEAA@XZ; AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(void)
0x180190900  xor     eax, eax
0x180190902  jmp     loc_180190F01
0x180190907  xor     ecx, ecx; dwErrCode
0x180190909  call    cs:__imp_SetLastError
0x18019090f  mov     [rbp+57h+var_D0], r12
0x180190913  mov     [rsp+120h+var_100], esi; int
0x180190917  xor     r9d, r9d
0x18019091a  lea     r8, [rbp+57h+var_D0]
0x18019091e  lea     r14d, [r9+1]
0x180190922  mov     edx, r14d
0x180190925  mov     rcx, rbx; struct IRequestContext *
0x180190928  call    _anonymous_namespace___OpenRegKey
0x18019092d  test    eax, eax
0x18019092f  jnz     short loc_180190969
0x180190931  call    cs:__imp_GetLastError
0x180190937  mov     r9d, eax
0x18019093a  lea     r8, aNoServiceKeyFo; "No Service key found for migration. Ret"...
0x180190941  xor     edx, edx
0x180190943  mov     rcx, rdi
0x180190946  call    _anonymous_namespace___LogMigrationMessage
0x18019094b  call    cs:__imp_GetLastError
0x180190951  cmp     eax, r13d
0x180190954  jz      short loc_180190961
0x180190956  lea     rcx, [rbp+57h+var_D0]
0x18019095a  call    ??1?$AutoCleanup@VAutoRegKey@@PEAUHKEY__@@@@QEAA@XZ; AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(void)
0x18019095f  jmp     short loc_1801908F6
0x180190961  xor     ecx, ecx; dwErrCode
0x180190963  call    cs:__imp_SetLastError
0x180190969  mov     [rbp+57h+var_C0], r12
0x18019096d  mov     [rsp+120h+var_100], 8; int
0x180190975  xor     r9d, r9d
0x180190978  lea     r8, [rbp+57h+var_C0]
0x18019097c  lea     edx, [r9+3]
0x180190980  mov     rcx, rbx; struct IRequestContext *
0x180190983  call    _anonymous_namespace___OpenRegKey
0x180190988  test    eax, eax
0x18019098a  jnz     short loc_1801909C4
0x18019098c  call    cs:__imp_GetLastError
0x180190992  mov     r9d, eax
0x180190995  lea     r8, aNoListenerKeyF; "No Listener key found for migration. Re"...
0x18019099c  xor     edx, edx
0x18019099e  mov     rcx, rdi
0x1801909a1  call    _anonymous_namespace___LogMigrationMessage
0x1801909a6  call    cs:__imp_GetLastError
0x1801909ac  cmp     eax, r13d
0x1801909af  jz      short loc_1801909BC
0x1801909b1  lea     rcx, [rbp+57h+var_C0]
0x1801909b5  call    ??1?$AutoCleanup@VAutoRegKey@@PEAUHKEY__@@@@QEAA@XZ; AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(void)
0x1801909ba  jmp     short loc_180190956
0x1801909bc  xor     ecx, ecx; dwErrCode
0x1801909be  call    cs:__imp_SetLastError
0x1801909c4  mov     [rbp+57h+var_B0], r12
0x1801909c8  mov     [rsp+120h+var_100], esi; int
0x1801909cc  xor     r9d, r9d
0x1801909cf  lea     r8, [rbp+57h+var_B0]
0x1801909d3  lea     edx, [r9+7]
0x1801909d7  mov     rcx, rbx; struct IRequestContext *
0x1801909da  call    _anonymous_namespace___OpenRegKey
0x1801909df  test    eax, eax
0x1801909e1  jnz     short loc_180190A1B
0x1801909e3  call    cs:__imp_GetLastError
0x1801909e9  mov     r9d, eax
0x1801909ec  lea     r8, aNoPluginKeyFou; "No Plugin key found for migration. Retu"...
0x1801909f3  xor     edx, edx
0x1801909f5  mov     rcx, rdi
0x1801909f8  call    _anonymous_namespace___LogMigrationMessage
0x1801909fd  call    cs:__imp_GetLastError
0x180190a03  cmp     eax, r13d
0x180190a06  jz      short loc_180190A13
0x180190a08  lea     rcx, [rbp+57h+var_B0]
0x180190a0c  call    ??1?$AutoCleanup@VAutoRegKey@@PEAUHKEY__@@@@QEAA@XZ; AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(void)
0x180190a11  jmp     short loc_1801909B1
0x180190a13  xor     ecx, ecx; dwErrCode
0x180190a15  call    cs:__imp_SetLastError
0x180190a1b  mov     [rbp+57h+var_A8], r12
0x180190a1f  mov     [rsp+120h+var_100], esi; int
0x180190a23  xor     r9d, r9d
0x180190a26  lea     r8, [rbp+57h+var_A8]
0x180190a2a  lea     edx, [r9+5]
0x180190a2e  mov     rcx, rbx; struct IRequestContext *
0x180190a31  call    _anonymous_namespace___OpenRegKey
0x180190a36  test    eax, eax
0x180190a38  jnz     short loc_180190A6F
0x180190a3a  call    cs:__imp_GetLastError
0x180190a40  mov     r9d, eax
0x180190a43  lea     r8, aNoCertmappingK; "No CertMapping key found for migration."...
0x180190a4a  xor     edx, edx
0x180190a4c  mov     rcx, rdi
0x180190a4f  call    _anonymous_namespace___LogMigrationMessage
0x180190a54  call    cs:__imp_GetLastError
0x180190a5a  cmp     eax, r13d
0x180190a5d  jz      short loc_180190A67
0x180190a5f  mov     r14d, r12d
0x180190a62  jmp     loc_180190ECC
0x180190a67  xor     ecx, ecx; dwErrCode
0x180190a69  call    cs:__imp_SetLastError
0x180190a6f  cmp     [rsp+120h+hKey], r12
0x180190a74  jnz     short loc_180190A9E
0x180190a76  cmp     [rbp+57h+var_D0], r12
0x180190a7a  jnz     short loc_180190A9E
0x180190a7c  cmp     [rbp+57h+var_C0], r12
0x180190a80  jnz     short loc_180190A9E
0x180190a82  cmp     [rbp+57h+var_B0], r12
0x180190a86  jnz     short loc_180190A9E
0x180190a88  lea     r8, aNoClientServic; "No Client, Service or Listener key for "...
0x180190a8f  xor     edx, edx
0x180190a91  mov     rcx, rdi
0x180190a94  call    _anonymous_namespace___LogMigrationMessage
0x180190a99  jmp     loc_180190ECC
0x180190a9e  mov     [rbp+57h+var_98], r12d
0x180190aa2  lea     rax, ??_7CErrorContext@@6B@; const CErrorContext::`vftable'
0x180190aa9  mov     [rbp+57h+var_A0], rax
0x180190aad  mov     [rbp+57h+var_90], r12d
0x180190ab1  mov     [rbp+57h+var_8C], 0FFFFFFFFh
0x180190ab8  lea     rax, Class
0x180190abf  mov     [rbp+57h+var_80], rax
0x180190ac3  mov     [rbp+57h+var_78], rax
0x180190ac7  mov     [rbp+57h+var_70], rax
0x180190acb  mov     [rbp+57h+var_68], rax
0x180190acf  mov     [rbp+57h+var_88], r14b
0x180190ad3  lock add [rbp+57h+var_98], r14d
0x180190ad8  lea     rsi, [rbp+57h+var_A0]
0x180190adc  test    rbx, rbx
0x180190adf  cmovnz  rsi, rbx
0x180190ae3  mov     r8d, r14d; int
0x180190ae6  xor     edx, edx; struct WSMANCONFIGTABLE_IDENTITY *
0x180190ae8  mov     rcx, rsi; struct IRequestContext *
0x180190aeb  call    ?StartUpdates@ConfigUpdate@@SAPEAV1@PEAVIRequestContext@@PEAVWSMANCONFIGTABLE_IDENTITY@@H@Z; ConfigUpdate::StartUpdates(IRequestContext *,WSMANCONFIGTABLE_IDENTITY *,int)
0x180190af0  mov     rbx, rax
0x180190af3  mov     [rsp+120h+var_D8], rax
0x180190af8  test    rax, rax
0x180190afb  jnz     short loc_180190B38
0x180190afd  mov     rax, [rsi]
0x180190b00  mov     rcx, rsi
0x180190b03  mov     rax, [rax+98h]
0x180190b0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180190b0f  lea     r8, aFailedToCreate_4; "Failed to create config update object.E"...
0x180190b16  mov     r9d, eax
0x180190b19  mov     edx, r13d
0x180190b1c  mov     rcx, rdi
0x180190b1f  call    _anonymous_namespace___LogMigrationMessage
0x180190b24  nop
0x180190b25  lea     rcx, [rsp+120h+var_D8]
0x180190b2a  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDelete@VConfigUpdate@@@@PEAVConfigUpdate@@@@AEAAXXZ; AutoCleanup<AutoDelete<ConfigUpdate>,ConfigUpdate *>::ReleasePtr(void)
0x180190b2f  nop
0x180190b30  mov     r14d, r12d
0x180190b33  jmp     loc_180190EC1
0x180190b38  mov     dword ptr [rbp+57h+var_C8], r12d
0x180190b3c  mov     [rbp+57h+var_B8], r12d
0x180190b40  lea     rax, [rbp+57h+var_B8]
0x180190b44  mov     [rsp+120h+var_F8], rax
0x180190b49  lea     rax, [rbp+57h+var_C8]
0x180190b4d  mov     qword ptr [rsp+120h+var_100], rax
0x180190b52  mov     r9d, r15d
0x180190b55  mov     r8, [rbp+57h+var_C0]
0x180190b59  mov     rdx, rsi
0x180190b5c  mov     rcx, rdi
0x180190b5f  call    _anonymous_namespace___MigrateListeners
0x180190b64  test    eax, eax
0x180190b66  jnz     short loc_180190B83
0x180190b68  mov     rax, [rsi]
0x180190b6b  mov     rcx, rsi
0x180190b6e  mov     rax, [rax+98h]
0x180190b75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180190b7a  lea     r8, aMigratelistene; "MigrateListeners returned failure.Error"...
0x180190b81  jmp     short loc_180190B16
0x180190b83  mov     r12d, [rbp+57h+var_B8]
0x180190b87  mov     [rsp+120h+var_100], r12d
0x180190b8c  mov     r13d, dword ptr [rbp+57h+var_C8]
0x180190b90  mov     r9d, r13d
0x180190b93  lea     r8, aMigratingListe; "Migrating Listeners was successful. Com"...
0x180190b9a  xor     edx, edx
0x180190b9c  mov     rcx, rdi
0x180190b9f  call    _anonymous_namespace___LogMigrationMessage
0x180190ba4  xor     r15d, r15d
0x180190ba7  xor     edx, edx
0x180190ba9  cmp     r15d, 7
0x180190bad  jnb     loc_180190C5C
0x180190bb3  mov     eax, r15d
0x180190bb6  shl     rax, 4
0x180190bba  lea     rcx, qword_18027C940
0x180190bc1  add     rax, rcx
0x180190bc4  mov     [rbp+57h+var_C8], rax
0x180190bc8  mov     r9d, [rax]
0x180190bcb  lea     r8, aLookingToMigra; "Looking to migrate setting: %lu"
0x180190bd2  mov     rcx, rdi
0x180190bd5  call    _anonymous_namespace___LogMigrationMessage
0x180190bda  mov     [rsp+120h+var_E8], 0
0x180190be3  mov     [rsp+120h+var_F0], 0
0x180190bec  mov     [rsp+120h+var_F8], rbx
0x180190bf1  mov     rax, [rbp+57h+var_C8]
0x180190bf5  mov     qword ptr [rsp+120h+var_100], rax
0x180190bfa  mov     r9, [rbp+57h+var_D0]
0x180190bfe  mov     r8, [rsp+120h+hKey]
0x180190c03  mov     rdx, rsi
0x180190c06  mov     rcx, rdi
0x180190c09  call    _anonymous_namespace___MigrateSetting
0x180190c0e  test    eax, eax
0x180190c10  jz      short loc_180190C17
0x180190c12  add     r15d, r14d
0x180190c15  jmp     short loc_180190BA7
0x180190c17  mov     rax, [rsi]
0x180190c1a  mov     rcx, rsi
0x180190c1d  mov     rax, [rax+98h]
0x180190c24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180190c29  mov     [rsp+120h+var_100], eax
0x180190c2d  mov     rax, [rbp+57h+var_C8]
0x180190c31  mov     r9d, [rax]
0x180190c34  lea     r8, aMigratesetting; "MigrateSetting for setting number %lu r"...
0x180190c3b  mov     edx, 2
0x180190c40  mov     rcx, rdi
0x180190c43  call    _anonymous_namespace___LogMigrationMessage
0x180190c48  nop
0x180190c49  lea     rcx, [rsp+120h+var_D8]
0x180190c4e  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDelete@VConfigUpdate@@@@PEAVConfigUpdate@@@@AEAAXXZ; AutoCleanup<AutoDelete<ConfigUpdate>,ConfigUpdate *>::ReleasePtr(void)
0x180190c53  nop
0x180190c54  xor     r14d, r14d
0x180190c57  jmp     loc_180190EC1
0x180190c5c  lea     r8, aMigrating1stSe; "Migrating 1st set of settings succesful"...
0x180190c63  mov     rcx, rdi
0x180190c66  call    _anonymous_namespace___LogMigrationMessage
0x180190c6b  mov     r9, rbx
0x180190c6e  mov     r8, [rbp+57h+var_D0]; HKEY
0x180190c72  mov     rdx, [rsp+120h+hKey]; hKey
0x180190c77  mov     rcx, rsi; struct IRequestContext *
0x180190c7a  call    _anonymous_namespace___MigrateSecuritySettingsUnencrypted
0x180190c7f  test    eax, eax
0x180190c81  jnz     short loc_180190CAE
0x180190c83  mov     rax, [rsi]
0x180190c86  mov     rcx, rsi
0x180190c89  mov     rax, [rax+98h]
0x180190c90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180190c95  lea     r8, aMigratesecurit; "MigrateSecuritySettingsUnencrypted retu"...
0x180190c9c  mov     r9d, eax
0x180190c9f  mov     edx, 2
0x180190ca4  mov     rcx, rdi
0x180190ca7  call    _anonymous_namespace___LogMigrationMessage
0x180190cac  jmp     short loc_180190C49
0x180190cae  lea     r8, aMigratingSecur; "Migrating Security Settings successful."
0x180190cb5  xor     edx, edx
0x180190cb7  mov     rcx, rdi
0x180190cba  call    _anonymous_namespace___LogMigrationMessage
0x180190cbf  mov     dword ptr [rsp+120h+var_F0], r12d
0x180190cc4  mov     dword ptr [rsp+120h+var_F8], r13d
0x180190cc9  mov     qword ptr [rsp+120h+var_100], rbx
0x180190cce  mov     r9, [rbp+57h+var_D0]
0x180190cd2  mov     r8, [rsp+120h+hKey]
0x180190cd7  mov     rdx, rsi
0x180190cda  mov     rcx, rdi
0x180190cdd  call    _anonymous_namespace___MigrateClientServiceConfigSettings
0x180190ce2  test    eax, eax
0x180190ce4  jnz     short loc_180190D01
0x180190ce6  mov     rax, [rsi]
0x180190ce9  mov     rcx, rsi
0x180190cec  mov     rax, [rax+98h]
0x180190cf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180190cf8  lea     r8, aMigrateclients; "MigrateClientServiceConfigSettings retu"...
  ... truncated ...
```
