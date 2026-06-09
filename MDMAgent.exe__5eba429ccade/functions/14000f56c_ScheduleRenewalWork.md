# ScheduleRenewalWork

- ea: `0x14000f56c`
- end: `0x14000fc6a`
- name: `ScheduleRenewalWork`
- size: `1790`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 *, unsigned int, unsigned int, struct _SYSTEMTIME *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x14000f1f8`

## callees

- `0x140002930`
- `0x140002954`
- `0x1400046a4`
- `0x140004c34`
- `0x140007724`
- `0x140008dc8`
- `0x140008e48`
- `0x1400090fc`
- `0x140009d3c`
- `0x140009f10`
- `0x14000a0b8`
- `0x14000f56c`
- `0x1400177b0`
- `0x140017ba0`
- `0x140019010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000f78a`
- `OLEAUT32!__imp_SysFreeString` at `0x14000f8ed`
- `OLEAUT32!__imp_SysFreeString` at `0x14000fa04`
- `OLEAUT32!__imp_SysFreeString` at `0x14000fb5b`
- `OLEAUT32!__imp_SysFreeString` at `0x14000f78a`
- `OLEAUT32!__imp_SysFreeString` at `0x14000f8ed`
- `OLEAUT32!__imp_SysFreeString` at `0x14000fa04`
- `OLEAUT32!__imp_SysFreeString` at `0x14000fb5b`
- `OLEAUT32!__imp_VariantInit` at `0x14000fa69`
- `OLEAUT32!__imp_VariantInit` at `0x14000fa7c`
- `OLEAUT32!__imp_VariantInit` at `0x14000fa69`
- `OLEAUT32!__imp_VariantInit` at `0x14000fa7c`

## string_xrefs

- `0x14000f619`: `%windir%\system32\deviceenroller.exe `
- `0x14000faab`: `Schedule created by enrollment client for renewal of certificate warning`

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
  BSTR *v16; // rbx
  BSTR v17; // rcx
  __int64 v18; // rbx
  __int64 (__fastcall *v19)(__int64, __int64); // rdi
  _bstr_t *v20; // rax
  __int64 v21; // rdx
  int v22; // eax
  BSTR *v23; // rbx
  BSTR v24; // rcx
  __int64 v25; // rbx
  __int64 (__fastcall *v26)(__int64, __int64); // rdi
  _bstr_t *v27; // rax
  __int64 v28; // rdx
  int v29; // eax
  BSTR *v30; // rbx
  BSTR v31; // rcx
  __int64 v32; // rbx
  __int64 (__fastcall *v33)(__int64, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *); // rsi
  __int128 v34; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  __int128 v36; // xmm8
  IRecordInfo *v37; // xmm9_8
  _variant_t *v38; // rax
  __int64 v39; // rdi
  __int128 v40; // xmm10
  __int64 v41; // xmm11_8
  _bstr_t *v42; // rax
  __int64 v43; // rdx
  int v44; // eax
  BSTR *v45; // rbx
  BSTR v46; // rcx
  CEnrollmentLogger *Logger; // rax
  unsigned int v48; // ebx
  int v50[2]; // [rsp+78h] [rbp-90h] BYREF
  __int64 v51; // [rsp+80h] [rbp-88h] BYREF
  void *v52; // [rsp+88h] [rbp-80h] BYREF
  int v53[2]; // [rsp+90h] [rbp-78h] BYREF
  void *Block; // [rsp+98h] [rbp-70h] BYREF
  __int64 v55; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v56; // [rsp+A8h] [rbp-60h] BYREF
  __int64 (__fastcall ***v57)(_QWORD, GUID *, __int64 *); // [rsp+B0h] [rbp-58h] BYREF
  int v58[2]; // [rsp+B8h] [rbp-50h] BYREF
  int v59[2]; // [rsp+C0h] [rbp-48h] BYREF
  VARIANTARG pvarg; // [rsp+C8h] [rbp-40h] BYREF
  VARIANTARG v61; // [rsp+E0h] [rbp-28h] BYREF
  __int64 v62; // [rsp+F8h] [rbp-10h] BYREF
  int v63[2]; // [rsp+100h] [rbp-8h] BYREF
  _QWORD v64[2]; // [rsp+108h] [rbp+0h] BYREF
  __int128 v65; // [rsp+118h] [rbp+10h] BYREF
  IRecordInfo *v66; // [rsp+128h] [rbp+20h]
  __int128 v67; // [rsp+138h] [rbp+30h] BYREF
  IRecordInfo *v68; // [rsp+148h] [rbp+40h]
  __int128 v69; // [rsp+158h] [rbp+50h] BYREF
  __int64 v70; // [rsp+168h] [rbp+60h]
  VARIANTARG v71; // [rsp+178h] [rbp+70h] BYREF
  unsigned __int16 v72[264]; // [rsp+198h] [rbp+90h] BYREF
  unsigned __int16 v73[264]; // [rsp+3A8h] [rbp+2A0h] BYREF
  unsigned __int16 v74[264]; // [rsp+5B8h] [rbp+4B0h] BYREF

  v7 = a7;
  v64[0] = "ScheduleRenewalWork";
  v8 = a4;
  v9 = a3;
  v64[1] = v50;
  v50[0] = 0;
  *(_QWORD *)v63 = 0;
  *(_QWORD *)v59 = 0;
  *(_QWORD *)v53 = 0;
  *(_QWORD *)v58 = 0;
  v56 = 0;
  v57 = 0;
  v55 = 0;
  v62 = 0;
  v51 = 0;
  LODWORD(v52) = 0;
  *(_OWORD *)&v61.vt = 0;
  *(_OWORD *)&pvarg.vt = 0;
  v50[0] = CreateTask(
             v63,
             (__int64)v59,
             v53,
             v58,
             a2,
             L"%windir%\\system32\\deviceenroller.exe ",
             a6,
             a7,
             0,
             1,
             1,
             1,
             0);
  if ( v50[0] >= 0 )
  {
    v50[0] = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v58 + 208LL))(*(_QWORD *)v58, 0xFFFFFFFFLL);
    if ( v50[0] >= 0 )
    {
      v50[0] = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)v53 + 72LL))(*(_QWORD *)v53, &v56);
      if ( v50[0] >= 0 )
      {
        v50[0] = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v56 + 80LL))(v56, 1, &v57);
        if ( v50[0] >= 0 )
        {
          v50[0] = (**v57)(v57, &IID_ITimeTrigger, &v55);
          if ( v50[0] >= 0 )
          {
            v50[0] = CreateDelayTimeString(a5, v72, v10);
            if ( v50[0] >= 0 )
            {
              v11 = v55;
              v12 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v55 + 120LL);
              v13 = _bstr_t::_bstr_t((_bstr_t *)&Block, v72);
              if ( *(_QWORD *)v13 )
                v14 = **(_QWORD **)v13;
              else
                v14 = 0;
              v15 = v12(v11, v14);
              v16 = (BSTR *)Block;
              v50[0] = v15;
              if ( Block && _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v16 )
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
              if ( v50[0] >= 0 )
              {
                v50[0] = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v55 + 80LL))(v55, &v51);
                if ( v50[0] >= 0 )
                {
                  if ( !(_DWORD)v9 )
                  {
                    v50[0] = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v51 + 96LL))(v51, 0);
                    if ( v50[0] < 0 )
                      goto LABEL_68;
                    goto LABEL_38;
                  }
                  v50[0] = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v51 + 96LL))(v51, 0xFFFFFFFFLL);
                  if ( v50[0] >= 0 )
                  {
                    v50[0] = ULongLongToULong(v9 * v8, (unsigned int *)&v52);
                    if ( v50[0] >= 0 )
                    {
                      *(_DWORD *)&pvarg.vt = 0;
                      v50[0] = 0;
                      pvarg.wReserved3 = (unsigned int)v52 / 0x3C / 0x18;
                      WORD1(pvarg.decVal.Lo64) = (unsigned int)v52 % 0x3C;
                      pvarg.iVal = (unsigned int)v52 / 0x3C % 0x18;
                      v50[0] = CreateScheduleTimeString(&pvarg, v73);
                      if ( v50[0] >= 0 )
                      {
                        v18 = v51;
                        v19 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v51 + 80LL);
                        v20 = _bstr_t::_bstr_t((_bstr_t *)&Block, v73);
                        if ( *(_QWORD *)v20 )
                          v21 = **(_QWORD **)v20;
                        else
                          v21 = 0;
                        v22 = v19(v18, v21);
                        v23 = (BSTR *)Block;
                        v50[0] = v22;
                        if ( Block
                          && _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1
                          && v23 )
                        {
                          if ( *v23 )
                          {
                            SysFreeString(*v23);
                            *v23 = 0;
                          }
                          v24 = v23[1];
                          if ( v24 )
                          {
                            operator delete(v24);
                            v23[1] = 0;
                          }
                          operator delete(v23);
                        }
                        if ( v50[0] >= 0 )
                        {
LABEL_38:
                          *(_DWORD *)&v61.vt = 0;
                          v50[0] = 0;
                          v61.wReserved3 = (unsigned int)v8 / 0x3C / 0x18;
                          WORD1(v61.decVal.Lo64) = (unsigned int)v8 % 0x3C;
                          v61.iVal = (unsigned int)v8 / 0x3C % 0x18;
                          v50[0] = CreateScheduleTimeString(&v61, v74);
                          if ( v50[0] >= 0 )
                          {
                            v25 = v51;
                            v26 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v51 + 64LL);
                            v27 = _bstr_t::_bstr_t((_bstr_t *)&Block, v74);
                            if ( *(_QWORD *)v27 )
                              v28 = **(_QWORD **)v27;
                            else
                              v28 = 0;
                            v29 = v26(v25, v28);
                            v30 = (BSTR *)Block;
                            v50[0] = v29;
                            if ( Block
                              && _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1
                              && v30 )
                            {
                              if ( *v30 )
                              {
                                SysFreeString(*v30);
                                *v30 = 0;
                              }
                              v31 = v30[1];
                              if ( v31 )
                              {
                                operator delete(v31);
                                v30[1] = 0;
                              }
                              operator delete(v30);
                            }
                            if ( v50[0] >= 0 )
                            {
                              v50[0] = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v53 + 80LL))(
                                         *(_QWORD *)v53,
                                         v56);
                              if ( v50[0] >= 0 )
                              {
                                v32 = *(_QWORD *)v59;
                                v33 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))(**(_QWORD **)v59 + 136LL);
                                VariantInit(&pvarg);
                                v34 = *(_OWORD *)&pvarg.vt;
                                pRecInfo = pvarg.pRecInfo;
                                VariantInit(&v61);
                                v36 = *(_OWORD *)&v61.vt;
                                v37 = v61.pRecInfo;
                                if ( !a7 )
                                  v7 = L"S-1-5-18";
                                v38 = _variant_t::_variant_t((_variant_t *)&v71, v7);
                                v39 = *(_QWORD *)v53;
                                v40 = *(_OWORD *)v38;
                                v41 = *((_QWORD *)v38 + 2);
                                v42 = _bstr_t::_bstr_t(
                                        (_bstr_t *)&v52,
                                        L"Schedule created by enrollment client for renewal of certificate warning");
                                if ( *(_QWORD *)v42 )
                                  v43 = **(_QWORD **)v42;
                                else
                                  v43 = 0;
                                v65 = v34;
                                v66 = pRecInfo;
                                v67 = v36;
                                v68 = v37;
                                v69 = v40;
                                v70 = v41;
                                v44 = v33(v32, v43, v39, 6, &v69, &v67, 3, &v65, &v62);
                                v45 = (BSTR *)v52;
                                v50[0] = v44;
                                if ( v52 )
                                {
                                  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v52 + 4, 0xFFFFFFFF) == 1
                                    && v45 )
                                  {
                                    if ( *v45 )
                                    {
                                      SysFreeString(*v45);
                                      *v45 = 0;
                                    }
                                    v46 = v45[1];
                                    if ( v46 )
                                    {
                                      operator delete(v46);
                                      v45[1] = 0;
                                    }
                                    operator delete(v45);
                                  }
                                  v52 = 0;
                                }
                                ATL::CComVariant::~CComVariant(&v71);
                                ATL::CComVariant::~CComVariant(&v61);
                                ATL::CComVariant::~CComVariant(&pvarg);
                                if ( v50[0] < 0 )
                                {
                                  Logger = CEnrollmentLogger::GetLogger();
                                  CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(
                                    Logger,
                                    v50[0],
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
  v48 = v50[0];
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v51);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v62);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v55);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v57);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v56);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(v58);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(v53);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(v59);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(v63);
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v64);
  return v48;
}

```

## disassembly

```asm
0x14000f56c  mov     rax, rsp
0x14000f56f  mov     [rax+8], rbx
0x14000f573  push    rbp
0x14000f574  push    rsi
0x14000f575  push    rdi
0x14000f576  push    r12
0x14000f578  push    r13
0x14000f57a  push    r14
0x14000f57c  push    r15
0x14000f57e  lea     rbp, [rax-768h]
0x14000f585  sub     rsp, 830h
0x14000f58c  movaps  xmmword ptr [rax-48h], xmm6
0x14000f590  movaps  xmmword ptr [rax-58h], xmm7
0x14000f594  movaps  xmmword ptr [rax-68h], xmm8
0x14000f599  movaps  xmmword ptr [rax-78h], xmm9
0x14000f59e  movaps  xmmword ptr [rax-88h], xmm10
0x14000f5a6  movaps  xmmword ptr [rax-98h], xmm11
0x14000f5ae  mov     rax, cs:__security_cookie
0x14000f5b5  xor     rax, rsp
0x14000f5b8  mov     [rbp+760h+var_A0], rax
0x14000f5bf  mov     rax, [rbp+760h+arg_28]
0x14000f5c6  lea     rcx, aSchedulerenewa; "ScheduleRenewalWork"
0x14000f5cd  mov     r15, [rbp+760h+arg_30]
0x14000f5d4  xor     r12d, r12d
0x14000f5d7  mov     rbx, [rbp+760h+arg_20]
0x14000f5de  xorps   xmm0, xmm0
0x14000f5e1  mov     [rsp+860h+Data], r12d; Data
0x14000f5e6  xorps   xmm1, xmm1
0x14000f5e9  mov     [rbp+760h+var_760], rcx
0x14000f5ed  lea     rcx, [rsp+860h+var_7F0]
0x14000f5f2  lea     edi, [r12+1]
0x14000f5f7  mov     r14d, r9d
0x14000f5fa  mov     [rsp+860h+var_808], edi; int
0x14000f5fe  lea     r9, [rbp+760h+var_7B0]; int
0x14000f602  mov     [rsp+860h+var_810], edi; int
0x14000f606  mov     [rsp+860h+var_818], edi; int
0x14000f60a  mov     [rsp+860h+var_820], r12d; int
0x14000f60f  mov     [rsp+860h+var_828], r15; unsigned __int16 *
0x14000f614  mov     [rsp+860h+var_830], rax; unsigned __int16 *
0x14000f619  lea     rax, aWindirSystem32_1; "%windir%\\system32\\deviceenroller.exe "
0x14000f620  mov     [rsp+860h+var_838], rax; unsigned __int16 *
0x14000f625  mov     [rsp+860h+var_840], rdx; unsigned __int16 *
0x14000f62a  lea     rdx, [rbp+760h+var_7A8]; int
0x14000f62e  mov     esi, r8d
0x14000f631  lea     r8, [rbp+760h+var_7D8]; int
0x14000f635  mov     [rbp+760h+var_758], rcx
0x14000f639  lea     rcx, [rbp+760h+var_768]; int
0x14000f63d  mov     [rsp+860h+var_7F0], r12d
0x14000f642  mov     qword ptr [rbp+760h+var_768], r12
0x14000f646  mov     qword ptr [rbp+760h+var_7A8], r12
0x14000f64a  mov     qword ptr [rbp+760h+var_7D8], r12
0x14000f64e  mov     qword ptr [rbp+760h+var_7B0], r12
0x14000f652  mov     [rbp+760h+var_7C0], r12
0x14000f656  mov     [rbp+760h+var_7B8], r12
0x14000f65a  mov     [rbp+760h+var_7C8], r12
0x14000f65e  mov     [rbp+760h+var_770], r12
0x14000f662  mov     [rsp+860h+var_7E8], r12
0x14000f667  mov     dword ptr [rbp+760h+var_7E0], r12d
0x14000f66b  movups  xmmword ptr [rbp+760h+var_788], xmm0
0x14000f66f  movups  xmmword ptr [rbp+760h+pvarg], xmm1
0x14000f673  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x14000f678  mov     [rsp+860h+var_7F0], eax
0x14000f67c  test    eax, eax
0x14000f67e  js      loc_14000FBC1
0x14000f684  mov     rcx, qword ptr [rbp+760h+var_7B0]
0x14000f688  or      r13d, 0FFFFFFFFh
0x14000f68c  mov     edx, r13d
0x14000f68f  mov     rax, [rcx]
0x14000f692  mov     rax, [rax+0D0h]
0x14000f699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f69e  mov     [rsp+860h+var_7F0], eax
0x14000f6a2  test    eax, eax
0x14000f6a4  js      loc_14000FBC1
0x14000f6aa  mov     rcx, qword ptr [rbp+760h+var_7D8]
0x14000f6ae  lea     rdx, [rbp+760h+var_7C0]
0x14000f6b2  mov     rax, [rcx]
0x14000f6b5  mov     rax, [rax+48h]
0x14000f6b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f6be  mov     [rsp+860h+var_7F0], eax
0x14000f6c2  test    eax, eax
0x14000f6c4  js      loc_14000FBC1
0x14000f6ca  mov     rcx, [rbp+760h+var_7C0]
0x14000f6ce  lea     r8, [rbp+760h+var_7B8]
0x14000f6d2  mov     edx, edi
0x14000f6d4  mov     rax, [rcx]
0x14000f6d7  mov     rax, [rax+50h]
0x14000f6db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f6e0  mov     [rsp+860h+var_7F0], eax
0x14000f6e4  test    eax, eax
0x14000f6e6  js      loc_14000FBC1
0x14000f6ec  mov     rcx, [rbp+760h+var_7B8]
0x14000f6f0  lea     r8, [rbp+760h+var_7C8]
0x14000f6f4  lea     rdx, IID_ITimeTrigger
0x14000f6fb  mov     rax, [rcx]
0x14000f6fe  mov     rax, [rax]
0x14000f701  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f706  mov     [rsp+860h+var_7F0], eax
0x14000f70a  test    eax, eax
0x14000f70c  js      loc_14000FBC1
0x14000f712  lea     rdx, [rbp+760h+var_6D0]; unsigned __int16 *
0x14000f719  mov     rcx, rbx; struct _SYSTEMTIME *
0x14000f71c  call    ?CreateDelayTimeString@@YAJPEAU_SYSTEMTIME@@PEAGK@Z; CreateDelayTimeString(_SYSTEMTIME *,ushort *,ulong)
0x14000f721  mov     [rsp+860h+var_7F0], eax
0x14000f725  test    eax, eax
0x14000f727  js      loc_14000FBC1
0x14000f72d  mov     rbx, [rbp+760h+var_7C8]
0x14000f731  lea     rdx, [rbp+760h+var_6D0]; unsigned __int16 *
0x14000f738  lea     rcx, [rbp+760h+Block]; this
0x14000f73c  mov     rax, [rbx]
0x14000f73f  mov     rdi, [rax+78h]
0x14000f743  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14000f748  mov     rdx, [rax]
0x14000f74b  test    rdx, rdx
0x14000f74e  jz      short loc_14000F755
0x14000f750  mov     rdx, [rdx]
0x14000f753  jmp     short loc_14000F758
0x14000f755  mov     rdx, r12
0x14000f758  mov     rcx, rbx
0x14000f75b  mov     rax, rdi
0x14000f75e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f763  mov     rbx, [rbp+760h+Block]
0x14000f767  mov     [rsp+860h+var_7F0], eax
0x14000f76b  test    rbx, rbx
0x14000f76e  jz      short loc_14000F7B2
0x14000f770  mov     eax, r13d
0x14000f773  lock xadd [rbx+10h], eax
0x14000f778  add     eax, r13d
0x14000f77b  jnz     short loc_14000F7B2
0x14000f77d  test    rbx, rbx
0x14000f780  jz      short loc_14000F7B2
0x14000f782  mov     rcx, [rbx]; bstrString
0x14000f785  test    rcx, rcx
0x14000f788  jz      short loc_14000F793
0x14000f78a  call    cs:__imp_SysFreeString
0x14000f790  mov     [rbx], r12
0x14000f793  mov     rcx, [rbx+8]; Block
0x14000f797  test    rcx, rcx
0x14000f79a  jz      short loc_14000F7A5
0x14000f79c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000f7a1  mov     [rbx+8], r12
0x14000f7a5  mov     edx, 18h
0x14000f7aa  mov     rcx, rbx; Block
0x14000f7ad  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000f7b2  cmp     [rsp+860h+var_7F0], r12d
0x14000f7b7  jl      loc_14000FBC1
0x14000f7bd  mov     rcx, [rbp+760h+var_7C8]
0x14000f7c1  lea     rdx, [rsp+860h+var_7E8]
0x14000f7c6  mov     rax, [rcx]
0x14000f7c9  mov     rax, [rax+50h]
0x14000f7cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f7d2  mov     [rsp+860h+var_7F0], eax
0x14000f7d6  test    eax, eax
0x14000f7d8  js      loc_14000FBC1
0x14000f7de  mov     rcx, [rsp+860h+var_7E8]
0x14000f7e3  test    esi, esi
0x14000f7e5  jz      loc_14000F922
0x14000f7eb  mov     rax, [rcx]
0x14000f7ee  mov     edx, r13d
0x14000f7f1  mov     rax, [rax+60h]
0x14000f7f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f7fa  mov     [rsp+860h+var_7F0], eax
0x14000f7fe  test    eax, eax
0x14000f800  js      loc_14000FBC1
0x14000f806  mov     rcx, r14
0x14000f809  lea     rdx, [rbp+760h+var_7E0]; unsigned int *
0x14000f80d  imul    rcx, rsi; unsigned __int64
0x14000f811  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x14000f816  mov     [rsp+860h+var_7F0], eax
0x14000f81a  test    eax, eax
0x14000f81c  js      loc_14000FBC1
0x14000f822  mov     r8d, dword ptr [rbp+760h+var_7E0]
0x14000f826  mov     eax, 88888889h
0x14000f82b  mul     r8d
0x14000f82e  mov     dword ptr [rbp+760h+pvarg], r12d
0x14000f832  mov     r9d, edx
0x14000f835  mov     [rsp+860h+var_7F0], r12d
0x14000f83a  shr     r9d, 5
0x14000f83e  movzx   eax, r9w
0x14000f842  imul    ecx, eax, 3Ch ; '<'
0x14000f845  mov     eax, 0AAAAAAABh
0x14000f84a  mul     r9d
0x14000f84d  sub     r8w, cx
0x14000f851  shr     edx, 4
0x14000f854  movzx   eax, dx
0x14000f857  mov     word ptr [rbp+760h+pvarg+6], dx
0x14000f85b  add     ax, ax
0x14000f85e  mov     word ptr [rbp+760h+pvarg+0Ah], r8w
0x14000f863  lea     ecx, [rax+rdx]
0x14000f866  shl     cx, 3
0x14000f86a  lea     rdx, [rbp+760h+var_4C0]
0x14000f871  sub     r9w, cx
0x14000f875  lea     rcx, [rbp+760h+pvarg]
0x14000f879  mov     word ptr [rbp+760h+pvarg+8], r9w
0x14000f87e  call    CreateScheduleTimeString
0x14000f883  mov     [rsp+860h+var_7F0], eax
0x14000f887  test    eax, eax
0x14000f889  js      loc_14000FBC1
0x14000f88f  mov     rbx, [rsp+860h+var_7E8]
0x14000f894  lea     rdx, [rbp+760h+var_4C0]; unsigned __int16 *
0x14000f89b  lea     rcx, [rbp+760h+Block]; this
0x14000f89f  mov     rax, [rbx]
0x14000f8a2  mov     rdi, [rax+50h]
0x14000f8a6  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14000f8ab  mov     rdx, [rax]
0x14000f8ae  test    rdx, rdx
0x14000f8b1  jz      short loc_14000F8B8
0x14000f8b3  mov     rdx, [rdx]
0x14000f8b6  jmp     short loc_14000F8BB
0x14000f8b8  mov     rdx, r12
0x14000f8bb  mov     rcx, rbx
0x14000f8be  mov     rax, rdi
0x14000f8c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f8c6  mov     rbx, [rbp+760h+Block]
0x14000f8ca  mov     [rsp+860h+var_7F0], eax
0x14000f8ce  test    rbx, rbx
0x14000f8d1  jz      short loc_14000F915
0x14000f8d3  mov     eax, r13d
0x14000f8d6  lock xadd [rbx+10h], eax
0x14000f8db  add     eax, r13d
0x14000f8de  jnz     short loc_14000F915
0x14000f8e0  test    rbx, rbx
0x14000f8e3  jz      short loc_14000F915
0x14000f8e5  mov     rcx, [rbx]; bstrString
0x14000f8e8  test    rcx, rcx
0x14000f8eb  jz      short loc_14000F8F6
0x14000f8ed  call    cs:__imp_SysFreeString
0x14000f8f3  mov     [rbx], r12
0x14000f8f6  mov     rcx, [rbx+8]; Block
0x14000f8fa  test    rcx, rcx
0x14000f8fd  jz      short loc_14000F908
0x14000f8ff  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000f904  mov     [rbx+8], r12
0x14000f908  mov     edx, 18h
0x14000f90d  mov     rcx, rbx; Block
0x14000f910  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000f915  cmp     [rsp+860h+var_7F0], r12d
0x14000f91a  jl      loc_14000FBC1
0x14000f920  jmp     short loc_14000F93C
0x14000f922  mov     r8, [rcx]
0x14000f925  xor     edx, edx
0x14000f927  mov     rax, [r8+60h]
0x14000f92b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f930  mov     [rsp+860h+var_7F0], eax
0x14000f934  test    eax, eax
0x14000f936  js      loc_14000FBC1
0x14000f93c  mov     eax, 88888889h
0x14000f941  mov     dword ptr [rbp+760h+var_788], r12d
0x14000f945  mul     r14d
0x14000f948  mov     eax, 0AAAAAAABh
0x14000f94d  mov     [rsp+860h+var_7F0], r12d
0x14000f952  mov     r9d, edx
0x14000f955  shr     r9d, 5
0x14000f959  mul     r9d
0x14000f95c  movzx   ecx, r9w
0x14000f960  shr     edx, 4
0x14000f963  imul    r8d, ecx, 3Ch ; '<'
0x14000f967  movzx   eax, dx
0x14000f96a  add     ax, ax
0x14000f96d  mov     word ptr [rbp+760h+var_788+6], dx
0x14000f971  lea     ecx, [rax+rdx]
0x14000f974  sub     r14w, r8w
0x14000f978  shl     cx, 3
0x14000f97c  lea     rdx, [rbp+760h+var_2B0]
0x14000f983  sub     r9w, cx
0x14000f987  mov     word ptr [rbp+760h+var_788+0Ah], r14w
0x14000f98c  lea     rcx, [rbp+760h+var_788]
0x14000f990  mov     word ptr [rbp+760h+var_788+8], r9w
0x14000f995  call    CreateScheduleTimeString
0x14000f99a  mov     [rsp+860h+var_7F0], eax
0x14000f99e  test    eax, eax
0x14000f9a0  js      loc_14000FBC1
0x14000f9a6  mov     rbx, [rsp+860h+var_7E8]
0x14000f9ab  lea     rdx, [rbp+760h+var_2B0]; unsigned __int16 *
0x14000f9b2  lea     rcx, [rbp+760h+Block]; this
0x14000f9b6  mov     rax, [rbx]
0x14000f9b9  mov     rdi, [rax+40h]
0x14000f9bd  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14000f9c2  mov     rdx, [rax]
0x14000f9c5  test    rdx, rdx
0x14000f9c8  jz      short loc_14000F9CF
0x14000f9ca  mov     rdx, [rdx]
0x14000f9cd  jmp     short loc_14000F9D2
0x14000f9cf  mov     rdx, r12
0x14000f9d2  mov     rcx, rbx
0x14000f9d5  mov     rax, rdi
0x14000f9d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f9dd  mov     rbx, [rbp+760h+Block]
0x14000f9e1  mov     [rsp+860h+var_7F0], eax
0x14000f9e5  test    rbx, rbx
0x14000f9e8  jz      short loc_14000FA2C
0x14000f9ea  mov     eax, r13d
0x14000f9ed  lock xadd [rbx+10h], eax
0x14000f9f2  add     eax, r13d
0x14000f9f5  jnz     short loc_14000FA2C
0x14000f9f7  test    rbx, rbx
0x14000f9fa  jz      short loc_14000FA2C
0x14000f9fc  mov     rcx, [rbx]; bstrString
0x14000f9ff  test    rcx, rcx
0x14000fa02  jz      short loc_14000FA0D
0x14000fa04  call    cs:__imp_SysFreeString
  ... truncated ...
```
