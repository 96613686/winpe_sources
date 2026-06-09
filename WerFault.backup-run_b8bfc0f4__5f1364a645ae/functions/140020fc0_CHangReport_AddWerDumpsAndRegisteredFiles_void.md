# CHangReport::_AddWerDumpsAndRegisteredFiles(void)

- ea: `0x140020fc0`
- end: `0x140021525`
- name: `?_AddWerDumpsAndRegisteredFiles@CHangReport@@IEAAJXZ`
- size: `1381`
- prototype: `__int64 __fastcall(CHangReport *__hidden this)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140026a70`
- `0x140027d30`

## callees

- `0x140002470`
- `0x1400030a8`
- `0x1400041bc`
- `0x140004230`
- `0x14000b4cc`
- `0x14001444c`
- `0x140014474`
- `0x14001a1d4`
- `0x14001e9a4`
- `0x14001eb14`
- `0x1400205c8`
- `0x140020c20`
- `0x140020fc0`
- `0x14003215c`
- `0x14005b770`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x140021216`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x140021374`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x140021216`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x140021374`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14002131f`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14002131f`
- `wer!WerpAddAppCompatData` at `0x140021493`
- `wer!WerpAddAppCompatData` at `0x140021493`
- `DiagnosticDataSettings!TelGetWerTelemetryMode` at `0x140021131`
- `DiagnosticDataSettings!TelGetWerTelemetryMode` at `0x140021131`

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
0x140020fc0  mov     [rsp-8+arg_8], rbx
0x140020fc5  mov     [rsp-8+arg_10], rdi
0x140020fca  push    rbp
0x140020fcb  push    r12
0x140020fcd  push    r13
0x140020fcf  push    r14
0x140020fd1  push    r15
0x140020fd3  lea     rbp, [rsp-1590h]
0x140020fdb  mov     eax, 1690h
0x140020fe0  call    _alloca_probe
0x140020fe5  sub     rsp, rax
0x140020fe8  mov     rax, cs:__security_cookie
0x140020fef  xor     rax, rsp
0x140020ff2  mov     [rbp+15B0h+var_30], rax
0x140020ff9  mov     rbx, rcx
0x140020ffc  xor     edx, edx; Val
0x140020ffe  mov     r8d, 208h; Size
0x140021004  lea     rcx, [rbp+15B0h+var_240]; void *
0x14002100b  call    memset_0
0x140021010  xor     r13d, r13d
0x140021013  mov     [rsp+16B0h+Buffer], r13d
0x140021018  lea     rax, ??1CRegSetting@@QEAA@XZ; CRegSetting::~CRegSetting(void)
0x14002101f  mov     qword ptr [rsp+16B0h+var_1690], rax; void (*)(void *)
0x140021024  lea     r9, ??0CRegSetting@@QEAA@XZ; void (*)(void *)
0x14002102b  lea     edx, [r13+68h]; unsigned __int64
0x14002102f  lea     r8d, [r13+31h]; unsigned __int64
0x140021033  lea     rcx, [rsp+16B0h+var_1650]; void *
0x140021038  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x14002103d  lea     r14d, [r13+1]
0x140021041  mov     [rbp+15B0h+var_268], r14d
0x140021048  mov     [rbp+15B0h+var_264], r14
0x14002104f  mov     [rbp+15B0h+var_25C], r13w
0x140021057  mov     [rbp+15B0h+var_25A], r14b
0x14002105e  mov     [rbp+15B0h+var_258], 5
0x140021069  mov     [rbp+15B0h+var_250], r13d
0x140021070  cmp     [rbx+6144h], r13d
0x140021077  jz      short loc_1400210B3
0x140021079  lea     rdi, WPP_GLOBAL_Control
0x140021080  mov     rcx, cs:WPP_GLOBAL_Control
0x140021087  cmp     rcx, rdi
0x14002108a  jz      loc_1400214DC
0x140021090  test    byte ptr [rcx+1Ch], 4
0x140021094  jz      loc_1400214DC
0x14002109a  lea     edx, [r13+5Eh]
0x14002109e  lea     r8, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids
0x1400210a5  mov     rcx, [rcx+10h]
0x1400210a9  call    WPP_SF_
0x1400210ae  jmp     loc_1400214DC
0x1400210b3  mov     [rbx+6144h], r14d
0x1400210ba  cmp     [rbx+50h], r13d
0x1400210be  jz      short loc_1400210E8
0x1400210c0  lea     rdi, WPP_GLOBAL_Control
0x1400210c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400210ce  cmp     rcx, rdi
0x1400210d1  jz      loc_1400214DC
0x1400210d7  test    byte ptr [rcx+1Ch], 4
0x1400210db  jz      loc_1400214DC
0x1400210e1  mov     edx, 5Fh ; '_'
0x1400210e6  jmp     short loc_14002109E
0x1400210e8  xor     r8d, r8d; wchar_t *
0x1400210eb  xor     edx, edx; wchar_t *
0x1400210ed  lea     rcx, [rsp+16B0h+var_1650]; this
0x1400210f2  call    ?LoadSettings@CSettings@@QEAAJPEB_W0W4_WER_CONSENT@@@Z; CSettings::LoadSettings(wchar_t const *,wchar_t const *,_WER_CONSENT)
0x1400210f7  mov     r15d, 2
0x1400210fd  lea     rdi, WPP_GLOBAL_Control
0x140021104  test    eax, eax
0x140021106  jns     short loc_140021131
0x140021108  mov     rcx, cs:WPP_GLOBAL_Control
0x14002110f  cmp     rcx, rdi
0x140021112  jz      short loc_140021131
0x140021114  test    [rcx+1Ch], r15b
0x140021118  jz      short loc_140021131
0x14002111a  lea     edx, [r15+5Eh]
0x14002111e  mov     r9d, eax
0x140021121  lea     r8, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids
0x140021128  mov     rcx, [rcx+10h]
0x14002112c  call    WPP_SF_d
0x140021131  call    cs:__imp_TelGetWerTelemetryMode
0x140021137  cmp     eax, 3
0x14002113a  jz      short loc_140021197
0x14002113c  mov     rax, [rbp+15B0h+var_F70]
0x140021143  cmp     [rbp+15B0h+var_FD0], r13b
0x14002114a  cmovnz  rax, [rbp+15B0h+var_FC8]
0x140021152  test    rax, rax
0x140021155  jnz     short loc_140021197
0x140021157  lea     r12, [rbx+5D60h]
0x14002115e  mov     [rsp+16B0h+var_1660], r12
0x140021163  mov     rax, [r12]
0x140021167  mov     rcx, [rax+740h]
0x14002116e  sub     rcx, r14
0x140021171  mov     rax, 40000766F41A4h
0x14002117b  cmp     rcx, rax
0x14002117e  jbe     short loc_1400211A3
0x140021180  mov     r15d, 4
0x140021186  mov     dword ptr [rbx+6138h], 1201A4h
0x140021190  mov     [rsp+16B0h+var_1660], r12
0x140021195  jmp     short loc_1400211AD
0x140021197  lea     r12, [rbx+5D60h]
0x14002119e  mov     [rsp+16B0h+var_1660], r12
0x1400211a3  mov     dword ptr [rbx+6138h], 60121h
0x1400211ad  mov     [rsp+16B0h+var_1670], r15d
0x1400211b2  cmp     [rbx+6148h], r13d
0x1400211b9  jnz     short loc_1400211D3
0x1400211bb  mov     rdx, [r12]
0x1400211bf  mov     edx, [rdx]; unsigned int
0x1400211c1  mov     rcx, rbx; this
0x1400211c4  call    ?FindSnapshotForProcess@CHangReport@@IEAAPEAUHPSS__@@K@Z; CHangReport::FindSnapshotForProcess(ulong)
0x1400211c9  mov     r14, rax
0x1400211cc  test    rax, rax
0x1400211cf  jnz     short loc_1400211E6
0x1400211d1  jmp     short loc_1400211D6
0x1400211d3  mov     r14, r13
0x1400211d6  mov     rax, [rbx+60C0h]
0x1400211dd  inc     rax
0x1400211e0  cmp     rax, 1
0x1400211e4  ja      short loc_14002122B
0x1400211e6  cmp     [rbp+15B0h+var_338], r13b
0x1400211ed  jz      short loc_14002121E
0x1400211ef  mov     eax, [rbp+15B0h+var_334]
0x1400211f5  test    eax, eax
0x1400211f7  jnz     short loc_140021204
0x1400211f9  mov     rax, [rbp+15B0h+String]
0x140021200  mov     eax, [rax]
0x140021202  jmp     short loc_140021224
0x140021204  cmp     eax, 1
0x140021207  jnz     short loc_14002121E
0x140021209  xor     edx, edx; EndPtr
0x14002120b  lea     r8d, [rax+9]; Radix
0x14002120f  mov     rcx, [rbp+15B0h+String]; String
0x140021216  call    cs:__imp_wcstol
0x14002121c  jmp     short loc_140021224
0x14002121e  mov     eax, [rbp+15B0h+var_2D8]
0x140021224  test    eax, eax
0x140021226  mov     r9d, r13d
0x140021229  jz      short loc_140021231
0x14002122b  mov     r9d, 1
0x140021231  mov     r8, [r12]
0x140021235  lea     rdx, [rbx+90h]
0x14002123c  mov     rax, r14
0x14002123f  neg     rax
0x140021242  sbb     ecx, ecx
0x140021244  and     ecx, 0C0000000h
0x14002124a  add     ecx, 20000000h
0x140021250  or      ecx, r9d
0x140021253  mov     [rsp+16B0h+var_1678], r14; struct HPSS__ *
0x140021258  mov     [rsp+16B0h+var_1680], rdx; struct _EXCEPTION_POINTERS *
0x14002125d  mov     [rsp+16B0h+var_1688], ecx; unsigned int
0x140021261  mov     [rsp+16B0h+var_1690], r15d; enum _WER_DUMP_TYPE
0x140021266  mov     r9d, [r8+4]; unsigned int
0x14002126a  mov     r8d, [r8]; unsigned int
0x14002126d  mov     rdx, [rbx+6090h]; void *
0x140021274  mov     rcx, [rbx+5F78h]; void *
0x14002127b  call    ?_AddWerDumpForProcess@CHangReport@@KAJPEAX0KKW4_WER_DUMP_TYPE@@KPEAU_EXCEPTION_POINTERS@@PEAUHPSS__@@@Z; CHangReport::_AddWerDumpForProcess(void *,void *,ulong,ulong,_WER_DUMP_TYPE,ulong,_EXCEPTION_POINTERS *,HPSS__ *)
0x140021280  test    eax, eax
0x140021282  jns     short loc_1400212AE
0x140021284  mov     rcx, cs:WPP_GLOBAL_Control
0x14002128b  cmp     rcx, rdi
0x14002128e  jz      short loc_1400212AE
0x140021290  test    byte ptr [rcx+1Ch], 2
0x140021294  jz      short loc_1400212AE
0x140021296  mov     edx, 61h ; 'a'
0x14002129b  mov     r9d, eax
0x14002129e  lea     r8, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids
0x1400212a5  mov     rcx, [rcx+10h]
0x1400212a9  call    WPP_SF_d
0x1400212ae  lea     r15, [rbx+5F70h]
0x1400212b5  mov     r12d, [rsp+16B0h+var_1670]
0x1400212ba  movsxd  r14, r13d
0x1400212bd  mov     [rsp+16B0h+var_1658], r14
0x1400212c2  mov     rcx, [rbx+r14*8+60C0h]; hProcess
0x1400212ca  lea     rax, [rcx+1]
0x1400212ce  cmp     rax, 1
0x1400212d2  jbe     loc_140021454
0x1400212d8  xor     r8d, r8d; int
0x1400212db  lea     rdx, [rsp+16B0h+Buffer]; lpBuffer
0x1400212e0  call    ?ExtractThreadIdFromPebHandle@@YAJPEAXPEAKH@Z; ExtractThreadIdFromPebHandle(void *,ulong *,int)
0x1400212e5  xor     r15d, r15d
0x1400212e8  test    eax, eax
0x1400212ea  jns     short loc_140021317
0x1400212ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400212f3  cmp     rcx, rdi
0x1400212f6  jz      short loc_140021312
0x1400212f8  test    byte ptr [rcx+1Ch], 2
0x1400212fc  jz      short loc_140021312
0x1400212fe  lea     edx, [r15+62h]
0x140021302  lea     r8, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids
0x140021309  mov     rcx, [rcx+10h]
0x14002130d  call    WPP_SF_
0x140021312  mov     [rsp+16B0h+Buffer], r15d
0x140021317  mov     rcx, [rbx+r14*8+60C0h]; Process
0x14002131f  call    cs:__imp_GetProcessId
0x140021325  mov     [rsp+16B0h+var_1670], eax
0x140021329  cmp     [rbx+6148h], r15d
0x140021330  jnz     short loc_14002138B
0x140021332  mov     edx, eax; unsigned int
0x140021334  mov     rcx, rbx; this
0x140021337  call    ?FindSnapshotForProcess@CHangReport@@IEAAPEAUHPSS__@@K@Z; CHangReport::FindSnapshotForProcess(ulong)
0x14002133c  mov     r14, rax
0x14002133f  test    rax, rax
0x140021342  jz      short loc_14002138E
0x140021344  cmp     [rbp+15B0h+var_338], r15b
0x14002134b  jz      short loc_14002137C
0x14002134d  mov     eax, [rbp+15B0h+var_334]
0x140021353  test    eax, eax
0x140021355  jnz     short loc_140021362
0x140021357  mov     rcx, [rbp+15B0h+String]
0x14002135e  mov     eax, [rcx]
0x140021360  jmp     short loc_140021382
0x140021362  cmp     eax, 1
0x140021365  jnz     short loc_14002137C
0x140021367  xor     edx, edx; EndPtr
0x140021369  lea     r8d, [rax+9]; Radix
0x14002136d  mov     rcx, [rbp+15B0h+String]; String
0x140021374  call    cs:__imp_wcstol
0x14002137a  jmp     short loc_140021382
0x14002137c  mov     eax, [rbp+15B0h+var_2D8]
0x140021382  test    eax, eax
0x140021384  jnz     short loc_14002138E
0x140021386  mov     ecx, r15d
0x140021389  jmp     short loc_140021393
0x14002138b  mov     r14, r15
0x14002138e  mov     ecx, 1
0x140021393  mov     rax, r14
0x140021396  neg     rax
0x140021399  sbb     r8d, r8d
0x14002139c  and     r8d, 0C0000000h
0x1400213a3  add     r8d, 20000002h
0x1400213aa  or      r8d, ecx
0x1400213ad  lea     r15, [rbx+5F70h]
0x1400213b4  inc     r13d
0x1400213b7  mov     [rsp+16B0h+var_1668], r13d
0x1400213bc  movsxd  r13, r13d
0x1400213bf  lea     rdx, [r13+9]
0x1400213c3  shl     rdx, 4
0x1400213c7  add     rdx, rbx
0x1400213ca  mov     rax, [r15]
0x1400213cd  mov     ecx, [rax+5A0h]
0x1400213d3  mov     eax, r8d
0x1400213d6  or      eax, 4
0x1400213d9  bt      ecx, 14h
0x1400213dd  cmovnb  eax, r8d
0x1400213e1  mov     [rsp+16B0h+var_1678], r14; struct HPSS__ *
0x1400213e6  mov     [rsp+16B0h+var_1680], rdx; struct _EXCEPTION_POINTERS *
0x1400213eb  mov     [rsp+16B0h+var_1688], eax; unsigned int
0x1400213ef  mov     [rsp+16B0h+var_1690], r12d; enum _WER_DUMP_TYPE
0x1400213f4  mov     r9d, [rsp+16B0h+Buffer]; unsigned int
0x1400213f9  mov     r8d, [rsp+16B0h+var_1670]; unsigned int
0x1400213fe  mov     rdx, [rsp+16B0h+var_1658]
0x140021403  mov     rdx, [rbx+rdx*8+60C0h]; void *
0x14002140b  mov     rcx, [rbx+5F78h]; void *
0x140021412  call    ?_AddWerDumpForProcess@CHangReport@@KAJPEAX0KKW4_WER_DUMP_TYPE@@KPEAU_EXCEPTION_POINTERS@@PEAUHPSS__@@@Z; CHangReport::_AddWerDumpForProcess(void *,void *,ulong,ulong,_WER_DUMP_TYPE,ulong,_EXCEPTION_POINTERS *,HPSS__ *)
0x140021417  test    eax, eax
0x140021419  jns     short loc_140021445
0x14002141b  mov     rcx, cs:WPP_GLOBAL_Control
0x140021422  cmp     rcx, rdi
0x140021425  jz      short loc_140021445
0x140021427  test    byte ptr [rcx+1Ch], 2
0x14002142b  jz      short loc_140021445
0x14002142d  mov     edx, 63h ; 'c'
0x140021432  mov     r9d, eax
0x140021435  lea     r8, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids
0x14002143c  mov     rcx, [rcx+10h]
0x140021440  call    WPP_SF_d
0x140021445  cmp     r13, 0Fh
0x140021449  mov     r13d, [rsp+16B0h+var_1668]
0x14002144e  jb      loc_1400212BA
0x140021454  mov     rax, [r15]
0x140021457  test    byte ptr [rax+5A0h], 10h
0x14002145e  mov     r12, [rsp+16B0h+var_1660]
0x140021463  jnz     short loc_1400214C7
0x140021465  mov     rcx, [r12]; this
0x140021469  call    ?AppFileName@CProcessInformation@@AEAAPEB_WXZ; CProcessInformation::AppFileName(void)
0x14002146e  mov     r8, rax; wchar_t *
0x140021471  mov     edx, 104h; unsigned __int64
0x140021476  lea     rcx, [rbp+15B0h+var_240]; wchar_t *
0x14002147d  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x140021482  xor     r8d, r8d
0x140021485  lea     rdx, [rbp+15B0h+var_240]
0x14002148c  mov     rcx, [rbx+5F78h]
0x140021493  call    cs:__imp_WerpAddAppCompatData
0x140021499  test    eax, eax
0x14002149b  jns     short loc_1400214C7
0x14002149d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400214a4  cmp     rcx, rdi
0x1400214a7  jz      short loc_1400214C7
0x1400214a9  test    byte ptr [rcx+1Ch], 2
0x1400214ad  jz      short loc_1400214C7
0x1400214af  mov     edx, 64h ; 'd'
0x1400214b4  mov     r9d, eax
0x1400214b7  lea     r8, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids
0x1400214be  mov     rcx, [rcx+10h]
0x1400214c2  call    WPP_SF_d
0x1400214c7  mov     rax, [r15]
0x1400214ca  test    byte ptr [rax+5A0h], 2
0x1400214d1  jz      short loc_1400214DC
0x1400214d3  mov     rcx, rbx; this
0x1400214d6  call    ?_AddOSVersion@CHangReport@@AEAAJXZ; CHangReport::_AddOSVersion(void)
0x1400214db  nop
0x1400214dc  lea     r9, ??1CRegSetting@@QEAA@XZ; void (*)(void *)
0x1400214e3  mov     edx, 68h ; 'h'; unsigned __int64
  ... truncated ...
```
