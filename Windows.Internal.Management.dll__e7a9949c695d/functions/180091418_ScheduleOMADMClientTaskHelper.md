# ScheduleOMADMClientTaskHelper

- ea: `0x180091418`
- end: `0x18009172c`
- name: `ScheduleOMADMClientTaskHelper`
- size: `788`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180091350`

## callees

- `0x180004d50`
- `0x1800051fc`
- `0x18000a8e8`
- `0x18008e454`
- `0x18008e4c4`
- `0x18008e510`
- `0x18008e584`
- `0x18008e5b8`
- `0x18008eb90`
- `0x180091418`
- `0x180093684`
- `0x180093f34`
- `0x1800b7010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180091619`
- `OLEAUT32!__imp_SysFreeString` at `0x180091619`
- `OLEAUT32!__imp_VariantInit` at `0x180091534`
- `OLEAUT32!__imp_VariantInit` at `0x180091547`
- `OLEAUT32!__imp_VariantInit` at `0x180091534`
- `OLEAUT32!__imp_VariantInit` at `0x180091547`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180091692`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180091692`

## string_xrefs

- `0x1800914b0`: `ScheduleOMADMClientTaskHelper`
- `0x18009167a`: `54RegisterTaskDefinition`
- `0x1800914fe`: `%windir%\system32\omadmclient.exe `

## pseudocode

```c
__int64 __fastcall ScheduleOMADMClientTaskHelper(__int64 a1, __int64 a2, const unsigned __int16 *a3, int a4)
{
  int v6; // ebx
  __int64 v7; // rbx
  __int64 (__fastcall *v8)(__int64, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *); // r14
  __int128 v9; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  __int128 v11; // xmm8
  IRecordInfo *v12; // xmm9_8
  _variant_t *v13; // rax
  __int64 v14; // rdi
  __int128 v15; // xmm10
  __int64 v16; // xmm11_8
  _bstr_t *v17; // rax
  __int64 v18; // rdx
  int v19; // eax
  BSTR *v20; // rbx
  BSTR v21; // rcx
  CEnrollmentLogger *Logger; // rax
  int v25; // [rsp+48h] [rbp-C0h]
  int v26; // [rsp+50h] [rbp-B8h]
  int v27; // [rsp+58h] [rbp-B0h]
  int v28; // [rsp+60h] [rbp-A8h]
  int v29; // [rsp+68h] [rbp-A0h]
  __int64 Data; // [rsp+78h] [rbp-90h] BYREF
  __int64 v31; // [rsp+80h] [rbp-88h] BYREF
  __int64 v32; // [rsp+88h] [rbp-80h] BYREF
  void *Block; // [rsp+90h] [rbp-78h] BYREF
  __int64 v34; // [rsp+98h] [rbp-70h] BYREF
  __int64 v35; // [rsp+A0h] [rbp-68h] BYREF
  _QWORD v36[2]; // [rsp+A8h] [rbp-60h] BYREF
  _QWORD v37[2]; // [rsp+B8h] [rbp-50h] BYREF
  VARIANTARG v38; // [rsp+C8h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+E0h] [rbp-28h] BYREF
  __int128 v40; // [rsp+F8h] [rbp-10h] BYREF
  IRecordInfo *v41; // [rsp+108h] [rbp+0h]
  __int128 v42; // [rsp+118h] [rbp+10h] BYREF
  IRecordInfo *v43; // [rsp+128h] [rbp+20h]
  __int128 v44; // [rsp+138h] [rbp+30h] BYREF
  __int64 v45; // [rsp+148h] [rbp+40h]
  _BYTE v46[32]; // [rsp+158h] [rbp+50h] BYREF
  unsigned __int16 v47[264]; // [rsp+178h] [rbp+70h] BYREF

  v36[0] = 0;
  v32 = 0;
  v31 = 0;
  v35 = 0;
  v34 = 0;
  v6 = StringCchPrintfW(v47, 0x104u, L"/serverid \"%s\" /lookuptype 1 /initiator %d ", a1, a4);
  LODWORD(Data) = v6;
  v37[1] = &Data;
  v37[0] = "ScheduleOMADMClientTaskHelper";
  if ( v6 >= 0 )
  {
    v29 = 0;
    v28 = 0;
    v27 = 0;
    v26 = 1;
    v25 = 0;
    LODWORD(Data) = CreateTask(
                      v36,
                      &v32,
                      &v31,
                      &v35,
                      a1,
                      L"%windir%\\system32\\omadmclient.exe ",
                      v47,
                      0,
                      v25,
                      v26,
                      v27,
                      v28,
                      v29);
    v6 = Data;
    if ( (int)Data >= 0 )
    {
      v7 = v32;
      v8 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))(*(_QWORD *)v32 + 136LL);
      VariantInit(&pvarg);
      v9 = *(_OWORD *)&pvarg.vt;
      pRecInfo = pvarg.pRecInfo;
      VariantInit(&v38);
      v11 = *(_OWORD *)&v38.vt;
      v12 = v38.pRecInfo;
      v13 = _variant_t::_variant_t((_variant_t *)v46, L"S-1-5-18");
      v14 = v31;
      v15 = *(_OWORD *)v13;
      v16 = *((_QWORD *)v13 + 2);
      v17 = _bstr_t::_bstr_t((_bstr_t *)&Block, a3);
      if ( *(_QWORD *)v17 )
        v18 = **(_QWORD **)v17;
      else
        v18 = 0;
      v40 = v9;
      v41 = pRecInfo;
      v42 = v11;
      v43 = v12;
      v44 = v15;
      v45 = v16;
      v19 = v8(v7, v18, v14, 6, &v44, &v42, 3, &v40, &v34);
      v20 = (BSTR *)Block;
      LODWORD(Data) = v19;
      if ( Block )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v20 )
        {
          if ( *v20 )
          {
            SysFreeString(*v20);
            *v20 = 0;
          }
          v21 = v20[1];
          if ( v21 )
          {
            operator delete(v21);
            v20[1] = 0;
          }
          operator delete(v20);
        }
        Block = 0;
      }
      _variant_t::~_variant_t((_variant_t *)v46);
      _variant_t::~_variant_t((_variant_t *)&v38);
      _variant_t::~_variant_t((_variant_t *)&pvarg);
      v6 = Data;
      if ( (int)Data < 0 )
      {
        RegSetKeyValueW(HKEY_LOCAL_MACHINE, c_szEnrollmentDB, L"54RegisterTaskDefinition", 4u, &Data, 4u);
        Logger = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(Logger, Data, "ScheduleOMADMClientTaskHelper");
        v6 = Data;
      }
    }
  }
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v37);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v34);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v35);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v31);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v32);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(v36);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180091418  mov     rax, rsp
0x18009141b  push    rbp
0x18009141c  push    rbx
0x18009141d  push    rsi
0x18009141e  push    rdi
0x18009141f  push    r12
0x180091421  push    r14
0x180091423  push    r15
0x180091425  lea     rbp, [rax-328h]
0x18009142c  sub     rsp, 3F0h
0x180091433  movaps  xmmword ptr [rax-48h], xmm6
0x180091437  movaps  xmmword ptr [rax-58h], xmm7
0x18009143b  movaps  xmmword ptr [rax-68h], xmm8
0x180091440  movaps  xmmword ptr [rax-78h], xmm9
0x180091445  movaps  xmmword ptr [rax-88h], xmm10
0x18009144d  movaps  xmmword ptr [rax-98h], xmm11
0x180091455  mov     rax, cs:__security_cookie
0x18009145c  xor     rax, rsp
0x18009145f  mov     [rbp+320h+var_A0], rax
0x180091466  xor     r15d, r15d
0x180091469  mov     dword ptr [rsp+420h+lpData], r9d
0x18009146e  mov     r9, rcx
0x180091471  mov     [rbp+320h+var_380], r15
0x180091475  mov     rsi, r8
0x180091478  mov     [rbp+320h+var_3A0], r15
0x18009147c  mov     rdi, rcx
0x18009147f  mov     [rsp+420h+var_3A8], r15
0x180091484  lea     rcx, [rbp+320h+var_2B0]; unsigned __int16 *
0x180091488  mov     [rbp+320h+var_388], r15
0x18009148c  lea     r8, aServeridSLooku; "/serverid \"%s\" /lookuptype 1 /initiat"...
0x180091493  mov     [rbp+320h+var_390], r15
0x180091497  mov     edx, 104h; unsigned __int64
0x18009149c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800914a1  mov     ebx, eax
0x1800914a3  mov     dword ptr [rsp+420h+Data], eax
0x1800914a7  lea     rax, [rsp+420h+Data]
0x1800914ac  mov     [rbp+320h+var_368], rax
0x1800914b0  lea     r12, aScheduleomadmc; "ScheduleOMADMClientTaskHelper"
0x1800914b7  mov     [rbp+320h+var_370], r12
0x1800914bb  test    ebx, ebx
0x1800914bd  js      loc_1800916B0
0x1800914c3  mov     [rsp+420h+var_3C0], r15d
0x1800914c8  lea     rax, [rbp+320h+var_2B0]
0x1800914cc  mov     [rsp+420h+var_3C8], r15d
0x1800914d1  lea     r9, [rbp+320h+var_388]
0x1800914d5  mov     [rsp+420h+var_3D0], r15d
0x1800914da  lea     r8, [rsp+420h+var_3A8]
0x1800914df  mov     [rsp+420h+var_3D8], 1
0x1800914e7  lea     rdx, [rbp+320h+var_3A0]
0x1800914eb  mov     [rsp+420h+var_3E0], r15d
0x1800914f0  lea     rcx, [rbp+320h+var_380]
0x1800914f4  mov     [rsp+420h+var_3E8], r15
0x1800914f9  mov     [rsp+420h+var_3F0], rax
0x1800914fe  lea     rax, aWindirSystem32; "%windir%\\system32\\omadmclient.exe "
0x180091505  mov     qword ptr [rsp+420h+cbData], rax
0x18009150a  mov     [rsp+420h+lpData], rdi
0x18009150f  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x180091514  mov     dword ptr [rsp+420h+Data], eax
0x180091518  mov     ebx, eax
0x18009151a  test    eax, eax
0x18009151c  js      loc_1800916B0
0x180091522  mov     rbx, [rbp+320h+var_3A0]
0x180091526  lea     rcx, [rbp+320h+pvarg]; pvarg
0x18009152a  mov     rax, [rbx]
0x18009152d  mov     r14, [rax+88h]
0x180091534  call    cs:__imp_VariantInit
0x18009153a  movups  xmm6, xmmword ptr [rbp+320h+pvarg]
0x18009153e  lea     rcx, [rbp+320h+var_360]; pvarg
0x180091542  movsd   xmm7, qword ptr [rbp+320h+pvarg+10h]
0x180091547  call    cs:__imp_VariantInit
0x18009154d  movups  xmm8, xmmword ptr [rbp+320h+var_360]
0x180091552  lea     rdx, aS1518; "S-1-5-18"
0x180091559  movsd   xmm9, qword ptr [rbp+320h+var_360+10h]
0x18009155f  lea     rcx, [rbp+320h+var_2D0]; this
0x180091563  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x180091568  mov     rdi, [rsp+420h+var_3A8]
0x18009156d  lea     rcx, [rbp+320h+Block]; this
0x180091571  mov     rdx, rsi; unsigned __int16 *
0x180091574  movups  xmm10, xmmword ptr [rax]
0x180091578  movsd   xmm11, qword ptr [rax+10h]
0x18009157e  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180091583  mov     rdx, [rax]
0x180091586  test    rdx, rdx
0x180091589  jz      short loc_180091590
0x18009158b  mov     rdx, [rdx]
0x18009158e  jmp     short loc_180091593
0x180091590  mov     rdx, r15
0x180091593  lea     rax, [rbp+320h+var_390]
0x180091597  movaps  [rbp+320h+var_330], xmm6
0x18009159b  mov     qword ptr [rsp+420h+var_3E0], rax
0x1800915a0  mov     r9d, 6
0x1800915a6  lea     rax, [rbp+320h+var_330]
0x1800915aa  movsd   [rbp+320h+var_320], xmm7
0x1800915af  mov     [rsp+420h+var_3E8], rax
0x1800915b4  mov     r8, rdi
0x1800915b7  lea     rax, [rbp+320h+var_310]
0x1800915bb  mov     dword ptr [rsp+420h+var_3F0], 3
0x1800915c3  mov     qword ptr [rsp+420h+cbData], rax
0x1800915c8  mov     rcx, rbx
0x1800915cb  lea     rax, [rbp+320h+var_2F0]
0x1800915cf  movaps  [rbp+320h+var_310], xmm8
0x1800915d4  mov     [rsp+420h+lpData], rax
0x1800915d9  mov     rax, r14
0x1800915dc  movsd   [rbp+320h+var_300], xmm9
0x1800915e2  movaps  [rbp+320h+var_2F0], xmm10
0x1800915e7  movsd   [rbp+320h+var_2E0], xmm11
0x1800915ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800915f2  mov     rbx, [rbp+320h+Block]
0x1800915f6  mov     dword ptr [rsp+420h+Data], eax
0x1800915fa  test    rbx, rbx
0x1800915fd  jz      short loc_180091645
0x1800915ff  or      eax, 0FFFFFFFFh
0x180091602  lock xadd [rbx+10h], eax
0x180091607  cmp     eax, 1
0x18009160a  jnz     short loc_180091641
0x18009160c  test    rbx, rbx
0x18009160f  jz      short loc_180091641
0x180091611  mov     rcx, [rbx]; bstrString
0x180091614  test    rcx, rcx
0x180091617  jz      short loc_180091622
0x180091619  call    cs:__imp_SysFreeString
0x18009161f  mov     [rbx], r15
0x180091622  mov     rcx, [rbx+8]; Block
0x180091626  test    rcx, rcx
0x180091629  jz      short loc_180091634
0x18009162b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180091630  mov     [rbx+8], r15
0x180091634  mov     edx, 18h
0x180091639  mov     rcx, rbx; Block
0x18009163c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180091641  mov     [rbp+320h+Block], r15
0x180091645  lea     rcx, [rbp+320h+var_2D0]; this
0x180091649  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18009164e  lea     rcx, [rbp+320h+var_360]; this
0x180091652  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180091657  lea     rcx, [rbp+320h+pvarg]; this
0x18009165b  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180091660  mov     ebx, dword ptr [rsp+420h+Data]
0x180091664  test    ebx, ebx
0x180091666  jns     short loc_1800916B0
0x180091668  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x18009166f  lea     rax, [rsp+420h+Data]
0x180091674  mov     r9d, 4; dwType
0x18009167a  lea     r8, a54registertask; "54RegisterTaskDefinition"
0x180091681  mov     [rsp+420h+cbData], r9d; cbData
0x180091686  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009168d  mov     [rsp+420h+lpData], rax; lpData
0x180091692  call    cs:__imp_RegSetKeyValueW
0x180091698  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18009169d  mov     edx, dword ptr [rsp+420h+Data]; int
0x1800916a1  mov     r8, r12; char *
0x1800916a4  mov     rcx, rax; this
0x1800916a7  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x1800916ac  mov     ebx, dword ptr [rsp+420h+Data]
0x1800916b0  lea     rcx, [rbp+320h+var_370]; this
0x1800916b4  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x1800916b9  lea     rcx, [rbp+320h+var_390]
0x1800916bd  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x1800916c2  lea     rcx, [rbp+320h+var_388]
0x1800916c6  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x1800916cb  lea     rcx, [rsp+420h+var_3A8]
0x1800916d0  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x1800916d5  lea     rcx, [rbp+320h+var_3A0]
0x1800916d9  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x1800916de  lea     rcx, [rbp+320h+var_380]
0x1800916e2  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x1800916e7  mov     eax, ebx
0x1800916e9  mov     rcx, [rbp+320h+var_A0]
0x1800916f0  xor     rcx, rsp; StackCookie
0x1800916f3  call    __security_check_cookie
0x1800916f8  lea     r11, [rsp+420h+var_30]
0x180091700  movaps  xmm6, xmmword ptr [r11-10h]
0x180091705  movaps  xmm7, xmmword ptr [r11-20h]
0x18009170a  movaps  xmm8, xmmword ptr [r11-30h]
0x18009170f  movaps  xmm9, xmmword ptr [r11-40h]
0x180091714  movaps  xmm10, xmmword ptr [r11-50h]
0x180091719  movaps  xmm11, xmmword ptr [r11-60h]
0x18009171e  mov     rsp, r11
0x180091721  pop     r15
0x180091723  pop     r14
0x180091725  pop     r12
0x180091727  pop     rdi
0x180091728  pop     rsi
0x180091729  pop     rbx
0x18009172a  pop     rbp
0x18009172b  retn
```
