# RunInstanceCompletion

- ea: `0x1800036f0`
- end: `0x1800038c6`
- name: `RunInstanceCompletion`
- size: `470`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180002770`

## callees

- `0x180002590`
- `0x1800036f0`
- `0x18000465c`
- `0x18000480c`
- `0x180004bf4`
- `0x180004f1c`
- `0x180004fa0`
- `0x180005020`
- `0x180005410`

## import_xrefs

- `wdi!WdiGetParameterByName` at `0x18000371c`
- `wdi!WdiGetParameterByName` at `0x18000377e`
- `wdi!WdiGetParameterByName` at `0x18000371c`
- `wdi!WdiGetParameterByName` at `0x18000377e`
- `wdi!WdiGetParameterData` at `0x180003741`
- `wdi!WdiGetParameterData` at `0x1800037a0`
- `wdi!WdiGetParameterData` at `0x180003741`
- `wdi!WdiGetParameterData` at `0x1800037a0`

## string_xrefs

- `0x180003722`: `MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n`

## pseudocode

```c
__int64 __fastcall RunInstanceCompletion(void *a1)
{
  int ParameterByName; // eax
  int v3; // r9d
  int ParameterData; // eax
  unsigned int v5; // edi
  int v6; // r9d
  int v7; // ebx
  int v8; // eax
  __int64 *v9; // rdx
  __int128 *v10; // rcx
  const EVENT_DESCRIPTOR *v11; // rcx
  unsigned int v12; // eax
  __int128 v14; // [rsp+30h] [rbp-50h] BYREF
  __int64 v15; // [rsp+40h] [rbp-40h]
  __int64 v16; // [rsp+48h] [rbp-38h]
  int v17; // [rsp+50h] [rbp-30h]
  __int64 v18[2]; // [rsp+58h] [rbp-28h] BYREF
  __int64 v19; // [rsp+68h] [rbp-18h]
  __int64 v20; // [rsp+70h] [rbp-10h]
  int v21; // [rsp+78h] [rbp-8h]
  unsigned int v22; // [rsp+B8h] [rbp+38h] BYREF
  unsigned int v23; // [rsp+C0h] [rbp+40h] BYREF
  __int64 v24; // [rsp+C8h] [rbp+48h] BYREF

  v23 = 0;
  v24 = 0;
  ParameterByName = WdiGetParameterByName(a1, 0, L"DMError", &v24);
  if ( ParameterByName >= 0 )
  {
    ParameterByName = WdiGetParameterData(v24, &v23, 4);
    if ( ParameterByName >= 0 )
      goto LABEL_6;
    v3 = 62;
  }
  else
  {
    v3 = 56;
  }
  DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "GetScenarioDMError", v3, ParameterByName);
LABEL_6:
  v22 = 0;
  v24 = 0;
  ParameterData = WdiGetParameterByName(a1, 0, L"ScenarioResult", &v24);
  v5 = ParameterData;
  if ( ParameterData < 0 )
  {
    v6 = 101;
LABEL_10:
    DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "GetScenarioResultParameter", v6, ParameterData);
    goto LABEL_11;
  }
  ParameterData = WdiGetParameterData(v24, &v22, 4);
  v5 = ParameterData;
  if ( ParameterData < 0 )
  {
    v6 = 107;
    goto LABEL_10;
  }
LABEL_11:
  v19 = 0;
  v20 = 0;
  v21 = 0;
  *(_OWORD *)v18 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v14 = 0;
  v7 = ResolverData::LoadFromWdi((ResolverData *)v18, a1);
  v8 = CrashEventData::LoadFromWdi((CrashEventData *)&v14, a1);
  v9 = v18;
  v10 = &v14;
  if ( v7 < 0 )
    v9 = 0;
  if ( v8 < 0 )
    v10 = 0;
  LogMsiCofire(v10, v9, v22, v23);
  switch ( v22 )
  {
    case 5u:
      goto LABEL_23;
    case 0xBu:
      v11 = (const EVENT_DESCRIPTOR *)&MSIRE_DM_ETW_EVENT_THROTTLED_FREQUENT_PRODUCT_INVOCATION;
      goto LABEL_24;
    case 0xCu:
      v11 = (const EVENT_DESCRIPTOR *)&MSIRE_DM_ETW_EVENT_THROTTLED_REPEATED_PRODUCT_INVOCATION;
      goto LABEL_24;
    case 0xFu:
      v12 = WriteServerFileAppEvent(&MSIRE_DM_ETW_EVENT_FILE_SKIPPED, (_WORD *)v14, *((_WORD **)&v14 + 1));
      goto LABEL_25;
    case 0x10u:
    case 0x11u:
    case 0x12u:
    case 0x14u:
LABEL_23:
      v11 = &MSIRE_DM_ETW_EVENT_REINSTALL_RECOMMENDED;
LABEL_24:
      v12 = WriteServerFileAppProductVersionEvent(
              v11,
              (_WORD *)v14,
              *((_WORD **)&v14 + 1),
              (_WORD *)v18[0],
              (_WORD *)v18[1]);
LABEL_25:
      v5 = v12;
      break;
  }
  CrashEventData::Free((CrashEventData *)&v14);
  ResolverData::Free((ResolverData *)v18);
  return v5;
}

```

## disassembly

```asm
0x1800036f0  push    rbp
0x1800036f2  push    rbx
0x1800036f3  push    rsi
0x1800036f4  push    rdi
0x1800036f5  push    r14
0x1800036f7  mov     rbp, rsp
0x1800036fa  sub     rsp, 80h
0x180003701  xor     r14d, r14d
0x180003704  lea     r9, [rbp+arg_18]
0x180003708  lea     r8, aDmerror; "DMError"
0x18000370f  mov     [rbp+arg_10], r14d
0x180003713  xor     edx, edx
0x180003715  mov     [rbp+arg_18], r14
0x180003719  mov     rsi, rcx
0x18000371c  call    cs:__imp_WdiGetParameterByName
0x180003722  lea     rbx, aMsiCofireError; "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n"
0x180003729  test    eax, eax
0x18000372b  jns     short loc_180003733
0x18000372d  lea     r9d, [r14+38h]
0x180003731  jmp     short loc_180003751
0x180003733  mov     rcx, [rbp+arg_18]
0x180003737  lea     rdx, [rbp+arg_10]
0x18000373b  mov     r8d, 4
0x180003741  call    cs:__imp_WdiGetParameterData
0x180003747  test    eax, eax
0x180003749  jns     short loc_180003766
0x18000374b  mov     r9d, 3Eh ; '>'
0x180003751  lea     r8, aGetscenariodme; "GetScenarioDMError"
0x180003758  mov     dword ptr [rsp+80h+var_60], eax
0x18000375c  mov     rdx, rbx; Format
0x18000375f  xor     ecx, ecx; Level
0x180003761  call    ?DebugPrint@@YAXKPEBDZZ; DebugPrint(ulong,char const *,...)
0x180003766  lea     r9, [rbp+arg_18]
0x18000376a  mov     [rbp+arg_8], r14d
0x18000376e  lea     r8, aScenarioresult; "ScenarioResult"
0x180003775  mov     [rbp+arg_18], r14
0x180003779  xor     edx, edx
0x18000377b  mov     rcx, rsi
0x18000377e  call    cs:__imp_WdiGetParameterByName
0x180003784  mov     edi, eax
0x180003786  test    eax, eax
0x180003788  jns     short loc_180003792
0x18000378a  mov     r9d, 65h ; 'e'
0x180003790  jmp     short loc_1800037B2
0x180003792  mov     rcx, [rbp+arg_18]
0x180003796  lea     rdx, [rbp+arg_8]
0x18000379a  mov     r8d, 4
0x1800037a0  call    cs:__imp_WdiGetParameterData
0x1800037a6  mov     edi, eax
0x1800037a8  test    eax, eax
0x1800037aa  jns     short loc_1800037C7
0x1800037ac  mov     r9d, 6Bh ; 'k'
0x1800037b2  lea     r8, aGetscenariores; "GetScenarioResultParameter"
0x1800037b9  mov     dword ptr [rsp+80h+var_60], eax
0x1800037bd  mov     rdx, rbx; Format
0x1800037c0  xor     ecx, ecx; Level
0x1800037c2  call    ?DebugPrint@@YAXKPEBDZZ; DebugPrint(ulong,char const *,...)
0x1800037c7  xorps   xmm0, xmm0
0x1800037ca  mov     [rbp+var_18], r14
0x1800037ce  mov     rdx, rsi; void *
0x1800037d1  mov     [rbp+var_10], r14
0x1800037d5  lea     rcx, [rbp+var_28]; this
0x1800037d9  mov     [rbp+var_8], r14d
0x1800037dd  movdqu  xmmword ptr [rbp+var_28], xmm0
0x1800037e2  call    ?LoadFromWdi@ResolverData@@QEAAJPEAX@Z; ResolverData::LoadFromWdi(void *)
0x1800037e7  xorps   xmm0, xmm0
0x1800037ea  mov     [rbp+var_40], r14
0x1800037ee  mov     rdx, rsi; void *
0x1800037f1  mov     [rbp+var_38], r14
0x1800037f5  lea     rcx, [rbp+var_50]; this
0x1800037f9  mov     [rbp+var_30], r14d
0x1800037fd  movdqu  [rbp+var_50], xmm0
0x180003802  mov     ebx, eax
0x180003804  call    ?LoadFromWdi@CrashEventData@@QEAAJPEAX@Z; CrashEventData::LoadFromWdi(void *)
0x180003809  mov     r9d, [rbp+arg_10]
0x18000380d  lea     rdx, [rbp+var_28]
0x180003811  mov     r8d, [rbp+arg_8]
0x180003815  lea     rcx, [rbp+var_50]
0x180003819  test    ebx, ebx
0x18000381b  cmovs   rdx, r14
0x18000381f  test    eax, eax
0x180003821  cmovs   rcx, r14
0x180003825  call    LogMsiCofire
0x18000382a  mov     ecx, [rbp+arg_8]
0x18000382d  sub     ecx, 5
0x180003830  jz      short loc_180003859
0x180003832  sub     ecx, 6
0x180003835  jz      loc_1800038BD
0x18000383b  sub     ecx, 1
0x18000383e  jz      short loc_1800038B4
0x180003840  sub     ecx, 3
0x180003843  jz      short loc_18000389E
0x180003845  sub     ecx, 1
0x180003848  jz      short loc_180003859
0x18000384a  sub     ecx, 1
0x18000384d  jz      short loc_180003859
0x18000384f  sub     ecx, 1
0x180003852  jz      short loc_180003859
0x180003854  cmp     ecx, 2
0x180003857  jnz     short loc_18000387C
0x180003859  lea     rcx, MSIRE_DM_ETW_EVENT_REINSTALL_RECOMMENDED; EventDescriptor
0x180003860  mov     rax, [rbp+var_28+8]
0x180003864  mov     r9, [rbp+var_28]
0x180003868  mov     r8, qword ptr [rbp+var_50+8]
0x18000386c  mov     rdx, qword ptr [rbp+var_50]
0x180003870  mov     [rsp+80h+var_60], rax; __int64
0x180003875  call    WriteServerFileAppProductVersionEvent
0x18000387a  mov     edi, eax
0x18000387c  lea     rcx, [rbp+var_50]; this
0x180003880  call    ?Free@CrashEventData@@QEAAXXZ; CrashEventData::Free(void)
0x180003885  lea     rcx, [rbp+var_28]; this
0x180003889  call    ?Free@ResolverData@@QEAAXXZ; ResolverData::Free(void)
0x18000388e  mov     eax, edi
0x180003890  add     rsp, 80h
0x180003897  pop     r14
0x180003899  pop     rdi
0x18000389a  pop     rsi
0x18000389b  pop     rbx
0x18000389c  pop     rbp
0x18000389d  retn
0x18000389e  mov     r8, qword ptr [rbp+var_50+8]
0x1800038a2  lea     rcx, MSIRE_DM_ETW_EVENT_FILE_SKIPPED; EventDescriptor
0x1800038a9  mov     rdx, qword ptr [rbp+var_50]
0x1800038ad  call    WriteServerFileAppEvent
0x1800038b2  jmp     short loc_18000387A
0x1800038b4  lea     rcx, MSIRE_DM_ETW_EVENT_THROTTLED_REPEATED_PRODUCT_INVOCATION
0x1800038bb  jmp     short loc_180003860
0x1800038bd  lea     rcx, MSIRE_DM_ETW_EVENT_THROTTLED_FREQUENT_PRODUCT_INVOCATION
0x1800038c4  jmp     short loc_180003860
```
