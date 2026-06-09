# EfsDisableEdp

- ea: `0x180041590`
- end: `0x1800419ff`
- name: `EfsDisableEdp`
- size: `1135`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800274b8`

## callees

- `0x180001a7c`
- `0x180001cc8`
- `0x180015294`
- `0x18003fc44`
- `0x18003ff18`
- `0x180041590`
- `0x180063600`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x1800dca3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004168c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800416f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800418f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004168c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800416f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800418f9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180041682`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180041682`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004166e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004166e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800418ef`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800418ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180041938`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180041938`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004165f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004165f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800416e8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800416e8`
- `ntdll!RtlPublishWnfStateData` at `0x1800418c9`
- `ntdll!RtlPublishWnfStateData` at `0x1800418c9`

## pseudocode

```c
__int64 __fastcall EfsDisableEdp(int a1)
{
  int v1; // edi
  int v2; // esi
  signed int EdpEnforcementLevel; // ebx
  int v4; // eax
  int v5; // r14d
  HANDLE CurrentThread; // rax
  int v7; // ecx
  __int64 v8; // rcx
  int v9; // ecx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  int v15; // [rsp+50h] [rbp-20h] BYREF
  int v16; // [rsp+54h] [rbp-1Ch] BYREF
  signed int v17; // [rsp+58h] [rbp-18h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp-10h] BYREF
  __int64 v19; // [rsp+68h] [rbp-8h] BYREF
  int v20; // [rsp+B0h] [rbp+40h] BYREF
  int pvData; // [rsp+B8h] [rbp+48h] BYREF
  int v22; // [rsp+C0h] [rbp+50h] BYREF
  DWORD pcbData; // [rsp+C8h] [rbp+58h] BYREF

  v1 = 0;
  pcbData = 4;
  v2 = 0;
  TokenHandle = 0;
  pvData = 0;
  v20 = 0;
  v22 = 0;
  fnEfsLogTrace1Strings(a1, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 32, 99);
  EdpEnforcementLevel = EdpGetEdpEnforcementLevel(&v22);
  v4 = fnEfsLogTrace1String1Dword(
         g_hPublisher,
         (unsigned int)EFS_TRACE_COMPLETE_EVENT,
         (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
         (unsigned int)&sourceString,
         EdpEnforcementLevel,
         32,
         99);
  v5 = v22;
  if ( v4 >= 0 )
  {
    if ( v22 )
    {
      RegGetValueW(
        HKEY_LOCAL_MACHINE,
        L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\EFS",
        L"OverrideEdpDisable",
        0x20000010u,
        0,
        &pvData,
        &pcbData);
      if ( !pvData )
      {
        CurrentThread = GetCurrentThread();
        if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
        {
          if ( RevertToSelf() )
          {
            fnEfsLogTrace1Strings(v7, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 32, 145);
            EdpEnforcementLevel = EfsGetEdpEnforcementLevelInPolicyManager((enum _EDP_ENFORCEMENT_LEVEL *)&v20);
            if ( (int)fnEfsLogTrace1String1Dword(
                        g_hPublisher,
                        (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                        (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                        (unsigned int)&sourceString,
                        EdpEnforcementLevel,
                        32,
                        145) < 0 )
            {
LABEL_24:
              v2 = v20;
            }
            else
            {
              v2 = v20;
              if ( v5 != v20 )
                MicrosoftTelemetryAssertTriggeredNoArgs(v8);
              if ( v2 )
              {
                while ( 1 )
                {
                  fnEfsLogTrace1Strings(v8, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 32, 157);
                  EdpEnforcementLevel = EfsSetEdpEnforcementLevelInPolicyManager();
                  if ( (int)fnEfsLogTrace1String1Dword(
                              g_hPublisher,
                              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                              (unsigned int)&sourceString,
                              EdpEnforcementLevel,
                              32,
                              157) < 0 )
                    break;
                  fnEfsLogTrace1Strings(v9, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 32, 158);
                  EdpEnforcementLevel = EfsGetEdpEnforcementLevelInPolicyManager((enum _EDP_ENFORCEMENT_LEVEL *)&v20);
                  if ( (int)fnEfsLogTrace1String1Dword(
                              g_hPublisher,
                              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                              (unsigned int)&sourceString,
                              EdpEnforcementLevel,
                              32,
                              158) < 0 )
                    goto LABEL_24;
                  v2 = v20;
                  if ( !v20 )
                    goto LABEL_23;
                  if ( (unsigned int)++v1 >= 0x19 )
                  {
                    if ( v1 == 25 )
                    {
                      EdpEnforcementLevel = -2147418113;
                      fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, -2147418113, 32, 168);
                      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147418113, 32, 169);
                      break;
                    }
LABEL_23:
                    RtlPublishWnfStateData(WNF_ENTR_EVALUATE_EDP_CONFIGURATION_STATE, 0, 0, 0, 0);
                    fnEfsLogTrace0(v10, EFS_WIP_DISABLE_SUCCESS, 32, 1462);
                    break;
                  }
                }
              }
            }
            if ( !SetThreadToken(0, TokenHandle) )
            {
              EdpEnforcementLevel = GetLastError();
              fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, EdpEnforcementLevel, 32, 191);
              if ( EdpEnforcementLevel > 0 )
                EdpEnforcementLevel = (unsigned __int16)EdpEnforcementLevel | 0x80070000;
            }
          }
          else
          {
            EdpEnforcementLevel = GetLastError();
            fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, EdpEnforcementLevel, 32, 134);
            if ( EdpEnforcementLevel > 0 )
              EdpEnforcementLevel = (unsigned __int16)EdpEnforcementLevel | 0x80070000;
            fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, EdpEnforcementLevel, 32, 135);
          }
        }
        else
        {
          EdpEnforcementLevel = GetLastError();
          fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, EdpEnforcementLevel, 32, 127);
          if ( EdpEnforcementLevel > 0 )
            EdpEnforcementLevel = (unsigned __int16)EdpEnforcementLevel | 0x80070000;
          fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, EdpEnforcementLevel, 32, 128);
        }
      }
    }
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v5 )
  {
    if ( EdpEnforcementLevel < 0 )
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_WIP_DISABLE_ERROR, EdpEnforcementLevel, 32, 204);
    if ( (unsigned int)dword_180114250 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180114250, 0x400000000000LL) )
    {
      v20 = pvData;
      v19 = 0x1000000;
      v22 = v5;
      v15 = v2;
      v16 = v1;
      v17 = EdpEnforcementLevel;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v11,
        (__int64)&dword_18010204C,
        v12,
        v13,
        (__int64)&v17,
        (__int64)&v16,
        (__int64)&v15,
        (__int64)&v22,
        (__int64)&v20,
        (__int64)&v19);
    }
  }
  return (unsigned int)EdpEnforcementLevel;
}

```

## disassembly

```asm
0x180041590  push    rbp
0x180041592  push    rbx
0x180041593  push    rsi
0x180041594  push    rdi
0x180041595  push    r13
0x180041597  push    r14
0x180041599  push    r15
0x18004159b  mov     rbp, rsp
0x18004159e  sub     rsp, 70h
0x1800415a2  xor     edi, edi
0x1800415a4  mov     [rbp+arg_18], 4
0x1800415ab  xor     esi, esi
0x1800415ad  mov     [rbp+TokenHandle], rdi
0x1800415b1  lea     r15, sourceString
0x1800415b8  mov     [rbp+arg_8], edi
0x1800415bb  mov     r14d, 563h
0x1800415c1  mov     [rbp+arg_0], esi
0x1800415c4  lea     r13d, [rdi+20h]
0x1800415c8  mov     [rbp+arg_10], esi
0x1800415cb  mov     r9d, r13d
0x1800415ce  mov     dword ptr [rsp+70h+pdwType], r14d
0x1800415d3  mov     r8, r15
0x1800415d6  lea     rdx, EFS_TRACE_START_EVENT
0x1800415dd  call    fnEfsLogTrace1Strings
0x1800415e2  lea     rcx, [rbp+arg_10]
0x1800415e6  call    EdpGetEdpEnforcementLevel
0x1800415eb  mov     rcx, cs:g_hPublisher
0x1800415f2  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800415f9  mov     dword ptr [rsp+70h+pcbData], r14d
0x1800415fe  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180041605  mov     dword ptr [rsp+70h+pvData], r13d
0x18004160a  mov     r9, r15
0x18004160d  mov     dword ptr [rsp+70h+pdwType], eax
0x180041611  mov     ebx, eax
0x180041613  call    fnEfsLogTrace1String1Dword
0x180041618  mov     r14d, [rbp+arg_10]
0x18004161c  test    eax, eax
0x18004161e  js      loc_18004192F
0x180041624  test    r14d, r14d
0x180041627  jz      loc_18004192F
0x18004162d  lea     rax, [rbp+arg_18]
0x180041631  mov     r9d, 20000010h; dwFlags
0x180041637  mov     [rsp+70h+pcbData], rax; pcbData
0x18004163c  lea     r8, aOverrideedpdis; "OverrideEdpDisable"
0x180041643  lea     rax, [rbp+arg_8]
0x180041647  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18004164e  mov     [rsp+70h+pvData], rax; pvData
0x180041653  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18004165a  mov     [rsp+70h+pdwType], rsi; pdwType
0x18004165f  call    cs:__imp_RegGetValueW
0x180041665  cmp     [rbp+arg_8], esi
0x180041668  jnz     loc_18004192F
0x18004166e  call    cs:__imp_GetCurrentThread
0x180041674  mov     rcx, rax; ThreadHandle
0x180041677  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18004167b  lea     edx, [rdi+0Ch]; DesiredAccess
0x18004167e  lea     r8d, [rdi+1]; OpenAsSelf
0x180041682  call    cs:__imp_OpenThreadToken
0x180041688  test    eax, eax
0x18004168a  jnz     short loc_1800416E8
0x18004168c  call    cs:__imp_GetLastError
0x180041692  mov     rcx, cs:g_hPublisher
0x180041699  lea     rdx, EFS_API_ERROR
0x1800416a0  mov     r8d, eax
0x1800416a3  mov     dword ptr [rsp+70h+pdwType], 57Fh
0x1800416ab  mov     r9d, r13d
0x1800416ae  mov     ebx, eax
0x1800416b0  call    fnEfsLogTrace1
0x1800416b5  test    ebx, ebx
0x1800416b7  jle     short loc_1800416C2
0x1800416b9  movzx   ebx, bx
0x1800416bc  or      ebx, 80070000h
0x1800416c2  mov     dword ptr [rsp+70h+pdwType], 580h
0x1800416ca  mov     rcx, cs:g_hPublisher
0x1800416d1  lea     rdx, EFS_TRACE_ERROR
0x1800416d8  mov     r9d, r13d
0x1800416db  mov     r8d, ebx
0x1800416de  call    fnEfsLogTrace1
0x1800416e3  jmp     loc_18004192F
0x1800416e8  call    cs:__imp_RevertToSelf
0x1800416ee  test    eax, eax
0x1800416f0  jnz     short loc_180041732
0x1800416f2  call    cs:__imp_GetLastError
0x1800416f8  mov     rcx, cs:g_hPublisher
0x1800416ff  lea     rdx, EFS_API_ERROR
0x180041706  mov     r8d, eax
0x180041709  mov     dword ptr [rsp+70h+pdwType], 586h
0x180041711  mov     r9d, r13d
0x180041714  mov     ebx, eax
0x180041716  call    fnEfsLogTrace1
0x18004171b  test    ebx, ebx
0x18004171d  jle     short loc_180041728
0x18004171f  movzx   ebx, bx
0x180041722  or      ebx, 80070000h
0x180041728  mov     dword ptr [rsp+70h+pdwType], 587h
0x180041730  jmp     short loc_1800416CA
0x180041732  mov     esi, 591h
0x180041737  lea     rdx, EFS_TRACE_START_EVENT
0x18004173e  mov     r9d, r13d
0x180041741  mov     dword ptr [rsp+70h+pdwType], esi
0x180041745  mov     r8, r15
0x180041748  call    fnEfsLogTrace1Strings
0x18004174d  lea     rcx, [rbp+arg_0]; enum _EDP_ENFORCEMENT_LEVEL *
0x180041751  call    ?EfsGetEdpEnforcementLevelInPolicyManager@@YAJPEAW4_EDP_ENFORCEMENT_LEVEL@@@Z; EfsGetEdpEnforcementLevelInPolicyManager(_EDP_ENFORCEMENT_LEVEL *)
0x180041756  mov     rcx, cs:g_hPublisher
0x18004175d  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180041764  mov     dword ptr [rsp+70h+pcbData], esi
0x180041768  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x18004176f  mov     dword ptr [rsp+70h+pvData], r13d
0x180041774  mov     r9, r15
0x180041777  mov     dword ptr [rsp+70h+pdwType], eax
0x18004177b  mov     ebx, eax
0x18004177d  call    fnEfsLogTrace1String1Dword
0x180041782  test    eax, eax
0x180041784  js      loc_1800418E6
0x18004178a  mov     esi, [rbp+arg_0]
0x18004178d  cmp     r14d, esi
0x180041790  jz      short loc_180041797
0x180041792  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "EdpEnforcementLevelCached == EdpEnforcementLevel")
0x180041797  test    esi, esi
0x180041799  jz      loc_1800418E9
0x18004179f  mov     r9d, r13d
0x1800417a2  mov     dword ptr [rsp+70h+pdwType], 59Dh
0x1800417aa  mov     r8, r15
0x1800417ad  lea     rdx, EFS_TRACE_START_EVENT
0x1800417b4  call    fnEfsLogTrace1Strings
0x1800417b9  call    ?EfsSetEdpEnforcementLevelInPolicyManager@@YAJW4_EDP_ENFORCEMENT_LEVEL@@@Z; EfsSetEdpEnforcementLevelInPolicyManager(_EDP_ENFORCEMENT_LEVEL)
0x1800417be  mov     rcx, cs:g_hPublisher
0x1800417c5  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800417cc  mov     dword ptr [rsp+70h+pcbData], 59Dh
0x1800417d4  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800417db  mov     dword ptr [rsp+70h+pvData], r13d
0x1800417e0  mov     r9, r15
0x1800417e3  mov     dword ptr [rsp+70h+pdwType], eax
0x1800417e7  mov     ebx, eax
0x1800417e9  call    fnEfsLogTrace1String1Dword
0x1800417ee  test    eax, eax
0x1800417f0  js      loc_1800418E9
0x1800417f6  mov     esi, 59Eh
0x1800417fb  lea     rdx, EFS_TRACE_START_EVENT
0x180041802  mov     r9d, r13d
0x180041805  mov     dword ptr [rsp+70h+pdwType], esi
0x180041809  mov     r8, r15
0x18004180c  call    fnEfsLogTrace1Strings
0x180041811  lea     rcx, [rbp+arg_0]; enum _EDP_ENFORCEMENT_LEVEL *
0x180041815  call    ?EfsGetEdpEnforcementLevelInPolicyManager@@YAJPEAW4_EDP_ENFORCEMENT_LEVEL@@@Z; EfsGetEdpEnforcementLevelInPolicyManager(_EDP_ENFORCEMENT_LEVEL *)
0x18004181a  mov     rcx, cs:g_hPublisher
0x180041821  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180041828  mov     dword ptr [rsp+70h+pcbData], esi
0x18004182c  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180041833  mov     dword ptr [rsp+70h+pvData], r13d
0x180041838  mov     r9, r15
0x18004183b  mov     dword ptr [rsp+70h+pdwType], eax
0x18004183f  mov     ebx, eax
0x180041841  call    fnEfsLogTrace1String1Dword
0x180041846  test    eax, eax
0x180041848  js      loc_1800418E6
0x18004184e  mov     esi, [rbp+arg_0]
0x180041851  test    esi, esi
0x180041853  jz      short loc_1800418B1
0x180041855  inc     edi
0x180041857  cmp     edi, 19h
0x18004185a  jb      loc_18004179F
0x180041860  jnz     short loc_1800418B1
0x180041862  mov     rcx, cs:g_hPublisher
0x180041869  lea     rdx, EFS_API_ERROR
0x180041870  mov     r15d, 8000FFFFh
0x180041876  mov     dword ptr [rsp+70h+pdwType], 5A8h
0x18004187e  mov     r8d, r15d
0x180041881  mov     r9d, r13d
0x180041884  mov     ebx, 8000FFFFh
0x180041889  call    fnEfsLogTrace1
0x18004188e  mov     rcx, cs:g_hPublisher
0x180041895  lea     rdx, EFS_TRACE_ERROR
0x18004189c  mov     r9d, r13d
0x18004189f  mov     dword ptr [rsp+70h+pdwType], 5A9h
0x1800418a7  mov     r8d, r15d
0x1800418aa  call    fnEfsLogTrace1
0x1800418af  jmp     short loc_1800418E9
0x1800418b1  mov     rcx, cs:WNF_ENTR_EVALUATE_EDP_CONFIGURATION_STATE
0x1800418b8  xor     r9d, r9d
0x1800418bb  xor     r8d, r8d
0x1800418be  mov     [rsp+70h+pdwType], 0
0x1800418c7  xor     edx, edx
0x1800418c9  call    cs:__imp_RtlPublishWnfStateData
0x1800418cf  mov     r9d, 5B6h
0x1800418d5  lea     rdx, EFS_WIP_DISABLE_SUCCESS
0x1800418dc  mov     r8d, r13d
0x1800418df  call    fnEfsLogTrace0
0x1800418e4  jmp     short loc_1800418E9
0x1800418e6  mov     esi, [rbp+arg_0]
0x1800418e9  mov     rdx, [rbp+TokenHandle]; Token
0x1800418ed  xor     ecx, ecx; Thread
0x1800418ef  call    cs:__imp_SetThreadToken
0x1800418f5  test    eax, eax
0x1800418f7  jnz     short loc_18004192F
0x1800418f9  call    cs:__imp_GetLastError
0x1800418ff  mov     rcx, cs:g_hPublisher
0x180041906  lea     rdx, EFS_API_ERROR
0x18004190d  mov     r8d, eax
0x180041910  mov     dword ptr [rsp+70h+pdwType], 5BFh
0x180041918  mov     r9d, r13d
0x18004191b  mov     ebx, eax
0x18004191d  call    fnEfsLogTrace1
0x180041922  test    ebx, ebx
0x180041924  jle     short loc_18004192F
0x180041926  movzx   ebx, bx
0x180041929  or      ebx, 80070000h
0x18004192f  mov     rcx, [rbp+TokenHandle]; hObject
0x180041933  test    rcx, rcx
0x180041936  jz      short loc_18004193E
0x180041938  call    cs:__imp_CloseHandle
0x18004193e  test    r14d, r14d
0x180041941  jz      loc_1800419EE
0x180041947  test    ebx, ebx
0x180041949  jns     short loc_18004196C
0x18004194b  mov     rcx, cs:g_hPublisher
0x180041952  lea     rdx, EFS_WIP_DISABLE_ERROR
0x180041959  mov     r9d, r13d
0x18004195c  mov     dword ptr [rsp+70h+pdwType], 5CCh
0x180041964  mov     r8d, ebx
0x180041967  call    fnEfsLogTrace1
0x18004196c  mov     eax, cs:dword_180114250
0x180041972  cmp     eax, 5
0x180041975  jbe     short loc_1800419EE
0x180041977  mov     rdx, 400000000000h
0x180041981  lea     rcx, dword_180114250
0x180041988  call    _tlgKeywordOn
0x18004198d  test    al, al
0x18004198f  jz      short loc_1800419EE
0x180041991  mov     eax, [rbp+arg_8]
0x180041994  lea     rdx, dword_18010204C
0x18004199b  mov     [rbp+arg_0], eax
0x18004199e  lea     rax, [rbp+var_8]
0x1800419a2  mov     [rsp+70h+var_28], rax
0x1800419a7  lea     rax, [rbp+arg_0]
0x1800419ab  mov     [rsp+70h+var_30], rax
0x1800419b0  lea     rax, [rbp+arg_10]
0x1800419b4  mov     [rsp+70h+var_38], rax
0x1800419b9  lea     rax, [rbp+var_20]
0x1800419bd  mov     [rsp+70h+pcbData], rax
0x1800419c2  lea     rax, [rbp+var_1C]
0x1800419c6  mov     [rsp+70h+pvData], rax
0x1800419cb  lea     rax, [rbp+var_18]
0x1800419cf  mov     [rsp+70h+pdwType], rax
0x1800419d4  mov     [rbp+var_8], 1000000h
0x1800419dc  mov     [rbp+arg_10], r14d
0x1800419e0  mov     [rbp+var_20], esi
0x1800419e3  mov     [rbp+var_1C], edi
0x1800419e6  mov     [rbp+var_18], ebx
0x1800419e9  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3333AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1800419ee  mov     eax, ebx
0x1800419f0  add     rsp, 70h
0x1800419f4  pop     r15
0x1800419f6  pop     r14
0x1800419f8  pop     r13
0x1800419fa  pop     rdi
0x1800419fb  pop     rsi
0x1800419fc  pop     rbx
0x1800419fd  pop     rbp
0x1800419fe  retn
```
