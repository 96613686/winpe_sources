# ScheduleDeviceEnrollerOnLogin

- ea: `0x14000d70c`
- end: `0x14000dc98`
- name: `ScheduleDeviceEnrollerOnLogin`
- size: `1420`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, __int64, int, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x14000ee6c`

## callees

- `0x140002954`
- `0x1400046a4`
- `0x140004c34`
- `0x140008dc8`
- `0x140008e48`
- `0x1400090fc`
- `0x140009cd8`
- `0x14000a0b8`
- `0x14000d70c`
- `0x1400177b0`
- `0x140017ba0`
- `0x140019010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000da16`
- `OLEAUT32!__imp_SysFreeString` at `0x14000db75`
- `OLEAUT32!__imp_SysFreeString` at `0x14000da16`
- `OLEAUT32!__imp_SysFreeString` at `0x14000db75`
- `OLEAUT32!__imp_VariantInit` at `0x14000d92e`
- `OLEAUT32!__imp_VariantInit` at `0x14000d941`
- `OLEAUT32!__imp_VariantInit` at `0x14000d956`
- `OLEAUT32!__imp_VariantInit` at `0x14000da69`
- `OLEAUT32!__imp_VariantInit` at `0x14000da7e`
- `OLEAUT32!__imp_VariantInit` at `0x14000daac`
- `OLEAUT32!__imp_VariantInit` at `0x14000d92e`
- `OLEAUT32!__imp_VariantInit` at `0x14000d941`
- `OLEAUT32!__imp_VariantInit` at `0x14000d956`
- `OLEAUT32!__imp_VariantInit` at `0x14000da69`
- `OLEAUT32!__imp_VariantInit` at `0x14000da7e`
- `OLEAUT32!__imp_VariantInit` at `0x14000daac`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000dc51`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000dc51`

## string_xrefs

- `0x14000dac1`: `Login Schedule created by enrollment client`
- `0x14000d7fd`: `%windir%\system32\deviceenroller.exe `
- `0x14000d731`: `ScheduleDeviceEnrollerOnLogin`
- `0x14000d961`: `First Login Schedule created by enrollment client`

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
             v54,
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
0x14000d70c  mov     rax, rsp
0x14000d70f  mov     [rax+20h], r9d
0x14000d713  push    rbp
0x14000d714  push    rbx
0x14000d715  push    rsi
0x14000d716  push    rdi
0x14000d717  push    r12
0x14000d719  push    r13
0x14000d71b  push    r14
0x14000d71d  push    r15
0x14000d71f  lea     rbp, [rax-148h]
0x14000d726  sub     rsp, 208h
0x14000d72d  movaps  xmmword ptr [rax-58h], xmm6
0x14000d731  lea     r13, aScheduledevice; "ScheduleDeviceEnrollerOnLogin"
0x14000d738  movaps  xmmword ptr [rax-68h], xmm7
0x14000d73c  mov     r15, rcx
0x14000d73f  movaps  xmmword ptr [rax-78h], xmm8
0x14000d744  lea     rcx, [rbp+140h+arg_28]; this
0x14000d74b  movaps  xmmword ptr [rax-88h], xmm9
0x14000d753  xor     r12d, r12d
0x14000d756  movaps  xmmword ptr [rax-98h], xmm10
0x14000d75e  mov     rsi, r8
0x14000d761  movaps  xmmword ptr [rax-0A8h], xmm11
0x14000d769  mov     r14, rdx
0x14000d76c  lea     rax, [rbp+140h+arg_18]
0x14000d773  mov     [rbp+140h+arg_18], r12d
0x14000d77a  mov     [rbp+140h+var_C8], rax
0x14000d77e  mov     [rbp+140h+var_D0], r13
0x14000d782  mov     [rbp+140h+arg_28], r12d
0x14000d789  call    ?CoInitializeEx@AutoCoInitialize@@QEAAJK@Z; AutoCoInitialize::CoInitializeEx(ulong)
0x14000d78e  mov     ecx, 80000000h
0x14000d793  mov     [rbp+140h+arg_18], eax
0x14000d799  mov     ebx, eax
0x14000d79b  add     eax, ecx
0x14000d79d  test    ecx, eax
0x14000d79f  jnz     short loc_14000D7AD
0x14000d7a1  cmp     ebx, 80010106h
0x14000d7a7  jnz     loc_14000DC48
0x14000d7ad  mov     edi, 1
0x14000d7b2  mov     qword ptr [rbp+140h+var_180], r12
0x14000d7b6  mov     [rsp+240h+Data], edi; Data
0x14000d7ba  lea     rax, aS1532545; "S-1-5-32-545"
0x14000d7c1  mov     [rsp+240h+var_1E8], edi; int
0x14000d7c5  lea     r9, [rbp+140h+var_188]; int
0x14000d7c9  mov     [rsp+240h+var_1F0], edi; int
0x14000d7cd  lea     r8, [rsp+240h+var_1D0]; int
0x14000d7d2  mov     [rsp+240h+var_1F8], r12d; int
0x14000d7d7  lea     rdx, [rbp+140h+var_1B8]; int
0x14000d7db  mov     [rsp+240h+var_200], r12d; int
0x14000d7e0  lea     rcx, [rbp+140h+var_180]; int
0x14000d7e4  test    rsi, rsi
0x14000d7e7  mov     qword ptr [rbp+140h+var_1B8], r12
0x14000d7eb  mov     qword ptr [rsp+240h+var_1D0], r12
0x14000d7f0  cmovnz  rax, rsi
0x14000d7f4  mov     qword ptr [rbp+140h+var_188], r12
0x14000d7f8  mov     [rsp+240h+var_208], rax; unsigned __int16 *
0x14000d7fd  lea     rax, aWindirSystem32_1; "%windir%\\system32\\deviceenroller.exe "
0x14000d804  mov     [rsp+240h+var_210], r14; unsigned __int16 *
0x14000d809  mov     [rsp+240h+var_218], rax; unsigned __int16 *
0x14000d80e  mov     [rsp+240h+var_220], r15; unsigned __int16 *
0x14000d813  mov     [rbp+140h+var_1C0], r12
0x14000d817  mov     [rbp+140h+var_190], r12
0x14000d81b  mov     [rbp+140h+var_198], r12
0x14000d81f  mov     [rbp+140h+var_1A0], r12
0x14000d823  mov     [rbp+140h+var_1A8], r12
0x14000d827  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x14000d82c  mov     [rbp+140h+arg_18], eax
0x14000d832  test    eax, eax
0x14000d834  js      loc_14000DBF0
0x14000d83a  mov     rcx, qword ptr [rsp+240h+var_1D0]
0x14000d83f  lea     rdx, [rbp+140h+var_1C0]
0x14000d843  mov     rax, [rcx]
0x14000d846  mov     rax, [rax+48h]
0x14000d84a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d84f  mov     [rbp+140h+arg_18], eax
0x14000d855  test    eax, eax
0x14000d857  js      loc_14000DBF0
0x14000d85d  mov     rcx, [rbp+140h+var_1C0]
0x14000d861  lea     r8, [rbp+140h+var_190]
0x14000d865  lea     edx, [rdi+8]
0x14000d868  mov     rax, [rcx]
0x14000d86b  mov     rax, [rax+50h]
0x14000d86f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d874  mov     [rbp+140h+arg_18], eax
0x14000d87a  test    eax, eax
0x14000d87c  js      loc_14000DBF0
0x14000d882  mov     rcx, [rbp+140h+var_190]
0x14000d886  lea     r8, [rbp+140h+var_198]
0x14000d88a  lea     rdx, IID_ILogonTrigger
0x14000d891  mov     rax, [rcx]
0x14000d894  mov     rax, [rax]
0x14000d897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d89c  mov     [rbp+140h+arg_18], eax
0x14000d8a2  test    eax, eax
0x14000d8a4  js      loc_14000DBF0
0x14000d8aa  mov     rcx, [rbp+140h+var_198]
0x14000d8ae  lea     rdx, [rbp+140h+var_1A8]
0x14000d8b2  mov     rax, [rcx]
0x14000d8b5  mov     rax, [rax+50h]
0x14000d8b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d8be  mov     [rbp+140h+arg_18], eax
0x14000d8c4  test    eax, eax
0x14000d8c6  js      loc_14000DBF0
0x14000d8cc  mov     rcx, [rbp+140h+var_1A8]
0x14000d8d0  xor     edx, edx
0x14000d8d2  mov     rax, [rcx]
0x14000d8d5  mov     rax, [rax+60h]
0x14000d8d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d8de  mov     [rbp+140h+arg_18], eax
0x14000d8e4  test    eax, eax
0x14000d8e6  js      loc_14000DBF0
0x14000d8ec  mov     rcx, qword ptr [rsp+240h+var_1D0]
0x14000d8f1  mov     rdx, [rbp+140h+var_1C0]
0x14000d8f5  mov     rax, [rcx]
0x14000d8f8  mov     rax, [rax+50h]
0x14000d8fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d901  mov     [rbp+140h+arg_18], eax
0x14000d907  test    eax, eax
0x14000d909  js      loc_14000DBF0
0x14000d90f  mov     rbx, qword ptr [rbp+140h+var_1B8]
0x14000d913  mov     rax, [rbx]
0x14000d916  cmp     [rbp+140h+arg_20], r12d
0x14000d91d  jz      loc_14000DA5E
0x14000d923  mov     rsi, [rax+88h]
0x14000d92a  lea     rcx, [rbp+140h+pvarg]; pvarg
0x14000d92e  call    cs:__imp_VariantInit
0x14000d934  movups  xmm6, xmmword ptr [rbp+140h+pvarg]
0x14000d938  lea     rcx, [rbp+140h+var_178]; pvarg
0x14000d93c  movsd   xmm7, qword ptr [rbp+140h+pvarg+10h]
0x14000d941  call    cs:__imp_VariantInit
0x14000d947  movups  xmm8, xmmword ptr [rbp+140h+var_178]
0x14000d94c  lea     rcx, [rbp+140h+var_148]; pvarg
0x14000d950  movsd   xmm9, qword ptr [rbp+140h+var_178+10h]
0x14000d956  call    cs:__imp_VariantInit
0x14000d95c  movups  xmm10, xmmword ptr [rbp+140h+var_148]
0x14000d961  lea     rdx, aFirstLoginSche; "First Login Schedule created by enrollm"...
0x14000d968  mov     rdi, qword ptr [rsp+240h+var_1D0]
0x14000d96d  movsd   xmm11, qword ptr [rbp+140h+var_148+10h]
0x14000d973  lea     rcx, [rsp+240h+Block]; this
0x14000d978  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14000d97d  mov     rdx, [rax]
0x14000d980  test    rdx, rdx
0x14000d983  jz      short loc_14000D98A
0x14000d985  mov     rdx, [rdx]
0x14000d988  jmp     short loc_14000D98D
0x14000d98a  mov     rdx, r12
0x14000d98d  lea     rax, [rbp+140h+var_1A0]
0x14000d991  movaps  [rbp+140h+var_130], xmm6
0x14000d995  mov     qword ptr [rsp+240h+var_200], rax
0x14000d99a  mov     r9d, 6
0x14000d9a0  lea     rax, [rbp+140h+var_130]
0x14000d9a4  movsd   [rbp+140h+var_120], xmm7
0x14000d9a9  mov     [rsp+240h+var_208], rax
0x14000d9ae  mov     r8, rdi
0x14000d9b1  lea     rax, [rbp+140h+var_110]
0x14000d9b5  mov     dword ptr [rsp+240h+var_210], 3
0x14000d9bd  mov     [rsp+240h+var_218], rax
0x14000d9c2  mov     rcx, rbx
0x14000d9c5  lea     rax, [rbp+140h+var_F0]
0x14000d9c9  movaps  [rbp+140h+var_110], xmm8
0x14000d9ce  mov     [rsp+240h+var_220], rax
0x14000d9d3  mov     rax, rsi
0x14000d9d6  movsd   [rbp+140h+var_100], xmm9
0x14000d9dc  movaps  [rbp+140h+var_F0], xmm10
0x14000d9e1  movsd   [rbp+140h+var_E0], xmm11
0x14000d9e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d9ec  mov     rbx, [rsp+240h+Block]
0x14000d9f1  mov     [rbp+140h+arg_18], eax
0x14000d9f7  test    rbx, rbx
0x14000d9fa  jz      short loc_14000DA43
0x14000d9fc  or      eax, 0FFFFFFFFh
0x14000d9ff  lock xadd [rbx+10h], eax
0x14000da04  cmp     eax, 1
0x14000da07  jnz     short loc_14000DA3E
0x14000da09  test    rbx, rbx
0x14000da0c  jz      short loc_14000DA3E
0x14000da0e  mov     rcx, [rbx]; bstrString
0x14000da11  test    rcx, rcx
0x14000da14  jz      short loc_14000DA1F
0x14000da16  call    cs:__imp_SysFreeString
0x14000da1c  mov     [rbx], r12
0x14000da1f  mov     rcx, [rbx+8]; Block
0x14000da23  test    rcx, rcx
0x14000da26  jz      short loc_14000DA31
0x14000da28  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000da2d  mov     [rbx+8], r12
0x14000da31  mov     edx, 18h
0x14000da36  mov     rcx, rbx; Block
0x14000da39  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000da3e  mov     [rsp+240h+Block], r12
0x14000da43  lea     rcx, [rbp+140h+var_148]; pvarg
0x14000da47  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000da4c  lea     rcx, [rbp+140h+var_178]; pvarg
0x14000da50  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000da55  lea     rcx, [rbp+140h+pvarg]
0x14000da59  jmp     loc_14000DBCC
0x14000da5e  mov     r15, [rax+88h]
0x14000da65  lea     rcx, [rbp+140h+var_178]; pvarg
0x14000da69  call    cs:__imp_VariantInit
0x14000da6f  movups  xmm8, xmmword ptr [rbp+140h+var_178]
0x14000da74  lea     rcx, [rbp+140h+pvarg]; pvarg
0x14000da78  movsd   xmm9, qword ptr [rbp+140h+var_178+10h]
0x14000da7e  call    cs:__imp_VariantInit
0x14000da84  movsd   xmm11, qword ptr [rbp+140h+pvarg+10h]
0x14000da8a  movups  xmm10, xmmword ptr [rbp+140h+pvarg]
0x14000da8f  test    rsi, rsi
0x14000da92  jz      short loc_14000DAA8
0x14000da94  mov     rdx, rsi; unsigned __int16 *
0x14000da97  lea     rcx, [rbp+140h+var_C0]; this
0x14000da9e  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x14000daa3  mov     esi, r12d
0x14000daa6  jmp     short loc_14000DABE
0x14000daa8  lea     rcx, [rbp+140h+var_148]; pvarg
0x14000daac  call    cs:__imp_VariantInit
0x14000dab2  lea     rax, [rbp+140h+var_148]
0x14000dab6  mov     edi, r12d
0x14000dab9  mov     esi, 2
0x14000dabe  movups  xmm6, xmmword ptr [rax]
0x14000dac1  lea     rdx, aLoginScheduleC; "Login Schedule created by enrollment cl"...
0x14000dac8  mov     r14, qword ptr [rsp+240h+var_1D0]
0x14000dacd  movsd   xmm7, qword ptr [rax+10h]
0x14000dad2  lea     rcx, [rsp+240h+Block]; this
0x14000dad7  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14000dadc  mov     rcx, [rax]
0x14000dadf  test    rcx, rcx
0x14000dae2  jz      short loc_14000DAE9
0x14000dae4  mov     rdx, [rcx]
0x14000dae7  jmp     short loc_14000DAEC
0x14000dae9  mov     rdx, r12
0x14000daec  lea     rax, [rbp+140h+var_1A0]
0x14000daf0  movaps  [rbp+140h+var_F0], xmm8
0x14000daf5  mov     qword ptr [rsp+240h+var_200], rax
0x14000dafa  mov     r9d, 6
0x14000db00  lea     rax, [rbp+140h+var_F0]
0x14000db04  movsd   [rbp+140h+var_E0], xmm9
0x14000db0a  mov     [rsp+240h+var_208], rax
0x14000db0f  mov     r8, r14
0x14000db12  lea     rax, [rbp+140h+var_110]
0x14000db16  mov     dword ptr [rsp+240h+var_210], 3
0x14000db1e  mov     [rsp+240h+var_218], rax
0x14000db23  mov     rcx, rbx
0x14000db26  lea     rax, [rbp+140h+var_130]
0x14000db2a  movaps  [rbp+140h+var_110], xmm10
0x14000db2f  mov     [rsp+240h+var_220], rax
0x14000db34  mov     rax, r15
0x14000db37  movsd   [rbp+140h+var_100], xmm11
0x14000db3d  movaps  [rbp+140h+var_130], xmm6
0x14000db41  movsd   [rbp+140h+var_120], xmm7
0x14000db46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000db4b  mov     rbx, [rsp+240h+Block]
0x14000db50  mov     [rbp+140h+arg_18], eax
0x14000db56  test    rbx, rbx
0x14000db59  jz      short loc_14000DBA2
0x14000db5b  or      eax, 0FFFFFFFFh
0x14000db5e  lock xadd [rbx+10h], eax
0x14000db63  cmp     eax, 1
0x14000db66  jnz     short loc_14000DB9D
0x14000db68  test    rbx, rbx
0x14000db6b  jz      short loc_14000DB9D
0x14000db6d  mov     rcx, [rbx]; bstrString
0x14000db70  test    rcx, rcx
0x14000db73  jz      short loc_14000DB7E
0x14000db75  call    cs:__imp_SysFreeString
0x14000db7b  mov     [rbx], r12
0x14000db7e  mov     rcx, [rbx+8]; Block
0x14000db82  test    rcx, rcx
0x14000db85  jz      short loc_14000DB90
0x14000db87  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000db8c  mov     [rbx+8], r12
0x14000db90  mov     edx, 18h
0x14000db95  mov     rcx, rbx; Block
0x14000db98  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000db9d  mov     [rsp+240h+Block], r12
0x14000dba2  test    esi, esi
0x14000dba4  jz      short loc_14000DBAF
0x14000dba6  lea     rcx, [rbp+140h+var_148]; pvarg
0x14000dbaa  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000dbaf  test    edi, edi
0x14000dbb1  jz      short loc_14000DBBF
0x14000dbb3  lea     rcx, [rbp+140h+var_C0]; pvarg
0x14000dbba  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000dbbf  lea     rcx, [rbp+140h+pvarg]; pvarg
0x14000dbc3  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000dbc8  lea     rcx, [rbp+140h+var_178]; pvarg
0x14000dbcc  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000dbd1  cmp     [rbp+140h+arg_18], r12d
0x14000dbd8  jge     short loc_14000DBF0
0x14000dbda  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x14000dbdf  mov     edx, [rbp+140h+arg_18]; int
0x14000dbe5  mov     r8, r13; char *
0x14000dbe8  mov     rcx, rax; this
0x14000dbeb  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x14000dbf0  lea     rcx, [rbp+140h+var_1A8]
0x14000dbf4  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000dbf9  lea     rcx, [rbp+140h+var_1A0]
0x14000dbfd  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000dc02  lea     rcx, [rbp+140h+var_198]
0x14000dc06  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000dc0b  lea     rcx, [rbp+140h+var_190]
0x14000dc0f  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
  ... truncated ...
```
