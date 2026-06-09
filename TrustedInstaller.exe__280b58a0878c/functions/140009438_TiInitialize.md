# TiInitialize

- ea: `0x140009438`
- end: `0x140009640`
- name: `TiInitialize`
- size: `520`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140009650`

## callees

- `0x1400023e0`
- `0x140009438`
- `0x14000cd7c`
- `0x14000ce08`
- `0x1400168ac`
- `0x140017658`
- `0x14001c74c`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140009496`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400094e9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140009496`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400094e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400094a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400094fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400094a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400094fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140009566`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140009566`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140009557`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140009557`

## string_xrefs

- `0x140009457`: `Starting TrustedInstaller initialization.`
- `0x140009471`: `Starting TrustedInstaller initialization.`
- `0x1400094bd`: `Failed to create shutdown event.`
- `0x140009510`: `Failed to create servicing event.`
- `0x1400095b1`: `Failed to initialize WRP integrity check and repair.`
- `0x1400095d1`: `Unable to initialize GenValObj.dll`
- `0x140009613`: `Ending TrustedInstaller initialization.`

## pseudocode

```c
__int64 TiInitialize()
{
  signed int LastError; // eax
  signed int v1; // ebx
  const char *v2; // r9
  __int64 v3; // rdx
  signed int v4; // eax
  int v5; // eax
  unsigned int i; // edi
  __int64 v7; // rcx
  HKEY hKey[2]; // [rsp+30h] [rbp-48h] BYREF

  CBSWdsLogLight(0x4000000, 0, 0, "Starting TrustedInstaller initialization.");
  *(_OWORD *)hKey = CbsTiInitializeEvent;
  CbsGenericEventReport(hKey, L"Starting TrustedInstaller initialization.");
  vhShutdownEvent = CreateEventW(0, 1, 0, 0);
  if ( !vhShutdownEvent )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
    v2 = "Failed to create shutdown event.";
LABEL_5:
    if ( v1 >= 0 )
      v1 = -2147467259;
    goto LABEL_7;
  }
  vhServicingEvent = CreateEventW(0, 0, 0, 0);
  if ( !vhServicingEvent )
  {
    v4 = GetLastError();
    v1 = v4;
    if ( v4 > 0 )
      v1 = (unsigned __int16)v4 | 0x80070000;
    v2 = "Failed to create servicing event.";
    goto LABEL_5;
  }
  v1 = TiCoreInitialize(0);
  if ( v1 < 0 )
  {
    hKey[0] = 0;
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\MiniNt", 0, 1u, hKey) )
    {
      v2 = "Failed to initialize CBS Core.";
LABEL_7:
      v3 = (unsigned int)v1;
LABEL_8:
      CBSWdsLogLight(0x4000000, v3, 1, v2);
      goto LABEL_30;
    }
    RegCloseKey(hKey[0]);
  }
  v5 = TiCoreInitialize(2u);
  v1 = v5;
  if ( v5 < 0 )
  {
    v2 = "Failed to initialize SxS.";
LABEL_18:
    v3 = (unsigned int)v5;
    goto LABEL_8;
  }
  v5 = TiCoreInitializeNonCBSHostedService(1u);
  v1 = v5;
  if ( v5 < 0 )
  {
    v2 = "Failed to initialize WRP integrity check and repair.";
    goto LABEL_18;
  }
  v5 = TiCoreInitializeNonCBSHostedService(3u);
  v1 = v5;
  if ( v5 < 0 )
  {
    v2 = "Unable to initialize GenValObj.dll";
    goto LABEL_18;
  }
  v5 = TiCoreWinlogonNotificationsInitialize();
  v1 = v5;
  if ( v5 < 0 )
  {
    v2 = "Failed initializing for winlogon notifications";
    goto LABEL_18;
  }
  for ( i = 0; i < 4; ++i )
  {
    v7 = qword_14003F290[4 * (int)i];
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
  }
LABEL_30:
  CBSWdsLogLight(0x4000000, 0, 0, "Ending TrustedInstaller initialization.");
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x140009438  push    rbx
0x14000943a  push    rbp
0x14000943b  push    rsi
0x14000943c  push    rdi
0x14000943d  push    r14
0x14000943f  sub     rsp, 50h
0x140009443  mov     rax, cs:__security_cookie
0x14000944a  xor     rax, rsp
0x14000944d  mov     [rsp+78h+var_38], rax
0x140009452  mov     ebp, 4000000h
0x140009457  lea     r9, aStartingTruste_0; "Starting TrustedInstaller initializatio"...
0x14000945e  mov     ecx, ebp
0x140009460  xor     r8d, r8d
0x140009463  xor     edx, edx
0x140009465  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000946a  movups  xmm0, cs:CbsTiInitializeEvent
0x140009471  lea     rdx, aStartingTruste_1; "Starting TrustedInstaller initializatio"...
0x140009478  lea     rcx, [rsp+78h+hKey]
0x14000947d  movdqu  xmmword ptr [rsp+78h+hKey], xmm0
0x140009483  call    CbsGenericEventReport
0x140009488  xor     r9d, r9d; lpName
0x14000948b  xor     r8d, r8d; bInitialState
0x14000948e  xor     ecx, ecx; lpEventAttributes
0x140009490  lea     esi, [r9+1]
0x140009494  mov     edx, esi; bManualReset
0x140009496  call    cs:__imp_CreateEventW
0x14000949c  mov     cs:?vhShutdownEvent@@3PEAXEA, rax; void * vhShutdownEvent
0x1400094a3  test    rax, rax
0x1400094a6  jnz     short loc_1400094DF
0x1400094a8  call    cs:__imp_GetLastError
0x1400094ae  mov     ebx, eax
0x1400094b0  test    eax, eax
0x1400094b2  jle     short loc_1400094BD
0x1400094b4  movzx   ebx, ax
0x1400094b7  or      ebx, 80070000h
0x1400094bd  lea     r9, aFailedToCreate_6; "Failed to create shutdown event."
0x1400094c4  test    ebx, ebx
0x1400094c6  mov     eax, 80004005h
0x1400094cb  cmovns  ebx, eax
0x1400094ce  mov     edx, ebx
0x1400094d0  mov     r8d, esi
0x1400094d3  mov     ecx, ebp
0x1400094d5  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400094da  jmp     loc_140009613
0x1400094df  xor     r9d, r9d; lpName
0x1400094e2  xor     r8d, r8d; bInitialState
0x1400094e5  xor     edx, edx; bManualReset
0x1400094e7  xor     ecx, ecx; lpEventAttributes
0x1400094e9  call    cs:__imp_CreateEventW
0x1400094ef  mov     cs:?vhServicingEvent@@3PEAXEA, rax; void * vhServicingEvent
0x1400094f6  test    rax, rax
0x1400094f9  jnz     short loc_140009519
0x1400094fb  call    cs:__imp_GetLastError
0x140009501  mov     ebx, eax
0x140009503  test    eax, eax
0x140009505  jle     short loc_140009510
0x140009507  movzx   ebx, ax
0x14000950a  or      ebx, 80070000h
0x140009510  lea     r9, aFailedToCreate_5; "Failed to create servicing event."
0x140009517  jmp     short loc_1400094C4
0x140009519  lea     r14, qword_14003F290
0x140009520  xor     ecx, ecx
0x140009522  mov     rdx, r14
0x140009525  call    TiCoreInitialize
0x14000952a  mov     ebx, eax
0x14000952c  test    eax, eax
0x14000952e  jns     short loc_14000956C
0x140009530  lea     rax, [rsp+78h+hKey]
0x140009535  mov     [rsp+78h+hKey], 0
0x14000953e  mov     r9d, esi; samDesired
0x140009541  mov     [rsp+78h+phkResult], rax; phkResult
0x140009546  xor     r8d, r8d; ulOptions
0x140009549  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Control\\Min"...
0x140009550  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140009557  call    cs:__imp_RegOpenKeyExW
0x14000955d  test    eax, eax
0x14000955f  jnz     short loc_140009591
0x140009561  mov     rcx, [rsp+78h+hKey]; hKey
0x140009566  call    cs:__imp_RegCloseKey
0x14000956c  lea     rdx, qword_14003F2D0
0x140009573  mov     ecx, 2
0x140009578  call    TiCoreInitialize
0x14000957d  mov     ebx, eax
0x14000957f  test    eax, eax
0x140009581  jns     short loc_14000959D
0x140009583  lea     r9, aFailedToInitia_10; "Failed to initialize SxS."
0x14000958a  mov     edx, eax
0x14000958c  jmp     loc_1400094D0
0x140009591  lea     r9, aFailedToInitia_2; "Failed to initialize CBS Core."
0x140009598  jmp     loc_1400094CE
0x14000959d  lea     rdx, qword_14003F2B0
0x1400095a4  mov     ecx, esi
0x1400095a6  call    TiCoreInitializeNonCBSHostedService
0x1400095ab  mov     ebx, eax
0x1400095ad  test    eax, eax
0x1400095af  jns     short loc_1400095BA
0x1400095b1  lea     r9, aFailedToInitia_11; "Failed to initialize WRP integrity chec"...
0x1400095b8  jmp     short loc_14000958A
0x1400095ba  lea     rdx, qword_14003F2F0
0x1400095c1  mov     ecx, 3
0x1400095c6  call    TiCoreInitializeNonCBSHostedService
0x1400095cb  mov     ebx, eax
0x1400095cd  test    eax, eax
0x1400095cf  jns     short loc_1400095DA
0x1400095d1  lea     r9, aUnableToInitia; "Unable to initialize GenValObj.dll"
0x1400095d8  jmp     short loc_14000958A
0x1400095da  call    TiCoreWinlogonNotificationsInitialize
0x1400095df  mov     ebx, eax
0x1400095e1  test    eax, eax
0x1400095e3  jns     short loc_1400095EE
0x1400095e5  lea     r9, aFailedInitiali; "Failed initializing for winlogon notifi"...
0x1400095ec  jmp     short loc_14000958A
0x1400095ee  xor     edi, edi
0x1400095f0  movsxd  rax, edi
0x1400095f3  shl     rax, 5
0x1400095f7  mov     rcx, [rax+r14]
0x1400095fb  test    rcx, rcx
0x1400095fe  jz      short loc_14000960C
0x140009600  mov     rax, [rcx]
0x140009603  mov     rax, [rax+8]
0x140009607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000960c  add     edi, esi
0x14000960e  cmp     edi, 4
0x140009611  jb      short loc_1400095F0
0x140009613  lea     r9, aEndingTrustedi_1; "Ending TrustedInstaller initialization."
0x14000961a  xor     r8d, r8d
0x14000961d  xor     edx, edx
0x14000961f  mov     ecx, ebp
0x140009621  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140009626  mov     eax, ebx
0x140009628  mov     rcx, [rsp+78h+var_38]
0x14000962d  xor     rcx, rsp; StackCookie
0x140009630  call    __security_check_cookie
0x140009635  add     rsp, 50h
0x140009639  pop     r14
0x14000963b  pop     rdi
0x14000963c  pop     rsi
0x14000963d  pop     rbp
0x14000963e  pop     rbx
0x14000963f  retn
```
