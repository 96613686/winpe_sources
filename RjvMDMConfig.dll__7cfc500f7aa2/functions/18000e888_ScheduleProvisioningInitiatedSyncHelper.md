# ScheduleProvisioningInitiatedSyncHelper

- ea: `0x18000e888`
- end: `0x18000eb87`
- name: `ScheduleProvisioningInitiatedSyncHelper`
- size: `767`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000da38`

## callees

- `0x180001c60`
- `0x180001cc8`
- `0x1800051d8`
- `0x180007258`
- `0x1800072d0`
- `0x180007364`
- `0x1800077a0`
- `0x1800079e8`
- `0x180008bd4`
- `0x18000e888`
- `0x18001b9d8`
- `0x18001bde0`
- `0x18001e010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000ea97`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ea97`
- `OLEAUT32!__imp_VariantInit` at `0x18000e9a6`
- `OLEAUT32!__imp_VariantInit` at `0x18000e9bf`
- `OLEAUT32!__imp_VariantInit` at `0x18000e9a6`
- `OLEAUT32!__imp_VariantInit` at `0x18000e9bf`

## string_xrefs

- `0x18000e970`: `%windir%\system32\deviceenroller.exe `

## pseudocode

```c
__int64 __fastcall ScheduleProvisioningInitiatedSyncHelper(unsigned __int16 *a1)
{
  int v2; // ebx
  struct IUnknown *v3; // rbx
  ULONG (__stdcall *Release)(IUnknown *); // rsi
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
  const struct std::nothrow_t *v16; // rdx
  BSTR *v17; // rbx
  BSTR v18; // rcx
  CEnrollmentLogger *Logger; // rax
  __int64 v21; // [rsp+48h] [rbp-C0h]
  int v22; // [rsp+68h] [rbp-A0h]
  int v23[2]; // [rsp+78h] [rbp-90h] BYREF
  __int64 v24; // [rsp+80h] [rbp-88h] BYREF
  struct IUnknown *v25; // [rsp+88h] [rbp-80h] BYREF
  void *v26; // [rsp+90h] [rbp-78h] BYREF
  __int64 v27; // [rsp+98h] [rbp-70h] BYREF
  __int64 v28; // [rsp+A0h] [rbp-68h] BYREF
  LPVOID v29[2]; // [rsp+A8h] [rbp-60h] BYREF
  _QWORD v30[2]; // [rsp+B8h] [rbp-50h] BYREF
  VARIANTARG v31; // [rsp+C8h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+E0h] [rbp-28h] BYREF
  __int128 v33; // [rsp+F8h] [rbp-10h] BYREF
  IRecordInfo *v34; // [rsp+108h] [rbp+0h]
  __int128 v35; // [rsp+118h] [rbp+10h] BYREF
  IRecordInfo *v36; // [rsp+128h] [rbp+20h]
  __int128 v37; // [rsp+138h] [rbp+30h] BYREF
  __int64 v38; // [rsp+148h] [rbp+40h]
  _BYTE v39[32]; // [rsp+158h] [rbp+50h] BYREF
  unsigned __int16 v40[264]; // [rsp+178h] [rbp+70h] BYREF

  v29[0] = 0;
  v25 = 0;
  v24 = 0;
  v28 = 0;
  v27 = 0;
  v2 = StringCchPrintfW(v40, 0x104u, L"/c /ProvInitiatedSession /o \"%s\"", a1);
  v23[0] = v2;
  v30[1] = v23;
  v30[0] = "ScheduleProvisioningInitiatedSyncHelper";
  if ( v2 >= 0 )
  {
    v22 = 0;
    LODWORD(v21) = 0;
    v23[0] = CreateTask(
               v29,
               &v25,
               &v24,
               &v28,
               a1,
               L"%windir%\\system32\\deviceenroller.exe ",
               v40,
               L"S-1-5-18",
               v21,
               1,
               0,
               0,
               v22);
    v2 = v23[0];
    if ( v23[0] >= 0 )
    {
      v3 = v25;
      Release = v25->lpVtbl[5].Release;
      VariantInit(&pvarg);
      v5 = *(_OWORD *)&pvarg.vt;
      pRecInfo = pvarg.pRecInfo;
      VariantInit(&v31);
      v7 = *(_OWORD *)&v31.vt;
      v8 = v31.pRecInfo;
      v9 = _variant_t::_variant_t((_variant_t *)v39, L"S-1-5-18");
      v10 = v24;
      v11 = *(_OWORD *)v9;
      v12 = *((_QWORD *)v9 + 2);
      v13 = _bstr_t::_bstr_t((_bstr_t *)&v26, L"Provisioning initiated session");
      if ( *(_QWORD *)v13 )
        v14 = **(_QWORD **)v13;
      else
        v14 = 0;
      v33 = v5;
      v34 = pRecInfo;
      v35 = v7;
      v36 = v8;
      v37 = v11;
      v38 = v12;
      v15 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))Release)(
              v3,
              v14,
              v10,
              6,
              &v37,
              &v35,
              3,
              &v33,
              &v27);
      v17 = (BSTR *)v26;
      v23[0] = v15;
      if ( v26 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v26 + 4, 0xFFFFFFFF) == 1 && v17 )
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
        v26 = 0;
      }
      _variant_t::~_variant_t((_variant_t *)v39);
      _variant_t::~_variant_t((_variant_t *)&v31);
      _variant_t::~_variant_t((_variant_t *)&pvarg);
      v2 = v23[0];
      if ( v23[0] < 0 )
      {
        Logger = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(Logger, v23[0], "ScheduleProvisioningInitiatedSyncHelper");
        v2 = v23[0];
      }
    }
  }
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v30);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v27);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v28);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v24);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v25);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(v29);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000e888  mov     rax, rsp
0x18000e88b  mov     [rax+10h], rbx
0x18000e88f  mov     [rax+18h], rsi
0x18000e893  push    rbp
0x18000e894  push    rdi
0x18000e895  push    r12
0x18000e897  push    r14
0x18000e899  push    r15
0x18000e89b  lea     rbp, [rax-318h]
0x18000e8a2  sub     rsp, 3F0h
0x18000e8a9  movaps  xmmword ptr [rax-38h], xmm6
0x18000e8ad  movaps  xmmword ptr [rax-48h], xmm7
0x18000e8b1  movaps  xmmword ptr [rax-58h], xmm8
0x18000e8b6  movaps  xmmword ptr [rax-68h], xmm9
0x18000e8bb  movaps  xmmword ptr [rax-78h], xmm10
0x18000e8c0  movaps  xmmword ptr [rax-88h], xmm11
0x18000e8c8  mov     rax, cs:__security_cookie
0x18000e8cf  xor     rax, rsp
0x18000e8d2  mov     [rbp+310h+var_90], rax
0x18000e8d9  xor     r14d, r14d
0x18000e8dc  lea     r8, aCProvinitiated; "/c /ProvInitiatedSession /o \"%s\""
0x18000e8e3  mov     rdi, rcx
0x18000e8e6  mov     [rbp+310h+var_370], r14
0x18000e8ea  mov     r9, rcx
0x18000e8ed  mov     [rbp+310h+var_390], r14
0x18000e8f1  lea     rcx, [rbp+310h+var_2A0]; unsigned __int16 *
0x18000e8f5  mov     [rsp+410h+var_398], r14
0x18000e8fa  mov     edx, 104h; unsigned __int64
0x18000e8ff  mov     [rbp+310h+var_378], r14
0x18000e903  mov     [rbp+310h+var_380], r14
0x18000e907  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000e90c  mov     ebx, eax
0x18000e90e  mov     [rsp+410h+var_3A0], eax
0x18000e912  lea     rax, [rsp+410h+var_3A0]
0x18000e917  mov     [rbp+310h+var_358], rax
0x18000e91b  lea     r15, aScheduleprovis; "ScheduleProvisioningInitiatedSyncHelper"
0x18000e922  mov     [rbp+310h+var_360], r15
0x18000e926  test    ebx, ebx
0x18000e928  js      loc_18000EB04
0x18000e92e  mov     [rsp+410h+var_3B0], r14d
0x18000e933  lea     rax, [rbp+310h+var_2A0]
0x18000e937  mov     [rsp+410h+var_3B8], r14d
0x18000e93c  lea     r12, aS1518; "S-1-5-18"
0x18000e943  mov     [rsp+410h+var_3C0], r14d
0x18000e948  lea     r9, [rbp+310h+var_378]
0x18000e94c  mov     [rsp+410h+var_3C8], 1
0x18000e954  lea     r8, [rsp+410h+var_398]
0x18000e959  mov     dword ptr [rsp+410h+var_3D0], r14d
0x18000e95e  lea     rdx, [rbp+310h+var_390]
0x18000e962  mov     [rsp+410h+var_3D8], r12
0x18000e967  lea     rcx, [rbp+310h+var_370]
0x18000e96b  mov     [rsp+410h+var_3E0], rax
0x18000e970  lea     rax, aWindirSystem32_1; "%windir%\\system32\\deviceenroller.exe "
0x18000e977  mov     [rsp+410h+var_3E8], rax
0x18000e97c  mov     [rsp+410h+var_3F0], rdi
0x18000e981  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x18000e986  mov     [rsp+410h+var_3A0], eax
0x18000e98a  mov     ebx, eax
0x18000e98c  test    eax, eax
0x18000e98e  js      loc_18000EB04
0x18000e994  mov     rbx, [rbp+310h+var_390]
0x18000e998  lea     rcx, [rbp+310h+pvarg]; pvarg
0x18000e99c  mov     rax, [rbx]
0x18000e99f  mov     rsi, [rax+88h]
0x18000e9a6  call    cs:__imp_VariantInit
0x18000e9ad  nop     dword ptr [rax+rax+00h]
0x18000e9b2  movups  xmm6, xmmword ptr [rbp+310h+pvarg]
0x18000e9b6  lea     rcx, [rbp+310h+var_350]; pvarg
0x18000e9ba  movsd   xmm7, qword ptr [rbp+310h+pvarg+10h]
0x18000e9bf  call    cs:__imp_VariantInit
0x18000e9c6  nop     dword ptr [rax+rax+00h]
0x18000e9cb  movups  xmm8, xmmword ptr [rbp+310h+var_350]
0x18000e9d0  lea     rcx, [rbp+310h+var_2C0]; this
0x18000e9d4  mov     rdx, r12; unsigned __int16 *
0x18000e9d7  movsd   xmm9, qword ptr [rbp+310h+var_350+10h]
0x18000e9dd  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x18000e9e2  mov     rdi, [rsp+410h+var_398]
0x18000e9e7  lea     rdx, aProvisioningIn; "Provisioning initiated session"
0x18000e9ee  lea     rcx, [rbp+310h+var_388]; this
0x18000e9f2  movups  xmm10, xmmword ptr [rax]
0x18000e9f6  movsd   xmm11, qword ptr [rax+10h]
0x18000e9fc  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000ea01  mov     rdx, [rax]
0x18000ea04  test    rdx, rdx
0x18000ea07  jz      short loc_18000EA0E
0x18000ea09  mov     rdx, [rdx]
0x18000ea0c  jmp     short loc_18000EA11
0x18000ea0e  mov     rdx, r14
0x18000ea11  lea     rax, [rbp+310h+var_380]
0x18000ea15  movaps  [rbp+310h+var_320], xmm6
0x18000ea19  mov     [rsp+410h+var_3D0], rax
0x18000ea1e  mov     r9d, 6
0x18000ea24  lea     rax, [rbp+310h+var_320]
0x18000ea28  movsd   [rbp+310h+var_310], xmm7
0x18000ea2d  mov     [rsp+410h+var_3D8], rax
0x18000ea32  mov     r8, rdi
0x18000ea35  lea     rax, [rbp+310h+var_300]
0x18000ea39  mov     dword ptr [rsp+410h+var_3E0], 3
0x18000ea41  mov     [rsp+410h+var_3E8], rax
0x18000ea46  mov     rcx, rbx
0x18000ea49  lea     rax, [rbp+310h+var_2E0]
0x18000ea4d  movaps  [rbp+310h+var_300], xmm8
0x18000ea52  mov     [rsp+410h+var_3F0], rax
0x18000ea57  mov     rax, rsi
0x18000ea5a  movsd   [rbp+310h+var_2F0], xmm9
0x18000ea60  movaps  [rbp+310h+var_2E0], xmm10
0x18000ea65  movsd   [rbp+310h+var_2D0], xmm11
0x18000ea6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea70  mov     rbx, [rbp+310h+var_388]
0x18000ea74  mov     [rsp+410h+var_3A0], eax
0x18000ea78  test    rbx, rbx
0x18000ea7b  jz      short loc_18000EAC9
0x18000ea7d  or      eax, 0FFFFFFFFh
0x18000ea80  lock xadd [rbx+10h], eax
0x18000ea85  cmp     eax, 1
0x18000ea88  jnz     short loc_18000EAC5
0x18000ea8a  test    rbx, rbx
0x18000ea8d  jz      short loc_18000EAC5
0x18000ea8f  mov     rcx, [rbx]; bstrString
0x18000ea92  test    rcx, rcx
0x18000ea95  jz      short loc_18000EAA6
0x18000ea97  call    cs:__imp_SysFreeString
0x18000ea9e  nop     dword ptr [rax+rax+00h]
0x18000eaa3  mov     [rbx], r14
0x18000eaa6  mov     rcx, [rbx+8]; void *
0x18000eaaa  test    rcx, rcx
0x18000eaad  jz      short loc_18000EAB8
0x18000eaaf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000eab4  mov     [rbx+8], r14
0x18000eab8  mov     edx, 18h; struct std::nothrow_t *
0x18000eabd  mov     rcx, rbx; void *
0x18000eac0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000eac5  mov     [rbp+310h+var_388], r14
0x18000eac9  lea     rcx, [rbp+310h+var_2C0]; this
0x18000eacd  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18000ead2  lea     rcx, [rbp+310h+var_350]; this
0x18000ead6  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18000eadb  lea     rcx, [rbp+310h+pvarg]; this
0x18000eadf  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18000eae4  mov     ebx, [rsp+410h+var_3A0]
0x18000eae8  test    ebx, ebx
0x18000eaea  jns     short loc_18000EB04
0x18000eaec  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18000eaf1  mov     edx, [rsp+410h+var_3A0]; int
0x18000eaf5  mov     r8, r15; char *
0x18000eaf8  mov     rcx, rax; this
0x18000eafb  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x18000eb00  mov     ebx, [rsp+410h+var_3A0]
0x18000eb04  lea     rcx, [rbp+310h+var_360]; this
0x18000eb08  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18000eb0d  lea     rcx, [rbp+310h+var_380]
0x18000eb11  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18000eb16  lea     rcx, [rbp+310h+var_378]
0x18000eb1a  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18000eb1f  lea     rcx, [rsp+410h+var_398]
0x18000eb24  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18000eb29  lea     rcx, [rbp+310h+var_390]
0x18000eb2d  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18000eb32  lea     rcx, [rbp+310h+var_370]
0x18000eb36  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18000eb3b  mov     eax, ebx
0x18000eb3d  mov     rcx, [rbp+310h+var_90]
0x18000eb44  xor     rcx, rsp; StackCookie
0x18000eb47  call    __security_check_cookie
0x18000eb4c  lea     r11, [rsp+410h+var_20]
0x18000eb54  mov     rbx, [r11+38h]
0x18000eb58  mov     rsi, [r11+40h]
0x18000eb5c  movaps  xmm6, xmmword ptr [r11-10h]
0x18000eb61  movaps  xmm7, xmmword ptr [r11-20h]
0x18000eb66  movaps  xmm8, xmmword ptr [r11-30h]
0x18000eb6b  movaps  xmm9, xmmword ptr [r11-40h]
0x18000eb70  movaps  xmm10, xmmword ptr [r11-50h]
0x18000eb75  movaps  xmm11, xmmword ptr [r11-60h]
0x18000eb7a  mov     rsp, r11
0x18000eb7d  pop     r15
0x18000eb7f  pop     r14
0x18000eb81  pop     r12
0x18000eb83  pop     rdi
0x18000eb84  pop     rbp
0x18000eb85  retn
```
