# SE_InitializeEngine

- ea: `0x180002520`
- end: `0x18000292c`
- name: `SE_InitializeEngine`
- size: `1036`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002520`
- `0x180002b38`
- `0x180007518`
- `0x180007e94`
- `0x180008f08`
- `0x18000a23c`
- `0x18000f114`
- `0x180015fb0`
- `0x180017334`
- `0x180017658`
- `0x18001cc90`
- `0x18001e198`
- `0x18001ea6c`
- `0x18001f3c4`
- `0x18001f7f8`
- `0x1800274f4`
- `0x18002bd60`
- `0x18002c0ec`
- `0x18002c2d8`
- `0x18002ce44`
- `0x18002d450`
- `0x180059235`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180002908`
- `ntdll!RtlLeaveCriticalSection` at `0x180002908`
- `ntdll!RtlEnterCriticalSection` at `0x18000255b`
- `ntdll!RtlEnterCriticalSection` at `0x18000255b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800027c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800027c2`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800027d1`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800027d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000271d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000271d`

## string_xrefs

- `0x180002659`: `Failed to open shim database`
- `0x180002594`: `Engine already initialized`
- `0x18000260c`: `Failed to create engine`
- `0x1800028e5`: `Failed to get shim dll list`

## pseudocode

```c
__int64 __fastcall SE_InitializeEngine(__int64 a1, __int64 a2, __int64 a3)
{
  int ShimDllList; // edi
  struct _PEB *v7; // rax
  __int64 v8; // rcx
  __int64 inited; // rax
  void *v10; // r14
  __int64 v11; // rbx
  DWORD CurrentProcessId; // eax
  int v13; // ecx
  HANDLE CurrentProcess; // rax
  __int64 v15; // rcx
  _BYTE v17[464]; // [rsp+40h] [rbp-C0h] BYREF
  int v18; // [rsp+258h] [rbp+158h] BYREF

  SeProcessAttach();
  SepApplyDebugPolicy();
  ShimDllList = RtlEnterCriticalSection(&g_EngineLock);
  if ( ShimDllList >= 0 )
  {
    if ( g_Engine )
    {
      AslLogCallPrintf(1, "SE_InitializeEngine", 2833, "Engine already initialized");
      ShimDllList = -1073741823;
LABEL_36:
      RtlLeaveCriticalSection(&g_EngineLock);
      return (unsigned int)ShimDllList;
    }
    v7 = NtCurrentPeb();
    g_InitState = 1;
    v18 = 0;
    g_CompatLayers = (STRSAFE_LPWSTR)((char *)v7->pShimData + 3908);
    memset_0(v17, 0, 0x1C8u);
    ShimDllList = SeEngineCreate();
    if ( ShimDllList < 0 )
    {
      AslLogCallPrintf(1, "SE_InitializeEngine", 2860, "Failed to create engine");
      goto LABEL_36;
    }
    v8 = (*(_DWORD *)(a3 + 728) >> 10) & 8 | 0x10u;
    if ( (*(_DWORD *)(a3 + 728) & 0x4000) == 0 )
      v8 = (*(_DWORD *)(a3 + 728) >> 10) & 8;
    inited = SdbInitDatabase(v8, 0);
    v10 = (void *)inited;
    if ( !inited )
    {
      AslLogCallPrintf(1, "SE_InitializeEngine", 2877, "Failed to open shim database");
      ShimDllList = -1073741801;
      goto LABEL_36;
    }
    if ( (unsigned int)SdbUnpackAppCompatData(inited, *(_QWORD *)(a2 + 8), a3, v17) )
    {
      if ( (unsigned int)SdbIsValidQueryResult(v10, v17) )
      {
        ShimDllList = SeSdbProcessLayers(g_CompatLayers);
        if ( ShimDllList < 0 )
        {
          AslLogCallPrintf(1, "SE_InitializeEngine", 2914, "Failed to do layer propagation");
          goto LABEL_35;
        }
        v11 = *(_QWORD *)(a2 + 8);
        CurrentProcessId = GetCurrentProcessId();
        TraceQueryResult(v11, (_DWORD)v10, (unsigned int)v17, CurrentProcessId, 0);
        SepDumpQueryResult(*(_QWORD *)(a2 + 8), (__int64)v10, (__int64)v17);
        SepDumpQueryResultToState(v10, v17);
        if ( (unsigned int)SdbShowApphelpFromQuery(
                             *(_QWORD *)(a2 + 8),
                             (_DWORD)v10,
                             (unsigned int)v17,
                             1,
                             (__int64)&v18) )
        {
          if ( v18 )
          {
            AslLogCallPrintf(
              3,
              "SE_InitializeEngine",
              2950,
              "Apphelped process is terminating, %ws",
              *(_QWORD *)(a2 + 8));
            CurrentProcess = GetCurrentProcess();
            TerminateProcess(CurrentProcess, g_dwApphelpExitCode);
          }
          else
          {
            ShimDllList = SeSdbProcessQueryResult(v13, (_DWORD)v10, (unsigned int)v17, *(_QWORD *)(a2 + 8), 0);
            if ( ShimDllList >= 0 )
            {
              if ( (unsigned int)IsArmadilloProtected()
                && (ShimDllList = SeHookManagerAddHooks(
                                    *(_QWORD *)(g_Engine + 24),
                                    -1,
                                    1,
                                    (int)&g_ArmadilloHooks,
                                    2,
                                    1,
                                    0),
                    ShimDllList < 0) )
              {
                AslLogCallPrintf(1, "SE_InitializeEngine", 2982, "Failed to add Armadillo hooks");
              }
              else
              {
                SeEngineShimDllLoaded(v15, g_DataTableEntry->DllBase);
                if ( (int)SeFlagManagerExecute(*(_QWORD *)g_Engine) < 0 )
                  AslLogCallPrintf(1, "SE_InitializeEngine", 2999, "Failed to apply flags");
                if ( (int)SeQuirkManagerExecute(*(_QWORD *)(g_Engine + 8)) < 0 )
                  AslLogCallPrintf(1, "SE_InitializeEngine", 3004, "Failed to apply quirks");
                ShimDllList = SeShimManagerGetShimDllList(a1, *(_QWORD *)(g_Engine + 16));
                if ( ShimDllList >= 0 )
                  ShimDllList = 0;
                else
                  AslLogCallPrintf(1, "SE_InitializeEngine", 3020, "Failed to get shim dll list");
              }
            }
            else
            {
              AslLogCallPrintf(1, "SE_InitializeEngine", 2965, "Failed to initialize engine from query result");
            }
          }
          goto LABEL_35;
        }
        AslLogCallPrintf(1, "SE_InitializeEngine", 2944, "Failed to do apphelp processing");
      }
      else
      {
        AslLogCallPrintf(1, "SE_InitializeEngine", 2900, "Invalid query result");
      }
    }
    else
    {
      AslLogCallPrintf(1, "SE_InitializeEngine", 2890, "Failed to unpack query result");
    }
    ShimDllList = -1073741595;
LABEL_35:
    SdbReleaseDatabase(v10);
    goto LABEL_36;
  }
  AslLogCallPrintf(1, "SE_InitializeEngine", 2820, "Failed to lock engine");
  return (unsigned int)ShimDllList;
}

```

## disassembly

```asm
0x180002520  mov     [rsp-8+arg_0], rbx
0x180002525  mov     [rsp-8+arg_8], rsi
0x18000252a  push    rbp
0x18000252b  push    rdi
0x18000252c  push    r12
0x18000252e  push    r14
0x180002530  push    r15
0x180002532  lea     rbp, [rsp-110h]
0x18000253a  sub     rsp, 210h
0x180002541  mov     rbx, r8
0x180002544  mov     r15, rdx
0x180002547  mov     r12, rcx
0x18000254a  call    SeProcessAttach
0x18000254f  call    SepApplyDebugPolicy
0x180002554  lea     rcx, g_EngineLock; CriticalSection
0x18000255b  call    cs:__imp_RtlEnterCriticalSection
0x180002561  mov     edi, eax
0x180002563  test    eax, eax
0x180002565  jns     short loc_18000258A
0x180002567  lea     r9, aFailedToLockEn; "Failed to lock engine"
0x18000256e  mov     r8d, 0B04h
0x180002574  lea     rdx, aSeInitializeen_0; "SE_InitializeEngine"
0x18000257b  mov     ecx, 1
0x180002580  call    AslLogCallPrintf
0x180002585  jmp     loc_18000290E
0x18000258a  cmp     cs:g_Engine, 0
0x180002592  jz      short loc_1800025BC
0x180002594  lea     r9, aEngineAlreadyI; "Engine already initialized"
0x18000259b  mov     r8d, 0B11h
0x1800025a1  lea     rdx, aSeInitializeen_0; "SE_InitializeEngine"
0x1800025a8  mov     ecx, 1
0x1800025ad  call    AslLogCallPrintf
0x1800025b2  mov     edi, 0C0000001h
0x1800025b7  jmp     loc_180002901
0x1800025bc  mov     rax, gs:60h
0x1800025c5  mov     esi, 1
0x1800025ca  xor     edx, edx; Val
0x1800025cc  mov     cs:g_InitState, esi
0x1800025d2  mov     r8d, 1C8h; Size
0x1800025d8  mov     [rbp+130h+arg_18], 0
0x1800025e2  mov     rcx, [rax+2D8h]
0x1800025e9  add     rcx, 0F44h
0x1800025f0  mov     cs:g_CompatLayers, rcx
0x1800025f7  lea     rcx, [rsp+230h+var_1F0]; void *
0x1800025fc  call    memset_0
0x180002601  call    SeEngineCreate
0x180002606  mov     edi, eax
0x180002608  test    eax, eax
0x18000260a  jns     short loc_18000262C
0x18000260c  lea     r9, aFailedToCreate_25; "Failed to create engine"
0x180002613  mov     r8d, 0B2Ch
0x180002619  lea     rdx, aSeInitializeen_0; "SE_InitializeEngine"
0x180002620  mov     ecx, esi
0x180002622  call    AslLogCallPrintf
0x180002627  jmp     loc_180002901
0x18000262c  mov     edx, [rbx+2D8h]
0x180002632  shr     edx, 0Ah
0x180002635  and     edx, 8
0x180002638  mov     ecx, edx
0x18000263a  or      ecx, 10h
0x18000263d  test    dword ptr [rbx+2D8h], 4000h
0x180002647  cmovz   ecx, edx
0x18000264a  xor     edx, edx
0x18000264c  call    SdbInitDatabase
0x180002651  mov     r14, rax
0x180002654  test    rax, rax
0x180002657  jnz     short loc_18000267E
0x180002659  lea     r9, aFailedToOpenSh; "Failed to open shim database"
0x180002660  mov     r8d, 0B3Dh
0x180002666  lea     rdx, aSeInitializeen_0; "SE_InitializeEngine"
0x18000266d  mov     ecx, esi
0x18000266f  call    AslLogCallPrintf
0x180002674  mov     edi, 0C0000017h
0x180002679  jmp     loc_180002901
0x18000267e  mov     rdx, [r15+8]
0x180002682  lea     r9, [rsp+230h+var_1F0]
0x180002687  mov     r8, rbx
0x18000268a  mov     rcx, r14
0x18000268d  call    SdbUnpackAppCompatData
0x180002692  test    eax, eax
0x180002694  jnz     short loc_1800026BB
0x180002696  lea     r9, aFailedToUnpack; "Failed to unpack query result"
0x18000269d  mov     r8d, 0B4Ah
0x1800026a3  lea     rdx, aSeInitializeen_0; "SE_InitializeEngine"
0x1800026aa  mov     ecx, esi
0x1800026ac  call    AslLogCallPrintf
0x1800026b1  mov     edi, 0C00000E5h
0x1800026b6  jmp     loc_1800028F9
0x1800026bb  lea     rdx, [rsp+230h+var_1F0]
0x1800026c0  mov     rcx, r14
0x1800026c3  call    SdbIsValidQueryResult
0x1800026c8  test    eax, eax
0x1800026ca  jnz     short loc_1800026DB
0x1800026cc  lea     r9, aInvalidQueryRe; "Invalid query result"
0x1800026d3  mov     r8d, 0B54h
0x1800026d9  jmp     short loc_1800026A3
0x1800026db  mov     r8, [r15+8]
0x1800026df  lea     r9, [rsp+230h+var_1F0]
0x1800026e4  mov     rcx, cs:g_CompatLayers; pszDest
0x1800026eb  mov     rdx, r14
0x1800026ee  call    SeSdbProcessLayers
0x1800026f3  mov     edi, eax
0x1800026f5  test    eax, eax
0x1800026f7  jns     short loc_180002719
0x1800026f9  lea     r9, aFailedToDoLaye; "Failed to do layer propagation"
0x180002700  mov     r8d, 0B62h
0x180002706  lea     rdx, aSeInitializeen_0; "SE_InitializeEngine"
0x18000270d  mov     ecx, esi
0x18000270f  call    AslLogCallPrintf
0x180002714  jmp     loc_1800028F9
0x180002719  mov     rbx, [r15+8]
0x18000271d  call    cs:__imp_GetCurrentProcessId
0x180002723  lea     r8, [rsp+230h+var_1F0]
0x180002728  mov     dword ptr [rsp+230h+var_210], 0
0x180002730  mov     r9d, eax
0x180002733  mov     rdx, r14
0x180002736  mov     rcx, rbx
0x180002739  call    TraceQueryResult
0x18000273e  mov     rcx, [r15+8]
0x180002742  lea     r8, [rsp+230h+var_1F0]
0x180002747  mov     rdx, r14
0x18000274a  call    SepDumpQueryResult
0x18000274f  lea     rdx, [rsp+230h+var_1F0]
0x180002754  mov     rcx, r14
0x180002757  call    SepDumpQueryResultToState
0x18000275c  mov     rcx, [r15+8]
0x180002760  lea     rax, [rbp+130h+arg_18]
0x180002767  mov     r9d, esi
0x18000276a  mov     [rsp+230h+var_210], rax
0x18000276f  lea     r8, [rsp+230h+var_1F0]
0x180002774  mov     rdx, r14
0x180002777  call    SdbShowApphelpFromQuery
0x18000277c  test    eax, eax
0x18000277e  jnz     short loc_180002792
0x180002780  lea     r9, aFailedToDoApph; "Failed to do apphelp processing"
0x180002787  mov     r8d, 0B80h
0x18000278d  jmp     loc_1800026A3
0x180002792  cmp     [rbp+130h+arg_18], 0
0x180002799  mov     r9, [r15+8]
0x18000279d  jz      short loc_1800027DC
0x18000279f  mov     [rsp+230h+var_210], r9
0x1800027a4  lea     rdx, aSeInitializeen_0; "SE_InitializeEngine"
0x1800027ab  lea     r9, aApphelpedProce; "Apphelped process is terminating, %ws"
0x1800027b2  mov     r8d, 0B86h
0x1800027b8  mov     ecx, 3
0x1800027bd  call    AslLogCallPrintf
0x1800027c2  call    cs:__imp_GetCurrentProcess
0x1800027c8  mov     edx, cs:g_dwApphelpExitCode; uExitCode
0x1800027ce  mov     rcx, rax; hProcess
0x1800027d1  call    cs:__imp_TerminateProcess
0x1800027d7  jmp     loc_1800028F9
0x1800027dc  lea     r8, [rsp+230h+var_1F0]
0x1800027e1  mov     [rsp+230h+var_210], 0
0x1800027ea  mov     rdx, r14
0x1800027ed  call    SeSdbProcessQueryResult
0x1800027f2  mov     edi, eax
0x1800027f4  test    eax, eax
0x1800027f6  jns     short loc_18000280A
0x1800027f8  lea     r9, aFailedToInitia_6; "Failed to initialize engine from query "...
0x1800027ff  mov     r8d, 0B95h
0x180002805  jmp     loc_180002706
0x18000280a  call    IsArmadilloProtected
0x18000280f  test    eax, eax
0x180002811  jz      short loc_18000285F
0x180002813  mov     rcx, cs:g_Engine
0x18000281a  lea     r9, g_ArmadilloHooks; int
0x180002821  mov     [rsp+230h+pullResult], 0; pullResult
0x18000282a  mov     r8d, esi; int
0x18000282d  mov     [rsp+230h+var_208], esi; int
0x180002831  or      rdx, 0FFFFFFFFFFFFFFFFh; int
0x180002835  mov     [rsp+230h+var_210], 2; __int64
0x18000283e  mov     rcx, [rcx+18h]; int
0x180002842  call    SeHookManagerAddHooks
0x180002847  mov     edi, eax
0x180002849  test    eax, eax
0x18000284b  jns     short loc_18000285F
0x18000284d  lea     r9, aFailedToAddArm; "Failed to add Armadillo hooks"
0x180002854  mov     r8d, 0BA6h
0x18000285a  jmp     loc_180002706
0x18000285f  mov     rdx, cs:g_DataTableEntry
0x180002866  mov     rdx, [rdx+30h]
0x18000286a  call    SeEngineShimDllLoaded
0x18000286f  mov     rcx, cs:g_Engine
0x180002876  mov     rcx, [rcx]
0x180002879  call    SeFlagManagerExecute
0x18000287e  test    eax, eax
0x180002880  jns     short loc_18000289D
0x180002882  lea     r9, aFailedToApplyF; "Failed to apply flags"
0x180002889  mov     r8d, 0BB7h
0x18000288f  lea     rdx, aSeInitializeen_0; "SE_InitializeEngine"
0x180002896  mov     ecx, esi
0x180002898  call    AslLogCallPrintf
0x18000289d  mov     rcx, cs:g_Engine
0x1800028a4  mov     rcx, [rcx+8]
0x1800028a8  call    SeQuirkManagerExecute
0x1800028ad  test    eax, eax
0x1800028af  jns     short loc_1800028CC
0x1800028b1  lea     r9, aFailedToApplyQ; "Failed to apply quirks"
0x1800028b8  mov     r8d, 0BBCh
0x1800028be  lea     rdx, aSeInitializeen_0; "SE_InitializeEngine"
0x1800028c5  mov     ecx, esi
0x1800028c7  call    AslLogCallPrintf
0x1800028cc  mov     rdx, cs:g_Engine
0x1800028d3  mov     rcx, r12
0x1800028d6  mov     rdx, [rdx+10h]
0x1800028da  call    SeShimManagerGetShimDllList
0x1800028df  mov     edi, eax
0x1800028e1  test    eax, eax
0x1800028e3  jns     short loc_1800028F7
0x1800028e5  lea     r9, aFailedToGetShi_1; "Failed to get shim dll list"
0x1800028ec  mov     r8d, 0BCCh
0x1800028f2  jmp     loc_180002706
0x1800028f7  xor     edi, edi
0x1800028f9  mov     rcx, r14; P
0x1800028fc  call    SdbReleaseDatabase
0x180002901  lea     rcx, g_EngineLock; CriticalSection
0x180002908  call    cs:__imp_RtlLeaveCriticalSection
0x18000290e  lea     r11, [rsp+230h+var_20]
0x180002916  mov     eax, edi
0x180002918  mov     rbx, [r11+30h]
0x18000291c  mov     rsi, [r11+38h]
0x180002920  mov     rsp, r11
0x180002923  pop     r15
0x180002925  pop     r14
0x180002927  pop     r12
0x180002929  pop     rdi
0x18000292a  pop     rbp
0x18000292b  retn
```
