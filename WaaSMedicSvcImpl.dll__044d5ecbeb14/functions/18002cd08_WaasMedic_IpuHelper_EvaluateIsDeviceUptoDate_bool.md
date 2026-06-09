# WaasMedic::IpuHelper::EvaluateIsDeviceUptoDate(bool &)

- ea: `0x18002cd08`
- end: `0x18002d100`
- name: `?EvaluateIsDeviceUptoDate@IpuHelper@WaasMedic@@SAJAEA_N@Z`
- size: `1016`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180061d00`

## callees

- `0x1800050a0`
- `0x180020d88`
- `0x180022e64`
- `0x18002524c`
- `0x180025398`
- `0x18002cd08`
- `0x18002e81c`
- `0x1800639bc`
- `0x18006531c`
- `0x18006f010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18002cd50`
- `OLEAUT32!__imp_VariantInit` at `0x18002cd50`
- `OLEAUT32!__imp_VariantClear` at `0x18002cd85`
- `OLEAUT32!__imp_VariantClear` at `0x18002cdf7`
- `OLEAUT32!__imp_VariantClear` at `0x18002ce58`
- `OLEAUT32!__imp_VariantClear` at `0x18002cec5`
- `OLEAUT32!__imp_VariantClear` at `0x18002cf5c`
- `OLEAUT32!__imp_VariantClear` at `0x18002cffc`
- `OLEAUT32!__imp_VariantClear` at `0x18002d067`
- `OLEAUT32!__imp_VariantClear` at `0x18002cd85`
- `OLEAUT32!__imp_VariantClear` at `0x18002cdf7`
- `OLEAUT32!__imp_VariantClear` at `0x18002ce58`
- `OLEAUT32!__imp_VariantClear` at `0x18002cec5`
- `OLEAUT32!__imp_VariantClear` at `0x18002cf5c`
- `OLEAUT32!__imp_VariantClear` at `0x18002cffc`
- `OLEAUT32!__imp_VariantClear` at `0x18002d067`

## string_xrefs

- `0x18002cf45`: `Error encountered when reading %s! hr=0x%08X`
- `0x18002cfe5`: `Error encountered when reading %s! hr=0x%08X`
- `0x18002ce9f`: `Failed to CreateInstance for State provider!`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WaasMedic::IpuHelper::EvaluateIsDeviceUptoDate(bool *a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  HRESULT v4; // eax
  struct WaasMedic::IRunnable *v6; // rdi
  int v7; // eax
  HRESULT v8; // eax
  int v9; // eax
  HRESULT v10; // eax
  HRESULT v11; // eax
  __int64 v12; // rbx
  int v13; // eax
  unsigned int v14; // esi
  HRESULT v15; // eax
  LONG lVal; // esi
  int v17; // eax
  unsigned int v18; // r15d
  HRESULT v19; // eax
  LONG v20; // eax
  HRESULT v21; // eax
  const char *v22; // [rsp+28h] [rbp-D8h]
  VARIANTARG pvarg; // [rsp+30h] [rbp-D0h] BYREF
  struct WaasMedic::IRunnable *v24; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v25; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v26[176]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v24 = 0;
  WaasMedic::SummaryEvent::SummaryEvent((WaasMedic::SummaryEvent *)v26);
  v25 = 0;
  VariantInit(&pvarg);
  *a1 = 0;
  v2 = WaasMedic::WaasCurrencyDetector::CreateInstance(&v24);
  v3 = v2;
  if ( v2 < 0 )
  {
    LogLevelW(2u, L"Error encountered when creating instance for WaasCurrencyDetector! hr=0x%08X", (unsigned int)v2);
    v4 = VariantClear(&pvarg);
    if ( v4 < 0 )
      _com_issue_error(v4);
    WaasMedic::SummaryEvent::~SummaryEvent((WaasMedic::SummaryEvent *)v26);
    if ( v24 )
      (*(void (__fastcall **)(struct WaasMedic::IRunnable *))(*(_QWORD *)v24 + 16LL))(v24);
    return v3;
  }
  v6 = v24;
  v7 = (*(__int64 (__fastcall **)(struct WaasMedic::IRunnable *, _QWORD, _BYTE *))(*(_QWORD *)v24 + 24LL))(v24, 0, v26);
  v3 = v7;
  if ( v7 < 0 )
  {
    LogLevelW(2u, L"Error encountered when initializing instance of WaasCurrencyDetector! hr=0x%08X", (unsigned int)v7);
    v8 = VariantClear(&pvarg);
    if ( v8 < 0 )
      _com_issue_error(v8);
    WaasMedic::SummaryEvent::~SummaryEvent((WaasMedic::SummaryEvent *)v26);
    if ( v6 )
      (*(void (__fastcall **)(struct WaasMedic::IRunnable *))(*(_QWORD *)v6 + 16LL))(v6);
    return v3;
  }
  v9 = (*(__int64 (__fastcall **)(struct WaasMedic::IRunnable *, _QWORD))(*(_QWORD *)v6 + 32LL))(v6, 0);
  v3 = v9;
  if ( v9 < 0 )
  {
    LogLevelW(2u, L"Error encountered when runnning instance of WaasCurrencyDetector! hr=0x%08X", (unsigned int)v9);
    v10 = VariantClear(&pvarg);
    if ( v10 < 0 )
      _com_issue_error(v10);
    WaasMedic::SummaryEvent::~SummaryEvent((WaasMedic::SummaryEvent *)v26);
    if ( v6 )
      (*(void (__fastcall **)(struct WaasMedic::IRunnable *))(*(_QWORD *)v6 + 16LL))(v6);
    return v3;
  }
  v3 = WaasMedic::StateProvider::CreateInstance(&v25);
  if ( (v3 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x8A,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\ipuhelper.cpp",
      (const char *)v3,
      (int)"Failed to CreateInstance for State provider!",
      v22);
    v11 = VariantClear(&pvarg);
    if ( v11 < 0 )
      _com_issue_error(v11);
    if ( v25 )
      (**(void (__fastcall ***)(__int64, __int64))v25)(v25, 1);
    WaasMedic::SummaryEvent::~SummaryEvent((WaasMedic::SummaryEvent *)v26);
    if ( v6 )
      (*(void (__fastcall **)(struct WaasMedic::IRunnable *))(*(_QWORD *)v6 + 16LL))(v6);
    return v3;
  }
  v12 = v25;
  v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, const unsigned __int16 *, VARIANTARG *))(*(_QWORD *)v25 + 16LL))(
          v25,
          0,
          L"FeatureAssessmentImpactLevel",
          &pvarg);
  v14 = v13;
  if ( v13 >= 0 )
  {
    lVal = 0;
    if ( pvarg.vt == 19 )
      lVal = pvarg.lVal;
    v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, const unsigned __int16 *, VARIANTARG *))(*(_QWORD *)v12 + 16LL))(
            v12,
            0,
            L"QualityAssessmentImpactLevel",
            &pvarg);
    v18 = v17;
    if ( v17 >= 0 )
    {
      v20 = 0;
      if ( pvarg.vt == 19 )
        v20 = pvarg.lVal;
      if ( lVal <= v20 )
        lVal = v20;
      if ( !lVal )
        *a1 = 1;
      v21 = VariantClear(&pvarg);
      if ( v21 < 0 )
        _com_issue_error(v21);
      if ( v12 )
        (**(void (__fastcall ***)(__int64, __int64))v12)(v12, 1);
      WaasMedic::SummaryEvent::~SummaryEvent((WaasMedic::SummaryEvent *)v26);
      if ( v6 )
        (*(void (__fastcall **)(struct WaasMedic::IRunnable *))(*(_QWORD *)v6 + 16LL))(v6);
      return 0;
    }
    else
    {
      LogLevelW(2u, L"Error encountered when reading %s! hr=0x%08X", L"QualityAssessmentImpactLevel", (unsigned int)v17);
      v19 = VariantClear(&pvarg);
      if ( v19 < 0 )
        _com_issue_error(v19);
      if ( v12 )
        (**(void (__fastcall ***)(__int64, __int64))v12)(v12, 1);
      WaasMedic::SummaryEvent::~SummaryEvent((WaasMedic::SummaryEvent *)v26);
      if ( v6 )
        (*(void (__fastcall **)(struct WaasMedic::IRunnable *))(*(_QWORD *)v6 + 16LL))(v6);
      return v18;
    }
  }
  else
  {
    LogLevelW(2u, L"Error encountered when reading %s! hr=0x%08X", L"FeatureAssessmentImpactLevel", (unsigned int)v13);
    v15 = VariantClear(&pvarg);
    if ( v15 < 0 )
      _com_issue_error(v15);
    if ( v12 )
      (**(void (__fastcall ***)(__int64, __int64))v12)(v12, 1);
    WaasMedic::SummaryEvent::~SummaryEvent((WaasMedic::SummaryEvent *)v26);
    if ( v6 )
      (*(void (__fastcall **)(struct WaasMedic::IRunnable *))(*(_QWORD *)v6 + 16LL))(v6);
    return v14;
  }
}

```

## disassembly

```asm
0x18002cd08  push    rbp
0x18002cd0a  push    rbx
0x18002cd0b  push    rsi
0x18002cd0c  push    rdi
0x18002cd0d  push    r14
0x18002cd0f  push    r15
0x18002cd11  lea     rbp, [rsp-28h]
0x18002cd16  sub     rsp, 128h
0x18002cd1d  mov     rax, cs:__security_cookie
0x18002cd24  xor     rax, rsp
0x18002cd27  mov     [rbp+50h+var_40], rax
0x18002cd2b  mov     r14, rcx
0x18002cd2e  mov     [rsp+150h+var_108], 0
0x18002cd37  lea     rcx, [rsp+150h+var_F0]; this
0x18002cd3c  call    ??0SummaryEvent@WaasMedic@@QEAA@XZ; WaasMedic::SummaryEvent::SummaryEvent(void)
0x18002cd41  nop
0x18002cd42  mov     [rsp+150h+var_100], 0
0x18002cd4b  lea     rcx, [rsp+150h+pvarg]; pvarg
0x18002cd50  call    cs:__imp_VariantInit
0x18002cd56  nop
0x18002cd57  mov     byte ptr [r14], 0
0x18002cd5b  lea     rcx, [rsp+150h+var_108]; struct WaasMedic::IRunnable **
0x18002cd60  call    ?CreateInstance@WaasCurrencyDetector@WaasMedic@@SAJPEAPEAVIRunnable@2@@Z; WaasMedic::WaasCurrencyDetector::CreateInstance(WaasMedic::IRunnable * *)
0x18002cd65  mov     ebx, eax
0x18002cd67  test    eax, eax
0x18002cd69  jns     short loc_18002CDBC
0x18002cd6b  mov     r8d, eax
0x18002cd6e  lea     rdx, aErrorEncounter_10; "Error encountered when creating instanc"...
0x18002cd75  mov     ecx, 2; unsigned __int8
0x18002cd7a  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002cd7f  nop
0x18002cd80  lea     rcx, [rsp+150h+pvarg]; pvarg
0x18002cd85  call    cs:__imp_VariantClear
0x18002cd8b  test    eax, eax
0x18002cd8d  js      loc_18002D0D0
0x18002cd93  lea     rcx, [rsp+150h+var_F0]; this
0x18002cd98  call    ??1SummaryEvent@WaasMedic@@QEAA@XZ; WaasMedic::SummaryEvent::~SummaryEvent(void)
0x18002cd9d  nop
0x18002cd9e  mov     rcx, [rsp+150h+var_108]
0x18002cda3  test    rcx, rcx
0x18002cda6  jz      short loc_18002CDB5
0x18002cda8  mov     rax, [rcx]
0x18002cdab  mov     rax, [rax+10h]
0x18002cdaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cdb4  nop
0x18002cdb5  mov     eax, ebx
0x18002cdb7  jmp     loc_18002D0AC
0x18002cdbc  mov     rdi, [rsp+150h+var_108]
0x18002cdc1  mov     rax, [rdi]
0x18002cdc4  lea     r8, [rsp+150h+var_F0]
0x18002cdc9  xor     edx, edx
0x18002cdcb  mov     rcx, rdi
0x18002cdce  mov     rax, [rax+18h]
0x18002cdd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cdd7  mov     ebx, eax
0x18002cdd9  test    eax, eax
0x18002cddb  jns     short loc_18002CE27
0x18002cddd  mov     r8d, eax
0x18002cde0  lea     rdx, aErrorEncounter_0; "Error encountered when initializing ins"...
0x18002cde7  mov     ecx, 2; unsigned __int8
0x18002cdec  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002cdf1  nop
0x18002cdf2  lea     rcx, [rsp+150h+pvarg]; pvarg
0x18002cdf7  call    cs:__imp_VariantClear
0x18002cdfd  test    eax, eax
0x18002cdff  js      loc_18002D0D8
0x18002ce05  lea     rcx, [rsp+150h+var_F0]; this
0x18002ce0a  call    ??1SummaryEvent@WaasMedic@@QEAA@XZ; WaasMedic::SummaryEvent::~SummaryEvent(void)
0x18002ce0f  nop
0x18002ce10  test    rdi, rdi
0x18002ce13  jz      short loc_18002CE25
0x18002ce15  mov     rax, [rdi]
0x18002ce18  mov     rcx, rdi
0x18002ce1b  mov     rax, [rax+10h]
0x18002ce1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce24  nop
0x18002ce25  jmp     short loc_18002CDB5
0x18002ce27  mov     rax, [rdi]
0x18002ce2a  xor     edx, edx
0x18002ce2c  mov     rcx, rdi
0x18002ce2f  mov     rax, [rax+20h]
0x18002ce33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce38  mov     ebx, eax
0x18002ce3a  test    eax, eax
0x18002ce3c  jns     short loc_18002CE8B
0x18002ce3e  mov     r8d, eax
0x18002ce41  lea     rdx, aErrorEncounter_15; "Error encountered when runnning instanc"...
0x18002ce48  mov     ecx, 2; unsigned __int8
0x18002ce4d  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002ce52  nop
0x18002ce53  lea     rcx, [rsp+150h+pvarg]; pvarg
0x18002ce58  call    cs:__imp_VariantClear
0x18002ce5e  test    eax, eax
0x18002ce60  js      loc_18002D0E0
0x18002ce66  lea     rcx, [rsp+150h+var_F0]; this
0x18002ce6b  call    ??1SummaryEvent@WaasMedic@@QEAA@XZ; WaasMedic::SummaryEvent::~SummaryEvent(void)
0x18002ce70  nop
0x18002ce71  test    rdi, rdi
0x18002ce74  jz      short loc_18002CE86
0x18002ce76  mov     rax, [rdi]
0x18002ce79  mov     rcx, rdi
0x18002ce7c  mov     rax, [rax+10h]
0x18002ce80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce85  nop
0x18002ce86  jmp     loc_18002CDB5
0x18002ce8b  lea     rcx, [rsp+150h+var_100]
0x18002ce90  call    ?CreateInstance@StateProvider@WaasMedic@@SAJAEAV?$unique_ptr@VIStateProvider@WaasMedic@@U?$default_delete@VIStateProvider@WaasMedic@@@std@@@std@@@Z; WaasMedic::StateProvider::CreateInstance(std::unique_ptr<WaasMedic::IStateProvider> &)
0x18002ce95  mov     ebx, eax
0x18002ce97  test    eax, eax
0x18002ce99  jns     short loc_18002CF13
0x18002ce9b  mov     rcx, [rbp+58h]; this
0x18002ce9f  lea     rax, aFailedToCreate_3; "Failed to CreateInstance for State prov"...
0x18002cea6  mov     qword ptr [rsp+150h+var_130], rax; int
0x18002ceab  mov     r9d, ebx; char *
0x18002ceae  lea     r8, aOnecoreEnduser_22; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18002ceb5  mov     edx, 8Ah; void *
0x18002ceba  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002cebf  nop
0x18002cec0  lea     rcx, [rsp+150h+pvarg]; pvarg
0x18002cec5  call    cs:__imp_VariantClear
0x18002cecb  test    eax, eax
0x18002cecd  js      loc_18002D0E8
0x18002ced3  mov     rcx, [rsp+150h+var_100]
0x18002ced8  test    rcx, rcx
0x18002cedb  jz      short loc_18002CEEE
0x18002cedd  mov     rax, [rcx]
0x18002cee0  mov     edx, 1
0x18002cee5  mov     rax, [rax]
0x18002cee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ceed  nop
0x18002ceee  lea     rcx, [rsp+150h+var_F0]; this
0x18002cef3  call    ??1SummaryEvent@WaasMedic@@QEAA@XZ; WaasMedic::SummaryEvent::~SummaryEvent(void)
0x18002cef8  nop
0x18002cef9  test    rdi, rdi
0x18002cefc  jz      short loc_18002CF0E
0x18002cefe  mov     rax, [rdi]
0x18002cf01  mov     rcx, rdi
0x18002cf04  mov     rax, [rax+10h]
0x18002cf08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cf0d  nop
0x18002cf0e  jmp     loc_18002CDB5
0x18002cf13  mov     rbx, [rsp+150h+var_100]
0x18002cf18  mov     rax, [rbx]
0x18002cf1b  lea     r9, [rsp+150h+pvarg]
0x18002cf20  lea     r8, aFeatureassessm; "FeatureAssessmentImpactLevel"
0x18002cf27  xor     edx, edx
0x18002cf29  mov     rcx, rbx
0x18002cf2c  mov     rax, [rax+10h]
0x18002cf30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cf35  mov     esi, eax
0x18002cf37  test    eax, eax
0x18002cf39  jns     short loc_18002CFAA
0x18002cf3b  mov     r9d, eax
0x18002cf3e  lea     r8, aFeatureassessm; "FeatureAssessmentImpactLevel"
0x18002cf45  lea     rdx, aErrorEncounter_9; "Error encountered when reading %s! hr=0"...
0x18002cf4c  mov     ecx, 2; unsigned __int8
0x18002cf51  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002cf56  nop
0x18002cf57  lea     rcx, [rsp+150h+pvarg]; pvarg
0x18002cf5c  call    cs:__imp_VariantClear
0x18002cf62  test    eax, eax
0x18002cf64  js      loc_18002D0F0
0x18002cf6a  test    rbx, rbx
0x18002cf6d  jz      short loc_18002CF83
0x18002cf6f  mov     rax, [rbx]
0x18002cf72  mov     edx, 1
0x18002cf77  mov     rcx, rbx
0x18002cf7a  mov     rax, [rax]
0x18002cf7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cf82  nop
0x18002cf83  lea     rcx, [rsp+150h+var_F0]; this
0x18002cf88  call    ??1SummaryEvent@WaasMedic@@QEAA@XZ; WaasMedic::SummaryEvent::~SummaryEvent(void)
0x18002cf8d  nop
0x18002cf8e  test    rdi, rdi
0x18002cf91  jz      short loc_18002CFA3
0x18002cf93  mov     rax, [rdi]
0x18002cf96  mov     rcx, rdi
0x18002cf99  mov     rax, [rax+10h]
0x18002cf9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cfa2  nop
0x18002cfa3  mov     eax, esi
0x18002cfa5  jmp     loc_18002D0AC
0x18002cfaa  xor     esi, esi
0x18002cfac  cmp     word ptr [rsp+150h+pvarg], 13h
0x18002cfb2  cmovz   esi, dword ptr [rsp+150h+pvarg+8]
0x18002cfb7  mov     rax, [rbx]
0x18002cfba  lea     r9, [rsp+150h+pvarg]
0x18002cfbf  lea     r8, aQualityassessm_0; "QualityAssessmentImpactLevel"
0x18002cfc6  xor     edx, edx
0x18002cfc8  mov     rcx, rbx
0x18002cfcb  mov     rax, [rax+10h]
0x18002cfcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cfd4  mov     r15d, eax
0x18002cfd7  test    eax, eax
0x18002cfd9  jns     short loc_18002D048
0x18002cfdb  mov     r9d, eax
0x18002cfde  lea     r8, aQualityassessm_0; "QualityAssessmentImpactLevel"
0x18002cfe5  lea     rdx, aErrorEncounter_9; "Error encountered when reading %s! hr=0"...
0x18002cfec  mov     ecx, 2; unsigned __int8
0x18002cff1  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002cff6  nop
0x18002cff7  lea     rcx, [rsp+150h+pvarg]; pvarg
0x18002cffc  call    cs:__imp_VariantClear
0x18002d002  test    eax, eax
0x18002d004  js      loc_18002D0F8
0x18002d00a  test    rbx, rbx
0x18002d00d  jz      short loc_18002D023
0x18002d00f  mov     rax, [rbx]
0x18002d012  mov     edx, 1
0x18002d017  mov     rcx, rbx
0x18002d01a  mov     rax, [rax]
0x18002d01d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d022  nop
0x18002d023  lea     rcx, [rsp+150h+var_F0]; this
0x18002d028  call    ??1SummaryEvent@WaasMedic@@QEAA@XZ; WaasMedic::SummaryEvent::~SummaryEvent(void)
0x18002d02d  nop
0x18002d02e  test    rdi, rdi
0x18002d031  jz      short loc_18002D043
0x18002d033  mov     rax, [rdi]
0x18002d036  mov     rcx, rdi
0x18002d039  mov     rax, [rax+10h]
0x18002d03d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d042  nop
0x18002d043  mov     eax, r15d
0x18002d046  jmp     short loc_18002D0AC
0x18002d048  xor     eax, eax
0x18002d04a  cmp     word ptr [rsp+150h+pvarg], 13h
0x18002d050  cmovz   eax, dword ptr [rsp+150h+pvarg+8]
0x18002d055  cmp     esi, eax
0x18002d057  cmovle  esi, eax
0x18002d05a  test    esi, esi
0x18002d05c  jnz     short loc_18002D062
0x18002d05e  mov     byte ptr [r14], 1
0x18002d062  lea     rcx, [rsp+150h+pvarg]; pvarg
0x18002d067  call    cs:__imp_VariantClear
0x18002d06d  test    eax, eax
0x18002d06f  js      short loc_18002D0C8
0x18002d071  test    rbx, rbx
0x18002d074  jz      short loc_18002D08A
0x18002d076  mov     rax, [rbx]
0x18002d079  mov     edx, 1
0x18002d07e  mov     rcx, rbx
0x18002d081  mov     rax, [rax]
0x18002d084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d089  nop
0x18002d08a  lea     rcx, [rsp+150h+var_F0]; this
0x18002d08f  call    ??1SummaryEvent@WaasMedic@@QEAA@XZ; WaasMedic::SummaryEvent::~SummaryEvent(void)
0x18002d094  nop
0x18002d095  test    rdi, rdi
0x18002d098  jz      short loc_18002D0AA
0x18002d09a  mov     rax, [rdi]
0x18002d09d  mov     rcx, rdi
0x18002d0a0  mov     rax, [rax+10h]
0x18002d0a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d0a9  nop
0x18002d0aa  xor     eax, eax
0x18002d0ac  mov     rcx, [rbp+50h+var_40]
0x18002d0b0  xor     rcx, rsp; StackCookie
0x18002d0b3  call    __security_check_cookie
0x18002d0b8  add     rsp, 128h
0x18002d0bf  pop     r15
0x18002d0c1  pop     r14
0x18002d0c3  pop     rdi
0x18002d0c4  pop     rsi
0x18002d0c5  pop     rbx
0x18002d0c6  pop     rbp
0x18002d0c7  retn
0x18002d0c8  mov     ecx, eax; int
0x18002d0ca  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18002d0d0  mov     ecx, eax; int
0x18002d0d2  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18002d0d8  mov     ecx, eax; int
0x18002d0da  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18002d0e0  mov     ecx, eax; int
0x18002d0e2  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18002d0e8  mov     ecx, eax; int
0x18002d0ea  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18002d0f0  mov     ecx, eax; int
0x18002d0f2  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18002d0f8  mov     ecx, eax; int
0x18002d0fa  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
