# ScheduleOMADMClientTaskHelper

- ea: `0x14000e934`
- end: `0x14000ec75`
- name: `ScheduleOMADMClientTaskHelper`
- size: `833`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

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
- `0x14000e934`
- `0x14001848c`
- `0x140018890`
- `0x14001a010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000eb53`
- `OLEAUT32!__imp_SysFreeString` at `0x14000eb53`
- `OLEAUT32!__imp_VariantInit` at `0x14000ea58`
- `OLEAUT32!__imp_VariantInit` at `0x14000ea71`
- `OLEAUT32!__imp_VariantInit` at `0x14000ea58`
- `OLEAUT32!__imp_VariantInit` at `0x14000ea71`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14000ebd2`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14000ebd2`

## string_xrefs

- `0x14000e9d4`: `ScheduleOMADMClientTaskHelper`
- `0x14000ea22`: `%windir%\system32\omadmclient.exe `
- `0x14000ebba`: `54RegisterTaskDefinition`

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
                      (int)v32,
                      (int)v28,
                      (int)v27,
                      (int)v31,
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
0x14000e934  mov     rax, rsp
0x14000e937  push    rbp
0x14000e938  push    rbx
0x14000e939  push    rsi
0x14000e93a  push    rdi
0x14000e93b  push    r12
0x14000e93d  push    r13
0x14000e93f  push    r14
0x14000e941  push    r15
0x14000e943  lea     rbp, [rax-338h]
0x14000e94a  sub     rsp, 3F8h
0x14000e951  movaps  xmmword ptr [rax-58h], xmm6
0x14000e955  movaps  xmmword ptr [rax-68h], xmm7
0x14000e959  movaps  xmmword ptr [rax-78h], xmm8
0x14000e95e  movaps  xmmword ptr [rax-88h], xmm9
0x14000e966  movaps  xmmword ptr [rax-98h], xmm10
0x14000e96e  movaps  xmmword ptr [rax-0A8h], xmm11
0x14000e976  mov     rax, cs:__security_cookie
0x14000e97d  xor     rax, rsp
0x14000e980  mov     [rbp+330h+var_B0], rax
0x14000e987  xor     r12d, r12d
0x14000e98a  mov     dword ptr [rsp+430h+lpData], r9d
0x14000e98f  mov     r9, rcx
0x14000e992  mov     qword ptr [rbp+330h+var_390], r12
0x14000e996  mov     r14, r8
0x14000e999  mov     qword ptr [rbp+330h+var_3B0], r12
0x14000e99d  mov     rsi, rdx
0x14000e9a0  mov     qword ptr [rsp+430h+var_3B8], r12
0x14000e9a5  mov     rdi, rcx
0x14000e9a8  mov     qword ptr [rbp+330h+var_398], r12
0x14000e9ac  lea     rcx, [rbp+330h+var_2C0]; unsigned __int16 *
0x14000e9b0  mov     [rbp+330h+var_3A0], r12
0x14000e9b4  lea     r8, aServeridSLooku; "/serverid \"%s\" /lookuptype 1 /initiat"...
0x14000e9bb  mov     edx, 104h; unsigned __int64
0x14000e9c0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000e9c5  mov     ebx, eax
0x14000e9c7  mov     dword ptr [rsp+430h+Data], eax
0x14000e9cb  lea     rax, [rsp+430h+Data]
0x14000e9d0  mov     [rbp+330h+var_378], rax
0x14000e9d4  lea     r13, aScheduleomadmc; "ScheduleOMADMClientTaskHelper"
0x14000e9db  mov     [rbp+330h+var_380], r13
0x14000e9df  test    ebx, ebx
0x14000e9e1  js      loc_14000EBF6
0x14000e9e7  mov     [rsp+430h+var_3D0], r12d; Data
0x14000e9ec  lea     rax, [rbp+330h+var_2C0]
0x14000e9f0  mov     [rsp+430h+var_3D8], r12d; int
0x14000e9f5  lea     r9, [rbp+330h+var_398]; int
0x14000e9f9  mov     [rsp+430h+var_3E0], r12d; int
0x14000e9fe  lea     r8, [rsp+430h+var_3B8]; int
0x14000ea03  mov     [rsp+430h+var_3E8], 1; int
0x14000ea0b  lea     rdx, [rbp+330h+var_3B0]; int
0x14000ea0f  mov     [rsp+430h+var_3F0], r12d; int
0x14000ea14  lea     rcx, [rbp+330h+var_390]; int
0x14000ea18  mov     [rsp+430h+var_3F8], rsi; unsigned __int16 *
0x14000ea1d  mov     [rsp+430h+var_400], rax; unsigned __int16 *
0x14000ea22  lea     rax, aWindirSystem32; "%windir%\\system32\\omadmclient.exe "
0x14000ea29  mov     qword ptr [rsp+430h+cbData], rax; unsigned __int16 *
0x14000ea2e  mov     [rsp+430h+lpData], rdi; unsigned __int16 *
0x14000ea33  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x14000ea38  mov     dword ptr [rsp+430h+Data], eax
0x14000ea3c  mov     ebx, eax
0x14000ea3e  test    eax, eax
0x14000ea40  js      loc_14000EBF6
0x14000ea46  mov     rbx, qword ptr [rbp+330h+var_3B0]
0x14000ea4a  lea     rcx, [rbp+330h+pvarg]; pvarg
0x14000ea4e  mov     rax, [rbx]
0x14000ea51  mov     r15, [rax+88h]
0x14000ea58  call    cs:__imp_VariantInit
0x14000ea5f  nop     dword ptr [rax+rax+00h]
0x14000ea64  movups  xmm6, xmmword ptr [rbp+330h+pvarg]
0x14000ea68  lea     rcx, [rbp+330h+var_370]; pvarg
0x14000ea6c  movsd   xmm7, qword ptr [rbp+330h+pvarg+10h]
0x14000ea71  call    cs:__imp_VariantInit
0x14000ea78  nop     dword ptr [rax+rax+00h]
0x14000ea7d  movups  xmm8, xmmword ptr [rbp+330h+var_370]
0x14000ea82  lea     rax, aS1518; "S-1-5-18"
0x14000ea89  test    rsi, rsi
0x14000ea8c  movsd   xmm9, qword ptr [rbp+330h+var_370+10h]
0x14000ea92  lea     rcx, [rbp+330h+var_2E0]; this
0x14000ea96  cmovz   rsi, rax
0x14000ea9a  mov     rdx, rsi; unsigned __int16 *
0x14000ea9d  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x14000eaa2  mov     rdi, qword ptr [rsp+430h+var_3B8]
0x14000eaa7  lea     rcx, [rbp+330h+Block]; this
0x14000eaab  mov     rdx, r14; unsigned __int16 *
0x14000eaae  movups  xmm10, xmmword ptr [rax]
0x14000eab2  movsd   xmm11, qword ptr [rax+10h]
0x14000eab8  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14000eabd  mov     rdx, [rax]
0x14000eac0  test    rdx, rdx
0x14000eac3  jz      short loc_14000EACA
0x14000eac5  mov     rdx, [rdx]
0x14000eac8  jmp     short loc_14000EACD
0x14000eaca  mov     rdx, r12
0x14000eacd  lea     rax, [rbp+330h+var_3A0]
0x14000ead1  movaps  [rbp+330h+var_340], xmm6
0x14000ead5  mov     qword ptr [rsp+430h+var_3F0], rax
0x14000eada  mov     r9d, 6
0x14000eae0  lea     rax, [rbp+330h+var_340]
0x14000eae4  movsd   [rbp+330h+var_330], xmm7
0x14000eae9  mov     [rsp+430h+var_3F8], rax
0x14000eaee  mov     r8, rdi
0x14000eaf1  lea     rax, [rbp+330h+var_320]
0x14000eaf5  mov     dword ptr [rsp+430h+var_400], 3
0x14000eafd  mov     qword ptr [rsp+430h+cbData], rax
0x14000eb02  mov     rcx, rbx
0x14000eb05  lea     rax, [rbp+330h+var_300]
0x14000eb09  movaps  [rbp+330h+var_320], xmm8
0x14000eb0e  mov     [rsp+430h+lpData], rax
0x14000eb13  mov     rax, r15
0x14000eb16  movsd   [rbp+330h+var_310], xmm9
0x14000eb1c  movaps  [rbp+330h+var_300], xmm10
0x14000eb21  movsd   [rbp+330h+var_2F0], xmm11
0x14000eb27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000eb2c  mov     rbx, [rbp+330h+Block]
0x14000eb30  mov     dword ptr [rsp+430h+Data], eax
0x14000eb34  test    rbx, rbx
0x14000eb37  jz      short loc_14000EB85
0x14000eb39  or      eax, 0FFFFFFFFh
0x14000eb3c  lock xadd [rbx+10h], eax
0x14000eb41  cmp     eax, 1
0x14000eb44  jnz     short loc_14000EB81
0x14000eb46  test    rbx, rbx
0x14000eb49  jz      short loc_14000EB81
0x14000eb4b  mov     rcx, [rbx]; bstrString
0x14000eb4e  test    rcx, rcx
0x14000eb51  jz      short loc_14000EB62
0x14000eb53  call    cs:__imp_SysFreeString
0x14000eb5a  nop     dword ptr [rax+rax+00h]
0x14000eb5f  mov     [rbx], r12
0x14000eb62  mov     rcx, [rbx+8]; Block
0x14000eb66  test    rcx, rcx
0x14000eb69  jz      short loc_14000EB74
0x14000eb6b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000eb70  mov     [rbx+8], r12
0x14000eb74  mov     edx, 18h
0x14000eb79  mov     rcx, rbx; Block
0x14000eb7c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000eb81  mov     [rbp+330h+Block], r12
0x14000eb85  lea     rcx, [rbp+330h+var_2E0]; pvarg
0x14000eb89  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000eb8e  lea     rcx, [rbp+330h+var_370]; pvarg
0x14000eb92  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000eb97  lea     rcx, [rbp+330h+pvarg]; pvarg
0x14000eb9b  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x14000eba0  mov     ebx, dword ptr [rsp+430h+Data]
0x14000eba4  test    ebx, ebx
0x14000eba6  jns     short loc_14000EBF6
0x14000eba8  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x14000ebaf  lea     rax, [rsp+430h+Data]
0x14000ebb4  mov     r9d, 4; dwType
0x14000ebba  lea     r8, a54registertask; "54RegisterTaskDefinition"
0x14000ebc1  mov     [rsp+430h+cbData], r9d; cbData
0x14000ebc6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000ebcd  mov     [rsp+430h+lpData], rax; lpData
0x14000ebd2  call    cs:__imp_RegSetKeyValueW
0x14000ebd9  nop     dword ptr [rax+rax+00h]
0x14000ebde  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x14000ebe3  mov     edx, dword ptr [rsp+430h+Data]; int
0x14000ebe7  mov     r8, r13; char *
0x14000ebea  mov     rcx, rax; this
0x14000ebed  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x14000ebf2  mov     ebx, dword ptr [rsp+430h+Data]
0x14000ebf6  lea     rcx, [rbp+330h+var_380]; this
0x14000ebfa  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x14000ebff  lea     rcx, [rbp+330h+var_3A0]
0x14000ec03  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000ec08  lea     rcx, [rbp+330h+var_398]
0x14000ec0c  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000ec11  lea     rcx, [rsp+430h+var_3B8]
0x14000ec16  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000ec1b  lea     rcx, [rbp+330h+var_3B0]
0x14000ec1f  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000ec24  lea     rcx, [rbp+330h+var_390]
0x14000ec28  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000ec2d  mov     eax, ebx
0x14000ec2f  mov     rcx, [rbp+330h+var_B0]
0x14000ec36  xor     rcx, rsp; StackCookie
0x14000ec39  call    __security_check_cookie
0x14000ec3e  lea     r11, [rsp+430h+var_38]
0x14000ec46  movaps  xmm6, xmmword ptr [r11-18h]
0x14000ec4b  movaps  xmm7, xmmword ptr [r11-28h]
0x14000ec50  movaps  xmm8, xmmword ptr [r11-38h]
0x14000ec55  movaps  xmm9, xmmword ptr [r11-48h]
0x14000ec5a  movaps  xmm10, xmmword ptr [r11-58h]
0x14000ec5f  movaps  xmm11, xmmword ptr [r11-68h]
0x14000ec64  mov     rsp, r11
0x14000ec67  pop     r15
0x14000ec69  pop     r14
0x14000ec6b  pop     r13
0x14000ec6d  pop     r12
0x14000ec6f  pop     rdi
0x14000ec70  pop     rsi
0x14000ec71  pop     rbx
0x14000ec72  pop     rbp
0x14000ec73  retn
```
