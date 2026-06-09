# ScheduleOMADMClientTaskHelper

- ea: `0x180093ae4`
- end: `0x180093e11`
- name: `ScheduleOMADMClientTaskHelper`
- size: `813`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180093a0c`

## callees

- `0x180004eb0`
- `0x18000535c`
- `0x18000ac30`
- `0x180090968`
- `0x1800909e0`
- `0x180090a34`
- `0x180090ab0`
- `0x180090ae4`
- `0x180091100`
- `0x180093ae4`
- `0x180095efc`
- `0x1800967cc`
- `0x1800bb010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180093cf1`
- `OLEAUT32!__imp_SysFreeString` at `0x180093cf1`
- `OLEAUT32!__imp_VariantInit` at `0x180093c00`
- `OLEAUT32!__imp_VariantInit` at `0x180093c19`
- `OLEAUT32!__imp_VariantInit` at `0x180093c00`
- `OLEAUT32!__imp_VariantInit` at `0x180093c19`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180093d70`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180093d70`

## string_xrefs

- `0x180093b7c`: `ScheduleOMADMClientTaskHelper`
- `0x180093d58`: `54RegisterTaskDefinition`
- `0x180093bca`: `%windir%\system32\omadmclient.exe `

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
0x180093ae4  mov     rax, rsp
0x180093ae7  push    rbp
0x180093ae8  push    rbx
0x180093ae9  push    rsi
0x180093aea  push    rdi
0x180093aeb  push    r12
0x180093aed  push    r14
0x180093aef  push    r15
0x180093af1  lea     rbp, [rax-328h]
0x180093af8  sub     rsp, 3F0h
0x180093aff  movaps  xmmword ptr [rax-48h], xmm6
0x180093b03  movaps  xmmword ptr [rax-58h], xmm7
0x180093b07  movaps  xmmword ptr [rax-68h], xmm8
0x180093b0c  movaps  xmmword ptr [rax-78h], xmm9
0x180093b11  movaps  xmmword ptr [rax-88h], xmm10
0x180093b19  movaps  xmmword ptr [rax-98h], xmm11
0x180093b21  mov     rax, cs:__security_cookie
0x180093b28  xor     rax, rsp
0x180093b2b  mov     [rbp+320h+var_A0], rax
0x180093b32  xor     r15d, r15d
0x180093b35  mov     dword ptr [rsp+420h+lpData], r9d
0x180093b3a  mov     r9, rcx
0x180093b3d  mov     [rbp+320h+var_380], r15
0x180093b41  mov     rsi, r8
0x180093b44  mov     [rbp+320h+var_3A0], r15
0x180093b48  mov     rdi, rcx
0x180093b4b  mov     [rsp+420h+var_3A8], r15
0x180093b50  lea     rcx, [rbp+320h+var_2B0]; unsigned __int16 *
0x180093b54  mov     [rbp+320h+var_388], r15
0x180093b58  lea     r8, aServeridSLooku; "/serverid \"%s\" /lookuptype 1 /initiat"...
0x180093b5f  mov     [rbp+320h+var_390], r15
0x180093b63  mov     edx, 104h; unsigned __int64
0x180093b68  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180093b6d  mov     ebx, eax
0x180093b6f  mov     dword ptr [rsp+420h+Data], eax
0x180093b73  lea     rax, [rsp+420h+Data]
0x180093b78  mov     [rbp+320h+var_368], rax
0x180093b7c  lea     r12, aScheduleomadmc; "ScheduleOMADMClientTaskHelper"
0x180093b83  mov     [rbp+320h+var_370], r12
0x180093b87  test    ebx, ebx
0x180093b89  js      loc_180093D94
0x180093b8f  mov     [rsp+420h+var_3C0], r15d
0x180093b94  lea     rax, [rbp+320h+var_2B0]
0x180093b98  mov     [rsp+420h+var_3C8], r15d
0x180093b9d  lea     r9, [rbp+320h+var_388]
0x180093ba1  mov     [rsp+420h+var_3D0], r15d
0x180093ba6  lea     r8, [rsp+420h+var_3A8]
0x180093bab  mov     [rsp+420h+var_3D8], 1
0x180093bb3  lea     rdx, [rbp+320h+var_3A0]
0x180093bb7  mov     [rsp+420h+var_3E0], r15d
0x180093bbc  lea     rcx, [rbp+320h+var_380]
0x180093bc0  mov     [rsp+420h+var_3E8], r15
0x180093bc5  mov     [rsp+420h+var_3F0], rax
0x180093bca  lea     rax, aWindirSystem32; "%windir%\\system32\\omadmclient.exe "
0x180093bd1  mov     qword ptr [rsp+420h+cbData], rax
0x180093bd6  mov     [rsp+420h+lpData], rdi
0x180093bdb  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x180093be0  mov     dword ptr [rsp+420h+Data], eax
0x180093be4  mov     ebx, eax
0x180093be6  test    eax, eax
0x180093be8  js      loc_180093D94
0x180093bee  mov     rbx, [rbp+320h+var_3A0]
0x180093bf2  lea     rcx, [rbp+320h+pvarg]; pvarg
0x180093bf6  mov     rax, [rbx]
0x180093bf9  mov     r14, [rax+88h]
0x180093c00  call    cs:__imp_VariantInit
0x180093c07  nop     dword ptr [rax+rax+00h]
0x180093c0c  movups  xmm6, xmmword ptr [rbp+320h+pvarg]
0x180093c10  lea     rcx, [rbp+320h+var_360]; pvarg
0x180093c14  movsd   xmm7, qword ptr [rbp+320h+pvarg+10h]
0x180093c19  call    cs:__imp_VariantInit
0x180093c20  nop     dword ptr [rax+rax+00h]
0x180093c25  movups  xmm8, xmmword ptr [rbp+320h+var_360]
0x180093c2a  lea     rdx, aS1518; "S-1-5-18"
0x180093c31  movsd   xmm9, qword ptr [rbp+320h+var_360+10h]
0x180093c37  lea     rcx, [rbp+320h+var_2D0]; this
0x180093c3b  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x180093c40  mov     rdi, [rsp+420h+var_3A8]
0x180093c45  lea     rcx, [rbp+320h+Block]; this
0x180093c49  mov     rdx, rsi; unsigned __int16 *
0x180093c4c  movups  xmm10, xmmword ptr [rax]
0x180093c50  movsd   xmm11, qword ptr [rax+10h]
0x180093c56  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180093c5b  mov     rdx, [rax]
0x180093c5e  test    rdx, rdx
0x180093c61  jz      short loc_180093C68
0x180093c63  mov     rdx, [rdx]
0x180093c66  jmp     short loc_180093C6B
0x180093c68  mov     rdx, r15
0x180093c6b  lea     rax, [rbp+320h+var_390]
0x180093c6f  movaps  [rbp+320h+var_330], xmm6
0x180093c73  mov     qword ptr [rsp+420h+var_3E0], rax
0x180093c78  mov     r9d, 6
0x180093c7e  lea     rax, [rbp+320h+var_330]
0x180093c82  movsd   [rbp+320h+var_320], xmm7
0x180093c87  mov     [rsp+420h+var_3E8], rax
0x180093c8c  mov     r8, rdi
0x180093c8f  lea     rax, [rbp+320h+var_310]
0x180093c93  mov     dword ptr [rsp+420h+var_3F0], 3
0x180093c9b  mov     qword ptr [rsp+420h+cbData], rax
0x180093ca0  mov     rcx, rbx
0x180093ca3  lea     rax, [rbp+320h+var_2F0]
0x180093ca7  movaps  [rbp+320h+var_310], xmm8
0x180093cac  mov     [rsp+420h+lpData], rax
0x180093cb1  mov     rax, r14
0x180093cb4  movsd   [rbp+320h+var_300], xmm9
0x180093cba  movaps  [rbp+320h+var_2F0], xmm10
0x180093cbf  movsd   [rbp+320h+var_2E0], xmm11
0x180093cc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093cca  mov     rbx, [rbp+320h+Block]
0x180093cce  mov     dword ptr [rsp+420h+Data], eax
0x180093cd2  test    rbx, rbx
0x180093cd5  jz      short loc_180093D23
0x180093cd7  or      eax, 0FFFFFFFFh
0x180093cda  lock xadd [rbx+10h], eax
0x180093cdf  cmp     eax, 1
0x180093ce2  jnz     short loc_180093D1F
0x180093ce4  test    rbx, rbx
0x180093ce7  jz      short loc_180093D1F
0x180093ce9  mov     rcx, [rbx]; bstrString
0x180093cec  test    rcx, rcx
0x180093cef  jz      short loc_180093D00
0x180093cf1  call    cs:__imp_SysFreeString
0x180093cf8  nop     dword ptr [rax+rax+00h]
0x180093cfd  mov     [rbx], r15
0x180093d00  mov     rcx, [rbx+8]; Block
0x180093d04  test    rcx, rcx
0x180093d07  jz      short loc_180093D12
0x180093d09  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180093d0e  mov     [rbx+8], r15
0x180093d12  mov     edx, 18h
0x180093d17  mov     rcx, rbx; Block
0x180093d1a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180093d1f  mov     [rbp+320h+Block], r15
0x180093d23  lea     rcx, [rbp+320h+var_2D0]; this
0x180093d27  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180093d2c  lea     rcx, [rbp+320h+var_360]; this
0x180093d30  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180093d35  lea     rcx, [rbp+320h+pvarg]; this
0x180093d39  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180093d3e  mov     ebx, dword ptr [rsp+420h+Data]
0x180093d42  test    ebx, ebx
0x180093d44  jns     short loc_180093D94
0x180093d46  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x180093d4d  lea     rax, [rsp+420h+Data]
0x180093d52  mov     r9d, 4; dwType
0x180093d58  lea     r8, a54registertask; "54RegisterTaskDefinition"
0x180093d5f  mov     [rsp+420h+cbData], r9d; cbData
0x180093d64  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180093d6b  mov     [rsp+420h+lpData], rax; lpData
0x180093d70  call    cs:__imp_RegSetKeyValueW
0x180093d77  nop     dword ptr [rax+rax+00h]
0x180093d7c  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180093d81  mov     edx, dword ptr [rsp+420h+Data]; int
0x180093d85  mov     r8, r12; char *
0x180093d88  mov     rcx, rax; this
0x180093d8b  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x180093d90  mov     ebx, dword ptr [rsp+420h+Data]
0x180093d94  lea     rcx, [rbp+320h+var_370]; this
0x180093d98  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x180093d9d  lea     rcx, [rbp+320h+var_390]
0x180093da1  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x180093da6  lea     rcx, [rbp+320h+var_388]
0x180093daa  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x180093daf  lea     rcx, [rsp+420h+var_3A8]
0x180093db4  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x180093db9  lea     rcx, [rbp+320h+var_3A0]
0x180093dbd  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x180093dc2  lea     rcx, [rbp+320h+var_380]
0x180093dc6  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x180093dcb  mov     eax, ebx
0x180093dcd  mov     rcx, [rbp+320h+var_A0]
0x180093dd4  xor     rcx, rsp; StackCookie
0x180093dd7  call    __security_check_cookie
0x180093ddc  lea     r11, [rsp+420h+var_30]
0x180093de4  movaps  xmm6, xmmword ptr [r11-10h]
0x180093de9  movaps  xmm7, xmmword ptr [r11-20h]
0x180093dee  movaps  xmm8, xmmword ptr [r11-30h]
0x180093df3  movaps  xmm9, xmmword ptr [r11-40h]
0x180093df8  movaps  xmm10, xmmword ptr [r11-50h]
0x180093dfd  movaps  xmm11, xmmword ptr [r11-60h]
0x180093e02  mov     rsp, r11
0x180093e05  pop     r15
0x180093e07  pop     r14
0x180093e09  pop     r12
0x180093e0b  pop     rdi
0x180093e0c  pop     rsi
0x180093e0d  pop     rbx
0x180093e0e  pop     rbp
0x180093e0f  retn
```
