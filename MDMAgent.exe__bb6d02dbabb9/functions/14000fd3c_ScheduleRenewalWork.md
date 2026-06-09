# ScheduleRenewalWork

- ea: `0x14000fd3c`
- end: `0x14001045f`
- name: `ScheduleRenewalWork`
- size: `1827`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x14000f9a4`

## callees

- `0x1400029c0`
- `0x1400029e4`
- `0x14000476c`
- `0x140004cd0`
- `0x1400079f8`
- `0x1400091e0`
- `0x140009268`
- `0x1400094e4`
- `0x14000a1a0`
- `0x14000a374`
- `0x14000a51c`
- `0x14000fd3c`
- `0x14001848c`
- `0x140018890`
- `0x14001a010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000ff5a`
- `OLEAUT32!__imp_SysFreeString` at `0x1400100c3`
- `OLEAUT32!__imp_SysFreeString` at `0x1400101e0`
- `OLEAUT32!__imp_SysFreeString` at `0x140010349`
- `OLEAUT32!__imp_SysFreeString` at `0x14000ff5a`
- `OLEAUT32!__imp_SysFreeString` at `0x1400100c3`
- `OLEAUT32!__imp_SysFreeString` at `0x1400101e0`
- `OLEAUT32!__imp_SysFreeString` at `0x140010349`
- `OLEAUT32!__imp_VariantInit` at `0x14001024b`
- `OLEAUT32!__imp_VariantInit` at `0x140010264`
- `OLEAUT32!__imp_VariantInit` at `0x14001024b`
- `OLEAUT32!__imp_VariantInit` at `0x140010264`

## string_xrefs

- `0x14000fde9`: `%windir%\system32\deviceenroller.exe `
- `0x140010299`: `Schedule created by enrollment client for renewal of certificate warning`

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
             (LPVOID *)v63,
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
0x14000fd3c  mov     rax, rsp
0x14000fd3f  mov     [rax+8], rbx
0x14000fd43  push    rbp
0x14000fd44  push    rsi
0x14000fd45  push    rdi
0x14000fd46  push    r12
0x14000fd48  push    r13
0x14000fd4a  push    r14
0x14000fd4c  push    r15
0x14000fd4e  lea     rbp, [rax-768h]
0x14000fd55  sub     rsp, 830h
0x14000fd5c  movaps  xmmword ptr [rax-48h], xmm6
0x14000fd60  movaps  xmmword ptr [rax-58h], xmm7
0x14000fd64  movaps  xmmword ptr [rax-68h], xmm8
0x14000fd69  movaps  xmmword ptr [rax-78h], xmm9
0x14000fd6e  movaps  xmmword ptr [rax-88h], xmm10
0x14000fd76  movaps  xmmword ptr [rax-98h], xmm11
0x14000fd7e  mov     rax, cs:__security_cookie
0x14000fd85  xor     rax, rsp
0x14000fd88  mov     [rbp+760h+var_A0], rax
0x14000fd8f  mov     rax, [rbp+760h+arg_28]
0x14000fd96  lea     rcx, aSchedulerenewa; "ScheduleRenewalWork"
0x14000fd9d  mov     r15, [rbp+760h+arg_30]
0x14000fda4  xor     r12d, r12d
0x14000fda7  mov     rbx, [rbp+760h+arg_20]
0x14000fdae  xorps   xmm0, xmm0
0x14000fdb1  mov     [rsp+860h+Data], r12d; Data
0x14000fdb6  xorps   xmm1, xmm1
0x14000fdb9  mov     [rbp+760h+var_760], rcx
0x14000fdbd  lea     rcx, [rsp+860h+var_7F0]
0x14000fdc2  lea     edi, [r12+1]
0x14000fdc7  mov     r14d, r9d
0x14000fdca  mov     [rsp+860h+var_808], edi; int
0x14000fdce  lea     r9, [rbp+760h+var_7B0]; int
0x14000fdd2  mov     [rsp+860h+var_810], edi; int
0x14000fdd6  mov     [rsp+860h+var_818], edi; int
0x14000fdda  mov     [rsp+860h+var_820], r12d; int
0x14000fddf  mov     [rsp+860h+var_828], r15; unsigned __int16 *
0x14000fde4  mov     [rsp+860h+var_830], rax; unsigned __int16 *
0x14000fde9  lea     rax, aWindirSystem32_1; "%windir%\\system32\\deviceenroller.exe "
0x14000fdf0  mov     [rsp+860h+var_838], rax; unsigned __int16 *
0x14000fdf5  mov     [rsp+860h+var_840], rdx; unsigned __int16 *
0x14000fdfa  lea     rdx, [rbp+760h+var_7A8]; int
0x14000fdfe  mov     esi, r8d
0x14000fe01  lea     r8, [rbp+760h+var_7D8]; int
0x14000fe05  mov     [rbp+760h+var_758], rcx
0x14000fe09  lea     rcx, [rbp+760h+var_768]; int
0x14000fe0d  mov     [rsp+860h+var_7F0], r12d
0x14000fe12  mov     qword ptr [rbp+760h+var_768], r12
0x14000fe16  mov     qword ptr [rbp+760h+var_7A8], r12
0x14000fe1a  mov     qword ptr [rbp+760h+var_7D8], r12
0x14000fe1e  mov     qword ptr [rbp+760h+var_7B0], r12
0x14000fe22  mov     [rbp+760h+var_7C0], r12
0x14000fe26  mov     [rbp+760h+var_7B8], r12
0x14000fe2a  mov     [rbp+760h+var_7C8], r12
0x14000fe2e  mov     [rbp+760h+var_770], r12
0x14000fe32  mov     [rsp+860h+var_7E8], r12
0x14000fe37  mov     dword ptr [rbp+760h+var_7E0], r12d
0x14000fe3b  movups  xmmword ptr [rbp+760h+var_788], xmm0
0x14000fe3f  movups  xmmword ptr [rbp+760h+pvarg], xmm1
0x14000fe43  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x14000fe48  mov     [rsp+860h+var_7F0], eax
0x14000fe4c  test    eax, eax
0x14000fe4e  js      loc_1400103B5
0x14000fe54  mov     rcx, qword ptr [rbp+760h+var_7B0]
0x14000fe58  or      r13d, 0FFFFFFFFh
0x14000fe5c  mov     edx, r13d
0x14000fe5f  mov     rax, [rcx]
0x14000fe62  mov     rax, [rax+0D0h]
0x14000fe69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fe6e  mov     [rsp+860h+var_7F0], eax
0x14000fe72  test    eax, eax
0x14000fe74  js      loc_1400103B5
0x14000fe7a  mov     rcx, qword ptr [rbp+760h+var_7D8]
0x14000fe7e  lea     rdx, [rbp+760h+var_7C0]
0x14000fe82  mov     rax, [rcx]
0x14000fe85  mov     rax, [rax+48h]
0x14000fe89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fe8e  mov     [rsp+860h+var_7F0], eax
0x14000fe92  test    eax, eax
0x14000fe94  js      loc_1400103B5
0x14000fe9a  mov     rcx, [rbp+760h+var_7C0]
0x14000fe9e  lea     r8, [rbp+760h+var_7B8]
0x14000fea2  mov     edx, edi
0x14000fea4  mov     rax, [rcx]
0x14000fea7  mov     rax, [rax+50h]
0x14000feab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000feb0  mov     [rsp+860h+var_7F0], eax
0x14000feb4  test    eax, eax
0x14000feb6  js      loc_1400103B5
0x14000febc  mov     rcx, [rbp+760h+var_7B8]
0x14000fec0  lea     r8, [rbp+760h+var_7C8]
0x14000fec4  lea     rdx, IID_ITimeTrigger
0x14000fecb  mov     rax, [rcx]
0x14000fece  mov     rax, [rax]
0x14000fed1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fed6  mov     [rsp+860h+var_7F0], eax
0x14000feda  test    eax, eax
0x14000fedc  js      loc_1400103B5
0x14000fee2  lea     rdx, [rbp+760h+var_6D0]; unsigned __int16 *
0x14000fee9  mov     rcx, rbx; struct _SYSTEMTIME *
0x14000feec  call    ?CreateDelayTimeString@@YAJPEAU_SYSTEMTIME@@PEAGK@Z; CreateDelayTimeString(_SYSTEMTIME *,ushort *,ulong)
0x14000fef1  mov     [rsp+860h+var_7F0], eax
0x14000fef5  test    eax, eax
0x14000fef7  js      loc_1400103B5
0x14000fefd  mov     rbx, [rbp+760h+var_7C8]
0x14000ff01  lea     rdx, [rbp+760h+var_6D0]; unsigned __int16 *
0x14000ff08  lea     rcx, [rbp+760h+Block]; this
0x14000ff0c  mov     rax, [rbx]
0x14000ff0f  mov     rdi, [rax+78h]
0x14000ff13  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14000ff18  mov     rdx, [rax]
0x14000ff1b  test    rdx, rdx
0x14000ff1e  jz      short loc_14000FF25
0x14000ff20  mov     rdx, [rdx]
0x14000ff23  jmp     short loc_14000FF28
0x14000ff25  mov     rdx, r12
0x14000ff28  mov     rcx, rbx
0x14000ff2b  mov     rax, rdi
0x14000ff2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ff33  mov     rbx, [rbp+760h+Block]
0x14000ff37  mov     [rsp+860h+var_7F0], eax
0x14000ff3b  test    rbx, rbx
0x14000ff3e  jz      short loc_14000FF88
0x14000ff40  mov     eax, r13d
0x14000ff43  lock xadd [rbx+10h], eax
0x14000ff48  add     eax, r13d
0x14000ff4b  jnz     short loc_14000FF88
0x14000ff4d  test    rbx, rbx
0x14000ff50  jz      short loc_14000FF88
0x14000ff52  mov     rcx, [rbx]; bstrString
0x14000ff55  test    rcx, rcx
0x14000ff58  jz      short loc_14000FF69
0x14000ff5a  call    cs:__imp_SysFreeString
0x14000ff61  nop     dword ptr [rax+rax+00h]
0x14000ff66  mov     [rbx], r12
0x14000ff69  mov     rcx, [rbx+8]; Block
0x14000ff6d  test    rcx, rcx
0x14000ff70  jz      short loc_14000FF7B
0x14000ff72  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000ff77  mov     [rbx+8], r12
0x14000ff7b  mov     edx, 18h
0x14000ff80  mov     rcx, rbx; Block
0x14000ff83  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000ff88  cmp     [rsp+860h+var_7F0], r12d
0x14000ff8d  jl      loc_1400103B5
0x14000ff93  mov     rcx, [rbp+760h+var_7C8]
0x14000ff97  lea     rdx, [rsp+860h+var_7E8]
0x14000ff9c  mov     rax, [rcx]
0x14000ff9f  mov     rax, [rax+50h]
0x14000ffa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ffa8  mov     [rsp+860h+var_7F0], eax
0x14000ffac  test    eax, eax
0x14000ffae  js      loc_1400103B5
0x14000ffb4  mov     rcx, [rsp+860h+var_7E8]
0x14000ffb9  test    esi, esi
0x14000ffbb  jz      loc_1400100FE
0x14000ffc1  mov     rax, [rcx]
0x14000ffc4  mov     edx, r13d
0x14000ffc7  mov     rax, [rax+60h]
0x14000ffcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ffd0  mov     [rsp+860h+var_7F0], eax
0x14000ffd4  test    eax, eax
0x14000ffd6  js      loc_1400103B5
0x14000ffdc  mov     rcx, r14
0x14000ffdf  lea     rdx, [rbp+760h+var_7E0]; unsigned int *
0x14000ffe3  imul    rcx, rsi; unsigned __int64
0x14000ffe7  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x14000ffec  mov     [rsp+860h+var_7F0], eax
0x14000fff0  test    eax, eax
0x14000fff2  js      loc_1400103B5
0x14000fff8  mov     r8d, dword ptr [rbp+760h+var_7E0]
0x14000fffc  mov     eax, 88888889h
0x140010001  mul     r8d
0x140010004  mov     dword ptr [rbp+760h+pvarg], r12d
0x140010008  mov     r9d, edx
0x14001000b  mov     [rsp+860h+var_7F0], r12d
0x140010010  shr     r9d, 5
0x140010014  movzx   eax, r9w
0x140010018  imul    ecx, eax, 3Ch ; '<'
0x14001001b  mov     eax, 0AAAAAAABh
0x140010020  mul     r9d
0x140010023  sub     r8w, cx
0x140010027  shr     edx, 4
0x14001002a  movzx   eax, dx
0x14001002d  mov     word ptr [rbp+760h+pvarg+6], dx
0x140010031  add     ax, ax
0x140010034  mov     word ptr [rbp+760h+pvarg+0Ah], r8w
0x140010039  lea     ecx, [rax+rdx]
0x14001003c  shl     cx, 3
0x140010040  lea     rdx, [rbp+760h+var_4C0]
0x140010047  sub     r9w, cx
0x14001004b  lea     rcx, [rbp+760h+pvarg]
0x14001004f  mov     word ptr [rbp+760h+pvarg+8], r9w
0x140010054  call    CreateScheduleTimeString
0x140010059  mov     [rsp+860h+var_7F0], eax
0x14001005d  test    eax, eax
0x14001005f  js      loc_1400103B5
0x140010065  mov     rbx, [rsp+860h+var_7E8]
0x14001006a  lea     rdx, [rbp+760h+var_4C0]; unsigned __int16 *
0x140010071  lea     rcx, [rbp+760h+Block]; this
0x140010075  mov     rax, [rbx]
0x140010078  mov     rdi, [rax+50h]
0x14001007c  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x140010081  mov     rdx, [rax]
0x140010084  test    rdx, rdx
0x140010087  jz      short loc_14001008E
0x140010089  mov     rdx, [rdx]
0x14001008c  jmp     short loc_140010091
0x14001008e  mov     rdx, r12
0x140010091  mov     rcx, rbx
0x140010094  mov     rax, rdi
0x140010097  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001009c  mov     rbx, [rbp+760h+Block]
0x1400100a0  mov     [rsp+860h+var_7F0], eax
0x1400100a4  test    rbx, rbx
0x1400100a7  jz      short loc_1400100F1
0x1400100a9  mov     eax, r13d
0x1400100ac  lock xadd [rbx+10h], eax
0x1400100b1  add     eax, r13d
0x1400100b4  jnz     short loc_1400100F1
0x1400100b6  test    rbx, rbx
0x1400100b9  jz      short loc_1400100F1
0x1400100bb  mov     rcx, [rbx]; bstrString
0x1400100be  test    rcx, rcx
0x1400100c1  jz      short loc_1400100D2
0x1400100c3  call    cs:__imp_SysFreeString
0x1400100ca  nop     dword ptr [rax+rax+00h]
0x1400100cf  mov     [rbx], r12
0x1400100d2  mov     rcx, [rbx+8]; Block
0x1400100d6  test    rcx, rcx
0x1400100d9  jz      short loc_1400100E4
0x1400100db  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400100e0  mov     [rbx+8], r12
0x1400100e4  mov     edx, 18h
0x1400100e9  mov     rcx, rbx; Block
0x1400100ec  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400100f1  cmp     [rsp+860h+var_7F0], r12d
0x1400100f6  jl      loc_1400103B5
0x1400100fc  jmp     short loc_140010118
0x1400100fe  mov     r8, [rcx]
0x140010101  xor     edx, edx
0x140010103  mov     rax, [r8+60h]
0x140010107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001010c  mov     [rsp+860h+var_7F0], eax
0x140010110  test    eax, eax
0x140010112  js      loc_1400103B5
0x140010118  mov     eax, 88888889h
0x14001011d  mov     dword ptr [rbp+760h+var_788], r12d
0x140010121  mul     r14d
0x140010124  mov     eax, 0AAAAAAABh
0x140010129  mov     [rsp+860h+var_7F0], r12d
0x14001012e  mov     r9d, edx
0x140010131  shr     r9d, 5
0x140010135  mul     r9d
0x140010138  movzx   ecx, r9w
0x14001013c  shr     edx, 4
0x14001013f  imul    r8d, ecx, 3Ch ; '<'
0x140010143  movzx   eax, dx
0x140010146  add     ax, ax
0x140010149  mov     word ptr [rbp+760h+var_788+6], dx
0x14001014d  lea     ecx, [rax+rdx]
0x140010150  sub     r14w, r8w
0x140010154  shl     cx, 3
0x140010158  lea     rdx, [rbp+760h+var_2B0]
0x14001015f  sub     r9w, cx
0x140010163  mov     word ptr [rbp+760h+var_788+0Ah], r14w
0x140010168  lea     rcx, [rbp+760h+var_788]
0x14001016c  mov     word ptr [rbp+760h+var_788+8], r9w
0x140010171  call    CreateScheduleTimeString
0x140010176  mov     [rsp+860h+var_7F0], eax
0x14001017a  test    eax, eax
0x14001017c  js      loc_1400103B5
0x140010182  mov     rbx, [rsp+860h+var_7E8]
0x140010187  lea     rdx, [rbp+760h+var_2B0]; unsigned __int16 *
0x14001018e  lea     rcx, [rbp+760h+Block]; this
0x140010192  mov     rax, [rbx]
0x140010195  mov     rdi, [rax+40h]
0x140010199  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14001019e  mov     rdx, [rax]
0x1400101a1  test    rdx, rdx
0x1400101a4  jz      short loc_1400101AB
0x1400101a6  mov     rdx, [rdx]
0x1400101a9  jmp     short loc_1400101AE
0x1400101ab  mov     rdx, r12
0x1400101ae  mov     rcx, rbx
0x1400101b1  mov     rax, rdi
0x1400101b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400101b9  mov     rbx, [rbp+760h+Block]
0x1400101bd  mov     [rsp+860h+var_7F0], eax
0x1400101c1  test    rbx, rbx
0x1400101c4  jz      short loc_14001020E
0x1400101c6  mov     eax, r13d
0x1400101c9  lock xadd [rbx+10h], eax
0x1400101ce  add     eax, r13d
0x1400101d1  jnz     short loc_14001020E
0x1400101d3  test    rbx, rbx
0x1400101d6  jz      short loc_14001020E
0x1400101d8  mov     rcx, [rbx]; bstrString
0x1400101db  test    rcx, rcx
  ... truncated ...
```
