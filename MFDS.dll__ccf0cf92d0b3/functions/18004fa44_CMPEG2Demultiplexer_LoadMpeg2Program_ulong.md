# CMPEG2Demultiplexer::LoadMpeg2Program_(ulong)

- ea: `0x18004fa44`
- end: `0x180050144`
- name: `?LoadMpeg2Program_@CMPEG2Demultiplexer@@AEAAJK@Z`
- size: `1792`
- prototype: `__int64 __fastcall(CMPEG2Demultiplexer *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002b540`
- `0x18002bcac`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x1800167d8`
- `0x18002166c`
- `0x180042cf0`
- `0x18004e978`
- `0x18004fa44`
- `0x180051ce4`
- `0x18005248c`
- `0x180073d0c`
- `0x18009bd00`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004fac8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004fac8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004fba4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004fc40`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004fcc6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004fd4c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004fdd2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004fe58`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004fba4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004fc40`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004fcc6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004fd4c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004fdd2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004fe58`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004fb6b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004fc07`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004fc8d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004fd13`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004fd99`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004fe1f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004fb6b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004fc07`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004fc8d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004fd13`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004fd99`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004fe1f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800500c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800500c9`

## pseudocode

```c
__int64 __fastcall CMPEG2Demultiplexer::LoadMpeg2Program_(CMPEG2Demultiplexer *this, unsigned int a2)
{
  HKEY *v2; // r15
  int v5; // edi
  CMPEG2ProgramController *v6; // rsi
  LSTATUS v7; // ebx
  HKEY v8; // rbx
  int v9; // eax
  bool v10; // zf
  int v11; // eax
  HKEY v12; // rbx
  HKEY v13; // rbx
  HKEY v14; // rbx
  HKEY v15; // rbx
  HKEY v16; // rbx
  struct CMpeg2Stats **v17; // rbx
  unsigned int v18; // edx
  CMPEG2PushClock *v19; // rcx
  CMPEG2PushClock *v20; // rax
  CMPEG2ProgramController *v21; // rax
  CMPEG2ProgramController *v22; // rcx
  CMPEG2ProgramController *v23; // rax
  __int64 v24; // rdx
  CMpeg2Stats *v25; // rbx
  int v26; // eax
  __int64 v27; // rdx
  CMPEG2PushClock *v28; // rcx
  HKEY v29; // rcx
  BYTE v31[4]; // [rsp+60h] [rbp-20h] BYREF
  BYTE v32[4]; // [rsp+64h] [rbp-1Ch] BYREF
  BYTE v33[4]; // [rsp+68h] [rbp-18h] BYREF
  BYTE v34[4]; // [rsp+6Ch] [rbp-14h] BYREF
  BYTE v35[4]; // [rsp+70h] [rbp-10h] BYREF
  DWORD dwDisposition; // [rsp+74h] [rbp-Ch] BYREF
  DWORD cbData; // [rsp+78h] [rbp-8h] BYREF
  DWORD Type; // [rsp+7Ch] [rbp-4h] BYREF
  int Data; // [rsp+C0h] [rbp+40h] BYREF
  int v40; // [rsp+D0h] [rbp+50h] BYREF
  int v41; // [rsp+D8h] [rbp+58h] BYREF

  v2 = (HKEY *)((char *)this + 272);
  v40 = 0;
  dwDisposition = 0;
  v5 = 0;
  v41 = 0;
  *(_DWORD *)v35 = 0;
  v6 = 0;
  *(_DWORD *)v34 = 0;
  *(_DWORD *)v33 = 0;
  *(_DWORD *)v32 = 0;
  *(_DWORD *)v31 = 0;
  v7 = RegCreateKeyExW(
         HKEY_CURRENT_USER,
         L"SOFTWARE\\Microsoft\\MPEG2Demultiplexer\\Program",
         0,
         0,
         0,
         0x2001Fu,
         0,
         (PHKEY)this + 34,
         &dwDisposition);
  if ( v7 )
  {
    *v2 = 0;
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)&Data,
      "CMPEG2Demultiplexer::LoadMpeg2Program_",
      1340);
    if ( byte_1800EACCB )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 17), 21, &WPP_a94830b6bd5f3023efd6e0bdea57da03_Traceguids, this, v7);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&Data);
  }
  v8 = *v2;
  Data = 0;
  v41 = 1;
  if ( !v8
    || ((cbData = 4, Type = 4, RegQueryValueExW(v8, L"Clock", 0, &Type, (LPBYTE)&Data, &cbData))
      ? (RegSetValueExW(v8, L"Clock", 0, 4u, (const BYTE *)&v41, 4u), v9 = v41)
      : (v9 = Data, v41 = Data),
        v10 = v9 == 0,
        v11 = 0,
        !v10) )
  {
    v11 = 1;
  }
  v12 = *v2;
  *((_DWORD *)this + 72) = v11;
  Data = 0;
  *(_DWORD *)v35 = 2000;
  if ( v12 )
  {
    Type = 4;
    cbData = 4;
    if ( RegQueryValueExW(v12, L"ClockSubordinateMinSamplingWindowMillis", 0, &cbData, (LPBYTE)&Data, &Type) )
      RegSetValueExW(v12, L"ClockSubordinateMinSamplingWindowMillis", 0, 4u, v35, 4u);
    else
      *(_DWORD *)v35 = Data;
  }
  v13 = *v2;
  Data = 0;
  *(_DWORD *)v34 = 240000;
  if ( v13 )
  {
    Type = 4;
    cbData = 4;
    if ( RegQueryValueExW(v13, L"ClockSubordinateHistoryMillis", 0, &cbData, (LPBYTE)&Data, &Type) )
      RegSetValueExW(v13, L"ClockSubordinateHistoryMillis", 0, 4u, v34, 4u);
    else
      *(_DWORD *)v34 = Data;
  }
  v14 = *v2;
  Data = 0;
  *(_DWORD *)v33 = 95;
  if ( v14 )
  {
    Type = 4;
    cbData = 4;
    if ( RegQueryValueExW(v14, L"ClockSubordinateMinSlavable", 0, &cbData, (LPBYTE)&Data, &Type) )
      RegSetValueExW(v14, L"ClockSubordinateMinSlavable", 0, 4u, v33, 4u);
    else
      *(_DWORD *)v33 = Data;
  }
  v15 = *v2;
  Data = 0;
  *(_DWORD *)v32 = 105;
  if ( v15 )
  {
    Type = 4;
    cbData = 4;
    if ( RegQueryValueExW(v15, L"ClockSubordinateMaxSlavable", 0, &cbData, (LPBYTE)&Data, &Type) )
      RegSetValueExW(v15, L"ClockSubordinateMaxSlavable", 0, 4u, v32, 4u);
    else
      *(_DWORD *)v32 = Data;
  }
  v16 = *v2;
  Data = 0;
  *(_DWORD *)v31 = 60;
  if ( v16 )
  {
    Type = 4;
    cbData = 4;
    if ( RegQueryValueExW(v16, L"ShiftMaxGlitchesPerHour", 0, &cbData, (LPBYTE)&Data, &Type) )
      RegSetValueExW(v16, L"ShiftMaxGlitchesPerHour", 0, 4u, v31, 4u);
    else
      *(_DWORD *)v31 = Data;
  }
  v17 = (struct CMpeg2Stats **)((char *)this + 264);
  v19 = (CMPEG2PushClock *)operator new(0x2D0u);
  if ( v19 )
  {
    v20 = CMPEG2PushClock::CMPEG2PushClock(
            v19,
            *((_DWORD *)this + 72),
            *v2,
            *v17,
            this,
            *(unsigned int *)v35,
            *(unsigned int *)v34,
            *(unsigned int *)v33,
            *(unsigned int *)v32,
            *(unsigned int *)v31,
            &v40);
    v5 = v40;
  }
  else
  {
    v20 = 0;
  }
  *((_QWORD *)this + 35) = v20;
  if ( !v20 )
    goto LABEL_55;
  if ( v5 < 0 )
    goto LABEL_58;
  if ( *((_DWORD *)this + 74) )
  {
    v21 = (CMPEG2ProgramController *)operator new(0xD0u);
    v6 = v21;
    if ( v21 )
    {
      CMPEG2ProgramController::CMPEG2ProgramController(
        v21,
        *v2,
        this,
        *v17,
        *((struct CMPEG2PushClock **)this + 35),
        a2,
        &v40);
      v5 = v40;
      *(_QWORD *)v6 = &CMPEG2PushProgramController::`vftable';
      *((_DWORD *)v6 + 45) = 1;
      goto LABEL_43;
    }
    v6 = 0;
  }
  else
  {
    v22 = (CMPEG2ProgramController *)operator new(0xD0u);
    if ( !v22 )
    {
LABEL_49:
      if ( v5 >= 0 )
        v5 = -2147024882;
      v6 = 0;
      CallStackScopeTrace::CallStackScopeTrace(
        (CallStackScopeTrace *)&Data,
        "CMPEG2Demultiplexer::LoadMpeg2Program_",
        1463);
      if ( !byte_1800EACCB )
        goto LABEL_54;
      v27 = 23;
      goto LABEL_53;
    }
    v23 = CMPEG2ProgramController::CMPEG2ProgramController(
            v22,
            *v2,
            this,
            *v17,
            *((struct CMPEG2PushClock **)this + 35),
            a2,
            &v40);
    v5 = v40;
    v6 = v23;
  }
  if ( !v6 )
    goto LABEL_49;
LABEL_43:
  if ( v5 < 0 )
  {
    (*(void (__fastcall **)(CMPEG2ProgramController *, __int64))(*(_QWORD *)v6 + 40LL))(v6, 1);
    goto LABEL_49;
  }
  v5 = CMPEG2Controller::Reset(v6);
  if ( v5 < 0 )
  {
    (*(void (__fastcall **)(CMPEG2ProgramController *, __int64))(*(_QWORD *)v6 + 40LL))(v6, 1);
    v6 = 0;
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)&Data,
      "CMPEG2Demultiplexer::LoadMpeg2Program_",
      1457);
    if ( !byte_1800EACCB )
    {
LABEL_54:
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&Data);
      goto LABEL_55;
    }
    v27 = 22;
LABEL_53:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 17), v27, &WPP_a94830b6bd5f3023efd6e0bdea57da03_Traceguids, this, v5);
    goto LABEL_54;
  }
  v24 = *((_QWORD *)this + 35);
  *((_QWORD *)this + 43) = v6;
  *(_QWORD *)(v24 + 640) = *((_QWORD *)v6 + 17);
  v25 = *v17;
  v26 = StatsEnabled(L"SOFTWARE\\Microsoft\\MPEG2Demultiplexer\\Program");
  CMpeg2Stats::Initialize(v25, v26, a2);
LABEL_55:
  if ( v5 >= 0 )
    return (unsigned int)v5;
  if ( v6 )
    (*(void (__fastcall **)(CMPEG2ProgramController *, __int64))(*(_QWORD *)v6 + 40LL))(v6, 1);
LABEL_58:
  v28 = (CMPEG2PushClock *)*((_QWORD *)this + 35);
  if ( v28 )
    CMPEG2PushClock::`scalar deleting destructor'(v28, v18);
  v29 = *v2;
  *((_QWORD *)this + 35) = 0;
  if ( v29 )
  {
    RegCloseKey(v29);
    *v2 = 0;
  }
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&Data, "CMPEG2Demultiplexer::LoadMpeg2Program_", 1473);
  if ( byte_1800EACCB )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 17), 24, &WPP_a94830b6bd5f3023efd6e0bdea57da03_Traceguids, this, v5);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&Data);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18004fa44  mov     [rsp-38h+arg_8], rbx
0x18004fa49  push    rbp
0x18004fa4a  push    rsi
0x18004fa4b  push    rdi
0x18004fa4c  push    r12
0x18004fa4e  push    r13
0x18004fa50  push    r14
0x18004fa52  push    r15
0x18004fa54  mov     rbp, rsp
0x18004fa57  sub     rsp, 80h
0x18004fa5e  xor     r13d, r13d
0x18004fa61  lea     r15, [rcx+110h]
0x18004fa68  lea     rax, [rbp+dwDisposition]
0x18004fa6c  mov     [rbp+arg_10], r13d
0x18004fa70  mov     [rsp+80h+lpdwDisposition], rax; lpdwDisposition
0x18004fa75  mov     r12d, edx
0x18004fa78  mov     [rsp+80h+phkResult], r15; phkResult
0x18004fa7d  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\MPEG2Demultiplexer"...
0x18004fa84  mov     [rsp+80h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18004fa89  mov     r14, rcx
0x18004fa8c  mov     [rsp+80h+samDesired], 2001Fh; samDesired
0x18004fa94  xor     r9d, r9d; lpClass
0x18004fa97  xor     r8d, r8d; Reserved
0x18004fa9a  mov     [rsp+80h+dwOptions], r13d; dwOptions
0x18004fa9f  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18004faa6  mov     [rbp+dwDisposition], r13d
0x18004faaa  mov     edi, r13d
0x18004faad  mov     [rbp+arg_18], r13d
0x18004fab1  mov     dword ptr [rbp+var_10], r13d
0x18004fab5  mov     esi, r13d
0x18004fab8  mov     dword ptr [rbp+var_14], r13d
0x18004fabc  mov     dword ptr [rbp+var_18], r13d
0x18004fac0  mov     dword ptr [rbp+var_1C], r13d
0x18004fac4  mov     dword ptr [rbp+var_20], r13d
0x18004fac8  call    cs:__imp_RegCreateKeyExW
0x18004facf  nop     dword ptr [rax+rax+00h]
0x18004fad4  mov     ebx, eax
0x18004fad6  test    eax, eax
0x18004fad8  jz      short loc_18004FB2A
0x18004fada  mov     r8d, 53Ch; int
0x18004fae0  mov     [r15], r13
0x18004fae3  lea     rdx, aCmpeg2demultip_23; "CMPEG2Demultiplexer::LoadMpeg2Program_"
0x18004faea  lea     rcx, [rbp+Data]; this
0x18004faee  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004faf3  cmp     cs:byte_1800EACCB, 1
0x18004fafa  jb      short loc_18004FB21
0x18004fafc  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fb03  lea     edx, [r13+15h]
0x18004fb07  mov     r9, r14
0x18004fb0a  mov     [rsp+80h+dwOptions], ebx
0x18004fb0e  lea     r8, WPP_a94830b6bd5f3023efd6e0bdea57da03_Traceguids
0x18004fb15  mov     rcx, [rcx+88h]
0x18004fb1c  call    WPP_SF_qD
0x18004fb21  lea     rcx, [rbp+Data]; this
0x18004fb25  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004fb2a  mov     rbx, [r15]
0x18004fb2d  mov     eax, 4
0x18004fb32  mov     [rbp+Data], r13d
0x18004fb36  mov     [rbp+arg_18], 1
0x18004fb3d  test    rbx, rbx
0x18004fb40  jz      short loc_18004FBBA
0x18004fb42  mov     [rbp+cbData], eax
0x18004fb45  lea     r9, [rbp+Type]; lpType
0x18004fb49  mov     [rbp+Type], eax
0x18004fb4c  lea     rdx, aClock; "Clock"
0x18004fb53  lea     rax, [rbp+cbData]
0x18004fb57  xor     r8d, r8d; lpReserved
0x18004fb5a  mov     qword ptr [rsp+80h+samDesired], rax; lpcbData
0x18004fb5f  mov     rcx, rbx; hKey
0x18004fb62  lea     rax, [rbp+Data]
0x18004fb66  mov     qword ptr [rsp+80h+dwOptions], rax; lpData
0x18004fb6b  call    cs:__imp_RegQueryValueExW
0x18004fb72  nop     dword ptr [rax+rax+00h]
0x18004fb77  test    eax, eax
0x18004fb79  jnz     short loc_18004FB83
0x18004fb7b  mov     eax, [rbp+Data]
0x18004fb7e  mov     [rbp+arg_18], eax
0x18004fb81  jmp     short loc_18004FBB3
0x18004fb83  mov     r9d, 4; dwType
0x18004fb89  lea     rax, [rbp+arg_18]
0x18004fb8d  mov     [rsp+80h+samDesired], r9d; cbData
0x18004fb92  lea     rdx, aClock; "Clock"
0x18004fb99  xor     r8d, r8d; Reserved
0x18004fb9c  mov     qword ptr [rsp+80h+dwOptions], rax; lpData
0x18004fba1  mov     rcx, rbx; hKey
0x18004fba4  call    cs:__imp_RegSetValueExW
0x18004fbab  nop     dword ptr [rax+rax+00h]
0x18004fbb0  mov     eax, [rbp+arg_18]
0x18004fbb3  test    eax, eax
0x18004fbb5  mov     eax, r13d
0x18004fbb8  jz      short loc_18004FBBF
0x18004fbba  mov     eax, 1
0x18004fbbf  mov     rbx, [r15]
0x18004fbc2  mov     [r14+120h], eax
0x18004fbc9  mov     [rbp+Data], r13d
0x18004fbcd  mov     dword ptr [rbp+var_10], 7D0h
0x18004fbd4  test    rbx, rbx
0x18004fbd7  jz      short loc_18004FC4C
0x18004fbd9  mov     eax, 4
0x18004fbde  lea     r9, [rbp+cbData]; lpType
0x18004fbe2  mov     [rbp+Type], eax
0x18004fbe5  lea     rdx, aClocksubordina_0; "ClockSubordinateMinSamplingWindowMillis"
0x18004fbec  mov     [rbp+cbData], eax
0x18004fbef  xor     r8d, r8d; lpReserved
0x18004fbf2  lea     rax, [rbp+Type]
0x18004fbf6  mov     rcx, rbx; hKey
0x18004fbf9  mov     qword ptr [rsp+80h+samDesired], rax; lpcbData
0x18004fbfe  lea     rax, [rbp+Data]
0x18004fc02  mov     qword ptr [rsp+80h+dwOptions], rax; lpData
0x18004fc07  call    cs:__imp_RegQueryValueExW
0x18004fc0e  nop     dword ptr [rax+rax+00h]
0x18004fc13  test    eax, eax
0x18004fc15  jnz     short loc_18004FC1F
0x18004fc17  mov     eax, [rbp+Data]
0x18004fc1a  mov     dword ptr [rbp+var_10], eax
0x18004fc1d  jmp     short loc_18004FC4C
0x18004fc1f  mov     r9d, 4; dwType
0x18004fc25  lea     rax, [rbp+var_10]
0x18004fc29  mov     [rsp+80h+samDesired], r9d; cbData
0x18004fc2e  lea     rdx, aClocksubordina_0; "ClockSubordinateMinSamplingWindowMillis"
0x18004fc35  xor     r8d, r8d; Reserved
0x18004fc38  mov     qword ptr [rsp+80h+dwOptions], rax; lpData
0x18004fc3d  mov     rcx, rbx; hKey
0x18004fc40  call    cs:__imp_RegSetValueExW
0x18004fc47  nop     dword ptr [rax+rax+00h]
0x18004fc4c  mov     rbx, [r15]
0x18004fc4f  mov     [rbp+Data], r13d
0x18004fc53  mov     dword ptr [rbp+var_14], 3A980h
0x18004fc5a  test    rbx, rbx
0x18004fc5d  jz      short loc_18004FCD2
0x18004fc5f  mov     eax, 4
0x18004fc64  lea     r9, [rbp+cbData]; lpType
0x18004fc68  mov     [rbp+Type], eax
0x18004fc6b  lea     rdx, aClocksubordina; "ClockSubordinateHistoryMillis"
0x18004fc72  mov     [rbp+cbData], eax
0x18004fc75  xor     r8d, r8d; lpReserved
0x18004fc78  lea     rax, [rbp+Type]
0x18004fc7c  mov     rcx, rbx; hKey
0x18004fc7f  mov     qword ptr [rsp+80h+samDesired], rax; lpcbData
0x18004fc84  lea     rax, [rbp+Data]
0x18004fc88  mov     qword ptr [rsp+80h+dwOptions], rax; lpData
0x18004fc8d  call    cs:__imp_RegQueryValueExW
0x18004fc94  nop     dword ptr [rax+rax+00h]
0x18004fc99  test    eax, eax
0x18004fc9b  jnz     short loc_18004FCA5
0x18004fc9d  mov     eax, [rbp+Data]
0x18004fca0  mov     dword ptr [rbp+var_14], eax
0x18004fca3  jmp     short loc_18004FCD2
0x18004fca5  mov     r9d, 4; dwType
0x18004fcab  lea     rax, [rbp+var_14]
0x18004fcaf  mov     [rsp+80h+samDesired], r9d; cbData
0x18004fcb4  lea     rdx, aClocksubordina; "ClockSubordinateHistoryMillis"
0x18004fcbb  xor     r8d, r8d; Reserved
0x18004fcbe  mov     qword ptr [rsp+80h+dwOptions], rax; lpData
0x18004fcc3  mov     rcx, rbx; hKey
0x18004fcc6  call    cs:__imp_RegSetValueExW
0x18004fccd  nop     dword ptr [rax+rax+00h]
0x18004fcd2  mov     rbx, [r15]
0x18004fcd5  mov     [rbp+Data], r13d
0x18004fcd9  mov     dword ptr [rbp+var_18], 5Fh ; '_'
0x18004fce0  test    rbx, rbx
0x18004fce3  jz      short loc_18004FD58
0x18004fce5  mov     eax, 4
0x18004fcea  lea     r9, [rbp+cbData]; lpType
0x18004fcee  mov     [rbp+Type], eax
0x18004fcf1  lea     rdx, aClocksubordina_3; "ClockSubordinateMinSlavable"
0x18004fcf8  mov     [rbp+cbData], eax
0x18004fcfb  xor     r8d, r8d; lpReserved
0x18004fcfe  lea     rax, [rbp+Type]
0x18004fd02  mov     rcx, rbx; hKey
0x18004fd05  mov     qword ptr [rsp+80h+samDesired], rax; lpcbData
0x18004fd0a  lea     rax, [rbp+Data]
0x18004fd0e  mov     qword ptr [rsp+80h+dwOptions], rax; lpData
0x18004fd13  call    cs:__imp_RegQueryValueExW
0x18004fd1a  nop     dword ptr [rax+rax+00h]
0x18004fd1f  test    eax, eax
0x18004fd21  jnz     short loc_18004FD2B
0x18004fd23  mov     eax, [rbp+Data]
0x18004fd26  mov     dword ptr [rbp+var_18], eax
0x18004fd29  jmp     short loc_18004FD58
0x18004fd2b  mov     r9d, 4; dwType
0x18004fd31  lea     rax, [rbp+var_18]
0x18004fd35  mov     [rsp+80h+samDesired], r9d; cbData
0x18004fd3a  lea     rdx, aClocksubordina_3; "ClockSubordinateMinSlavable"
0x18004fd41  xor     r8d, r8d; Reserved
0x18004fd44  mov     qword ptr [rsp+80h+dwOptions], rax; lpData
0x18004fd49  mov     rcx, rbx; hKey
0x18004fd4c  call    cs:__imp_RegSetValueExW
0x18004fd53  nop     dword ptr [rax+rax+00h]
0x18004fd58  mov     rbx, [r15]
0x18004fd5b  mov     [rbp+Data], r13d
0x18004fd5f  mov     dword ptr [rbp+var_1C], 69h ; 'i'
0x18004fd66  test    rbx, rbx
0x18004fd69  jz      short loc_18004FDDE
0x18004fd6b  mov     eax, 4
0x18004fd70  lea     r9, [rbp+cbData]; lpType
0x18004fd74  mov     [rbp+Type], eax
0x18004fd77  lea     rdx, aClocksubordina_1; "ClockSubordinateMaxSlavable"
0x18004fd7e  mov     [rbp+cbData], eax
0x18004fd81  xor     r8d, r8d; lpReserved
0x18004fd84  lea     rax, [rbp+Type]
0x18004fd88  mov     rcx, rbx; hKey
0x18004fd8b  mov     qword ptr [rsp+80h+samDesired], rax; lpcbData
0x18004fd90  lea     rax, [rbp+Data]
0x18004fd94  mov     qword ptr [rsp+80h+dwOptions], rax; lpData
0x18004fd99  call    cs:__imp_RegQueryValueExW
0x18004fda0  nop     dword ptr [rax+rax+00h]
0x18004fda5  test    eax, eax
0x18004fda7  jnz     short loc_18004FDB1
0x18004fda9  mov     eax, [rbp+Data]
0x18004fdac  mov     dword ptr [rbp+var_1C], eax
0x18004fdaf  jmp     short loc_18004FDDE
0x18004fdb1  mov     r9d, 4; dwType
0x18004fdb7  lea     rax, [rbp+var_1C]
0x18004fdbb  mov     [rsp+80h+samDesired], r9d; cbData
0x18004fdc0  lea     rdx, aClocksubordina_1; "ClockSubordinateMaxSlavable"
0x18004fdc7  xor     r8d, r8d; Reserved
0x18004fdca  mov     qword ptr [rsp+80h+dwOptions], rax; lpData
0x18004fdcf  mov     rcx, rbx; hKey
0x18004fdd2  call    cs:__imp_RegSetValueExW
0x18004fdd9  nop     dword ptr [rax+rax+00h]
0x18004fdde  mov     rbx, [r15]
0x18004fde1  mov     [rbp+Data], r13d
0x18004fde5  mov     dword ptr [rbp+var_20], 3Ch ; '<'
0x18004fdec  test    rbx, rbx
0x18004fdef  jz      short loc_18004FE64
0x18004fdf1  mov     eax, 4
0x18004fdf6  lea     r9, [rbp+cbData]; lpType
0x18004fdfa  mov     [rbp+Type], eax
0x18004fdfd  lea     rdx, aShiftmaxglitch; "ShiftMaxGlitchesPerHour"
0x18004fe04  mov     [rbp+cbData], eax
0x18004fe07  xor     r8d, r8d; lpReserved
0x18004fe0a  lea     rax, [rbp+Type]
0x18004fe0e  mov     rcx, rbx; hKey
0x18004fe11  mov     qword ptr [rsp+80h+samDesired], rax; lpcbData
0x18004fe16  lea     rax, [rbp+Data]
0x18004fe1a  mov     qword ptr [rsp+80h+dwOptions], rax; lpData
0x18004fe1f  call    cs:__imp_RegQueryValueExW
0x18004fe26  nop     dword ptr [rax+rax+00h]
0x18004fe2b  test    eax, eax
0x18004fe2d  jnz     short loc_18004FE37
0x18004fe2f  mov     eax, [rbp+Data]
0x18004fe32  mov     dword ptr [rbp+var_20], eax
0x18004fe35  jmp     short loc_18004FE64
0x18004fe37  mov     r9d, 4; dwType
0x18004fe3d  lea     rax, [rbp+var_20]
0x18004fe41  mov     [rsp+80h+samDesired], r9d; cbData
0x18004fe46  lea     rdx, aShiftmaxglitch; "ShiftMaxGlitchesPerHour"
0x18004fe4d  xor     r8d, r8d; Reserved
0x18004fe50  mov     qword ptr [rsp+80h+dwOptions], rax; lpData
0x18004fe55  mov     rcx, rbx; hKey
0x18004fe58  call    cs:__imp_RegSetValueExW
0x18004fe5f  nop     dword ptr [rax+rax+00h]
0x18004fe64  mov     ecx, 2D0h; Size
0x18004fe69  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004fe6e  lea     rbx, [r14+108h]
0x18004fe75  mov     rcx, rax; this
0x18004fe78  test    rax, rax
0x18004fe7b  jz      short loc_18004FEC5
0x18004fe7d  mov     r9, [rbx]; struct CMpeg2Stats *
0x18004fe80  lea     rax, [rbp+arg_10]
0x18004fe84  mov     r8, [r15]; HKEY
0x18004fe87  mov     edx, [r14+120h]; int
0x18004fe8e  mov     [rsp+80h+var_30], rax; int *
0x18004fe93  mov     eax, dword ptr [rbp+var_20]
0x18004fe96  mov     [rsp+80h+var_38], eax; unsigned int
0x18004fe9a  mov     eax, dword ptr [rbp+var_1C]
0x18004fe9d  mov     dword ptr [rsp+80h+lpdwDisposition], eax; unsigned int
0x18004fea1  mov     eax, dword ptr [rbp+var_18]
0x18004fea4  mov     dword ptr [rsp+80h+phkResult], eax; unsigned int
0x18004fea8  mov     eax, dword ptr [rbp+var_14]
0x18004feab  mov     dword ptr [rsp+80h+lpSecurityAttributes], eax; unsigned int
0x18004feaf  mov     eax, dword ptr [rbp+var_10]
0x18004feb2  mov     [rsp+80h+samDesired], eax; unsigned int
0x18004feb6  mov     qword ptr [rsp+80h+dwOptions], r14; struct CMPEG2Demultiplexer *
0x18004febb  call    ??0CMPEG2PushClock@@QEAA@HPEAUHKEY__@@PEAVCMpeg2Stats@@PEAVCMPEG2Demultiplexer@@KKKKKPEAJ@Z; CMPEG2PushClock::CMPEG2PushClock(int,HKEY__ *,CMpeg2Stats *,CMPEG2Demultiplexer *,ulong,ulong,ulong,ulong,ulong,long *)
0x18004fec0  mov     edi, [rbp+arg_10]
0x18004fec3  jmp     short loc_18004FEC8
0x18004fec5  mov     rax, r13
0x18004fec8  mov     [r14+118h], rax
0x18004fecf  test    rax, rax
0x18004fed2  jz      loc_180050088
0x18004fed8  test    edi, edi
0x18004feda  js      loc_1800500A9
0x18004fee0  mov     ecx, 0D0h; Size
0x18004fee5  cmp     [r14+128h], r13d
0x18004feec  jz      short loc_18004FF44
0x18004feee  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004fef3  mov     rsi, rax
0x18004fef6  test    rax, rax
0x18004fef9  jz      short loc_18004FF3F
0x18004fefb  mov     r9, [rbx]; struct CMpeg2Stats *
0x18004fefe  lea     rax, [rbp+arg_10]
0x18004ff02  mov     rdx, [r15]; HKEY
0x18004ff05  mov     r8, r14; struct CMPEG2Demultiplexer *
0x18004ff08  mov     [rsp+80h+lpSecurityAttributes], rax; int *
0x18004ff0d  mov     rcx, rsi; this
0x18004ff10  mov     rax, [r14+118h]
0x18004ff17  mov     [rsp+80h+samDesired], r12d; unsigned int
0x18004ff1c  mov     qword ptr [rsp+80h+dwOptions], rax; struct CMPEG2PushClock *
  ... truncated ...
```
