# ScheduleOneOmaDmSessionMaintenanceCycle

- ea: `0x14000eaa8`
- end: `0x14000ee65`
- name: `ScheduleOneOmaDmSessionMaintenanceCycle`
- size: `957`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, __int64, unsigned __int16 *, __int64, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x14000e530`

## callees

- `0x140002954`
- `0x1400046a4`
- `0x140004c34`
- `0x140008d58`
- `0x140008e48`
- `0x1400090fc`
- `0x14000a0b8`
- `0x14000eaa8`
- `0x1400177b0`
- `0x140017ba0`
- `0x140019010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000ec2b`
- `OLEAUT32!__imp_SysFreeString` at `0x14000ed56`
- `OLEAUT32!__imp_SysFreeString` at `0x14000ec2b`
- `OLEAUT32!__imp_SysFreeString` at `0x14000ed56`
- `OLEAUT32!__imp_VariantInit` at `0x14000ec72`
- `OLEAUT32!__imp_VariantInit` at `0x14000ec85`
- `OLEAUT32!__imp_VariantInit` at `0x14000ec9a`
- `OLEAUT32!__imp_VariantInit` at `0x14000ec72`
- `OLEAUT32!__imp_VariantInit` at `0x14000ec85`
- `OLEAUT32!__imp_VariantInit` at `0x14000ec9a`

## string_xrefs

- `0x14000eb32`: `%windir%\system32\deviceenroller.exe `

## pseudocode

```c
__int64 __fastcall ScheduleOneOmaDmSessionMaintenanceCycle(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 *a4,
        __int64 a5,
        int a6)
{
  __int64 v7; // rbx
  __int64 (__fastcall *v8)(__int64, __int64); // rdi
  _bstr_t *v9; // rax
  __int64 v10; // rdx
  int v11; // eax
  BSTR *v12; // rbx
  BSTR v13; // rcx
  __int64 v14; // rbx
  __int64 (__fastcall *v15)(__int64, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *); // r14
  __int128 v16; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  __int128 v18; // xmm8
  IRecordInfo *v19; // xmm9_8
  __int128 v20; // xmm10
  __int64 v21; // rdi
  IRecordInfo *v22; // xmm11_8
  _bstr_t *v23; // rax
  __int64 v24; // rdx
  int v25; // eax
  BSTR *v26; // rbx
  BSTR v27; // rcx
  CEnrollmentLogger *Logger; // rax
  unsigned int v29; // ebx
  void *Block; // [rsp+78h] [rbp-90h] BYREF
  int v32[2]; // [rsp+80h] [rbp-88h] BYREF
  int v33[2]; // [rsp+88h] [rbp-80h] BYREF
  __int64 v34; // [rsp+90h] [rbp-78h] BYREF
  int v35[2]; // [rsp+98h] [rbp-70h] BYREF
  __int64 v36; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v37; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v38; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v39; // [rsp+B8h] [rbp-50h] BYREF
  _QWORD v40[2]; // [rsp+C0h] [rbp-48h] BYREF
  VARIANTARG v41; // [rsp+D0h] [rbp-38h] BYREF
  VARIANTARG v42; // [rsp+E8h] [rbp-20h] BYREF
  VARIANTARG pvarg; // [rsp+100h] [rbp-8h] BYREF
  __int128 v44; // [rsp+118h] [rbp+10h] BYREF
  IRecordInfo *v45; // [rsp+128h] [rbp+20h]
  __int128 v46; // [rsp+138h] [rbp+30h] BYREF
  IRecordInfo *v47; // [rsp+148h] [rbp+40h]
  __int128 v48; // [rsp+158h] [rbp+50h] BYREF
  IRecordInfo *v49; // [rsp+168h] [rbp+60h]
  __int64 v50; // [rsp+228h] [rbp+120h] BYREF

  v40[0] = "ScheduleOneOmaDmSessionMaintenanceCycle";
  v40[1] = &a6;
  a6 = 0;
  *(_QWORD *)v35 = 0;
  *(_QWORD *)v33 = 0;
  *(_QWORD *)v32 = 0;
  a5 = 0;
  v39 = 0;
  v38 = 0;
  v37 = 0;
  v34 = 0;
  v36 = 0;
  v50 = 0;
  a6 = CreateTask(
         v35,
         (__int64)v33,
         v32,
         &a5,
         a2,
         L"%windir%\\system32\\deviceenroller.exe ",
         a4,
         L"S-1-5-18",
         0,
         1,
         1,
         1,
         0);
  if ( a6 >= 0 )
  {
    a6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a5 + 424LL))(a5, &v50);
    if ( a6 >= 0 )
    {
      v7 = v50;
      v8 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v50 + 56LL);
      v9 = _bstr_t::_bstr_t((_bstr_t *)&Block, "P1D");
      if ( *(_QWORD *)v9 )
        v10 = **(_QWORD **)v9;
      else
        v10 = 0;
      v11 = v8(v7, v10);
      v12 = (BSTR *)Block;
      a6 = v11;
      if ( Block && _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v12 )
      {
        if ( *v12 )
        {
          SysFreeString(*v12);
          *v12 = 0;
        }
        v13 = v12[1];
        if ( v13 )
        {
          operator delete(v13);
          v12[1] = 0;
        }
        operator delete(v12);
      }
      if ( a6 >= 0 )
      {
        v14 = *(_QWORD *)v33;
        v15 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))(**(_QWORD **)v33 + 136LL);
        VariantInit(&pvarg);
        v16 = *(_OWORD *)&pvarg.vt;
        pRecInfo = pvarg.pRecInfo;
        VariantInit(&v42);
        v18 = *(_OWORD *)&v42.vt;
        v19 = v42.pRecInfo;
        VariantInit(&v41);
        v20 = *(_OWORD *)&v41.vt;
        v21 = *(_QWORD *)v32;
        v22 = v41.pRecInfo;
        v23 = _bstr_t::_bstr_t((_bstr_t *)&Block, a1);
        if ( *(_QWORD *)v23 )
          v24 = **(_QWORD **)v23;
        else
          v24 = 0;
        v44 = v16;
        v45 = pRecInfo;
        v46 = v18;
        v47 = v19;
        v48 = v20;
        v49 = v22;
        v25 = v15(v14, v24, v21, 6, &v48, &v46, 3, &v44, &v34);
        v26 = (BSTR *)Block;
        a6 = v25;
        if ( Block )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v26 )
          {
            if ( *v26 )
            {
              SysFreeString(*v26);
              *v26 = 0;
            }
            v27 = v26[1];
            if ( v27 )
            {
              operator delete(v27);
              v26[1] = 0;
            }
            operator delete(v26);
          }
          Block = 0;
        }
        ATL::CComVariant::~CComVariant(&v41);
        ATL::CComVariant::~CComVariant(&v42);
        ATL::CComVariant::~CComVariant(&pvarg);
        if ( a6 < 0 )
        {
          Logger = CEnrollmentLogger::GetLogger();
          CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(Logger, a6, "ScheduleOneOmaDmSessionMaintenanceCycle");
        }
      }
    }
  }
  v29 = a6;
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v50);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v36);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v34);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v37);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v38);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v39);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&a5);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(v32);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(v33);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(v35);
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v40);
  return v29;
}

```

## disassembly

```asm
0x14000eaa8  mov     rax, rsp
0x14000eaab  mov     [rax+18h], r8
0x14000eaaf  push    rbp
0x14000eab0  push    rbx
0x14000eab1  push    rsi
0x14000eab2  push    rdi
0x14000eab3  push    r14
0x14000eab5  push    r15
0x14000eab7  lea     rbp, [rax-108h]
0x14000eabe  sub     rsp, 1D8h
0x14000eac5  xor     r15d, r15d
0x14000eac8  movaps  xmmword ptr [rax-48h], xmm6
0x14000eacc  movaps  xmmword ptr [rax-58h], xmm7
0x14000ead0  lea     r8, [rsp+200h+var_188]; int
0x14000ead5  movaps  xmmword ptr [rax-68h], xmm8
0x14000eada  mov     rsi, rcx
0x14000eadd  movaps  xmmword ptr [rax-78h], xmm9
0x14000eae2  lea     rcx, [rbp+100h+var_170]; int
0x14000eae6  mov     [rsp+200h+Data], r15d; Data
0x14000eaeb  movaps  xmmword ptr [rax-88h], xmm10
0x14000eaf3  movaps  xmmword ptr [rax-98h], xmm11
0x14000eafb  lea     rax, aScheduleoneoma_1; "ScheduleOneOmaDmSessionMaintenanceCycle"
0x14000eb02  mov     [rbp+100h+var_148], rax
0x14000eb06  lea     rax, [rbp+100h+arg_28]
0x14000eb0d  mov     [rbp+100h+var_140], rax
0x14000eb11  lea     eax, [r15+1]
0x14000eb15  mov     [rsp+200h+var_1A8], eax; int
0x14000eb19  mov     [rsp+200h+var_1B0], eax; int
0x14000eb1d  mov     [rsp+200h+var_1B8], eax; int
0x14000eb21  lea     rax, aS1518; "S-1-5-18"
0x14000eb28  mov     [rsp+200h+var_1C0], r15d; int
0x14000eb2d  mov     [rsp+200h+var_1C8], rax; unsigned __int16 *
0x14000eb32  lea     rax, aWindirSystem32_1; "%windir%\\system32\\deviceenroller.exe "
0x14000eb39  mov     [rsp+200h+var_1D0], r9; unsigned __int16 *
0x14000eb3e  lea     r9, [rbp+100h+arg_20]; int
0x14000eb45  mov     [rsp+200h+var_1D8], rax; unsigned __int16 *
0x14000eb4a  mov     [rsp+200h+var_1E0], rdx; unsigned __int16 *
0x14000eb4f  lea     rdx, [rbp+100h+var_180]; int
0x14000eb53  mov     [rbp+100h+arg_28], r15d
0x14000eb5a  mov     qword ptr [rbp+100h+var_170], r15
0x14000eb5e  mov     qword ptr [rbp+100h+var_180], r15
0x14000eb62  mov     qword ptr [rsp+200h+var_188], r15
0x14000eb67  mov     [rbp+100h+arg_20], r15
0x14000eb6e  mov     [rbp+100h+var_150], r15
0x14000eb72  mov     [rbp+100h+var_158], r15
0x14000eb76  mov     [rbp+100h+var_160], r15
0x14000eb7a  mov     [rbp+100h+var_178], r15
0x14000eb7e  mov     [rbp+100h+var_168], r15
0x14000eb82  mov     [rbp+100h+arg_10], r15
0x14000eb89  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x14000eb8e  mov     [rbp+100h+arg_28], eax
0x14000eb94  test    eax, eax
0x14000eb96  js      loc_14000EDC1
0x14000eb9c  mov     rcx, [rbp+100h+arg_20]
0x14000eba3  lea     rdx, [rbp+100h+arg_10]
0x14000ebaa  mov     rax, [rcx]
0x14000ebad  mov     rax, [rax+1A8h]
0x14000ebb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ebb9  mov     [rbp+100h+arg_28], eax
0x14000ebbf  test    eax, eax
0x14000ebc1  js      loc_14000EDC1
0x14000ebc7  mov     rbx, [rbp+100h+arg_10]
0x14000ebce  lea     rdx, aP1d; "P1D"
0x14000ebd5  lea     rcx, [rsp+200h+Block]; this
0x14000ebda  mov     rax, [rbx]
0x14000ebdd  mov     rdi, [rax+38h]
0x14000ebe1  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x14000ebe6  mov     rdx, [rax]
0x14000ebe9  test    rdx, rdx
0x14000ebec  jz      short loc_14000EBF3
0x14000ebee  mov     rdx, [rdx]
0x14000ebf1  jmp     short loc_14000EBF6
0x14000ebf3  mov     rdx, r15
0x14000ebf6  mov     rcx, rbx
0x14000ebf9  mov     rax, rdi
0x14000ebfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ec01  mov     rbx, [rsp+200h+Block]
0x14000ec06  mov     [rbp+100h+arg_28], eax
0x14000ec0c  test    rbx, rbx
0x14000ec0f  jz      short loc_14000EC53
0x14000ec11  or      eax, 0FFFFFFFFh
0x14000ec14  lock xadd [rbx+10h], eax
0x14000ec19  cmp     eax, 1
0x14000ec1c  jnz     short loc_14000EC53
0x14000ec1e  test    rbx, rbx
0x14000ec21  jz      short loc_14000EC53
0x14000ec23  mov     rcx, [rbx]; bstrString
0x14000ec26  test    rcx, rcx
0x14000ec29  jz      short loc_14000EC34
0x14000ec2b  call    cs:__imp_SysFreeString
0x14000ec31  mov     [rbx], r15
0x14000ec34  mov     rcx, [rbx+8]; Block
0x14000ec38  test    rcx, rcx
0x14000ec3b  jz      short loc_14000EC46
0x14000ec3d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000ec42  mov     [rbx+8], r15
0x14000ec46  mov     edx, 18h
0x14000ec4b  mov     rcx, rbx; Block
0x14000ec4e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000ec53  cmp     [rbp+100h+arg_28], r15d
0x14000ec5a  jl      loc_14000EDC1
0x14000ec60  mov     rbx, qword ptr [rbp+100h+var_180]
0x14000ec64  lea     rcx, [rbp+100h+pvarg]; pvarg
0x14000ec68  mov     rax, [rbx]
0x14000ec6b  mov     r14, [rax+88h]
0x14000ec72  call    cs:__imp_VariantInit
0x14000ec78  movups  xmm6, xmmword ptr [rbp+100h+pvarg]
0x14000ec7c  lea     rcx, [rbp+100h+var_120]; pvarg
0x14000ec80  movsd   xmm7, qword ptr [rbp+100h+pvarg+10h]
0x14000ec85  call    cs:__imp_VariantInit
0x14000ec8b  movups  xmm8, xmmword ptr [rbp+100h+var_120]
0x14000ec90  lea     rcx, [rbp+100h+var_138]; pvarg
0x14000ec94  movsd   xmm9, qword ptr [rbp+100h+var_120+10h]
0x14000ec9a  call    cs:__imp_VariantInit
0x14000eca0  movups  xmm10, xmmword ptr [rbp+100h+var_138]
0x14000eca5  lea     rcx, [rsp+200h+Block]; this
0x14000ecaa  mov     rdi, qword ptr [rsp+200h+var_188]
0x14000ecaf  movsd   xmm11, qword ptr [rbp+100h+var_138+10h]
0x14000ecb5  mov     rdx, rsi; unsigned __int16 *
0x14000ecb8  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14000ecbd  mov     rdx, [rax]
0x14000ecc0  test    rdx, rdx
0x14000ecc3  jz      short loc_14000ECCA
0x14000ecc5  mov     rdx, [rdx]
0x14000ecc8  jmp     short loc_14000ECCD
0x14000ecca  mov     rdx, r15
0x14000eccd  lea     rax, [rbp+100h+var_178]
0x14000ecd1  movaps  [rbp+100h+var_F0], xmm6
0x14000ecd5  mov     qword ptr [rsp+200h+var_1C0], rax
0x14000ecda  mov     r9d, 6
0x14000ece0  lea     rax, [rbp+100h+var_F0]
0x14000ece4  movsd   [rbp+100h+var_E0], xmm7
0x14000ece9  mov     [rsp+200h+var_1C8], rax
0x14000ecee  mov     r8, rdi
0x14000ecf1  lea     rax, [rbp+100h+var_D0]
0x14000ecf5  mov     dword ptr [rsp+200h+var_1D0], 3
0x14000ecfd  mov     [rsp+200h+var_1D8], rax
0x14000ed02  mov     rcx, rbx
0x14000ed05  lea     rax, [rbp+100h+var_B0]
0x14000ed09  movaps  [rbp+100h+var_D0], xmm8
0x14000ed0e  mov     [rsp+200h+var_1E0], rax
0x14000ed13  mov     rax, r14
0x14000ed16  movsd   [rbp+100h+var_C0], xmm9
0x14000ed1c  movaps  [rbp+100h+var_B0], xmm10
0x14000ed21  movsd   [rbp+100h+var_A0], xmm11
0x14000ed27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ed2c  mov     rbx, [rsp+200h+Block]
0x14000ed31  mov     [rbp+100h+arg_28], eax
0x14000ed37  test    rbx, rbx
0x14000ed3a  jz      short loc_14000ED83
0x14000ed3c  or      eax, 0FFFFFFFFh
0x14000ed3f  lock xadd [rbx+10h], eax
0x14000ed44  cmp     eax, 1
0x14000ed47  jnz     short loc_14000ED7E
0x14000ed49  test    rbx, rbx
0x14000ed4c  jz      short loc_14000ED7E
0x14000ed4e  mov     rcx, [rbx]; bstrString
0x14000ed51  test    rcx, rcx
0x14000ed54  jz      short loc_14000ED5F
0x14000ed56  call    cs:__imp_SysFreeString
0x14000ed5c  mov     [rbx], r15
0x14000ed5f  mov     rcx, [rbx+8]; Block
0x14000ed63  test    rcx, rcx
0x14000ed66  jz      short loc_14000ED71
0x14000ed68  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000ed6d  mov     [rbx+8], r15
0x14000ed71  mov     edx, 18h
0x14000ed76  mov     rcx, rbx; Block
0x14000ed79  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000ed7e  mov     [rsp+200h+Block], r15
0x14000ed83  lea     rcx, [rbp+100h+var_138]; pvarg
0x14000ed87  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000ed8c  lea     rcx, [rbp+100h+var_120]; pvarg
0x14000ed90  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000ed95  lea     rcx, [rbp+100h+pvarg]; pvarg
0x14000ed99  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000ed9e  cmp     [rbp+100h+arg_28], r15d
0x14000eda5  jge     short loc_14000EDC1
0x14000eda7  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x14000edac  mov     edx, [rbp+100h+arg_28]; int
0x14000edb2  lea     r8, aScheduleoneoma_1; "ScheduleOneOmaDmSessionMaintenanceCycle"
0x14000edb9  mov     rcx, rax; this
0x14000edbc  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x14000edc1  mov     ebx, [rbp+100h+arg_28]
0x14000edc7  lea     rcx, [rbp+100h+arg_10]
0x14000edce  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000edd3  lea     rcx, [rbp+100h+var_168]
0x14000edd7  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000eddc  lea     rcx, [rbp+100h+var_178]
0x14000ede0  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000ede5  lea     rcx, [rbp+100h+var_160]
0x14000ede9  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000edee  lea     rcx, [rbp+100h+var_158]
0x14000edf2  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000edf7  lea     rcx, [rbp+100h+var_150]
0x14000edfb  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000ee00  lea     rcx, [rbp+100h+arg_20]
0x14000ee07  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000ee0c  lea     rcx, [rsp+200h+var_188]
0x14000ee11  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000ee16  lea     rcx, [rbp+100h+var_180]
0x14000ee1a  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000ee1f  lea     rcx, [rbp+100h+var_170]
0x14000ee23  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000ee28  lea     rcx, [rbp+100h+var_148]; this
0x14000ee2c  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x14000ee31  lea     r11, [rsp+200h+var_28]
0x14000ee39  mov     eax, ebx
0x14000ee3b  movaps  xmm6, xmmword ptr [r11-18h]
0x14000ee40  movaps  xmm7, xmmword ptr [r11-28h]
0x14000ee45  movaps  xmm8, xmmword ptr [r11-38h]
0x14000ee4a  movaps  xmm9, xmmword ptr [r11-48h]
0x14000ee4f  movaps  xmm10, xmmword ptr [r11-58h]
0x14000ee54  movaps  xmm11, xmmword ptr [r11-68h]
0x14000ee59  mov     rsp, r11
0x14000ee5c  pop     r15
0x14000ee5e  pop     r14
0x14000ee60  pop     rdi
0x14000ee61  pop     rsi
0x14000ee62  pop     rbx
0x14000ee63  pop     rbp
0x14000ee64  retn
```
