# ScheduleOneOmaDmSessionMaintenanceCycle

- ea: `0x18000e40c`
- end: `0x18000e7e8`
- name: `ScheduleOneOmaDmSessionMaintenanceCycle`
- size: `988`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, __int64, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000de68`

## callees

- `0x180001cc8`
- `0x1800071e8`
- `0x180007258`
- `0x180007364`
- `0x1800077a0`
- `0x1800079e8`
- `0x180008bd4`
- `0x18000e40c`
- `0x18001b9d8`
- `0x18001bde0`
- `0x18001e010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000e58f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e6d2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e58f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e6d2`
- `OLEAUT32!__imp_VariantInit` at `0x18000e5dc`
- `OLEAUT32!__imp_VariantInit` at `0x18000e5f5`
- `OLEAUT32!__imp_VariantInit` at `0x18000e610`
- `OLEAUT32!__imp_VariantInit` at `0x18000e5dc`
- `OLEAUT32!__imp_VariantInit` at `0x18000e5f5`
- `OLEAUT32!__imp_VariantInit` at `0x18000e610`

## string_xrefs

- `0x18000e496`: `%windir%\system32\deviceenroller.exe `

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
  const struct std::nothrow_t *v12; // rdx
  BSTR *v13; // rbx
  BSTR v14; // rcx
  struct IUnknown *v15; // rbx
  ULONG (__stdcall *Release)(IUnknown *); // r14
  __int128 v17; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  __int128 v19; // xmm8
  IRecordInfo *v20; // xmm9_8
  __int128 v21; // xmm10
  __int64 v22; // rdi
  IRecordInfo *v23; // xmm11_8
  _bstr_t *v24; // rax
  __int64 v25; // rdx
  int v26; // eax
  const struct std::nothrow_t *v27; // rdx
  BSTR *v28; // rbx
  BSTR v29; // rcx
  CEnrollmentLogger *Logger; // rax
  unsigned int v31; // ebx
  __int64 v33; // [rsp+48h] [rbp-C0h]
  int v34; // [rsp+68h] [rbp-A0h]
  void *v35; // [rsp+78h] [rbp-90h] BYREF
  __int64 v36; // [rsp+80h] [rbp-88h] BYREF
  struct IUnknown *v37; // [rsp+88h] [rbp-80h] BYREF
  __int64 v38; // [rsp+90h] [rbp-78h] BYREF
  LPVOID v39; // [rsp+98h] [rbp-70h] BYREF
  __int64 v40; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v41; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v42; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v43; // [rsp+B8h] [rbp-50h] BYREF
  _QWORD v44[2]; // [rsp+C0h] [rbp-48h] BYREF
  VARIANTARG v45; // [rsp+D0h] [rbp-38h] BYREF
  VARIANTARG v46; // [rsp+E8h] [rbp-20h] BYREF
  VARIANTARG pvarg; // [rsp+100h] [rbp-8h] BYREF
  __int128 v48; // [rsp+118h] [rbp+10h] BYREF
  IRecordInfo *v49; // [rsp+128h] [rbp+20h]
  __int128 v50; // [rsp+138h] [rbp+30h] BYREF
  IRecordInfo *v51; // [rsp+148h] [rbp+40h]
  __int128 v52; // [rsp+158h] [rbp+50h] BYREF
  IRecordInfo *v53; // [rsp+168h] [rbp+60h]
  __int64 v54; // [rsp+228h] [rbp+120h] BYREF

  v34 = 0;
  v44[0] = "ScheduleOneOmaDmSessionMaintenanceCycle";
  v44[1] = &a6;
  LODWORD(v33) = 0;
  a6 = 0;
  v39 = 0;
  v37 = 0;
  v36 = 0;
  a5 = 0;
  v43 = 0;
  v42 = 0;
  v41 = 0;
  v38 = 0;
  v40 = 0;
  v54 = 0;
  a6 = CreateTask(
         &v39,
         &v37,
         &v36,
         &a5,
         a2,
         L"%windir%\\system32\\deviceenroller.exe ",
         a4,
         L"S-1-5-18",
         v33,
         1,
         1,
         1,
         v34);
  if ( a6 >= 0 )
  {
    a6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a5 + 424LL))(a5, &v54);
    if ( a6 >= 0 )
    {
      v7 = v54;
      v8 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v54 + 56LL);
      v9 = _bstr_t::_bstr_t((_bstr_t *)&v35, "P1D");
      if ( *(_QWORD *)v9 )
        v10 = **(_QWORD **)v9;
      else
        v10 = 0;
      v11 = v8(v7, v10);
      v13 = (BSTR *)v35;
      a6 = v11;
      if ( v35 && _InterlockedExchangeAdd((volatile signed __int32 *)v35 + 4, 0xFFFFFFFF) == 1 && v13 )
      {
        if ( *v13 )
        {
          SysFreeString(*v13);
          *v13 = 0;
        }
        v14 = v13[1];
        if ( v14 )
        {
          operator delete(v14, v12);
          v13[1] = 0;
        }
        operator delete(v13, (const struct std::nothrow_t *)0x18);
      }
      if ( a6 >= 0 )
      {
        v15 = v37;
        Release = v37->lpVtbl[5].Release;
        VariantInit(&pvarg);
        v17 = *(_OWORD *)&pvarg.vt;
        pRecInfo = pvarg.pRecInfo;
        VariantInit(&v46);
        v19 = *(_OWORD *)&v46.vt;
        v20 = v46.pRecInfo;
        VariantInit(&v45);
        v21 = *(_OWORD *)&v45.vt;
        v22 = v36;
        v23 = v45.pRecInfo;
        v24 = _bstr_t::_bstr_t((_bstr_t *)&v35, a1);
        if ( *(_QWORD *)v24 )
          v25 = **(_QWORD **)v24;
        else
          v25 = 0;
        v48 = v17;
        v49 = pRecInfo;
        v50 = v19;
        v51 = v20;
        v52 = v21;
        v53 = v23;
        v26 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))Release)(
                v15,
                v25,
                v22,
                6,
                &v52,
                &v50,
                3,
                &v48,
                &v38);
        v28 = (BSTR *)v35;
        a6 = v26;
        if ( v35 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v35 + 4, 0xFFFFFFFF) == 1 && v28 )
          {
            if ( *v28 )
            {
              SysFreeString(*v28);
              *v28 = 0;
            }
            v29 = v28[1];
            if ( v29 )
            {
              operator delete(v29, v27);
              v28[1] = 0;
            }
            operator delete(v28, (const struct std::nothrow_t *)0x18);
          }
          v35 = 0;
        }
        _variant_t::~_variant_t((_variant_t *)&v45);
        _variant_t::~_variant_t((_variant_t *)&v46);
        _variant_t::~_variant_t((_variant_t *)&pvarg);
        if ( a6 < 0 )
        {
          Logger = CEnrollmentLogger::GetLogger();
          CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(Logger, a6, "ScheduleOneOmaDmSessionMaintenanceCycle");
        }
      }
    }
  }
  v31 = a6;
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v54);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v40);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v38);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v41);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v42);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v43);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&a5);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v36);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v37);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v39);
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v44);
  return v31;
}

```

## disassembly

```asm
0x18000e40c  mov     rax, rsp
0x18000e40f  mov     [rax+18h], r8
0x18000e413  push    rbp
0x18000e414  push    rbx
0x18000e415  push    rsi
0x18000e416  push    rdi
0x18000e417  push    r14
0x18000e419  push    r15
0x18000e41b  lea     rbp, [rax-108h]
0x18000e422  sub     rsp, 1D8h
0x18000e429  xor     r15d, r15d
0x18000e42c  movaps  xmmword ptr [rax-48h], xmm6
0x18000e430  movaps  xmmword ptr [rax-58h], xmm7
0x18000e434  lea     r8, [rsp+200h+var_188]
0x18000e439  movaps  xmmword ptr [rax-68h], xmm8
0x18000e43e  mov     rsi, rcx
0x18000e441  movaps  xmmword ptr [rax-78h], xmm9
0x18000e446  lea     rcx, [rbp+100h+var_170]
0x18000e44a  mov     [rsp+200h+var_1A0], r15d
0x18000e44f  movaps  xmmword ptr [rax-88h], xmm10
0x18000e457  movaps  xmmword ptr [rax-98h], xmm11
0x18000e45f  lea     rax, aScheduleoneoma_1; "ScheduleOneOmaDmSessionMaintenanceCycle"
0x18000e466  mov     [rbp+100h+var_148], rax
0x18000e46a  lea     rax, [rbp+100h+arg_28]
0x18000e471  mov     [rbp+100h+var_140], rax
0x18000e475  lea     eax, [r15+1]
0x18000e479  mov     [rsp+200h+var_1A8], eax
0x18000e47d  mov     [rsp+200h+var_1B0], eax
0x18000e481  mov     [rsp+200h+var_1B8], eax
0x18000e485  lea     rax, aS1518; "S-1-5-18"
0x18000e48c  mov     dword ptr [rsp+200h+var_1C0], r15d
0x18000e491  mov     [rsp+200h+var_1C8], rax
0x18000e496  lea     rax, aWindirSystem32_1; "%windir%\\system32\\deviceenroller.exe "
0x18000e49d  mov     [rsp+200h+var_1D0], r9
0x18000e4a2  lea     r9, [rbp+100h+arg_20]
0x18000e4a9  mov     [rsp+200h+var_1D8], rax
0x18000e4ae  mov     [rsp+200h+var_1E0], rdx
0x18000e4b3  lea     rdx, [rbp+100h+var_180]
0x18000e4b7  mov     [rbp+100h+arg_28], r15d
0x18000e4be  mov     [rbp+100h+var_170], r15
0x18000e4c2  mov     [rbp+100h+var_180], r15
0x18000e4c6  mov     [rsp+200h+var_188], r15
0x18000e4cb  mov     [rbp+100h+arg_20], r15
0x18000e4d2  mov     [rbp+100h+var_150], r15
0x18000e4d6  mov     [rbp+100h+var_158], r15
0x18000e4da  mov     [rbp+100h+var_160], r15
0x18000e4de  mov     [rbp+100h+var_178], r15
0x18000e4e2  mov     [rbp+100h+var_168], r15
0x18000e4e6  mov     [rbp+100h+arg_10], r15
0x18000e4ed  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x18000e4f2  mov     [rbp+100h+arg_28], eax
0x18000e4f8  test    eax, eax
0x18000e4fa  js      loc_18000E743
0x18000e500  mov     rcx, [rbp+100h+arg_20]
0x18000e507  lea     rdx, [rbp+100h+arg_10]
0x18000e50e  mov     rax, [rcx]
0x18000e511  mov     rax, [rax+1A8h]
0x18000e518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e51d  mov     [rbp+100h+arg_28], eax
0x18000e523  test    eax, eax
0x18000e525  js      loc_18000E743
0x18000e52b  mov     rbx, [rbp+100h+arg_10]
0x18000e532  lea     rdx, aP1d; "P1D"
0x18000e539  lea     rcx, [rsp+200h+var_190]; this
0x18000e53e  mov     rax, [rbx]
0x18000e541  mov     rdi, [rax+38h]
0x18000e545  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x18000e54a  mov     rdx, [rax]
0x18000e54d  test    rdx, rdx
0x18000e550  jz      short loc_18000E557
0x18000e552  mov     rdx, [rdx]
0x18000e555  jmp     short loc_18000E55A
0x18000e557  mov     rdx, r15
0x18000e55a  mov     rcx, rbx
0x18000e55d  mov     rax, rdi
0x18000e560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e565  mov     rbx, [rsp+200h+var_190]
0x18000e56a  mov     [rbp+100h+arg_28], eax
0x18000e570  test    rbx, rbx
0x18000e573  jz      short loc_18000E5BD
0x18000e575  or      eax, 0FFFFFFFFh
0x18000e578  lock xadd [rbx+10h], eax
0x18000e57d  cmp     eax, 1
0x18000e580  jnz     short loc_18000E5BD
0x18000e582  test    rbx, rbx
0x18000e585  jz      short loc_18000E5BD
0x18000e587  mov     rcx, [rbx]; bstrString
0x18000e58a  test    rcx, rcx
0x18000e58d  jz      short loc_18000E59E
0x18000e58f  call    cs:__imp_SysFreeString
0x18000e596  nop     dword ptr [rax+rax+00h]
0x18000e59b  mov     [rbx], r15
0x18000e59e  mov     rcx, [rbx+8]; void *
0x18000e5a2  test    rcx, rcx
0x18000e5a5  jz      short loc_18000E5B0
0x18000e5a7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000e5ac  mov     [rbx+8], r15
0x18000e5b0  mov     edx, 18h; struct std::nothrow_t *
0x18000e5b5  mov     rcx, rbx; void *
0x18000e5b8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000e5bd  cmp     [rbp+100h+arg_28], r15d
0x18000e5c4  jl      loc_18000E743
0x18000e5ca  mov     rbx, [rbp+100h+var_180]
0x18000e5ce  lea     rcx, [rbp+100h+pvarg]; pvarg
0x18000e5d2  mov     rax, [rbx]
0x18000e5d5  mov     r14, [rax+88h]
0x18000e5dc  call    cs:__imp_VariantInit
0x18000e5e3  nop     dword ptr [rax+rax+00h]
0x18000e5e8  movups  xmm6, xmmword ptr [rbp+100h+pvarg]
0x18000e5ec  lea     rcx, [rbp+100h+var_120]; pvarg
0x18000e5f0  movsd   xmm7, qword ptr [rbp+100h+pvarg+10h]
0x18000e5f5  call    cs:__imp_VariantInit
0x18000e5fc  nop     dword ptr [rax+rax+00h]
0x18000e601  movups  xmm8, xmmword ptr [rbp+100h+var_120]
0x18000e606  lea     rcx, [rbp+100h+var_138]; pvarg
0x18000e60a  movsd   xmm9, qword ptr [rbp+100h+var_120+10h]
0x18000e610  call    cs:__imp_VariantInit
0x18000e617  nop     dword ptr [rax+rax+00h]
0x18000e61c  movups  xmm10, xmmword ptr [rbp+100h+var_138]
0x18000e621  lea     rcx, [rsp+200h+var_190]; this
0x18000e626  mov     rdi, [rsp+200h+var_188]
0x18000e62b  movsd   xmm11, qword ptr [rbp+100h+var_138+10h]
0x18000e631  mov     rdx, rsi; unsigned __int16 *
0x18000e634  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000e639  mov     rdx, [rax]
0x18000e63c  test    rdx, rdx
0x18000e63f  jz      short loc_18000E646
0x18000e641  mov     rdx, [rdx]
0x18000e644  jmp     short loc_18000E649
0x18000e646  mov     rdx, r15
0x18000e649  lea     rax, [rbp+100h+var_178]
0x18000e64d  movaps  [rbp+100h+var_F0], xmm6
0x18000e651  mov     [rsp+200h+var_1C0], rax
0x18000e656  mov     r9d, 6
0x18000e65c  lea     rax, [rbp+100h+var_F0]
0x18000e660  movsd   [rbp+100h+var_E0], xmm7
0x18000e665  mov     [rsp+200h+var_1C8], rax
0x18000e66a  mov     r8, rdi
0x18000e66d  lea     rax, [rbp+100h+var_D0]
0x18000e671  mov     dword ptr [rsp+200h+var_1D0], 3
0x18000e679  mov     [rsp+200h+var_1D8], rax
0x18000e67e  mov     rcx, rbx
0x18000e681  lea     rax, [rbp+100h+var_B0]
0x18000e685  movaps  [rbp+100h+var_D0], xmm8
0x18000e68a  mov     [rsp+200h+var_1E0], rax
0x18000e68f  mov     rax, r14
0x18000e692  movsd   [rbp+100h+var_C0], xmm9
0x18000e698  movaps  [rbp+100h+var_B0], xmm10
0x18000e69d  movsd   [rbp+100h+var_A0], xmm11
0x18000e6a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6a8  mov     rbx, [rsp+200h+var_190]
0x18000e6ad  mov     [rbp+100h+arg_28], eax
0x18000e6b3  test    rbx, rbx
0x18000e6b6  jz      short loc_18000E705
0x18000e6b8  or      eax, 0FFFFFFFFh
0x18000e6bb  lock xadd [rbx+10h], eax
0x18000e6c0  cmp     eax, 1
0x18000e6c3  jnz     short loc_18000E700
0x18000e6c5  test    rbx, rbx
0x18000e6c8  jz      short loc_18000E700
0x18000e6ca  mov     rcx, [rbx]; bstrString
0x18000e6cd  test    rcx, rcx
0x18000e6d0  jz      short loc_18000E6E1
0x18000e6d2  call    cs:__imp_SysFreeString
0x18000e6d9  nop     dword ptr [rax+rax+00h]
0x18000e6de  mov     [rbx], r15
0x18000e6e1  mov     rcx, [rbx+8]; void *
0x18000e6e5  test    rcx, rcx
0x18000e6e8  jz      short loc_18000E6F3
0x18000e6ea  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000e6ef  mov     [rbx+8], r15
0x18000e6f3  mov     edx, 18h; struct std::nothrow_t *
0x18000e6f8  mov     rcx, rbx; void *
0x18000e6fb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000e700  mov     [rsp+200h+var_190], r15
0x18000e705  lea     rcx, [rbp+100h+var_138]; this
0x18000e709  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18000e70e  lea     rcx, [rbp+100h+var_120]; this
0x18000e712  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18000e717  lea     rcx, [rbp+100h+pvarg]; this
0x18000e71b  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18000e720  cmp     [rbp+100h+arg_28], r15d
0x18000e727  jge     short loc_18000E743
0x18000e729  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18000e72e  mov     edx, [rbp+100h+arg_28]; int
0x18000e734  lea     r8, aScheduleoneoma_1; "ScheduleOneOmaDmSessionMaintenanceCycle"
0x18000e73b  mov     rcx, rax; this
0x18000e73e  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x18000e743  mov     ebx, [rbp+100h+arg_28]
0x18000e749  lea     rcx, [rbp+100h+arg_10]
0x18000e750  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18000e755  lea     rcx, [rbp+100h+var_168]
0x18000e759  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18000e75e  lea     rcx, [rbp+100h+var_178]
0x18000e762  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18000e767  lea     rcx, [rbp+100h+var_160]
0x18000e76b  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18000e770  lea     rcx, [rbp+100h+var_158]
0x18000e774  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18000e779  lea     rcx, [rbp+100h+var_150]
0x18000e77d  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18000e782  lea     rcx, [rbp+100h+arg_20]
0x18000e789  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18000e78e  lea     rcx, [rsp+200h+var_188]
0x18000e793  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18000e798  lea     rcx, [rbp+100h+var_180]
0x18000e79c  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18000e7a1  lea     rcx, [rbp+100h+var_170]
0x18000e7a5  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18000e7aa  lea     rcx, [rbp+100h+var_148]; this
0x18000e7ae  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18000e7b3  lea     r11, [rsp+200h+var_28]
0x18000e7bb  mov     eax, ebx
0x18000e7bd  movaps  xmm6, xmmword ptr [r11-18h]
0x18000e7c2  movaps  xmm7, xmmword ptr [r11-28h]
0x18000e7c7  movaps  xmm8, xmmword ptr [r11-38h]
0x18000e7cc  movaps  xmm9, xmmword ptr [r11-48h]
0x18000e7d1  movaps  xmm10, xmmword ptr [r11-58h]
0x18000e7d6  movaps  xmm11, xmmword ptr [r11-68h]
0x18000e7db  mov     rsp, r11
0x18000e7de  pop     r15
0x18000e7e0  pop     r14
0x18000e7e2  pop     rdi
0x18000e7e3  pop     rsi
0x18000e7e4  pop     rbx
0x18000e7e5  pop     rbp
0x18000e7e6  retn
```
