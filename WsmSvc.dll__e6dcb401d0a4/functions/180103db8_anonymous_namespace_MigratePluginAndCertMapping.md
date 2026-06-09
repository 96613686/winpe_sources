# _anonymous_namespace_::MigratePluginAndCertMapping

- ea: `0x180103db8`
- end: `0x1801042d2`
- name: `_anonymous_namespace_::MigratePluginAndCertMapping`
- size: `1306`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180190860`

## callees

- `0x180008920`
- `0x180035ee0`
- `0x1800621e0`
- `0x1800a901c`
- `0x1800bac30`
- `0x1800d42a8`
- `0x1800e8a50`
- `0x1800ed980`
- `0x1801013ac`
- `0x180103db8`
- `0x1801902b0`
- `0x1801930d0`
- `0x180199c88`
- `0x18019b1d8`
- `0x1801ba1b0`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180104223`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180104223`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180103e99`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180103e99`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x18010424b`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x18010424b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180103e43`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180103f4f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801041d6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180103e43`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180103f4f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801041d6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180103fae`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180103fae`

## string_xrefs

- `0x180103e09`: `SOFTWARE\Microsoft\Windows\CurrentVersion\WSMAN\Plugin`
- `0x180103edd`: `SEL Plugin`
- `0x180103ec5`: `Event Forwarding Plugin`
- `0x180103ef9`: `Plugin Migration Migrating plugin - %ls`
- `0x180104209`: `RegOpenKeyEx`
- `0x180103e4f`: `Plugin Migration RegOpenKeyEx for plugin Source returned %d`
- `0x180104072`: `Plugin Migration Skipping Migrating Inbox plugin - %ls`
- `0x180103f5a`: `Plugin Migration Plugin registration check returned %d`
- `0x180103fa0`: `ConfigXML`
- `0x1801040d7`: `Plugin Migration ERROR: Can not start the ConfigUpdate.`
- `0x1801040c5`: `Plugin Migration ERROR: in MakeChanges().`
- `0x1801040ce`: `Plugin Migration ERROR: in AddChange().`
- `0x180104106`: `Plugin Migration ERROR: RegGetValue returned %lu.`
- `0x18010409d`: `Plugin Migration ERROR: RegEnumKeyEx returned %lu. on index = %d`
- `0x1801041ea`: `Migration ERROR in MigratePluginAndCertMapping: RegOpenKeyEx returned %lu for %ls `
- `0x180104279`: `RegCopyTree`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall anonymous_namespace_::MigratePluginAndCertMapping(
        __int64 *a1,
        struct IRequestContext *a2,
        HKEY a3,
        HKEY a4)
{
  HKEY v4; // rbx
  DWORD v8; // r12d
  const WCHAR *v9; // rdx
  __int64 v10; // r15
  unsigned int v11; // eax
  HKEY v12; // rdi
  __int64 v13; // rbx
  unsigned int ValueW; // eax
  struct ConfigUpdate *started; // rax
  HKEY v16; // rbx
  HKEY *p_hKey; // rcx
  WCHAR *v19; // rbx
  unsigned int v20; // eax
  DWORD v21; // edi
  DWORD v22; // ecx
  unsigned int v23; // eax
  DWORD v24; // ebx
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  HKEY v26; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKeyDest; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  const WCHAR *v29; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cchName; // [rsp+60h] [rbp-A0h] BYREF
  DWORD pcbData; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY hKeySrc; // [rsp+68h] [rbp-98h]
  void **v33; // [rsp+70h] [rbp-90h] BYREF
  int v34; // [rsp+78h] [rbp-88h]
  WCHAR *v35; // [rsp+80h] [rbp-80h]
  int v36; // [rsp+88h] [rbp-78h]
  WCHAR Name[512]; // [rsp+90h] [rbp-70h] BYREF

  v4 = a4;
  hKeySrc = a4;
  if ( a3 )
  {
    v8 = 0;
    hKey = 0;
    v9 = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WSMAN\\Plugin";
    if ( a1 )
      v9 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64 *, const WCHAR *))(*a1 + 16))(
                            a1,
                            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WSMAN\\Plugin");
    v29 = v9;
    v10 = (unsigned int)RegOpenKeyExW(HKEY_LOCAL_MACHINE, v9, 0, 0xF003Fu, &hKey);
    anonymous_namespace_::LogMigrationMessage(
      a1,
      2u,
      L"Plugin Migration RegOpenKeyEx for plugin Source returned %d",
      v10);
    while ( !(_DWORD)v10 )
    {
      cchName = 512;
      v11 = RegEnumKeyExW(a3, v8, Name, &cchName, 0, 0, 0, 0);
      LODWORD(v10) = v11;
      ++v8;
      if ( v11 )
      {
        if ( v11 != 259 )
        {
          LODWORD(phkResult) = v8;
          anonymous_namespace_::LogMigrationMessage(
            a1,
            2u,
            L"Plugin Migration ERROR: RegEnumKeyEx returned %lu. on index = %d",
            v11,
            phkResult);
          (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a2 + 72LL))(a2, (unsigned int)v10);
          goto LABEL_29;
        }
      }
      else if ( (unsigned int)StringCchEqualsCI(Name, (wchar_t *)L"WMI Provider")
             || (unsigned int)StringCchEqualsCI(Name, (wchar_t *)L"Event Forwarding Plugin")
             || (unsigned int)StringCchEqualsCI(Name, (wchar_t *)L"SEL Plugin") )
      {
        anonymous_namespace_::LogMigrationMessage(
          a1,
          2u,
          L"Plugin Migration Skipping Migrating Inbox plugin - %ls",
          Name);
      }
      else
      {
        anonymous_namespace_::LogMigrationMessage(a1, 2u, L"Plugin Migration Migrating plugin - %ls", Name);
        v12 = (HKEY)WSManMemory::Alloc(20480, 0, 0);
        hKeyDest = v12;
        if ( !v12 )
        {
          (*(void (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 24LL))(a2);
          goto LABEL_28;
        }
        v26 = 0;
        v13 = (unsigned int)RegOpenKeyExW(hKey, Name, 0, 0xF003Fu, &v26);
        anonymous_namespace_::LogMigrationMessage(
          a1,
          2u,
          L"Plugin Migration Plugin registration check returned %d",
          v13);
        AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(&v26);
        pcbData = 10240;
        ValueW = RegGetValueW(a3, Name, L"ConfigXML", 2u, 0, v12, &pcbData);
        LODWORD(v10) = ValueW;
        if ( ValueW )
        {
          anonymous_namespace_::LogMigrationMessage(
            a1,
            2u,
            L"Plugin Migration ERROR: RegGetValue returned %lu.",
            ValueW);
          (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a2 + 72LL))(a2, (unsigned int)v10);
          goto LABEL_28;
        }
        v33 = &PLUGIN_IDENTITY::`vftable';
        v36 = 0;
        v34 = 4;
        v35 = Name;
        v26 = 0;
        if ( (_DWORD)v13 )
          started = ConfigUpdate::AddPluginConfig(a2, (struct PLUGIN_IDENTITY *)&v33, 1);
        else
          started = ConfigUpdate::StartUpdates(a2, (struct WSMANCONFIGTABLE_IDENTITY *)&v33, 1);
        AutoCleanup<AutoDelete<ConfigUpdate>,ConfigUpdate *>::operator=(&v26, started);
        v16 = v26;
        if ( !v26 )
        {
          anonymous_namespace_::LogMigrationMessage(a1, 2u, L"Plugin Migration ERROR: Can not start the ConfigUpdate.");
LABEL_25:
          AutoCleanup<AutoDelete<ConfigUpdate>,ConfigUpdate *>::ReleasePtr(&v26);
          PLUGIN_IDENTITY::~PLUGIN_IDENTITY((PLUGIN_IDENTITY *)&v33);
LABEL_28:
          AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&hKeyDest);
LABEL_29:
          AutoCleanup<AutoBstr,unsigned short *>::ReleasePtr(&v29);
          p_hKey = &hKey;
          goto LABEL_30;
        }
        if ( !(unsigned int)ConfigUpdate::PutConfigXml((ConfigUpdate *)v26, a2, (const unsigned __int16 *)v12) )
        {
          anonymous_namespace_::LogMigrationMessage(a1, 2u, L"Plugin Migration ERROR: in AddChange().");
          goto LABEL_25;
        }
        if ( !(unsigned int)ConfigUpdate::MakeChanges((unsigned int *)v16, a2) )
        {
          anonymous_namespace_::LogMigrationMessage(a1, 2u, L"Plugin Migration ERROR: in MakeChanges().");
          goto LABEL_25;
        }
        AutoCleanup<AutoDelete<ConfigUpdate>,ConfigUpdate *>::ReleasePtr(&v26);
        PLUGIN_IDENTITY::~PLUGIN_IDENTITY((PLUGIN_IDENTITY *)&v33);
        AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&hKeyDest);
      }
    }
    AutoCleanup<AutoBstr,unsigned short *>::ReleasePtr(&v29);
    AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(&hKey);
    v4 = hKeySrc;
  }
  if ( !v4 )
    return 1;
  hKeyDest = 0;
  if ( a1 )
    v19 = (WCHAR *)(*(__int64 (__fastcall **)(__int64 *, const unsigned __int16 *))(*a1 + 16))(
                     a1,
                     L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WSMAN\\CertMapping");
  else
    v19 = (WCHAR *)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WSMAN\\CertMapping";
  v26 = (HKEY)v19;
  v20 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v19, 0, 0xF003Fu, &hKeyDest);
  v21 = v20;
  if ( v20 )
  {
    anonymous_namespace_::LogMigrationMessage(
      a1,
      2u,
      L"Migration ERROR in MigratePluginAndCertMapping: RegOpenKeyEx returned %lu for %ls ",
      v20,
      v19);
    if ( a2 )
      (*(void (__fastcall **)(struct IRequestContext *, __int64, const wchar_t *, _QWORD))(*(_QWORD *)a2 + 88LL))(
        a2,
        1077134180,
        L"RegOpenKeyEx",
        v21);
    v22 = v21;
    goto LABEL_40;
  }
  v23 = RegCopyTreeW(hKeySrc, 0, hKeyDest);
  v24 = v23;
  if ( !v23 )
  {
    AutoCleanup<AutoBstr,unsigned short *>::ReleasePtr(&v26);
    AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(&hKeyDest);
    return 1;
  }
  anonymous_namespace_::LogMigrationMessage(a1, 2u, L"Failed to migrate CertMapping. Error: %lu", v23);
  if ( a2 )
    (*(void (__fastcall **)(struct IRequestContext *, __int64, const wchar_t *, _QWORD))(*(_QWORD *)a2 + 88LL))(
      a2,
      1077134180,
      L"RegCopyTree",
      v24);
  v22 = v24;
LABEL_40:
  SetLastError(v22);
  AutoCleanup<AutoBstr,unsigned short *>::ReleasePtr(&v26);
  p_hKey = &hKeyDest;
LABEL_30:
  AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(p_hKey);
  return 0;
}

```

## disassembly

```asm
0x180103db8  push    rbp
0x180103dba  push    rbx
0x180103dbb  push    rsi
0x180103dbc  push    rdi
0x180103dbd  push    r12
0x180103dbf  push    r13
0x180103dc1  push    r14
0x180103dc3  push    r15
0x180103dc5  lea     rbp, [rsp-3A8h]
0x180103dcd  sub     rsp, 4A8h
0x180103dd4  mov     rax, cs:__security_cookie
0x180103ddb  xor     rax, rsp
0x180103dde  mov     [rbp+3E0h+var_50], rax
0x180103de5  mov     rbx, r9
0x180103de8  mov     [rsp+4E0h+hKeySrc], rbx
0x180103ded  mov     r13, r8
0x180103df0  mov     r14, rdx
0x180103df3  mov     rsi, rcx
0x180103df6  xor     edi, edi
0x180103df8  test    r8, r8
0x180103dfb  jz      loc_18010417F
0x180103e01  mov     r12d, edi
0x180103e04  mov     [rsp+4E0h+hKey], rdi
0x180103e09  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180103e10  test    rcx, rcx
0x180103e13  jz      short loc_180103E24
0x180103e15  mov     rax, [rcx]
0x180103e18  mov     rax, [rax+10h]
0x180103e1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103e21  mov     rdx, rax; lpSubKey
0x180103e24  mov     [rsp+4E0h+var_488], rdx
0x180103e29  lea     rax, [rsp+4E0h+hKey]
0x180103e2e  mov     [rsp+4E0h+phkResult], rax; phkResult
0x180103e33  mov     r9d, 0F003Fh; samDesired
0x180103e39  xor     r8d, r8d; ulOptions
0x180103e3c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180103e43  call    cs:__imp_RegOpenKeyExW
0x180103e49  mov     r15d, eax
0x180103e4c  mov     r9d, eax
0x180103e4f  lea     r8, aPluginMigratio_9; "Plugin Migration RegOpenKeyEx for plugi"...
0x180103e56  mov     ebx, 2
0x180103e5b  mov     edx, ebx
0x180103e5d  mov     rcx, rsi
0x180103e60  call    _anonymous_namespace___LogMigrationMessage
0x180103e65  test    r15d, r15d
0x180103e68  jnz     loc_180104165
0x180103e6e  mov     [rsp+4E0h+cchName], 200h
0x180103e76  mov     [rsp+4E0h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x180103e7b  mov     [rsp+4E0h+lpcchClass], rdi; lpcchClass
0x180103e80  mov     [rsp+4E0h+lpClass], rdi; lpClass
0x180103e85  mov     [rsp+4E0h+phkResult], rdi; lpReserved
0x180103e8a  lea     r9, [rsp+4E0h+cchName]; lpcchName
0x180103e8f  lea     r8, [rbp+3E0h+Name]; lpName
0x180103e93  mov     edx, r12d; dwIndex
0x180103e96  mov     rcx, r13; hKey
0x180103e99  call    cs:__imp_RegEnumKeyExW
0x180103e9f  mov     r15d, eax
0x180103ea2  inc     r12d
0x180103ea5  test    eax, eax
0x180103ea7  jnz     loc_180104088
0x180103ead  lea     rdx, aWmiProvider; "WMI Provider"
0x180103eb4  lea     rcx, [rbp+3E0h+Name]; String1
0x180103eb8  call    ?StringCchEqualsCI@@YAHPEBG0@Z; StringCchEqualsCI(ushort const *,ushort const *)
0x180103ebd  test    eax, eax
0x180103ebf  jnz     loc_18010406E
0x180103ec5  lea     rdx, aEventForwardin; "Event Forwarding Plugin"
0x180103ecc  lea     rcx, [rbp+3E0h+Name]; String1
0x180103ed0  call    ?StringCchEqualsCI@@YAHPEBG0@Z; StringCchEqualsCI(ushort const *,ushort const *)
0x180103ed5  test    eax, eax
0x180103ed7  jnz     loc_18010406E
0x180103edd  lea     rdx, aSelPlugin; "SEL Plugin"
0x180103ee4  lea     rcx, [rbp+3E0h+Name]; String1
0x180103ee8  call    ?StringCchEqualsCI@@YAHPEBG0@Z; StringCchEqualsCI(ushort const *,ushort const *)
0x180103eed  test    eax, eax
0x180103eef  jnz     loc_18010406E
0x180103ef5  lea     r9, [rbp+3E0h+Name]
0x180103ef9  lea     r8, aPluginMigratio_5; "Plugin Migration Migrating plugin - %ls"
0x180103f00  mov     edx, ebx
0x180103f02  mov     rcx, rsi
0x180103f05  call    _anonymous_namespace___LogMigrationMessage
0x180103f0a  xor     r8d, r8d
0x180103f0d  xor     edx, edx
0x180103f0f  mov     ecx, 5000h
0x180103f14  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x180103f19  mov     rdi, rax
0x180103f1c  mov     [rsp+4E0h+hKeyDest], rax
0x180103f21  test    rax, rax
0x180103f24  jz      loc_18010412E
0x180103f2a  mov     [rsp+4E0h+var_4A0], 0
0x180103f33  lea     rax, [rsp+4E0h+var_4A0]
0x180103f38  mov     [rsp+4E0h+phkResult], rax; phkResult
0x180103f3d  mov     r9d, 0F003Fh; samDesired
0x180103f43  xor     r8d, r8d; ulOptions
0x180103f46  lea     rdx, [rbp+3E0h+Name]; lpSubKey
0x180103f4a  mov     rcx, [rsp+4E0h+hKey]; hKey
0x180103f4f  call    cs:__imp_RegOpenKeyExW
0x180103f55  mov     ebx, eax
0x180103f57  mov     r9d, eax
0x180103f5a  lea     r8, aPluginMigratio_12; "Plugin Migration Plugin registration ch"...
0x180103f61  mov     r15d, 2
0x180103f67  mov     edx, r15d
0x180103f6a  mov     rcx, rsi
0x180103f6d  call    _anonymous_namespace___LogMigrationMessage
0x180103f72  nop
0x180103f73  lea     rcx, [rsp+4E0h+var_4A0]
0x180103f78  call    ??1?$AutoCleanup@VAutoRegKey@@PEAUHKEY__@@@@QEAA@XZ; AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(void)
0x180103f7d  mov     [rsp+4E0h+pcbData], 2800h
0x180103f85  lea     rax, [rsp+4E0h+pcbData]
0x180103f8a  mov     [rsp+4E0h+lpcchClass], rax; pcbData
0x180103f8f  mov     [rsp+4E0h+lpClass], rdi; pvData
0x180103f94  mov     [rsp+4E0h+phkResult], 0; pdwType
0x180103f9d  mov     r9d, r15d; dwFlags
0x180103fa0  lea     r8, Value; "ConfigXML"
0x180103fa7  lea     rdx, [rbp+3E0h+Name]; lpSubKey
0x180103fab  mov     rcx, r13; hkey
0x180103fae  call    cs:__imp_RegGetValueW
0x180103fb4  mov     r15d, eax
0x180103fb7  test    eax, eax
0x180103fb9  jnz     loc_180104103
0x180103fbf  lea     rax, ??_7PLUGIN_IDENTITY@@6B@; const PLUGIN_IDENTITY::`vftable'
0x180103fc6  mov     [rsp+4E0h+var_470], rax
0x180103fcb  mov     [rbp+3E0h+var_458], r15d
0x180103fcf  mov     [rsp+4E0h+var_468], 4
0x180103fd7  lea     rax, [rbp+3E0h+Name]
0x180103fdb  mov     [rbp+3E0h+var_460], rax
0x180103fdf  mov     [rsp+4E0h+var_4A0], 0
0x180103fe8  lea     r8d, [r15+1]; int
0x180103fec  lea     rdx, [rsp+4E0h+var_470]; struct PLUGIN_IDENTITY *
0x180103ff1  mov     rcx, r14; struct IRequestContext *
0x180103ff4  test    ebx, ebx
0x180103ff6  jnz     short loc_180103FFF
0x180103ff8  call    ?StartUpdates@ConfigUpdate@@SAPEAV1@PEAVIRequestContext@@PEAVWSMANCONFIGTABLE_IDENTITY@@H@Z; ConfigUpdate::StartUpdates(IRequestContext *,WSMANCONFIGTABLE_IDENTITY *,int)
0x180103ffd  jmp     short loc_180104004
0x180103fff  call    ?AddPluginConfig@ConfigUpdate@@SAPEAV1@PEAVIRequestContext@@PEAVPLUGIN_IDENTITY@@H@Z; ConfigUpdate::AddPluginConfig(IRequestContext *,PLUGIN_IDENTITY *,int)
0x180104004  mov     rdx, rax
0x180104007  lea     rcx, [rsp+4E0h+var_4A0]
0x18010400c  call    ??4?$AutoCleanup@V?$AutoDelete@VConfigUpdate@@@@PEAVConfigUpdate@@@@QEAAAEAV?$AutoDelete@VConfigUpdate@@@@PEAVConfigUpdate@@@Z; AutoCleanup<AutoDelete<ConfigUpdate>,ConfigUpdate *>::operator=(ConfigUpdate *)
0x180104011  mov     rbx, [rsp+4E0h+var_4A0]
0x180104016  test    rbx, rbx
0x180104019  jz      loc_1801040D7
0x18010401f  mov     r8, rdi; unsigned __int16 *
0x180104022  mov     rdx, r14; struct IRequestContext *
0x180104025  mov     rcx, rbx; this
0x180104028  call    ?PutConfigXml@ConfigUpdate@@QEAAHPEAVIRequestContext@@PEBG@Z; ConfigUpdate::PutConfigXml(IRequestContext *,ushort const *)
0x18010402d  xor     edi, edi
0x18010402f  test    eax, eax
0x180104031  jz      loc_1801040CE
0x180104037  mov     rdx, r14; struct IRequestContext *
0x18010403a  mov     rcx, rbx; lpSubKey
0x18010403d  call    ?MakeChanges@ConfigUpdate@@QEAAHPEAVIRequestContext@@@Z; ConfigUpdate::MakeChanges(IRequestContext *)
0x180104042  test    eax, eax
0x180104044  jz      short loc_1801040C5
0x180104046  lea     rcx, [rsp+4E0h+var_4A0]
0x18010404b  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDelete@VConfigUpdate@@@@PEAVConfigUpdate@@@@AEAAXXZ; AutoCleanup<AutoDelete<ConfigUpdate>,ConfigUpdate *>::ReleasePtr(void)
0x180104050  nop
0x180104051  lea     rcx, [rsp+4E0h+var_470]; this
0x180104056  call    ??1PLUGIN_IDENTITY@@UEAA@XZ; PLUGIN_IDENTITY::~PLUGIN_IDENTITY(void)
0x18010405b  nop
0x18010405c  lea     rcx, [rsp+4E0h+hKeyDest]
0x180104061  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x180104066  lea     ebx, [rdi+2]
0x180104069  jmp     loc_180103E65
0x18010406e  lea     r9, [rbp+3E0h+Name]
0x180104072  lea     r8, aPluginMigratio_7; "Plugin Migration Skipping Migrating Inb"...
0x180104079  mov     edx, ebx
0x18010407b  mov     rcx, rsi
0x18010407e  call    _anonymous_namespace___LogMigrationMessage
0x180104083  jmp     loc_180103E65
0x180104088  cmp     r15d, 103h
0x18010408f  jz      loc_180103E65
0x180104095  mov     dword ptr [rsp+4E0h+phkResult], r12d
0x18010409a  mov     r9d, r15d
0x18010409d  lea     r8, aPluginMigratio_10; "Plugin Migration ERROR: RegEnumKeyEx re"...
0x1801040a4  mov     edx, ebx
0x1801040a6  mov     rcx, rsi
0x1801040a9  call    _anonymous_namespace___LogMigrationMessage
0x1801040ae  mov     rax, [r14]
0x1801040b1  mov     edx, r15d
0x1801040b4  mov     rcx, r14
0x1801040b7  mov     rax, [rax+48h]
0x1801040bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801040c0  jmp     loc_180104149
0x1801040c5  lea     r8, aPluginMigratio_0; "Plugin Migration ERROR: in MakeChanges("...
0x1801040cc  jmp     short loc_1801040DE
0x1801040ce  lea     r8, aPluginMigratio_3; "Plugin Migration ERROR: in AddChange()."
0x1801040d5  jmp     short loc_1801040DE
0x1801040d7  lea     r8, aPluginMigratio_4; "Plugin Migration ERROR: Can not start t"...
0x1801040de  mov     edx, 2
0x1801040e3  mov     rcx, rsi
0x1801040e6  call    _anonymous_namespace___LogMigrationMessage
0x1801040eb  nop
0x1801040ec  lea     rcx, [rsp+4E0h+var_4A0]
0x1801040f1  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDelete@VConfigUpdate@@@@PEAVConfigUpdate@@@@AEAAXXZ; AutoCleanup<AutoDelete<ConfigUpdate>,ConfigUpdate *>::ReleasePtr(void)
0x1801040f6  nop
0x1801040f7  lea     rcx, [rsp+4E0h+var_470]; this
0x1801040fc  call    ??1PLUGIN_IDENTITY@@UEAA@XZ; PLUGIN_IDENTITY::~PLUGIN_IDENTITY(void)
0x180104101  jmp     short loc_18010413E
0x180104103  mov     r9d, r15d
0x180104106  lea     r8, aPluginMigratio_13; "Plugin Migration ERROR: RegGetValue ret"...
0x18010410d  mov     edx, 2
0x180104112  mov     rcx, rsi
0x180104115  call    _anonymous_namespace___LogMigrationMessage
0x18010411a  mov     rax, [r14]
0x18010411d  mov     edx, r15d
0x180104120  mov     rcx, r14
0x180104123  mov     rax, [rax+48h]
0x180104127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010412c  jmp     short loc_18010413E
0x18010412e  mov     rax, [r14]
0x180104131  mov     rcx, r14
0x180104134  mov     rax, [rax+18h]
0x180104138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010413d  nop
0x18010413e  lea     rcx, [rsp+4E0h+hKeyDest]
0x180104143  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x180104148  nop
0x180104149  lea     rcx, [rsp+4E0h+var_488]
0x18010414e  call    ?ReleasePtr@?$AutoCleanup@VAutoBstr@@PEAG@@AEAAXXZ; AutoCleanup<AutoBstr,ushort *>::ReleasePtr(void)
0x180104153  nop
0x180104154  lea     rcx, [rsp+4E0h+hKey]
0x180104159  call    ??1?$AutoCleanup@VAutoRegKey@@PEAUHKEY__@@@@QEAA@XZ; AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(void)
0x18010415e  xor     eax, eax
0x180104160  jmp     loc_1801042AF
0x180104165  lea     rcx, [rsp+4E0h+var_488]
0x18010416a  call    ?ReleasePtr@?$AutoCleanup@VAutoBstr@@PEAG@@AEAAXXZ; AutoCleanup<AutoBstr,ushort *>::ReleasePtr(void)
0x18010416f  nop
0x180104170  lea     rcx, [rsp+4E0h+hKey]
0x180104175  call    ??1?$AutoCleanup@VAutoRegKey@@PEAUHKEY__@@@@QEAA@XZ; AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(void)
0x18010417a  mov     rbx, [rsp+4E0h+hKeySrc]
0x18010417f  test    rbx, rbx
0x180104182  jz      loc_1801042AA
0x180104188  mov     [rsp+4E0h+hKeyDest], rdi
0x18010418d  test    rsi, rsi
0x180104190  jz      short loc_1801041AD
0x180104192  mov     rax, [rsi]
0x180104195  lea     rdx, aSoftwareMicros_14; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18010419c  mov     rcx, rsi
0x18010419f  mov     rax, [rax+10h]
0x1801041a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801041a8  mov     rbx, rax
0x1801041ab  jmp     short loc_1801041B4
0x1801041ad  lea     rbx, aSoftwareMicros_14; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1801041b4  mov     [rsp+4E0h+var_4A0], rbx
0x1801041b9  lea     rax, [rsp+4E0h+hKeyDest]
0x1801041be  mov     [rsp+4E0h+phkResult], rax; phkResult
0x1801041c3  mov     r9d, 0F003Fh; samDesired
0x1801041c9  xor     r8d, r8d; ulOptions
0x1801041cc  mov     rdx, rbx; lpSubKey
0x1801041cf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801041d6  call    cs:__imp_RegOpenKeyExW
0x1801041dc  mov     edi, eax
0x1801041de  test    eax, eax
0x1801041e0  jz      short loc_18010423F
0x1801041e2  mov     [rsp+4E0h+phkResult], rbx
0x1801041e7  mov     r9d, eax
0x1801041ea  lea     r8, aMigrationError_1; "Migration ERROR in MigratePluginAndCert"...
0x1801041f1  mov     edx, 2
0x1801041f6  mov     rcx, rsi
0x1801041f9  call    _anonymous_namespace___LogMigrationMessage
0x1801041fe  test    r14, r14
0x180104201  jz      short loc_180104221
0x180104203  mov     rax, [r14]
0x180104206  mov     r9d, edi
0x180104209  lea     r8, aRegopenkeyex; "RegOpenKeyEx"
0x180104210  mov     edx, 4033C364h
0x180104215  mov     rcx, r14
0x180104218  mov     rax, [rax+58h]
0x18010421c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180104221  mov     ecx, edi; dwErrCode
0x180104223  call    cs:__imp_SetLastError
0x180104229  nop
0x18010422a  lea     rcx, [rsp+4E0h+var_4A0]
0x18010422f  call    ?ReleasePtr@?$AutoCleanup@VAutoBstr@@PEAG@@AEAAXXZ; AutoCleanup<AutoBstr,ushort *>::ReleasePtr(void)
0x180104234  nop
0x180104235  lea     rcx, [rsp+4E0h+hKeyDest]
0x18010423a  jmp     loc_180104159
0x18010423f  mov     r8, [rsp+4E0h+hKeyDest]; hKeyDest
0x180104244  xor     edx, edx; lpSubKey
0x180104246  mov     rcx, [rsp+4E0h+hKeySrc]; hKeySrc
0x18010424b  call    cs:__imp_RegCopyTreeW
0x180104251  mov     ebx, eax
0x180104253  test    eax, eax
0x180104255  jz      short loc_180104295
0x180104257  mov     r9d, eax
0x18010425a  lea     r8, aFailedToMigrat_1; "Failed to migrate CertMapping. Error: %"...
0x180104261  mov     edx, 2
0x180104266  mov     rcx, rsi
0x180104269  call    _anonymous_namespace___LogMigrationMessage
0x18010426e  test    r14, r14
0x180104271  jz      short loc_180104291
0x180104273  mov     rax, [r14]
0x180104276  mov     r9d, ebx
0x180104279  lea     r8, aRegcopytree; "RegCopyTree"
0x180104280  mov     edx, 4033C364h
0x180104285  mov     rcx, r14
0x180104288  mov     rax, [rax+58h]
0x18010428c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180104291  mov     ecx, ebx
0x180104293  jmp     short loc_180104223
0x180104295  lea     rcx, [rsp+4E0h+var_4A0]
  ... truncated ...
```
