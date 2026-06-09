# ScheduleDeviceEnrollerOnPFW

- ea: `0x18000d590`
- end: `0x18000da31`
- name: `ScheduleDeviceEnrollerOnPFW`
- size: `1185`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000fc24`

## callees

- `0x180001c60`
- `0x180001cc8`
- `0x1800051d8`
- `0x180007258`
- `0x1800072d0`
- `0x180007364`
- `0x1800077a0`
- `0x1800079e8`
- `0x1800086c4`
- `0x180008bd4`
- `0x18000d590`
- `0x18001b9d8`
- `0x18001bde0`
- `0x18001e010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000d790`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d8fb`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d790`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d8fb`
- `OLEAUT32!__imp_VariantInit` at `0x18000d7fc`
- `OLEAUT32!__imp_VariantInit` at `0x18000d815`
- `OLEAUT32!__imp_VariantInit` at `0x18000d7fc`
- `OLEAUT32!__imp_VariantInit` at `0x18000d815`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000d9d5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000d9d5`

## string_xrefs

- `0x18000d6a5`: `%windir%\system32\deviceenroller.exe `
- `0x18000d5dc`: `ScheduleDeviceEnrollerOnPFW`
- `0x18000d969`: `ScheduleDeviceEnrollerOnPFW`
- `0x18000d84b`: `Passport for Work alert created by enrollment client`
- `0x18000d734`: `<QueryList><Query Id="0" Path="Microsoft-Windows-User Device Registration/Admin"><Select Path="Microsoft-Windows-User Device Registration/Admin">*[System[Provider[@Name='Microsoft-Windows-User Device Registration'] and EventID=300]]</Select></Query></QueryList>`

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
  const struct std::nothrow_t *v10; // rdx
  BSTR *v11; // rbx
  BSTR v12; // rcx
  struct IUnknown *v13; // rbx
  ULONG (__stdcall *Release)(IUnknown *); // r14
  __int128 v15; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  __int128 v17; // xmm8
  IRecordInfo *v18; // xmm9_8
  _variant_t *v19; // rax
  __int64 v20; // rdi
  __int128 v21; // xmm10
  __int64 v22; // xmm11_8
  _bstr_t *v23; // rax
  __int64 v24; // rdx
  int v25; // eax
  const struct std::nothrow_t *v26; // rdx
  BSTR *v27; // rbx
  BSTR v28; // rcx
  CEnrollmentLogger *Logger; // rax
  __int64 v31; // [rsp+48h] [rbp-C0h]
  int v32; // [rsp+68h] [rbp-A0h]
  int v33[2]; // [rsp+78h] [rbp-90h] BYREF
  __int64 v34; // [rsp+80h] [rbp-88h] BYREF
  __int64 v35; // [rsp+88h] [rbp-80h] BYREF
  void *v36[2]; // [rsp+90h] [rbp-78h] BYREF
  __int64 v37; // [rsp+A0h] [rbp-68h] BYREF
  __int64 (__fastcall ***v38)(_QWORD, GUID *, __int64 *); // [rsp+A8h] [rbp-60h] BYREF
  struct IUnknown *v39; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v40; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v41; // [rsp+C0h] [rbp-48h] BYREF
  LPVOID v42; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v43; // [rsp+D0h] [rbp-38h] BYREF
  _QWORD v44[2]; // [rsp+D8h] [rbp-30h] BYREF
  VARIANTARG v45; // [rsp+E8h] [rbp-20h] BYREF
  VARIANTARG pvarg; // [rsp+100h] [rbp-8h] BYREF
  __int128 v47; // [rsp+118h] [rbp+10h] BYREF
  IRecordInfo *v48; // [rsp+128h] [rbp+20h]
  __int128 v49; // [rsp+138h] [rbp+30h] BYREF
  IRecordInfo *v50; // [rsp+148h] [rbp+40h]
  __int128 v51; // [rsp+158h] [rbp+50h] BYREF
  __int64 v52; // [rsp+168h] [rbp+60h]
  _BYTE v53[32]; // [rsp+178h] [rbp+70h] BYREF
  unsigned __int16 v54[264]; // [rsp+198h] [rbp+90h] BYREF

  v44[0] = "ScheduleDeviceEnrollerOnPFW";
  v44[1] = v33;
  v3 = a2;
  v33[0] = 0;
  v33[1] = 0;
  v33[0] = AutoCoInitialize::CoInitializeEx((AutoCoInitialize *)&v33[1], (unsigned int)a2);
  v4 = v33[0];
  if ( v33[0] >= 0 )
  {
    v42 = 0;
    v39 = 0;
    v34 = 0;
    v41 = 0;
    v35 = 0;
    v38 = 0;
    v37 = 0;
    v40 = 0;
    v43 = 0;
    v33[0] = StringCchPrintfW(v54, 0x104u, L"/o \"%s\" /c /PFW", a1);
    if ( v33[0] >= 0 )
    {
      v32 = 0;
      LODWORD(v31) = 0;
      v33[0] = CreateTask(
                 &v42,
                 &v39,
                 &v34,
                 &v41,
                 a1,
                 L"%windir%\\system32\\deviceenroller.exe ",
                 v54,
                 v3,
                 v31,
                 1,
                 0,
                 0,
                 v32);
      if ( v33[0] >= 0 )
      {
        v33[0] = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v34 + 72LL))(v34, &v35);
        if ( v33[0] >= 0 )
        {
          v33[0] = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v35 + 80LL))(v35, 0, &v38);
          if ( v33[0] >= 0 )
          {
            v33[0] = (**v38)(v38, &IID_IEventTrigger, &v37);
            if ( v33[0] >= 0 )
            {
              v5 = v37;
              v6 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v37 + 168LL);
              v7 = _bstr_t::_bstr_t(
                     (_bstr_t *)v36,
                     L"<QueryList><Query Id=\"0\" Path=\"Microsoft-Windows-User Device Registration/Admin\"><Select Path=\""
                      "Microsoft-Windows-User Device Registration/Admin\">*[System[Provider[@Name='Microsoft-Windows-User"
                      " Device Registration'] and EventID=300]]</Select></Query></QueryList>");
              if ( *(_QWORD *)v7 )
                v8 = **(_QWORD **)v7;
              else
                v8 = 0;
              v9 = v6(v5, v8);
              v11 = (BSTR *)v36[0];
              v33[0] = v9;
              if ( v36[0] && _InterlockedExchangeAdd((volatile signed __int32 *)v36[0] + 4, 0xFFFFFFFF) == 1 && v11 )
              {
                if ( *v11 )
                {
                  SysFreeString(*v11);
                  *v11 = 0;
                }
                v12 = v11[1];
                if ( v12 )
                {
                  operator delete(v12, v10);
                  v11[1] = 0;
                }
                operator delete(v11, (const struct std::nothrow_t *)0x18);
              }
              if ( v33[0] >= 0 )
              {
                v33[0] = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v34 + 80LL))(v34, v35);
                if ( v33[0] >= 0 )
                {
                  v13 = v39;
                  Release = v39->lpVtbl[5].Release;
                  VariantInit(&pvarg);
                  v15 = *(_OWORD *)&pvarg.vt;
                  pRecInfo = pvarg.pRecInfo;
                  VariantInit(&v45);
                  v17 = *(_OWORD *)&v45.vt;
                  v18 = v45.pRecInfo;
                  if ( !v3 )
                    v3 = L"S-1-5-18";
                  v19 = _variant_t::_variant_t((_variant_t *)v53, v3);
                  v20 = v34;
                  v21 = *(_OWORD *)v19;
                  v22 = *((_QWORD *)v19 + 2);
                  v23 = _bstr_t::_bstr_t((_bstr_t *)v36, L"Passport for Work alert created by enrollment client");
                  if ( *(_QWORD *)v23 )
                    v24 = **(_QWORD **)v23;
                  else
                    v24 = 0;
                  v47 = v15;
                  v48 = pRecInfo;
                  v49 = v17;
                  v50 = v18;
                  v51 = v21;
                  v52 = v22;
                  v25 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))Release)(
                          v13,
                          v24,
                          v20,
                          6,
                          &v51,
                          &v49,
                          3,
                          &v47,
                          &v40);
                  v27 = (BSTR *)v36[0];
                  v33[0] = v25;
                  if ( v36[0] )
                  {
                    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v36[0] + 4, 0xFFFFFFFF) == 1 && v27 )
                    {
                      if ( *v27 )
                      {
                        SysFreeString(*v27);
                        *v27 = 0;
                      }
                      v28 = v27[1];
                      if ( v28 )
                      {
                        operator delete(v28, v26);
                        v27[1] = 0;
                      }
                      operator delete(v27, (const struct std::nothrow_t *)0x18);
                    }
                    v36[0] = 0;
                  }
                  _variant_t::~_variant_t((_variant_t *)v53);
                  _variant_t::~_variant_t((_variant_t *)&v45);
                  _variant_t::~_variant_t((_variant_t *)&pvarg);
                  if ( (int)(v33[0] + 0x80000000) >= 0 && v33[0] != -2147024769 )
                  {
                    Logger = CEnrollmentLogger::GetLogger();
                    CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(Logger, v33[0], "ScheduleDeviceEnrollerOnPFW");
                  }
                }
              }
            }
          }
        }
      }
    }
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v43);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v40);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v37);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v38);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v35);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v41);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v34);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v39);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v42);
    v4 = v33[0];
  }
  if ( v33[1] )
    CoUninitialize();
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v44);
  return v4;
}

```

## disassembly

```asm
0x18000d590  mov     rax, rsp
0x18000d593  mov     [rax+18h], rbx
0x18000d597  push    rbp
0x18000d598  push    rsi
0x18000d599  push    rdi
0x18000d59a  push    r14
0x18000d59c  push    r15
0x18000d59e  lea     rbp, [rax-338h]
0x18000d5a5  sub     rsp, 410h
0x18000d5ac  movaps  xmmword ptr [rax-38h], xmm6
0x18000d5b0  movaps  xmmword ptr [rax-48h], xmm7
0x18000d5b4  movaps  xmmword ptr [rax-58h], xmm8
0x18000d5b9  movaps  xmmword ptr [rax-68h], xmm9
0x18000d5be  movaps  xmmword ptr [rax-78h], xmm10
0x18000d5c3  movaps  xmmword ptr [rax-88h], xmm11
0x18000d5cb  mov     rax, cs:__security_cookie
0x18000d5d2  xor     rax, rsp
0x18000d5d5  mov     [rbp+330h+var_90], rax
0x18000d5dc  lea     rax, aScheduledevice_0; "ScheduleDeviceEnrollerOnPFW"
0x18000d5e3  mov     rdi, rcx
0x18000d5e6  mov     [rbp+330h+var_360], rax
0x18000d5ea  lea     rcx, [rsp+430h+var_3C0+4]; this
0x18000d5ef  lea     rax, [rsp+430h+var_3C0]
0x18000d5f4  xor     r15d, r15d
0x18000d5f7  mov     [rbp+330h+var_358], rax
0x18000d5fb  mov     rsi, rdx
0x18000d5fe  mov     [rsp+430h+var_3C0], r15d
0x18000d603  mov     [rsp+430h+var_3C0+4], r15d
0x18000d608  call    ?CoInitializeEx@AutoCoInitialize@@QEAAJK@Z; AutoCoInitialize::CoInitializeEx(ulong)
0x18000d60d  mov     [rsp+430h+var_3C0], eax
0x18000d611  mov     ebx, eax
0x18000d613  test    eax, eax
0x18000d615  js      loc_18000D9CE
0x18000d61b  mov     r9, rdi
0x18000d61e  mov     [rbp+330h+var_370], r15
0x18000d622  lea     r8, aOSCPfw; "/o \"%s\" /c /PFW"
0x18000d629  mov     [rbp+330h+var_388], r15
0x18000d62d  mov     edx, 104h; unsigned __int64
0x18000d632  mov     [rsp+430h+var_3B8], r15
0x18000d637  lea     rcx, [rbp+330h+var_2A0]; unsigned __int16 *
0x18000d63e  mov     [rbp+330h+var_378], r15
0x18000d642  mov     [rbp+330h+var_3B0], r15
0x18000d646  mov     [rbp+330h+var_390], r15
0x18000d64a  mov     [rbp+330h+var_398], r15
0x18000d64e  mov     [rbp+330h+var_380], r15
0x18000d652  mov     [rbp+330h+var_368], r15
0x18000d656  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000d65b  mov     [rsp+430h+var_3C0], eax
0x18000d65f  test    eax, eax
0x18000d661  js      loc_18000D978
0x18000d667  mov     [rsp+430h+var_3D0], r15d
0x18000d66c  lea     rax, [rbp+330h+var_2A0]
0x18000d673  mov     [rsp+430h+var_3D8], r15d
0x18000d678  lea     r9, [rbp+330h+var_378]
0x18000d67c  mov     [rsp+430h+var_3E0], r15d
0x18000d681  lea     r8, [rsp+430h+var_3B8]
0x18000d686  mov     [rsp+430h+var_3E8], 1
0x18000d68e  lea     rdx, [rbp+330h+var_388]
0x18000d692  mov     dword ptr [rsp+430h+var_3F0], r15d
0x18000d697  lea     rcx, [rbp+330h+var_370]
0x18000d69b  mov     [rsp+430h+var_3F8], rsi
0x18000d6a0  mov     [rsp+430h+var_400], rax
0x18000d6a5  lea     rax, aWindirSystem32_1; "%windir%\\system32\\deviceenroller.exe "
0x18000d6ac  mov     [rsp+430h+var_408], rax
0x18000d6b1  mov     [rsp+430h+var_410], rdi
0x18000d6b6  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x18000d6bb  mov     [rsp+430h+var_3C0], eax
0x18000d6bf  test    eax, eax
0x18000d6c1  js      loc_18000D978
0x18000d6c7  mov     rcx, [rsp+430h+var_3B8]
0x18000d6cc  lea     rdx, [rbp+330h+var_3B0]
0x18000d6d0  mov     rax, [rcx]
0x18000d6d3  mov     rax, [rax+48h]
0x18000d6d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6dc  mov     [rsp+430h+var_3C0], eax
0x18000d6e0  test    eax, eax
0x18000d6e2  js      loc_18000D978
0x18000d6e8  mov     rcx, [rbp+330h+var_3B0]
0x18000d6ec  lea     r8, [rbp+330h+var_390]
0x18000d6f0  xor     edx, edx
0x18000d6f2  mov     rax, [rcx]
0x18000d6f5  mov     rax, [rax+50h]
0x18000d6f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6fe  mov     [rsp+430h+var_3C0], eax
0x18000d702  test    eax, eax
0x18000d704  js      loc_18000D978
0x18000d70a  mov     rcx, [rbp+330h+var_390]
0x18000d70e  lea     r8, [rbp+330h+var_398]
0x18000d712  lea     rdx, IID_IEventTrigger
0x18000d719  mov     rax, [rcx]
0x18000d71c  mov     rax, [rax]
0x18000d71f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d724  mov     [rsp+430h+var_3C0], eax
0x18000d728  test    eax, eax
0x18000d72a  js      loc_18000D978
0x18000d730  mov     rbx, [rbp+330h+var_398]
0x18000d734  lea     rdx, aQuerylistQuery; "<QueryList><Query Id=\"0\" Path=\"Micro"...
0x18000d73b  lea     rcx, [rbp+330h+var_3A8]; this
0x18000d73f  mov     rax, [rbx]
0x18000d742  mov     rdi, [rax+0A8h]
0x18000d749  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000d74e  mov     rdx, [rax]
0x18000d751  test    rdx, rdx
0x18000d754  jz      short loc_18000D75B
0x18000d756  mov     rdx, [rdx]
0x18000d759  jmp     short loc_18000D75E
0x18000d75b  mov     rdx, r15
0x18000d75e  mov     rcx, rbx
0x18000d761  mov     rax, rdi
0x18000d764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d769  mov     rbx, [rbp+330h+var_3A8]
0x18000d76d  mov     [rsp+430h+var_3C0], eax
0x18000d771  test    rbx, rbx
0x18000d774  jz      short loc_18000D7BE
0x18000d776  or      eax, 0FFFFFFFFh
0x18000d779  lock xadd [rbx+10h], eax
0x18000d77e  cmp     eax, 1
0x18000d781  jnz     short loc_18000D7BE
0x18000d783  test    rbx, rbx
0x18000d786  jz      short loc_18000D7BE
0x18000d788  mov     rcx, [rbx]; bstrString
0x18000d78b  test    rcx, rcx
0x18000d78e  jz      short loc_18000D79F
0x18000d790  call    cs:__imp_SysFreeString
0x18000d797  nop     dword ptr [rax+rax+00h]
0x18000d79c  mov     [rbx], r15
0x18000d79f  mov     rcx, [rbx+8]; void *
0x18000d7a3  test    rcx, rcx
0x18000d7a6  jz      short loc_18000D7B1
0x18000d7a8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000d7ad  mov     [rbx+8], r15
0x18000d7b1  mov     edx, 18h; struct std::nothrow_t *
0x18000d7b6  mov     rcx, rbx; void *
0x18000d7b9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000d7be  cmp     [rsp+430h+var_3C0], r15d
0x18000d7c3  jl      loc_18000D978
0x18000d7c9  mov     rcx, [rsp+430h+var_3B8]
0x18000d7ce  mov     rdx, [rbp+330h+var_3B0]
0x18000d7d2  mov     rax, [rcx]
0x18000d7d5  mov     rax, [rax+50h]
0x18000d7d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7de  mov     [rsp+430h+var_3C0], eax
0x18000d7e2  test    eax, eax
0x18000d7e4  js      loc_18000D978
0x18000d7ea  mov     rbx, [rbp+330h+var_388]
0x18000d7ee  lea     rcx, [rbp+330h+pvarg]; pvarg
0x18000d7f2  mov     rax, [rbx]
0x18000d7f5  mov     r14, [rax+88h]
0x18000d7fc  call    cs:__imp_VariantInit
0x18000d803  nop     dword ptr [rax+rax+00h]
0x18000d808  movups  xmm6, xmmword ptr [rbp+330h+pvarg]
0x18000d80c  lea     rcx, [rbp+330h+var_350]; pvarg
0x18000d810  movsd   xmm7, qword ptr [rbp+330h+pvarg+10h]
0x18000d815  call    cs:__imp_VariantInit
0x18000d81c  nop     dword ptr [rax+rax+00h]
0x18000d821  movups  xmm8, xmmword ptr [rbp+330h+var_350]
0x18000d826  lea     rax, aS1518; "S-1-5-18"
0x18000d82d  test    rsi, rsi
0x18000d830  movsd   xmm9, qword ptr [rbp+330h+var_350+10h]
0x18000d836  lea     rcx, [rbp+330h+var_2C0]; this
0x18000d83a  cmovz   rsi, rax
0x18000d83e  mov     rdx, rsi; unsigned __int16 *
0x18000d841  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x18000d846  mov     rdi, [rsp+430h+var_3B8]
0x18000d84b  lea     rdx, aPassportForWor; "Passport for Work alert created by enro"...
0x18000d852  lea     rcx, [rbp+330h+var_3A8]; this
0x18000d856  movups  xmm10, xmmword ptr [rax]
0x18000d85a  movsd   xmm11, qword ptr [rax+10h]
0x18000d860  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000d865  mov     rdx, [rax]
0x18000d868  test    rdx, rdx
0x18000d86b  jz      short loc_18000D872
0x18000d86d  mov     rdx, [rdx]
0x18000d870  jmp     short loc_18000D875
0x18000d872  mov     rdx, r15
0x18000d875  lea     rax, [rbp+330h+var_380]
0x18000d879  movaps  [rbp+330h+var_320], xmm6
0x18000d87d  mov     [rsp+430h+var_3F0], rax
0x18000d882  mov     r9d, 6
0x18000d888  lea     rax, [rbp+330h+var_320]
0x18000d88c  movsd   [rbp+330h+var_310], xmm7
0x18000d891  mov     [rsp+430h+var_3F8], rax
0x18000d896  mov     r8, rdi
0x18000d899  lea     rax, [rbp+330h+var_300]
0x18000d89d  mov     dword ptr [rsp+430h+var_400], 3
0x18000d8a5  mov     [rsp+430h+var_408], rax
0x18000d8aa  mov     rcx, rbx
0x18000d8ad  lea     rax, [rbp+330h+var_2E0]
0x18000d8b1  movaps  [rbp+330h+var_300], xmm8
0x18000d8b6  mov     [rsp+430h+var_410], rax
0x18000d8bb  mov     rax, r14
0x18000d8be  movsd   [rbp+330h+var_2F0], xmm9
0x18000d8c4  movaps  [rbp+330h+var_2E0], xmm10
0x18000d8c9  movsd   [rbp+330h+var_2D0], xmm11
0x18000d8cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8d4  mov     rbx, [rbp+330h+var_3A8]
0x18000d8d8  mov     [rsp+430h+var_3C0], eax
0x18000d8dc  test    rbx, rbx
0x18000d8df  jz      short loc_18000D92D
0x18000d8e1  or      eax, 0FFFFFFFFh
0x18000d8e4  lock xadd [rbx+10h], eax
0x18000d8e9  cmp     eax, 1
0x18000d8ec  jnz     short loc_18000D929
0x18000d8ee  test    rbx, rbx
0x18000d8f1  jz      short loc_18000D929
0x18000d8f3  mov     rcx, [rbx]; bstrString
0x18000d8f6  test    rcx, rcx
0x18000d8f9  jz      short loc_18000D90A
0x18000d8fb  call    cs:__imp_SysFreeString
0x18000d902  nop     dword ptr [rax+rax+00h]
0x18000d907  mov     [rbx], r15
0x18000d90a  mov     rcx, [rbx+8]; void *
0x18000d90e  test    rcx, rcx
0x18000d911  jz      short loc_18000D91C
0x18000d913  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000d918  mov     [rbx+8], r15
0x18000d91c  mov     edx, 18h; struct std::nothrow_t *
0x18000d921  mov     rcx, rbx; void *
0x18000d924  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000d929  mov     [rbp+330h+var_3A8], r15
0x18000d92d  lea     rcx, [rbp+330h+var_2C0]; this
0x18000d931  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18000d936  lea     rcx, [rbp+330h+var_350]; this
0x18000d93a  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18000d93f  lea     rcx, [rbp+330h+pvarg]; this
0x18000d943  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18000d948  mov     ecx, [rsp+430h+var_3C0]
0x18000d94c  mov     edx, 80000000h
0x18000d951  lea     eax, [rcx+rdx]
0x18000d954  test    edx, eax
0x18000d956  jnz     short loc_18000D978
0x18000d958  cmp     ecx, 8007007Fh
0x18000d95e  jz      short loc_18000D978
0x18000d960  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18000d965  mov     edx, [rsp+430h+var_3C0]; int
0x18000d969  lea     r8, aScheduledevice_0; "ScheduleDeviceEnrollerOnPFW"
0x18000d970  mov     rcx, rax; this
0x18000d973  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x18000d978  lea     rcx, [rbp+330h+var_368]
0x18000d97c  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18000d981  lea     rcx, [rbp+330h+var_380]
0x18000d985  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18000d98a  lea     rcx, [rbp+330h+var_398]
0x18000d98e  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18000d993  lea     rcx, [rbp+330h+var_390]
0x18000d997  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18000d99c  lea     rcx, [rbp+330h+var_3B0]
0x18000d9a0  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18000d9a5  lea     rcx, [rbp+330h+var_378]
0x18000d9a9  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18000d9ae  lea     rcx, [rsp+430h+var_3B8]
0x18000d9b3  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18000d9b8  lea     rcx, [rbp+330h+var_388]
0x18000d9bc  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18000d9c1  lea     rcx, [rbp+330h+var_370]
0x18000d9c5  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18000d9ca  mov     ebx, [rsp+430h+var_3C0]
0x18000d9ce  cmp     [rsp+430h+var_3C0+4], r15d
0x18000d9d3  jz      short loc_18000D9E1
0x18000d9d5  call    cs:__imp_CoUninitialize
0x18000d9dc  nop     dword ptr [rax+rax+00h]
0x18000d9e1  lea     rcx, [rbp+330h+var_360]; this
0x18000d9e5  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18000d9ea  mov     eax, ebx
0x18000d9ec  mov     rcx, [rbp+330h+var_90]
0x18000d9f3  xor     rcx, rsp; StackCookie
0x18000d9f6  call    __security_check_cookie
0x18000d9fb  lea     r11, [rsp+430h+var_20]
0x18000da03  mov     rbx, [r11+40h]
0x18000da07  movaps  xmm6, xmmword ptr [r11-10h]
0x18000da0c  movaps  xmm7, xmmword ptr [r11-20h]
0x18000da11  movaps  xmm8, xmmword ptr [r11-30h]
0x18000da16  movaps  xmm9, xmmword ptr [r11-40h]
0x18000da1b  movaps  xmm10, xmmword ptr [r11-50h]
0x18000da20  movaps  xmm11, xmmword ptr [r11-60h]
0x18000da25  mov     rsp, r11
0x18000da28  pop     r15
0x18000da2a  pop     r14
0x18000da2c  pop     rdi
0x18000da2d  pop     rsi
0x18000da2e  pop     rbp
0x18000da2f  retn
```
