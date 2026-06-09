# ScheduleDeviceEnrollerOnPFW

- ea: `0x14000e3a4`
- end: `0x14000e845`
- name: `ScheduleDeviceEnrollerOnPFW`
- size: `1185`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x140010818`

## callees

- `0x1400029c0`
- `0x1400029e4`
- `0x14000476c`
- `0x140004cd0`
- `0x140007628`
- `0x1400091e0`
- `0x140009268`
- `0x1400094e4`
- `0x14000a134`
- `0x14000a51c`
- `0x14000e3a4`
- `0x14001848c`
- `0x140018890`
- `0x14001a010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000e5a4`
- `OLEAUT32!__imp_SysFreeString` at `0x14000e70f`
- `OLEAUT32!__imp_SysFreeString` at `0x14000e5a4`
- `OLEAUT32!__imp_SysFreeString` at `0x14000e70f`
- `OLEAUT32!__imp_VariantInit` at `0x14000e610`
- `OLEAUT32!__imp_VariantInit` at `0x14000e629`
- `OLEAUT32!__imp_VariantInit` at `0x14000e610`
- `OLEAUT32!__imp_VariantInit` at `0x14000e629`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000e7e9`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000e7e9`

## string_xrefs

- `0x14000e4b9`: `%windir%\system32\deviceenroller.exe `
- `0x14000e3f0`: `ScheduleDeviceEnrollerOnPFW`
- `0x14000e77d`: `ScheduleDeviceEnrollerOnPFW`
- `0x14000e65f`: `Passport for Work alert created by enrollment client`
- `0x14000e548`: `<QueryList><Query Id="0" Path="Microsoft-Windows-User Device Registration/Admin"><Select Path="Microsoft-Windows-User Device Registration/Admin">*[System[Provider[@Name='Microsoft-Windows-User Device Registration'] and EventID=300]]</Select></Query></QueryList>`

## pseudocode

```c
__int64 __fastcall ScheduleDeviceEnrollerOnPFW(unsigned __int16 *a1, unsigned __int16 *a2)
{
  unsigned __int16 *v3; // rsi
  unsigned int v4; // ebx
  __int64 v5; // rbx
  __int64 (__fastcall *v6)(__int64, __int64); // rdi
  _bstr_t *v7; // rax
  __int64 v8; // rdx
  int v9; // eax
  BSTR *v10; // rbx
  BSTR v11; // rcx
  __int64 v12; // rbx
  __int64 (__fastcall *v13)(__int64, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *); // r14
  __int128 v14; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  __int128 v16; // xmm8
  IRecordInfo *v17; // xmm9_8
  _variant_t *v18; // rax
  __int64 v19; // rdi
  __int128 v20; // xmm10
  __int64 v21; // xmm11_8
  _bstr_t *v22; // rax
  __int64 v23; // rdx
  int v24; // eax
  BSTR *v25; // rbx
  BSTR v26; // rcx
  CEnrollmentLogger *Logger; // rax
  int v29[2]; // [rsp+78h] [rbp-90h] BYREF
  int v30[2]; // [rsp+80h] [rbp-88h] BYREF
  __int64 v31; // [rsp+88h] [rbp-80h] BYREF
  void *Block[2]; // [rsp+90h] [rbp-78h] BYREF
  __int64 v33; // [rsp+A0h] [rbp-68h] BYREF
  __int64 (__fastcall ***v34)(_QWORD, GUID *, __int64 *); // [rsp+A8h] [rbp-60h] BYREF
  int v35[2]; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v36; // [rsp+B8h] [rbp-50h] BYREF
  int v37[2]; // [rsp+C0h] [rbp-48h] BYREF
  int v38[2]; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v39; // [rsp+D0h] [rbp-38h] BYREF
  _QWORD v40[2]; // [rsp+D8h] [rbp-30h] BYREF
  VARIANTARG v41; // [rsp+E8h] [rbp-20h] BYREF
  VARIANTARG pvarg; // [rsp+100h] [rbp-8h] BYREF
  __int128 v43; // [rsp+118h] [rbp+10h] BYREF
  IRecordInfo *v44; // [rsp+128h] [rbp+20h]
  __int128 v45; // [rsp+138h] [rbp+30h] BYREF
  IRecordInfo *v46; // [rsp+148h] [rbp+40h]
  __int128 v47; // [rsp+158h] [rbp+50h] BYREF
  __int64 v48; // [rsp+168h] [rbp+60h]
  VARIANTARG v49; // [rsp+178h] [rbp+70h] BYREF
  unsigned __int16 v50[264]; // [rsp+198h] [rbp+90h] BYREF

  v40[0] = "ScheduleDeviceEnrollerOnPFW";
  v40[1] = v29;
  v3 = a2;
  v29[0] = 0;
  v29[1] = 0;
  v29[0] = AutoCoInitialize::CoInitializeEx((AutoCoInitialize *)&v29[1], (unsigned int)a2);
  v4 = v29[0];
  if ( v29[0] >= 0 )
  {
    *(_QWORD *)v38 = 0;
    *(_QWORD *)v35 = 0;
    *(_QWORD *)v30 = 0;
    *(_QWORD *)v37 = 0;
    v31 = 0;
    v34 = 0;
    v33 = 0;
    v36 = 0;
    v39 = 0;
    v29[0] = StringCchPrintfW(v50, 0x104u, L"/o \"%s\" /c /PFW", a1);
    if ( v29[0] >= 0 )
    {
      v29[0] = CreateTask(
                 (LPVOID *)v38,
                 (__int64)v35,
                 v30,
                 v37,
                 a1,
                 L"%windir%\\system32\\deviceenroller.exe ",
                 v50,
                 v3,
                 0,
                 1,
                 0,
                 0,
                 0);
      if ( v29[0] >= 0 )
      {
        v29[0] = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)v30 + 72LL))(*(_QWORD *)v30, &v31);
        if ( v29[0] >= 0 )
        {
          v29[0] = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v31 + 80LL))(v31, 0, &v34);
          if ( v29[0] >= 0 )
          {
            v29[0] = (**v34)(v34, &IID_IEventTrigger, &v33);
            if ( v29[0] >= 0 )
            {
              v5 = v33;
              v6 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v33 + 168LL);
              v7 = _bstr_t::_bstr_t(
                     (_bstr_t *)Block,
                     L"<QueryList><Query Id=\"0\" Path=\"Microsoft-Windows-User Device Registration/Admin\"><Select Path=\""
                      "Microsoft-Windows-User Device Registration/Admin\">*[System[Provider[@Name='Microsoft-Windows-User"
                      " Device Registration'] and EventID=300]]</Select></Query></QueryList>");
              if ( *(_QWORD *)v7 )
                v8 = **(_QWORD **)v7;
              else
                v8 = 0;
              v9 = v6(v5, v8);
              v10 = (BSTR *)Block[0];
              v29[0] = v9;
              if ( Block[0] && _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v10 )
              {
                if ( *v10 )
                {
                  SysFreeString(*v10);
                  *v10 = 0;
                }
                v11 = v10[1];
                if ( v11 )
                {
                  operator delete(v11);
                  v10[1] = 0;
                }
                operator delete(v10);
              }
              if ( v29[0] >= 0 )
              {
                v29[0] = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v30 + 80LL))(*(_QWORD *)v30, v31);
                if ( v29[0] >= 0 )
                {
                  v12 = *(_QWORD *)v35;
                  v13 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))(**(_QWORD **)v35 + 136LL);
                  VariantInit(&pvarg);
                  v14 = *(_OWORD *)&pvarg.vt;
                  pRecInfo = pvarg.pRecInfo;
                  VariantInit(&v41);
                  v16 = *(_OWORD *)&v41.vt;
                  v17 = v41.pRecInfo;
                  if ( !v3 )
                    v3 = L"S-1-5-18";
                  v18 = _variant_t::_variant_t((_variant_t *)&v49, v3);
                  v19 = *(_QWORD *)v30;
                  v20 = *(_OWORD *)v18;
                  v21 = *((_QWORD *)v18 + 2);
                  v22 = _bstr_t::_bstr_t((_bstr_t *)Block, L"Passport for Work alert created by enrollment client");
                  if ( *(_QWORD *)v22 )
                    v23 = **(_QWORD **)v22;
                  else
                    v23 = 0;
                  v43 = v14;
                  v44 = pRecInfo;
                  v45 = v16;
                  v46 = v17;
                  v47 = v20;
                  v48 = v21;
                  v24 = v13(v12, v23, v19, 6, &v47, &v45, 3, &v43, &v36);
                  v25 = (BSTR *)Block[0];
                  v29[0] = v24;
                  if ( Block[0] )
                  {
                    if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v25 )
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
                    Block[0] = 0;
                  }
                  ATL::CComVariant::~CComVariant(&v49);
                  ATL::CComVariant::~CComVariant(&v41);
                  ATL::CComVariant::~CComVariant(&pvarg);
                  if ( (int)(v29[0] + 0x80000000) >= 0 && v29[0] != -2147024769 )
                  {
                    Logger = CEnrollmentLogger::GetLogger();
                    CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(Logger, v29[0], "ScheduleDeviceEnrollerOnPFW");
                  }
                }
              }
            }
          }
        }
      }
    }
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v39);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v36);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v33);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v34);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v31);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(v37);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(v30);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(v35);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(v38);
    v4 = v29[0];
  }
  if ( v29[1] )
    CoUninitialize();
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v40);
  return v4;
}

```

## disassembly

```asm
0x14000e3a4  mov     rax, rsp
0x14000e3a7  mov     [rax+18h], rbx
0x14000e3ab  push    rbp
0x14000e3ac  push    rsi
0x14000e3ad  push    rdi
0x14000e3ae  push    r14
0x14000e3b0  push    r15
0x14000e3b2  lea     rbp, [rax-338h]
0x14000e3b9  sub     rsp, 410h
0x14000e3c0  movaps  xmmword ptr [rax-38h], xmm6
0x14000e3c4  movaps  xmmword ptr [rax-48h], xmm7
0x14000e3c8  movaps  xmmword ptr [rax-58h], xmm8
0x14000e3cd  movaps  xmmword ptr [rax-68h], xmm9
0x14000e3d2  movaps  xmmword ptr [rax-78h], xmm10
0x14000e3d7  movaps  xmmword ptr [rax-88h], xmm11
0x14000e3df  mov     rax, cs:__security_cookie
0x14000e3e6  xor     rax, rsp
0x14000e3e9  mov     [rbp+330h+var_90], rax
0x14000e3f0  lea     rax, aScheduledevice_0; "ScheduleDeviceEnrollerOnPFW"
0x14000e3f7  mov     rdi, rcx
0x14000e3fa  mov     [rbp+330h+var_360], rax
0x14000e3fe  lea     rcx, [rsp+430h+var_3C0+4]; this
0x14000e403  lea     rax, [rsp+430h+var_3C0]
0x14000e408  xor     r15d, r15d
0x14000e40b  mov     [rbp+330h+var_358], rax
0x14000e40f  mov     rsi, rdx
0x14000e412  mov     [rsp+430h+var_3C0], r15d
0x14000e417  mov     [rsp+430h+var_3C0+4], r15d
0x14000e41c  call    ?CoInitializeEx@AutoCoInitialize@@QEAAJK@Z; AutoCoInitialize::CoInitializeEx(ulong)
0x14000e421  mov     [rsp+430h+var_3C0], eax
0x14000e425  mov     ebx, eax
0x14000e427  test    eax, eax
0x14000e429  js      loc_14000E7E2
0x14000e42f  mov     r9, rdi
0x14000e432  mov     qword ptr [rbp+330h+var_370], r15
0x14000e436  lea     r8, aOSCPfw; "/o \"%s\" /c /PFW"
0x14000e43d  mov     qword ptr [rbp+330h+var_388], r15
0x14000e441  mov     edx, 104h; unsigned __int64
0x14000e446  mov     qword ptr [rsp+430h+var_3B8], r15
0x14000e44b  lea     rcx, [rbp+330h+var_2A0]; unsigned __int16 *
0x14000e452  mov     qword ptr [rbp+330h+var_378], r15
0x14000e456  mov     [rbp+330h+var_3B0], r15
0x14000e45a  mov     [rbp+330h+var_390], r15
0x14000e45e  mov     [rbp+330h+var_398], r15
0x14000e462  mov     [rbp+330h+var_380], r15
0x14000e466  mov     [rbp+330h+var_368], r15
0x14000e46a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000e46f  mov     [rsp+430h+var_3C0], eax
0x14000e473  test    eax, eax
0x14000e475  js      loc_14000E78C
0x14000e47b  mov     [rsp+430h+Data], r15d; Data
0x14000e480  lea     rax, [rbp+330h+var_2A0]
0x14000e487  mov     [rsp+430h+var_3D8], r15d; int
0x14000e48c  lea     r9, [rbp+330h+var_378]; int
0x14000e490  mov     [rsp+430h+var_3E0], r15d; int
0x14000e495  lea     r8, [rsp+430h+var_3B8]; int
0x14000e49a  mov     [rsp+430h+var_3E8], 1; int
0x14000e4a2  lea     rdx, [rbp+330h+var_388]; int
0x14000e4a6  mov     [rsp+430h+var_3F0], r15d; int
0x14000e4ab  lea     rcx, [rbp+330h+var_370]; int
0x14000e4af  mov     [rsp+430h+var_3F8], rsi; unsigned __int16 *
0x14000e4b4  mov     [rsp+430h+var_400], rax; unsigned __int16 *
0x14000e4b9  lea     rax, aWindirSystem32_1; "%windir%\\system32\\deviceenroller.exe "
0x14000e4c0  mov     [rsp+430h+var_408], rax; unsigned __int16 *
0x14000e4c5  mov     [rsp+430h+var_410], rdi; unsigned __int16 *
0x14000e4ca  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x14000e4cf  mov     [rsp+430h+var_3C0], eax
0x14000e4d3  test    eax, eax
0x14000e4d5  js      loc_14000E78C
0x14000e4db  mov     rcx, qword ptr [rsp+430h+var_3B8]
0x14000e4e0  lea     rdx, [rbp+330h+var_3B0]
0x14000e4e4  mov     rax, [rcx]
0x14000e4e7  mov     rax, [rax+48h]
0x14000e4eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e4f0  mov     [rsp+430h+var_3C0], eax
0x14000e4f4  test    eax, eax
0x14000e4f6  js      loc_14000E78C
0x14000e4fc  mov     rcx, [rbp+330h+var_3B0]
0x14000e500  lea     r8, [rbp+330h+var_390]
0x14000e504  xor     edx, edx
0x14000e506  mov     rax, [rcx]
0x14000e509  mov     rax, [rax+50h]
0x14000e50d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e512  mov     [rsp+430h+var_3C0], eax
0x14000e516  test    eax, eax
0x14000e518  js      loc_14000E78C
0x14000e51e  mov     rcx, [rbp+330h+var_390]
0x14000e522  lea     r8, [rbp+330h+var_398]
0x14000e526  lea     rdx, IID_IEventTrigger
0x14000e52d  mov     rax, [rcx]
0x14000e530  mov     rax, [rax]
0x14000e533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e538  mov     [rsp+430h+var_3C0], eax
0x14000e53c  test    eax, eax
0x14000e53e  js      loc_14000E78C
0x14000e544  mov     rbx, [rbp+330h+var_398]
0x14000e548  lea     rdx, aQuerylistQuery; "<QueryList><Query Id=\"0\" Path=\"Micro"...
0x14000e54f  lea     rcx, [rbp+330h+Block]; this
0x14000e553  mov     rax, [rbx]
0x14000e556  mov     rdi, [rax+0A8h]
0x14000e55d  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14000e562  mov     rdx, [rax]
0x14000e565  test    rdx, rdx
0x14000e568  jz      short loc_14000E56F
0x14000e56a  mov     rdx, [rdx]
0x14000e56d  jmp     short loc_14000E572
0x14000e56f  mov     rdx, r15
0x14000e572  mov     rcx, rbx
0x14000e575  mov     rax, rdi
0x14000e578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e57d  mov     rbx, [rbp+330h+Block]
0x14000e581  mov     [rsp+430h+var_3C0], eax
0x14000e585  test    rbx, rbx
0x14000e588  jz      short loc_14000E5D2
0x14000e58a  or      eax, 0FFFFFFFFh
0x14000e58d  lock xadd [rbx+10h], eax
0x14000e592  cmp     eax, 1
0x14000e595  jnz     short loc_14000E5D2
0x14000e597  test    rbx, rbx
0x14000e59a  jz      short loc_14000E5D2
0x14000e59c  mov     rcx, [rbx]; bstrString
0x14000e59f  test    rcx, rcx
0x14000e5a2  jz      short loc_14000E5B3
0x14000e5a4  call    cs:__imp_SysFreeString
0x14000e5ab  nop     dword ptr [rax+rax+00h]
0x14000e5b0  mov     [rbx], r15
0x14000e5b3  mov     rcx, [rbx+8]; Block
0x14000e5b7  test    rcx, rcx
0x14000e5ba  jz      short loc_14000E5C5
0x14000e5bc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000e5c1  mov     [rbx+8], r15
0x14000e5c5  mov     edx, 18h
0x14000e5ca  mov     rcx, rbx; Block
0x14000e5cd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000e5d2  cmp     [rsp+430h+var_3C0], r15d
0x14000e5d7  jl      loc_14000E78C
0x14000e5dd  mov     rcx, qword ptr [rsp+430h+var_3B8]
0x14000e5e2  mov     rdx, [rbp+330h+var_3B0]
0x14000e5e6  mov     rax, [rcx]
0x14000e5e9  mov     rax, [rax+50h]
0x14000e5ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e5f2  mov     [rsp+430h+var_3C0], eax
0x14000e5f6  test    eax, eax
0x14000e5f8  js      loc_14000E78C
0x14000e5fe  mov     rbx, qword ptr [rbp+330h+var_388]
0x14000e602  lea     rcx, [rbp+330h+pvarg]; pvarg
0x14000e606  mov     rax, [rbx]
0x14000e609  mov     r14, [rax+88h]
0x14000e610  call    cs:__imp_VariantInit
0x14000e617  nop     dword ptr [rax+rax+00h]
0x14000e61c  movups  xmm6, xmmword ptr [rbp+330h+pvarg]
0x14000e620  lea     rcx, [rbp+330h+var_350]; pvarg
0x14000e624  movsd   xmm7, qword ptr [rbp+330h+pvarg+10h]
0x14000e629  call    cs:__imp_VariantInit
0x14000e630  nop     dword ptr [rax+rax+00h]
0x14000e635  movups  xmm8, xmmword ptr [rbp+330h+var_350]
0x14000e63a  lea     rax, aS1518; "S-1-5-18"
0x14000e641  test    rsi, rsi
0x14000e644  movsd   xmm9, qword ptr [rbp+330h+var_350+10h]
0x14000e64a  lea     rcx, [rbp+330h+var_2C0]; this
0x14000e64e  cmovz   rsi, rax
0x14000e652  mov     rdx, rsi; unsigned __int16 *
0x14000e655  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x14000e65a  mov     rdi, qword ptr [rsp+430h+var_3B8]
0x14000e65f  lea     rdx, aPassportForWor; "Passport for Work alert created by enro"...
0x14000e666  lea     rcx, [rbp+330h+Block]; this
0x14000e66a  movups  xmm10, xmmword ptr [rax]
0x14000e66e  movsd   xmm11, qword ptr [rax+10h]
0x14000e674  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14000e679  mov     rdx, [rax]
0x14000e67c  test    rdx, rdx
0x14000e67f  jz      short loc_14000E686
0x14000e681  mov     rdx, [rdx]
0x14000e684  jmp     short loc_14000E689
0x14000e686  mov     rdx, r15
0x14000e689  lea     rax, [rbp+330h+var_380]
0x14000e68d  movaps  [rbp+330h+var_320], xmm6
0x14000e691  mov     qword ptr [rsp+430h+var_3F0], rax
0x14000e696  mov     r9d, 6
0x14000e69c  lea     rax, [rbp+330h+var_320]
0x14000e6a0  movsd   [rbp+330h+var_310], xmm7
0x14000e6a5  mov     [rsp+430h+var_3F8], rax
0x14000e6aa  mov     r8, rdi
0x14000e6ad  lea     rax, [rbp+330h+var_300]
0x14000e6b1  mov     dword ptr [rsp+430h+var_400], 3
0x14000e6b9  mov     [rsp+430h+var_408], rax
0x14000e6be  mov     rcx, rbx
0x14000e6c1  lea     rax, [rbp+330h+var_2E0]
0x14000e6c5  movaps  [rbp+330h+var_300], xmm8
0x14000e6ca  mov     [rsp+430h+var_410], rax
0x14000e6cf  mov     rax, r14
0x14000e6d2  movsd   [rbp+330h+var_2F0], xmm9
0x14000e6d8  movaps  [rbp+330h+var_2E0], xmm10
0x14000e6dd  movsd   [rbp+330h+var_2D0], xmm11
0x14000e6e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e6e8  mov     rbx, [rbp+330h+Block]
0x14000e6ec  mov     [rsp+430h+var_3C0], eax
0x14000e6f0  test    rbx, rbx
0x14000e6f3  jz      short loc_14000E741
0x14000e6f5  or      eax, 0FFFFFFFFh
0x14000e6f8  lock xadd [rbx+10h], eax
0x14000e6fd  cmp     eax, 1
0x14000e700  jnz     short loc_14000E73D
0x14000e702  test    rbx, rbx
0x14000e705  jz      short loc_14000E73D
0x14000e707  mov     rcx, [rbx]; bstrString
0x14000e70a  test    rcx, rcx
0x14000e70d  jz      short loc_14000E71E
0x14000e70f  call    cs:__imp_SysFreeString
0x14000e716  nop     dword ptr [rax+rax+00h]
0x14000e71b  mov     [rbx], r15
0x14000e71e  mov     rcx, [rbx+8]; Block
0x14000e722  test    rcx, rcx
0x14000e725  jz      short loc_14000E730
0x14000e727  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000e72c  mov     [rbx+8], r15
0x14000e730  mov     edx, 18h
0x14000e735  mov     rcx, rbx; Block
0x14000e738  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000e73d  mov     [rbp+330h+Block], r15
0x14000e741  lea     rcx, [rbp+330h+var_2C0]; pvarg
0x14000e745  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000e74a  lea     rcx, [rbp+330h+var_350]; pvarg
0x14000e74e  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000e753  lea     rcx, [rbp+330h+pvarg]; pvarg
0x14000e757  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000e75c  mov     ecx, [rsp+430h+var_3C0]
0x14000e760  mov     edx, 80000000h
0x14000e765  lea     eax, [rcx+rdx]
0x14000e768  test    edx, eax
0x14000e76a  jnz     short loc_14000E78C
0x14000e76c  cmp     ecx, 8007007Fh
0x14000e772  jz      short loc_14000E78C
0x14000e774  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x14000e779  mov     edx, [rsp+430h+var_3C0]; int
0x14000e77d  lea     r8, aScheduledevice_0; "ScheduleDeviceEnrollerOnPFW"
0x14000e784  mov     rcx, rax; this
0x14000e787  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x14000e78c  lea     rcx, [rbp+330h+var_368]
0x14000e790  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000e795  lea     rcx, [rbp+330h+var_380]
0x14000e799  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000e79e  lea     rcx, [rbp+330h+var_398]
0x14000e7a2  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000e7a7  lea     rcx, [rbp+330h+var_390]
0x14000e7ab  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000e7b0  lea     rcx, [rbp+330h+var_3B0]
0x14000e7b4  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000e7b9  lea     rcx, [rbp+330h+var_378]
0x14000e7bd  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000e7c2  lea     rcx, [rsp+430h+var_3B8]
0x14000e7c7  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000e7cc  lea     rcx, [rbp+330h+var_388]
0x14000e7d0  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000e7d5  lea     rcx, [rbp+330h+var_370]
0x14000e7d9  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000e7de  mov     ebx, [rsp+430h+var_3C0]
0x14000e7e2  cmp     [rsp+430h+var_3C0+4], r15d
0x14000e7e7  jz      short loc_14000E7F5
0x14000e7e9  call    cs:__imp_CoUninitialize
0x14000e7f0  nop     dword ptr [rax+rax+00h]
0x14000e7f5  lea     rcx, [rbp+330h+var_360]; this
0x14000e7f9  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x14000e7fe  mov     eax, ebx
0x14000e800  mov     rcx, [rbp+330h+var_90]
0x14000e807  xor     rcx, rsp; StackCookie
0x14000e80a  call    __security_check_cookie
0x14000e80f  lea     r11, [rsp+430h+var_20]
0x14000e817  mov     rbx, [r11+40h]
0x14000e81b  movaps  xmm6, xmmword ptr [r11-10h]
0x14000e820  movaps  xmm7, xmmword ptr [r11-20h]
0x14000e825  movaps  xmm8, xmmword ptr [r11-30h]
0x14000e82a  movaps  xmm9, xmmword ptr [r11-40h]
0x14000e82f  movaps  xmm10, xmmword ptr [r11-50h]
0x14000e834  movaps  xmm11, xmmword ptr [r11-60h]
0x14000e839  mov     rsp, r11
0x14000e83c  pop     r15
0x14000e83e  pop     r14
0x14000e840  pop     rdi
0x14000e841  pop     rsi
0x14000e842  pop     rbp
0x14000e843  retn
```
