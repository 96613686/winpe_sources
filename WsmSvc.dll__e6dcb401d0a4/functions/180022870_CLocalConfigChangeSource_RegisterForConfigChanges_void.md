# CLocalConfigChangeSource::RegisterForConfigChanges(void)

- ea: `0x180022870`
- end: `0x180022bbc`
- name: `?RegisterForConfigChanges@CLocalConfigChangeSource@@AEAAXXZ`
- size: `844`
- prototype: `void __fastcall(struct _TP_CALLBACK_ENVIRON_V3 *pv)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x1800eaf40`

## callees

- `0x180005d10`
- `0x180010030`
- `0x180022870`
- `0x1800485f0`
- `0x1800732d0`
- `0x1800973c0`
- `0x180112380`
- `0x1801123a8`
- `0x18011a6d4`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022b58`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022b58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022937`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002299d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800229d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022a9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022b21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022b40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022b5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022937`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002299d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800229d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022a9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022b21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022b40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022b5e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180022b6b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180022b6b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180022965`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180022965`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180022ae6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180022ae6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180022a66`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180022a66`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x1800229aa`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x1800229aa`

## string_xrefs

- `0x180022b90`: `onecore\admin\wmi\wmx\config\clocalconfigchangesource.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CLocalConfigChangeSource::RegisterForConfigChanges(struct _TP_CALLBACK_ENVIRON_V3 *pv)
{
  CConfigManager *ConfigManager; // rbx
  DWORD LastError; // eax
  HANDLE EventW; // rax
  HANDLE *p_FinalizationCallback; // rdi
  DWORD v6; // eax
  __int64 v7; // rdx
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  struct ConfigNotification *v9; // rdi
  DWORD v10; // eax
  DWORD v11; // ebx
  CConfigManager *v12; // [rsp+50h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_370815dc9a9336867a18c46a9d5d6ff6_Traceguids, pv);
  v12 = 0;
  if ( !HIDWORD(pv->RaceDll) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_370815dc9a9336867a18c46a9d5d6ff6_Traceguids);
    goto LABEL_34;
  }
  ConfigManager = CConfigManager::GetConfigManager();
  AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&v12);
  v12 = ConfigManager;
  if ( !ConfigManager )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_370815dc9a9336867a18c46a9d5d6ff6_Traceguids, LastError);
    }
    goto LABEL_33;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  p_FinalizationCallback = (HANDLE *)&pv->FinalizationCallback;
  AutoHandle::operator=(&pv->FinalizationCallback, EventW);
  if ( !pv->FinalizationCallback )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0 )
      goto LABEL_33;
    v6 = GetLastError();
    v7 = 21;
LABEL_20:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, WPP_370815dc9a9336867a18c46a9d5d6ff6_Traceguids, v6);
LABEL_33:
    pv->Size = GetLastError();
    goto LABEL_34;
  }
  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  pv[2].Pool = ThreadpoolCleanupGroup;
  if ( !ThreadpoolCleanupGroup )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0 )
      goto LABEL_33;
    v6 = GetLastError();
    v7 = 24;
    goto LABEL_20;
  }
  pv[1].Version = 3;
  pv[1].RaceDll = 0;
  pv[1].ActivationContext = 0;
  pv[1].FinalizationCallback = 0;
  pv[1].u.Flags = 0;
  pv[1].CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
  pv[1].Size = 72;
  pv[2].Version = 1;
  pv[1].Pool = 0;
  pv[1].CleanupGroup = pv[2].Pool;
  pv[1].CleanupGroupCancelCallback = 0;
  pv[2].CleanupGroup = CreateThreadpoolWait(CLocalConfigChangeSource::_LocalChangeNotificationCallback, pv, pv + 1);
  if ( !pv[2].CleanupGroup )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0 )
      goto LABEL_33;
    v6 = GetLastError();
    v7 = 25;
    goto LABEL_20;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      26,
      WPP_370815dc9a9336867a18c46a9d5d6ff6_Traceguids,
      pv[2].CleanupGroup);
  SetThreadpoolWait(pv[2].CleanupGroup, *p_FinalizationCallback, 0);
  v9 = CConfigManager::RegisterConfigChangeNotification(ConfigManager, *p_FinalizationCallback);
  AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&pv->u);
  *(_QWORD *)&pv->u.Flags = v9;
  if ( !v9 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
    {
      v10 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_370815dc9a9336867a18c46a9d5d6ff6_Traceguids, v10);
    }
    v11 = GetLastError();
    (**(void (__fastcall ***)(struct _TP_CALLBACK_ENVIRON_V3 *))&pv->Version)(pv);
    SetLastError(v11);
    goto LABEL_33;
  }
LABEL_34:
  if ( !SetEvent(pv->ActivationContext) )
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\clocalconfigchangesource.cpp", 285, L"285", 0x54Fu, 0);
  AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&v12);
}

```

## disassembly

```asm
0x180022870  mov     [rsp+arg_8], rbx
0x180022875  mov     [rsp+arg_10], rsi
0x18002287a  push    rdi
0x18002287b  push    r14
0x18002287d  push    r15
0x18002287f  sub     rsp, 30h
0x180022883  mov     rsi, rcx
0x180022886  lea     r14, WPP_GLOBAL_Control
0x18002288d  lea     r15, WPP_370815dc9a9336867a18c46a9d5d6ff6_Traceguids
0x180022894  mov     rcx, cs:WPP_GLOBAL_Control
0x18002289b  cmp     rcx, r14
0x18002289e  jz      short loc_1800228BD
0x1800228a0  test    dword ptr [rcx+1Ch], 200000h
0x1800228a7  jz      short loc_1800228BD
0x1800228a9  mov     edx, 12h
0x1800228ae  mov     r9, rsi
0x1800228b1  mov     r8, r15
0x1800228b4  mov     rcx, [rcx+10h]
0x1800228b8  call    WPP_SF_q
0x1800228bd  mov     [rsp+48h+arg_0], 0
0x1800228c6  mov     eax, [rsi+24h]
0x1800228c9  test    eax, eax
0x1800228cb  jnz     short loc_1800228FE
0x1800228cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800228d4  cmp     rcx, r14
0x1800228d7  jz      loc_180022B67
0x1800228dd  test    dword ptr [rcx+1Ch], 400000h
0x1800228e4  jz      loc_180022B67
0x1800228ea  lea     edx, [rax+13h]
0x1800228ed  mov     r8, r15
0x1800228f0  mov     rcx, [rcx+10h]
0x1800228f4  call    WPP_SF_
0x1800228f9  jmp     loc_180022B67
0x1800228fe  call    ?GetConfigManager@CConfigManager@@SAPEAV1@XZ; CConfigManager::GetConfigManager(void)
0x180022903  mov     rbx, rax
0x180022906  lea     rcx, [rsp+48h+arg_0]
0x18002290b  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VWSManHttpListener@@@@PEAVWSManHttpListener@@@@AEAAXXZ; AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(void)
0x180022910  mov     [rsp+48h+arg_0], rbx
0x180022915  test    rbx, rbx
0x180022918  jnz     short loc_18002295B
0x18002291a  mov     rax, cs:WPP_GLOBAL_Control
0x180022921  cmp     rax, r14
0x180022924  jz      loc_180022B5E
0x18002292a  test    dword ptr [rax+1Ch], 400000h
0x180022931  jz      loc_180022B5E
0x180022937  call    cs:__imp_GetLastError
0x18002293d  lea     edx, [rbx+14h]
0x180022940  mov     r9d, eax
0x180022943  mov     r8, r15
0x180022946  mov     rcx, cs:WPP_GLOBAL_Control
0x18002294d  mov     rcx, [rcx+10h]
0x180022951  call    WPP_SF_d
0x180022956  jmp     loc_180022B5E
0x18002295b  xor     r9d, r9d; lpName
0x18002295e  xor     r8d, r8d; bInitialState
0x180022961  xor     edx, edx; bManualReset
0x180022963  xor     ecx, ecx; lpEventAttributes
0x180022965  call    cs:__imp_CreateEventW
0x18002296b  lea     rdi, [rsi+30h]
0x18002296f  mov     rdx, rax
0x180022972  mov     rcx, rdi
0x180022975  call    ??4AutoHandle@@QEAAAEAV0@PEAX@Z; AutoHandle::operator=(void *)
0x18002297a  cmp     qword ptr [rdi], 0
0x18002297e  jnz     short loc_1800229AA
0x180022980  mov     rax, cs:WPP_GLOBAL_Control
0x180022987  cmp     rax, r14
0x18002298a  jz      loc_180022B5E
0x180022990  test    dword ptr [rax+1Ch], 400000h
0x180022997  jz      loc_180022B5E
0x18002299d  call    cs:__imp_GetLastError
0x1800229a3  mov     edx, 15h
0x1800229a8  jmp     short loc_1800229E4
0x1800229aa  call    cs:__imp_CreateThreadpoolCleanupGroup
0x1800229b0  mov     [rsi+98h], rax
0x1800229b7  test    rax, rax
0x1800229ba  jnz     short loc_1800229FF
0x1800229bc  mov     rax, cs:WPP_GLOBAL_Control
0x1800229c3  cmp     rax, r14
0x1800229c6  jz      loc_180022B5E
0x1800229cc  test    dword ptr [rax+1Ch], 400000h
0x1800229d3  jz      loc_180022B5E
0x1800229d9  call    cs:__imp_GetLastError
0x1800229df  mov     edx, 18h
0x1800229e4  mov     r9d, eax
0x1800229e7  mov     r8, r15
0x1800229ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800229f1  mov     rcx, [rcx+10h]
0x1800229f5  call    WPP_SF_d
0x1800229fa  jmp     loc_180022B5E
0x1800229ff  lea     r8, [rsi+48h]; pcbe
0x180022a03  mov     dword ptr [r8], 3
0x180022a0a  mov     qword ptr [r8+20h], 0
0x180022a12  mov     qword ptr [r8+28h], 0
0x180022a1a  mov     qword ptr [r8+30h], 0
0x180022a22  mov     dword ptr [r8+38h], 0
0x180022a2a  mov     eax, 1
0x180022a2f  mov     [r8+3Ch], eax
0x180022a33  mov     dword ptr [r8+40h], 48h ; 'H'
0x180022a3b  mov     [rsi+90h], eax
0x180022a41  mov     qword ptr [rsi+50h], 0
0x180022a49  mov     rax, [rsi+98h]
0x180022a50  mov     [rsi+58h], rax
0x180022a54  mov     qword ptr [rsi+60h], 0
0x180022a5c  mov     rdx, rsi; pv
0x180022a5f  lea     rcx, ?_LocalChangeNotificationCallback@CLocalConfigChangeSource@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x180022a66  call    cs:__imp_CreateThreadpoolWait
0x180022a6c  mov     [rsi+0A0h], rax
0x180022a73  mov     rax, [rsi+0A0h]
0x180022a7a  test    rax, rax
0x180022a7d  jnz     short loc_180022AAC
0x180022a7f  mov     rax, cs:WPP_GLOBAL_Control
0x180022a86  cmp     rax, r14
0x180022a89  jz      loc_180022B5E
0x180022a8f  test    dword ptr [rax+1Ch], 400000h
0x180022a96  jz      loc_180022B5E
0x180022a9c  call    cs:__imp_GetLastError
0x180022aa2  mov     edx, 19h
0x180022aa7  jmp     loc_1800229E4
0x180022aac  mov     rcx, cs:WPP_GLOBAL_Control
0x180022ab3  cmp     rcx, r14
0x180022ab6  jz      short loc_180022AD9
0x180022ab8  test    dword ptr [rcx+1Ch], 200000h
0x180022abf  jz      short loc_180022AD9
0x180022ac1  mov     rcx, [rcx+10h]
0x180022ac5  mov     edx, 1Ah
0x180022aca  mov     r9, [rsi+0A0h]
0x180022ad1  mov     r8, r15
0x180022ad4  call    WPP_SF_q
0x180022ad9  mov     rdx, [rdi]; h
0x180022adc  mov     rcx, [rsi+0A0h]; pwa
0x180022ae3  xor     r8d, r8d; pftTimeout
0x180022ae6  call    cs:__imp_SetThreadpoolWait
0x180022aec  mov     rdx, [rdi]; void *
0x180022aef  mov     rcx, rbx; this
0x180022af2  call    ?RegisterConfigChangeNotification@CConfigManager@@QEAAPEAVConfigNotification@@PEAX@Z; CConfigManager::RegisterConfigChangeNotification(void *)
0x180022af7  mov     rdi, rax
0x180022afa  lea     rcx, [rsi+38h]
0x180022afe  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VWSManHttpListener@@@@PEAVWSManHttpListener@@@@AEAAXXZ; AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(void)
0x180022b03  mov     [rsi+38h], rdi
0x180022b07  test    rdi, rdi
0x180022b0a  jnz     short loc_180022B67
0x180022b0c  mov     rax, cs:WPP_GLOBAL_Control
0x180022b13  cmp     rax, r14
0x180022b16  jz      short loc_180022B40
0x180022b18  test    dword ptr [rax+1Ch], 400000h
0x180022b1f  jz      short loc_180022B40
0x180022b21  call    cs:__imp_GetLastError
0x180022b27  lea     edx, [rdi+1Bh]
0x180022b2a  mov     r9d, eax
0x180022b2d  mov     r8, r15
0x180022b30  mov     rcx, cs:WPP_GLOBAL_Control
0x180022b37  mov     rcx, [rcx+10h]
0x180022b3b  call    WPP_SF_d
0x180022b40  call    cs:__imp_GetLastError
0x180022b46  mov     ebx, eax
0x180022b48  mov     rcx, [rsi]
0x180022b4b  mov     rax, [rcx]
0x180022b4e  mov     rcx, rsi
0x180022b51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022b56  mov     ecx, ebx; dwErrCode
0x180022b58  call    cs:__imp_SetLastError
0x180022b5e  call    cs:__imp_GetLastError
0x180022b64  mov     [rsi+40h], eax
0x180022b67  mov     rcx, [rsi+28h]; hEvent
0x180022b6b  call    cs:__imp_SetEvent
0x180022b71  test    eax, eax
0x180022b73  jnz     short loc_180022B9D
0x180022b75  mov     [rsp+48h+var_28], 0; struct IRequestContext *
0x180022b7e  mov     r9d, 54Fh; unsigned int
0x180022b84  lea     r8, a285; "285"
0x180022b8b  mov     edx, 11Dh; unsigned int
0x180022b90  lea     rcx, aOnecoreAdminWm_170; "onecore\\admin\\wmi\\wmx\\config\\cloca"...
0x180022b97  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180022b9c  nop
0x180022b9d  lea     rcx, [rsp+48h+arg_0]
0x180022ba2  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VWSManHttpListener@@@@PEAVWSManHttpListener@@@@AEAAXXZ; AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(void)
0x180022ba7  nop
0x180022ba8  mov     rbx, [rsp+48h+arg_8]
0x180022bad  mov     rsi, [rsp+48h+arg_10]
0x180022bb2  add     rsp, 30h
0x180022bb6  pop     r15
0x180022bb8  pop     r14
0x180022bba  pop     rdi
0x180022bbb  retn
```
