# ScheduleDeviceEnrollerOnLogin

- ea: `0x18000cfc4`
- end: `0x18000d587`
- name: `ScheduleDeviceEnrollerOnLogin`
- size: `1475`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000e7f0`

## callees

- `0x180001cc8`
- `0x180007258`
- `0x1800072d0`
- `0x180007364`
- `0x1800077a0`
- `0x1800079e8`
- `0x1800086c4`
- `0x180008bd4`
- `0x18000cfc4`
- `0x18001b9d8`
- `0x18001bde0`
- `0x18001e010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000d2e0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d457`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d2e0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d457`
- `OLEAUT32!__imp_VariantInit` at `0x18000d1e6`
- `OLEAUT32!__imp_VariantInit` at `0x18000d1ff`
- `OLEAUT32!__imp_VariantInit` at `0x18000d21a`
- `OLEAUT32!__imp_VariantInit` at `0x18000d339`
- `OLEAUT32!__imp_VariantInit` at `0x18000d354`
- `OLEAUT32!__imp_VariantInit` at `0x18000d388`
- `OLEAUT32!__imp_VariantInit` at `0x18000d1e6`
- `OLEAUT32!__imp_VariantInit` at `0x18000d1ff`
- `OLEAUT32!__imp_VariantInit` at `0x18000d21a`
- `OLEAUT32!__imp_VariantInit` at `0x18000d339`
- `OLEAUT32!__imp_VariantInit` at `0x18000d354`
- `OLEAUT32!__imp_VariantInit` at `0x18000d388`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000d539`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000d539`

## string_xrefs

- `0x18000d3a3`: `Login Schedule created by enrollment client`
- `0x18000d0b5`: `%windir%\system32\deviceenroller.exe `
- `0x18000cfe9`: `ScheduleDeviceEnrollerOnLogin`
- `0x18000d22b`: `First Login Schedule created by enrollment client`

## pseudocode

```c
__int64 __fastcall ScheduleDeviceEnrollerOnLogin(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        int a5,
        int a6)
{
  unsigned int v9; // ebx
  int v10; // edi
  unsigned __int16 *v11; // rax
  struct IUnknown *v12; // rbx
  struct IUnknownVtbl *lpVtbl; // rax
  ULONG (__stdcall *Release)(IUnknown *); // rsi
  __int128 v15; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  __int128 v17; // xmm8
  IRecordInfo *v18; // xmm9_8
  __int128 v19; // xmm10
  __int64 v20; // rdi
  IRecordInfo *v21; // xmm11_8
  _bstr_t *v22; // rax
  __int64 v23; // rdx
  int v24; // eax
  const struct std::nothrow_t *v25; // rdx
  BSTR *v26; // rbx
  BSTR v27; // rcx
  VARIANTARG *p_pvarg; // rcx
  ULONG (__stdcall *v29)(IUnknown *); // r15
  __int128 v30; // xmm8
  IRecordInfo *v31; // xmm9_8
  IRecordInfo *v32; // xmm11_8
  __int128 v33; // xmm10
  VARIANTARG *v34; // rax
  int v35; // esi
  __int128 v36; // xmm6
  __int64 v37; // r14
  IRecordInfo *v38; // xmm7_8
  _bstr_t *v39; // rax
  __int64 v40; // rdx
  int v41; // eax
  const struct std::nothrow_t *v42; // rdx
  BSTR *v43; // rbx
  BSTR v44; // rcx
  CEnrollmentLogger *Logger; // rax
  __int64 v47; // [rsp+48h] [rbp-C0h]
  __int64 v48; // [rsp+78h] [rbp-90h] BYREF
  void *v49; // [rsp+80h] [rbp-88h] BYREF
  __int64 v50; // [rsp+88h] [rbp-80h] BYREF
  struct IUnknown *v51[2]; // [rsp+90h] [rbp-78h] BYREF
  __int64 v52; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v53; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v54; // [rsp+B0h] [rbp-58h] BYREF
  __int64 (__fastcall ***v55)(_QWORD, GUID *, __int64 *); // [rsp+B8h] [rbp-50h] BYREF
  __int64 v56; // [rsp+C0h] [rbp-48h] BYREF
  LPVOID v57; // [rsp+C8h] [rbp-40h] BYREF
  VARIANTARG v58; // [rsp+D0h] [rbp-38h] BYREF
  VARIANTARG pvarg; // [rsp+E8h] [rbp-20h] BYREF
  VARIANTARG v60; // [rsp+100h] [rbp-8h] BYREF
  __int128 v61; // [rsp+118h] [rbp+10h] BYREF
  IRecordInfo *v62; // [rsp+128h] [rbp+20h]
  __int128 v63; // [rsp+138h] [rbp+30h] BYREF
  IRecordInfo *v64; // [rsp+148h] [rbp+40h]
  __int128 v65; // [rsp+158h] [rbp+50h] BYREF
  IRecordInfo *v66; // [rsp+168h] [rbp+60h]
  _QWORD v67[2]; // [rsp+178h] [rbp+70h] BYREF
  _BYTE v68[136]; // [rsp+188h] [rbp+80h] BYREF
  int v69; // [rsp+270h] [rbp+168h] BYREF

  v69 = 0;
  v67[1] = &v69;
  v67[0] = "ScheduleDeviceEnrollerOnLogin";
  a6 = 0;
  v69 = AutoCoInitialize::CoInitializeEx((AutoCoInitialize *)&a6, (unsigned int)a2);
  v9 = v69;
  if ( (int)(v69 + 0x80000000) < 0 || v69 == -2147417850 )
  {
    v10 = 1;
    v57 = 0;
    v11 = L"S-1-5-32-545";
    LODWORD(v47) = 0;
    v51[0] = 0;
    v48 = 0;
    if ( a3 )
      v11 = (unsigned __int16 *)a3;
    v56 = 0;
    v50 = 0;
    v55 = 0;
    v54 = 0;
    v53 = 0;
    v52 = 0;
    v69 = CreateTask(&v57, v51, &v48, &v56, a1, L"%windir%\\system32\\deviceenroller.exe ", a2, v11, v47, 0, 1, 1, 1);
    if ( v69 >= 0 )
    {
      v69 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v48 + 72LL))(v48, &v50);
      if ( v69 >= 0 )
      {
        v69 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v50 + 80LL))(v50, 9, &v55);
        if ( v69 >= 0 )
        {
          v69 = (**v55)(v55, &IID_ILogonTrigger, &v54);
          if ( v69 >= 0 )
          {
            v69 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v54 + 80LL))(v54, &v52);
            if ( v69 >= 0 )
            {
              v69 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v52 + 96LL))(v52, 0);
              if ( v69 >= 0 )
              {
                v69 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v48 + 80LL))(v48, v50);
                if ( v69 >= 0 )
                {
                  v12 = v51[0];
                  lpVtbl = v51[0]->lpVtbl;
                  if ( a5 )
                  {
                    Release = lpVtbl[5].Release;
                    VariantInit(&pvarg);
                    v15 = *(_OWORD *)&pvarg.vt;
                    pRecInfo = pvarg.pRecInfo;
                    VariantInit(&v58);
                    v17 = *(_OWORD *)&v58.vt;
                    v18 = v58.pRecInfo;
                    VariantInit(&v60);
                    v19 = *(_OWORD *)&v60.vt;
                    v20 = v48;
                    v21 = v60.pRecInfo;
                    v22 = _bstr_t::_bstr_t((_bstr_t *)&v49, L"First Login Schedule created by enrollment client");
                    if ( *(_QWORD *)v22 )
                      v23 = **(_QWORD **)v22;
                    else
                      v23 = 0;
                    v61 = v15;
                    v62 = pRecInfo;
                    v63 = v17;
                    v64 = v18;
                    v65 = v19;
                    v66 = v21;
                    v24 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))Release)(
                            v12,
                            v23,
                            v20,
                            6,
                            &v65,
                            &v63,
                            3,
                            &v61,
                            &v53);
                    v26 = (BSTR *)v49;
                    v69 = v24;
                    if ( v49 )
                    {
                      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v49 + 4, 0xFFFFFFFF) == 1 && v26 )
                      {
                        if ( *v26 )
                        {
                          SysFreeString(*v26);
                          *v26 = 0;
                        }
                        v27 = v26[1];
                        if ( v27 )
                        {
                          operator delete(v27, v25);
                          v26[1] = 0;
                        }
                        operator delete(v26, (const struct std::nothrow_t *)0x18);
                      }
                      v49 = 0;
                    }
                    _variant_t::~_variant_t((_variant_t *)&v60);
                    _variant_t::~_variant_t((_variant_t *)&v58);
                    p_pvarg = &pvarg;
                  }
                  else
                  {
                    v29 = lpVtbl[5].Release;
                    VariantInit(&v58);
                    v30 = *(_OWORD *)&v58.vt;
                    v31 = v58.pRecInfo;
                    VariantInit(&pvarg);
                    v32 = pvarg.pRecInfo;
                    v33 = *(_OWORD *)&pvarg.vt;
                    if ( a3 )
                    {
                      v34 = (VARIANTARG *)_variant_t::_variant_t((_variant_t *)v68, a3);
                      v35 = 0;
                    }
                    else
                    {
                      VariantInit(&v60);
                      v34 = &v60;
                      v10 = 0;
                      v35 = 2;
                    }
                    v36 = *(_OWORD *)&v34->vt;
                    v37 = v48;
                    v38 = v34->pRecInfo;
                    v39 = _bstr_t::_bstr_t((_bstr_t *)&v49, L"Login Schedule created by enrollment client");
                    if ( *(_QWORD *)v39 )
                      v40 = **(_QWORD **)v39;
                    else
                      v40 = 0;
                    v65 = v30;
                    v66 = v31;
                    v63 = v33;
                    v64 = v32;
                    v61 = v36;
                    v62 = v38;
                    v41 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))v29)(
                            v12,
                            v40,
                            v37,
                            6,
                            &v61,
                            &v63,
                            3,
                            &v65,
                            &v53);
                    v43 = (BSTR *)v49;
                    v69 = v41;
                    if ( v49 )
                    {
                      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v49 + 4, 0xFFFFFFFF) == 1 && v43 )
                      {
                        if ( *v43 )
                        {
                          SysFreeString(*v43);
                          *v43 = 0;
                        }
                        v44 = v43[1];
                        if ( v44 )
                        {
                          operator delete(v44, v42);
                          v43[1] = 0;
                        }
                        operator delete(v43, (const struct std::nothrow_t *)0x18);
                      }
                      v49 = 0;
                    }
                    if ( v35 )
                      _variant_t::~_variant_t((_variant_t *)&v60);
                    if ( v10 )
                      _variant_t::~_variant_t((_variant_t *)v68);
                    _variant_t::~_variant_t((_variant_t *)&pvarg);
                    p_pvarg = &v58;
                  }
                  _variant_t::~_variant_t((_variant_t *)p_pvarg);
                  if ( v69 < 0 )
                  {
                    Logger = CEnrollmentLogger::GetLogger();
                    CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(Logger, v69, "ScheduleDeviceEnrollerOnLogin");
                  }
                }
              }
            }
          }
        }
      }
    }
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v52);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v53);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v54);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v55);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v50);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v56);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v48);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(v51);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v57);
    v9 = v69;
  }
  if ( a6 )
    CoUninitialize();
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v67);
  return v9;
}

```

## disassembly

```asm
0x18000cfc4  mov     rax, rsp
0x18000cfc7  mov     [rax+20h], r9d
0x18000cfcb  push    rbp
0x18000cfcc  push    rbx
0x18000cfcd  push    rsi
0x18000cfce  push    rdi
0x18000cfcf  push    r12
0x18000cfd1  push    r13
0x18000cfd3  push    r14
0x18000cfd5  push    r15
0x18000cfd7  lea     rbp, [rax-148h]
0x18000cfde  sub     rsp, 208h
0x18000cfe5  movaps  xmmword ptr [rax-58h], xmm6
0x18000cfe9  lea     r13, aScheduledevice; "ScheduleDeviceEnrollerOnLogin"
0x18000cff0  movaps  xmmword ptr [rax-68h], xmm7
0x18000cff4  mov     r15, rcx
0x18000cff7  movaps  xmmword ptr [rax-78h], xmm8
0x18000cffc  lea     rcx, [rbp+140h+arg_28]; this
0x18000d003  movaps  xmmword ptr [rax-88h], xmm9
0x18000d00b  xor     r12d, r12d
0x18000d00e  movaps  xmmword ptr [rax-98h], xmm10
0x18000d016  mov     rsi, r8
0x18000d019  movaps  xmmword ptr [rax-0A8h], xmm11
0x18000d021  mov     r14, rdx
0x18000d024  lea     rax, [rbp+140h+arg_18]
0x18000d02b  mov     [rbp+140h+arg_18], r12d
0x18000d032  mov     [rbp+140h+var_C8], rax
0x18000d036  mov     [rbp+140h+var_D0], r13
0x18000d03a  mov     [rbp+140h+arg_28], r12d
0x18000d041  call    ?CoInitializeEx@AutoCoInitialize@@QEAAJK@Z; AutoCoInitialize::CoInitializeEx(ulong)
0x18000d046  mov     ecx, 80000000h
0x18000d04b  mov     [rbp+140h+arg_18], eax
0x18000d051  mov     ebx, eax
0x18000d053  add     eax, ecx
0x18000d055  test    ecx, eax
0x18000d057  jnz     short loc_18000D065
0x18000d059  cmp     ebx, 80010106h
0x18000d05f  jnz     loc_18000D530
0x18000d065  mov     edi, 1
0x18000d06a  mov     [rbp+140h+var_180], r12
0x18000d06e  mov     [rsp+240h+var_1E0], edi
0x18000d072  lea     rax, aS1532545; "S-1-5-32-545"
0x18000d079  mov     [rsp+240h+var_1E8], edi
0x18000d07d  lea     r9, [rbp+140h+var_188]
0x18000d081  mov     [rsp+240h+var_1F0], edi
0x18000d085  lea     r8, [rsp+240h+var_1D0]
0x18000d08a  mov     [rsp+240h+var_1F8], r12d
0x18000d08f  lea     rdx, [rbp+140h+var_1B8]
0x18000d093  mov     dword ptr [rsp+240h+var_200], r12d
0x18000d098  lea     rcx, [rbp+140h+var_180]
0x18000d09c  test    rsi, rsi
0x18000d09f  mov     [rbp+140h+var_1B8], r12
0x18000d0a3  mov     [rsp+240h+var_1D0], r12
0x18000d0a8  cmovnz  rax, rsi
0x18000d0ac  mov     [rbp+140h+var_188], r12
0x18000d0b0  mov     [rsp+240h+var_208], rax
0x18000d0b5  lea     rax, aWindirSystem32_1; "%windir%\\system32\\deviceenroller.exe "
0x18000d0bc  mov     [rsp+240h+var_210], r14
0x18000d0c1  mov     [rsp+240h+var_218], rax
0x18000d0c6  mov     [rsp+240h+var_220], r15
0x18000d0cb  mov     [rbp+140h+var_1C0], r12
0x18000d0cf  mov     [rbp+140h+var_190], r12
0x18000d0d3  mov     [rbp+140h+var_198], r12
0x18000d0d7  mov     [rbp+140h+var_1A0], r12
0x18000d0db  mov     [rbp+140h+var_1A8], r12
0x18000d0df  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x18000d0e4  mov     [rbp+140h+arg_18], eax
0x18000d0ea  test    eax, eax
0x18000d0ec  js      loc_18000D4D8
0x18000d0f2  mov     rcx, [rsp+240h+var_1D0]
0x18000d0f7  lea     rdx, [rbp+140h+var_1C0]
0x18000d0fb  mov     rax, [rcx]
0x18000d0fe  mov     rax, [rax+48h]
0x18000d102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d107  mov     [rbp+140h+arg_18], eax
0x18000d10d  test    eax, eax
0x18000d10f  js      loc_18000D4D8
0x18000d115  mov     rcx, [rbp+140h+var_1C0]
0x18000d119  lea     r8, [rbp+140h+var_190]
0x18000d11d  lea     edx, [rdi+8]
0x18000d120  mov     rax, [rcx]
0x18000d123  mov     rax, [rax+50h]
0x18000d127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d12c  mov     [rbp+140h+arg_18], eax
0x18000d132  test    eax, eax
0x18000d134  js      loc_18000D4D8
0x18000d13a  mov     rcx, [rbp+140h+var_190]
0x18000d13e  lea     r8, [rbp+140h+var_198]
0x18000d142  lea     rdx, IID_ILogonTrigger
0x18000d149  mov     rax, [rcx]
0x18000d14c  mov     rax, [rax]
0x18000d14f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d154  mov     [rbp+140h+arg_18], eax
0x18000d15a  test    eax, eax
0x18000d15c  js      loc_18000D4D8
0x18000d162  mov     rcx, [rbp+140h+var_198]
0x18000d166  lea     rdx, [rbp+140h+var_1A8]
0x18000d16a  mov     rax, [rcx]
0x18000d16d  mov     rax, [rax+50h]
0x18000d171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d176  mov     [rbp+140h+arg_18], eax
0x18000d17c  test    eax, eax
0x18000d17e  js      loc_18000D4D8
0x18000d184  mov     rcx, [rbp+140h+var_1A8]
0x18000d188  xor     edx, edx
0x18000d18a  mov     rax, [rcx]
0x18000d18d  mov     rax, [rax+60h]
0x18000d191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d196  mov     [rbp+140h+arg_18], eax
0x18000d19c  test    eax, eax
0x18000d19e  js      loc_18000D4D8
0x18000d1a4  mov     rcx, [rsp+240h+var_1D0]
0x18000d1a9  mov     rdx, [rbp+140h+var_1C0]
0x18000d1ad  mov     rax, [rcx]
0x18000d1b0  mov     rax, [rax+50h]
0x18000d1b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1b9  mov     [rbp+140h+arg_18], eax
0x18000d1bf  test    eax, eax
0x18000d1c1  js      loc_18000D4D8
0x18000d1c7  mov     rbx, [rbp+140h+var_1B8]
0x18000d1cb  mov     rax, [rbx]
0x18000d1ce  cmp     [rbp+140h+arg_20], r12d
0x18000d1d5  jz      loc_18000D32E
0x18000d1db  mov     rsi, [rax+88h]
0x18000d1e2  lea     rcx, [rbp+140h+pvarg]; pvarg
0x18000d1e6  call    cs:__imp_VariantInit
0x18000d1ed  nop     dword ptr [rax+rax+00h]
0x18000d1f2  movups  xmm6, xmmword ptr [rbp+140h+pvarg]
0x18000d1f6  lea     rcx, [rbp+140h+var_178]; pvarg
0x18000d1fa  movsd   xmm7, qword ptr [rbp+140h+pvarg+10h]
0x18000d1ff  call    cs:__imp_VariantInit
0x18000d206  nop     dword ptr [rax+rax+00h]
0x18000d20b  movups  xmm8, xmmword ptr [rbp+140h+var_178]
0x18000d210  lea     rcx, [rbp+140h+var_148]; pvarg
0x18000d214  movsd   xmm9, qword ptr [rbp+140h+var_178+10h]
0x18000d21a  call    cs:__imp_VariantInit
0x18000d221  nop     dword ptr [rax+rax+00h]
0x18000d226  movups  xmm10, xmmword ptr [rbp+140h+var_148]
0x18000d22b  lea     rdx, aFirstLoginSche; "First Login Schedule created by enrollm"...
0x18000d232  mov     rdi, [rsp+240h+var_1D0]
0x18000d237  movsd   xmm11, qword ptr [rbp+140h+var_148+10h]
0x18000d23d  lea     rcx, [rsp+240h+var_1C8]; this
0x18000d242  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000d247  mov     rdx, [rax]
0x18000d24a  test    rdx, rdx
0x18000d24d  jz      short loc_18000D254
0x18000d24f  mov     rdx, [rdx]
0x18000d252  jmp     short loc_18000D257
0x18000d254  mov     rdx, r12
0x18000d257  lea     rax, [rbp+140h+var_1A0]
0x18000d25b  movaps  [rbp+140h+var_130], xmm6
0x18000d25f  mov     [rsp+240h+var_200], rax
0x18000d264  mov     r9d, 6
0x18000d26a  lea     rax, [rbp+140h+var_130]
0x18000d26e  movsd   [rbp+140h+var_120], xmm7
0x18000d273  mov     [rsp+240h+var_208], rax
0x18000d278  mov     r8, rdi
0x18000d27b  lea     rax, [rbp+140h+var_110]
0x18000d27f  mov     dword ptr [rsp+240h+var_210], 3
0x18000d287  mov     [rsp+240h+var_218], rax
0x18000d28c  mov     rcx, rbx
0x18000d28f  lea     rax, [rbp+140h+var_F0]
0x18000d293  movaps  [rbp+140h+var_110], xmm8
0x18000d298  mov     [rsp+240h+var_220], rax
0x18000d29d  mov     rax, rsi
0x18000d2a0  movsd   [rbp+140h+var_100], xmm9
0x18000d2a6  movaps  [rbp+140h+var_F0], xmm10
0x18000d2ab  movsd   [rbp+140h+var_E0], xmm11
0x18000d2b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2b6  mov     rbx, [rsp+240h+var_1C8]
0x18000d2bb  mov     [rbp+140h+arg_18], eax
0x18000d2c1  test    rbx, rbx
0x18000d2c4  jz      short loc_18000D313
0x18000d2c6  or      eax, 0FFFFFFFFh
0x18000d2c9  lock xadd [rbx+10h], eax
0x18000d2ce  cmp     eax, 1
0x18000d2d1  jnz     short loc_18000D30E
0x18000d2d3  test    rbx, rbx
0x18000d2d6  jz      short loc_18000D30E
0x18000d2d8  mov     rcx, [rbx]; bstrString
0x18000d2db  test    rcx, rcx
0x18000d2de  jz      short loc_18000D2EF
0x18000d2e0  call    cs:__imp_SysFreeString
0x18000d2e7  nop     dword ptr [rax+rax+00h]
0x18000d2ec  mov     [rbx], r12
0x18000d2ef  mov     rcx, [rbx+8]; void *
0x18000d2f3  test    rcx, rcx
0x18000d2f6  jz      short loc_18000D301
0x18000d2f8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000d2fd  mov     [rbx+8], r12
0x18000d301  mov     edx, 18h; struct std::nothrow_t *
0x18000d306  mov     rcx, rbx; void *
0x18000d309  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000d30e  mov     [rsp+240h+var_1C8], r12
0x18000d313  lea     rcx, [rbp+140h+var_148]; this
0x18000d317  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18000d31c  lea     rcx, [rbp+140h+var_178]; this
0x18000d320  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18000d325  lea     rcx, [rbp+140h+pvarg]
0x18000d329  jmp     loc_18000D4B4
0x18000d32e  mov     r15, [rax+88h]
0x18000d335  lea     rcx, [rbp+140h+var_178]; pvarg
0x18000d339  call    cs:__imp_VariantInit
0x18000d340  nop     dword ptr [rax+rax+00h]
0x18000d345  movups  xmm8, xmmword ptr [rbp+140h+var_178]
0x18000d34a  lea     rcx, [rbp+140h+pvarg]; pvarg
0x18000d34e  movsd   xmm9, qword ptr [rbp+140h+var_178+10h]
0x18000d354  call    cs:__imp_VariantInit
0x18000d35b  nop     dword ptr [rax+rax+00h]
0x18000d360  movsd   xmm11, qword ptr [rbp+140h+pvarg+10h]
0x18000d366  movups  xmm10, xmmword ptr [rbp+140h+pvarg]
0x18000d36b  test    rsi, rsi
0x18000d36e  jz      short loc_18000D384
0x18000d370  mov     rdx, rsi; unsigned __int16 *
0x18000d373  lea     rcx, [rbp+140h+var_C0]; this
0x18000d37a  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x18000d37f  mov     esi, r12d
0x18000d382  jmp     short loc_18000D3A0
0x18000d384  lea     rcx, [rbp+140h+var_148]; pvarg
0x18000d388  call    cs:__imp_VariantInit
0x18000d38f  nop     dword ptr [rax+rax+00h]
0x18000d394  lea     rax, [rbp+140h+var_148]
0x18000d398  mov     edi, r12d
0x18000d39b  mov     esi, 2
0x18000d3a0  movups  xmm6, xmmword ptr [rax]
0x18000d3a3  lea     rdx, aLoginScheduleC; "Login Schedule created by enrollment cl"...
0x18000d3aa  mov     r14, [rsp+240h+var_1D0]
0x18000d3af  movsd   xmm7, qword ptr [rax+10h]
0x18000d3b4  lea     rcx, [rsp+240h+var_1C8]; this
0x18000d3b9  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000d3be  mov     rcx, [rax]
0x18000d3c1  test    rcx, rcx
0x18000d3c4  jz      short loc_18000D3CB
0x18000d3c6  mov     rdx, [rcx]
0x18000d3c9  jmp     short loc_18000D3CE
0x18000d3cb  mov     rdx, r12
0x18000d3ce  lea     rax, [rbp+140h+var_1A0]
0x18000d3d2  movaps  [rbp+140h+var_F0], xmm8
0x18000d3d7  mov     [rsp+240h+var_200], rax
0x18000d3dc  mov     r9d, 6
0x18000d3e2  lea     rax, [rbp+140h+var_F0]
0x18000d3e6  movsd   [rbp+140h+var_E0], xmm9
0x18000d3ec  mov     [rsp+240h+var_208], rax
0x18000d3f1  mov     r8, r14
0x18000d3f4  lea     rax, [rbp+140h+var_110]
0x18000d3f8  mov     dword ptr [rsp+240h+var_210], 3
0x18000d400  mov     [rsp+240h+var_218], rax
0x18000d405  mov     rcx, rbx
0x18000d408  lea     rax, [rbp+140h+var_130]
0x18000d40c  movaps  [rbp+140h+var_110], xmm10
0x18000d411  mov     [rsp+240h+var_220], rax
0x18000d416  mov     rax, r15
0x18000d419  movsd   [rbp+140h+var_100], xmm11
0x18000d41f  movaps  [rbp+140h+var_130], xmm6
0x18000d423  movsd   [rbp+140h+var_120], xmm7
0x18000d428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d42d  mov     rbx, [rsp+240h+var_1C8]
0x18000d432  mov     [rbp+140h+arg_18], eax
0x18000d438  test    rbx, rbx
0x18000d43b  jz      short loc_18000D48A
0x18000d43d  or      eax, 0FFFFFFFFh
0x18000d440  lock xadd [rbx+10h], eax
0x18000d445  cmp     eax, 1
0x18000d448  jnz     short loc_18000D485
0x18000d44a  test    rbx, rbx
0x18000d44d  jz      short loc_18000D485
0x18000d44f  mov     rcx, [rbx]; bstrString
0x18000d452  test    rcx, rcx
0x18000d455  jz      short loc_18000D466
0x18000d457  call    cs:__imp_SysFreeString
0x18000d45e  nop     dword ptr [rax+rax+00h]
0x18000d463  mov     [rbx], r12
0x18000d466  mov     rcx, [rbx+8]; void *
0x18000d46a  test    rcx, rcx
0x18000d46d  jz      short loc_18000D478
0x18000d46f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000d474  mov     [rbx+8], r12
0x18000d478  mov     edx, 18h; struct std::nothrow_t *
0x18000d47d  mov     rcx, rbx; void *
0x18000d480  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000d485  mov     [rsp+240h+var_1C8], r12
0x18000d48a  test    esi, esi
0x18000d48c  jz      short loc_18000D497
0x18000d48e  lea     rcx, [rbp+140h+var_148]; this
0x18000d492  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18000d497  test    edi, edi
0x18000d499  jz      short loc_18000D4A7
0x18000d49b  lea     rcx, [rbp+140h+var_C0]; this
0x18000d4a2  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18000d4a7  lea     rcx, [rbp+140h+pvarg]; this
0x18000d4ab  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18000d4b0  lea     rcx, [rbp+140h+var_178]; this
0x18000d4b4  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18000d4b9  cmp     [rbp+140h+arg_18], r12d
0x18000d4c0  jge     short loc_18000D4D8
0x18000d4c2  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18000d4c7  mov     edx, [rbp+140h+arg_18]; int
0x18000d4cd  mov     r8, r13; char *
0x18000d4d0  mov     rcx, rax; this
0x18000d4d3  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
  ... truncated ...
```
