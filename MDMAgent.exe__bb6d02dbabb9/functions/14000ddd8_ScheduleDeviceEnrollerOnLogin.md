# ScheduleDeviceEnrollerOnLogin

- ea: `0x14000ddd8`
- end: `0x14000e39b`
- name: `ScheduleDeviceEnrollerOnLogin`
- size: `1475`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, unsigned __int16 *@<rdx>, unsigned __int16 *@<r8>, int, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x14000f604`

## callees

- `0x1400029e4`
- `0x14000476c`
- `0x140004cd0`
- `0x1400091e0`
- `0x140009268`
- `0x1400094e4`
- `0x14000a134`
- `0x14000a51c`
- `0x14000ddd8`
- `0x14001848c`
- `0x140018890`
- `0x14001a010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000e0f4`
- `OLEAUT32!__imp_SysFreeString` at `0x14000e26b`
- `OLEAUT32!__imp_SysFreeString` at `0x14000e0f4`
- `OLEAUT32!__imp_SysFreeString` at `0x14000e26b`
- `OLEAUT32!__imp_VariantInit` at `0x14000dffa`
- `OLEAUT32!__imp_VariantInit` at `0x14000e013`
- `OLEAUT32!__imp_VariantInit` at `0x14000e02e`
- `OLEAUT32!__imp_VariantInit` at `0x14000e14d`
- `OLEAUT32!__imp_VariantInit` at `0x14000e168`
- `OLEAUT32!__imp_VariantInit` at `0x14000e19c`
- `OLEAUT32!__imp_VariantInit` at `0x14000dffa`
- `OLEAUT32!__imp_VariantInit` at `0x14000e013`
- `OLEAUT32!__imp_VariantInit` at `0x14000e02e`
- `OLEAUT32!__imp_VariantInit` at `0x14000e14d`
- `OLEAUT32!__imp_VariantInit` at `0x14000e168`
- `OLEAUT32!__imp_VariantInit` at `0x14000e19c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000e34d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000e34d`

## string_xrefs

- `0x14000e1b7`: `Login Schedule created by enrollment client`
- `0x14000dec9`: `%windir%\system32\deviceenroller.exe `
- `0x14000ddfd`: `ScheduleDeviceEnrollerOnLogin`
- `0x14000e03f`: `First Login Schedule created by enrollment client`

## pseudocode

```c
__int64 __fastcall ScheduleDeviceEnrollerOnLogin(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        __int64 a4,
        int a5,
        int a6)
{
  unsigned int v9; // ebx
  int v10; // edi
  unsigned __int16 *v11; // rax
  __int64 *v12; // rbx
  __int64 v13; // rax
  __int64 (__fastcall *v14)(__int64 *, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *); // rsi
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
  BSTR *v25; // rbx
  BSTR v26; // rcx
  VARIANTARG *p_pvarg; // rcx
  __int64 (__fastcall *v28)(__int64 *, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *); // r15
  __int128 v29; // xmm8
  IRecordInfo *v30; // xmm9_8
  IRecordInfo *v31; // xmm11_8
  __int128 v32; // xmm10
  VARIANTARG *v33; // rax
  int v34; // esi
  __int128 v35; // xmm6
  __int64 v36; // r14
  IRecordInfo *v37; // xmm7_8
  _bstr_t *v38; // rax
  __int64 v39; // rdx
  int v40; // eax
  BSTR *v41; // rbx
  BSTR v42; // rcx
  CEnrollmentLogger *Logger; // rax
  int v45[2]; // [rsp+78h] [rbp-90h] BYREF
  void *Block; // [rsp+80h] [rbp-88h] BYREF
  __int64 v47; // [rsp+88h] [rbp-80h] BYREF
  int v48[2]; // [rsp+90h] [rbp-78h] BYREF
  __int64 v49; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v50; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v51; // [rsp+B0h] [rbp-58h] BYREF
  __int64 (__fastcall ***v52)(_QWORD, GUID *, __int64 *); // [rsp+B8h] [rbp-50h] BYREF
  int v53[2]; // [rsp+C0h] [rbp-48h] BYREF
  int v54[2]; // [rsp+C8h] [rbp-40h] BYREF
  VARIANTARG v55; // [rsp+D0h] [rbp-38h] BYREF
  VARIANTARG pvarg; // [rsp+E8h] [rbp-20h] BYREF
  VARIANTARG v57; // [rsp+100h] [rbp-8h] BYREF
  __int128 v58; // [rsp+118h] [rbp+10h] BYREF
  IRecordInfo *v59; // [rsp+128h] [rbp+20h]
  __int128 v60; // [rsp+138h] [rbp+30h] BYREF
  IRecordInfo *v61; // [rsp+148h] [rbp+40h]
  __int128 v62; // [rsp+158h] [rbp+50h] BYREF
  IRecordInfo *v63; // [rsp+168h] [rbp+60h]
  _QWORD v64[2]; // [rsp+178h] [rbp+70h] BYREF
  VARIANTARG v65; // [rsp+188h] [rbp+80h] BYREF
  int Task; // [rsp+270h] [rbp+168h] BYREF

  Task = 0;
  v64[1] = &Task;
  v64[0] = "ScheduleDeviceEnrollerOnLogin";
  a6 = 0;
  Task = AutoCoInitialize::CoInitializeEx((AutoCoInitialize *)&a6, (unsigned int)a2);
  v9 = Task;
  if ( (int)(Task + 0x80000000) < 0 || Task == -2147417850 )
  {
    v10 = 1;
    *(_QWORD *)v54 = 0;
    v11 = L"S-1-5-32-545";
    *(_QWORD *)v48 = 0;
    *(_QWORD *)v45 = 0;
    if ( a3 )
      v11 = a3;
    *(_QWORD *)v53 = 0;
    v47 = 0;
    v52 = 0;
    v51 = 0;
    v50 = 0;
    v49 = 0;
    Task = CreateTask(
             (LPVOID *)v54,
             (__int64)v48,
             v45,
             v53,
             a1,
             L"%windir%\\system32\\deviceenroller.exe ",
             a2,
             v11,
             0,
             0,
             1,
             1,
             1);
    if ( Task >= 0 )
    {
      Task = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)v45 + 72LL))(*(_QWORD *)v45, &v47);
      if ( Task >= 0 )
      {
        Task = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v47 + 80LL))(v47, 9, &v52);
        if ( Task >= 0 )
        {
          Task = (**v52)(v52, &IID_ILogonTrigger, &v51);
          if ( Task >= 0 )
          {
            Task = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v51 + 80LL))(v51, &v49);
            if ( Task >= 0 )
            {
              Task = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v49 + 96LL))(v49, 0);
              if ( Task >= 0 )
              {
                Task = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v45 + 80LL))(*(_QWORD *)v45, v47);
                if ( Task >= 0 )
                {
                  v12 = *(__int64 **)v48;
                  v13 = **(_QWORD **)v48;
                  if ( a5 )
                  {
                    v14 = *(__int64 (__fastcall **)(__int64 *, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))(v13 + 136);
                    VariantInit(&pvarg);
                    v15 = *(_OWORD *)&pvarg.vt;
                    pRecInfo = pvarg.pRecInfo;
                    VariantInit(&v55);
                    v17 = *(_OWORD *)&v55.vt;
                    v18 = v55.pRecInfo;
                    VariantInit(&v57);
                    v19 = *(_OWORD *)&v57.vt;
                    v20 = *(_QWORD *)v45;
                    v21 = v57.pRecInfo;
                    v22 = _bstr_t::_bstr_t((_bstr_t *)&Block, L"First Login Schedule created by enrollment client");
                    if ( *(_QWORD *)v22 )
                      v23 = **(_QWORD **)v22;
                    else
                      v23 = 0;
                    v58 = v15;
                    v59 = pRecInfo;
                    v60 = v17;
                    v61 = v18;
                    v62 = v19;
                    v63 = v21;
                    v24 = v14(v12, v23, v20, 6, &v62, &v60, 3, &v58, &v50);
                    v25 = (BSTR *)Block;
                    Task = v24;
                    if ( Block )
                    {
                      if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v25 )
                      {
                        if ( *v25 )
                        {
                          SysFreeString(*v25);
                          *v25 = 0;
                        }
                        v26 = v25[1];
                        if ( v26 )
                        {
                          operator delete(v26);
                          v25[1] = 0;
                        }
                        operator delete(v25);
                      }
                      Block = 0;
                    }
                    ATL::CComVariant::~CComVariant(&v57);
                    ATL::CComVariant::~CComVariant(&v55);
                    p_pvarg = &pvarg;
                  }
                  else
                  {
                    v28 = *(__int64 (__fastcall **)(__int64 *, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))(v13 + 136);
                    VariantInit(&v55);
                    v29 = *(_OWORD *)&v55.vt;
                    v30 = v55.pRecInfo;
                    VariantInit(&pvarg);
                    v31 = pvarg.pRecInfo;
                    v32 = *(_OWORD *)&pvarg.vt;
                    if ( a3 )
                    {
                      v33 = (VARIANTARG *)_variant_t::_variant_t((_variant_t *)&v65, a3);
                      v34 = 0;
                    }
                    else
                    {
                      VariantInit(&v57);
                      v33 = &v57;
                      v10 = 0;
                      v34 = 2;
                    }
                    v35 = *(_OWORD *)&v33->vt;
                    v36 = *(_QWORD *)v45;
                    v37 = v33->pRecInfo;
                    v38 = _bstr_t::_bstr_t((_bstr_t *)&Block, L"Login Schedule created by enrollment client");
                    if ( *(_QWORD *)v38 )
                      v39 = **(_QWORD **)v38;
                    else
                      v39 = 0;
                    v62 = v29;
                    v63 = v30;
                    v60 = v32;
                    v61 = v31;
                    v58 = v35;
                    v59 = v37;
                    v40 = v28(v12, v39, v36, 6, &v58, &v60, 3, &v62, &v50);
                    v41 = (BSTR *)Block;
                    Task = v40;
                    if ( Block )
                    {
                      if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v41 )
                      {
                        if ( *v41 )
                        {
                          SysFreeString(*v41);
                          *v41 = 0;
                        }
                        v42 = v41[1];
                        if ( v42 )
                        {
                          operator delete(v42);
                          v41[1] = 0;
                        }
                        operator delete(v41);
                      }
                      Block = 0;
                    }
                    if ( v34 )
                      ATL::CComVariant::~CComVariant(&v57);
                    if ( v10 )
                      ATL::CComVariant::~CComVariant(&v65);
                    ATL::CComVariant::~CComVariant(&pvarg);
                    p_pvarg = &v55;
                  }
                  ATL::CComVariant::~CComVariant(p_pvarg);
                  if ( Task < 0 )
                  {
                    Logger = CEnrollmentLogger::GetLogger();
                    CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(Logger, Task, "ScheduleDeviceEnrollerOnLogin");
                  }
                }
              }
            }
          }
        }
      }
    }
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v49);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v50);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v51);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v52);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v47);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(v53);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(v45);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(v48);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(v54);
    v9 = Task;
  }
  if ( a6 )
    CoUninitialize();
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v64);
  return v9;
}

```

## disassembly

```asm
0x14000ddd8  mov     rax, rsp
0x14000dddb  mov     [rax+20h], r9d
0x14000dddf  push    rbp
0x14000dde0  push    rbx
0x14000dde1  push    rsi
0x14000dde2  push    rdi
0x14000dde3  push    r12
0x14000dde5  push    r13
0x14000dde7  push    r14
0x14000dde9  push    r15
0x14000ddeb  lea     rbp, [rax-148h]
0x14000ddf2  sub     rsp, 208h
0x14000ddf9  movaps  xmmword ptr [rax-58h], xmm6
0x14000ddfd  lea     r13, aScheduledevice; "ScheduleDeviceEnrollerOnLogin"
0x14000de04  movaps  xmmword ptr [rax-68h], xmm7
0x14000de08  mov     r15, rcx
0x14000de0b  movaps  xmmword ptr [rax-78h], xmm8
0x14000de10  lea     rcx, [rbp+140h+arg_28]; this
0x14000de17  movaps  xmmword ptr [rax-88h], xmm9
0x14000de1f  xor     r12d, r12d
0x14000de22  movaps  xmmword ptr [rax-98h], xmm10
0x14000de2a  mov     rsi, r8
0x14000de2d  movaps  xmmword ptr [rax-0A8h], xmm11
0x14000de35  mov     r14, rdx
0x14000de38  lea     rax, [rbp+140h+arg_18]
0x14000de3f  mov     [rbp+140h+arg_18], r12d
0x14000de46  mov     [rbp+140h+var_C8], rax
0x14000de4a  mov     [rbp+140h+var_D0], r13
0x14000de4e  mov     [rbp+140h+arg_28], r12d
0x14000de55  call    ?CoInitializeEx@AutoCoInitialize@@QEAAJK@Z; AutoCoInitialize::CoInitializeEx(ulong)
0x14000de5a  mov     ecx, 80000000h
0x14000de5f  mov     [rbp+140h+arg_18], eax
0x14000de65  mov     ebx, eax
0x14000de67  add     eax, ecx
0x14000de69  test    ecx, eax
0x14000de6b  jnz     short loc_14000DE79
0x14000de6d  cmp     ebx, 80010106h
0x14000de73  jnz     loc_14000E344
0x14000de79  mov     edi, 1
0x14000de7e  mov     qword ptr [rbp+140h+var_180], r12
0x14000de82  mov     [rsp+240h+Data], edi; Data
0x14000de86  lea     rax, aS1532545; "S-1-5-32-545"
0x14000de8d  mov     [rsp+240h+var_1E8], edi; int
0x14000de91  lea     r9, [rbp+140h+var_188]; int
0x14000de95  mov     [rsp+240h+var_1F0], edi; int
0x14000de99  lea     r8, [rsp+240h+var_1D0]; int
0x14000de9e  mov     [rsp+240h+var_1F8], r12d; int
0x14000dea3  lea     rdx, [rbp+140h+var_1B8]; int
0x14000dea7  mov     [rsp+240h+var_200], r12d; int
0x14000deac  lea     rcx, [rbp+140h+var_180]; int
0x14000deb0  test    rsi, rsi
0x14000deb3  mov     qword ptr [rbp+140h+var_1B8], r12
0x14000deb7  mov     qword ptr [rsp+240h+var_1D0], r12
0x14000debc  cmovnz  rax, rsi
0x14000dec0  mov     qword ptr [rbp+140h+var_188], r12
0x14000dec4  mov     [rsp+240h+var_208], rax; unsigned __int16 *
0x14000dec9  lea     rax, aWindirSystem32_1; "%windir%\\system32\\deviceenroller.exe "
0x14000ded0  mov     [rsp+240h+var_210], r14; unsigned __int16 *
0x14000ded5  mov     [rsp+240h+var_218], rax; unsigned __int16 *
0x14000deda  mov     [rsp+240h+var_220], r15; unsigned __int16 *
0x14000dedf  mov     [rbp+140h+var_1C0], r12
0x14000dee3  mov     [rbp+140h+var_190], r12
0x14000dee7  mov     [rbp+140h+var_198], r12
0x14000deeb  mov     [rbp+140h+var_1A0], r12
0x14000deef  mov     [rbp+140h+var_1A8], r12
0x14000def3  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x14000def8  mov     [rbp+140h+arg_18], eax
0x14000defe  test    eax, eax
0x14000df00  js      loc_14000E2EC
0x14000df06  mov     rcx, qword ptr [rsp+240h+var_1D0]
0x14000df0b  lea     rdx, [rbp+140h+var_1C0]
0x14000df0f  mov     rax, [rcx]
0x14000df12  mov     rax, [rax+48h]
0x14000df16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000df1b  mov     [rbp+140h+arg_18], eax
0x14000df21  test    eax, eax
0x14000df23  js      loc_14000E2EC
0x14000df29  mov     rcx, [rbp+140h+var_1C0]
0x14000df2d  lea     r8, [rbp+140h+var_190]
0x14000df31  lea     edx, [rdi+8]
0x14000df34  mov     rax, [rcx]
0x14000df37  mov     rax, [rax+50h]
0x14000df3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000df40  mov     [rbp+140h+arg_18], eax
0x14000df46  test    eax, eax
0x14000df48  js      loc_14000E2EC
0x14000df4e  mov     rcx, [rbp+140h+var_190]
0x14000df52  lea     r8, [rbp+140h+var_198]
0x14000df56  lea     rdx, IID_ILogonTrigger
0x14000df5d  mov     rax, [rcx]
0x14000df60  mov     rax, [rax]
0x14000df63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000df68  mov     [rbp+140h+arg_18], eax
0x14000df6e  test    eax, eax
0x14000df70  js      loc_14000E2EC
0x14000df76  mov     rcx, [rbp+140h+var_198]
0x14000df7a  lea     rdx, [rbp+140h+var_1A8]
0x14000df7e  mov     rax, [rcx]
0x14000df81  mov     rax, [rax+50h]
0x14000df85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000df8a  mov     [rbp+140h+arg_18], eax
0x14000df90  test    eax, eax
0x14000df92  js      loc_14000E2EC
0x14000df98  mov     rcx, [rbp+140h+var_1A8]
0x14000df9c  xor     edx, edx
0x14000df9e  mov     rax, [rcx]
0x14000dfa1  mov     rax, [rax+60h]
0x14000dfa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dfaa  mov     [rbp+140h+arg_18], eax
0x14000dfb0  test    eax, eax
0x14000dfb2  js      loc_14000E2EC
0x14000dfb8  mov     rcx, qword ptr [rsp+240h+var_1D0]
0x14000dfbd  mov     rdx, [rbp+140h+var_1C0]
0x14000dfc1  mov     rax, [rcx]
0x14000dfc4  mov     rax, [rax+50h]
0x14000dfc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dfcd  mov     [rbp+140h+arg_18], eax
0x14000dfd3  test    eax, eax
0x14000dfd5  js      loc_14000E2EC
0x14000dfdb  mov     rbx, qword ptr [rbp+140h+var_1B8]
0x14000dfdf  mov     rax, [rbx]
0x14000dfe2  cmp     [rbp+140h+arg_20], r12d
0x14000dfe9  jz      loc_14000E142
0x14000dfef  mov     rsi, [rax+88h]
0x14000dff6  lea     rcx, [rbp+140h+pvarg]; pvarg
0x14000dffa  call    cs:__imp_VariantInit
0x14000e001  nop     dword ptr [rax+rax+00h]
0x14000e006  movups  xmm6, xmmword ptr [rbp+140h+pvarg]
0x14000e00a  lea     rcx, [rbp+140h+var_178]; pvarg
0x14000e00e  movsd   xmm7, qword ptr [rbp+140h+pvarg+10h]
0x14000e013  call    cs:__imp_VariantInit
0x14000e01a  nop     dword ptr [rax+rax+00h]
0x14000e01f  movups  xmm8, xmmword ptr [rbp+140h+var_178]
0x14000e024  lea     rcx, [rbp+140h+var_148]; pvarg
0x14000e028  movsd   xmm9, qword ptr [rbp+140h+var_178+10h]
0x14000e02e  call    cs:__imp_VariantInit
0x14000e035  nop     dword ptr [rax+rax+00h]
0x14000e03a  movups  xmm10, xmmword ptr [rbp+140h+var_148]
0x14000e03f  lea     rdx, aFirstLoginSche; "First Login Schedule created by enrollm"...
0x14000e046  mov     rdi, qword ptr [rsp+240h+var_1D0]
0x14000e04b  movsd   xmm11, qword ptr [rbp+140h+var_148+10h]
0x14000e051  lea     rcx, [rsp+240h+Block]; this
0x14000e056  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14000e05b  mov     rdx, [rax]
0x14000e05e  test    rdx, rdx
0x14000e061  jz      short loc_14000E068
0x14000e063  mov     rdx, [rdx]
0x14000e066  jmp     short loc_14000E06B
0x14000e068  mov     rdx, r12
0x14000e06b  lea     rax, [rbp+140h+var_1A0]
0x14000e06f  movaps  [rbp+140h+var_130], xmm6
0x14000e073  mov     qword ptr [rsp+240h+var_200], rax
0x14000e078  mov     r9d, 6
0x14000e07e  lea     rax, [rbp+140h+var_130]
0x14000e082  movsd   [rbp+140h+var_120], xmm7
0x14000e087  mov     [rsp+240h+var_208], rax
0x14000e08c  mov     r8, rdi
0x14000e08f  lea     rax, [rbp+140h+var_110]
0x14000e093  mov     dword ptr [rsp+240h+var_210], 3
0x14000e09b  mov     [rsp+240h+var_218], rax
0x14000e0a0  mov     rcx, rbx
0x14000e0a3  lea     rax, [rbp+140h+var_F0]
0x14000e0a7  movaps  [rbp+140h+var_110], xmm8
0x14000e0ac  mov     [rsp+240h+var_220], rax
0x14000e0b1  mov     rax, rsi
0x14000e0b4  movsd   [rbp+140h+var_100], xmm9
0x14000e0ba  movaps  [rbp+140h+var_F0], xmm10
0x14000e0bf  movsd   [rbp+140h+var_E0], xmm11
0x14000e0c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e0ca  mov     rbx, [rsp+240h+Block]
0x14000e0cf  mov     [rbp+140h+arg_18], eax
0x14000e0d5  test    rbx, rbx
0x14000e0d8  jz      short loc_14000E127
0x14000e0da  or      eax, 0FFFFFFFFh
0x14000e0dd  lock xadd [rbx+10h], eax
0x14000e0e2  cmp     eax, 1
0x14000e0e5  jnz     short loc_14000E122
0x14000e0e7  test    rbx, rbx
0x14000e0ea  jz      short loc_14000E122
0x14000e0ec  mov     rcx, [rbx]; bstrString
0x14000e0ef  test    rcx, rcx
0x14000e0f2  jz      short loc_14000E103
0x14000e0f4  call    cs:__imp_SysFreeString
0x14000e0fb  nop     dword ptr [rax+rax+00h]
0x14000e100  mov     [rbx], r12
0x14000e103  mov     rcx, [rbx+8]; Block
0x14000e107  test    rcx, rcx
0x14000e10a  jz      short loc_14000E115
0x14000e10c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000e111  mov     [rbx+8], r12
0x14000e115  mov     edx, 18h
0x14000e11a  mov     rcx, rbx; Block
0x14000e11d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000e122  mov     [rsp+240h+Block], r12
0x14000e127  lea     rcx, [rbp+140h+var_148]; pvarg
0x14000e12b  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000e130  lea     rcx, [rbp+140h+var_178]; pvarg
0x14000e134  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000e139  lea     rcx, [rbp+140h+pvarg]
0x14000e13d  jmp     loc_14000E2C8
0x14000e142  mov     r15, [rax+88h]
0x14000e149  lea     rcx, [rbp+140h+var_178]; pvarg
0x14000e14d  call    cs:__imp_VariantInit
0x14000e154  nop     dword ptr [rax+rax+00h]
0x14000e159  movups  xmm8, xmmword ptr [rbp+140h+var_178]
0x14000e15e  lea     rcx, [rbp+140h+pvarg]; pvarg
0x14000e162  movsd   xmm9, qword ptr [rbp+140h+var_178+10h]
0x14000e168  call    cs:__imp_VariantInit
0x14000e16f  nop     dword ptr [rax+rax+00h]
0x14000e174  movsd   xmm11, qword ptr [rbp+140h+pvarg+10h]
0x14000e17a  movups  xmm10, xmmword ptr [rbp+140h+pvarg]
0x14000e17f  test    rsi, rsi
0x14000e182  jz      short loc_14000E198
0x14000e184  mov     rdx, rsi; unsigned __int16 *
0x14000e187  lea     rcx, [rbp+140h+var_C0]; this
0x14000e18e  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x14000e193  mov     esi, r12d
0x14000e196  jmp     short loc_14000E1B4
0x14000e198  lea     rcx, [rbp+140h+var_148]; pvarg
0x14000e19c  call    cs:__imp_VariantInit
0x14000e1a3  nop     dword ptr [rax+rax+00h]
0x14000e1a8  lea     rax, [rbp+140h+var_148]
0x14000e1ac  mov     edi, r12d
0x14000e1af  mov     esi, 2
0x14000e1b4  movups  xmm6, xmmword ptr [rax]
0x14000e1b7  lea     rdx, aLoginScheduleC; "Login Schedule created by enrollment cl"...
0x14000e1be  mov     r14, qword ptr [rsp+240h+var_1D0]
0x14000e1c3  movsd   xmm7, qword ptr [rax+10h]
0x14000e1c8  lea     rcx, [rsp+240h+Block]; this
0x14000e1cd  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14000e1d2  mov     rcx, [rax]
0x14000e1d5  test    rcx, rcx
0x14000e1d8  jz      short loc_14000E1DF
0x14000e1da  mov     rdx, [rcx]
0x14000e1dd  jmp     short loc_14000E1E2
0x14000e1df  mov     rdx, r12
0x14000e1e2  lea     rax, [rbp+140h+var_1A0]
0x14000e1e6  movaps  [rbp+140h+var_F0], xmm8
0x14000e1eb  mov     qword ptr [rsp+240h+var_200], rax
0x14000e1f0  mov     r9d, 6
0x14000e1f6  lea     rax, [rbp+140h+var_F0]
0x14000e1fa  movsd   [rbp+140h+var_E0], xmm9
0x14000e200  mov     [rsp+240h+var_208], rax
0x14000e205  mov     r8, r14
0x14000e208  lea     rax, [rbp+140h+var_110]
0x14000e20c  mov     dword ptr [rsp+240h+var_210], 3
0x14000e214  mov     [rsp+240h+var_218], rax
0x14000e219  mov     rcx, rbx
0x14000e21c  lea     rax, [rbp+140h+var_130]
0x14000e220  movaps  [rbp+140h+var_110], xmm10
0x14000e225  mov     [rsp+240h+var_220], rax
0x14000e22a  mov     rax, r15
0x14000e22d  movsd   [rbp+140h+var_100], xmm11
0x14000e233  movaps  [rbp+140h+var_130], xmm6
0x14000e237  movsd   [rbp+140h+var_120], xmm7
0x14000e23c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e241  mov     rbx, [rsp+240h+Block]
0x14000e246  mov     [rbp+140h+arg_18], eax
0x14000e24c  test    rbx, rbx
0x14000e24f  jz      short loc_14000E29E
0x14000e251  or      eax, 0FFFFFFFFh
0x14000e254  lock xadd [rbx+10h], eax
0x14000e259  cmp     eax, 1
0x14000e25c  jnz     short loc_14000E299
0x14000e25e  test    rbx, rbx
0x14000e261  jz      short loc_14000E299
0x14000e263  mov     rcx, [rbx]; bstrString
0x14000e266  test    rcx, rcx
0x14000e269  jz      short loc_14000E27A
0x14000e26b  call    cs:__imp_SysFreeString
0x14000e272  nop     dword ptr [rax+rax+00h]
0x14000e277  mov     [rbx], r12
0x14000e27a  mov     rcx, [rbx+8]; Block
0x14000e27e  test    rcx, rcx
0x14000e281  jz      short loc_14000E28C
0x14000e283  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000e288  mov     [rbx+8], r12
0x14000e28c  mov     edx, 18h
0x14000e291  mov     rcx, rbx; Block
0x14000e294  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000e299  mov     [rsp+240h+Block], r12
0x14000e29e  test    esi, esi
0x14000e2a0  jz      short loc_14000E2AB
0x14000e2a2  lea     rcx, [rbp+140h+var_148]; pvarg
0x14000e2a6  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000e2ab  test    edi, edi
0x14000e2ad  jz      short loc_14000E2BB
0x14000e2af  lea     rcx, [rbp+140h+var_C0]; pvarg
0x14000e2b6  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000e2bb  lea     rcx, [rbp+140h+pvarg]; pvarg
0x14000e2bf  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000e2c4  lea     rcx, [rbp+140h+var_178]; pvarg
0x14000e2c8  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000e2cd  cmp     [rbp+140h+arg_18], r12d
0x14000e2d4  jge     short loc_14000E2EC
0x14000e2d6  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x14000e2db  mov     edx, [rbp+140h+arg_18]; int
0x14000e2e1  mov     r8, r13; char *
0x14000e2e4  mov     rcx, rax; this
0x14000e2e7  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
  ... truncated ...
```
