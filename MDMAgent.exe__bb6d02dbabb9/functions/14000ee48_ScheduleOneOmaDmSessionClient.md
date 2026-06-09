# ScheduleOneOmaDmSessionClient

- ea: `0x14000ee48`
- end: `0x14000f218`
- name: `ScheduleOneOmaDmSessionClient`
- size: `976`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, unsigned __int16 *@<rdx>, int, int, unsigned __int16 *, __int64, int Data, int, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x14000ec7c`

## callees

- `0x1400029e4`
- `0x14000476c`
- `0x140004cd0`
- `0x1400091e0`
- `0x140009268`
- `0x1400094e4`
- `0x140009ae8`
- `0x14000a51c`
- `0x14000ee48`
- `0x14001848c`
- `0x140018890`
- `0x14001a010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000f0d2`
- `OLEAUT32!__imp_SysFreeString` at `0x14000f0d2`
- `OLEAUT32!__imp_VariantInit` at `0x14000efdf`
- `OLEAUT32!__imp_VariantInit` at `0x14000eff8`
- `OLEAUT32!__imp_VariantInit` at `0x14000efdf`
- `OLEAUT32!__imp_VariantInit` at `0x14000eff8`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14000f156`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14000f156`

## string_xrefs

- `0x14000f13e`: `24RegisterTaskDefinition`
- `0x14000eefa`: `%windir%\system32\deviceenroller.exe `

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
           (LPVOID *)v36,
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
0x14000ee48  mov     rax, rsp
0x14000ee4b  push    rbp
0x14000ee4c  push    rbx
0x14000ee4d  push    rsi
0x14000ee4e  push    rdi
0x14000ee4f  push    r12
0x14000ee51  push    r13
0x14000ee53  push    r14
0x14000ee55  push    r15
0x14000ee57  lea     rbp, [rax-118h]
0x14000ee5e  sub     rsp, 1D8h
0x14000ee65  xor     r15d, r15d
0x14000ee68  movaps  xmmword ptr [rax-58h], xmm6
0x14000ee6c  movaps  xmmword ptr [rax-68h], xmm7
0x14000ee70  lea     r13, aS1518; "S-1-5-18"
0x14000ee77  movaps  xmmword ptr [rax-78h], xmm8
0x14000ee7c  lea     r12, aScheduleoneoma_0; "ScheduleOneOmaDmSessionClient"
0x14000ee83  movaps  xmmword ptr [rax-88h], xmm9
0x14000ee8b  mov     edi, r9d
0x14000ee8e  mov     [rsp+210h+var_1B0], r15d; Data
0x14000ee93  lea     r9, [rbp+110h+var_188]; int
0x14000ee97  movaps  xmmword ptr [rax-98h], xmm10
0x14000ee9f  mov     esi, r8d
0x14000eea2  movaps  xmmword ptr [rax-0A8h], xmm11
0x14000eeaa  lea     r8, [rbp+110h+arg_28]; int
0x14000eeb1  lea     rax, [rbp+110h+Data]
0x14000eeb8  mov     [rbp+110h+Data], r15d
0x14000eebf  mov     [rbp+110h+var_158], rax
0x14000eec3  mov     r14, rcx
0x14000eec6  lea     eax, [r15+1]
0x14000eeca  mov     [rbp+110h+var_160], r12
0x14000eece  mov     [rsp+210h+var_1B8], eax; int
0x14000eed2  lea     rcx, [rbp+110h+var_180]; int
0x14000eed6  mov     [rsp+210h+var_1C0], eax; int
0x14000eeda  mov     eax, [rbp+110h+arg_50]
0x14000eee0  mov     [rsp+210h+var_1C8], eax; int
0x14000eee4  mov     rax, [rbp+110h+arg_30]
0x14000eeeb  mov     [rsp+210h+var_1D0], r15d; int
0x14000eef0  mov     [rsp+210h+var_1D8], r13; unsigned __int16 *
0x14000eef5  mov     [rsp+210h+var_1E0], rax; unsigned __int16 *
0x14000eefa  lea     rax, aWindirSystem32_1; "%windir%\\system32\\deviceenroller.exe "
0x14000ef01  mov     qword ptr [rsp+210h+cbData], rax; unsigned __int16 *
0x14000ef06  mov     [rsp+210h+lpData], rdx; unsigned __int16 *
0x14000ef0b  lea     rdx, [rsp+210h+var_1A0]; int
0x14000ef10  mov     qword ptr [rbp+110h+var_180], r15
0x14000ef14  mov     qword ptr [rsp+210h+var_1A0], r15
0x14000ef19  mov     [rbp+110h+arg_28], r15
0x14000ef20  mov     qword ptr [rbp+110h+var_188], r15
0x14000ef24  mov     [rbp+110h+arg_38], r15
0x14000ef2b  mov     [rbp+110h+var_168], r15
0x14000ef2f  mov     [rbp+110h+var_170], r15
0x14000ef33  mov     [rbp+110h+var_178], r15
0x14000ef37  mov     [rbp+110h+var_190], r15
0x14000ef3b  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x14000ef40  mov     [rbp+110h+Data], eax
0x14000ef46  mov     ebx, eax
0x14000ef48  test    eax, eax
0x14000ef4a  js      loc_14000F17E
0x14000ef50  mov     rcx, [rbp+110h+arg_28]
0x14000ef57  lea     rdx, [rbp+110h+arg_38]
0x14000ef5e  mov     rax, [rcx]
0x14000ef61  mov     rax, [rax+48h]
0x14000ef65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ef6a  mov     [rbp+110h+Data], eax
0x14000ef70  mov     ebx, eax
0x14000ef72  test    eax, eax
0x14000ef74  js      loc_14000F17E
0x14000ef7a  mov     r9d, [rbp+110h+arg_20]
0x14000ef81  lea     rcx, [rbp+110h+arg_38]
0x14000ef88  mov     r8d, edi
0x14000ef8b  mov     edx, esi
0x14000ef8d  call    ?AddTimeTaskTriggers@@YAJAEAV?$CComPtr@UITriggerCollection@@@ATL@@KKK@Z; AddTimeTaskTriggers(ATL::CComPtr<ITriggerCollection> &,ulong,ulong,ulong)
0x14000ef92  mov     [rbp+110h+Data], eax
0x14000ef98  mov     ebx, eax
0x14000ef9a  test    eax, eax
0x14000ef9c  js      loc_14000F17E
0x14000efa2  mov     rcx, [rbp+110h+arg_28]
0x14000efa9  mov     rdx, [rbp+110h+arg_38]
0x14000efb0  mov     rax, [rcx]
0x14000efb3  mov     rax, [rax+50h]
0x14000efb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000efbc  mov     [rbp+110h+Data], eax
0x14000efc2  mov     ebx, eax
0x14000efc4  test    eax, eax
0x14000efc6  js      loc_14000F17E
0x14000efcc  mov     rbx, qword ptr [rsp+210h+var_1A0]
0x14000efd1  lea     rcx, [rbp+110h+pvarg]; pvarg
0x14000efd5  mov     rax, [rbx]
0x14000efd8  mov     rsi, [rax+88h]
0x14000efdf  call    cs:__imp_VariantInit
0x14000efe6  nop     dword ptr [rax+rax+00h]
0x14000efeb  movups  xmm6, xmmword ptr [rbp+110h+pvarg]
0x14000efef  lea     rcx, [rbp+110h+var_150]; pvarg
0x14000eff3  movsd   xmm7, qword ptr [rbp+110h+pvarg+10h]
0x14000eff8  call    cs:__imp_VariantInit
0x14000efff  nop     dword ptr [rax+rax+00h]
0x14000f004  movups  xmm8, xmmword ptr [rbp+110h+var_150]
0x14000f009  lea     rcx, [rbp+110h+var_C0]; this
0x14000f00d  mov     rdx, r13; unsigned __int16 *
0x14000f010  movsd   xmm9, qword ptr [rbp+110h+var_150+10h]
0x14000f016  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x14000f01b  mov     rdi, [rbp+110h+arg_28]
0x14000f022  lea     rcx, [rsp+210h+Block]; this
0x14000f027  mov     rdx, r14; unsigned __int16 *
0x14000f02a  movups  xmm10, xmmword ptr [rax]
0x14000f02e  movsd   xmm11, qword ptr [rax+10h]
0x14000f034  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14000f039  mov     rdx, [rax]
0x14000f03c  test    rdx, rdx
0x14000f03f  jz      short loc_14000F046
0x14000f041  mov     rdx, [rdx]
0x14000f044  jmp     short loc_14000F049
0x14000f046  mov     rdx, r15
0x14000f049  lea     rax, [rbp+110h+var_190]
0x14000f04d  movaps  [rbp+110h+var_120], xmm6
0x14000f051  mov     qword ptr [rsp+210h+var_1D0], rax
0x14000f056  mov     r9d, 6
0x14000f05c  lea     rax, [rbp+110h+var_120]
0x14000f060  movsd   [rbp+110h+var_110], xmm7
0x14000f065  mov     [rsp+210h+var_1D8], rax
0x14000f06a  mov     r8, rdi
0x14000f06d  lea     rax, [rbp+110h+var_100]
0x14000f071  mov     dword ptr [rsp+210h+var_1E0], 3
0x14000f079  mov     qword ptr [rsp+210h+cbData], rax
0x14000f07e  mov     rcx, rbx
0x14000f081  lea     rax, [rbp+110h+var_E0]
0x14000f085  movaps  [rbp+110h+var_100], xmm8
0x14000f08a  mov     [rsp+210h+lpData], rax
0x14000f08f  mov     rax, rsi
0x14000f092  movsd   [rbp+110h+var_F0], xmm9
0x14000f098  movaps  [rbp+110h+var_E0], xmm10
0x14000f09d  movsd   [rbp+110h+var_D0], xmm11
0x14000f0a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f0a8  mov     rbx, [rsp+210h+Block]
0x14000f0ad  mov     [rbp+110h+Data], eax
0x14000f0b3  test    rbx, rbx
0x14000f0b6  jz      short loc_14000F105
0x14000f0b8  or      eax, 0FFFFFFFFh
0x14000f0bb  lock xadd [rbx+10h], eax
0x14000f0c0  cmp     eax, 1
0x14000f0c3  jnz     short loc_14000F100
0x14000f0c5  test    rbx, rbx
0x14000f0c8  jz      short loc_14000F100
0x14000f0ca  mov     rcx, [rbx]; bstrString
0x14000f0cd  test    rcx, rcx
0x14000f0d0  jz      short loc_14000F0E1
0x14000f0d2  call    cs:__imp_SysFreeString
0x14000f0d9  nop     dword ptr [rax+rax+00h]
0x14000f0de  mov     [rbx], r15
0x14000f0e1  mov     rcx, [rbx+8]; Block
0x14000f0e5  test    rcx, rcx
0x14000f0e8  jz      short loc_14000F0F3
0x14000f0ea  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000f0ef  mov     [rbx+8], r15
0x14000f0f3  mov     edx, 18h
0x14000f0f8  mov     rcx, rbx; Block
0x14000f0fb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000f100  mov     [rsp+210h+Block], r15
0x14000f105  lea     rcx, [rbp+110h+var_C0]; pvarg
0x14000f109  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000f10e  lea     rcx, [rbp+110h+var_150]; pvarg
0x14000f112  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000f117  lea     rcx, [rbp+110h+pvarg]; pvarg
0x14000f11b  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000f120  mov     ebx, [rbp+110h+Data]
0x14000f126  test    ebx, ebx
0x14000f128  jns     short loc_14000F17E
0x14000f12a  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x14000f131  lea     rax, [rbp+110h+Data]
0x14000f138  mov     r9d, 4; dwType
0x14000f13e  lea     r8, a24registertask; "24RegisterTaskDefinition"
0x14000f145  mov     [rsp+210h+cbData], r9d; cbData
0x14000f14a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000f151  mov     [rsp+210h+lpData], rax; lpData
0x14000f156  call    cs:__imp_RegSetKeyValueW
0x14000f15d  nop     dword ptr [rax+rax+00h]
0x14000f162  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x14000f167  mov     edx, [rbp+110h+Data]; int
0x14000f16d  mov     r8, r12; char *
0x14000f170  mov     rcx, rax; this
0x14000f173  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x14000f178  mov     ebx, [rbp+110h+Data]
0x14000f17e  lea     rcx, [rbp+110h+var_190]
0x14000f182  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000f187  lea     rcx, [rbp+110h+var_178]
0x14000f18b  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000f190  lea     rcx, [rbp+110h+var_170]
0x14000f194  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000f199  lea     rcx, [rbp+110h+var_168]
0x14000f19d  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000f1a2  lea     rcx, [rbp+110h+arg_38]
0x14000f1a9  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000f1ae  lea     rcx, [rbp+110h+var_188]
0x14000f1b2  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000f1b7  lea     rcx, [rbp+110h+arg_28]
0x14000f1be  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000f1c3  lea     rcx, [rsp+210h+var_1A0]
0x14000f1c8  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000f1cd  lea     rcx, [rbp+110h+var_180]
0x14000f1d1  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000f1d6  lea     rcx, [rbp+110h+var_160]; this
0x14000f1da  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x14000f1df  lea     r11, [rsp+210h+var_38]
0x14000f1e7  mov     eax, ebx
0x14000f1e9  movaps  xmm6, xmmword ptr [r11-18h]
0x14000f1ee  movaps  xmm7, xmmword ptr [r11-28h]
0x14000f1f3  movaps  xmm8, xmmword ptr [r11-38h]
0x14000f1f8  movaps  xmm9, xmmword ptr [r11-48h]
0x14000f1fd  movaps  xmm10, xmmword ptr [r11-58h]
0x14000f202  movaps  xmm11, xmmword ptr [r11-68h]
0x14000f207  mov     rsp, r11
0x14000f20a  pop     r15
0x14000f20c  pop     r14
0x14000f20e  pop     r13
0x14000f210  pop     r12
0x14000f212  pop     rdi
0x14000f213  pop     rsi
0x14000f214  pop     rbx
0x14000f215  pop     rbp
0x14000f216  retn
```
