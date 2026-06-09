# ScheduleRenewalWork

- ea: `0x18000ef24`
- end: `0x18000f647`
- name: `ScheduleRenewalWork`
- size: `1827`
- prototype: `__int64 __fastcall(int, int, int, int, struct _SYSTEMTIME *, __int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000eb90`

## callees

- `0x180001c60`
- `0x180001cc8`
- `0x180006574`
- `0x180007258`
- `0x1800072d0`
- `0x180007364`
- `0x1800077a0`
- `0x1800079e8`
- `0x180008730`
- `0x180008a2c`
- `0x180008bd4`
- `0x18000ef24`
- `0x18001b9d8`
- `0x18001bde0`
- `0x18001e010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000f142`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f2ab`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f3c8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f531`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f142`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f2ab`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f3c8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f531`
- `OLEAUT32!__imp_VariantInit` at `0x18000f433`
- `OLEAUT32!__imp_VariantInit` at `0x18000f44c`
- `OLEAUT32!__imp_VariantInit` at `0x18000f433`
- `OLEAUT32!__imp_VariantInit` at `0x18000f44c`

## string_xrefs

- `0x18000efd1`: `%windir%\system32\deviceenroller.exe `
- `0x18000f481`: `Schedule created by enrollment client for renewal of certificate warning`

## pseudocode

```c
__int64 __fastcall ScheduleRenewalWork(
        __int64 a1,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        struct _SYSTEMTIME *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7)
{
  const unsigned __int16 *v7; // r15
  __int64 v8; // r14
  __int64 v9; // rsi
  unsigned int v10; // r8d
  __int64 v11; // rbx
  __int64 (__fastcall *v12)(__int64, __int64); // rdi
  _bstr_t *v13; // rax
  __int64 v14; // rdx
  int v15; // eax
  const struct std::nothrow_t *v16; // rdx
  BSTR *v17; // rbx
  BSTR v18; // rcx
  __int64 v19; // rbx
  __int64 (__fastcall *v20)(__int64, __int64); // rdi
  _bstr_t *v21; // rax
  __int64 v22; // rdx
  int v23; // eax
  const struct std::nothrow_t *v24; // rdx
  BSTR *v25; // rbx
  BSTR v26; // rcx
  __int64 v27; // rbx
  __int64 (__fastcall *v28)(__int64, __int64); // rdi
  _bstr_t *v29; // rax
  __int64 v30; // rdx
  int v31; // eax
  const struct std::nothrow_t *v32; // rdx
  BSTR *v33; // rbx
  BSTR v34; // rcx
  struct IUnknown *v35; // rbx
  ULONG (__stdcall *Release)(IUnknown *); // rsi
  __int128 v37; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  __int128 v39; // xmm8
  IRecordInfo *v40; // xmm9_8
  _variant_t *v41; // rax
  __int64 v42; // rdi
  __int128 v43; // xmm10
  __int64 v44; // xmm11_8
  _bstr_t *v45; // rax
  __int64 v46; // rdx
  int v47; // eax
  const struct std::nothrow_t *v48; // rdx
  BSTR *v49; // rbx
  BSTR v50; // rcx
  CEnrollmentLogger *Logger; // rax
  unsigned int v52; // ebx
  __int64 v54; // [rsp+48h] [rbp-C0h]
  int v55[2]; // [rsp+78h] [rbp-90h] BYREF
  __int64 v56; // [rsp+80h] [rbp-88h] BYREF
  void *v57; // [rsp+88h] [rbp-80h] BYREF
  __int64 v58; // [rsp+90h] [rbp-78h] BYREF
  void *v59; // [rsp+98h] [rbp-70h] BYREF
  __int64 v60; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v61; // [rsp+A8h] [rbp-60h] BYREF
  __int64 (__fastcall ***v62)(_QWORD, GUID *, __int64 *); // [rsp+B0h] [rbp-58h] BYREF
  __int64 v63; // [rsp+B8h] [rbp-50h] BYREF
  struct IUnknown *v64; // [rsp+C0h] [rbp-48h] BYREF
  VARIANTARG pvarg; // [rsp+C8h] [rbp-40h] BYREF
  VARIANTARG v66; // [rsp+E0h] [rbp-28h] BYREF
  __int64 v67; // [rsp+F8h] [rbp-10h] BYREF
  LPVOID v68; // [rsp+100h] [rbp-8h] BYREF
  _QWORD v69[2]; // [rsp+108h] [rbp+0h] BYREF
  __int128 v70; // [rsp+118h] [rbp+10h] BYREF
  IRecordInfo *v71; // [rsp+128h] [rbp+20h]
  __int128 v72; // [rsp+138h] [rbp+30h] BYREF
  IRecordInfo *v73; // [rsp+148h] [rbp+40h]
  __int128 v74; // [rsp+158h] [rbp+50h] BYREF
  __int64 v75; // [rsp+168h] [rbp+60h]
  _BYTE v76[32]; // [rsp+178h] [rbp+70h] BYREF
  unsigned __int16 v77[264]; // [rsp+198h] [rbp+90h] BYREF
  unsigned __int16 v78[264]; // [rsp+3A8h] [rbp+2A0h] BYREF
  unsigned __int16 v79[264]; // [rsp+5B8h] [rbp+4B0h] BYREF

  v7 = a7;
  v69[0] = "ScheduleRenewalWork";
  v8 = a4;
  LODWORD(v54) = 0;
  v9 = a3;
  v69[1] = v55;
  v55[0] = 0;
  v68 = 0;
  v64 = 0;
  v58 = 0;
  v63 = 0;
  v61 = 0;
  v62 = 0;
  v60 = 0;
  v67 = 0;
  v56 = 0;
  LODWORD(v57) = 0;
  *(_OWORD *)&v66.vt = 0;
  *(_OWORD *)&pvarg.vt = 0;
  v55[0] = CreateTask(&v68, &v64, &v58, &v63, a2, L"%windir%\\system32\\deviceenroller.exe ", a6, a7, v54, 1, 1, 1, 0);
  if ( v55[0] >= 0 )
  {
    v55[0] = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v63 + 208LL))(v63, 0xFFFFFFFFLL);
    if ( v55[0] >= 0 )
    {
      v55[0] = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v58 + 72LL))(v58, &v61);
      if ( v55[0] >= 0 )
      {
        v55[0] = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v61 + 80LL))(v61, 1, &v62);
        if ( v55[0] >= 0 )
        {
          v55[0] = (**v62)(v62, &IID_ITimeTrigger, &v60);
          if ( v55[0] >= 0 )
          {
            v55[0] = CreateDelayTimeString(a5, v77, v10);
            if ( v55[0] >= 0 )
            {
              v11 = v60;
              v12 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v60 + 120LL);
              v13 = _bstr_t::_bstr_t((_bstr_t *)&v59, v77);
              if ( *(_QWORD *)v13 )
                v14 = **(_QWORD **)v13;
              else
                v14 = 0;
              v15 = v12(v11, v14);
              v17 = (BSTR *)v59;
              v55[0] = v15;
              if ( v59 && _InterlockedExchangeAdd((volatile signed __int32 *)v59 + 4, 0xFFFFFFFF) == 1 && v17 )
              {
                if ( *v17 )
                {
                  SysFreeString(*v17);
                  *v17 = 0;
                }
                v18 = v17[1];
                if ( v18 )
                {
                  operator delete(v18, v16);
                  v17[1] = 0;
                }
                operator delete(v17, (const struct std::nothrow_t *)0x18);
              }
              if ( v55[0] >= 0 )
              {
                v55[0] = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v60 + 80LL))(v60, &v56);
                if ( v55[0] >= 0 )
                {
                  if ( !(_DWORD)v9 )
                  {
                    v55[0] = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v56 + 96LL))(v56, 0);
                    if ( v55[0] < 0 )
                      goto LABEL_68;
                    goto LABEL_38;
                  }
                  v55[0] = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v56 + 96LL))(v56, 0xFFFFFFFFLL);
                  if ( v55[0] >= 0 )
                  {
                    v55[0] = ULongLongToULong(v9 * v8, (unsigned int *)&v57);
                    if ( v55[0] >= 0 )
                    {
                      *(_DWORD *)&pvarg.vt = 0;
                      v55[0] = 0;
                      pvarg.wReserved3 = (unsigned int)v57 / 0x3C / 0x18;
                      WORD1(pvarg.decVal.Lo64) = (unsigned int)v57 % 0x3C;
                      pvarg.iVal = (unsigned int)v57 / 0x3C % 0x18;
                      v55[0] = CreateScheduleTimeString(&pvarg, v78);
                      if ( v55[0] >= 0 )
                      {
                        v19 = v56;
                        v20 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v56 + 80LL);
                        v21 = _bstr_t::_bstr_t((_bstr_t *)&v59, v78);
                        if ( *(_QWORD *)v21 )
                          v22 = **(_QWORD **)v21;
                        else
                          v22 = 0;
                        v23 = v20(v19, v22);
                        v25 = (BSTR *)v59;
                        v55[0] = v23;
                        if ( v59 && _InterlockedExchangeAdd((volatile signed __int32 *)v59 + 4, 0xFFFFFFFF) == 1 && v25 )
                        {
                          if ( *v25 )
                          {
                            SysFreeString(*v25);
                            *v25 = 0;
                          }
                          v26 = v25[1];
                          if ( v26 )
                          {
                            operator delete(v26, v24);
                            v25[1] = 0;
                          }
                          operator delete(v25, (const struct std::nothrow_t *)0x18);
                        }
                        if ( v55[0] >= 0 )
                        {
LABEL_38:
                          *(_DWORD *)&v66.vt = 0;
                          v55[0] = 0;
                          v66.wReserved3 = (unsigned int)v8 / 0x3C / 0x18;
                          WORD1(v66.decVal.Lo64) = (unsigned int)v8 % 0x3C;
                          v66.iVal = (unsigned int)v8 / 0x3C % 0x18;
                          v55[0] = CreateScheduleTimeString(&v66, v79);
                          if ( v55[0] >= 0 )
                          {
                            v27 = v56;
                            v28 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v56 + 64LL);
                            v29 = _bstr_t::_bstr_t((_bstr_t *)&v59, v79);
                            if ( *(_QWORD *)v29 )
                              v30 = **(_QWORD **)v29;
                            else
                              v30 = 0;
                            v31 = v28(v27, v30);
                            v33 = (BSTR *)v59;
                            v55[0] = v31;
                            if ( v59
                              && _InterlockedExchangeAdd((volatile signed __int32 *)v59 + 4, 0xFFFFFFFF) == 1
                              && v33 )
                            {
                              if ( *v33 )
                              {
                                SysFreeString(*v33);
                                *v33 = 0;
                              }
                              v34 = v33[1];
                              if ( v34 )
                              {
                                operator delete(v34, v32);
                                v33[1] = 0;
                              }
                              operator delete(v33, (const struct std::nothrow_t *)0x18);
                            }
                            if ( v55[0] >= 0 )
                            {
                              v55[0] = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v58 + 80LL))(v58, v61);
                              if ( v55[0] >= 0 )
                              {
                                v35 = v64;
                                Release = v64->lpVtbl[5].Release;
                                VariantInit(&pvarg);
                                v37 = *(_OWORD *)&pvarg.vt;
                                pRecInfo = pvarg.pRecInfo;
                                VariantInit(&v66);
                                v39 = *(_OWORD *)&v66.vt;
                                v40 = v66.pRecInfo;
                                if ( !a7 )
                                  v7 = L"S-1-5-18";
                                v41 = _variant_t::_variant_t((_variant_t *)v76, v7);
                                v42 = v58;
                                v43 = *(_OWORD *)v41;
                                v44 = *((_QWORD *)v41 + 2);
                                v45 = _bstr_t::_bstr_t(
                                        (_bstr_t *)&v57,
                                        L"Schedule created by enrollment client for renewal of certificate warning");
                                if ( *(_QWORD *)v45 )
                                  v46 = **(_QWORD **)v45;
                                else
                                  v46 = 0;
                                v70 = v37;
                                v71 = pRecInfo;
                                v72 = v39;
                                v73 = v40;
                                v74 = v43;
                                v75 = v44;
                                v47 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))Release)(
                                        v35,
                                        v46,
                                        v42,
                                        6,
                                        &v74,
                                        &v72,
                                        3,
                                        &v70,
                                        &v67);
                                v49 = (BSTR *)v57;
                                v55[0] = v47;
                                if ( v57 )
                                {
                                  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v57 + 4, 0xFFFFFFFF) == 1
                                    && v49 )
                                  {
                                    if ( *v49 )
                                    {
                                      SysFreeString(*v49);
                                      *v49 = 0;
                                    }
                                    v50 = v49[1];
                                    if ( v50 )
                                    {
                                      operator delete(v50, v48);
                                      v49[1] = 0;
                                    }
                                    operator delete(v49, (const struct std::nothrow_t *)0x18);
                                  }
                                  v57 = 0;
                                }
                                _variant_t::~_variant_t((_variant_t *)v76);
                                _variant_t::~_variant_t((_variant_t *)&v66);
                                _variant_t::~_variant_t((_variant_t *)&pvarg);
                                if ( v55[0] < 0 )
                                {
                                  Logger = CEnrollmentLogger::GetLogger();
                                  CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(
                                    Logger,
                                    v55[0],
                                    "ScheduleRenewalWork");
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_68:
  v52 = v55[0];
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v56);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v67);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v60);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v62);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v61);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v63);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v58);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v64);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v68);
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v69);
  return v52;
}

```

## disassembly

```asm
0x18000ef24  mov     rax, rsp
0x18000ef27  mov     [rax+8], rbx
0x18000ef2b  push    rbp
0x18000ef2c  push    rsi
0x18000ef2d  push    rdi
0x18000ef2e  push    r12
0x18000ef30  push    r13
0x18000ef32  push    r14
0x18000ef34  push    r15
0x18000ef36  lea     rbp, [rax-768h]
0x18000ef3d  sub     rsp, 830h
0x18000ef44  movaps  xmmword ptr [rax-48h], xmm6
0x18000ef48  movaps  xmmword ptr [rax-58h], xmm7
0x18000ef4c  movaps  xmmword ptr [rax-68h], xmm8
0x18000ef51  movaps  xmmword ptr [rax-78h], xmm9
0x18000ef56  movaps  xmmword ptr [rax-88h], xmm10
0x18000ef5e  movaps  xmmword ptr [rax-98h], xmm11
0x18000ef66  mov     rax, cs:__security_cookie
0x18000ef6d  xor     rax, rsp
0x18000ef70  mov     [rbp+760h+var_A0], rax
0x18000ef77  mov     rax, [rbp+760h+arg_28]
0x18000ef7e  lea     rcx, aSchedulerenewa; "ScheduleRenewalWork"
0x18000ef85  mov     r15, [rbp+760h+arg_30]
0x18000ef8c  xor     r12d, r12d
0x18000ef8f  mov     rbx, [rbp+760h+arg_20]
0x18000ef96  xorps   xmm0, xmm0
0x18000ef99  mov     [rsp+860h+var_800], r12d
0x18000ef9e  xorps   xmm1, xmm1
0x18000efa1  mov     [rbp+760h+var_760], rcx
0x18000efa5  lea     rcx, [rsp+860h+var_7F0]
0x18000efaa  lea     edi, [r12+1]
0x18000efaf  mov     r14d, r9d
0x18000efb2  mov     [rsp+860h+var_808], edi
0x18000efb6  lea     r9, [rbp+760h+var_7B0]
0x18000efba  mov     [rsp+860h+var_810], edi
0x18000efbe  mov     [rsp+860h+var_818], edi
0x18000efc2  mov     dword ptr [rsp+860h+var_820], r12d
0x18000efc7  mov     [rsp+860h+var_828], r15
0x18000efcc  mov     [rsp+860h+var_830], rax
0x18000efd1  lea     rax, aWindirSystem32_1; "%windir%\\system32\\deviceenroller.exe "
0x18000efd8  mov     [rsp+860h+var_838], rax
0x18000efdd  mov     [rsp+860h+var_840], rdx
0x18000efe2  lea     rdx, [rbp+760h+var_7A8]
0x18000efe6  mov     esi, r8d
0x18000efe9  lea     r8, [rbp+760h+var_7D8]
0x18000efed  mov     [rbp+760h+var_758], rcx
0x18000eff1  lea     rcx, [rbp+760h+var_768]
0x18000eff5  mov     [rsp+860h+var_7F0], r12d
0x18000effa  mov     [rbp+760h+var_768], r12
0x18000effe  mov     [rbp+760h+var_7A8], r12
0x18000f002  mov     [rbp+760h+var_7D8], r12
0x18000f006  mov     [rbp+760h+var_7B0], r12
0x18000f00a  mov     [rbp+760h+var_7C0], r12
0x18000f00e  mov     [rbp+760h+var_7B8], r12
0x18000f012  mov     [rbp+760h+var_7C8], r12
0x18000f016  mov     [rbp+760h+var_770], r12
0x18000f01a  mov     [rsp+860h+var_7E8], r12
0x18000f01f  mov     dword ptr [rbp+760h+var_7E0], r12d
0x18000f023  movups  xmmword ptr [rbp+760h+var_788], xmm0
0x18000f027  movups  xmmword ptr [rbp+760h+pvarg], xmm1
0x18000f02b  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x18000f030  mov     [rsp+860h+var_7F0], eax
0x18000f034  test    eax, eax
0x18000f036  js      loc_18000F59D
0x18000f03c  mov     rcx, [rbp+760h+var_7B0]
0x18000f040  or      r13d, 0FFFFFFFFh
0x18000f044  mov     edx, r13d
0x18000f047  mov     rax, [rcx]
0x18000f04a  mov     rax, [rax+0D0h]
0x18000f051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f056  mov     [rsp+860h+var_7F0], eax
0x18000f05a  test    eax, eax
0x18000f05c  js      loc_18000F59D
0x18000f062  mov     rcx, [rbp+760h+var_7D8]
0x18000f066  lea     rdx, [rbp+760h+var_7C0]
0x18000f06a  mov     rax, [rcx]
0x18000f06d  mov     rax, [rax+48h]
0x18000f071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f076  mov     [rsp+860h+var_7F0], eax
0x18000f07a  test    eax, eax
0x18000f07c  js      loc_18000F59D
0x18000f082  mov     rcx, [rbp+760h+var_7C0]
0x18000f086  lea     r8, [rbp+760h+var_7B8]
0x18000f08a  mov     edx, edi
0x18000f08c  mov     rax, [rcx]
0x18000f08f  mov     rax, [rax+50h]
0x18000f093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f098  mov     [rsp+860h+var_7F0], eax
0x18000f09c  test    eax, eax
0x18000f09e  js      loc_18000F59D
0x18000f0a4  mov     rcx, [rbp+760h+var_7B8]
0x18000f0a8  lea     r8, [rbp+760h+var_7C8]
0x18000f0ac  lea     rdx, IID_ITimeTrigger
0x18000f0b3  mov     rax, [rcx]
0x18000f0b6  mov     rax, [rax]
0x18000f0b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0be  mov     [rsp+860h+var_7F0], eax
0x18000f0c2  test    eax, eax
0x18000f0c4  js      loc_18000F59D
0x18000f0ca  lea     rdx, [rbp+760h+var_6D0]; unsigned __int16 *
0x18000f0d1  mov     rcx, rbx; struct _SYSTEMTIME *
0x18000f0d4  call    ?CreateDelayTimeString@@YAJPEAU_SYSTEMTIME@@PEAGK@Z; CreateDelayTimeString(_SYSTEMTIME *,ushort *,ulong)
0x18000f0d9  mov     [rsp+860h+var_7F0], eax
0x18000f0dd  test    eax, eax
0x18000f0df  js      loc_18000F59D
0x18000f0e5  mov     rbx, [rbp+760h+var_7C8]
0x18000f0e9  lea     rdx, [rbp+760h+var_6D0]; unsigned __int16 *
0x18000f0f0  lea     rcx, [rbp+760h+var_7D0]; this
0x18000f0f4  mov     rax, [rbx]
0x18000f0f7  mov     rdi, [rax+78h]
0x18000f0fb  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000f100  mov     rdx, [rax]
0x18000f103  test    rdx, rdx
0x18000f106  jz      short loc_18000F10D
0x18000f108  mov     rdx, [rdx]
0x18000f10b  jmp     short loc_18000F110
0x18000f10d  mov     rdx, r12
0x18000f110  mov     rcx, rbx
0x18000f113  mov     rax, rdi
0x18000f116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f11b  mov     rbx, [rbp+760h+var_7D0]
0x18000f11f  mov     [rsp+860h+var_7F0], eax
0x18000f123  test    rbx, rbx
0x18000f126  jz      short loc_18000F170
0x18000f128  mov     eax, r13d
0x18000f12b  lock xadd [rbx+10h], eax
0x18000f130  add     eax, r13d
0x18000f133  jnz     short loc_18000F170
0x18000f135  test    rbx, rbx
0x18000f138  jz      short loc_18000F170
0x18000f13a  mov     rcx, [rbx]; bstrString
0x18000f13d  test    rcx, rcx
0x18000f140  jz      short loc_18000F151
0x18000f142  call    cs:__imp_SysFreeString
0x18000f149  nop     dword ptr [rax+rax+00h]
0x18000f14e  mov     [rbx], r12
0x18000f151  mov     rcx, [rbx+8]; void *
0x18000f155  test    rcx, rcx
0x18000f158  jz      short loc_18000F163
0x18000f15a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000f15f  mov     [rbx+8], r12
0x18000f163  mov     edx, 18h; struct std::nothrow_t *
0x18000f168  mov     rcx, rbx; void *
0x18000f16b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000f170  cmp     [rsp+860h+var_7F0], r12d
0x18000f175  jl      loc_18000F59D
0x18000f17b  mov     rcx, [rbp+760h+var_7C8]
0x18000f17f  lea     rdx, [rsp+860h+var_7E8]
0x18000f184  mov     rax, [rcx]
0x18000f187  mov     rax, [rax+50h]
0x18000f18b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f190  mov     [rsp+860h+var_7F0], eax
0x18000f194  test    eax, eax
0x18000f196  js      loc_18000F59D
0x18000f19c  mov     rcx, [rsp+860h+var_7E8]
0x18000f1a1  test    esi, esi
0x18000f1a3  jz      loc_18000F2E6
0x18000f1a9  mov     rax, [rcx]
0x18000f1ac  mov     edx, r13d
0x18000f1af  mov     rax, [rax+60h]
0x18000f1b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1b8  mov     [rsp+860h+var_7F0], eax
0x18000f1bc  test    eax, eax
0x18000f1be  js      loc_18000F59D
0x18000f1c4  mov     rcx, r14
0x18000f1c7  lea     rdx, [rbp+760h+var_7E0]; unsigned int *
0x18000f1cb  imul    rcx, rsi; unsigned __int64
0x18000f1cf  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18000f1d4  mov     [rsp+860h+var_7F0], eax
0x18000f1d8  test    eax, eax
0x18000f1da  js      loc_18000F59D
0x18000f1e0  mov     r8d, dword ptr [rbp+760h+var_7E0]
0x18000f1e4  mov     eax, 88888889h
0x18000f1e9  mul     r8d
0x18000f1ec  mov     dword ptr [rbp+760h+pvarg], r12d
0x18000f1f0  mov     r9d, edx
0x18000f1f3  mov     [rsp+860h+var_7F0], r12d
0x18000f1f8  shr     r9d, 5
0x18000f1fc  movzx   eax, r9w
0x18000f200  imul    ecx, eax, 3Ch ; '<'
0x18000f203  mov     eax, 0AAAAAAABh
0x18000f208  mul     r9d
0x18000f20b  sub     r8w, cx
0x18000f20f  shr     edx, 4
0x18000f212  movzx   eax, dx
0x18000f215  mov     word ptr [rbp+760h+pvarg+6], dx
0x18000f219  add     ax, ax
0x18000f21c  mov     word ptr [rbp+760h+pvarg+0Ah], r8w
0x18000f221  lea     ecx, [rax+rdx]
0x18000f224  shl     cx, 3
0x18000f228  lea     rdx, [rbp+760h+var_4C0]
0x18000f22f  sub     r9w, cx
0x18000f233  lea     rcx, [rbp+760h+pvarg]
0x18000f237  mov     word ptr [rbp+760h+pvarg+8], r9w
0x18000f23c  call    CreateScheduleTimeString
0x18000f241  mov     [rsp+860h+var_7F0], eax
0x18000f245  test    eax, eax
0x18000f247  js      loc_18000F59D
0x18000f24d  mov     rbx, [rsp+860h+var_7E8]
0x18000f252  lea     rdx, [rbp+760h+var_4C0]; unsigned __int16 *
0x18000f259  lea     rcx, [rbp+760h+var_7D0]; this
0x18000f25d  mov     rax, [rbx]
0x18000f260  mov     rdi, [rax+50h]
0x18000f264  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000f269  mov     rdx, [rax]
0x18000f26c  test    rdx, rdx
0x18000f26f  jz      short loc_18000F276
0x18000f271  mov     rdx, [rdx]
0x18000f274  jmp     short loc_18000F279
0x18000f276  mov     rdx, r12
0x18000f279  mov     rcx, rbx
0x18000f27c  mov     rax, rdi
0x18000f27f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f284  mov     rbx, [rbp+760h+var_7D0]
0x18000f288  mov     [rsp+860h+var_7F0], eax
0x18000f28c  test    rbx, rbx
0x18000f28f  jz      short loc_18000F2D9
0x18000f291  mov     eax, r13d
0x18000f294  lock xadd [rbx+10h], eax
0x18000f299  add     eax, r13d
0x18000f29c  jnz     short loc_18000F2D9
0x18000f29e  test    rbx, rbx
0x18000f2a1  jz      short loc_18000F2D9
0x18000f2a3  mov     rcx, [rbx]; bstrString
0x18000f2a6  test    rcx, rcx
0x18000f2a9  jz      short loc_18000F2BA
0x18000f2ab  call    cs:__imp_SysFreeString
0x18000f2b2  nop     dword ptr [rax+rax+00h]
0x18000f2b7  mov     [rbx], r12
0x18000f2ba  mov     rcx, [rbx+8]; void *
0x18000f2be  test    rcx, rcx
0x18000f2c1  jz      short loc_18000F2CC
0x18000f2c3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000f2c8  mov     [rbx+8], r12
0x18000f2cc  mov     edx, 18h; struct std::nothrow_t *
0x18000f2d1  mov     rcx, rbx; void *
0x18000f2d4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000f2d9  cmp     [rsp+860h+var_7F0], r12d
0x18000f2de  jl      loc_18000F59D
0x18000f2e4  jmp     short loc_18000F300
0x18000f2e6  mov     r8, [rcx]
0x18000f2e9  xor     edx, edx
0x18000f2eb  mov     rax, [r8+60h]
0x18000f2ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2f4  mov     [rsp+860h+var_7F0], eax
0x18000f2f8  test    eax, eax
0x18000f2fa  js      loc_18000F59D
0x18000f300  mov     eax, 88888889h
0x18000f305  mov     dword ptr [rbp+760h+var_788], r12d
0x18000f309  mul     r14d
0x18000f30c  mov     eax, 0AAAAAAABh
0x18000f311  mov     [rsp+860h+var_7F0], r12d
0x18000f316  mov     r9d, edx
0x18000f319  shr     r9d, 5
0x18000f31d  mul     r9d
0x18000f320  movzx   ecx, r9w
0x18000f324  shr     edx, 4
0x18000f327  imul    r8d, ecx, 3Ch ; '<'
0x18000f32b  movzx   eax, dx
0x18000f32e  add     ax, ax
0x18000f331  mov     word ptr [rbp+760h+var_788+6], dx
0x18000f335  lea     ecx, [rax+rdx]
0x18000f338  sub     r14w, r8w
0x18000f33c  shl     cx, 3
0x18000f340  lea     rdx, [rbp+760h+var_2B0]
0x18000f347  sub     r9w, cx
0x18000f34b  mov     word ptr [rbp+760h+var_788+0Ah], r14w
0x18000f350  lea     rcx, [rbp+760h+var_788]
0x18000f354  mov     word ptr [rbp+760h+var_788+8], r9w
0x18000f359  call    CreateScheduleTimeString
0x18000f35e  mov     [rsp+860h+var_7F0], eax
0x18000f362  test    eax, eax
0x18000f364  js      loc_18000F59D
0x18000f36a  mov     rbx, [rsp+860h+var_7E8]
0x18000f36f  lea     rdx, [rbp+760h+var_2B0]; unsigned __int16 *
0x18000f376  lea     rcx, [rbp+760h+var_7D0]; this
0x18000f37a  mov     rax, [rbx]
0x18000f37d  mov     rdi, [rax+40h]
0x18000f381  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000f386  mov     rdx, [rax]
0x18000f389  test    rdx, rdx
0x18000f38c  jz      short loc_18000F393
0x18000f38e  mov     rdx, [rdx]
0x18000f391  jmp     short loc_18000F396
0x18000f393  mov     rdx, r12
0x18000f396  mov     rcx, rbx
0x18000f399  mov     rax, rdi
0x18000f39c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3a1  mov     rbx, [rbp+760h+var_7D0]
0x18000f3a5  mov     [rsp+860h+var_7F0], eax
0x18000f3a9  test    rbx, rbx
0x18000f3ac  jz      short loc_18000F3F6
0x18000f3ae  mov     eax, r13d
0x18000f3b1  lock xadd [rbx+10h], eax
0x18000f3b6  add     eax, r13d
0x18000f3b9  jnz     short loc_18000F3F6
0x18000f3bb  test    rbx, rbx
0x18000f3be  jz      short loc_18000F3F6
0x18000f3c0  mov     rcx, [rbx]; bstrString
0x18000f3c3  test    rcx, rcx
  ... truncated ...
```
