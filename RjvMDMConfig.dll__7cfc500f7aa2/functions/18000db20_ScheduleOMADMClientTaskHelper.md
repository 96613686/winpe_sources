# ScheduleOMADMClientTaskHelper

- ea: `0x18000db20`
- end: `0x18000de61`
- name: `ScheduleOMADMClientTaskHelper`
- size: `833`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

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
- `0x18000db20`
- `0x18001b9d8`
- `0x18001bde0`
- `0x18001e010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000dd3f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dd3f`
- `OLEAUT32!__imp_VariantInit` at `0x18000dc44`
- `OLEAUT32!__imp_VariantInit` at `0x18000dc5d`
- `OLEAUT32!__imp_VariantInit` at `0x18000dc44`
- `OLEAUT32!__imp_VariantInit` at `0x18000dc5d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18000ddbe`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18000ddbe`

## string_xrefs

- `0x18000dbc0`: `ScheduleOMADMClientTaskHelper`
- `0x18000dc0e`: `%windir%\system32\omadmclient.exe `
- `0x18000dda6`: `54RegisterTaskDefinition`

## pseudocode

```c
__int64 __fastcall ScheduleOMADMClientTaskHelper(
        __int64 a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
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
  const struct std::nothrow_t *v21; // rdx
  BSTR *v22; // rbx
  BSTR v23; // rcx
  CEnrollmentLogger *Logger; // rax
  int v27; // [rsp+48h] [rbp-C0h]
  int v28; // [rsp+50h] [rbp-B8h]
  int v29; // [rsp+58h] [rbp-B0h]
  int v30; // [rsp+60h] [rbp-A8h]
  int v31; // [rsp+68h] [rbp-A0h]
  __int64 Data; // [rsp+78h] [rbp-90h] BYREF
  __int64 v33; // [rsp+80h] [rbp-88h] BYREF
  __int64 v34; // [rsp+88h] [rbp-80h] BYREF
  void *v35; // [rsp+90h] [rbp-78h] BYREF
  __int64 v36; // [rsp+98h] [rbp-70h] BYREF
  __int64 v37; // [rsp+A0h] [rbp-68h] BYREF
  _QWORD v38[2]; // [rsp+A8h] [rbp-60h] BYREF
  _QWORD v39[2]; // [rsp+B8h] [rbp-50h] BYREF
  VARIANTARG v40; // [rsp+C8h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+E0h] [rbp-28h] BYREF
  __int128 v42; // [rsp+F8h] [rbp-10h] BYREF
  IRecordInfo *v43; // [rsp+108h] [rbp+0h]
  __int128 v44; // [rsp+118h] [rbp+10h] BYREF
  IRecordInfo *v45; // [rsp+128h] [rbp+20h]
  __int128 v46; // [rsp+138h] [rbp+30h] BYREF
  __int64 v47; // [rsp+148h] [rbp+40h]
  _BYTE v48[32]; // [rsp+158h] [rbp+50h] BYREF
  unsigned __int16 v49[264]; // [rsp+178h] [rbp+70h] BYREF

  v38[0] = 0;
  v34 = 0;
  v33 = 0;
  v37 = 0;
  v36 = 0;
  v7 = StringCchPrintfW(v49, 0x104u, L"/serverid \"%s\" /lookuptype 1 /initiator %d ", a1, a4);
  LODWORD(Data) = v7;
  v39[1] = &Data;
  v39[0] = "ScheduleOMADMClientTaskHelper";
  if ( v7 >= 0 )
  {
    v31 = 0;
    v30 = 0;
    v29 = 0;
    v28 = 1;
    v27 = 0;
    LODWORD(Data) = CreateTask(
                      v38,
                      &v34,
                      &v33,
                      &v37,
                      a1,
                      L"%windir%\\system32\\omadmclient.exe ",
                      v49,
                      a2,
                      v27,
                      v28,
                      v29,
                      v30,
                      v31);
    v7 = Data;
    if ( (int)Data >= 0 )
    {
      v8 = v34;
      v9 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))(*(_QWORD *)v34 + 136LL);
      VariantInit(&pvarg);
      v10 = *(_OWORD *)&pvarg.vt;
      pRecInfo = pvarg.pRecInfo;
      VariantInit(&v40);
      v12 = *(_OWORD *)&v40.vt;
      v13 = v40.pRecInfo;
      if ( !a2 )
        a2 = L"S-1-5-18";
      v14 = _variant_t::_variant_t((_variant_t *)v48, a2);
      v15 = v33;
      v16 = *(_OWORD *)v14;
      v17 = *((_QWORD *)v14 + 2);
      v18 = _bstr_t::_bstr_t((_bstr_t *)&v35, a3);
      if ( *(_QWORD *)v18 )
        v19 = **(_QWORD **)v18;
      else
        v19 = 0;
      v42 = v10;
      v43 = pRecInfo;
      v44 = v12;
      v45 = v13;
      v46 = v16;
      v47 = v17;
      v20 = v9(v8, v19, v15, 6, &v46, &v44, 3, &v42, &v36);
      v22 = (BSTR *)v35;
      LODWORD(Data) = v20;
      if ( v35 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v35 + 4, 0xFFFFFFFF) == 1 && v22 )
        {
          if ( *v22 )
          {
            SysFreeString(*v22);
            *v22 = 0;
          }
          v23 = v22[1];
          if ( v23 )
          {
            operator delete(v23, v21);
            v22[1] = 0;
          }
          operator delete(v22, (const struct std::nothrow_t *)0x18);
        }
        v35 = 0;
      }
      _variant_t::~_variant_t((_variant_t *)v48);
      _variant_t::~_variant_t((_variant_t *)&v40);
      _variant_t::~_variant_t((_variant_t *)&pvarg);
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
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v39);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v36);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v37);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v33);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v34);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(v38);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000db20  mov     rax, rsp
0x18000db23  push    rbp
0x18000db24  push    rbx
0x18000db25  push    rsi
0x18000db26  push    rdi
0x18000db27  push    r12
0x18000db29  push    r13
0x18000db2b  push    r14
0x18000db2d  push    r15
0x18000db2f  lea     rbp, [rax-338h]
0x18000db36  sub     rsp, 3F8h
0x18000db3d  movaps  xmmword ptr [rax-58h], xmm6
0x18000db41  movaps  xmmword ptr [rax-68h], xmm7
0x18000db45  movaps  xmmword ptr [rax-78h], xmm8
0x18000db4a  movaps  xmmword ptr [rax-88h], xmm9
0x18000db52  movaps  xmmword ptr [rax-98h], xmm10
0x18000db5a  movaps  xmmword ptr [rax-0A8h], xmm11
0x18000db62  mov     rax, cs:__security_cookie
0x18000db69  xor     rax, rsp
0x18000db6c  mov     [rbp+330h+var_B0], rax
0x18000db73  xor     r12d, r12d
0x18000db76  mov     dword ptr [rsp+430h+lpData], r9d
0x18000db7b  mov     r9, rcx
0x18000db7e  mov     [rbp+330h+var_390], r12
0x18000db82  mov     r14, r8
0x18000db85  mov     [rbp+330h+var_3B0], r12
0x18000db89  mov     rsi, rdx
0x18000db8c  mov     [rsp+430h+var_3B8], r12
0x18000db91  mov     rdi, rcx
0x18000db94  mov     [rbp+330h+var_398], r12
0x18000db98  lea     rcx, [rbp+330h+var_2C0]; unsigned __int16 *
0x18000db9c  mov     [rbp+330h+var_3A0], r12
0x18000dba0  lea     r8, aServeridSLooku; "/serverid \"%s\" /lookuptype 1 /initiat"...
0x18000dba7  mov     edx, 104h; unsigned __int64
0x18000dbac  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000dbb1  mov     ebx, eax
0x18000dbb3  mov     dword ptr [rsp+430h+Data], eax
0x18000dbb7  lea     rax, [rsp+430h+Data]
0x18000dbbc  mov     [rbp+330h+var_378], rax
0x18000dbc0  lea     r13, aScheduleomadmc; "ScheduleOMADMClientTaskHelper"
0x18000dbc7  mov     [rbp+330h+var_380], r13
0x18000dbcb  test    ebx, ebx
0x18000dbcd  js      loc_18000DDE2
0x18000dbd3  mov     [rsp+430h+var_3D0], r12d
0x18000dbd8  lea     rax, [rbp+330h+var_2C0]
0x18000dbdc  mov     [rsp+430h+var_3D8], r12d
0x18000dbe1  lea     r9, [rbp+330h+var_398]
0x18000dbe5  mov     [rsp+430h+var_3E0], r12d
0x18000dbea  lea     r8, [rsp+430h+var_3B8]
0x18000dbef  mov     [rsp+430h+var_3E8], 1
0x18000dbf7  lea     rdx, [rbp+330h+var_3B0]
0x18000dbfb  mov     [rsp+430h+var_3F0], r12d
0x18000dc00  lea     rcx, [rbp+330h+var_390]
0x18000dc04  mov     [rsp+430h+var_3F8], rsi
0x18000dc09  mov     [rsp+430h+var_400], rax
0x18000dc0e  lea     rax, aWindirSystem32; "%windir%\\system32\\omadmclient.exe "
0x18000dc15  mov     qword ptr [rsp+430h+cbData], rax
0x18000dc1a  mov     [rsp+430h+lpData], rdi
0x18000dc1f  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x18000dc24  mov     dword ptr [rsp+430h+Data], eax
0x18000dc28  mov     ebx, eax
0x18000dc2a  test    eax, eax
0x18000dc2c  js      loc_18000DDE2
0x18000dc32  mov     rbx, [rbp+330h+var_3B0]
0x18000dc36  lea     rcx, [rbp+330h+pvarg]; pvarg
0x18000dc3a  mov     rax, [rbx]
0x18000dc3d  mov     r15, [rax+88h]
0x18000dc44  call    cs:__imp_VariantInit
0x18000dc4b  nop     dword ptr [rax+rax+00h]
0x18000dc50  movups  xmm6, xmmword ptr [rbp+330h+pvarg]
0x18000dc54  lea     rcx, [rbp+330h+var_370]; pvarg
0x18000dc58  movsd   xmm7, qword ptr [rbp+330h+pvarg+10h]
0x18000dc5d  call    cs:__imp_VariantInit
0x18000dc64  nop     dword ptr [rax+rax+00h]
0x18000dc69  movups  xmm8, xmmword ptr [rbp+330h+var_370]
0x18000dc6e  lea     rax, aS1518; "S-1-5-18"
0x18000dc75  test    rsi, rsi
0x18000dc78  movsd   xmm9, qword ptr [rbp+330h+var_370+10h]
0x18000dc7e  lea     rcx, [rbp+330h+var_2E0]; this
0x18000dc82  cmovz   rsi, rax
0x18000dc86  mov     rdx, rsi; unsigned __int16 *
0x18000dc89  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x18000dc8e  mov     rdi, [rsp+430h+var_3B8]
0x18000dc93  lea     rcx, [rbp+330h+var_3A8]; this
0x18000dc97  mov     rdx, r14; unsigned __int16 *
0x18000dc9a  movups  xmm10, xmmword ptr [rax]
0x18000dc9e  movsd   xmm11, qword ptr [rax+10h]
0x18000dca4  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000dca9  mov     rdx, [rax]
0x18000dcac  test    rdx, rdx
0x18000dcaf  jz      short loc_18000DCB6
0x18000dcb1  mov     rdx, [rdx]
0x18000dcb4  jmp     short loc_18000DCB9
0x18000dcb6  mov     rdx, r12
0x18000dcb9  lea     rax, [rbp+330h+var_3A0]
0x18000dcbd  movaps  [rbp+330h+var_340], xmm6
0x18000dcc1  mov     qword ptr [rsp+430h+var_3F0], rax
0x18000dcc6  mov     r9d, 6
0x18000dccc  lea     rax, [rbp+330h+var_340]
0x18000dcd0  movsd   [rbp+330h+var_330], xmm7
0x18000dcd5  mov     [rsp+430h+var_3F8], rax
0x18000dcda  mov     r8, rdi
0x18000dcdd  lea     rax, [rbp+330h+var_320]
0x18000dce1  mov     dword ptr [rsp+430h+var_400], 3
0x18000dce9  mov     qword ptr [rsp+430h+cbData], rax
0x18000dcee  mov     rcx, rbx
0x18000dcf1  lea     rax, [rbp+330h+var_300]
0x18000dcf5  movaps  [rbp+330h+var_320], xmm8
0x18000dcfa  mov     [rsp+430h+lpData], rax
0x18000dcff  mov     rax, r15
0x18000dd02  movsd   [rbp+330h+var_310], xmm9
0x18000dd08  movaps  [rbp+330h+var_300], xmm10
0x18000dd0d  movsd   [rbp+330h+var_2F0], xmm11
0x18000dd13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd18  mov     rbx, [rbp+330h+var_3A8]
0x18000dd1c  mov     dword ptr [rsp+430h+Data], eax
0x18000dd20  test    rbx, rbx
0x18000dd23  jz      short loc_18000DD71
0x18000dd25  or      eax, 0FFFFFFFFh
0x18000dd28  lock xadd [rbx+10h], eax
0x18000dd2d  cmp     eax, 1
0x18000dd30  jnz     short loc_18000DD6D
0x18000dd32  test    rbx, rbx
0x18000dd35  jz      short loc_18000DD6D
0x18000dd37  mov     rcx, [rbx]; bstrString
0x18000dd3a  test    rcx, rcx
0x18000dd3d  jz      short loc_18000DD4E
0x18000dd3f  call    cs:__imp_SysFreeString
0x18000dd46  nop     dword ptr [rax+rax+00h]
0x18000dd4b  mov     [rbx], r12
0x18000dd4e  mov     rcx, [rbx+8]; void *
0x18000dd52  test    rcx, rcx
0x18000dd55  jz      short loc_18000DD60
0x18000dd57  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000dd5c  mov     [rbx+8], r12
0x18000dd60  mov     edx, 18h; struct std::nothrow_t *
0x18000dd65  mov     rcx, rbx; void *
0x18000dd68  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000dd6d  mov     [rbp+330h+var_3A8], r12
0x18000dd71  lea     rcx, [rbp+330h+var_2E0]; this
0x18000dd75  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18000dd7a  lea     rcx, [rbp+330h+var_370]; this
0x18000dd7e  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18000dd83  lea     rcx, [rbp+330h+pvarg]; this
0x18000dd87  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18000dd8c  mov     ebx, dword ptr [rsp+430h+Data]
0x18000dd90  test    ebx, ebx
0x18000dd92  jns     short loc_18000DDE2
0x18000dd94  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x18000dd9b  lea     rax, [rsp+430h+Data]
0x18000dda0  mov     r9d, 4; dwType
0x18000dda6  lea     r8, a54registertask; "54RegisterTaskDefinition"
0x18000ddad  mov     [rsp+430h+cbData], r9d; cbData
0x18000ddb2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ddb9  mov     [rsp+430h+lpData], rax; lpData
0x18000ddbe  call    cs:__imp_RegSetKeyValueW
0x18000ddc5  nop     dword ptr [rax+rax+00h]
0x18000ddca  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18000ddcf  mov     edx, dword ptr [rsp+430h+Data]; int
0x18000ddd3  mov     r8, r13; char *
0x18000ddd6  mov     rcx, rax; this
0x18000ddd9  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x18000ddde  mov     ebx, dword ptr [rsp+430h+Data]
0x18000dde2  lea     rcx, [rbp+330h+var_380]; this
0x18000dde6  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18000ddeb  lea     rcx, [rbp+330h+var_3A0]
0x18000ddef  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18000ddf4  lea     rcx, [rbp+330h+var_398]
0x18000ddf8  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18000ddfd  lea     rcx, [rsp+430h+var_3B8]
0x18000de02  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18000de07  lea     rcx, [rbp+330h+var_3B0]
0x18000de0b  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18000de10  lea     rcx, [rbp+330h+var_390]
0x18000de14  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18000de19  mov     eax, ebx
0x18000de1b  mov     rcx, [rbp+330h+var_B0]
0x18000de22  xor     rcx, rsp; StackCookie
0x18000de25  call    __security_check_cookie
0x18000de2a  lea     r11, [rsp+430h+var_38]
0x18000de32  movaps  xmm6, xmmword ptr [r11-18h]
0x18000de37  movaps  xmm7, xmmword ptr [r11-28h]
0x18000de3c  movaps  xmm8, xmmword ptr [r11-38h]
0x18000de41  movaps  xmm9, xmmword ptr [r11-48h]
0x18000de46  movaps  xmm10, xmmword ptr [r11-58h]
0x18000de4b  movaps  xmm11, xmmword ptr [r11-68h]
0x18000de50  mov     rsp, r11
0x18000de53  pop     r15
0x18000de55  pop     r14
0x18000de57  pop     r13
0x18000de59  pop     r12
0x18000de5b  pop     rdi
0x18000de5c  pop     rsi
0x18000de5d  pop     rbx
0x18000de5e  pop     rbp
0x18000de5f  retn
```
