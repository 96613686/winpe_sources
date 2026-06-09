# CPITRBase::GetPITRTask(ITaskFolder * *,IRegisteredTask * *)

- ea: `0x18000f08c`
- end: `0x18000f504`
- name: `?GetPITRTask@CPITRBase@@IEAAJPEAPEAUITaskFolder@@PEAPEAUIRegisteredTask@@@Z`
- size: `1144`
- prototype: `__int64 __fastcall(CPITRBase *__hidden this, struct ITaskFolder **, struct IRegisteredTask **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180015ad0`

## callees

- `0x180005c20`
- `0x180006d1c`
- `0x180009e04`
- `0x18000f08c`
- `0x18003a784`
- `0x180050300`
- `0x180053010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000f1a3`
- `OLEAUT32!__imp_VariantInit` at `0x18000f1b9`
- `OLEAUT32!__imp_VariantInit` at `0x18000f1cf`
- `OLEAUT32!__imp_VariantInit` at `0x18000f1e4`
- `OLEAUT32!__imp_VariantInit` at `0x18000f1a3`
- `OLEAUT32!__imp_VariantInit` at `0x18000f1b9`
- `OLEAUT32!__imp_VariantInit` at `0x18000f1cf`
- `OLEAUT32!__imp_VariantInit` at `0x18000f1e4`
- `OLEAUT32!__imp_VariantClear` at `0x18000f246`
- `OLEAUT32!__imp_VariantClear` at `0x18000f258`
- `OLEAUT32!__imp_VariantClear` at `0x18000f26a`
- `OLEAUT32!__imp_VariantClear` at `0x18000f27c`
- `OLEAUT32!__imp_VariantClear` at `0x18000f246`
- `OLEAUT32!__imp_VariantClear` at `0x18000f258`
- `OLEAUT32!__imp_VariantClear` at `0x18000f26a`
- `OLEAUT32!__imp_VariantClear` at `0x18000f27c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f122`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f28e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f338`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f3e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f122`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f28e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f338`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f3e2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000f116`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000f116`
- `WDSCORE!CurrentIP` at `0x18000f12a`
- `WDSCORE!CurrentIP` at `0x18000f296`
- `WDSCORE!CurrentIP` at `0x18000f340`
- `WDSCORE!CurrentIP` at `0x18000f3ea`
- `WDSCORE!CurrentIP` at `0x18000f12a`
- `WDSCORE!CurrentIP` at `0x18000f296`
- `WDSCORE!CurrentIP` at `0x18000f340`
- `WDSCORE!CurrentIP` at `0x18000f3ea`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000f189`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000f189`

## string_xrefs

- `0x18000f166`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x18000f2d2`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x18000f37c`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x18000f426`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x18000f15a`: `CPITRBase::GetPITRTask`
- `0x18000f2c6`: `CPITRBase::GetPITRTask`
- `0x18000f370`: `CPITRBase::GetPITRTask`
- `0x18000f41a`: `CPITRBase::GetPITRTask`
- `0x18000f136`: `CPITRBase::GetPITRTask: Failed to instantiate task scheduler. Error: 0x%08X`
- `0x18000f2a2`: `CPITRBase::GetPITRTask: Failed to connect to task scheduler. Error: 0x%08X`
- `0x18000f34c`: `CPITRBase::GetPITRTask: Failed to get tasks root folder. Error: 0x%08X`
- `0x18000f3a0`: `Microsoft\Windows\Setup\PITRTask`
- `0x18000f3f6`: `CPITRBase::GetPITRTask: Failed to get PITR task. Error: 0x%08X`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CPITRBase::GetPITRTask(CPITRBase *this, struct ITaskFolder **a2, struct IRegisteredTask **a3)
{
  HRESULT v5; // esi
  DWORD v6; // edi
  __int64 v7; // rbx
  struct tagLOG_PARTIAL_MSG *v8; // rax
  __int64 (__fastcall *v9)(LPVOID, __int128 *, __int128 *, __int128 *, __int128 *); // rbx
  __int128 v10; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v12; // xmm8
  IRecordInfo *v13; // xmm9_8
  __int128 v14; // xmm6
  IRecordInfo *v15; // xmm7_8
  HRESULT v16; // eax
  HRESULT v17; // eax
  HRESULT v18; // eax
  HRESULT v19; // eax
  DWORD v20; // edi
  __int64 v21; // rbx
  struct tagLOG_PARTIAL_MSG *v22; // rax
  __int64 (__fastcall *v23)(LPVOID, __int64, struct ITaskFolder **); // rbx
  _bstr_t *v24; // rax
  __int64 v25; // rdx
  DWORD v26; // edi
  __int64 v27; // rbx
  struct tagLOG_PARTIAL_MSG *v28; // rax
  HRESULT (__stdcall *GetTask)(ITaskFolder *, BSTR, IRegisteredTask **); // rbx
  _bstr_t *v30; // rax
  __int64 v31; // rdx
  DWORD LastError; // edi
  __int64 v33; // rbx
  struct tagLOG_PARTIAL_MSG *v34; // rax
  VARIANTARG v36; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v37; // [rsp+80h] [rbp-88h]
  VARIANTARG v38; // [rsp+88h] [rbp-80h] BYREF
  VARIANTARG v39; // [rsp+A0h] [rbp-68h] BYREF
  VARIANTARG pvarg; // [rsp+B8h] [rbp-50h] BYREF
  __int128 v41; // [rsp+D8h] [rbp-30h] BYREF
  IRecordInfo *v42; // [rsp+E8h] [rbp-20h]
  __int128 v43; // [rsp+F8h] [rbp-10h] BYREF
  IRecordInfo *v44; // [rsp+108h] [rbp+0h]
  __int128 v45; // [rsp+118h] [rbp+10h] BYREF
  IRecordInfo *v46; // [rsp+128h] [rbp+20h]
  __int128 v47; // [rsp+138h] [rbp+30h] BYREF
  __int64 v48; // [rsp+148h] [rbp+40h]
  struct ITaskFolder *v49; // [rsp+158h] [rbp+50h] BYREF
  LPVOID ppv; // [rsp+160h] [rbp+58h] BYREF
  struct IRegisteredTask *v51; // [rsp+168h] [rbp+60h] BYREF

  ppv = 0;
  v49 = 0;
  v51 = 0;
  if ( a3 )
  {
    v5 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &ppv);
    if ( v5 >= 0 )
    {
      v9 = *(__int64 (__fastcall **)(LPVOID, __int128 *, __int128 *, __int128 *, __int128 *))(*(_QWORD *)ppv + 80LL);
      VariantInit(&pvarg);
      v10 = *(_OWORD *)&pvarg.vt;
      pRecInfo = pvarg.pRecInfo;
      VariantInit(&v39);
      v12 = *(_OWORD *)&v39.vt;
      v13 = v39.pRecInfo;
      VariantInit(&v38);
      v14 = *(_OWORD *)&v38.vt;
      v15 = v38.pRecInfo;
      VariantInit((VARIANTARG *)&v36.decVal.8);
      v41 = v10;
      v42 = pRecInfo;
      v43 = v12;
      v44 = v13;
      v45 = v14;
      v46 = v15;
      v47 = *(_OWORD *)&v36.decVal.Lo32;
      v48 = v37;
      v5 = v9(ppv, &v47, &v45, &v43, &v41);
      v16 = VariantClear((VARIANTARG *)&v36.decVal.8);
      if ( v16 < 0 )
        _com_issue_error(v16);
      v17 = VariantClear(&v38);
      if ( v17 < 0 )
        _com_issue_error(v17);
      v18 = VariantClear(&v39);
      if ( v18 < 0 )
        _com_issue_error(v18);
      v19 = VariantClear(&pvarg);
      if ( v19 < 0 )
        _com_issue_error(v19);
      if ( v5 >= 0 )
      {
        v23 = *(__int64 (__fastcall **)(LPVOID, __int64, struct ITaskFolder **))(*(_QWORD *)ppv + 56LL);
        v24 = _bstr_t::_bstr_t((_bstr_t *)&v36, L"\\");
        if ( *(_QWORD *)v24 )
          v25 = **(_QWORD **)v24;
        else
          v25 = 0;
        v5 = v23(ppv, v25, &v49);
        _bstr_t::~_bstr_t((_bstr_t *)&v36);
        if ( v5 >= 0 )
        {
          GetTask = v49->lpVtbl->GetTask;
          v30 = _bstr_t::_bstr_t((_bstr_t *)&v36, L"Microsoft\\Windows\\Setup\\PITRTask");
          if ( *(_QWORD *)v30 )
            v31 = **(_QWORD **)v30;
          else
            v31 = 0;
          v5 = ((__int64 (__fastcall *)(struct ITaskFolder *, __int64, struct IRegisteredTask **))GetTask)(
                 v49,
                 v31,
                 &v51);
          _bstr_t::~_bstr_t((_bstr_t *)&v36);
          if ( v5 >= 0 )
          {
            if ( a2 )
            {
              *a2 = v49;
              v49 = 0;
            }
            *a3 = v51;
            v51 = 0;
          }
          else
          {
            LastError = GetLastError();
            v33 = CurrentIP();
            v34 = ConstructPartialMsgW(0x2000000u, "CPITRBase::GetPITRTask: Failed to get PITR task. Error: 0x%08X", v5);
            WdsSetupLogMessageW(
              v34,
              0,
              L"D",
              0,
              3359,
              L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
              L"CPITRBase::GetPITRTask",
              v33,
              LastError,
              0,
              0);
          }
        }
        else
        {
          v26 = GetLastError();
          v27 = CurrentIP();
          v28 = ConstructPartialMsgW(
                  0x2000000u,
                  "CPITRBase::GetPITRTask: Failed to get tasks root folder. Error: 0x%08X",
                  v5);
          WdsSetupLogMessageW(
            v28,
            0,
            L"D",
            0,
            3353,
            L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
            L"CPITRBase::GetPITRTask",
            v27,
            v26,
            0,
            0);
        }
      }
      else
      {
        v20 = GetLastError();
        v21 = CurrentIP();
        v22 = ConstructPartialMsgW(
                0x2000000u,
                "CPITRBase::GetPITRTask: Failed to connect to task scheduler. Error: 0x%08X",
                v5);
        WdsSetupLogMessageW(
          v22,
          0,
          L"D",
          0,
          3347,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"CPITRBase::GetPITRTask",
          v21,
          v20,
          0,
          0);
      }
    }
    else
    {
      v6 = GetLastError();
      v7 = CurrentIP();
      v8 = ConstructPartialMsgW(
             0x2000000u,
             "CPITRBase::GetPITRTask: Failed to instantiate task scheduler. Error: 0x%08X",
             v5);
      WdsSetupLogMessageW(
        v8,
        0,
        L"D",
        0,
        3341,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
        L"CPITRBase::GetPITRTask",
        v7,
        v6,
        0,
        0);
    }
    if ( v51 )
    {
      ((void (__fastcall *)(struct IRegisteredTask *))v51->lpVtbl->Release)(v51);
      v51 = 0;
    }
    if ( v49 )
    {
      ((void (__fastcall *)(struct ITaskFolder *))v49->lpVtbl->Release)(v49);
      v49 = 0;
    }
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000f08c  mov     rax, rsp
0x18000f08f  mov     [rax+8], rbx
0x18000f093  push    rbp
0x18000f094  push    rsi
0x18000f095  push    rdi
0x18000f096  push    r14
0x18000f098  push    r15
0x18000f09a  lea     rbp, [rax-0F8h]
0x18000f0a1  sub     rsp, 1D0h
0x18000f0a8  movaps  xmmword ptr [rax-38h], xmm6
0x18000f0ac  movaps  xmmword ptr [rax-48h], xmm7
0x18000f0b0  movaps  xmmword ptr [rax-58h], xmm8
0x18000f0b5  movaps  xmmword ptr [rax-68h], xmm9
0x18000f0ba  movaps  xmmword ptr [rax-78h], xmm10
0x18000f0bf  movaps  xmmword ptr [rax-88h], xmm11
0x18000f0c7  mov     rax, cs:__security_cookie
0x18000f0ce  xor     rax, rsp
0x18000f0d1  mov     [rbp+0F0h+var_88], rax
0x18000f0d5  mov     r14, r8
0x18000f0d8  mov     rdi, rdx
0x18000f0db  xor     r15d, r15d
0x18000f0de  mov     [rbp+0F0h+var_98], r15
0x18000f0e2  mov     [rbp+0F0h+var_A0], r15
0x18000f0e6  mov     [rbp+0F0h+var_90], r15
0x18000f0ea  test    r8, r8
0x18000f0ed  jnz     short loc_18000F0F9
0x18000f0ef  mov     esi, 80070057h
0x18000f0f4  jmp     loc_18000F4A1
0x18000f0f9  lea     rax, [rbp+0F0h+var_98]
0x18000f0fd  mov     [rsp+1F0h+ppv], rax; ppv
0x18000f102  lea     r9, IID_ITaskService; riid
0x18000f109  xor     edx, edx; pUnkOuter
0x18000f10b  lea     r8d, [rdx+1]; dwClsContext
0x18000f10f  lea     rcx, CLSID_TaskScheduler; rclsid
0x18000f116  call    cs:__imp_CoCreateInstance
0x18000f11c  mov     esi, eax
0x18000f11e  test    eax, eax
0x18000f120  jns     short loc_18000F194
0x18000f122  call    cs:__imp_GetLastError
0x18000f128  mov     edi, eax
0x18000f12a  call    cs:__imp_CurrentIP
0x18000f130  mov     rbx, rax
0x18000f133  mov     r8d, esi
0x18000f136  lea     rdx, aCpitrbaseGetpi_2; "CPITRBase::GetPITRTask: Failed to insta"...
0x18000f13d  mov     ecx, 2000000h; unsigned int
0x18000f142  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000f147  mov     [rsp+1F0h+var_1A0], r15d
0x18000f14c  mov     qword ptr [rsp+1F0h+var_1A8], r15
0x18000f151  mov     dword ptr [rsp+1F0h+var_1B0], edi
0x18000f155  mov     qword ptr [rsp+1F0h+var_1B8], rbx
0x18000f15a  lea     rcx, aCpitrbaseGetpi_3; "CPITRBase::GetPITRTask"
0x18000f161  mov     [rsp+1F0h+var_1C0], rcx
0x18000f166  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x18000f16d  mov     [rsp+1F0h+var_1C8], rcx
0x18000f172  mov     dword ptr [rsp+1F0h+ppv], 0D0Dh
0x18000f17a  xor     r9d, r9d
0x18000f17d  lea     r8, aD; "D"
0x18000f184  xor     edx, edx
0x18000f186  mov     rcx, rax
0x18000f189  call    cs:__imp_WdsSetupLogMessageW
0x18000f18f  jmp     loc_18000F45A
0x18000f194  mov     rax, [rbp+0F0h+var_98]
0x18000f198  mov     rcx, [rax]
0x18000f19b  mov     rbx, [rcx+50h]
0x18000f19f  lea     rcx, [rbp+0F0h+pvarg]; pvarg
0x18000f1a3  call    cs:__imp_VariantInit
0x18000f1a9  nop
0x18000f1aa  movups  xmm10, xmmword ptr [rbp+0F0h+pvarg]
0x18000f1af  movsd   xmm11, qword ptr [rbp+0F0h+pvarg+10h]
0x18000f1b5  lea     rcx, [rbp+0F0h+var_158]; pvarg
0x18000f1b9  call    cs:__imp_VariantInit
0x18000f1bf  nop
0x18000f1c0  movups  xmm8, xmmword ptr [rbp+0F0h+var_158]
0x18000f1c5  movsd   xmm9, qword ptr [rbp+0F0h+var_158+10h]
0x18000f1cb  lea     rcx, [rbp+0F0h+var_170]; pvarg
0x18000f1cf  call    cs:__imp_VariantInit
0x18000f1d5  nop
0x18000f1d6  movups  xmm6, xmmword ptr [rbp+0F0h+var_170]
0x18000f1da  movsd   xmm7, qword ptr [rbp+0F0h+var_170+10h]
0x18000f1df  lea     rcx, [rsp+1F0h+var_190+8]; pvarg
0x18000f1e4  call    cs:__imp_VariantInit
0x18000f1ea  nop
0x18000f1eb  movups  xmm0, xmmword ptr [rsp+1F0h+var_190+8]
0x18000f1f0  movsd   xmm1, [rsp+1F0h+var_178]
0x18000f1f6  movaps  [rbp+0F0h+var_120], xmm10
0x18000f1fb  movsd   [rbp+0F0h+var_110], xmm11
0x18000f201  movaps  [rbp+0F0h+var_100], xmm8
0x18000f206  movsd   [rbp+0F0h+var_F0], xmm9
0x18000f20c  movaps  [rbp+0F0h+var_E0], xmm6
0x18000f210  movsd   [rbp+0F0h+var_D0], xmm7
0x18000f215  movaps  [rbp+0F0h+var_C0], xmm0
0x18000f219  movsd   [rbp+0F0h+var_B0], xmm1
0x18000f21e  lea     rax, [rbp+0F0h+var_120]
0x18000f222  mov     [rsp+1F0h+ppv], rax
0x18000f227  lea     r9, [rbp+0F0h+var_100]
0x18000f22b  lea     r8, [rbp+0F0h+var_E0]
0x18000f22f  lea     rdx, [rbp+0F0h+var_C0]
0x18000f233  mov     rcx, [rbp+0F0h+var_98]
0x18000f237  mov     rax, rbx
0x18000f23a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f23f  mov     esi, eax
0x18000f241  lea     rcx, [rsp+1F0h+var_190+8]; pvarg
0x18000f246  call    cs:__imp_VariantClear
0x18000f24c  test    eax, eax
0x18000f24e  js      loc_18000F4EC
0x18000f254  lea     rcx, [rbp+0F0h+var_170]; pvarg
0x18000f258  call    cs:__imp_VariantClear
0x18000f25e  test    eax, eax
0x18000f260  js      loc_18000F4F4
0x18000f266  lea     rcx, [rbp+0F0h+var_158]; pvarg
0x18000f26a  call    cs:__imp_VariantClear
0x18000f270  test    eax, eax
0x18000f272  js      loc_18000F4FC
0x18000f278  lea     rcx, [rbp+0F0h+pvarg]; pvarg
0x18000f27c  call    cs:__imp_VariantClear
0x18000f282  test    eax, eax
0x18000f284  js      loc_18000F4E4
0x18000f28a  test    esi, esi
0x18000f28c  jns     short loc_18000F2EB
0x18000f28e  call    cs:__imp_GetLastError
0x18000f294  mov     edi, eax
0x18000f296  call    cs:__imp_CurrentIP
0x18000f29c  mov     rbx, rax
0x18000f29f  mov     r8d, esi
0x18000f2a2  lea     rdx, aCpitrbaseGetpi; "CPITRBase::GetPITRTask: Failed to conne"...
0x18000f2a9  mov     ecx, 2000000h; unsigned int
0x18000f2ae  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000f2b3  mov     [rsp+1F0h+var_1A0], r15d
0x18000f2b8  mov     qword ptr [rsp+1F0h+var_1A8], r15
0x18000f2bd  mov     dword ptr [rsp+1F0h+var_1B0], edi
0x18000f2c1  mov     qword ptr [rsp+1F0h+var_1B8], rbx
0x18000f2c6  lea     rcx, aCpitrbaseGetpi_3; "CPITRBase::GetPITRTask"
0x18000f2cd  mov     [rsp+1F0h+var_1C0], rcx
0x18000f2d2  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x18000f2d9  mov     [rsp+1F0h+var_1C8], rcx
0x18000f2de  mov     dword ptr [rsp+1F0h+ppv], 0D13h
0x18000f2e6  jmp     loc_18000F17A
0x18000f2eb  mov     rax, [rbp+0F0h+var_98]
0x18000f2ef  mov     rcx, [rax]
0x18000f2f2  mov     rbx, [rcx+38h]
0x18000f2f6  lea     rdx, pszSrc; "\\"
0x18000f2fd  lea     rcx, [rsp+1F0h+var_190]; this
0x18000f302  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000f307  nop
0x18000f308  mov     rdx, [rax]
0x18000f30b  test    rdx, rdx
0x18000f30e  jz      short loc_18000F315
0x18000f310  mov     rdx, [rdx]
0x18000f313  jmp     short loc_18000F318
0x18000f315  mov     rdx, r15
0x18000f318  lea     r8, [rbp+0F0h+var_A0]
0x18000f31c  mov     rcx, [rbp+0F0h+var_98]
0x18000f320  mov     rax, rbx
0x18000f323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f328  mov     esi, eax
0x18000f32a  lea     rcx, [rsp+1F0h+var_190]; this
0x18000f32f  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18000f334  test    esi, esi
0x18000f336  jns     short loc_18000F395
0x18000f338  call    cs:__imp_GetLastError
0x18000f33e  mov     edi, eax
0x18000f340  call    cs:__imp_CurrentIP
0x18000f346  mov     rbx, rax
0x18000f349  mov     r8d, esi
0x18000f34c  lea     rdx, aCpitrbaseGetpi_1; "CPITRBase::GetPITRTask: Failed to get t"...
0x18000f353  mov     ecx, 2000000h; unsigned int
0x18000f358  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000f35d  mov     [rsp+1F0h+var_1A0], r15d
0x18000f362  mov     qword ptr [rsp+1F0h+var_1A8], r15
0x18000f367  mov     dword ptr [rsp+1F0h+var_1B0], edi
0x18000f36b  mov     qword ptr [rsp+1F0h+var_1B8], rbx
0x18000f370  lea     rcx, aCpitrbaseGetpi_3; "CPITRBase::GetPITRTask"
0x18000f377  mov     [rsp+1F0h+var_1C0], rcx
0x18000f37c  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x18000f383  mov     [rsp+1F0h+var_1C8], rcx
0x18000f388  mov     dword ptr [rsp+1F0h+ppv], 0D19h
0x18000f390  jmp     loc_18000F17A
0x18000f395  mov     rax, [rbp+0F0h+var_A0]
0x18000f399  mov     rcx, [rax]
0x18000f39c  mov     rbx, [rcx+68h]
0x18000f3a0  lea     rdx, aMicrosoftWindo; "Microsoft\\Windows\\Setup\\PITRTask"
0x18000f3a7  lea     rcx, [rsp+1F0h+var_190]; this
0x18000f3ac  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000f3b1  nop
0x18000f3b2  mov     rdx, [rax]
0x18000f3b5  test    rdx, rdx
0x18000f3b8  jz      short loc_18000F3BF
0x18000f3ba  mov     rdx, [rdx]
0x18000f3bd  jmp     short loc_18000F3C2
0x18000f3bf  mov     rdx, r15
0x18000f3c2  lea     r8, [rbp+0F0h+var_90]
0x18000f3c6  mov     rcx, [rbp+0F0h+var_A0]
0x18000f3ca  mov     rax, rbx
0x18000f3cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3d2  mov     esi, eax
0x18000f3d4  lea     rcx, [rsp+1F0h+var_190]; this
0x18000f3d9  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18000f3de  test    esi, esi
0x18000f3e0  jns     short loc_18000F43F
0x18000f3e2  call    cs:__imp_GetLastError
0x18000f3e8  mov     edi, eax
0x18000f3ea  call    cs:__imp_CurrentIP
0x18000f3f0  mov     rbx, rax
0x18000f3f3  mov     r8d, esi
0x18000f3f6  lea     rdx, aCpitrbaseGetpi_0; "CPITRBase::GetPITRTask: Failed to get P"...
0x18000f3fd  mov     ecx, 2000000h; unsigned int
0x18000f402  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000f407  mov     [rsp+1F0h+var_1A0], r15d
0x18000f40c  mov     qword ptr [rsp+1F0h+var_1A8], r15
0x18000f411  mov     dword ptr [rsp+1F0h+var_1B0], edi
0x18000f415  mov     qword ptr [rsp+1F0h+var_1B8], rbx
0x18000f41a  lea     rcx, aCpitrbaseGetpi_3; "CPITRBase::GetPITRTask"
0x18000f421  mov     [rsp+1F0h+var_1C0], rcx
0x18000f426  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x18000f42d  mov     [rsp+1F0h+var_1C8], rcx
0x18000f432  mov     dword ptr [rsp+1F0h+ppv], 0D1Fh
0x18000f43a  jmp     loc_18000F17A
0x18000f43f  test    rdi, rdi
0x18000f442  jz      short loc_18000F44F
0x18000f444  mov     rax, [rbp+0F0h+var_A0]
0x18000f448  mov     [rdi], rax
0x18000f44b  mov     [rbp+0F0h+var_A0], r15
0x18000f44f  mov     rax, [rbp+0F0h+var_90]
0x18000f453  mov     [r14], rax
0x18000f456  mov     [rbp+0F0h+var_90], r15
0x18000f45a  mov     rcx, [rbp+0F0h+var_90]
0x18000f45e  test    rcx, rcx
0x18000f461  jz      short loc_18000F473
0x18000f463  mov     rax, [rcx]
0x18000f466  mov     rax, [rax+10h]
0x18000f46a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f46f  mov     [rbp+0F0h+var_90], r15
0x18000f473  mov     rcx, [rbp+0F0h+var_A0]
0x18000f477  test    rcx, rcx
0x18000f47a  jz      short loc_18000F48C
0x18000f47c  mov     rax, [rcx]
0x18000f47f  mov     rax, [rax+10h]
0x18000f483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f488  mov     [rbp+0F0h+var_A0], r15
0x18000f48c  mov     rcx, [rbp+0F0h+var_98]
0x18000f490  test    rcx, rcx
0x18000f493  jz      short loc_18000F4A1
0x18000f495  mov     rax, [rcx]
0x18000f498  mov     rax, [rax+10h]
0x18000f49c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4a1  mov     eax, esi
0x18000f4a3  mov     rcx, [rbp+0F0h+var_88]
0x18000f4a7  xor     rcx, rsp; StackCookie
0x18000f4aa  call    __security_check_cookie
0x18000f4af  lea     r11, [rsp+1F0h+var_20]
0x18000f4b7  mov     rbx, [r11+30h]
0x18000f4bb  movaps  xmm6, xmmword ptr [r11-10h]
0x18000f4c0  movaps  xmm7, xmmword ptr [r11-20h]
0x18000f4c5  movaps  xmm8, xmmword ptr [r11-30h]
0x18000f4ca  movaps  xmm9, xmmword ptr [r11-40h]
0x18000f4cf  movaps  xmm10, xmmword ptr [r11-50h]
0x18000f4d4  movaps  xmm11, xmmword ptr [r11-60h]
0x18000f4d9  mov     rsp, r11
0x18000f4dc  pop     r15
0x18000f4de  pop     r14
0x18000f4e0  pop     rdi
0x18000f4e1  pop     rsi
0x18000f4e2  pop     rbp
0x18000f4e3  retn
0x18000f4e4  mov     ecx, eax; int
0x18000f4e6  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18000f4ec  mov     ecx, eax; int
0x18000f4ee  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18000f4f4  mov     ecx, eax; int
0x18000f4f6  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18000f4fc  mov     ecx, eax; int
0x18000f4fe  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
