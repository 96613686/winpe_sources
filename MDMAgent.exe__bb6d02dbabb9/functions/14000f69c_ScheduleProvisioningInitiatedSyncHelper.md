# ScheduleProvisioningInitiatedSyncHelper

- ea: `0x14000f69c`
- end: `0x14000f99b`
- name: `ScheduleProvisioningInitiatedSyncHelper`
- size: `767`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x14000e84c`

## callees

- `0x1400029c0`
- `0x1400029e4`
- `0x14000476c`
- `0x140004cd0`
- `0x140007628`
- `0x1400091e0`
- `0x140009268`
- `0x1400094e4`
- `0x14000a51c`
- `0x14000f69c`
- `0x14001848c`
- `0x140018890`
- `0x14001a010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000f8ab`
- `OLEAUT32!__imp_SysFreeString` at `0x14000f8ab`
- `OLEAUT32!__imp_VariantInit` at `0x14000f7ba`
- `OLEAUT32!__imp_VariantInit` at `0x14000f7d3`
- `OLEAUT32!__imp_VariantInit` at `0x14000f7ba`
- `OLEAUT32!__imp_VariantInit` at `0x14000f7d3`

## string_xrefs

- `0x14000f784`: `%windir%\system32\deviceenroller.exe `

## pseudocode

```c
__int64 __fastcall ScheduleProvisioningInitiatedSyncHelper(unsigned __int16 *a1)
{
  int v2; // ebx
  __int64 v3; // rbx
  __int64 (__fastcall *v4)(__int64, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *); // rsi
  __int128 v5; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  __int128 v7; // xmm8
  IRecordInfo *v8; // xmm9_8
  _variant_t *v9; // rax
  __int64 v10; // rdi
  __int128 v11; // xmm10
  __int64 v12; // xmm11_8
  _bstr_t *v13; // rax
  __int64 v14; // rdx
  int v15; // eax
  BSTR *v16; // rbx
  BSTR v17; // rcx
  CEnrollmentLogger *Logger; // rax
  int v20[2]; // [rsp+78h] [rbp-90h] BYREF
  int v21[2]; // [rsp+80h] [rbp-88h] BYREF
  int v22[2]; // [rsp+88h] [rbp-80h] BYREF
  void *Block; // [rsp+90h] [rbp-78h] BYREF
  __int64 v24; // [rsp+98h] [rbp-70h] BYREF
  int v25[2]; // [rsp+A0h] [rbp-68h] BYREF
  int v26[2]; // [rsp+A8h] [rbp-60h] BYREF
  _QWORD v27[2]; // [rsp+B8h] [rbp-50h] BYREF
  VARIANTARG v28; // [rsp+C8h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+E0h] [rbp-28h] BYREF
  __int128 v30; // [rsp+F8h] [rbp-10h] BYREF
  IRecordInfo *v31; // [rsp+108h] [rbp+0h]
  __int128 v32; // [rsp+118h] [rbp+10h] BYREF
  IRecordInfo *v33; // [rsp+128h] [rbp+20h]
  __int128 v34; // [rsp+138h] [rbp+30h] BYREF
  __int64 v35; // [rsp+148h] [rbp+40h]
  VARIANTARG v36; // [rsp+158h] [rbp+50h] BYREF
  unsigned __int16 v37[264]; // [rsp+178h] [rbp+70h] BYREF

  *(_QWORD *)v26 = 0;
  *(_QWORD *)v22 = 0;
  *(_QWORD *)v21 = 0;
  *(_QWORD *)v25 = 0;
  v24 = 0;
  v2 = StringCchPrintfW(v37, 0x104u, L"/c /ProvInitiatedSession /o \"%s\"", a1);
  v20[0] = v2;
  v27[1] = v20;
  v27[0] = "ScheduleProvisioningInitiatedSyncHelper";
  if ( v2 >= 0 )
  {
    v20[0] = CreateTask(
               (LPVOID *)v26,
               (__int64)v22,
               v21,
               v25,
               a1,
               L"%windir%\\system32\\deviceenroller.exe ",
               v37,
               L"S-1-5-18",
               0,
               1,
               0,
               0,
               0);
    v2 = v20[0];
    if ( v20[0] >= 0 )
    {
      v3 = *(_QWORD *)v22;
      v4 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))(**(_QWORD **)v22 + 136LL);
      VariantInit(&pvarg);
      v5 = *(_OWORD *)&pvarg.vt;
      pRecInfo = pvarg.pRecInfo;
      VariantInit(&v28);
      v7 = *(_OWORD *)&v28.vt;
      v8 = v28.pRecInfo;
      v9 = _variant_t::_variant_t((_variant_t *)&v36, L"S-1-5-18");
      v10 = *(_QWORD *)v21;
      v11 = *(_OWORD *)v9;
      v12 = *((_QWORD *)v9 + 2);
      v13 = _bstr_t::_bstr_t((_bstr_t *)&Block, L"Provisioning initiated session");
      if ( *(_QWORD *)v13 )
        v14 = **(_QWORD **)v13;
      else
        v14 = 0;
      v30 = v5;
      v31 = pRecInfo;
      v32 = v7;
      v33 = v8;
      v34 = v11;
      v35 = v12;
      v15 = v4(v3, v14, v10, 6, &v34, &v32, 3, &v30, &v24);
      v16 = (BSTR *)Block;
      v20[0] = v15;
      if ( Block )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v16 )
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
        Block = 0;
      }
      ATL::CComVariant::~CComVariant(&v36);
      ATL::CComVariant::~CComVariant(&v28);
      ATL::CComVariant::~CComVariant(&pvarg);
      v2 = v20[0];
      if ( v20[0] < 0 )
      {
        Logger = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(Logger, v20[0], "ScheduleProvisioningInitiatedSyncHelper");
        v2 = v20[0];
      }
    }
  }
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v27);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v24);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(v25);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(v21);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(v22);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(v26);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14000f69c  mov     rax, rsp
0x14000f69f  mov     [rax+10h], rbx
0x14000f6a3  mov     [rax+18h], rsi
0x14000f6a7  push    rbp
0x14000f6a8  push    rdi
0x14000f6a9  push    r12
0x14000f6ab  push    r14
0x14000f6ad  push    r15
0x14000f6af  lea     rbp, [rax-318h]
0x14000f6b6  sub     rsp, 3F0h
0x14000f6bd  movaps  xmmword ptr [rax-38h], xmm6
0x14000f6c1  movaps  xmmword ptr [rax-48h], xmm7
0x14000f6c5  movaps  xmmword ptr [rax-58h], xmm8
0x14000f6ca  movaps  xmmword ptr [rax-68h], xmm9
0x14000f6cf  movaps  xmmword ptr [rax-78h], xmm10
0x14000f6d4  movaps  xmmword ptr [rax-88h], xmm11
0x14000f6dc  mov     rax, cs:__security_cookie
0x14000f6e3  xor     rax, rsp
0x14000f6e6  mov     [rbp+310h+var_90], rax
0x14000f6ed  xor     r14d, r14d
0x14000f6f0  lea     r8, aCProvinitiated; "/c /ProvInitiatedSession /o \"%s\""
0x14000f6f7  mov     rdi, rcx
0x14000f6fa  mov     qword ptr [rbp+310h+var_370], r14
0x14000f6fe  mov     r9, rcx
0x14000f701  mov     qword ptr [rbp+310h+var_390], r14
0x14000f705  lea     rcx, [rbp+310h+var_2A0]; unsigned __int16 *
0x14000f709  mov     qword ptr [rsp+410h+var_398], r14
0x14000f70e  mov     edx, 104h; unsigned __int64
0x14000f713  mov     qword ptr [rbp+310h+var_378], r14
0x14000f717  mov     [rbp+310h+var_380], r14
0x14000f71b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000f720  mov     ebx, eax
0x14000f722  mov     [rsp+410h+var_3A0], eax
0x14000f726  lea     rax, [rsp+410h+var_3A0]
0x14000f72b  mov     [rbp+310h+var_358], rax
0x14000f72f  lea     r15, aScheduleprovis; "ScheduleProvisioningInitiatedSyncHelper"
0x14000f736  mov     [rbp+310h+var_360], r15
0x14000f73a  test    ebx, ebx
0x14000f73c  js      loc_14000F918
0x14000f742  mov     [rsp+410h+Data], r14d; Data
0x14000f747  lea     rax, [rbp+310h+var_2A0]
0x14000f74b  mov     [rsp+410h+var_3B8], r14d; int
0x14000f750  lea     r12, aS1518; "S-1-5-18"
0x14000f757  mov     [rsp+410h+var_3C0], r14d; int
0x14000f75c  lea     r9, [rbp+310h+var_378]; int
0x14000f760  mov     [rsp+410h+var_3C8], 1; int
0x14000f768  lea     r8, [rsp+410h+var_398]; int
0x14000f76d  mov     [rsp+410h+var_3D0], r14d; int
0x14000f772  lea     rdx, [rbp+310h+var_390]; int
0x14000f776  mov     [rsp+410h+var_3D8], r12; unsigned __int16 *
0x14000f77b  lea     rcx, [rbp+310h+var_370]; int
0x14000f77f  mov     [rsp+410h+var_3E0], rax; unsigned __int16 *
0x14000f784  lea     rax, aWindirSystem32_1; "%windir%\\system32\\deviceenroller.exe "
0x14000f78b  mov     [rsp+410h+var_3E8], rax; unsigned __int16 *
0x14000f790  mov     [rsp+410h+var_3F0], rdi; unsigned __int16 *
0x14000f795  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x14000f79a  mov     [rsp+410h+var_3A0], eax
0x14000f79e  mov     ebx, eax
0x14000f7a0  test    eax, eax
0x14000f7a2  js      loc_14000F918
0x14000f7a8  mov     rbx, qword ptr [rbp+310h+var_390]
0x14000f7ac  lea     rcx, [rbp+310h+pvarg]; pvarg
0x14000f7b0  mov     rax, [rbx]
0x14000f7b3  mov     rsi, [rax+88h]
0x14000f7ba  call    cs:__imp_VariantInit
0x14000f7c1  nop     dword ptr [rax+rax+00h]
0x14000f7c6  movups  xmm6, xmmword ptr [rbp+310h+pvarg]
0x14000f7ca  lea     rcx, [rbp+310h+var_350]; pvarg
0x14000f7ce  movsd   xmm7, qword ptr [rbp+310h+pvarg+10h]
0x14000f7d3  call    cs:__imp_VariantInit
0x14000f7da  nop     dword ptr [rax+rax+00h]
0x14000f7df  movups  xmm8, xmmword ptr [rbp+310h+var_350]
0x14000f7e4  lea     rcx, [rbp+310h+var_2C0]; this
0x14000f7e8  mov     rdx, r12; unsigned __int16 *
0x14000f7eb  movsd   xmm9, qword ptr [rbp+310h+var_350+10h]
0x14000f7f1  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x14000f7f6  mov     rdi, qword ptr [rsp+410h+var_398]
0x14000f7fb  lea     rdx, aProvisioningIn; "Provisioning initiated session"
0x14000f802  lea     rcx, [rbp+310h+Block]; this
0x14000f806  movups  xmm10, xmmword ptr [rax]
0x14000f80a  movsd   xmm11, qword ptr [rax+10h]
0x14000f810  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14000f815  mov     rdx, [rax]
0x14000f818  test    rdx, rdx
0x14000f81b  jz      short loc_14000F822
0x14000f81d  mov     rdx, [rdx]
0x14000f820  jmp     short loc_14000F825
0x14000f822  mov     rdx, r14
0x14000f825  lea     rax, [rbp+310h+var_380]
0x14000f829  movaps  [rbp+310h+var_320], xmm6
0x14000f82d  mov     qword ptr [rsp+410h+var_3D0], rax
0x14000f832  mov     r9d, 6
0x14000f838  lea     rax, [rbp+310h+var_320]
0x14000f83c  movsd   [rbp+310h+var_310], xmm7
0x14000f841  mov     [rsp+410h+var_3D8], rax
0x14000f846  mov     r8, rdi
0x14000f849  lea     rax, [rbp+310h+var_300]
0x14000f84d  mov     dword ptr [rsp+410h+var_3E0], 3
0x14000f855  mov     [rsp+410h+var_3E8], rax
0x14000f85a  mov     rcx, rbx
0x14000f85d  lea     rax, [rbp+310h+var_2E0]
0x14000f861  movaps  [rbp+310h+var_300], xmm8
0x14000f866  mov     [rsp+410h+var_3F0], rax
0x14000f86b  mov     rax, rsi
0x14000f86e  movsd   [rbp+310h+var_2F0], xmm9
0x14000f874  movaps  [rbp+310h+var_2E0], xmm10
0x14000f879  movsd   [rbp+310h+var_2D0], xmm11
0x14000f87f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f884  mov     rbx, [rbp+310h+Block]
0x14000f888  mov     [rsp+410h+var_3A0], eax
0x14000f88c  test    rbx, rbx
0x14000f88f  jz      short loc_14000F8DD
0x14000f891  or      eax, 0FFFFFFFFh
0x14000f894  lock xadd [rbx+10h], eax
0x14000f899  cmp     eax, 1
0x14000f89c  jnz     short loc_14000F8D9
0x14000f89e  test    rbx, rbx
0x14000f8a1  jz      short loc_14000F8D9
0x14000f8a3  mov     rcx, [rbx]; bstrString
0x14000f8a6  test    rcx, rcx
0x14000f8a9  jz      short loc_14000F8BA
0x14000f8ab  call    cs:__imp_SysFreeString
0x14000f8b2  nop     dword ptr [rax+rax+00h]
0x14000f8b7  mov     [rbx], r14
0x14000f8ba  mov     rcx, [rbx+8]; Block
0x14000f8be  test    rcx, rcx
0x14000f8c1  jz      short loc_14000F8CC
0x14000f8c3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000f8c8  mov     [rbx+8], r14
0x14000f8cc  mov     edx, 18h
0x14000f8d1  mov     rcx, rbx; Block
0x14000f8d4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000f8d9  mov     [rbp+310h+Block], r14
0x14000f8dd  lea     rcx, [rbp+310h+var_2C0]; pvarg
0x14000f8e1  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000f8e6  lea     rcx, [rbp+310h+var_350]; pvarg
0x14000f8ea  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000f8ef  lea     rcx, [rbp+310h+pvarg]; pvarg
0x14000f8f3  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000f8f8  mov     ebx, [rsp+410h+var_3A0]
0x14000f8fc  test    ebx, ebx
0x14000f8fe  jns     short loc_14000F918
0x14000f900  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x14000f905  mov     edx, [rsp+410h+var_3A0]; int
0x14000f909  mov     r8, r15; char *
0x14000f90c  mov     rcx, rax; this
0x14000f90f  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x14000f914  mov     ebx, [rsp+410h+var_3A0]
0x14000f918  lea     rcx, [rbp+310h+var_360]; this
0x14000f91c  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x14000f921  lea     rcx, [rbp+310h+var_380]
0x14000f925  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000f92a  lea     rcx, [rbp+310h+var_378]
0x14000f92e  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000f933  lea     rcx, [rsp+410h+var_398]
0x14000f938  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000f93d  lea     rcx, [rbp+310h+var_390]
0x14000f941  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000f946  lea     rcx, [rbp+310h+var_370]
0x14000f94a  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000f94f  mov     eax, ebx
0x14000f951  mov     rcx, [rbp+310h+var_90]
0x14000f958  xor     rcx, rsp; StackCookie
0x14000f95b  call    __security_check_cookie
0x14000f960  lea     r11, [rsp+410h+var_20]
0x14000f968  mov     rbx, [r11+38h]
0x14000f96c  mov     rsi, [r11+40h]
0x14000f970  movaps  xmm6, xmmword ptr [r11-10h]
0x14000f975  movaps  xmm7, xmmword ptr [r11-20h]
0x14000f97a  movaps  xmm8, xmmword ptr [r11-30h]
0x14000f97f  movaps  xmm9, xmmword ptr [r11-40h]
0x14000f984  movaps  xmm10, xmmword ptr [r11-50h]
0x14000f989  movaps  xmm11, xmmword ptr [r11-60h]
0x14000f98e  mov     rsp, r11
0x14000f991  pop     r15
0x14000f993  pop     r14
0x14000f995  pop     r12
0x14000f997  pop     rdi
0x14000f998  pop     rbp
0x14000f999  retn
```
