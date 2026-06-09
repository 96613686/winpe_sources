# CDtcTmManager::InitTm(char *,ulong,ulong,ulong,int,int,int,int,int,int)

- ea: `0x180007668`
- end: `0x180007b9f`
- name: `?InitTm@CDtcTmManager@@QEAAJPEADKKKHHHHHH@Z`
- size: `1335`
- prototype: `__int64 __usercall@<rax>(CDtcTmManager *__hidden this@<rcx>, char *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int, int, int, int, int, int, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180006750`

## callees

- `0x180004c90`
- `0x1800063b0`
- `0x180007668`
- `0x180015230`
- `0x180016fb0`
- `0x18001a210`
- `0x180032b9c`
- `0x1800828f8`
- `0x18008345c`
- `0x18008356c`
- `0x1800856d4`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007b54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007b54`
- `MSDTCPRX!__imp_?ContactToNameObject@@YAPEAUINameObject@@PEAUIProperties@@@Z` at `0x180007884`
- `MSDTCPRX!__imp_?ContactToNameObject@@YAPEAUINameObject@@PEAUIProperties@@@Z` at `0x180007884`

## string_xrefs

- `0x180007693`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x1800076f6`: `GetDtcLogPath failed`
- `0x18000776f`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x180007954`: `DllGetDTCTM failed`

## pseudocode

```c
__int64 __fastcall CDtcTmManager::InitTm(
        CDtcTmManager *this,
        char *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        int a6,
        int a7,
        int a8,
        int a9,
        int a10,
        int a11)
{
  int DTCTM; // ebx
  unsigned int v15; // edx
  int v16; // eax
  const wchar_t *v17; // rax
  __int64 v18; // r9
  unsigned int v19; // edx
  struct INameObject *v20; // rax
  struct IProperties *v21; // rcx
  const struct _GUID *v22; // rdx
  const struct _GUID *v23; // rcx
  int v24; // edi
  char *v26; // [rsp+20h] [rbp-30h]
  char *v27; // [rsp+20h] [rbp-30h]
  char *v28; // [rsp+20h] [rbp-30h]
  unsigned __int16 *v29; // [rsp+28h] [rbp-28h]
  unsigned __int16 *v30; // [rsp+28h] [rbp-28h]
  unsigned __int16 *v31; // [rsp+28h] [rbp-28h]
  int v32; // [rsp+30h] [rbp-20h]
  struct IProperties *v33; // [rsp+90h] [rbp+40h] BYREF
  LPVOID pv; // [rsp+98h] [rbp+48h] BYREF

  v33 = 0;
  pv = 0;
  TraceStringInline(
    3,
    6,
    L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
    1841,
    L"CDtcTmManager::InitTm",
    0,
    L"CDtcTmManager::InitTm IN");
  DTCTM = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(**((_QWORD **)this + 71) + 96LL))(
            *((_QWORD *)this + 71),
            260,
            (char *)this + 32);
  if ( DTCTM < 0 )
  {
    LODWORD(v29) = DTCTM;
    TraceStringInline(
      3,
      1,
      L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
      1847,
      L"CDtcTmManager::InitTm",
      v29,
      L"GetDtcLogPath failed");
    if ( z_pTrace )
    {
      v16 = (*(__int64 (__fastcall **)(struct IDtcTrace *, __int64, __int64, _QWORD, int, _DWORD, _QWORD, _QWORD))(*(_QWORD *)z_pTrace + 24LL))(
              z_pTrace,
              1,
              1,
              0,
              -1073737711,
              0,
              0,
              0);
      if ( v16 < 0 )
        TraceFile(v16, "failed in z_pTrace->Trace", "com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp", 0x961u);
    }
    else
    {
      DtcWriteToEventLoggerW(1u, v15, 0xC0001011, 0, 0, v30, v32);
    }
    goto LABEL_26;
  }
  StringCbCatW((unsigned __int16 *)this + 16, 0x208u, L"\\MSDTC.LOG");
  DTCTM = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(**((_QWORD **)this + 71) + 296LL))(*((_QWORD *)this + 71), &pv);
  if ( DTCTM < 0 )
  {
    v17 = L"Call to GetMsDtcSPN failed";
    v18 = 1856;
LABEL_8:
    LODWORD(v29) = DTCTM;
    TraceStringInline(3, 1, L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp", v18, L"CDtcTmManager::InitTm", v29, v17);
    goto LABEL_26;
  }
  DTCTM = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, struct IProperties **))(**((_QWORD **)this + 71) + 144LL))(
            *((_QWORD *)this + 71),
            L"MSDTC",
            &v33);
  if ( DTCTM < 0 )
  {
    LODWORD(v29) = DTCTM;
    TraceStringInline(
      3,
      1,
      L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
      1864,
      L"CDtcTmManager::InitTm",
      v29,
      L"GetTmContact failed");
    v19 = -1073737695;
LABEL_11:
    locprint(1u, v19, 0, 0, v27);
    goto LABEL_26;
  }
  v20 = ContactToNameObject(v33);
  *((_QWORD *)this + 72) = v20;
  if ( !v20 )
  {
    locprint(1u, 0xC0001014, 0, 0, v26);
    v17 = L"failed in the first call to ContactToNameObject";
    v18 = 1874;
    DTCTM = -2147418113;
    goto LABEL_8;
  }
  DTCTM = (*(__int64 (__fastcall **)(struct INameObject *, LPVOID))(*(_QWORD *)v20 + 104LL))(v20, pv);
  if ( DTCTM < 0 )
  {
    LODWORD(v29) = DTCTM;
    TraceStringInline(
      3,
      1,
      L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
      1882,
      L"CDtcTmManager::InitTm",
      v29,
      L"SetSPN failed");
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 72) + 16LL))(*((_QWORD *)this + 72));
    *((_QWORD *)this + 72) = 0;
    goto LABEL_26;
  }
  v21 = v33;
  *(_QWORD *)this = 0;
  (*(void (__fastcall **)(struct IProperties *))(*(_QWORD *)v21 + 16LL))(v21);
  DTCTM = DllGetDTCTM(v23, v22, (void **)this);
  if ( DTCTM )
  {
    LODWORD(v29) = DTCTM;
    TraceStringInline(
      3,
      1,
      L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
      1897,
      L"CDtcTmManager::InitTm",
      v29,
      L"DllGetDTCTM failed");
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 72) + 16LL))(*((_QWORD *)this + 72));
    v19 = -1073737710;
    *((_QWORD *)this + 72) = 0;
    goto LABEL_11;
  }
  DTCTM = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, unsigned int))(**(_QWORD **)this + 24LL))(
            *(_QWORD *)this,
            *((_QWORD *)this + 72),
            a3,
            a4,
            a5);
  if ( DTCTM )
  {
    LODWORD(v29) = DTCTM;
    TraceStringInline(
      3,
      1,
      L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
      1914,
      L"CDtcTmManager::InitTm",
      v29,
      L"ITmInit3::Init failed");
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 72) + 16LL))(*((_QWORD *)this + 72));
    *((_QWORD *)this + 72) = 0;
    locprint(1u, 0xC0001006, 0, 0, v28);
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)this + 16LL))(*(_QWORD *)this);
    *(_QWORD *)this = 0;
    goto LABEL_26;
  }
  DTCTM = CDtcTmManager::InitUIServer(this, (const unsigned __int16 *)pv);
  if ( DTCTM )
  {
    LODWORD(v29) = DTCTM;
    TraceStringInline(
      3,
      1,
      L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
      1928,
      L"CDtcTmManager::InitTm",
      v29,
      L"InitUIServer failed");
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 72) + 16LL))(*((_QWORD *)this + 72));
    v19 = -1073737707;
    *((_QWORD *)this + 72) = 0;
    goto LABEL_11;
  }
  v24 = a10;
  if ( a10 )
  {
    TraceStringInline(
      3,
      4,
      L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
      1943,
      L"CDtcTmManager::InitTm",
      0,
      L"Calling InitTipGateway since TIP is enabled");
    CDtcTmManager::InitTipGateway(this, (unsigned __int16 *)pv, v24, a7);
  }
  else
  {
    TraceStringInline(
      3,
      4,
      L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
      1948,
      L"CDtcTmManager::InitTm",
      0,
      L"Skipping call to InitTipGateway since TIP is disabled");
  }
  CDtcTmManager::InitXaTm(this, (unsigned __int16 *)pv, a11, a7);
  InitTransactionBridge(
    *((struct ITmInstance **)this + 71),
    *((struct IUnknown **)this + 3),
    *((struct INameObject **)this + 72),
    (struct ITransactionBridge **)this + 70);
  CoTaskMemFree(pv);
LABEL_26:
  LODWORD(v31) = DTCTM;
  TraceStringInline(
    3,
    6,
    L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
    1957,
    L"CDtcTmManager::InitTm",
    v31,
    L"CDtcTmManager::InitTm OUT");
  return (unsigned int)DTCTM;
}

```

## disassembly

```asm
0x180007668  mov     r11, rsp
0x18000766b  mov     [r11+18h], rbx
0x18000766f  mov     [r11+10h], rdx
0x180007673  push    rbp
0x180007674  push    rsi
0x180007675  push    rdi
0x180007676  push    r12
0x180007678  push    r13
0x18000767a  push    r14
0x18000767c  push    r15
0x18000767e  mov     rbp, rsp
0x180007681  sub     rsp, 50h
0x180007685  xor     r12d, r12d
0x180007688  lea     rax, aCdtctmmanagerI_2; "CDtcTmManager::InitTm IN"
0x18000768f  mov     [r11-58h], rax
0x180007693  lea     r13, aComComplusDtcD_88; "com\\complus\\dtc\\dtc\\msdtc\\src\\msd"...
0x18000769a  mov     r14d, r9d
0x18000769d  mov     [r11-60h], r12
0x1800076a1  mov     r15d, r8d
0x1800076a4  mov     [rbp+arg_0], r12
0x1800076a8  lea     edx, [r12+6]
0x1800076ad  mov     [rbp+pv], r12
0x1800076b1  mov     rsi, rcx
0x1800076b4  lea     rax, aCdtctmmanagerI_5; "CDtcTmManager::InitTm"
0x1800076bb  lea     ecx, [rdx-3]
0x1800076be  mov     [r11-68h], rax
0x1800076c2  mov     r9d, 731h
0x1800076c8  mov     r8, r13
0x1800076cb  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800076d0  mov     rcx, [rsi+238h]
0x1800076d7  lea     r8, [rsi+20h]
0x1800076db  mov     edx, 104h
0x1800076e0  mov     rax, [rcx]
0x1800076e3  mov     rax, [rax+60h]
0x1800076e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076ec  mov     ebx, eax
0x1800076ee  test    eax, eax
0x1800076f0  jns     loc_1800077A0
0x1800076f6  lea     rax, aGetdtclogpathF; "GetDtcLogPath failed"
0x1800076fd  mov     r9d, 737h
0x180007703  mov     qword ptr [rsp+50h+var_20], rax; int
0x180007708  lea     edi, [r12+1]
0x18000770d  lea     r14, aCdtctmmanagerI_5; "CDtcTmManager::InitTm"
0x180007714  mov     dword ptr [rsp+50h+var_28], ebx; unsigned __int16 *
0x180007718  mov     r8, r13
0x18000771b  mov     [rsp+50h+var_30], r14
0x180007720  mov     edx, edi
0x180007722  lea     ecx, [rdi+2]
0x180007725  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18000772a  mov     rcx, cs:?z_pTrace@@3PEAUIDtcTrace@@EA; IDtcTrace * z_pTrace
0x180007731  xor     r9d, r9d; unsigned int
0x180007734  test    rcx, rcx
0x180007737  jz      short loc_180007789
0x180007739  mov     rax, [rcx]
0x18000773c  mov     r8d, edi
0x18000773f  mov     [rsp+50h+var_18], r12
0x180007744  mov     edx, edi
0x180007746  mov     qword ptr [rsp+50h+var_20], r12
0x18000774b  mov     dword ptr [rsp+50h+var_28], r12d
0x180007750  mov     rax, [rax+18h]
0x180007754  mov     dword ptr [rsp+50h+var_30], 0C0001011h
0x18000775c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007761  test    eax, eax
0x180007763  jns     loc_180007B5A
0x180007769  mov     r9d, 961h; unsigned int
0x18000776f  lea     r8, aComComplusDtcD_7; "com\\complus\\dtc\\dtc\\msdtc\\src\\msd"...
0x180007776  lea     rdx, aFailedInZPtrac; "failed in z_pTrace->Trace"
0x18000777d  mov     ecx, eax; int
0x18000777f  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180007784  jmp     loc_180007B5A
0x180007789  mov     r8d, 0C0001011h; unsigned int
0x18000778f  mov     [rsp+50h+var_30], r12; void *
0x180007794  mov     ecx, edi; unsigned int
0x180007796  call    ?DtcWriteToEventLoggerW@@YAJKKKKPEAXPEAGH@Z; DtcWriteToEventLoggerW(ulong,ulong,ulong,ulong,void *,ushort *,int)
0x18000779b  jmp     loc_180007B5A
0x1800077a0  lea     r8, aMsdtcLog; "\\MSDTC.LOG"
0x1800077a7  mov     edx, 208h; unsigned __int64
0x1800077ac  lea     rcx, [rsi+20h]; unsigned __int16 *
0x1800077b0  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x1800077b5  mov     rcx, [rsi+238h]
0x1800077bc  lea     rdx, [rbp+pv]
0x1800077c0  mov     rax, [rcx]
0x1800077c3  mov     rax, [rax+128h]
0x1800077ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077cf  mov     ebx, eax
0x1800077d1  test    eax, eax
0x1800077d3  jns     short loc_18000780E
0x1800077d5  lea     rax, aCallToGetmsdtc; "Call to GetMsDtcSPN failed"
0x1800077dc  mov     r9d, 740h
0x1800077e2  mov     edx, 1
0x1800077e7  mov     qword ptr [rsp+50h+var_20], rax
0x1800077ec  lea     r14, aCdtctmmanagerI_5; "CDtcTmManager::InitTm"
0x1800077f3  mov     dword ptr [rsp+50h+var_28], ebx
0x1800077f7  mov     r8, r13
0x1800077fa  mov     ecx, 3
0x1800077ff  mov     [rsp+50h+var_30], r14
0x180007804  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180007809  jmp     loc_180007B5A
0x18000780e  mov     rcx, [rsi+238h]
0x180007815  lea     r8, [rbp+arg_0]
0x180007819  lea     rdx, aMsdtc; "MSDTC"
0x180007820  mov     rax, [rcx]
0x180007823  mov     rax, [rax+90h]
0x18000782a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000782f  mov     ebx, eax
0x180007831  test    eax, eax
0x180007833  jns     short loc_180007880
0x180007835  mov     edi, 1
0x18000783a  lea     rax, aGettmcontactFa_0; "GetTmContact failed"
0x180007841  mov     qword ptr [rsp+50h+var_20], rax
0x180007846  lea     r14, aCdtctmmanagerI_5; "CDtcTmManager::InitTm"
0x18000784d  mov     dword ptr [rsp+50h+var_28], ebx
0x180007851  mov     r9d, 748h
0x180007857  mov     r8, r13
0x18000785a  mov     [rsp+50h+var_30], r14; char *
0x18000785f  lea     ecx, [rdi+2]
0x180007862  mov     edx, edi
0x180007864  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180007869  mov     edx, 0C0001021h; unsigned int
0x18000786e  xor     r9d, r9d; void *
0x180007871  xor     r8d, r8d; unsigned int
0x180007874  mov     ecx, edi; unsigned int
0x180007876  call    ?locprint@@YAXKKKPEAXPEAD@Z; locprint(ulong,ulong,ulong,void *,char *)
0x18000787b  jmp     loc_180007B5A
0x180007880  mov     rcx, [rbp+arg_0]
0x180007884  call    cs:__imp_?ContactToNameObject@@YAPEAUINameObject@@PEAUIProperties@@@Z; ContactToNameObject(IProperties *)
0x18000788a  mov     [rsi+240h], rax
0x180007891  mov     rcx, rax
0x180007894  test    rax, rax
0x180007897  jnz     short loc_1800078C7
0x180007899  lea     edi, [rax+1]
0x18000789c  xor     r9d, r9d; void *
0x18000789f  mov     ecx, edi; unsigned int
0x1800078a1  xor     r8d, r8d; unsigned int
0x1800078a4  mov     edx, 0C0001014h; unsigned int
0x1800078a9  call    ?locprint@@YAXKKKPEAXPEAD@Z; locprint(ulong,ulong,ulong,void *,char *)
0x1800078ae  lea     rax, aFailedInTheFir; "failed in the first call to ContactToNa"...
0x1800078b5  mov     r9d, 752h
0x1800078bb  mov     edx, edi
0x1800078bd  mov     ebx, 8000FFFFh
0x1800078c2  jmp     loc_1800077E7
0x1800078c7  mov     rax, [rax]
0x1800078ca  mov     rdx, [rbp+pv]
0x1800078ce  mov     rax, [rax+68h]
0x1800078d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078d7  mov     ebx, eax
0x1800078d9  test    eax, eax
0x1800078db  jns     short loc_18000792E
0x1800078dd  mov     edx, 1
0x1800078e2  lea     rax, aSetspnFailed; "SetSPN failed"
0x1800078e9  mov     qword ptr [rsp+50h+var_20], rax
0x1800078ee  lea     r14, aCdtctmmanagerI_5; "CDtcTmManager::InitTm"
0x1800078f5  mov     dword ptr [rsp+50h+var_28], ebx
0x1800078f9  mov     r9d, 75Ah
0x1800078ff  mov     r8, r13
0x180007902  mov     [rsp+50h+var_30], r14
0x180007907  lea     ecx, [rdx+2]
0x18000790a  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18000790f  mov     rcx, [rsi+240h]
0x180007916  mov     rax, [rcx]
0x180007919  mov     rax, [rax+10h]
0x18000791d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007922  mov     [rsi+240h], r12
0x180007929  jmp     loc_180007B5A
0x18000792e  mov     rcx, [rbp+arg_0]
0x180007932  mov     [rsi], r12
0x180007935  mov     rax, [rcx]
0x180007938  mov     rax, [rax+10h]
0x18000793c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007941  mov     r8, rsi; void **
0x180007944  call    ?DllGetDTCTM@@YAJAEBU_GUID@@0PEAPEAX@Z; DllGetDTCTM(_GUID const &,_GUID const &,void * *)
0x180007949  mov     ebx, eax
0x18000794b  test    eax, eax
0x18000794d  jz      short loc_1800079A7
0x18000794f  mov     edi, 1
0x180007954  lea     rax, aDllgetdtctmFai; "DllGetDTCTM failed"
0x18000795b  mov     qword ptr [rsp+50h+var_20], rax
0x180007960  lea     r14, aCdtctmmanagerI_5; "CDtcTmManager::InitTm"
0x180007967  mov     dword ptr [rsp+50h+var_28], ebx
0x18000796b  mov     r9d, 769h
0x180007971  mov     r8, r13
0x180007974  mov     [rsp+50h+var_30], r14
0x180007979  lea     ecx, [rdi+2]
0x18000797c  mov     edx, edi
0x18000797e  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180007983  mov     rcx, [rsi+240h]
0x18000798a  mov     rax, [rcx]
0x18000798d  mov     rax, [rax+10h]
0x180007991  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007996  mov     edx, 0C0001012h
0x18000799b  mov     [rsi+240h], r12
0x1800079a2  jmp     loc_18000786E
0x1800079a7  mov     rcx, [rsi]
0x1800079aa  mov     r9d, r14d
0x1800079ad  mov     edx, [rbp+arg_20]
0x1800079b0  mov     r8d, r15d
0x1800079b3  mov     dword ptr [rsp+50h+var_30], edx
0x1800079b7  mov     rdx, [rsi+240h]
0x1800079be  mov     rax, [rcx]
0x1800079c1  mov     rax, [rax+18h]
0x1800079c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079ca  mov     ebx, eax
0x1800079cc  test    eax, eax
0x1800079ce  jz      short loc_180007A47
0x1800079d0  mov     edi, 1
0x1800079d5  lea     rax, aItminit3InitFa; "ITmInit3::Init failed"
0x1800079dc  mov     qword ptr [rsp+50h+var_20], rax
0x1800079e1  lea     r14, aCdtctmmanagerI_5; "CDtcTmManager::InitTm"
0x1800079e8  mov     dword ptr [rsp+50h+var_28], ebx
0x1800079ec  mov     r9d, 77Ah
0x1800079f2  mov     r8, r13
0x1800079f5  mov     [rsp+50h+var_30], r14; char *
0x1800079fa  lea     ecx, [rdi+2]
0x1800079fd  mov     edx, edi
0x1800079ff  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180007a04  mov     rcx, [rsi+240h]
0x180007a0b  mov     rax, [rcx]
0x180007a0e  mov     rax, [rax+10h]
0x180007a12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a17  xor     r9d, r9d; void *
0x180007a1a  mov     [rsi+240h], r12
0x180007a21  xor     r8d, r8d; unsigned int
0x180007a24  mov     edx, 0C0001006h; unsigned int
0x180007a29  mov     ecx, edi; unsigned int
0x180007a2b  call    ?locprint@@YAXKKKPEAXPEAD@Z; locprint(ulong,ulong,ulong,void *,char *)
0x180007a30  mov     rcx, [rsi]
0x180007a33  mov     rax, [rcx]
0x180007a36  mov     rax, [rax+10h]
0x180007a3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a3f  mov     [rsi], r12
0x180007a42  jmp     loc_180007B5A
0x180007a47  mov     r8d, [rbp+arg_28]; int
0x180007a4b  mov     rcx, rsi; this
0x180007a4e  mov     rdx, [rbp+pv]; unsigned __int16 *
0x180007a52  call    ?InitUIServer@CDtcTmManager@@QEAAJPEBGH@Z; CDtcTmManager::InitUIServer(ushort const *,int)
0x180007a57  lea     r14, aCdtctmmanagerI_5; "CDtcTmManager::InitTm"
0x180007a5e  mov     ebx, eax
0x180007a60  mov     r8, r13
0x180007a63  mov     ecx, 3
0x180007a68  test    eax, eax
0x180007a6a  jz      short loc_180007AB5
0x180007a6c  lea     rax, aInituiserverFa; "InitUIServer failed"
0x180007a73  mov     r9d, 788h
0x180007a79  mov     qword ptr [rsp+50h+var_20], rax
0x180007a7e  lea     edi, [rcx-2]
0x180007a81  mov     dword ptr [rsp+50h+var_28], ebx
0x180007a85  mov     edx, edi
0x180007a87  mov     [rsp+50h+var_30], r14
0x180007a8c  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180007a91  mov     rcx, [rsi+240h]
0x180007a98  mov     rax, [rcx]
0x180007a9b  mov     rax, [rax+10h]
0x180007a9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007aa4  mov     edx, 0C0001015h
0x180007aa9  mov     [rsi+240h], r12
0x180007ab0  jmp     loc_18000786E
0x180007ab5  mov     edi, [rbp+arg_48]
0x180007abb  mov     edx, 4
0x180007ac0  test    edi, edi
0x180007ac2  jz      short loc_180007AFA
0x180007ac4  lea     rax, aCallingInittip; "Calling InitTipGateway since TIP is ena"...
0x180007acb  mov     r9d, 797h
0x180007ad1  mov     qword ptr [rsp+50h+var_20], rax
0x180007ad6  mov     [rsp+50h+var_28], r12
0x180007adb  mov     [rsp+50h+var_30], r14
0x180007ae0  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180007ae5  mov     r9d, [rbp+arg_30]; int
0x180007ae9  mov     r8d, edi; int
0x180007aec  mov     rdx, [rbp+pv]; unsigned __int16 *
0x180007af0  mov     rcx, rsi; this
0x180007af3  call    ?InitTipGateway@CDtcTmManager@@IEAAXPEAGHH@Z; CDtcTmManager::InitTipGateway(ushort *,int,int)
0x180007af8  jmp     short loc_180007B1B
0x180007afa  lea     rax, aSkippingCallTo; "Skipping call to InitTipGateway since T"...
0x180007b01  mov     r9d, 79Ch
0x180007b07  mov     qword ptr [rsp+50h+var_20], rax
0x180007b0c  mov     [rsp+50h+var_28], r12
0x180007b11  mov     [rsp+50h+var_30], r14
0x180007b16  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180007b1b  mov     r9d, [rbp+arg_30]; int
0x180007b1f  mov     rcx, rsi; this
0x180007b22  mov     r8d, [rbp+arg_50]; int
0x180007b29  mov     rdx, [rbp+pv]; unsigned __int16 *
0x180007b2d  call    ?InitXaTm@CDtcTmManager@@IEAAXPEAGHH@Z; CDtcTmManager::InitXaTm(ushort *,int,int)
0x180007b32  mov     r8, [rsi+240h]; struct INameObject *
0x180007b39  lea     r9, [rsi+230h]; struct ITransactionBridge **
0x180007b40  mov     rdx, [rsi+18h]; struct IUnknown *
0x180007b44  mov     rcx, [rsi+238h]; struct ITmInstance *
0x180007b4b  call    ?InitTransactionBridge@@YAJPEAUITmInstance@@PEAUIUnknown@@PEAUINameObject@@PEAPEAUITransactionBridge@@@Z; InitTransactionBridge(ITmInstance *,IUnknown *,INameObject *,ITransactionBridge * *)
0x180007b50  mov     rcx, [rbp+pv]; pv
0x180007b54  call    cs:__imp_CoTaskMemFree
0x180007b5a  mov     edx, 6
0x180007b5f  lea     rax, aCdtctmmanagerI_0; "CDtcTmManager::InitTm OUT"
0x180007b66  mov     qword ptr [rsp+50h+var_20], rax
0x180007b6b  mov     r9d, 7A5h
0x180007b71  mov     dword ptr [rsp+50h+var_28], ebx
0x180007b75  mov     r8, r13
0x180007b78  mov     [rsp+50h+var_30], r14
0x180007b7d  lea     ecx, [rdx-3]
0x180007b80  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180007b85  mov     eax, ebx
  ... truncated ...
```
