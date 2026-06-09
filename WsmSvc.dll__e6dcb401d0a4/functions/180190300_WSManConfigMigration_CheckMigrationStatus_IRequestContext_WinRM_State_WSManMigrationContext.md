# WSManConfigMigration::CheckMigrationStatus(IRequestContext *,WinRM_State *,WSManMigrationContext *)

- ea: `0x180190300`
- end: `0x1801907a6`
- name: `?CheckMigrationStatus@WSManConfigMigration@@YAHPEAVIRequestContext@@PEAW4WinRM_State@@PEAVWSManMigrationContext@@@Z`
- size: `1190`
- prototype: `__int64 __fastcall(WSManConfigMigration *__hidden this, struct IRequestContext *, enum WinRM_State *, struct WSManMigrationContext *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180191490`

## callees

- `0x180005d10`
- `0x1800bac30`
- `0x1800e8a50`
- `0x1800ed980`
- `0x180112380`
- `0x1801123e8`
- `0x1801133b0`
- `0x180190300`
- `0x1801ba1b0`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019051b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180190631`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180190750`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019051b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180190631`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180190750`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18019057c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18019057c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801903ee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180190479`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801903ee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180190479`

## string_xrefs

- `0x180190350`: `onecore\admin\wmi\wmx\config\wsmanconfigmigration.cpp`
- `0x180190438`: `SOFTWARE\Microsoft\Windows\CurrentVersion\WSMAN\Migration\Plugin`
- `0x180190450`: `SOFTWARE\Microsoft\Windows\CurrentVersion\WSMAN\Migration\Plugin`
- `0x1801905f5`: `SOFTWARE\Microsoft\Windows\CurrentVersion\WSMAN\Migration\Plugin`
- `0x180190501`: `RegOpenKeyEx`
- `0x180190735`: `RegOpenKeyEx`
- `0x1801904b9`: `No plugin regkey found. Assuming State_VistaAndBefore`
- `0x180190521`: `Failed while opening plugin regkey. Error %d`
- `0x1801905b5`: `Plugin regkey has no subkeys. Assuming State_VistaAndBefore`
- `0x180190637`: `Failed while enumerating plugin regkey. Error %d`
- `0x180190643`: `Found Some plugins. Assuming State_WTROrWin7AndLater`
- `0x180190759`: `Failed while opening migration regkey. Error %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WSManConfigMigration::CheckMigrationStatus(
        WSManConfigMigration *this,
        struct IRequestContext *a2,
        enum WinRM_State *a3,
        struct WSManMigrationContext *a4)
{
  const WCHAR *v7; // rsi
  LSTATUS v8; // eax
  DWORD v9; // r14d
  const WCHAR *v10; // r14
  LSTATUS v11; // eax
  DWORD v12; // esi
  const unsigned __int16 *v13; // r8
  unsigned int v14; // ebx
  LSTATUS v15; // eax
  DWORD v16; // esi
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchName; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  const WCHAR *v21; // [rsp+58h] [rbp-A8h] BYREF
  const WCHAR *v22; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Name[256]; // [rsp+70h] [rbp-90h] BYREF

  if ( !a2 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\wsmanconfigmigration.cpp", 2563, L"2563", 0x54Fu, this);
    return 0;
  }
  if ( a3 )
    v7 = (const WCHAR *)(*(__int64 (__fastcall **)(enum WinRM_State *, const wchar_t *, enum WinRM_State *, struct WSManMigrationContext *))(*(_QWORD *)a3 + 16LL))(
                          a3,
                          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WSMAN\\Migration",
                          a3,
                          a4);
  else
    v7 = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WSMAN\\Migration";
  v21 = v7;
  *(_DWORD *)a2 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_924e359b40323068f2064522ccf2fc25_Traceguids, v7);
  phkResult = 0;
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v7, 0, 0x101u, &phkResult);
  v9 = v8;
  if ( !v8 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_924e359b40323068f2064522ccf2fc25_Traceguids);
    hKey = 0;
    if ( a3 )
      v10 = (const WCHAR *)(*(__int64 (__fastcall **)(enum WinRM_State *, const wchar_t *))(*(_QWORD *)a3 + 16LL))(
                             a3,
                             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WSMAN\\Migration\\Plugin");
    else
      v10 = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WSMAN\\Migration\\Plugin";
    v22 = v10;
    v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v10, 0, 0x109u, &hKey);
    v12 = v11;
    if ( v11 )
    {
      if ( v11 == 2 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_924e359b40323068f2064522ccf2fc25_Traceguids, v10);
        v13 = L"No plugin regkey found. Assuming State_VistaAndBefore";
LABEL_34:
        v14 = 1;
        *(_DWORD *)a2 = 1;
        anonymous_namespace_::LogMigrationMessage((__int64 *)a3, 0, v13);
        goto LABEL_43;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          43,
          (unsigned int)WPP_924e359b40323068f2064522ccf2fc25_Traceguids,
          (_DWORD)v10,
          v11);
      if ( this )
        (*(void (__fastcall **)(WSManConfigMigration *, __int64, const wchar_t *, _QWORD))(*(_QWORD *)this + 88LL))(
          this,
          1077134180,
          L"RegOpenKeyEx",
          v12);
      SetLastError(v12);
      anonymous_namespace_::LogMigrationMessage((__int64 *)a3, 2u, L"Failed while opening plugin regkey. Error %d", v12);
    }
    else
    {
      cchName = 256;
      v15 = RegEnumKeyExW(hKey, 0, Name, &cchName, 0, 0, 0, 0);
      v16 = v15;
      if ( v15 == 259 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_924e359b40323068f2064522ccf2fc25_Traceguids);
        v13 = L"Plugin regkey has no subkeys. Assuming State_VistaAndBefore";
        goto LABEL_34;
      }
      if ( !v15 )
      {
        anonymous_namespace_::LogMigrationMessage(
          (__int64 *)a3,
          0,
          L"Found Some plugins. Assuming State_WTROrWin7AndLater");
        *(_DWORD *)a2 = 2;
        v14 = 1;
        goto LABEL_43;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          45,
          (unsigned int)WPP_924e359b40323068f2064522ccf2fc25_Traceguids,
          (unsigned int)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WSMAN\\Migration\\Plugin",
          v15);
      if ( this )
        (*(void (__fastcall **)(WSManConfigMigration *, __int64, const wchar_t *, _QWORD))(*(_QWORD *)this + 88LL))(
          this,
          1077134180,
          L"RegEnumKeyEx",
          v16);
      SetLastError(v16);
      anonymous_namespace_::LogMigrationMessage(
        (__int64 *)a3,
        2u,
        L"Failed while enumerating plugin regkey. Error %d",
        v16);
    }
    v14 = 0;
LABEL_43:
    AutoCleanup<AutoBstr,unsigned short *>::ReleasePtr(&v22);
    AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(&hKey);
    AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(&phkResult);
    AutoCleanup<AutoBstr,unsigned short *>::ReleasePtr(&v21);
    return v14;
  }
  if ( v8 != 2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        49,
        (unsigned int)WPP_924e359b40323068f2064522ccf2fc25_Traceguids,
        (_DWORD)v7,
        v8);
    if ( this )
      (*(void (__fastcall **)(WSManConfigMigration *, __int64, const wchar_t *, _QWORD))(*(_QWORD *)this + 88LL))(
        this,
        1077134180,
        L"RegOpenKeyEx",
        v9);
    SetLastError(v9);
    anonymous_namespace_::LogMigrationMessage((__int64 *)a3, 2u, L"Failed while opening migration regkey. Error %d", v9);
    AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(&phkResult);
    AutoCleanup<AutoBstr,unsigned short *>::ReleasePtr(&v21);
    return 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (unsigned int)(v8 + 46),
      WPP_924e359b40323068f2064522ccf2fc25_Traceguids);
  anonymous_namespace_::LogMigrationMessage(
    (__int64 *)a3,
    0,
    L"Didn't find migration subkey. Assuming State_DontMigrate");
  *(_DWORD *)a2 = 0;
  AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(&phkResult);
  AutoCleanup<AutoBstr,unsigned short *>::ReleasePtr(&v21);
  return 1;
}

```

## disassembly

```asm
0x180190300  push    rbp
0x180190302  push    rbx
0x180190303  push    rsi
0x180190304  push    rdi
0x180190305  push    r13
0x180190307  push    r14
0x180190309  push    r15
0x18019030b  lea     rbp, [rsp-180h]
0x180190313  sub     rsp, 280h
0x18019031a  mov     rax, cs:__security_cookie
0x180190321  xor     rax, rsp
0x180190324  mov     [rbp+1B0h+var_40], rax
0x18019032b  mov     rdi, r8
0x18019032e  mov     r15, rdx
0x180190331  mov     rbx, rcx
0x180190334  test    rdx, rdx
0x180190337  jnz     short loc_180190361
0x180190339  mov     [rsp+2B0h+phkResult], rcx; struct IRequestContext *
0x18019033e  mov     r9d, 54Fh; unsigned int
0x180190344  lea     r8, a2563; "2563"
0x18019034b  mov     edx, 0A03h; unsigned int
0x180190350  lea     rcx, aOnecoreAdminWm_134; "onecore\\admin\\wmi\\wmx\\config\\wsman"...
0x180190357  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18019035c  jmp     loc_180190783
0x180190361  test    rdi, rdi
0x180190364  jz      short loc_180190381
0x180190366  mov     rax, [r8]
0x180190369  lea     rdx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180190370  mov     rcx, rdi
0x180190373  mov     rax, [rax+10h]
0x180190377  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019037c  mov     rsi, rax
0x18019037f  jmp     short loc_180190388
0x180190381  lea     rsi, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180190388  mov     [rsp+2B0h+var_258], rsi
0x18019038d  mov     dword ptr [r15], 0
0x180190394  lea     r13, WPP_GLOBAL_Control
0x18019039b  mov     rcx, cs:WPP_GLOBAL_Control
0x1801903a2  cmp     rcx, r13
0x1801903a5  jz      short loc_1801903C8
0x1801903a7  test    dword ptr [rcx+1Ch], 200000h
0x1801903ae  jz      short loc_1801903C8
0x1801903b0  mov     edx, 28h ; '('
0x1801903b5  mov     r9, rsi
0x1801903b8  lea     r8, WPP_924e359b40323068f2064522ccf2fc25_Traceguids
0x1801903bf  mov     rcx, [rcx+10h]
0x1801903c3  call    WPP_SF_S
0x1801903c8  mov     [rsp+2B0h+var_270], 0
0x1801903d1  lea     rax, [rsp+2B0h+var_270]
0x1801903d6  mov     [rsp+2B0h+phkResult], rax; phkResult
0x1801903db  mov     r9d, 101h; samDesired
0x1801903e1  xor     r8d, r8d; ulOptions
0x1801903e4  mov     rdx, rsi; lpSubKey
0x1801903e7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801903ee  call    cs:__imp_RegOpenKeyExW
0x1801903f4  mov     r14d, eax
0x1801903f7  test    eax, eax
0x1801903f9  jnz     loc_180190692
0x1801903ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180190406  cmp     rcx, r13
0x180190409  jz      short loc_180190427
0x18019040b  test    dword ptr [rcx+1Ch], 200000h
0x180190412  jz      short loc_180190427
0x180190414  lea     edx, [rax+29h]
0x180190417  lea     r8, WPP_924e359b40323068f2064522ccf2fc25_Traceguids
0x18019041e  mov     rcx, [rcx+10h]
0x180190422  call    WPP_SF_
0x180190427  mov     [rsp+2B0h+hKey], 0
0x180190430  test    rdi, rdi
0x180190433  jz      short loc_180190450
0x180190435  mov     rax, [rdi]
0x180190438  lea     rdx, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18019043f  mov     rcx, rdi
0x180190442  mov     rax, [rax+10h]
0x180190446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019044b  mov     r14, rax
0x18019044e  jmp     short loc_180190457
0x180190450  lea     r14, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180190457  mov     [rsp+2B0h+var_250], r14
0x18019045c  lea     rax, [rsp+2B0h+hKey]
0x180190461  mov     [rsp+2B0h+phkResult], rax; phkResult
0x180190466  mov     r9d, 109h; samDesired
0x18019046c  xor     r8d, r8d; ulOptions
0x18019046f  mov     rdx, r14; lpSubKey
0x180190472  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180190479  call    cs:__imp_RegOpenKeyExW
0x18019047f  mov     esi, eax
0x180190481  test    eax, eax
0x180190483  jz      loc_18019053F
0x180190489  cmp     eax, 2
0x18019048c  jnz     short loc_1801904C5
0x18019048e  mov     rcx, cs:WPP_GLOBAL_Control
0x180190495  cmp     rcx, r13
0x180190498  jz      short loc_1801904B9
0x18019049a  test    dword ptr [rcx+1Ch], 200000h
0x1801904a1  jz      short loc_1801904B9
0x1801904a3  lea     edx, [rax+28h]
0x1801904a6  mov     r9, r14
0x1801904a9  lea     r8, WPP_924e359b40323068f2064522ccf2fc25_Traceguids
0x1801904b0  mov     rcx, [rcx+10h]
0x1801904b4  call    WPP_SF_S
0x1801904b9  lea     r8, aNoPluginRegkey; "No plugin regkey found. Assuming State_"...
0x1801904c0  jmp     loc_1801905BC
0x1801904c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1801904cc  cmp     rcx, r13
0x1801904cf  jz      short loc_1801904F6
0x1801904d1  test    dword ptr [rcx+1Ch], 400000h
0x1801904d8  jz      short loc_1801904F6
0x1801904da  mov     edx, 2Bh ; '+'
0x1801904df  mov     dword ptr [rsp+2B0h+phkResult], esi
0x1801904e3  mov     r9, r14
0x1801904e6  lea     r8, WPP_924e359b40323068f2064522ccf2fc25_Traceguids
0x1801904ed  mov     rcx, [rcx+10h]
0x1801904f1  call    WPP_SF_Sd
0x1801904f6  test    rbx, rbx
0x1801904f9  jz      short loc_180190519
0x1801904fb  mov     rax, [rbx]
0x1801904fe  mov     r9d, esi
0x180190501  lea     r8, aRegopenkeyex; "RegOpenKeyEx"
0x180190508  mov     edx, 4033C364h
0x18019050d  mov     rcx, rbx
0x180190510  mov     rax, [rax+58h]
0x180190514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180190519  mov     ecx, esi; dwErrCode
0x18019051b  call    cs:__imp_SetLastError
0x180190521  lea     r8, aFailedWhileOpe_0; "Failed while opening plugin regkey. Err"...
0x180190528  mov     r9d, esi
0x18019052b  mov     edx, 2
0x180190530  mov     rcx, rdi
0x180190533  call    _anonymous_namespace___LogMigrationMessage
0x180190538  xor     ebx, ebx
0x18019053a  jmp     loc_180190660
0x18019053f  mov     [rsp+2B0h+cchName], 100h
0x180190547  mov     [rsp+2B0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180190550  mov     [rsp+2B0h+lpcchClass], 0; lpcchClass
0x180190559  mov     [rsp+2B0h+lpClass], 0; lpClass
0x180190562  mov     [rsp+2B0h+phkResult], 0; lpReserved
0x18019056b  lea     r9, [rsp+2B0h+cchName]; lpcchName
0x180190570  lea     r8, [rsp+2B0h+Name]; lpName
0x180190575  xor     edx, edx; dwIndex
0x180190577  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18019057c  call    cs:__imp_RegEnumKeyExW
0x180190582  mov     esi, eax
0x180190584  cmp     eax, 103h
0x180190589  jnz     short loc_1801905D3
0x18019058b  mov     rcx, cs:WPP_GLOBAL_Control
0x180190592  cmp     rcx, r13
0x180190595  jz      short loc_1801905B5
0x180190597  test    dword ptr [rcx+1Ch], 200000h
0x18019059e  jz      short loc_1801905B5
0x1801905a0  mov     edx, 2Ch ; ','
0x1801905a5  lea     r8, WPP_924e359b40323068f2064522ccf2fc25_Traceguids
0x1801905ac  mov     rcx, [rcx+10h]
0x1801905b0  call    WPP_SF_
0x1801905b5  lea     r8, aPluginRegkeyHa; "Plugin regkey has no subkeys. Assuming "...
0x1801905bc  mov     ebx, 1
0x1801905c1  mov     [r15], ebx
0x1801905c4  xor     edx, edx
0x1801905c6  mov     rcx, rdi
0x1801905c9  call    _anonymous_namespace___LogMigrationMessage
0x1801905ce  jmp     loc_180190660
0x1801905d3  test    esi, esi
0x1801905d5  jz      short loc_180190643
0x1801905d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1801905de  cmp     rcx, r13
0x1801905e1  jz      short loc_18019060C
0x1801905e3  test    dword ptr [rcx+1Ch], 400000h
0x1801905ea  jz      short loc_18019060C
0x1801905ec  mov     edx, 2Dh ; '-'
0x1801905f1  mov     dword ptr [rsp+2B0h+phkResult], esi
0x1801905f5  lea     r9, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1801905fc  lea     r8, WPP_924e359b40323068f2064522ccf2fc25_Traceguids
0x180190603  mov     rcx, [rcx+10h]
0x180190607  call    WPP_SF_Sd
0x18019060c  test    rbx, rbx
0x18019060f  jz      short loc_18019062F
0x180190611  mov     rax, [rbx]
0x180190614  mov     r9d, esi
0x180190617  lea     r8, aRegenumkeyex; "RegEnumKeyEx"
0x18019061e  mov     edx, 4033C364h
0x180190623  mov     rcx, rbx
0x180190626  mov     rax, [rax+58h]
0x18019062a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019062f  mov     ecx, esi; dwErrCode
0x180190631  call    cs:__imp_SetLastError
0x180190637  lea     r8, aFailedWhileEnu; "Failed while enumerating plugin regkey."...
0x18019063e  jmp     loc_180190528
0x180190643  lea     r8, aFoundSomePlugi; "Found Some plugins. Assuming State_WTRO"...
0x18019064a  xor     edx, edx
0x18019064c  mov     rcx, rdi
0x18019064f  call    _anonymous_namespace___LogMigrationMessage
0x180190654  mov     dword ptr [r15], 2
0x18019065b  mov     ebx, 1
0x180190660  lea     rcx, [rsp+2B0h+var_250]
0x180190665  call    ?ReleasePtr@?$AutoCleanup@VAutoBstr@@PEAG@@AEAAXXZ; AutoCleanup<AutoBstr,ushort *>::ReleasePtr(void)
0x18019066a  nop
0x18019066b  lea     rcx, [rsp+2B0h+hKey]
0x180190670  call    ??1?$AutoCleanup@VAutoRegKey@@PEAUHKEY__@@@@QEAA@XZ; AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(void)
0x180190675  nop
0x180190676  lea     rcx, [rsp+2B0h+var_270]
0x18019067b  call    ??1?$AutoCleanup@VAutoRegKey@@PEAUHKEY__@@@@QEAA@XZ; AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(void)
0x180190680  nop
0x180190681  lea     rcx, [rsp+2B0h+var_258]
0x180190686  call    ?ReleasePtr@?$AutoCleanup@VAutoBstr@@PEAG@@AEAAXXZ; AutoCleanup<AutoBstr,ushort *>::ReleasePtr(void)
0x18019068b  mov     eax, ebx
0x18019068d  jmp     loc_180190785
0x180190692  cmp     r14d, 2
0x180190696  jnz     short loc_1801906F8
0x180190698  mov     rcx, cs:WPP_GLOBAL_Control
0x18019069f  cmp     rcx, r13
0x1801906a2  jz      short loc_1801906C1
0x1801906a4  test    dword ptr [rcx+1Ch], 200000h
0x1801906ab  jz      short loc_1801906C1
0x1801906ad  lea     edx, [r14+2Eh]
0x1801906b1  lea     r8, WPP_924e359b40323068f2064522ccf2fc25_Traceguids
0x1801906b8  mov     rcx, [rcx+10h]
0x1801906bc  call    WPP_SF_
0x1801906c1  lea     r8, aDidnTFindMigra; "Didn't find migration subkey. Assuming "...
0x1801906c8  xor     edx, edx
0x1801906ca  mov     rcx, rdi
0x1801906cd  call    _anonymous_namespace___LogMigrationMessage
0x1801906d2  mov     dword ptr [r15], 0
0x1801906d9  lea     rcx, [rsp+2B0h+var_270]
0x1801906de  call    ??1?$AutoCleanup@VAutoRegKey@@PEAUHKEY__@@@@QEAA@XZ; AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(void)
0x1801906e3  nop
0x1801906e4  lea     rcx, [rsp+2B0h+var_258]
0x1801906e9  call    ?ReleasePtr@?$AutoCleanup@VAutoBstr@@PEAG@@AEAAXXZ; AutoCleanup<AutoBstr,ushort *>::ReleasePtr(void)
0x1801906ee  mov     eax, 1
0x1801906f3  jmp     loc_180190785
0x1801906f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1801906ff  cmp     rcx, r13
0x180190702  jz      short loc_18019072A
0x180190704  test    dword ptr [rcx+1Ch], 400000h
0x18019070b  jz      short loc_18019072A
0x18019070d  mov     edx, 31h ; '1'
0x180190712  mov     dword ptr [rsp+2B0h+phkResult], r14d
0x180190717  mov     r9, rsi
0x18019071a  lea     r8, WPP_924e359b40323068f2064522ccf2fc25_Traceguids
0x180190721  mov     rcx, [rcx+10h]
0x180190725  call    WPP_SF_Sd
0x18019072a  test    rbx, rbx
0x18019072d  jz      short loc_18019074D
0x18019072f  mov     rax, [rbx]
0x180190732  mov     r9d, r14d
0x180190735  lea     r8, aRegopenkeyex; "RegOpenKeyEx"
0x18019073c  mov     edx, 4033C364h
0x180190741  mov     rcx, rbx
0x180190744  mov     rax, [rax+58h]
0x180190748  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019074d  mov     ecx, r14d; dwErrCode
0x180190750  call    cs:__imp_SetLastError
0x180190756  mov     r9d, r14d
0x180190759  lea     r8, aFailedWhileOpe; "Failed while opening migration regkey. "...
0x180190760  mov     edx, 2
0x180190765  mov     rcx, rdi
0x180190768  call    _anonymous_namespace___LogMigrationMessage
0x18019076d  nop
0x18019076e  lea     rcx, [rsp+2B0h+var_270]
0x180190773  call    ??1?$AutoCleanup@VAutoRegKey@@PEAUHKEY__@@@@QEAA@XZ; AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(void)
0x180190778  nop
0x180190779  lea     rcx, [rsp+2B0h+var_258]
0x18019077e  call    ?ReleasePtr@?$AutoCleanup@VAutoBstr@@PEAG@@AEAAXXZ; AutoCleanup<AutoBstr,ushort *>::ReleasePtr(void)
0x180190783  xor     eax, eax
0x180190785  mov     rcx, [rbp+1B0h+var_40]
0x18019078c  xor     rcx, rsp; StackCookie
0x18019078f  call    __security_check_cookie
0x180190794  add     rsp, 280h
0x18019079b  pop     r15
0x18019079d  pop     r14
0x18019079f  pop     r13
0x1801907a1  pop     rdi
0x1801907a2  pop     rsi
0x1801907a3  pop     rbx
0x1801907a4  pop     rbp
0x1801907a5  retn
```
