# CHangReport::_AddWerDumpsAndRegisteredFiles(void)

- ea: `0x1400225cc`
- end: `0x140022b50`
- name: `?_AddWerDumpsAndRegisteredFiles@CHangReport@@IEAAJXZ`
- size: `1412`
- prototype: `__int64 __fastcall(CHangReport *__hidden this)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14002840c`
- `0x140029760`

## callees

- `0x140002490`
- `0x1400030f8`
- `0x14000420c`
- `0x140004280`
- `0x14000b50c`
- `0x140014ee4`
- `0x140014f14`
- `0x14001b1b4`
- `0x14001ffa4`
- `0x140020118`
- `0x140021b9c`
- `0x1400221f4`
- `0x1400225cc`
- `0x14003444c`
- `0x14005f510`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x140022828`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x140022992`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x140022828`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x140022992`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x140022937`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x140022937`
- `wer!WerpAddAppCompatData` at `0x140022ab7`
- `wer!WerpAddAppCompatData` at `0x140022ab7`
- `DiagnosticDataSettings!TelGetWerTelemetryMode` at `0x14002273d`
- `DiagnosticDataSettings!TelGetWerTelemetryMode` at `0x14002273d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CHangReport::_AddWerDumpsAndRegisteredFiles(CHangReport *this)
{
  int v2; // r13d
  DWORD v3; // r9d
  CUserModeHangReport *v4; // rcx
  __int64 v5; // rdx
  int Settings; // eax
  enum _WER_DUMP_TYPE v7; // r15d
  __int64 v8; // rax
  unsigned int **v9; // r12
  struct HPSS__ *SnapshotForProcess; // r14
  int v11; // eax
  int v12; // r9d
  int v13; // eax
  char *v14; // r15
  enum _WER_DUMP_TYPE v15; // r12d
  void *v16; // rcx
  DWORD ProcessId; // eax
  struct HPSS__ *v18; // r14
  int v19; // eax
  int v20; // ecx
  unsigned __int64 v21; // r13
  unsigned int v22; // eax
  int v23; // eax
  bool v24; // cf
  const wchar_t *v25; // rax
  int v26; // eax
  enum _WER_DUMP_TYPE v28; // [rsp+40h] [rbp-C0h]
  enum _WER_DUMP_TYPE v29; // [rsp+40h] [rbp-C0h]
  unsigned int Buffer; // [rsp+44h] [rbp-BCh] BYREF
  int v31; // [rsp+48h] [rbp-B8h]
  CProcessInformation **v32; // [rsp+50h] [rbp-B0h]
  __int64 v33; // [rsp+58h] [rbp-A8h]
  _BYTE v34[1672]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v35; // [rsp+6E8h] [rbp+5E8h]
  __int64 v36; // [rsp+740h] [rbp+640h]
  char v37; // [rsp+1378h] [rbp+1278h]
  int v38; // [rsp+137Ch] [rbp+127Ch]
  wchar_t *String; // [rsp+1380h] [rbp+1280h]
  int v40; // [rsp+13D8h] [rbp+12D8h]
  int v41; // [rsp+1448h] [rbp+1348h]
  __int64 v42; // [rsp+144Ch] [rbp+134Ch]
  __int16 v43; // [rsp+1454h] [rbp+1354h]
  char v44; // [rsp+1456h] [rbp+1356h]
  __int64 v45; // [rsp+1458h] [rbp+1358h]
  int v46; // [rsp+1460h] [rbp+1360h]
  wchar_t v47[264]; // [rsp+1470h] [rbp+1370h] BYREF

  memset_0(v47, 0, 0x208u);
  v2 = 0;
  Buffer = 0;
  `eh vector constructor iterator'(
    v34,
    0x68u,
    0x31u,
    (void (*)(void *))CRegSetting::CRegSetting,
    (void (*)(void *))CRegSetting::~CRegSetting);
  v41 = 1;
  v42 = 1;
  v43 = 0;
  v44 = 1;
  v45 = 5;
  v46 = 0;
  if ( *((_DWORD *)this + 6225) )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      goto LABEL_72;
    }
    v5 = 94;
    goto LABEL_5;
  }
  *((_DWORD *)this + 6225) = 1;
  if ( *((_DWORD *)this + 20) )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      goto LABEL_72;
    }
    v5 = 95;
LABEL_5:
    WPP_SF_(*((_QWORD *)v4 + 2), v5, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids);
    goto LABEL_72;
  }
  Settings = CSettings::LoadSettings((CSettings *)v34, 0, 0, v3);
  v7 = WerDumpTypeMiniDump;
  if ( Settings < 0
    && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      96,
      WPP_6c7034e0252a3228ea586abc03935af9_Traceguids,
      (unsigned int)Settings);
  }
  if ( (unsigned int)TelGetWerTelemetryMode() == 3 )
    goto LABEL_20;
  v8 = v36;
  if ( v34[1664] )
    v8 = v35;
  if ( v8 )
  {
LABEL_20:
    v9 = (unsigned int **)((char *)this + 23904);
    v32 = (CProcessInformation **)((char *)this + 23904);
  }
  else
  {
    v9 = (unsigned int **)((char *)this + 23904);
    v32 = (CProcessInformation **)((char *)this + 23904);
    if ( (unsigned __int64)(*(_QWORD *)(*((_QWORD *)this + 2988) + 1856LL) - 1LL) > 0x40000766F41A4LL )
    {
      v7 = WerDumpTypeTriageDump;
      *((_DWORD *)this + 6222) = 1180068;
      v32 = (CProcessInformation **)((char *)this + 23904);
      goto LABEL_22;
    }
  }
  *((_DWORD *)this + 6222) = 393505;
LABEL_22:
  v28 = v7;
  if ( *((_DWORD *)this + 6226) )
  {
    SnapshotForProcess = 0;
  }
  else
  {
    SnapshotForProcess = CHangReport::FindSnapshotForProcess(this, **v9);
    if ( SnapshotForProcess )
    {
LABEL_27:
      if ( !v37 )
        goto LABEL_32;
      if ( !v38 )
      {
        v11 = *(_DWORD *)String;
        goto LABEL_33;
      }
      if ( v38 == 1 )
        v11 = wcstol(String, 0, 10);
      else
LABEL_32:
        v11 = v40;
LABEL_33:
      v12 = 0;
      if ( !v11 )
        goto LABEL_35;
      goto LABEL_34;
    }
  }
  if ( *((_QWORD *)this + 3096) == -1 || *((_QWORD *)this + 3096) == 0 )
    goto LABEL_27;
LABEL_34:
  v12 = 1;
LABEL_35:
  v13 = CHangReport::_AddWerDumpForProcess(
          *((void **)this + 3055),
          *((void **)this + 3090),
          **v9,
          (*v9)[1],
          v7,
          v12 | (SnapshotForProcess != 0 ? -536870912 : 0x20000000),
          (struct _EXCEPTION_POINTERS *)this + 9,
          SnapshotForProcess);
  if ( v13 < 0
    && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      97,
      WPP_6c7034e0252a3228ea586abc03935af9_Traceguids,
      (unsigned int)v13);
  }
  v14 = (char *)this + 24432;
  v15 = v28;
  do
  {
    v33 = v2;
    v16 = (void *)*((_QWORD *)this + v2 + 3096);
    if ( (unsigned __int64)v16 + 1 <= 1 )
      break;
    if ( (int)ExtractThreadIdFromPebHandle(v16, &Buffer, 0) < 0 )
    {
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids);
      }
      Buffer = 0;
    }
    ProcessId = GetProcessId(*((HANDLE *)this + v2 + 3096));
    v29 = ProcessId;
    if ( *((_DWORD *)this + 6226) )
    {
      v18 = 0;
LABEL_57:
      v20 = 1;
      goto LABEL_58;
    }
    v18 = CHangReport::FindSnapshotForProcess(this, ProcessId);
    if ( !v18 )
      goto LABEL_57;
    if ( !v37 )
      goto LABEL_53;
    if ( !v38 )
    {
      v19 = *(_DWORD *)String;
      goto LABEL_54;
    }
    if ( v38 == 1 )
      v19 = wcstol(String, 0, 10);
    else
LABEL_53:
      v19 = v40;
LABEL_54:
    if ( v19 )
      goto LABEL_57;
    v20 = 0;
LABEL_58:
    v14 = (char *)this + 24432;
    v31 = v2 + 1;
    v21 = v2 + 1;
    v22 = v20 | (v18 != 0 ? -536870910 : 536870914) | 4;
    if ( (*(_DWORD *)(*((_QWORD *)this + 3054) + 1440LL) & 0x100000) == 0 )
      v22 = v20 | (v18 != 0 ? -536870910 : 536870914);
    v23 = CHangReport::_AddWerDumpForProcess(
            *((void **)this + 3055),
            *((void **)this + v33 + 3096),
            v29,
            Buffer,
            v15,
            v22,
            (struct _EXCEPTION_POINTERS *)this + v21 + 9,
            v18);
    if ( v23 < 0
      && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        99,
        WPP_6c7034e0252a3228ea586abc03935af9_Traceguids,
        (unsigned int)v23);
    }
    v24 = v21 < 0xF;
    v2 = v31;
  }
  while ( v24 );
  if ( (*(_BYTE *)(*(_QWORD *)v14 + 1440LL) & 0x10) == 0 )
  {
    v25 = CProcessInformation::AppFileName(*v32);
    StringCchCopyW(v47, 0x104u, v25);
    v26 = WerpAddAppCompatData(*((_QWORD *)this + 3055), v47, 0);
    if ( v26 < 0
      && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        100,
        WPP_6c7034e0252a3228ea586abc03935af9_Traceguids,
        (unsigned int)v26);
    }
  }
  if ( (*(_BYTE *)(*(_QWORD *)v14 + 1440LL) & 2) != 0 )
    CHangReport::_AddOSVersion(this);
LABEL_72:
  `eh vector destructor iterator'(v34, 0x68u, 0x31u, (void (*)(void *))CRegSetting::~CRegSetting);
  return 0;
}

```

## disassembly

```asm
0x1400225cc  mov     [rsp-8+arg_8], rbx
0x1400225d1  mov     [rsp-8+arg_10], rdi
0x1400225d6  push    rbp
0x1400225d7  push    r12
0x1400225d9  push    r13
0x1400225db  push    r14
0x1400225dd  push    r15
0x1400225df  lea     rbp, [rsp-1590h]
0x1400225e7  mov     eax, 1690h
0x1400225ec  call    _alloca_probe
0x1400225f1  sub     rsp, rax
0x1400225f4  mov     rax, cs:__security_cookie
0x1400225fb  xor     rax, rsp
0x1400225fe  mov     [rbp+15B0h+var_30], rax
0x140022605  mov     rbx, rcx
0x140022608  xor     edx, edx; Val
0x14002260a  mov     r8d, 208h; Size
0x140022610  lea     rcx, [rbp+15B0h+var_240]; void *
0x140022617  call    memset_0
0x14002261c  xor     r13d, r13d
0x14002261f  mov     [rsp+16B0h+Buffer], r13d
0x140022624  lea     rax, ??1CRegSetting@@QEAA@XZ; CRegSetting::~CRegSetting(void)
0x14002262b  mov     qword ptr [rsp+16B0h+var_1690], rax; void (*)(void *)
0x140022630  lea     r9, ??0CRegSetting@@QEAA@XZ; void (*)(void *)
0x140022637  lea     edx, [r13+68h]; unsigned __int64
0x14002263b  lea     r8d, [r13+31h]; unsigned __int64
0x14002263f  lea     rcx, [rsp+16B0h+var_1650]; void *
0x140022644  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x140022649  lea     r14d, [r13+1]
0x14002264d  mov     [rbp+15B0h+var_268], r14d
0x140022654  mov     [rbp+15B0h+var_264], r14
0x14002265b  mov     [rbp+15B0h+var_25C], r13w
0x140022663  mov     [rbp+15B0h+var_25A], r14b
0x14002266a  mov     [rbp+15B0h+var_258], 5
0x140022675  mov     [rbp+15B0h+var_250], r13d
0x14002267c  cmp     [rbx+6144h], r13d
0x140022683  jz      short loc_1400226BF
0x140022685  lea     rdi, WPP_GLOBAL_Control
0x14002268c  mov     rcx, cs:WPP_GLOBAL_Control
0x140022693  cmp     rcx, rdi
0x140022696  jz      loc_140022B06
0x14002269c  test    byte ptr [rcx+1Ch], 4
0x1400226a0  jz      loc_140022B06
0x1400226a6  lea     edx, [r13+5Eh]
0x1400226aa  lea     r8, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids
0x1400226b1  mov     rcx, [rcx+10h]
0x1400226b5  call    WPP_SF_
0x1400226ba  jmp     loc_140022B06
0x1400226bf  mov     [rbx+6144h], r14d
0x1400226c6  cmp     [rbx+50h], r13d
0x1400226ca  jz      short loc_1400226F4
0x1400226cc  lea     rdi, WPP_GLOBAL_Control
0x1400226d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400226da  cmp     rcx, rdi
0x1400226dd  jz      loc_140022B06
0x1400226e3  test    byte ptr [rcx+1Ch], 4
0x1400226e7  jz      loc_140022B06
0x1400226ed  mov     edx, 5Fh ; '_'
0x1400226f2  jmp     short loc_1400226AA
0x1400226f4  xor     r8d, r8d; wchar_t *
0x1400226f7  xor     edx, edx; wchar_t *
0x1400226f9  lea     rcx, [rsp+16B0h+var_1650]; this
0x1400226fe  call    ?LoadSettings@CSettings@@QEAAJPEB_W0W4_WER_CONSENT@@@Z; CSettings::LoadSettings(wchar_t const *,wchar_t const *,_WER_CONSENT)
0x140022703  mov     r15d, 2
0x140022709  lea     rdi, WPP_GLOBAL_Control
0x140022710  test    eax, eax
0x140022712  jns     short loc_14002273D
0x140022714  mov     rcx, cs:WPP_GLOBAL_Control
0x14002271b  cmp     rcx, rdi
0x14002271e  jz      short loc_14002273D
0x140022720  test    [rcx+1Ch], r15b
0x140022724  jz      short loc_14002273D
0x140022726  lea     edx, [r15+5Eh]
0x14002272a  mov     r9d, eax
0x14002272d  lea     r8, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids
0x140022734  mov     rcx, [rcx+10h]
0x140022738  call    WPP_SF_d
0x14002273d  call    cs:__imp_TelGetWerTelemetryMode
0x140022744  nop     dword ptr [rax+rax+00h]
0x140022749  cmp     eax, 3
0x14002274c  jz      short loc_1400227A9
0x14002274e  mov     rax, [rbp+15B0h+var_F70]
0x140022755  cmp     [rbp+15B0h+var_FD0], r13b
0x14002275c  cmovnz  rax, [rbp+15B0h+var_FC8]
0x140022764  test    rax, rax
0x140022767  jnz     short loc_1400227A9
0x140022769  lea     r12, [rbx+5D60h]
0x140022770  mov     [rsp+16B0h+var_1660], r12
0x140022775  mov     rax, [r12]
0x140022779  mov     rcx, [rax+740h]
0x140022780  sub     rcx, r14
0x140022783  mov     rax, 40000766F41A4h
0x14002278d  cmp     rcx, rax
0x140022790  jbe     short loc_1400227B5
0x140022792  mov     r15d, 4
0x140022798  mov     dword ptr [rbx+6138h], 1201A4h
0x1400227a2  mov     [rsp+16B0h+var_1660], r12
0x1400227a7  jmp     short loc_1400227BF
0x1400227a9  lea     r12, [rbx+5D60h]
0x1400227b0  mov     [rsp+16B0h+var_1660], r12
0x1400227b5  mov     dword ptr [rbx+6138h], 60121h
0x1400227bf  mov     [rsp+16B0h+var_1670], r15d
0x1400227c4  cmp     [rbx+6148h], r13d
0x1400227cb  jnz     short loc_1400227E5
0x1400227cd  mov     rdx, [r12]
0x1400227d1  mov     edx, [rdx]; unsigned int
0x1400227d3  mov     rcx, rbx; this
0x1400227d6  call    ?FindSnapshotForProcess@CHangReport@@IEAAPEAUHPSS__@@K@Z; CHangReport::FindSnapshotForProcess(ulong)
0x1400227db  mov     r14, rax
0x1400227de  test    rax, rax
0x1400227e1  jnz     short loc_1400227F8
0x1400227e3  jmp     short loc_1400227E8
0x1400227e5  mov     r14, r13
0x1400227e8  mov     rax, [rbx+60C0h]
0x1400227ef  inc     rax
0x1400227f2  cmp     rax, 1
0x1400227f6  ja      short loc_140022843
0x1400227f8  cmp     [rbp+15B0h+var_338], r13b
0x1400227ff  jz      short loc_140022836
0x140022801  mov     eax, [rbp+15B0h+var_334]
0x140022807  test    eax, eax
0x140022809  jnz     short loc_140022816
0x14002280b  mov     rax, [rbp+15B0h+String]
0x140022812  mov     eax, [rax]
0x140022814  jmp     short loc_14002283C
0x140022816  cmp     eax, 1
0x140022819  jnz     short loc_140022836
0x14002281b  xor     edx, edx; EndPtr
0x14002281d  lea     r8d, [rax+9]; Radix
0x140022821  mov     rcx, [rbp+15B0h+String]; String
0x140022828  call    cs:__imp_wcstol
0x14002282f  nop     dword ptr [rax+rax+00h]
0x140022834  jmp     short loc_14002283C
0x140022836  mov     eax, [rbp+15B0h+var_2D8]
0x14002283c  test    eax, eax
0x14002283e  mov     r9d, r13d
0x140022841  jz      short loc_140022849
0x140022843  mov     r9d, 1
0x140022849  mov     r8, [r12]
0x14002284d  lea     rdx, [rbx+90h]
0x140022854  mov     rax, r14
0x140022857  neg     rax
0x14002285a  sbb     ecx, ecx
0x14002285c  and     ecx, 0C0000000h
0x140022862  add     ecx, 20000000h
0x140022868  or      ecx, r9d
0x14002286b  mov     [rsp+16B0h+var_1678], r14; struct HPSS__ *
0x140022870  mov     [rsp+16B0h+var_1680], rdx; struct _EXCEPTION_POINTERS *
0x140022875  mov     [rsp+16B0h+var_1688], ecx; unsigned int
0x140022879  mov     [rsp+16B0h+var_1690], r15d; enum _WER_DUMP_TYPE
0x14002287e  mov     r9d, [r8+4]; unsigned int
0x140022882  mov     r8d, [r8]; unsigned int
0x140022885  mov     rdx, [rbx+6090h]; void *
0x14002288c  mov     rcx, [rbx+5F78h]; void *
0x140022893  call    ?_AddWerDumpForProcess@CHangReport@@KAJPEAX0KKW4_WER_DUMP_TYPE@@KPEAU_EXCEPTION_POINTERS@@PEAUHPSS__@@@Z; CHangReport::_AddWerDumpForProcess(void *,void *,ulong,ulong,_WER_DUMP_TYPE,ulong,_EXCEPTION_POINTERS *,HPSS__ *)
0x140022898  test    eax, eax
0x14002289a  jns     short loc_1400228C6
0x14002289c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400228a3  cmp     rcx, rdi
0x1400228a6  jz      short loc_1400228C6
0x1400228a8  test    byte ptr [rcx+1Ch], 2
0x1400228ac  jz      short loc_1400228C6
0x1400228ae  mov     edx, 61h ; 'a'
0x1400228b3  mov     r9d, eax
0x1400228b6  lea     r8, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids
0x1400228bd  mov     rcx, [rcx+10h]
0x1400228c1  call    WPP_SF_d
0x1400228c6  lea     r15, [rbx+5F70h]
0x1400228cd  mov     r12d, [rsp+16B0h+var_1670]
0x1400228d2  movsxd  r14, r13d
0x1400228d5  mov     [rsp+16B0h+var_1658], r14
0x1400228da  mov     rcx, [rbx+r14*8+60C0h]; hProcess
0x1400228e2  lea     rax, [rcx+1]
0x1400228e6  cmp     rax, 1
0x1400228ea  jbe     loc_140022A78
0x1400228f0  xor     r8d, r8d; int
0x1400228f3  lea     rdx, [rsp+16B0h+Buffer]; lpBuffer
0x1400228f8  call    ?ExtractThreadIdFromPebHandle@@YAJPEAXPEAKH@Z; ExtractThreadIdFromPebHandle(void *,ulong *,int)
0x1400228fd  xor     r15d, r15d
0x140022900  test    eax, eax
0x140022902  jns     short loc_14002292F
0x140022904  mov     rcx, cs:WPP_GLOBAL_Control
0x14002290b  cmp     rcx, rdi
0x14002290e  jz      short loc_14002292A
0x140022910  test    byte ptr [rcx+1Ch], 2
0x140022914  jz      short loc_14002292A
0x140022916  lea     edx, [r15+62h]
0x14002291a  lea     r8, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids
0x140022921  mov     rcx, [rcx+10h]
0x140022925  call    WPP_SF_
0x14002292a  mov     [rsp+16B0h+Buffer], r15d
0x14002292f  mov     rcx, [rbx+r14*8+60C0h]; Process
0x140022937  call    cs:__imp_GetProcessId
0x14002293e  nop     dword ptr [rax+rax+00h]
0x140022943  mov     [rsp+16B0h+var_1670], eax
0x140022947  cmp     [rbx+6148h], r15d
0x14002294e  jnz     short loc_1400229AF
0x140022950  mov     edx, eax; unsigned int
0x140022952  mov     rcx, rbx; this
0x140022955  call    ?FindSnapshotForProcess@CHangReport@@IEAAPEAUHPSS__@@K@Z; CHangReport::FindSnapshotForProcess(ulong)
0x14002295a  mov     r14, rax
0x14002295d  test    rax, rax
0x140022960  jz      short loc_1400229B2
0x140022962  cmp     [rbp+15B0h+var_338], r15b
0x140022969  jz      short loc_1400229A0
0x14002296b  mov     eax, [rbp+15B0h+var_334]
0x140022971  test    eax, eax
0x140022973  jnz     short loc_140022980
0x140022975  mov     rcx, [rbp+15B0h+String]
0x14002297c  mov     eax, [rcx]
0x14002297e  jmp     short loc_1400229A6
0x140022980  cmp     eax, 1
0x140022983  jnz     short loc_1400229A0
0x140022985  xor     edx, edx; EndPtr
0x140022987  lea     r8d, [rax+9]; Radix
0x14002298b  mov     rcx, [rbp+15B0h+String]; String
0x140022992  call    cs:__imp_wcstol
0x140022999  nop     dword ptr [rax+rax+00h]
0x14002299e  jmp     short loc_1400229A6
0x1400229a0  mov     eax, [rbp+15B0h+var_2D8]
0x1400229a6  test    eax, eax
0x1400229a8  jnz     short loc_1400229B2
0x1400229aa  mov     ecx, r15d
0x1400229ad  jmp     short loc_1400229B7
0x1400229af  mov     r14, r15
0x1400229b2  mov     ecx, 1
0x1400229b7  mov     rax, r14
0x1400229ba  neg     rax
0x1400229bd  sbb     r8d, r8d
0x1400229c0  and     r8d, 0C0000000h
0x1400229c7  add     r8d, 20000002h
0x1400229ce  or      r8d, ecx
0x1400229d1  lea     r15, [rbx+5F70h]
0x1400229d8  inc     r13d
0x1400229db  mov     [rsp+16B0h+var_1668], r13d
0x1400229e0  movsxd  r13, r13d
0x1400229e3  lea     rdx, [r13+9]
0x1400229e7  shl     rdx, 4
0x1400229eb  add     rdx, rbx
0x1400229ee  mov     rax, [r15]
0x1400229f1  mov     ecx, [rax+5A0h]
0x1400229f7  mov     eax, r8d
0x1400229fa  or      eax, 4
0x1400229fd  bt      ecx, 14h
0x140022a01  cmovnb  eax, r8d
0x140022a05  mov     [rsp+16B0h+var_1678], r14; struct HPSS__ *
0x140022a0a  mov     [rsp+16B0h+var_1680], rdx; struct _EXCEPTION_POINTERS *
0x140022a0f  mov     [rsp+16B0h+var_1688], eax; unsigned int
0x140022a13  mov     [rsp+16B0h+var_1690], r12d; enum _WER_DUMP_TYPE
0x140022a18  mov     r9d, [rsp+16B0h+Buffer]; unsigned int
0x140022a1d  mov     r8d, [rsp+16B0h+var_1670]; unsigned int
0x140022a22  mov     rdx, [rsp+16B0h+var_1658]
0x140022a27  mov     rdx, [rbx+rdx*8+60C0h]; void *
0x140022a2f  mov     rcx, [rbx+5F78h]; void *
0x140022a36  call    ?_AddWerDumpForProcess@CHangReport@@KAJPEAX0KKW4_WER_DUMP_TYPE@@KPEAU_EXCEPTION_POINTERS@@PEAUHPSS__@@@Z; CHangReport::_AddWerDumpForProcess(void *,void *,ulong,ulong,_WER_DUMP_TYPE,ulong,_EXCEPTION_POINTERS *,HPSS__ *)
0x140022a3b  test    eax, eax
0x140022a3d  jns     short loc_140022A69
0x140022a3f  mov     rcx, cs:WPP_GLOBAL_Control
0x140022a46  cmp     rcx, rdi
0x140022a49  jz      short loc_140022A69
0x140022a4b  test    byte ptr [rcx+1Ch], 2
0x140022a4f  jz      short loc_140022A69
0x140022a51  mov     edx, 63h ; 'c'
0x140022a56  mov     r9d, eax
0x140022a59  lea     r8, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids
0x140022a60  mov     rcx, [rcx+10h]
0x140022a64  call    WPP_SF_d
0x140022a69  cmp     r13, 0Fh
0x140022a6d  mov     r13d, [rsp+16B0h+var_1668]
0x140022a72  jb      loc_1400228D2
0x140022a78  mov     rax, [r15]
0x140022a7b  test    byte ptr [rax+5A0h], 10h
0x140022a82  mov     r12, [rsp+16B0h+var_1660]
0x140022a87  jnz     short loc_140022AF1
0x140022a89  mov     rcx, [r12]; this
0x140022a8d  call    ?AppFileName@CProcessInformation@@AEAAPEB_WXZ; CProcessInformation::AppFileName(void)
0x140022a92  mov     r8, rax; wchar_t *
0x140022a95  mov     edx, 104h; unsigned __int64
0x140022a9a  lea     rcx, [rbp+15B0h+var_240]; wchar_t *
0x140022aa1  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x140022aa6  xor     r8d, r8d
0x140022aa9  lea     rdx, [rbp+15B0h+var_240]
0x140022ab0  mov     rcx, [rbx+5F78h]
0x140022ab7  call    cs:__imp_WerpAddAppCompatData
0x140022abe  nop     dword ptr [rax+rax+00h]
0x140022ac3  test    eax, eax
0x140022ac5  jns     short loc_140022AF1
0x140022ac7  mov     rcx, cs:WPP_GLOBAL_Control
0x140022ace  cmp     rcx, rdi
0x140022ad1  jz      short loc_140022AF1
0x140022ad3  test    byte ptr [rcx+1Ch], 2
0x140022ad7  jz      short loc_140022AF1
0x140022ad9  mov     edx, 64h ; 'd'
0x140022ade  mov     r9d, eax
0x140022ae1  lea     r8, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids
0x140022ae8  mov     rcx, [rcx+10h]
0x140022aec  call    WPP_SF_d
0x140022af1  mov     rax, [r15]
0x140022af4  test    byte ptr [rax+5A0h], 2
0x140022afb  jz      short loc_140022B06
  ... truncated ...
```
