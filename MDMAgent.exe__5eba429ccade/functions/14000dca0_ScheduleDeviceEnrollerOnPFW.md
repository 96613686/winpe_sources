# ScheduleDeviceEnrollerOnPFW

- ea: `0x14000dca0`
- end: `0x14000e122`
- name: `ScheduleDeviceEnrollerOnPFW`
- size: `1154`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x140010000`

## callees

- `0x140002930`
- `0x140002954`
- `0x1400046a4`
- `0x140004c34`
- `0x140007368`
- `0x140008dc8`
- `0x140008e48`
- `0x1400090fc`
- `0x140009cd8`
- `0x14000a0b8`
- `0x14000dca0`
- `0x1400177b0`
- `0x140017ba0`
- `0x140019010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000dea0`
- `OLEAUT32!__imp_SysFreeString` at `0x14000dff9`
- `OLEAUT32!__imp_SysFreeString` at `0x14000dea0`
- `OLEAUT32!__imp_SysFreeString` at `0x14000dff9`
- `OLEAUT32!__imp_VariantInit` at `0x14000df06`
- `OLEAUT32!__imp_VariantInit` at `0x14000df19`
- `OLEAUT32!__imp_VariantInit` at `0x14000df06`
- `OLEAUT32!__imp_VariantInit` at `0x14000df19`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000e0cd`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000e0cd`

## string_xrefs

- `0x14000ddb5`: `%windir%\system32\deviceenroller.exe `
- `0x14000dcec`: `ScheduleDeviceEnrollerOnPFW`
- `0x14000e061`: `ScheduleDeviceEnrollerOnPFW`
- `0x14000df49`: `Passport for Work alert created by enrollment client`
- `0x14000de44`: `<QueryList><Query Id="0" Path="Microsoft-Windows-User Device Registration/Admin"><Select Path="Microsoft-Windows-User Device Registration/Admin">*[System[Provider[@Name='Microsoft-Windows-User Device Registration'] and EventID=300]]</Select></Query></QueryList>`

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
                 v38,
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
0x14000dca0  mov     rax, rsp
0x14000dca3  mov     [rax+18h], rbx
0x14000dca7  push    rbp
0x14000dca8  push    rsi
0x14000dca9  push    rdi
0x14000dcaa  push    r14
0x14000dcac  push    r15
0x14000dcae  lea     rbp, [rax-338h]
0x14000dcb5  sub     rsp, 410h
0x14000dcbc  movaps  xmmword ptr [rax-38h], xmm6
0x14000dcc0  movaps  xmmword ptr [rax-48h], xmm7
0x14000dcc4  movaps  xmmword ptr [rax-58h], xmm8
0x14000dcc9  movaps  xmmword ptr [rax-68h], xmm9
0x14000dcce  movaps  xmmword ptr [rax-78h], xmm10
0x14000dcd3  movaps  xmmword ptr [rax-88h], xmm11
0x14000dcdb  mov     rax, cs:__security_cookie
0x14000dce2  xor     rax, rsp
0x14000dce5  mov     [rbp+330h+var_90], rax
0x14000dcec  lea     rax, aScheduledevice_0; "ScheduleDeviceEnrollerOnPFW"
0x14000dcf3  mov     rdi, rcx
0x14000dcf6  mov     [rbp+330h+var_360], rax
0x14000dcfa  lea     rcx, [rsp+430h+var_3C0+4]; this
0x14000dcff  lea     rax, [rsp+430h+var_3C0]
0x14000dd04  xor     r15d, r15d
0x14000dd07  mov     [rbp+330h+var_358], rax
0x14000dd0b  mov     rsi, rdx
0x14000dd0e  mov     [rsp+430h+var_3C0], r15d
0x14000dd13  mov     [rsp+430h+var_3C0+4], r15d
0x14000dd18  call    ?CoInitializeEx@AutoCoInitialize@@QEAAJK@Z; AutoCoInitialize::CoInitializeEx(ulong)
0x14000dd1d  mov     [rsp+430h+var_3C0], eax
0x14000dd21  mov     ebx, eax
0x14000dd23  test    eax, eax
0x14000dd25  js      loc_14000E0C6
0x14000dd2b  mov     r9, rdi
0x14000dd2e  mov     qword ptr [rbp+330h+var_370], r15
0x14000dd32  lea     r8, aOSCPfw; "/o \"%s\" /c /PFW"
0x14000dd39  mov     qword ptr [rbp+330h+var_388], r15
0x14000dd3d  mov     edx, 104h; unsigned __int64
0x14000dd42  mov     qword ptr [rsp+430h+var_3B8], r15
0x14000dd47  lea     rcx, [rbp+330h+var_2A0]; unsigned __int16 *
0x14000dd4e  mov     qword ptr [rbp+330h+var_378], r15
0x14000dd52  mov     [rbp+330h+var_3B0], r15
0x14000dd56  mov     [rbp+330h+var_390], r15
0x14000dd5a  mov     [rbp+330h+var_398], r15
0x14000dd5e  mov     [rbp+330h+var_380], r15
0x14000dd62  mov     [rbp+330h+var_368], r15
0x14000dd66  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000dd6b  mov     [rsp+430h+var_3C0], eax
0x14000dd6f  test    eax, eax
0x14000dd71  js      loc_14000E070
0x14000dd77  mov     [rsp+430h+Data], r15d; Data
0x14000dd7c  lea     rax, [rbp+330h+var_2A0]
0x14000dd83  mov     [rsp+430h+var_3D8], r15d; int
0x14000dd88  lea     r9, [rbp+330h+var_378]; int
0x14000dd8c  mov     [rsp+430h+var_3E0], r15d; int
0x14000dd91  lea     r8, [rsp+430h+var_3B8]; int
0x14000dd96  mov     [rsp+430h+var_3E8], 1; int
0x14000dd9e  lea     rdx, [rbp+330h+var_388]; int
0x14000dda2  mov     [rsp+430h+var_3F0], r15d; int
0x14000dda7  lea     rcx, [rbp+330h+var_370]; int
0x14000ddab  mov     [rsp+430h+var_3F8], rsi; unsigned __int16 *
0x14000ddb0  mov     [rsp+430h+var_400], rax; unsigned __int16 *
0x14000ddb5  lea     rax, aWindirSystem32_1; "%windir%\\system32\\deviceenroller.exe "
0x14000ddbc  mov     [rsp+430h+var_408], rax; unsigned __int16 *
0x14000ddc1  mov     [rsp+430h+var_410], rdi; unsigned __int16 *
0x14000ddc6  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x14000ddcb  mov     [rsp+430h+var_3C0], eax
0x14000ddcf  test    eax, eax
0x14000ddd1  js      loc_14000E070
0x14000ddd7  mov     rcx, qword ptr [rsp+430h+var_3B8]
0x14000dddc  lea     rdx, [rbp+330h+var_3B0]
0x14000dde0  mov     rax, [rcx]
0x14000dde3  mov     rax, [rax+48h]
0x14000dde7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ddec  mov     [rsp+430h+var_3C0], eax
0x14000ddf0  test    eax, eax
0x14000ddf2  js      loc_14000E070
0x14000ddf8  mov     rcx, [rbp+330h+var_3B0]
0x14000ddfc  lea     r8, [rbp+330h+var_390]
0x14000de00  xor     edx, edx
0x14000de02  mov     rax, [rcx]
0x14000de05  mov     rax, [rax+50h]
0x14000de09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000de0e  mov     [rsp+430h+var_3C0], eax
0x14000de12  test    eax, eax
0x14000de14  js      loc_14000E070
0x14000de1a  mov     rcx, [rbp+330h+var_390]
0x14000de1e  lea     r8, [rbp+330h+var_398]
0x14000de22  lea     rdx, IID_IEventTrigger
0x14000de29  mov     rax, [rcx]
0x14000de2c  mov     rax, [rax]
0x14000de2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000de34  mov     [rsp+430h+var_3C0], eax
0x14000de38  test    eax, eax
0x14000de3a  js      loc_14000E070
0x14000de40  mov     rbx, [rbp+330h+var_398]
0x14000de44  lea     rdx, aQuerylistQuery; "<QueryList><Query Id=\"0\" Path=\"Micro"...
0x14000de4b  lea     rcx, [rbp+330h+Block]; this
0x14000de4f  mov     rax, [rbx]
0x14000de52  mov     rdi, [rax+0A8h]
0x14000de59  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14000de5e  mov     rdx, [rax]
0x14000de61  test    rdx, rdx
0x14000de64  jz      short loc_14000DE6B
0x14000de66  mov     rdx, [rdx]
0x14000de69  jmp     short loc_14000DE6E
0x14000de6b  mov     rdx, r15
0x14000de6e  mov     rcx, rbx
0x14000de71  mov     rax, rdi
0x14000de74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000de79  mov     rbx, [rbp+330h+Block]
0x14000de7d  mov     [rsp+430h+var_3C0], eax
0x14000de81  test    rbx, rbx
0x14000de84  jz      short loc_14000DEC8
0x14000de86  or      eax, 0FFFFFFFFh
0x14000de89  lock xadd [rbx+10h], eax
0x14000de8e  cmp     eax, 1
0x14000de91  jnz     short loc_14000DEC8
0x14000de93  test    rbx, rbx
0x14000de96  jz      short loc_14000DEC8
0x14000de98  mov     rcx, [rbx]; bstrString
0x14000de9b  test    rcx, rcx
0x14000de9e  jz      short loc_14000DEA9
0x14000dea0  call    cs:__imp_SysFreeString
0x14000dea6  mov     [rbx], r15
0x14000dea9  mov     rcx, [rbx+8]; Block
0x14000dead  test    rcx, rcx
0x14000deb0  jz      short loc_14000DEBB
0x14000deb2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000deb7  mov     [rbx+8], r15
0x14000debb  mov     edx, 18h
0x14000dec0  mov     rcx, rbx; Block
0x14000dec3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000dec8  cmp     [rsp+430h+var_3C0], r15d
0x14000decd  jl      loc_14000E070
0x14000ded3  mov     rcx, qword ptr [rsp+430h+var_3B8]
0x14000ded8  mov     rdx, [rbp+330h+var_3B0]
0x14000dedc  mov     rax, [rcx]
0x14000dedf  mov     rax, [rax+50h]
0x14000dee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dee8  mov     [rsp+430h+var_3C0], eax
0x14000deec  test    eax, eax
0x14000deee  js      loc_14000E070
0x14000def4  mov     rbx, qword ptr [rbp+330h+var_388]
0x14000def8  lea     rcx, [rbp+330h+pvarg]; pvarg
0x14000defc  mov     rax, [rbx]
0x14000deff  mov     r14, [rax+88h]
0x14000df06  call    cs:__imp_VariantInit
0x14000df0c  movups  xmm6, xmmword ptr [rbp+330h+pvarg]
0x14000df10  lea     rcx, [rbp+330h+var_350]; pvarg
0x14000df14  movsd   xmm7, qword ptr [rbp+330h+pvarg+10h]
0x14000df19  call    cs:__imp_VariantInit
0x14000df1f  movups  xmm8, xmmword ptr [rbp+330h+var_350]
0x14000df24  lea     rax, aS1518; "S-1-5-18"
0x14000df2b  test    rsi, rsi
0x14000df2e  movsd   xmm9, qword ptr [rbp+330h+var_350+10h]
0x14000df34  lea     rcx, [rbp+330h+var_2C0]; this
0x14000df38  cmovz   rsi, rax
0x14000df3c  mov     rdx, rsi; unsigned __int16 *
0x14000df3f  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x14000df44  mov     rdi, qword ptr [rsp+430h+var_3B8]
0x14000df49  lea     rdx, aPassportForWor; "Passport for Work alert created by enro"...
0x14000df50  lea     rcx, [rbp+330h+Block]; this
0x14000df54  movups  xmm10, xmmword ptr [rax]
0x14000df58  movsd   xmm11, qword ptr [rax+10h]
0x14000df5e  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14000df63  mov     rdx, [rax]
0x14000df66  test    rdx, rdx
0x14000df69  jz      short loc_14000DF70
0x14000df6b  mov     rdx, [rdx]
0x14000df6e  jmp     short loc_14000DF73
0x14000df70  mov     rdx, r15
0x14000df73  lea     rax, [rbp+330h+var_380]
0x14000df77  movaps  [rbp+330h+var_320], xmm6
0x14000df7b  mov     qword ptr [rsp+430h+var_3F0], rax
0x14000df80  mov     r9d, 6
0x14000df86  lea     rax, [rbp+330h+var_320]
0x14000df8a  movsd   [rbp+330h+var_310], xmm7
0x14000df8f  mov     [rsp+430h+var_3F8], rax
0x14000df94  mov     r8, rdi
0x14000df97  lea     rax, [rbp+330h+var_300]
0x14000df9b  mov     dword ptr [rsp+430h+var_400], 3
0x14000dfa3  mov     [rsp+430h+var_408], rax
0x14000dfa8  mov     rcx, rbx
0x14000dfab  lea     rax, [rbp+330h+var_2E0]
0x14000dfaf  movaps  [rbp+330h+var_300], xmm8
0x14000dfb4  mov     [rsp+430h+var_410], rax
0x14000dfb9  mov     rax, r14
0x14000dfbc  movsd   [rbp+330h+var_2F0], xmm9
0x14000dfc2  movaps  [rbp+330h+var_2E0], xmm10
0x14000dfc7  movsd   [rbp+330h+var_2D0], xmm11
0x14000dfcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dfd2  mov     rbx, [rbp+330h+Block]
0x14000dfd6  mov     [rsp+430h+var_3C0], eax
0x14000dfda  test    rbx, rbx
0x14000dfdd  jz      short loc_14000E025
0x14000dfdf  or      eax, 0FFFFFFFFh
0x14000dfe2  lock xadd [rbx+10h], eax
0x14000dfe7  cmp     eax, 1
0x14000dfea  jnz     short loc_14000E021
0x14000dfec  test    rbx, rbx
0x14000dfef  jz      short loc_14000E021
0x14000dff1  mov     rcx, [rbx]; bstrString
0x14000dff4  test    rcx, rcx
0x14000dff7  jz      short loc_14000E002
0x14000dff9  call    cs:__imp_SysFreeString
0x14000dfff  mov     [rbx], r15
0x14000e002  mov     rcx, [rbx+8]; Block
0x14000e006  test    rcx, rcx
0x14000e009  jz      short loc_14000E014
0x14000e00b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000e010  mov     [rbx+8], r15
0x14000e014  mov     edx, 18h
0x14000e019  mov     rcx, rbx; Block
0x14000e01c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000e021  mov     [rbp+330h+Block], r15
0x14000e025  lea     rcx, [rbp+330h+var_2C0]; pvarg
0x14000e029  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000e02e  lea     rcx, [rbp+330h+var_350]; pvarg
0x14000e032  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000e037  lea     rcx, [rbp+330h+pvarg]; pvarg
0x14000e03b  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000e040  mov     ecx, [rsp+430h+var_3C0]
0x14000e044  mov     edx, 80000000h
0x14000e049  lea     eax, [rcx+rdx]
0x14000e04c  test    edx, eax
0x14000e04e  jnz     short loc_14000E070
0x14000e050  cmp     ecx, 8007007Fh
0x14000e056  jz      short loc_14000E070
0x14000e058  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x14000e05d  mov     edx, [rsp+430h+var_3C0]; int
0x14000e061  lea     r8, aScheduledevice_0; "ScheduleDeviceEnrollerOnPFW"
0x14000e068  mov     rcx, rax; this
0x14000e06b  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x14000e070  lea     rcx, [rbp+330h+var_368]
0x14000e074  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000e079  lea     rcx, [rbp+330h+var_380]
0x14000e07d  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000e082  lea     rcx, [rbp+330h+var_398]
0x14000e086  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000e08b  lea     rcx, [rbp+330h+var_390]
0x14000e08f  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000e094  lea     rcx, [rbp+330h+var_3B0]
0x14000e098  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000e09d  lea     rcx, [rbp+330h+var_378]
0x14000e0a1  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000e0a6  lea     rcx, [rsp+430h+var_3B8]
0x14000e0ab  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000e0b0  lea     rcx, [rbp+330h+var_388]
0x14000e0b4  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000e0b9  lea     rcx, [rbp+330h+var_370]
0x14000e0bd  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000e0c2  mov     ebx, [rsp+430h+var_3C0]
0x14000e0c6  cmp     [rsp+430h+var_3C0+4], r15d
0x14000e0cb  jz      short loc_14000E0D3
0x14000e0cd  call    cs:__imp_CoUninitialize
0x14000e0d3  lea     rcx, [rbp+330h+var_360]; this
0x14000e0d7  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x14000e0dc  mov     eax, ebx
0x14000e0de  mov     rcx, [rbp+330h+var_90]
0x14000e0e5  xor     rcx, rsp; StackCookie
0x14000e0e8  call    __security_check_cookie
0x14000e0ed  lea     r11, [rsp+430h+var_20]
0x14000e0f5  mov     rbx, [r11+40h]
0x14000e0f9  movaps  xmm6, xmmword ptr [r11-10h]
0x14000e0fe  movaps  xmm7, xmmword ptr [r11-20h]
0x14000e103  movaps  xmm8, xmmword ptr [r11-30h]
0x14000e108  movaps  xmm9, xmmword ptr [r11-40h]
0x14000e10d  movaps  xmm10, xmmword ptr [r11-50h]
0x14000e112  movaps  xmm11, xmmword ptr [r11-60h]
0x14000e117  mov     rsp, r11
0x14000e11a  pop     r15
0x14000e11c  pop     r14
0x14000e11e  pop     rdi
0x14000e11f  pop     rsi
0x14000e120  pop     rbp
0x14000e121  retn
```
