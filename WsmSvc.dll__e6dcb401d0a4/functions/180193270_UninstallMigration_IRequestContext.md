# UninstallMigration(IRequestContext *)

- ea: `0x180193270`
- end: `0x1801933bd`
- name: `?UninstallMigration@@YAHPEAVIRequestContext@@@Z`
- size: `333`
- prototype: `__int64 __fastcall(struct IRequestContext *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800bac30`
- `0x180105ae0`
- `0x18010e030`
- `0x1801907ac`
- `0x1801917b4`
- `0x1801931d0`
- `0x180193270`
- `0x1801c2010`

## import_xrefs

- `msvcrt!fwprintf` at `0x18019329f`
- `msvcrt!fwprintf` at `0x1801932c7`
- `msvcrt!fwprintf` at `0x18019332f`
- `msvcrt!fwprintf` at `0x180193367`
- `msvcrt!fwprintf` at `0x180193392`
- `msvcrt!fwprintf` at `0x18019329f`
- `msvcrt!fwprintf` at `0x1801932c7`
- `msvcrt!fwprintf` at `0x18019332f`
- `msvcrt!fwprintf` at `0x180193367`
- `msvcrt!fwprintf` at `0x180193392`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18019330f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18019330f`

## string_xrefs

- `0x180193301`: `SOFTWARE\Microsoft\Windows\CurrentVersion\WSMAN\Plugin`
- `0x180193298`: `WTR registry present, Skip uninstall. \n`
- `0x180193328`: `WSMan Generic Command ERROR: Error in opening WSMan regkey while uninstalling: error<%ld>\n`
- `0x180193360`: `UninstallMigration failed while migration plugin`
- `0x18019338b`: `UninstallMigration failed while restoring the global quotas for previous version of Windows8.`

## pseudocode

```c
__int64 __fastcall UninstallMigration(struct IRequestContext *a1)
{
  unsigned int v2; // edi
  FILE *v3; // rax
  FILE *v5; // rax
  unsigned int v6; // edi
  FILE *v7; // rax
  unsigned __int16 v8; // dx
  unsigned __int16 v9; // cx
  unsigned __int16 v10; // r8
  FILE *v11; // rax
  FILE *v12; // rax
  unsigned int v13; // ebx
  HKEY phkResult; // [rsp+48h] [rbp+10h] BYREF

  v2 = CheckWTRRegistryValueStatus();
  if ( !v2 )
  {
    v3 = _acrt_iob_func(2u);
    fwprintf(v3, L"WTR registry present, Skip uninstall. \n");
    return 1;
  }
  if ( v2 != 2 )
  {
    v5 = _acrt_iob_func(2u);
    fwprintf(v5, L"Can not find the WTR status. \n");
    (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a1 + 72LL))(a1, v2);
    return 0;
  }
  phkResult = 0;
  v6 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WSMAN\\Plugin",
         0,
         0xF013Fu,
         &phkResult);
  if ( v6 )
  {
    v7 = _acrt_iob_func(2u);
    fwprintf(v7, L"WSMan Generic Command ERROR: Error in opening WSMan regkey while uninstalling: error<%ld>\n", v6);
LABEL_8:
    AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(&phkResult);
    return 0;
  }
  if ( !(unsigned int)anonymous_namespace_::MigratePluginXmlForUninstall(a1, phkResult, 0) )
  {
    v11 = _acrt_iob_func(2u);
    fwprintf(v11, L"UninstallMigration failed while migration plugin");
    goto LABEL_8;
  }
  if ( IsWindowsVersionOrGreater(v9, v8, v10)
    || (unsigned __int8)anonymous_namespace_::RestoreGlobalQuotasToDefaultOnUninstall_PreWin8() )
  {
    v13 = 1;
  }
  else
  {
    v12 = _acrt_iob_func(2u);
    fwprintf(v12, L"UninstallMigration failed while restoring the global quotas for previous version of Windows8.");
    v13 = 0;
  }
  AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(&phkResult);
  return v13;
}

```

## disassembly

```asm
0x180193270  mov     [rsp+arg_0], rbx
0x180193275  mov     [rsp+arg_10], rsi
0x18019327a  push    rdi
0x18019327b  sub     rsp, 30h
0x18019327f  mov     rsi, rcx
0x180193282  call    ?CheckWTRRegistryValueStatus@@YAJXZ; CheckWTRRegistryValueStatus(void)
0x180193287  mov     edi, eax
0x180193289  test    eax, eax
0x18019328b  jnz     short loc_1801932AD
0x18019328d  lea     ecx, [rax+2]; Ix
0x180193290  call    __acrt_iob_func
0x180193295  mov     rcx, rax; Stream
0x180193298  lea     rdx, aWtrRegistryPre; "WTR registry present, Skip uninstall. "...
0x18019329f  call    cs:__imp_fwprintf
0x1801932a5  lea     eax, [rdi+1]
0x1801932a8  jmp     loc_1801933AD
0x1801932ad  mov     ebx, 2
0x1801932b2  cmp     edi, ebx
0x1801932b4  jz      short loc_1801932E5
0x1801932b6  mov     ecx, ebx; Ix
0x1801932b8  call    __acrt_iob_func
0x1801932bd  mov     rcx, rax; Stream
0x1801932c0  lea     rdx, aCanNotFindTheW; "Can not find the WTR status. \n"
0x1801932c7  call    cs:__imp_fwprintf
0x1801932cd  mov     rax, [rsi]
0x1801932d0  mov     edx, edi
0x1801932d2  mov     rcx, rsi
0x1801932d5  mov     rax, [rax+48h]
0x1801932d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801932de  xor     eax, eax
0x1801932e0  jmp     loc_1801933AD
0x1801932e5  mov     [rsp+38h+arg_8], 0
0x1801932ee  lea     rax, [rsp+38h+arg_8]
0x1801932f3  mov     [rsp+38h+phkResult], rax; phkResult
0x1801932f8  mov     r9d, 0F013Fh; samDesired
0x1801932fe  xor     r8d, r8d; ulOptions
0x180193301  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180193308  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18019330f  call    cs:__imp_RegOpenKeyExW
0x180193315  mov     edi, eax
0x180193317  test    eax, eax
0x180193319  jz      short loc_180193342
0x18019331b  mov     ecx, ebx; Ix
0x18019331d  call    __acrt_iob_func
0x180193322  mov     rcx, rax; Stream
0x180193325  mov     r8d, edi
0x180193328  lea     rdx, aWsmanGenericCo; "WSMan Generic Command ERROR: Error in o"...
0x18019332f  call    cs:__imp_fwprintf
0x180193335  nop
0x180193336  lea     rcx, [rsp+38h+arg_8]
0x18019333b  call    ??1?$AutoCleanup@VAutoRegKey@@PEAUHKEY__@@@@QEAA@XZ; AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(void)
0x180193340  jmp     short loc_1801932DE
0x180193342  xor     r8d, r8d
0x180193345  mov     rdx, [rsp+38h+arg_8]
0x18019334a  mov     rcx, rsi
0x18019334d  call    _anonymous_namespace___MigratePluginXmlForUninstall
0x180193352  test    eax, eax
0x180193354  jnz     short loc_18019336F
0x180193356  mov     ecx, ebx; Ix
0x180193358  call    __acrt_iob_func
0x18019335d  mov     rcx, rax; Stream
0x180193360  lea     rdx, aUninstallmigra_0; "UninstallMigration failed while migrati"...
0x180193367  call    cs:__imp_fwprintf
0x18019336d  jmp     short loc_180193336
0x18019336f  call    ?IsWindowsVersionOrGreater@@YA_NGGG@Z; IsWindowsVersionOrGreater(ushort,ushort,ushort)
0x180193374  test    al, al
0x180193376  jnz     short loc_18019339C
0x180193378  call    _anonymous_namespace___RestoreGlobalQuotasToDefaultOnUninstall_PreWin8
0x18019337d  test    al, al
0x18019337f  jnz     short loc_18019339C
0x180193381  mov     ecx, ebx; Ix
0x180193383  call    __acrt_iob_func
0x180193388  mov     rcx, rax; Stream
0x18019338b  lea     rdx, aUninstallmigra_1; "UninstallMigration failed while restori"...
0x180193392  call    cs:__imp_fwprintf
0x180193398  xor     ebx, ebx
0x18019339a  jmp     short loc_1801933A1
0x18019339c  mov     ebx, 1
0x1801933a1  lea     rcx, [rsp+38h+arg_8]
0x1801933a6  call    ??1?$AutoCleanup@VAutoRegKey@@PEAUHKEY__@@@@QEAA@XZ; AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(void)
0x1801933ab  mov     eax, ebx
0x1801933ad  mov     rbx, [rsp+38h+arg_0]
0x1801933b2  mov     rsi, [rsp+38h+arg_10]
0x1801933b7  add     rsp, 30h
0x1801933bb  pop     rdi
0x1801933bc  retn
```
