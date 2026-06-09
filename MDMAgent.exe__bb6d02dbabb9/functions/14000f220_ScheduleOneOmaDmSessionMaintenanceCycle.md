# ScheduleOneOmaDmSessionMaintenanceCycle

- ea: `0x14000f220`
- end: `0x14000f5fc`
- name: `ScheduleOneOmaDmSessionMaintenanceCycle`
- size: `988`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, unsigned __int16 *@<rdx>, int, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x14000ec7c`

## callees

- `0x1400029e4`
- `0x14000476c`
- `0x140004cd0`
- `0x140009170`
- `0x140009268`
- `0x1400094e4`
- `0x14000a51c`
- `0x14000f220`
- `0x14001848c`
- `0x140018890`
- `0x14001a010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000f3a3`
- `OLEAUT32!__imp_SysFreeString` at `0x14000f4e6`
- `OLEAUT32!__imp_SysFreeString` at `0x14000f3a3`
- `OLEAUT32!__imp_SysFreeString` at `0x14000f4e6`
- `OLEAUT32!__imp_VariantInit` at `0x14000f3f0`
- `OLEAUT32!__imp_VariantInit` at `0x14000f409`
- `OLEAUT32!__imp_VariantInit` at `0x14000f424`
- `OLEAUT32!__imp_VariantInit` at `0x14000f3f0`
- `OLEAUT32!__imp_VariantInit` at `0x14000f409`
- `OLEAUT32!__imp_VariantInit` at `0x14000f424`

## string_xrefs

- `0x14000f2aa`: `%windir%\system32\deviceenroller.exe `

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
         (LPVOID *)v35,
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
0x14000f220  mov     rax, rsp
0x14000f223  mov     [rax+18h], r8
0x14000f227  push    rbp
0x14000f228  push    rbx
0x14000f229  push    rsi
0x14000f22a  push    rdi
0x14000f22b  push    r14
0x14000f22d  push    r15
0x14000f22f  lea     rbp, [rax-108h]
0x14000f236  sub     rsp, 1D8h
0x14000f23d  xor     r15d, r15d
0x14000f240  movaps  xmmword ptr [rax-48h], xmm6
0x14000f244  movaps  xmmword ptr [rax-58h], xmm7
0x14000f248  lea     r8, [rsp+200h+var_188]; int
0x14000f24d  movaps  xmmword ptr [rax-68h], xmm8
0x14000f252  mov     rsi, rcx
0x14000f255  movaps  xmmword ptr [rax-78h], xmm9
0x14000f25a  lea     rcx, [rbp+100h+var_170]; int
0x14000f25e  mov     [rsp+200h+Data], r15d; Data
0x14000f263  movaps  xmmword ptr [rax-88h], xmm10
0x14000f26b  movaps  xmmword ptr [rax-98h], xmm11
0x14000f273  lea     rax, aScheduleoneoma_1; "ScheduleOneOmaDmSessionMaintenanceCycle"
0x14000f27a  mov     [rbp+100h+var_148], rax
0x14000f27e  lea     rax, [rbp+100h+arg_28]
0x14000f285  mov     [rbp+100h+var_140], rax
0x14000f289  lea     eax, [r15+1]
0x14000f28d  mov     [rsp+200h+var_1A8], eax; int
0x14000f291  mov     [rsp+200h+var_1B0], eax; int
0x14000f295  mov     [rsp+200h+var_1B8], eax; int
0x14000f299  lea     rax, aS1518; "S-1-5-18"
0x14000f2a0  mov     [rsp+200h+var_1C0], r15d; int
0x14000f2a5  mov     [rsp+200h+var_1C8], rax; unsigned __int16 *
0x14000f2aa  lea     rax, aWindirSystem32_1; "%windir%\\system32\\deviceenroller.exe "
0x14000f2b1  mov     [rsp+200h+var_1D0], r9; unsigned __int16 *
0x14000f2b6  lea     r9, [rbp+100h+arg_20]; int
0x14000f2bd  mov     [rsp+200h+var_1D8], rax; unsigned __int16 *
0x14000f2c2  mov     [rsp+200h+var_1E0], rdx; unsigned __int16 *
0x14000f2c7  lea     rdx, [rbp+100h+var_180]; int
0x14000f2cb  mov     [rbp+100h+arg_28], r15d
0x14000f2d2  mov     qword ptr [rbp+100h+var_170], r15
0x14000f2d6  mov     qword ptr [rbp+100h+var_180], r15
0x14000f2da  mov     qword ptr [rsp+200h+var_188], r15
0x14000f2df  mov     [rbp+100h+arg_20], r15
0x14000f2e6  mov     [rbp+100h+var_150], r15
0x14000f2ea  mov     [rbp+100h+var_158], r15
0x14000f2ee  mov     [rbp+100h+var_160], r15
0x14000f2f2  mov     [rbp+100h+var_178], r15
0x14000f2f6  mov     [rbp+100h+var_168], r15
0x14000f2fa  mov     [rbp+100h+arg_10], r15
0x14000f301  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x14000f306  mov     [rbp+100h+arg_28], eax
0x14000f30c  test    eax, eax
0x14000f30e  js      loc_14000F557
0x14000f314  mov     rcx, [rbp+100h+arg_20]
0x14000f31b  lea     rdx, [rbp+100h+arg_10]
0x14000f322  mov     rax, [rcx]
0x14000f325  mov     rax, [rax+1A8h]
0x14000f32c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f331  mov     [rbp+100h+arg_28], eax
0x14000f337  test    eax, eax
0x14000f339  js      loc_14000F557
0x14000f33f  mov     rbx, [rbp+100h+arg_10]
0x14000f346  lea     rdx, aP1d; "P1D"
0x14000f34d  lea     rcx, [rsp+200h+Block]; this
0x14000f352  mov     rax, [rbx]
0x14000f355  mov     rdi, [rax+38h]
0x14000f359  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x14000f35e  mov     rdx, [rax]
0x14000f361  test    rdx, rdx
0x14000f364  jz      short loc_14000F36B
0x14000f366  mov     rdx, [rdx]
0x14000f369  jmp     short loc_14000F36E
0x14000f36b  mov     rdx, r15
0x14000f36e  mov     rcx, rbx
0x14000f371  mov     rax, rdi
0x14000f374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f379  mov     rbx, [rsp+200h+Block]
0x14000f37e  mov     [rbp+100h+arg_28], eax
0x14000f384  test    rbx, rbx
0x14000f387  jz      short loc_14000F3D1
0x14000f389  or      eax, 0FFFFFFFFh
0x14000f38c  lock xadd [rbx+10h], eax
0x14000f391  cmp     eax, 1
0x14000f394  jnz     short loc_14000F3D1
0x14000f396  test    rbx, rbx
0x14000f399  jz      short loc_14000F3D1
0x14000f39b  mov     rcx, [rbx]; bstrString
0x14000f39e  test    rcx, rcx
0x14000f3a1  jz      short loc_14000F3B2
0x14000f3a3  call    cs:__imp_SysFreeString
0x14000f3aa  nop     dword ptr [rax+rax+00h]
0x14000f3af  mov     [rbx], r15
0x14000f3b2  mov     rcx, [rbx+8]; Block
0x14000f3b6  test    rcx, rcx
0x14000f3b9  jz      short loc_14000F3C4
0x14000f3bb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000f3c0  mov     [rbx+8], r15
0x14000f3c4  mov     edx, 18h
0x14000f3c9  mov     rcx, rbx; Block
0x14000f3cc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000f3d1  cmp     [rbp+100h+arg_28], r15d
0x14000f3d8  jl      loc_14000F557
0x14000f3de  mov     rbx, qword ptr [rbp+100h+var_180]
0x14000f3e2  lea     rcx, [rbp+100h+pvarg]; pvarg
0x14000f3e6  mov     rax, [rbx]
0x14000f3e9  mov     r14, [rax+88h]
0x14000f3f0  call    cs:__imp_VariantInit
0x14000f3f7  nop     dword ptr [rax+rax+00h]
0x14000f3fc  movups  xmm6, xmmword ptr [rbp+100h+pvarg]
0x14000f400  lea     rcx, [rbp+100h+var_120]; pvarg
0x14000f404  movsd   xmm7, qword ptr [rbp+100h+pvarg+10h]
0x14000f409  call    cs:__imp_VariantInit
0x14000f410  nop     dword ptr [rax+rax+00h]
0x14000f415  movups  xmm8, xmmword ptr [rbp+100h+var_120]
0x14000f41a  lea     rcx, [rbp+100h+var_138]; pvarg
0x14000f41e  movsd   xmm9, qword ptr [rbp+100h+var_120+10h]
0x14000f424  call    cs:__imp_VariantInit
0x14000f42b  nop     dword ptr [rax+rax+00h]
0x14000f430  movups  xmm10, xmmword ptr [rbp+100h+var_138]
0x14000f435  lea     rcx, [rsp+200h+Block]; this
0x14000f43a  mov     rdi, qword ptr [rsp+200h+var_188]
0x14000f43f  movsd   xmm11, qword ptr [rbp+100h+var_138+10h]
0x14000f445  mov     rdx, rsi; unsigned __int16 *
0x14000f448  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14000f44d  mov     rdx, [rax]
0x14000f450  test    rdx, rdx
0x14000f453  jz      short loc_14000F45A
0x14000f455  mov     rdx, [rdx]
0x14000f458  jmp     short loc_14000F45D
0x14000f45a  mov     rdx, r15
0x14000f45d  lea     rax, [rbp+100h+var_178]
0x14000f461  movaps  [rbp+100h+var_F0], xmm6
0x14000f465  mov     qword ptr [rsp+200h+var_1C0], rax
0x14000f46a  mov     r9d, 6
0x14000f470  lea     rax, [rbp+100h+var_F0]
0x14000f474  movsd   [rbp+100h+var_E0], xmm7
0x14000f479  mov     [rsp+200h+var_1C8], rax
0x14000f47e  mov     r8, rdi
0x14000f481  lea     rax, [rbp+100h+var_D0]
0x14000f485  mov     dword ptr [rsp+200h+var_1D0], 3
0x14000f48d  mov     [rsp+200h+var_1D8], rax
0x14000f492  mov     rcx, rbx
0x14000f495  lea     rax, [rbp+100h+var_B0]
0x14000f499  movaps  [rbp+100h+var_D0], xmm8
0x14000f49e  mov     [rsp+200h+var_1E0], rax
0x14000f4a3  mov     rax, r14
0x14000f4a6  movsd   [rbp+100h+var_C0], xmm9
0x14000f4ac  movaps  [rbp+100h+var_B0], xmm10
0x14000f4b1  movsd   [rbp+100h+var_A0], xmm11
0x14000f4b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f4bc  mov     rbx, [rsp+200h+Block]
0x14000f4c1  mov     [rbp+100h+arg_28], eax
0x14000f4c7  test    rbx, rbx
0x14000f4ca  jz      short loc_14000F519
0x14000f4cc  or      eax, 0FFFFFFFFh
0x14000f4cf  lock xadd [rbx+10h], eax
0x14000f4d4  cmp     eax, 1
0x14000f4d7  jnz     short loc_14000F514
0x14000f4d9  test    rbx, rbx
0x14000f4dc  jz      short loc_14000F514
0x14000f4de  mov     rcx, [rbx]; bstrString
0x14000f4e1  test    rcx, rcx
0x14000f4e4  jz      short loc_14000F4F5
0x14000f4e6  call    cs:__imp_SysFreeString
0x14000f4ed  nop     dword ptr [rax+rax+00h]
0x14000f4f2  mov     [rbx], r15
0x14000f4f5  mov     rcx, [rbx+8]; Block
0x14000f4f9  test    rcx, rcx
0x14000f4fc  jz      short loc_14000F507
0x14000f4fe  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000f503  mov     [rbx+8], r15
0x14000f507  mov     edx, 18h
0x14000f50c  mov     rcx, rbx; Block
0x14000f50f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000f514  mov     [rsp+200h+Block], r15
0x14000f519  lea     rcx, [rbp+100h+var_138]; pvarg
0x14000f51d  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000f522  lea     rcx, [rbp+100h+var_120]; pvarg
0x14000f526  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000f52b  lea     rcx, [rbp+100h+pvarg]; pvarg
0x14000f52f  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000f534  cmp     [rbp+100h+arg_28], r15d
0x14000f53b  jge     short loc_14000F557
0x14000f53d  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x14000f542  mov     edx, [rbp+100h+arg_28]; int
0x14000f548  lea     r8, aScheduleoneoma_1; "ScheduleOneOmaDmSessionMaintenanceCycle"
0x14000f54f  mov     rcx, rax; this
0x14000f552  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x14000f557  mov     ebx, [rbp+100h+arg_28]
0x14000f55d  lea     rcx, [rbp+100h+arg_10]
0x14000f564  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000f569  lea     rcx, [rbp+100h+var_168]
0x14000f56d  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000f572  lea     rcx, [rbp+100h+var_178]
0x14000f576  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000f57b  lea     rcx, [rbp+100h+var_160]
0x14000f57f  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000f584  lea     rcx, [rbp+100h+var_158]
0x14000f588  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000f58d  lea     rcx, [rbp+100h+var_150]
0x14000f591  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000f596  lea     rcx, [rbp+100h+arg_20]
0x14000f59d  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000f5a2  lea     rcx, [rsp+200h+var_188]
0x14000f5a7  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000f5ac  lea     rcx, [rbp+100h+var_180]
0x14000f5b0  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000f5b5  lea     rcx, [rbp+100h+var_170]
0x14000f5b9  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000f5be  lea     rcx, [rbp+100h+var_148]; this
0x14000f5c2  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x14000f5c7  lea     r11, [rsp+200h+var_28]
0x14000f5cf  mov     eax, ebx
0x14000f5d1  movaps  xmm6, xmmword ptr [r11-18h]
0x14000f5d6  movaps  xmm7, xmmword ptr [r11-28h]
0x14000f5db  movaps  xmm8, xmmword ptr [r11-38h]
0x14000f5e0  movaps  xmm9, xmmword ptr [r11-48h]
0x14000f5e5  movaps  xmm10, xmmword ptr [r11-58h]
0x14000f5ea  movaps  xmm11, xmmword ptr [r11-68h]
0x14000f5ef  mov     rsp, r11
0x14000f5f2  pop     r15
0x14000f5f4  pop     r14
0x14000f5f6  pop     rdi
0x14000f5f7  pop     rsi
0x14000f5f8  pop     rbx
0x14000f5f9  pop     rbp
0x14000f5fa  retn
```
