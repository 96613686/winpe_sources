# ScheduleOMADMClientTaskHelper

- ea: `0x14000e200`
- end: `0x14000e528`
- name: `ScheduleOMADMClientTaskHelper`
- size: `808`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x14000e128`

## callees

- `0x140002930`
- `0x140002954`
- `0x1400046a4`
- `0x140004c34`
- `0x140007368`
- `0x140008dc8`
- `0x140008e48`
- `0x1400090fc`
- `0x14000a0b8`
- `0x14000e200`
- `0x1400177b0`
- `0x140017ba0`
- `0x140019010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000e413`
- `OLEAUT32!__imp_SysFreeString` at `0x14000e413`
- `OLEAUT32!__imp_VariantInit` at `0x14000e324`
- `OLEAUT32!__imp_VariantInit` at `0x14000e337`
- `OLEAUT32!__imp_VariantInit` at `0x14000e324`
- `OLEAUT32!__imp_VariantInit` at `0x14000e337`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14000e48c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14000e48c`

## string_xrefs

- `0x14000e2a0`: `ScheduleOMADMClientTaskHelper`
- `0x14000e2ee`: `%windir%\system32\omadmclient.exe `
- `0x14000e474`: `54RegisterTaskDefinition`

## pseudocode

```c
__int64 __fastcall ScheduleOMADMClientTaskHelper(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        int a4)
{
  int v7; // ebx
  __int64 v8; // rbx
  __int64 (__fastcall *v9)(__int64, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *); // r15
  __int128 v10; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  __int128 v12; // xmm8
  IRecordInfo *v13; // xmm9_8
  _variant_t *v14; // rax
  __int64 v15; // rdi
  __int128 v16; // xmm10
  __int64 v17; // xmm11_8
  _bstr_t *v18; // rax
  __int64 v19; // rdx
  int v20; // eax
  BSTR *v21; // rbx
  BSTR v22; // rcx
  CEnrollmentLogger *Logger; // rax
  __int64 Data; // [rsp+78h] [rbp-90h] BYREF
  int v27[2]; // [rsp+80h] [rbp-88h] BYREF
  int v28[2]; // [rsp+88h] [rbp-80h] BYREF
  void *Block; // [rsp+90h] [rbp-78h] BYREF
  __int64 v30; // [rsp+98h] [rbp-70h] BYREF
  int v31[2]; // [rsp+A0h] [rbp-68h] BYREF
  int v32[2]; // [rsp+A8h] [rbp-60h] BYREF
  _QWORD v33[2]; // [rsp+B8h] [rbp-50h] BYREF
  VARIANTARG v34; // [rsp+C8h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+E0h] [rbp-28h] BYREF
  __int128 v36; // [rsp+F8h] [rbp-10h] BYREF
  IRecordInfo *v37; // [rsp+108h] [rbp+0h]
  __int128 v38; // [rsp+118h] [rbp+10h] BYREF
  IRecordInfo *v39; // [rsp+128h] [rbp+20h]
  __int128 v40; // [rsp+138h] [rbp+30h] BYREF
  __int64 v41; // [rsp+148h] [rbp+40h]
  VARIANTARG v42; // [rsp+158h] [rbp+50h] BYREF
  unsigned __int16 v43[264]; // [rsp+178h] [rbp+70h] BYREF

  *(_QWORD *)v32 = 0;
  *(_QWORD *)v28 = 0;
  *(_QWORD *)v27 = 0;
  *(_QWORD *)v31 = 0;
  v30 = 0;
  v7 = StringCchPrintfW(v43, 0x104u, L"/serverid \"%s\" /lookuptype 1 /initiator %d ", a1, a4);
  LODWORD(Data) = v7;
  v33[1] = &Data;
  v33[0] = "ScheduleOMADMClientTaskHelper";
  if ( v7 >= 0 )
  {
    LODWORD(Data) = CreateTask(
                      v32,
                      (__int64)v28,
                      v27,
                      v31,
                      a1,
                      L"%windir%\\system32\\omadmclient.exe ",
                      v43,
                      a2,
                      0,
                      1,
                      0,
                      0,
                      0);
    v7 = Data;
    if ( (int)Data >= 0 )
    {
      v8 = *(_QWORD *)v28;
      v9 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))(**(_QWORD **)v28 + 136LL);
      VariantInit(&pvarg);
      v10 = *(_OWORD *)&pvarg.vt;
      pRecInfo = pvarg.pRecInfo;
      VariantInit(&v34);
      v12 = *(_OWORD *)&v34.vt;
      v13 = v34.pRecInfo;
      if ( !a2 )
        a2 = L"S-1-5-18";
      v14 = _variant_t::_variant_t((_variant_t *)&v42, a2);
      v15 = *(_QWORD *)v27;
      v16 = *(_OWORD *)v14;
      v17 = *((_QWORD *)v14 + 2);
      v18 = _bstr_t::_bstr_t((_bstr_t *)&Block, a3);
      if ( *(_QWORD *)v18 )
        v19 = **(_QWORD **)v18;
      else
        v19 = 0;
      v36 = v10;
      v37 = pRecInfo;
      v38 = v12;
      v39 = v13;
      v40 = v16;
      v41 = v17;
      v20 = v9(v8, v19, v15, 6, &v40, &v38, 3, &v36, &v30);
      v21 = (BSTR *)Block;
      LODWORD(Data) = v20;
      if ( Block )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v21 )
        {
          if ( *v21 )
          {
            SysFreeString(*v21);
            *v21 = 0;
          }
          v22 = v21[1];
          if ( v22 )
          {
            operator delete(v22);
            v21[1] = 0;
          }
          operator delete(v21);
        }
        Block = 0;
      }
      ATL::CComVariant::~CComVariant(&v42);
      ATL::CComVariant::~CComVariant(&v34);
      ATL::CComVariant::~CComVariant(&pvarg);
      v7 = Data;
      if ( (int)Data < 0 )
      {
        RegSetKeyValueW(HKEY_LOCAL_MACHINE, c_szEnrollmentDB, L"54RegisterTaskDefinition", 4u, &Data, 4u);
        Logger = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(Logger, Data, "ScheduleOMADMClientTaskHelper");
        v7 = Data;
      }
    }
  }
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v33);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v30);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(v31);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(v27);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(v28);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(v32);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14000e200  mov     rax, rsp
0x14000e203  push    rbp
0x14000e204  push    rbx
0x14000e205  push    rsi
0x14000e206  push    rdi
0x14000e207  push    r12
0x14000e209  push    r13
0x14000e20b  push    r14
0x14000e20d  push    r15
0x14000e20f  lea     rbp, [rax-338h]
0x14000e216  sub     rsp, 3F8h
0x14000e21d  movaps  xmmword ptr [rax-58h], xmm6
0x14000e221  movaps  xmmword ptr [rax-68h], xmm7
0x14000e225  movaps  xmmword ptr [rax-78h], xmm8
0x14000e22a  movaps  xmmword ptr [rax-88h], xmm9
0x14000e232  movaps  xmmword ptr [rax-98h], xmm10
0x14000e23a  movaps  xmmword ptr [rax-0A8h], xmm11
0x14000e242  mov     rax, cs:__security_cookie
0x14000e249  xor     rax, rsp
0x14000e24c  mov     [rbp+330h+var_B0], rax
0x14000e253  xor     r12d, r12d
0x14000e256  mov     dword ptr [rsp+430h+lpData], r9d
0x14000e25b  mov     r9, rcx
0x14000e25e  mov     qword ptr [rbp+330h+var_390], r12
0x14000e262  mov     r14, r8
0x14000e265  mov     qword ptr [rbp+330h+var_3B0], r12
0x14000e269  mov     rsi, rdx
0x14000e26c  mov     qword ptr [rsp+430h+var_3B8], r12
0x14000e271  mov     rdi, rcx
0x14000e274  mov     qword ptr [rbp+330h+var_398], r12
0x14000e278  lea     rcx, [rbp+330h+var_2C0]; unsigned __int16 *
0x14000e27c  mov     [rbp+330h+var_3A0], r12
0x14000e280  lea     r8, aServeridSLooku; "/serverid \"%s\" /lookuptype 1 /initiat"...
0x14000e287  mov     edx, 104h; unsigned __int64
0x14000e28c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000e291  mov     ebx, eax
0x14000e293  mov     dword ptr [rsp+430h+Data], eax
0x14000e297  lea     rax, [rsp+430h+Data]
0x14000e29c  mov     [rbp+330h+var_378], rax
0x14000e2a0  lea     r13, aScheduleomadmc; "ScheduleOMADMClientTaskHelper"
0x14000e2a7  mov     [rbp+330h+var_380], r13
0x14000e2ab  test    ebx, ebx
0x14000e2ad  js      loc_14000E4AA
0x14000e2b3  mov     [rsp+430h+var_3D0], r12d; Data
0x14000e2b8  lea     rax, [rbp+330h+var_2C0]
0x14000e2bc  mov     [rsp+430h+var_3D8], r12d; int
0x14000e2c1  lea     r9, [rbp+330h+var_398]; int
0x14000e2c5  mov     [rsp+430h+var_3E0], r12d; int
0x14000e2ca  lea     r8, [rsp+430h+var_3B8]; int
0x14000e2cf  mov     [rsp+430h+var_3E8], 1; int
0x14000e2d7  lea     rdx, [rbp+330h+var_3B0]; int
0x14000e2db  mov     [rsp+430h+var_3F0], r12d; int
0x14000e2e0  lea     rcx, [rbp+330h+var_390]; int
0x14000e2e4  mov     [rsp+430h+var_3F8], rsi; unsigned __int16 *
0x14000e2e9  mov     [rsp+430h+var_400], rax; unsigned __int16 *
0x14000e2ee  lea     rax, aWindirSystem32; "%windir%\\system32\\omadmclient.exe "
0x14000e2f5  mov     qword ptr [rsp+430h+cbData], rax; unsigned __int16 *
0x14000e2fa  mov     [rsp+430h+lpData], rdi; unsigned __int16 *
0x14000e2ff  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x14000e304  mov     dword ptr [rsp+430h+Data], eax
0x14000e308  mov     ebx, eax
0x14000e30a  test    eax, eax
0x14000e30c  js      loc_14000E4AA
0x14000e312  mov     rbx, qword ptr [rbp+330h+var_3B0]
0x14000e316  lea     rcx, [rbp+330h+pvarg]; pvarg
0x14000e31a  mov     rax, [rbx]
0x14000e31d  mov     r15, [rax+88h]
0x14000e324  call    cs:__imp_VariantInit
0x14000e32a  movups  xmm6, xmmword ptr [rbp+330h+pvarg]
0x14000e32e  lea     rcx, [rbp+330h+var_370]; pvarg
0x14000e332  movsd   xmm7, qword ptr [rbp+330h+pvarg+10h]
0x14000e337  call    cs:__imp_VariantInit
0x14000e33d  movups  xmm8, xmmword ptr [rbp+330h+var_370]
0x14000e342  lea     rax, aS1518; "S-1-5-18"
0x14000e349  test    rsi, rsi
0x14000e34c  movsd   xmm9, qword ptr [rbp+330h+var_370+10h]
0x14000e352  lea     rcx, [rbp+330h+var_2E0]; this
0x14000e356  cmovz   rsi, rax
0x14000e35a  mov     rdx, rsi; unsigned __int16 *
0x14000e35d  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x14000e362  mov     rdi, qword ptr [rsp+430h+var_3B8]
0x14000e367  lea     rcx, [rbp+330h+Block]; this
0x14000e36b  mov     rdx, r14; unsigned __int16 *
0x14000e36e  movups  xmm10, xmmword ptr [rax]
0x14000e372  movsd   xmm11, qword ptr [rax+10h]
0x14000e378  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14000e37d  mov     rdx, [rax]
0x14000e380  test    rdx, rdx
0x14000e383  jz      short loc_14000E38A
0x14000e385  mov     rdx, [rdx]
0x14000e388  jmp     short loc_14000E38D
0x14000e38a  mov     rdx, r12
0x14000e38d  lea     rax, [rbp+330h+var_3A0]
0x14000e391  movaps  [rbp+330h+var_340], xmm6
0x14000e395  mov     qword ptr [rsp+430h+var_3F0], rax
0x14000e39a  mov     r9d, 6
0x14000e3a0  lea     rax, [rbp+330h+var_340]
0x14000e3a4  movsd   [rbp+330h+var_330], xmm7
0x14000e3a9  mov     [rsp+430h+var_3F8], rax
0x14000e3ae  mov     r8, rdi
0x14000e3b1  lea     rax, [rbp+330h+var_320]
0x14000e3b5  mov     dword ptr [rsp+430h+var_400], 3
0x14000e3bd  mov     qword ptr [rsp+430h+cbData], rax
0x14000e3c2  mov     rcx, rbx
0x14000e3c5  lea     rax, [rbp+330h+var_300]
0x14000e3c9  movaps  [rbp+330h+var_320], xmm8
0x14000e3ce  mov     [rsp+430h+lpData], rax
0x14000e3d3  mov     rax, r15
0x14000e3d6  movsd   [rbp+330h+var_310], xmm9
0x14000e3dc  movaps  [rbp+330h+var_300], xmm10
0x14000e3e1  movsd   [rbp+330h+var_2F0], xmm11
0x14000e3e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e3ec  mov     rbx, [rbp+330h+Block]
0x14000e3f0  mov     dword ptr [rsp+430h+Data], eax
0x14000e3f4  test    rbx, rbx
0x14000e3f7  jz      short loc_14000E43F
0x14000e3f9  or      eax, 0FFFFFFFFh
0x14000e3fc  lock xadd [rbx+10h], eax
0x14000e401  cmp     eax, 1
0x14000e404  jnz     short loc_14000E43B
0x14000e406  test    rbx, rbx
0x14000e409  jz      short loc_14000E43B
0x14000e40b  mov     rcx, [rbx]; bstrString
0x14000e40e  test    rcx, rcx
0x14000e411  jz      short loc_14000E41C
0x14000e413  call    cs:__imp_SysFreeString
0x14000e419  mov     [rbx], r12
0x14000e41c  mov     rcx, [rbx+8]; Block
0x14000e420  test    rcx, rcx
0x14000e423  jz      short loc_14000E42E
0x14000e425  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000e42a  mov     [rbx+8], r12
0x14000e42e  mov     edx, 18h
0x14000e433  mov     rcx, rbx; Block
0x14000e436  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000e43b  mov     [rbp+330h+Block], r12
0x14000e43f  lea     rcx, [rbp+330h+var_2E0]; pvarg
0x14000e443  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000e448  lea     rcx, [rbp+330h+var_370]; pvarg
0x14000e44c  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000e451  lea     rcx, [rbp+330h+pvarg]; pvarg
0x14000e455  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000e45a  mov     ebx, dword ptr [rsp+430h+Data]
0x14000e45e  test    ebx, ebx
0x14000e460  jns     short loc_14000E4AA
0x14000e462  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x14000e469  lea     rax, [rsp+430h+Data]
0x14000e46e  mov     r9d, 4; dwType
0x14000e474  lea     r8, a54registertask; "54RegisterTaskDefinition"
0x14000e47b  mov     [rsp+430h+cbData], r9d; cbData
0x14000e480  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000e487  mov     [rsp+430h+lpData], rax; lpData
0x14000e48c  call    cs:__imp_RegSetKeyValueW
0x14000e492  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x14000e497  mov     edx, dword ptr [rsp+430h+Data]; int
0x14000e49b  mov     r8, r13; char *
0x14000e49e  mov     rcx, rax; this
0x14000e4a1  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x14000e4a6  mov     ebx, dword ptr [rsp+430h+Data]
0x14000e4aa  lea     rcx, [rbp+330h+var_380]; this
0x14000e4ae  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x14000e4b3  lea     rcx, [rbp+330h+var_3A0]
0x14000e4b7  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000e4bc  lea     rcx, [rbp+330h+var_398]
0x14000e4c0  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000e4c5  lea     rcx, [rsp+430h+var_3B8]
0x14000e4ca  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000e4cf  lea     rcx, [rbp+330h+var_3B0]
0x14000e4d3  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000e4d8  lea     rcx, [rbp+330h+var_390]
0x14000e4dc  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000e4e1  mov     eax, ebx
0x14000e4e3  mov     rcx, [rbp+330h+var_B0]
0x14000e4ea  xor     rcx, rsp; StackCookie
0x14000e4ed  call    __security_check_cookie
0x14000e4f2  lea     r11, [rsp+430h+var_38]
0x14000e4fa  movaps  xmm6, xmmword ptr [r11-18h]
0x14000e4ff  movaps  xmm7, xmmword ptr [r11-28h]
0x14000e504  movaps  xmm8, xmmword ptr [r11-38h]
0x14000e509  movaps  xmm9, xmmword ptr [r11-48h]
0x14000e50e  movaps  xmm10, xmmword ptr [r11-58h]
0x14000e513  movaps  xmm11, xmmword ptr [r11-68h]
0x14000e518  mov     rsp, r11
0x14000e51b  pop     r15
0x14000e51d  pop     r14
0x14000e51f  pop     r13
0x14000e521  pop     r12
0x14000e523  pop     rdi
0x14000e524  pop     rsi
0x14000e525  pop     rbx
0x14000e526  pop     rbp
0x14000e527  retn
```
