# ScheduleProvisioningInitiatedSyncHelper

- ea: `0x14000ef04`
- end: `0x14000f1f0`
- name: `ScheduleProvisioningInitiatedSyncHelper`
- size: `748`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x14000e128`

## callees

- `0x140002930`
- `0x140002954`
- `0x1400046a4`
- `0x140004c34`
- `0x140007368`
- `0x140008dc8`
- `0x140008e48`
- `0x1400090fc`
- `0x14000a0b8`
- `0x14000ef04`
- `0x1400177b0`
- `0x140017ba0`
- `0x140019010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000f107`
- `OLEAUT32!__imp_SysFreeString` at `0x14000f107`
- `OLEAUT32!__imp_VariantInit` at `0x14000f022`
- `OLEAUT32!__imp_VariantInit` at `0x14000f035`
- `OLEAUT32!__imp_VariantInit` at `0x14000f022`
- `OLEAUT32!__imp_VariantInit` at `0x14000f035`

## string_xrefs

- `0x14000efec`: `%windir%\system32\deviceenroller.exe `

## pseudocode

```c
__int64 __fastcall ScheduleProvisioningInitiatedSyncHelper(unsigned __int16 *a1)
{
  int v2; // ebx
  __int64 v3; // rbx
  __int64 (__fastcall *v4)(__int64, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *); // rsi
  __int128 v5; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  __int128 v7; // xmm8
  IRecordInfo *v8; // xmm9_8
  _variant_t *v9; // rax
  __int64 v10; // rdi
  __int128 v11; // xmm10
  __int64 v12; // xmm11_8
  _bstr_t *v13; // rax
  __int64 v14; // rdx
  int v15; // eax
  BSTR *v16; // rbx
  BSTR v17; // rcx
  CEnrollmentLogger *Logger; // rax
  int v20[2]; // [rsp+78h] [rbp-90h] BYREF
  int v21[2]; // [rsp+80h] [rbp-88h] BYREF
  int v22[2]; // [rsp+88h] [rbp-80h] BYREF
  void *Block; // [rsp+90h] [rbp-78h] BYREF
  __int64 v24; // [rsp+98h] [rbp-70h] BYREF
  int v25[2]; // [rsp+A0h] [rbp-68h] BYREF
  int v26[2]; // [rsp+A8h] [rbp-60h] BYREF
  _QWORD v27[2]; // [rsp+B8h] [rbp-50h] BYREF
  VARIANTARG v28; // [rsp+C8h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+E0h] [rbp-28h] BYREF
  __int128 v30; // [rsp+F8h] [rbp-10h] BYREF
  IRecordInfo *v31; // [rsp+108h] [rbp+0h]
  __int128 v32; // [rsp+118h] [rbp+10h] BYREF
  IRecordInfo *v33; // [rsp+128h] [rbp+20h]
  __int128 v34; // [rsp+138h] [rbp+30h] BYREF
  __int64 v35; // [rsp+148h] [rbp+40h]
  VARIANTARG v36; // [rsp+158h] [rbp+50h] BYREF
  unsigned __int16 v37[264]; // [rsp+178h] [rbp+70h] BYREF

  *(_QWORD *)v26 = 0;
  *(_QWORD *)v22 = 0;
  *(_QWORD *)v21 = 0;
  *(_QWORD *)v25 = 0;
  v24 = 0;
  v2 = StringCchPrintfW(v37, 0x104u, L"/c /ProvInitiatedSession /o \"%s\"", a1);
  v20[0] = v2;
  v27[1] = v20;
  v27[0] = "ScheduleProvisioningInitiatedSyncHelper";
  if ( v2 >= 0 )
  {
    v20[0] = CreateTask(
               v26,
               (__int64)v22,
               v21,
               v25,
               a1,
               L"%windir%\\system32\\deviceenroller.exe ",
               v37,
               L"S-1-5-18",
               0,
               1,
               0,
               0,
               0);
    v2 = v20[0];
    if ( v20[0] >= 0 )
    {
      v3 = *(_QWORD *)v22;
      v4 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))(**(_QWORD **)v22 + 136LL);
      VariantInit(&pvarg);
      v5 = *(_OWORD *)&pvarg.vt;
      pRecInfo = pvarg.pRecInfo;
      VariantInit(&v28);
      v7 = *(_OWORD *)&v28.vt;
      v8 = v28.pRecInfo;
      v9 = _variant_t::_variant_t((_variant_t *)&v36, L"S-1-5-18");
      v10 = *(_QWORD *)v21;
      v11 = *(_OWORD *)v9;
      v12 = *((_QWORD *)v9 + 2);
      v13 = _bstr_t::_bstr_t((_bstr_t *)&Block, L"Provisioning initiated session");
      if ( *(_QWORD *)v13 )
        v14 = **(_QWORD **)v13;
      else
        v14 = 0;
      v30 = v5;
      v31 = pRecInfo;
      v32 = v7;
      v33 = v8;
      v34 = v11;
      v35 = v12;
      v15 = v4(v3, v14, v10, 6, &v34, &v32, 3, &v30, &v24);
      v16 = (BSTR *)Block;
      v20[0] = v15;
      if ( Block )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v16 )
        {
          if ( *v16 )
          {
            SysFreeString(*v16);
            *v16 = 0;
          }
          v17 = v16[1];
          if ( v17 )
          {
            operator delete(v17);
            v16[1] = 0;
          }
          operator delete(v16);
        }
        Block = 0;
      }
      ATL::CComVariant::~CComVariant(&v36);
      ATL::CComVariant::~CComVariant(&v28);
      ATL::CComVariant::~CComVariant(&pvarg);
      v2 = v20[0];
      if ( v20[0] < 0 )
      {
        Logger = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(Logger, v20[0], "ScheduleProvisioningInitiatedSyncHelper");
        v2 = v20[0];
      }
    }
  }
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v27);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v24);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(v25);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(v21);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(v22);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(v26);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14000ef04  mov     rax, rsp
0x14000ef07  mov     [rax+10h], rbx
0x14000ef0b  mov     [rax+18h], rsi
0x14000ef0f  push    rbp
0x14000ef10  push    rdi
0x14000ef11  push    r12
0x14000ef13  push    r14
0x14000ef15  push    r15
0x14000ef17  lea     rbp, [rax-318h]
0x14000ef1e  sub     rsp, 3F0h
0x14000ef25  movaps  xmmword ptr [rax-38h], xmm6
0x14000ef29  movaps  xmmword ptr [rax-48h], xmm7
0x14000ef2d  movaps  xmmword ptr [rax-58h], xmm8
0x14000ef32  movaps  xmmword ptr [rax-68h], xmm9
0x14000ef37  movaps  xmmword ptr [rax-78h], xmm10
0x14000ef3c  movaps  xmmword ptr [rax-88h], xmm11
0x14000ef44  mov     rax, cs:__security_cookie
0x14000ef4b  xor     rax, rsp
0x14000ef4e  mov     [rbp+310h+var_90], rax
0x14000ef55  xor     r14d, r14d
0x14000ef58  lea     r8, aCProvinitiated; "/c /ProvInitiatedSession /o \"%s\""
0x14000ef5f  mov     rdi, rcx
0x14000ef62  mov     qword ptr [rbp+310h+var_370], r14
0x14000ef66  mov     r9, rcx
0x14000ef69  mov     qword ptr [rbp+310h+var_390], r14
0x14000ef6d  lea     rcx, [rbp+310h+var_2A0]; unsigned __int16 *
0x14000ef71  mov     qword ptr [rsp+410h+var_398], r14
0x14000ef76  mov     edx, 104h; unsigned __int64
0x14000ef7b  mov     qword ptr [rbp+310h+var_378], r14
0x14000ef7f  mov     [rbp+310h+var_380], r14
0x14000ef83  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000ef88  mov     ebx, eax
0x14000ef8a  mov     [rsp+410h+var_3A0], eax
0x14000ef8e  lea     rax, [rsp+410h+var_3A0]
0x14000ef93  mov     [rbp+310h+var_358], rax
0x14000ef97  lea     r15, aScheduleprovis; "ScheduleProvisioningInitiatedSyncHelper"
0x14000ef9e  mov     [rbp+310h+var_360], r15
0x14000efa2  test    ebx, ebx
0x14000efa4  js      loc_14000F16E
0x14000efaa  mov     [rsp+410h+Data], r14d; Data
0x14000efaf  lea     rax, [rbp+310h+var_2A0]
0x14000efb3  mov     [rsp+410h+var_3B8], r14d; int
0x14000efb8  lea     r12, aS1518; "S-1-5-18"
0x14000efbf  mov     [rsp+410h+var_3C0], r14d; int
0x14000efc4  lea     r9, [rbp+310h+var_378]; int
0x14000efc8  mov     [rsp+410h+var_3C8], 1; int
0x14000efd0  lea     r8, [rsp+410h+var_398]; int
0x14000efd5  mov     [rsp+410h+var_3D0], r14d; int
0x14000efda  lea     rdx, [rbp+310h+var_390]; int
0x14000efde  mov     [rsp+410h+var_3D8], r12; unsigned __int16 *
0x14000efe3  lea     rcx, [rbp+310h+var_370]; int
0x14000efe7  mov     [rsp+410h+var_3E0], rax; unsigned __int16 *
0x14000efec  lea     rax, aWindirSystem32_1; "%windir%\\system32\\deviceenroller.exe "
0x14000eff3  mov     [rsp+410h+var_3E8], rax; unsigned __int16 *
0x14000eff8  mov     [rsp+410h+var_3F0], rdi; unsigned __int16 *
0x14000effd  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x14000f002  mov     [rsp+410h+var_3A0], eax
0x14000f006  mov     ebx, eax
0x14000f008  test    eax, eax
0x14000f00a  js      loc_14000F16E
0x14000f010  mov     rbx, qword ptr [rbp+310h+var_390]
0x14000f014  lea     rcx, [rbp+310h+pvarg]; pvarg
0x14000f018  mov     rax, [rbx]
0x14000f01b  mov     rsi, [rax+88h]
0x14000f022  call    cs:__imp_VariantInit
0x14000f028  movups  xmm6, xmmword ptr [rbp+310h+pvarg]
0x14000f02c  lea     rcx, [rbp+310h+var_350]; pvarg
0x14000f030  movsd   xmm7, qword ptr [rbp+310h+pvarg+10h]
0x14000f035  call    cs:__imp_VariantInit
0x14000f03b  movups  xmm8, xmmword ptr [rbp+310h+var_350]
0x14000f040  lea     rcx, [rbp+310h+var_2C0]; this
0x14000f044  mov     rdx, r12; unsigned __int16 *
0x14000f047  movsd   xmm9, qword ptr [rbp+310h+var_350+10h]
0x14000f04d  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x14000f052  mov     rdi, qword ptr [rsp+410h+var_398]
0x14000f057  lea     rdx, aProvisioningIn; "Provisioning initiated session"
0x14000f05e  lea     rcx, [rbp+310h+Block]; this
0x14000f062  movups  xmm10, xmmword ptr [rax]
0x14000f066  movsd   xmm11, qword ptr [rax+10h]
0x14000f06c  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14000f071  mov     rdx, [rax]
0x14000f074  test    rdx, rdx
0x14000f077  jz      short loc_14000F07E
0x14000f079  mov     rdx, [rdx]
0x14000f07c  jmp     short loc_14000F081
0x14000f07e  mov     rdx, r14
0x14000f081  lea     rax, [rbp+310h+var_380]
0x14000f085  movaps  [rbp+310h+var_320], xmm6
0x14000f089  mov     qword ptr [rsp+410h+var_3D0], rax
0x14000f08e  mov     r9d, 6
0x14000f094  lea     rax, [rbp+310h+var_320]
0x14000f098  movsd   [rbp+310h+var_310], xmm7
0x14000f09d  mov     [rsp+410h+var_3D8], rax
0x14000f0a2  mov     r8, rdi
0x14000f0a5  lea     rax, [rbp+310h+var_300]
0x14000f0a9  mov     dword ptr [rsp+410h+var_3E0], 3
0x14000f0b1  mov     [rsp+410h+var_3E8], rax
0x14000f0b6  mov     rcx, rbx
0x14000f0b9  lea     rax, [rbp+310h+var_2E0]
0x14000f0bd  movaps  [rbp+310h+var_300], xmm8
0x14000f0c2  mov     [rsp+410h+var_3F0], rax
0x14000f0c7  mov     rax, rsi
0x14000f0ca  movsd   [rbp+310h+var_2F0], xmm9
0x14000f0d0  movaps  [rbp+310h+var_2E0], xmm10
0x14000f0d5  movsd   [rbp+310h+var_2D0], xmm11
0x14000f0db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f0e0  mov     rbx, [rbp+310h+Block]
0x14000f0e4  mov     [rsp+410h+var_3A0], eax
0x14000f0e8  test    rbx, rbx
0x14000f0eb  jz      short loc_14000F133
0x14000f0ed  or      eax, 0FFFFFFFFh
0x14000f0f0  lock xadd [rbx+10h], eax
0x14000f0f5  cmp     eax, 1
0x14000f0f8  jnz     short loc_14000F12F
0x14000f0fa  test    rbx, rbx
0x14000f0fd  jz      short loc_14000F12F
0x14000f0ff  mov     rcx, [rbx]; bstrString
0x14000f102  test    rcx, rcx
0x14000f105  jz      short loc_14000F110
0x14000f107  call    cs:__imp_SysFreeString
0x14000f10d  mov     [rbx], r14
0x14000f110  mov     rcx, [rbx+8]; Block
0x14000f114  test    rcx, rcx
0x14000f117  jz      short loc_14000F122
0x14000f119  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000f11e  mov     [rbx+8], r14
0x14000f122  mov     edx, 18h
0x14000f127  mov     rcx, rbx; Block
0x14000f12a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000f12f  mov     [rbp+310h+Block], r14
0x14000f133  lea     rcx, [rbp+310h+var_2C0]; pvarg
0x14000f137  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000f13c  lea     rcx, [rbp+310h+var_350]; pvarg
0x14000f140  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000f145  lea     rcx, [rbp+310h+pvarg]; pvarg
0x14000f149  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000f14e  mov     ebx, [rsp+410h+var_3A0]
0x14000f152  test    ebx, ebx
0x14000f154  jns     short loc_14000F16E
0x14000f156  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x14000f15b  mov     edx, [rsp+410h+var_3A0]; int
0x14000f15f  mov     r8, r15; char *
0x14000f162  mov     rcx, rax; this
0x14000f165  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x14000f16a  mov     ebx, [rsp+410h+var_3A0]
0x14000f16e  lea     rcx, [rbp+310h+var_360]; this
0x14000f172  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x14000f177  lea     rcx, [rbp+310h+var_380]
0x14000f17b  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000f180  lea     rcx, [rbp+310h+var_378]
0x14000f184  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000f189  lea     rcx, [rsp+410h+var_398]
0x14000f18e  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000f193  lea     rcx, [rbp+310h+var_390]
0x14000f197  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000f19c  lea     rcx, [rbp+310h+var_370]
0x14000f1a0  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000f1a5  mov     eax, ebx
0x14000f1a7  mov     rcx, [rbp+310h+var_90]
0x14000f1ae  xor     rcx, rsp; StackCookie
0x14000f1b1  call    __security_check_cookie
0x14000f1b6  lea     r11, [rsp+410h+var_20]
0x14000f1be  mov     rbx, [r11+38h]
0x14000f1c2  mov     rsi, [r11+40h]
0x14000f1c6  movaps  xmm6, xmmword ptr [r11-10h]
0x14000f1cb  movaps  xmm7, xmmword ptr [r11-20h]
0x14000f1d0  movaps  xmm8, xmmword ptr [r11-30h]
0x14000f1d5  movaps  xmm9, xmmword ptr [r11-40h]
0x14000f1da  movaps  xmm10, xmmword ptr [r11-50h]
0x14000f1df  movaps  xmm11, xmmword ptr [r11-60h]
0x14000f1e4  mov     rsp, r11
0x14000f1e7  pop     r15
0x14000f1e9  pop     r14
0x14000f1eb  pop     r12
0x14000f1ed  pop     rdi
0x14000f1ee  pop     rbp
0x14000f1ef  retn
```
