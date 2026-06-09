# ScheduleOneOmaDmSessionClient

- ea: `0x14000e6e8`
- end: `0x14000ea9f`
- name: `ScheduleOneOmaDmSessionClient`
- size: `951`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int, unsigned int, __int64, unsigned __int16 *, __int64, int Data, int, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x14000e530`

## callees

- `0x140002954`
- `0x1400046a4`
- `0x140004c34`
- `0x140008dc8`
- `0x140008e48`
- `0x1400090fc`
- `0x1400096dc`
- `0x14000a0b8`
- `0x14000e6e8`
- `0x1400177b0`
- `0x140017ba0`
- `0x140019010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000e966`
- `OLEAUT32!__imp_SysFreeString` at `0x14000e966`
- `OLEAUT32!__imp_VariantInit` at `0x14000e87f`
- `OLEAUT32!__imp_VariantInit` at `0x14000e892`
- `OLEAUT32!__imp_VariantInit` at `0x14000e87f`
- `OLEAUT32!__imp_VariantInit` at `0x14000e892`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14000e9e4`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14000e9e4`

## string_xrefs

- `0x14000e9cc`: `24RegisterTaskDefinition`
- `0x14000e79a`: `%windir%\system32\deviceenroller.exe `

## pseudocode

```c
__int64 __fastcall ScheduleOneOmaDmSessionClient(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        __int64 a6,
        unsigned __int16 *a7,
        __int64 a8,
        int Data,
        int a10,
        int a11)
{
  unsigned int v14; // ebx
  __int64 v15; // rbx
  __int64 (__fastcall *v16)(__int64, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *); // rsi
  __int128 v17; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  __int128 v19; // xmm8
  IRecordInfo *v20; // xmm9_8
  _variant_t *v21; // rax
  __int64 v22; // rdi
  __int128 v23; // xmm10
  __int64 v24; // xmm11_8
  _bstr_t *v25; // rax
  __int64 v26; // rdx
  int v27; // eax
  BSTR *v28; // rbx
  BSTR v29; // rcx
  CEnrollmentLogger *Logger; // rax
  int v32[2]; // [rsp+78h] [rbp-90h] BYREF
  void *Block; // [rsp+80h] [rbp-88h] BYREF
  __int64 v34; // [rsp+88h] [rbp-80h] BYREF
  int v35[2]; // [rsp+90h] [rbp-78h] BYREF
  int v36[2]; // [rsp+98h] [rbp-70h] BYREF
  __int64 v37; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v38; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v39; // [rsp+B0h] [rbp-58h] BYREF
  _QWORD v40[2]; // [rsp+B8h] [rbp-50h] BYREF
  VARIANTARG v41; // [rsp+C8h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+E0h] [rbp-28h] BYREF
  __int128 v43; // [rsp+F8h] [rbp-10h] BYREF
  IRecordInfo *v44; // [rsp+108h] [rbp+0h]
  __int128 v45; // [rsp+118h] [rbp+10h] BYREF
  IRecordInfo *v46; // [rsp+128h] [rbp+20h]
  __int128 v47; // [rsp+138h] [rbp+30h] BYREF
  __int64 v48; // [rsp+148h] [rbp+40h]
  VARIANTARG v49; // [rsp+158h] [rbp+50h] BYREF

  Data = 0;
  v40[1] = &Data;
  v40[0] = "ScheduleOneOmaDmSessionClient";
  *(_QWORD *)v36 = 0;
  *(_QWORD *)v32 = 0;
  a6 = 0;
  *(_QWORD *)v35 = 0;
  a8 = 0;
  v39 = 0;
  v38 = 0;
  v37 = 0;
  v34 = 0;
  Data = CreateTask(
           v36,
           (__int64)v32,
           &a6,
           v35,
           a2,
           L"%windir%\\system32\\deviceenroller.exe ",
           a7,
           L"S-1-5-18",
           0,
           a11,
           1,
           1,
           0);
  v14 = Data;
  if ( Data >= 0 )
  {
    Data = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a6 + 72LL))(a6, &a8);
    v14 = Data;
    if ( Data >= 0 )
    {
      Data = AddTimeTaskTriggers(&a8, a3, a4, a5);
      v14 = Data;
      if ( Data >= 0 )
      {
        Data = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a6 + 80LL))(a6, a8);
        v14 = Data;
        if ( Data >= 0 )
        {
          v15 = *(_QWORD *)v32;
          v16 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))(**(_QWORD **)v32 + 136LL);
          VariantInit(&pvarg);
          v17 = *(_OWORD *)&pvarg.vt;
          pRecInfo = pvarg.pRecInfo;
          VariantInit(&v41);
          v19 = *(_OWORD *)&v41.vt;
          v20 = v41.pRecInfo;
          v21 = _variant_t::_variant_t((_variant_t *)&v49, L"S-1-5-18");
          v22 = a6;
          v23 = *(_OWORD *)v21;
          v24 = *((_QWORD *)v21 + 2);
          v25 = _bstr_t::_bstr_t((_bstr_t *)&Block, a1);
          if ( *(_QWORD *)v25 )
            v26 = **(_QWORD **)v25;
          else
            v26 = 0;
          v43 = v17;
          v44 = pRecInfo;
          v45 = v19;
          v46 = v20;
          v47 = v23;
          v48 = v24;
          v27 = v16(v15, v26, v22, 6, &v47, &v45, 3, &v43, &v34);
          v28 = (BSTR *)Block;
          Data = v27;
          if ( Block )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v28 )
            {
              if ( *v28 )
              {
                SysFreeString(*v28);
                *v28 = 0;
              }
              v29 = v28[1];
              if ( v29 )
              {
                operator delete(v29);
                v28[1] = 0;
              }
              operator delete(v28);
            }
            Block = 0;
          }
          ATL::CComVariant::~CComVariant(&v49);
          ATL::CComVariant::~CComVariant(&v41);
          ATL::CComVariant::~CComVariant(&pvarg);
          v14 = Data;
          if ( Data < 0 )
          {
            RegSetKeyValueW(HKEY_LOCAL_MACHINE, c_szEnrollmentDB, L"24RegisterTaskDefinition", 4u, &Data, 4u);
            Logger = CEnrollmentLogger::GetLogger();
            CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(Logger, Data, "ScheduleOneOmaDmSessionClient");
            v14 = Data;
          }
        }
      }
    }
  }
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v34);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v37);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v38);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v39);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&a8);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(v35);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&a6);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(v32);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(v36);
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v40);
  return v14;
}

```

## disassembly

```asm
0x14000e6e8  mov     rax, rsp
0x14000e6eb  push    rbp
0x14000e6ec  push    rbx
0x14000e6ed  push    rsi
0x14000e6ee  push    rdi
0x14000e6ef  push    r12
0x14000e6f1  push    r13
0x14000e6f3  push    r14
0x14000e6f5  push    r15
0x14000e6f7  lea     rbp, [rax-118h]
0x14000e6fe  sub     rsp, 1D8h
0x14000e705  xor     r15d, r15d
0x14000e708  movaps  xmmword ptr [rax-58h], xmm6
0x14000e70c  movaps  xmmword ptr [rax-68h], xmm7
0x14000e710  lea     r13, aS1518; "S-1-5-18"
0x14000e717  movaps  xmmword ptr [rax-78h], xmm8
0x14000e71c  lea     r12, aScheduleoneoma_0; "ScheduleOneOmaDmSessionClient"
0x14000e723  movaps  xmmword ptr [rax-88h], xmm9
0x14000e72b  mov     edi, r9d
0x14000e72e  mov     [rsp+210h+var_1B0], r15d; Data
0x14000e733  lea     r9, [rbp+110h+var_188]; int
0x14000e737  movaps  xmmword ptr [rax-98h], xmm10
0x14000e73f  mov     esi, r8d
0x14000e742  movaps  xmmword ptr [rax-0A8h], xmm11
0x14000e74a  lea     r8, [rbp+110h+arg_28]; int
0x14000e751  lea     rax, [rbp+110h+Data]
0x14000e758  mov     [rbp+110h+Data], r15d
0x14000e75f  mov     [rbp+110h+var_158], rax
0x14000e763  mov     r14, rcx
0x14000e766  lea     eax, [r15+1]
0x14000e76a  mov     [rbp+110h+var_160], r12
0x14000e76e  mov     [rsp+210h+var_1B8], eax; int
0x14000e772  lea     rcx, [rbp+110h+var_180]; int
0x14000e776  mov     [rsp+210h+var_1C0], eax; int
0x14000e77a  mov     eax, [rbp+110h+arg_50]
0x14000e780  mov     [rsp+210h+var_1C8], eax; int
0x14000e784  mov     rax, [rbp+110h+arg_30]
0x14000e78b  mov     [rsp+210h+var_1D0], r15d; int
0x14000e790  mov     [rsp+210h+var_1D8], r13; unsigned __int16 *
0x14000e795  mov     [rsp+210h+var_1E0], rax; unsigned __int16 *
0x14000e79a  lea     rax, aWindirSystem32_1; "%windir%\\system32\\deviceenroller.exe "
0x14000e7a1  mov     qword ptr [rsp+210h+cbData], rax; unsigned __int16 *
0x14000e7a6  mov     [rsp+210h+lpData], rdx; unsigned __int16 *
0x14000e7ab  lea     rdx, [rsp+210h+var_1A0]; int
0x14000e7b0  mov     qword ptr [rbp+110h+var_180], r15
0x14000e7b4  mov     qword ptr [rsp+210h+var_1A0], r15
0x14000e7b9  mov     [rbp+110h+arg_28], r15
0x14000e7c0  mov     qword ptr [rbp+110h+var_188], r15
0x14000e7c4  mov     [rbp+110h+arg_38], r15
0x14000e7cb  mov     [rbp+110h+var_168], r15
0x14000e7cf  mov     [rbp+110h+var_170], r15
0x14000e7d3  mov     [rbp+110h+var_178], r15
0x14000e7d7  mov     [rbp+110h+var_190], r15
0x14000e7db  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x14000e7e0  mov     [rbp+110h+Data], eax
0x14000e7e6  mov     ebx, eax
0x14000e7e8  test    eax, eax
0x14000e7ea  js      loc_14000EA06
0x14000e7f0  mov     rcx, [rbp+110h+arg_28]
0x14000e7f7  lea     rdx, [rbp+110h+arg_38]
0x14000e7fe  mov     rax, [rcx]
0x14000e801  mov     rax, [rax+48h]
0x14000e805  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e80a  mov     [rbp+110h+Data], eax
0x14000e810  mov     ebx, eax
0x14000e812  test    eax, eax
0x14000e814  js      loc_14000EA06
0x14000e81a  mov     r9d, [rbp+110h+arg_20]
0x14000e821  lea     rcx, [rbp+110h+arg_38]
0x14000e828  mov     r8d, edi
0x14000e82b  mov     edx, esi
0x14000e82d  call    ?AddTimeTaskTriggers@@YAJAEAV?$CComPtr@UITriggerCollection@@@ATL@@KKK@Z; AddTimeTaskTriggers(ATL::CComPtr<ITriggerCollection> &,ulong,ulong,ulong)
0x14000e832  mov     [rbp+110h+Data], eax
0x14000e838  mov     ebx, eax
0x14000e83a  test    eax, eax
0x14000e83c  js      loc_14000EA06
0x14000e842  mov     rcx, [rbp+110h+arg_28]
0x14000e849  mov     rdx, [rbp+110h+arg_38]
0x14000e850  mov     rax, [rcx]
0x14000e853  mov     rax, [rax+50h]
0x14000e857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e85c  mov     [rbp+110h+Data], eax
0x14000e862  mov     ebx, eax
0x14000e864  test    eax, eax
0x14000e866  js      loc_14000EA06
0x14000e86c  mov     rbx, qword ptr [rsp+210h+var_1A0]
0x14000e871  lea     rcx, [rbp+110h+pvarg]; pvarg
0x14000e875  mov     rax, [rbx]
0x14000e878  mov     rsi, [rax+88h]
0x14000e87f  call    cs:__imp_VariantInit
0x14000e885  movups  xmm6, xmmword ptr [rbp+110h+pvarg]
0x14000e889  lea     rcx, [rbp+110h+var_150]; pvarg
0x14000e88d  movsd   xmm7, qword ptr [rbp+110h+pvarg+10h]
0x14000e892  call    cs:__imp_VariantInit
0x14000e898  movups  xmm8, xmmword ptr [rbp+110h+var_150]
0x14000e89d  lea     rcx, [rbp+110h+var_C0]; this
0x14000e8a1  mov     rdx, r13; unsigned __int16 *
0x14000e8a4  movsd   xmm9, qword ptr [rbp+110h+var_150+10h]
0x14000e8aa  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x14000e8af  mov     rdi, [rbp+110h+arg_28]
0x14000e8b6  lea     rcx, [rsp+210h+Block]; this
0x14000e8bb  mov     rdx, r14; unsigned __int16 *
0x14000e8be  movups  xmm10, xmmword ptr [rax]
0x14000e8c2  movsd   xmm11, qword ptr [rax+10h]
0x14000e8c8  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14000e8cd  mov     rdx, [rax]
0x14000e8d0  test    rdx, rdx
0x14000e8d3  jz      short loc_14000E8DA
0x14000e8d5  mov     rdx, [rdx]
0x14000e8d8  jmp     short loc_14000E8DD
0x14000e8da  mov     rdx, r15
0x14000e8dd  lea     rax, [rbp+110h+var_190]
0x14000e8e1  movaps  [rbp+110h+var_120], xmm6
0x14000e8e5  mov     qword ptr [rsp+210h+var_1D0], rax
0x14000e8ea  mov     r9d, 6
0x14000e8f0  lea     rax, [rbp+110h+var_120]
0x14000e8f4  movsd   [rbp+110h+var_110], xmm7
0x14000e8f9  mov     [rsp+210h+var_1D8], rax
0x14000e8fe  mov     r8, rdi
0x14000e901  lea     rax, [rbp+110h+var_100]
0x14000e905  mov     dword ptr [rsp+210h+var_1E0], 3
0x14000e90d  mov     qword ptr [rsp+210h+cbData], rax
0x14000e912  mov     rcx, rbx
0x14000e915  lea     rax, [rbp+110h+var_E0]
0x14000e919  movaps  [rbp+110h+var_100], xmm8
0x14000e91e  mov     [rsp+210h+lpData], rax
0x14000e923  mov     rax, rsi
0x14000e926  movsd   [rbp+110h+var_F0], xmm9
0x14000e92c  movaps  [rbp+110h+var_E0], xmm10
0x14000e931  movsd   [rbp+110h+var_D0], xmm11
0x14000e937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e93c  mov     rbx, [rsp+210h+Block]
0x14000e941  mov     [rbp+110h+Data], eax
0x14000e947  test    rbx, rbx
0x14000e94a  jz      short loc_14000E993
0x14000e94c  or      eax, 0FFFFFFFFh
0x14000e94f  lock xadd [rbx+10h], eax
0x14000e954  cmp     eax, 1
0x14000e957  jnz     short loc_14000E98E
0x14000e959  test    rbx, rbx
0x14000e95c  jz      short loc_14000E98E
0x14000e95e  mov     rcx, [rbx]; bstrString
0x14000e961  test    rcx, rcx
0x14000e964  jz      short loc_14000E96F
0x14000e966  call    cs:__imp_SysFreeString
0x14000e96c  mov     [rbx], r15
0x14000e96f  mov     rcx, [rbx+8]; Block
0x14000e973  test    rcx, rcx
0x14000e976  jz      short loc_14000E981
0x14000e978  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000e97d  mov     [rbx+8], r15
0x14000e981  mov     edx, 18h
0x14000e986  mov     rcx, rbx; Block
0x14000e989  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000e98e  mov     [rsp+210h+Block], r15
0x14000e993  lea     rcx, [rbp+110h+var_C0]; pvarg
0x14000e997  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000e99c  lea     rcx, [rbp+110h+var_150]; pvarg
0x14000e9a0  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000e9a5  lea     rcx, [rbp+110h+pvarg]; pvarg
0x14000e9a9  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000e9ae  mov     ebx, [rbp+110h+Data]
0x14000e9b4  test    ebx, ebx
0x14000e9b6  jns     short loc_14000EA06
0x14000e9b8  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x14000e9bf  lea     rax, [rbp+110h+Data]
0x14000e9c6  mov     r9d, 4; dwType
0x14000e9cc  lea     r8, a24registertask; "24RegisterTaskDefinition"
0x14000e9d3  mov     [rsp+210h+cbData], r9d; cbData
0x14000e9d8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000e9df  mov     [rsp+210h+lpData], rax; lpData
0x14000e9e4  call    cs:__imp_RegSetKeyValueW
0x14000e9ea  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x14000e9ef  mov     edx, [rbp+110h+Data]; int
0x14000e9f5  mov     r8, r12; char *
0x14000e9f8  mov     rcx, rax; this
0x14000e9fb  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x14000ea00  mov     ebx, [rbp+110h+Data]
0x14000ea06  lea     rcx, [rbp+110h+var_190]
0x14000ea0a  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000ea0f  lea     rcx, [rbp+110h+var_178]
0x14000ea13  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000ea18  lea     rcx, [rbp+110h+var_170]
0x14000ea1c  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000ea21  lea     rcx, [rbp+110h+var_168]
0x14000ea25  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000ea2a  lea     rcx, [rbp+110h+arg_38]
0x14000ea31  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000ea36  lea     rcx, [rbp+110h+var_188]
0x14000ea3a  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000ea3f  lea     rcx, [rbp+110h+arg_28]
0x14000ea46  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000ea4b  lea     rcx, [rsp+210h+var_1A0]
0x14000ea50  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000ea55  lea     rcx, [rbp+110h+var_180]
0x14000ea59  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000ea5e  lea     rcx, [rbp+110h+var_160]; this
0x14000ea62  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x14000ea67  lea     r11, [rsp+210h+var_38]
0x14000ea6f  mov     eax, ebx
0x14000ea71  movaps  xmm6, xmmword ptr [r11-18h]
0x14000ea76  movaps  xmm7, xmmword ptr [r11-28h]
0x14000ea7b  movaps  xmm8, xmmword ptr [r11-38h]
0x14000ea80  movaps  xmm9, xmmword ptr [r11-48h]
0x14000ea85  movaps  xmm10, xmmword ptr [r11-58h]
0x14000ea8a  movaps  xmm11, xmmword ptr [r11-68h]
0x14000ea8f  mov     rsp, r11
0x14000ea92  pop     r15
0x14000ea94  pop     r14
0x14000ea96  pop     r13
0x14000ea98  pop     r12
0x14000ea9a  pop     rdi
0x14000ea9b  pop     rsi
0x14000ea9c  pop     rbx
0x14000ea9d  pop     rbp
0x14000ea9e  retn
```
