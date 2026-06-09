# ScheduleOneOmaDmSessionClient

- ea: `0x18000e034`
- end: `0x18000e404`
- name: `ScheduleOneOmaDmSessionClient`
- size: `976`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, int, __int64, __int64, __int64, int Data, int, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18000de68`

## callees

- `0x180001cc8`
- `0x180007258`
- `0x1800072d0`
- `0x180007364`
- `0x1800077a0`
- `0x1800079e8`
- `0x180007f4c`
- `0x180008bd4`
- `0x18000e034`
- `0x18001b9d8`
- `0x18001bde0`
- `0x18001e010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000e2be`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e2be`
- `OLEAUT32!__imp_VariantInit` at `0x18000e1cb`
- `OLEAUT32!__imp_VariantInit` at `0x18000e1e4`
- `OLEAUT32!__imp_VariantInit` at `0x18000e1cb`
- `OLEAUT32!__imp_VariantInit` at `0x18000e1e4`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18000e342`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18000e342`

## string_xrefs

- `0x18000e32a`: `24RegisterTaskDefinition`
- `0x18000e0e6`: `%windir%\system32\deviceenroller.exe `

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
  struct IUnknown *v15; // rbx
  ULONG (__stdcall *Release)(IUnknown *); // rsi
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
  const struct std::nothrow_t *v28; // rdx
  BSTR *v29; // rbx
  BSTR v30; // rcx
  CEnrollmentLogger *Logger; // rax
  __int64 v33; // [rsp+48h] [rbp-C0h]
  int v34; // [rsp+68h] [rbp-A0h]
  struct IUnknown *v35; // [rsp+78h] [rbp-90h] BYREF
  void *v36; // [rsp+80h] [rbp-88h] BYREF
  __int64 v37; // [rsp+88h] [rbp-80h] BYREF
  __int64 v38; // [rsp+90h] [rbp-78h] BYREF
  LPVOID v39; // [rsp+98h] [rbp-70h] BYREF
  __int64 v40; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v41; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v42; // [rsp+B0h] [rbp-58h] BYREF
  _QWORD v43[2]; // [rsp+B8h] [rbp-50h] BYREF
  VARIANTARG v44; // [rsp+C8h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+E0h] [rbp-28h] BYREF
  __int128 v46; // [rsp+F8h] [rbp-10h] BYREF
  IRecordInfo *v47; // [rsp+108h] [rbp+0h]
  __int128 v48; // [rsp+118h] [rbp+10h] BYREF
  IRecordInfo *v49; // [rsp+128h] [rbp+20h]
  __int128 v50; // [rsp+138h] [rbp+30h] BYREF
  __int64 v51; // [rsp+148h] [rbp+40h]
  _BYTE v52[136]; // [rsp+158h] [rbp+50h] BYREF

  v34 = 0;
  Data = 0;
  v43[1] = &Data;
  v43[0] = "ScheduleOneOmaDmSessionClient";
  LODWORD(v33) = 0;
  v39 = 0;
  v35 = 0;
  a6 = 0;
  v38 = 0;
  a8 = 0;
  v42 = 0;
  v41 = 0;
  v40 = 0;
  v37 = 0;
  Data = CreateTask(
           &v39,
           &v35,
           &a6,
           &v38,
           a2,
           L"%windir%\\system32\\deviceenroller.exe ",
           a7,
           L"S-1-5-18",
           v33,
           a11,
           1,
           1,
           v34);
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
          v15 = v35;
          Release = v35->lpVtbl[5].Release;
          VariantInit(&pvarg);
          v17 = *(_OWORD *)&pvarg.vt;
          pRecInfo = pvarg.pRecInfo;
          VariantInit(&v44);
          v19 = *(_OWORD *)&v44.vt;
          v20 = v44.pRecInfo;
          v21 = _variant_t::_variant_t((_variant_t *)v52, L"S-1-5-18");
          v22 = a6;
          v23 = *(_OWORD *)v21;
          v24 = *((_QWORD *)v21 + 2);
          v25 = _bstr_t::_bstr_t((_bstr_t *)&v36, a1);
          if ( *(_QWORD *)v25 )
            v26 = **(_QWORD **)v25;
          else
            v26 = 0;
          v46 = v17;
          v47 = pRecInfo;
          v48 = v19;
          v49 = v20;
          v50 = v23;
          v51 = v24;
          v27 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))Release)(
                  v15,
                  v26,
                  v22,
                  6,
                  &v50,
                  &v48,
                  3,
                  &v46,
                  &v37);
          v29 = (BSTR *)v36;
          Data = v27;
          if ( v36 )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v36 + 4, 0xFFFFFFFF) == 1 && v29 )
            {
              if ( *v29 )
              {
                SysFreeString(*v29);
                *v29 = 0;
              }
              v30 = v29[1];
              if ( v30 )
              {
                operator delete(v30, v28);
                v29[1] = 0;
              }
              operator delete(v29, (const struct std::nothrow_t *)0x18);
            }
            v36 = 0;
          }
          _variant_t::~_variant_t((_variant_t *)v52);
          _variant_t::~_variant_t((_variant_t *)&v44);
          _variant_t::~_variant_t((_variant_t *)&pvarg);
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
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v37);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v40);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v41);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v42);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&a8);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v38);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&a6);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v35);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v39);
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v43);
  return v14;
}

```

## disassembly

```asm
0x18000e034  mov     rax, rsp
0x18000e037  push    rbp
0x18000e038  push    rbx
0x18000e039  push    rsi
0x18000e03a  push    rdi
0x18000e03b  push    r12
0x18000e03d  push    r13
0x18000e03f  push    r14
0x18000e041  push    r15
0x18000e043  lea     rbp, [rax-118h]
0x18000e04a  sub     rsp, 1D8h
0x18000e051  xor     r15d, r15d
0x18000e054  movaps  xmmword ptr [rax-58h], xmm6
0x18000e058  movaps  xmmword ptr [rax-68h], xmm7
0x18000e05c  lea     r13, aS1518; "S-1-5-18"
0x18000e063  movaps  xmmword ptr [rax-78h], xmm8
0x18000e068  lea     r12, aScheduleoneoma_0; "ScheduleOneOmaDmSessionClient"
0x18000e06f  movaps  xmmword ptr [rax-88h], xmm9
0x18000e077  mov     edi, r9d
0x18000e07a  mov     [rsp+210h+var_1B0], r15d
0x18000e07f  lea     r9, [rbp+110h+var_188]
0x18000e083  movaps  xmmword ptr [rax-98h], xmm10
0x18000e08b  mov     esi, r8d
0x18000e08e  movaps  xmmword ptr [rax-0A8h], xmm11
0x18000e096  lea     r8, [rbp+110h+arg_28]
0x18000e09d  lea     rax, [rbp+110h+Data]
0x18000e0a4  mov     [rbp+110h+Data], r15d
0x18000e0ab  mov     [rbp+110h+var_158], rax
0x18000e0af  mov     r14, rcx
0x18000e0b2  lea     eax, [r15+1]
0x18000e0b6  mov     [rbp+110h+var_160], r12
0x18000e0ba  mov     [rsp+210h+var_1B8], eax
0x18000e0be  lea     rcx, [rbp+110h+var_180]
0x18000e0c2  mov     [rsp+210h+var_1C0], eax
0x18000e0c6  mov     eax, [rbp+110h+arg_50]
0x18000e0cc  mov     [rsp+210h+var_1C8], eax
0x18000e0d0  mov     rax, [rbp+110h+arg_30]
0x18000e0d7  mov     dword ptr [rsp+210h+var_1D0], r15d
0x18000e0dc  mov     [rsp+210h+var_1D8], r13
0x18000e0e1  mov     [rsp+210h+var_1E0], rax
0x18000e0e6  lea     rax, aWindirSystem32_1; "%windir%\\system32\\deviceenroller.exe "
0x18000e0ed  mov     qword ptr [rsp+210h+cbData], rax
0x18000e0f2  mov     [rsp+210h+lpData], rdx
0x18000e0f7  lea     rdx, [rsp+210h+var_1A0]
0x18000e0fc  mov     [rbp+110h+var_180], r15
0x18000e100  mov     [rsp+210h+var_1A0], r15
0x18000e105  mov     [rbp+110h+arg_28], r15
0x18000e10c  mov     [rbp+110h+var_188], r15
0x18000e110  mov     [rbp+110h+arg_38], r15
0x18000e117  mov     [rbp+110h+var_168], r15
0x18000e11b  mov     [rbp+110h+var_170], r15
0x18000e11f  mov     [rbp+110h+var_178], r15
0x18000e123  mov     [rbp+110h+var_190], r15
0x18000e127  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x18000e12c  mov     [rbp+110h+Data], eax
0x18000e132  mov     ebx, eax
0x18000e134  test    eax, eax
0x18000e136  js      loc_18000E36A
0x18000e13c  mov     rcx, [rbp+110h+arg_28]
0x18000e143  lea     rdx, [rbp+110h+arg_38]
0x18000e14a  mov     rax, [rcx]
0x18000e14d  mov     rax, [rax+48h]
0x18000e151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e156  mov     [rbp+110h+Data], eax
0x18000e15c  mov     ebx, eax
0x18000e15e  test    eax, eax
0x18000e160  js      loc_18000E36A
0x18000e166  mov     r9d, [rbp+110h+arg_20]
0x18000e16d  lea     rcx, [rbp+110h+arg_38]
0x18000e174  mov     r8d, edi
0x18000e177  mov     edx, esi
0x18000e179  call    ?AddTimeTaskTriggers@@YAJAEAV?$CComPtr@UITriggerCollection@@@ATL@@KKK@Z; AddTimeTaskTriggers(ATL::CComPtr<ITriggerCollection> &,ulong,ulong,ulong)
0x18000e17e  mov     [rbp+110h+Data], eax
0x18000e184  mov     ebx, eax
0x18000e186  test    eax, eax
0x18000e188  js      loc_18000E36A
0x18000e18e  mov     rcx, [rbp+110h+arg_28]
0x18000e195  mov     rdx, [rbp+110h+arg_38]
0x18000e19c  mov     rax, [rcx]
0x18000e19f  mov     rax, [rax+50h]
0x18000e1a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1a8  mov     [rbp+110h+Data], eax
0x18000e1ae  mov     ebx, eax
0x18000e1b0  test    eax, eax
0x18000e1b2  js      loc_18000E36A
0x18000e1b8  mov     rbx, [rsp+210h+var_1A0]
0x18000e1bd  lea     rcx, [rbp+110h+pvarg]; pvarg
0x18000e1c1  mov     rax, [rbx]
0x18000e1c4  mov     rsi, [rax+88h]
0x18000e1cb  call    cs:__imp_VariantInit
0x18000e1d2  nop     dword ptr [rax+rax+00h]
0x18000e1d7  movups  xmm6, xmmword ptr [rbp+110h+pvarg]
0x18000e1db  lea     rcx, [rbp+110h+var_150]; pvarg
0x18000e1df  movsd   xmm7, qword ptr [rbp+110h+pvarg+10h]
0x18000e1e4  call    cs:__imp_VariantInit
0x18000e1eb  nop     dword ptr [rax+rax+00h]
0x18000e1f0  movups  xmm8, xmmword ptr [rbp+110h+var_150]
0x18000e1f5  lea     rcx, [rbp+110h+var_C0]; this
0x18000e1f9  mov     rdx, r13; unsigned __int16 *
0x18000e1fc  movsd   xmm9, qword ptr [rbp+110h+var_150+10h]
0x18000e202  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x18000e207  mov     rdi, [rbp+110h+arg_28]
0x18000e20e  lea     rcx, [rsp+210h+var_198]; this
0x18000e213  mov     rdx, r14; unsigned __int16 *
0x18000e216  movups  xmm10, xmmword ptr [rax]
0x18000e21a  movsd   xmm11, qword ptr [rax+10h]
0x18000e220  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000e225  mov     rdx, [rax]
0x18000e228  test    rdx, rdx
0x18000e22b  jz      short loc_18000E232
0x18000e22d  mov     rdx, [rdx]
0x18000e230  jmp     short loc_18000E235
0x18000e232  mov     rdx, r15
0x18000e235  lea     rax, [rbp+110h+var_190]
0x18000e239  movaps  [rbp+110h+var_120], xmm6
0x18000e23d  mov     [rsp+210h+var_1D0], rax
0x18000e242  mov     r9d, 6
0x18000e248  lea     rax, [rbp+110h+var_120]
0x18000e24c  movsd   [rbp+110h+var_110], xmm7
0x18000e251  mov     [rsp+210h+var_1D8], rax
0x18000e256  mov     r8, rdi
0x18000e259  lea     rax, [rbp+110h+var_100]
0x18000e25d  mov     dword ptr [rsp+210h+var_1E0], 3
0x18000e265  mov     qword ptr [rsp+210h+cbData], rax
0x18000e26a  mov     rcx, rbx
0x18000e26d  lea     rax, [rbp+110h+var_E0]
0x18000e271  movaps  [rbp+110h+var_100], xmm8
0x18000e276  mov     [rsp+210h+lpData], rax
0x18000e27b  mov     rax, rsi
0x18000e27e  movsd   [rbp+110h+var_F0], xmm9
0x18000e284  movaps  [rbp+110h+var_E0], xmm10
0x18000e289  movsd   [rbp+110h+var_D0], xmm11
0x18000e28f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e294  mov     rbx, [rsp+210h+var_198]
0x18000e299  mov     [rbp+110h+Data], eax
0x18000e29f  test    rbx, rbx
0x18000e2a2  jz      short loc_18000E2F1
0x18000e2a4  or      eax, 0FFFFFFFFh
0x18000e2a7  lock xadd [rbx+10h], eax
0x18000e2ac  cmp     eax, 1
0x18000e2af  jnz     short loc_18000E2EC
0x18000e2b1  test    rbx, rbx
0x18000e2b4  jz      short loc_18000E2EC
0x18000e2b6  mov     rcx, [rbx]; bstrString
0x18000e2b9  test    rcx, rcx
0x18000e2bc  jz      short loc_18000E2CD
0x18000e2be  call    cs:__imp_SysFreeString
0x18000e2c5  nop     dword ptr [rax+rax+00h]
0x18000e2ca  mov     [rbx], r15
0x18000e2cd  mov     rcx, [rbx+8]; void *
0x18000e2d1  test    rcx, rcx
0x18000e2d4  jz      short loc_18000E2DF
0x18000e2d6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000e2db  mov     [rbx+8], r15
0x18000e2df  mov     edx, 18h; struct std::nothrow_t *
0x18000e2e4  mov     rcx, rbx; void *
0x18000e2e7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000e2ec  mov     [rsp+210h+var_198], r15
0x18000e2f1  lea     rcx, [rbp+110h+var_C0]; this
0x18000e2f5  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18000e2fa  lea     rcx, [rbp+110h+var_150]; this
0x18000e2fe  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18000e303  lea     rcx, [rbp+110h+pvarg]; this
0x18000e307  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18000e30c  mov     ebx, [rbp+110h+Data]
0x18000e312  test    ebx, ebx
0x18000e314  jns     short loc_18000E36A
0x18000e316  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x18000e31d  lea     rax, [rbp+110h+Data]
0x18000e324  mov     r9d, 4; dwType
0x18000e32a  lea     r8, a24registertask; "24RegisterTaskDefinition"
0x18000e331  mov     [rsp+210h+cbData], r9d; cbData
0x18000e336  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000e33d  mov     [rsp+210h+lpData], rax; lpData
0x18000e342  call    cs:__imp_RegSetKeyValueW
0x18000e349  nop     dword ptr [rax+rax+00h]
0x18000e34e  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18000e353  mov     edx, [rbp+110h+Data]; int
0x18000e359  mov     r8, r12; char *
0x18000e35c  mov     rcx, rax; this
0x18000e35f  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x18000e364  mov     ebx, [rbp+110h+Data]
0x18000e36a  lea     rcx, [rbp+110h+var_190]
0x18000e36e  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18000e373  lea     rcx, [rbp+110h+var_178]
0x18000e377  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18000e37c  lea     rcx, [rbp+110h+var_170]
0x18000e380  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18000e385  lea     rcx, [rbp+110h+var_168]
0x18000e389  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18000e38e  lea     rcx, [rbp+110h+arg_38]
0x18000e395  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18000e39a  lea     rcx, [rbp+110h+var_188]
0x18000e39e  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18000e3a3  lea     rcx, [rbp+110h+arg_28]
0x18000e3aa  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18000e3af  lea     rcx, [rsp+210h+var_1A0]
0x18000e3b4  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18000e3b9  lea     rcx, [rbp+110h+var_180]
0x18000e3bd  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18000e3c2  lea     rcx, [rbp+110h+var_160]; this
0x18000e3c6  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18000e3cb  lea     r11, [rsp+210h+var_38]
0x18000e3d3  mov     eax, ebx
0x18000e3d5  movaps  xmm6, xmmword ptr [r11-18h]
0x18000e3da  movaps  xmm7, xmmword ptr [r11-28h]
0x18000e3df  movaps  xmm8, xmmword ptr [r11-38h]
0x18000e3e4  movaps  xmm9, xmmword ptr [r11-48h]
0x18000e3e9  movaps  xmm10, xmmword ptr [r11-58h]
0x18000e3ee  movaps  xmm11, xmmword ptr [r11-68h]
0x18000e3f3  mov     rsp, r11
0x18000e3f6  pop     r15
0x18000e3f8  pop     r14
0x18000e3fa  pop     r13
0x18000e3fc  pop     r12
0x18000e3fe  pop     rdi
0x18000e3ff  pop     rsi
0x18000e400  pop     rbx
0x18000e401  pop     rbp
0x18000e402  retn
```
