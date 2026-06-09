# OobeEsimTaskManager::SetTaskCellularStateSnapshotTrigger(bool)

- ea: `0x180009290`
- end: `0x180009c05`
- name: `?SetTaskCellularStateSnapshotTrigger@OobeEsimTaskManager@@AEAAJ_N@Z`
- size: `2421`
- prototype: `__int64 __fastcall(OobeEsimTaskManager *__hidden this, bool)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800079a0`

## callees

- `0x180002150`
- `0x180009290`
- `0x18000ad20`
- `0x18002cd20`
- `0x180036714`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800093f3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800093f3`
- `OLEAUT32!__imp_SysAllocString` at `0x1800093aa`
- `OLEAUT32!__imp_SysAllocString` at `0x1800093c2`
- `OLEAUT32!__imp_SysAllocString` at `0x1800093aa`
- `OLEAUT32!__imp_SysAllocString` at `0x1800093c2`
- `OLEAUT32!__imp_SysFreeString` at `0x180009795`
- `OLEAUT32!__imp_SysFreeString` at `0x1800097a4`
- `OLEAUT32!__imp_SysFreeString` at `0x180009928`
- `OLEAUT32!__imp_SysFreeString` at `0x180009937`
- `OLEAUT32!__imp_SysFreeString` at `0x180009795`
- `OLEAUT32!__imp_SysFreeString` at `0x1800097a4`
- `OLEAUT32!__imp_SysFreeString` at `0x180009928`
- `OLEAUT32!__imp_SysFreeString` at `0x180009937`
- `OLEAUT32!__imp_VariantInit` at `0x1800092c9`
- `OLEAUT32!__imp_VariantInit` at `0x180009303`
- `OLEAUT32!__imp_VariantInit` at `0x180009588`
- `OLEAUT32!__imp_VariantInit` at `0x1800092c9`
- `OLEAUT32!__imp_VariantInit` at `0x180009303`
- `OLEAUT32!__imp_VariantInit` at `0x180009588`
- `OLEAUT32!__imp_VariantClear` at `0x180009786`
- `OLEAUT32!__imp_VariantClear` at `0x1800097b3`
- `OLEAUT32!__imp_VariantClear` at `0x180009892`
- `OLEAUT32!__imp_VariantClear` at `0x1800098e5`
- `OLEAUT32!__imp_VariantClear` at `0x180009946`
- `OLEAUT32!__imp_VariantClear` at `0x180009a25`
- `OLEAUT32!__imp_VariantClear` at `0x180009ab1`
- `OLEAUT32!__imp_VariantClear` at `0x180009bcf`
- `OLEAUT32!__imp_VariantClear` at `0x180009786`
- `OLEAUT32!__imp_VariantClear` at `0x1800097b3`
- `OLEAUT32!__imp_VariantClear` at `0x180009892`
- `OLEAUT32!__imp_VariantClear` at `0x1800098e5`
- `OLEAUT32!__imp_VariantClear` at `0x180009946`
- `OLEAUT32!__imp_VariantClear` at `0x180009a25`
- `OLEAUT32!__imp_VariantClear` at `0x180009ab1`
- `OLEAUT32!__imp_VariantClear` at `0x180009bcf`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18000933b`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18000933b`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180009777`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180009919`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180009777`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180009919`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180009384`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180009384`

## string_xrefs

- `0x18000966b`: `OobeEsimTaskManager::SetTaskCellularStateSnapshotTrigger`
- `0x180009763`: `OobeEsimTaskManager::SetTaskCellularStateSnapshotTrigger`
- `0x180009905`: `OobeEsimTaskManager::SetTaskCellularStateSnapshotTrigger`
- `0x180009757`: `Completed SetTaskCellularStateSnapshotTrigger to: %d`
- `0x180009ad0`: `onecoreuap\net\ux\mbmediamanager\lib\oobeesimtaskmanager.cpp`
- `0x180009ae4`: `onecoreuap\net\ux\mbmediamanager\lib\oobeesimtaskmanager.cpp`
- `0x180009af8`: `onecoreuap\net\ux\mbmediamanager\lib\oobeesimtaskmanager.cpp`
- `0x180009b0c`: `onecoreuap\net\ux\mbmediamanager\lib\oobeesimtaskmanager.cpp`
- `0x180009b20`: `onecoreuap\net\ux\mbmediamanager\lib\oobeesimtaskmanager.cpp`
- `0x180009b34`: `onecoreuap\net\ux\mbmediamanager\lib\oobeesimtaskmanager.cpp`
- `0x180009b48`: `onecoreuap\net\ux\mbmediamanager\lib\oobeesimtaskmanager.cpp`
- `0x180009b5d`: `onecoreuap\net\ux\mbmediamanager\lib\oobeesimtaskmanager.cpp`
- `0x180009b71`: `onecoreuap\net\ux\mbmediamanager\lib\oobeesimtaskmanager.cpp`
- `0x180009b85`: `onecoreuap\net\ux\mbmediamanager\lib\oobeesimtaskmanager.cpp`
- `0x180009ba1`: `onecoreuap\net\ux\mbmediamanager\lib\oobeesimtaskmanager.cpp`
- `0x180009bb5`: `onecoreuap\net\ux\mbmediamanager\lib\oobeesimtaskmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=27 #try_helpers=1
__int64 __fastcall OobeEsimTaskManager::SetTaskCellularStateSnapshotTrigger(
        OobeEsimTaskManager *this,
        unsigned __int8 a2)
{
  int v2; // r13d
  int v3; // r12d
  SAFEARRAY *parray; // r9
  int v5; // ecx
  OLECHAR *v6; // rdi
  OLECHAR *v7; // rbx
  HRESULT v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  __int64 v15; // r15
  __int64 (__fastcall *v16)(__int64, _QWORD, _QWORD); // r14
  int v17; // eax
  __int64 (__fastcall ***v18)(_QWORD, _QWORD, _QWORD); // r15
  __int64 (__fastcall *v19)(_QWORD, GUID *, __int64 *); // r14
  int v20; // eax
  int v21; // eax
  unsigned int i; // r8d
  int v23; // eax
  __int64 v24; // r15
  __int64 (__fastcall *v25)(__int64, OLECHAR *, __int64, __int64); // r14
  int v26; // eax
  __int64 v27; // rcx
  __int64 (__fastcall ***v28)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  LPVOID v33; // rcx
  __int64 v35; // rcx
  __int64 (__fastcall ***v36)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rcx
  LPVOID v41; // rcx
  int ppv; // [rsp+20h] [rbp-1A8h]
  int v43; // [rsp+50h] [rbp-178h] BYREF
  __int64 v44; // [rsp+58h] [rbp-170h] BYREF
  __int64 v45; // [rsp+60h] [rbp-168h] BYREF
  __int64 v46; // [rsp+68h] [rbp-160h] BYREF
  __int64 v47; // [rsp+70h] [rbp-158h] BYREF
  __int64 v48; // [rsp+78h] [rbp-150h] BYREF
  LPVOID v49; // [rsp+80h] [rbp-148h] BYREF
  __int64 (__fastcall ***v50)(_QWORD, GUID *, __int64 *); // [rsp+88h] [rbp-140h] BYREF
  LONG rgIndices[2]; // [rsp+90h] [rbp-138h] BYREF
  VARIANTARG v52; // [rsp+98h] [rbp-130h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+B0h] [rbp-118h] BYREF
  VARIANTARG v54; // [rsp+C0h] [rbp-108h] BYREF
  VARIANTARG pvarg; // [rsp+E0h] [rbp-E8h] BYREF
  VARIANTARG v56; // [rsp+100h] [rbp-C8h] BYREF
  VARIANTARG v57; // [rsp+120h] [rbp-A8h] BYREF
  VARIANTARG v58; // [rsp+140h] [rbp-88h] BYREF
  OLECHAR *v59; // [rsp+160h] [rbp-68h]
  _DWORD v60[2]; // [rsp+168h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+0h]

  v2 = a2;
  VariantInit(&pvarg);
  v49 = 0;
  v48 = 0;
  v47 = 0;
  v46 = 0;
  v45 = 0;
  v50 = 0;
  v44 = 0;
  VariantInit(&v52);
  v52.vt = 27;
  rgsabound = (SAFEARRAYBOUND)8LL;
  v3 = 1;
  parray = SafeArrayCreate(0x11u, 1u, &rgsabound);
  v52.llVal = (LONGLONG)parray;
  v60[0] = -1547954059;
  v60[1] = 260512058;
  rgIndices[0] = 0;
  v5 = 0;
  while ( 1 )
  {
    SafeArrayPutElement(parray, rgIndices, (char *)v60 + v5);
    v5 = rgIndices[0] + 1;
    rgIndices[0] = v5;
    if ( (unsigned int)v5 >= 8 )
      break;
    parray = v52.parray;
  }
  v6 = SysAllocString(L"\\Microsoft\\Windows\\WwanSvc");
  *(_QWORD *)rgIndices = v6;
  v7 = SysAllocString(L"OobeDiscovery");
  v59 = v7;
  v8 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &v49);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x189,
      (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeesimtaskmanager.cpp",
      (const char *)(unsigned int)v8,
      ppv);
  v54 = pvarg;
  v56 = pvarg;
  v57 = pvarg;
  v58 = pvarg;
  v9 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *))(*(_QWORD *)v49 + 80LL))(
         v49,
         &v58,
         &v57,
         &v56);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18A,
      (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeesimtaskmanager.cpp",
      (const char *)(unsigned int)v9,
      (int)&v54);
  v10 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, __int64 *))(*(_QWORD *)v49 + 56LL))(v49, v6, &v48);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18B,
      (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeesimtaskmanager.cpp",
      (const char *)(unsigned int)v10,
      (int)&v54);
  v11 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, __int64 *))(*(_QWORD *)v48 + 104LL))(v48, v7, &v47);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeesimtaskmanager.cpp",
      (const char *)(unsigned int)v11,
      (int)&v54);
  v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v47 + 152LL))(v47, &v46);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18D,
      (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeesimtaskmanager.cpp",
      (const char *)(unsigned int)v12,
      (int)&v54);
  v13 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v46 + 72LL))(v46, &v45);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18E,
      (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeesimtaskmanager.cpp",
      (const char *)(unsigned int)v13,
      (int)&v54);
  v43 = 0;
  v14 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v45 + 56LL))(v45, &v43);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x192,
      (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeesimtaskmanager.cpp",
      (const char *)(unsigned int)v14,
      (int)&v54);
LABEL_10:
  if ( v3 > v43 )
  {
    MBSettingUXLogging::Info(
      "OobeEsimTaskManager::SetTaskCellularStateSnapshotTrigger",
      0x1C0u,
      "CellularStateSnapshot Trigger was not found");
    SafeArrayDestroy(v52.parray);
    if ( v7 )
      SysFreeString(v7);
    if ( v6 )
      SysFreeString(v6);
    VariantClear(&v52);
    v35 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    }
    v36 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v50;
    if ( v50 )
    {
      v50 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v36)[2])(v36);
    }
    v37 = v45;
    if ( v45 )
    {
      v45 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    }
    v38 = v46;
    if ( v46 )
    {
      v46 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    }
    v39 = v47;
    if ( v47 )
    {
      v47 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    }
    v40 = v48;
    if ( v48 )
    {
      v48 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    }
    v41 = v49;
    if ( v49 )
    {
      v49 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v41 + 16LL))(v41);
    }
  }
  else
  {
    VariantInit(&v54);
    v54.vt = 27;
    v15 = v45;
    v16 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v45 + 64LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
    v17 = v16(v15, (unsigned int)v3, &v50);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x198,
        (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeesimtaskmanager.cpp",
        (const char *)(unsigned int)v17,
        (int)&v54);
    v18 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v50;
    v19 = **v50;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
    v20 = v19(v18, &IID_IWnfStateChangeTrigger, &v44);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x199,
        (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeesimtaskmanager.cpp",
        (const char *)(unsigned int)v20,
        (int)&v54);
    v21 = (*(__int64 (__fastcall **)(__int64, CY *))(*(_QWORD *)v44 + 176LL))(v44, &v54.cyVal);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x19A,
        (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeesimtaskmanager.cpp",
        (const char *)(unsigned int)v21,
        (int)&v54);
    for ( i = 0; i < 8; ++i )
    {
      if ( *(_BYTE *)(i + *(_QWORD *)(v52.llVal + 16)) != *(_BYTE *)(i + *(_QWORD *)(v54.llVal + 16)) )
      {
        VariantClear(&v54);
        ++v3;
        goto LABEL_10;
      }
    }
    MBSettingUXLogging::Info(
      "OobeEsimTaskManager::SetTaskCellularStateSnapshotTrigger",
      0x1AAu,
      "CellularStateSnapshot Trigger found",
      v52.llVal);
    v23 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v44 + 152LL))(
            v44,
            (unsigned __int16)(((unsigned __int8)v2 ^ 1) - 1));
    if ( v23 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1AD,
        (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeesimtaskmanager.cpp",
        (const char *)(unsigned int)v23,
        (int)&v54);
    v24 = v48;
    v25 = *(__int64 (__fastcall **)(__int64, OLECHAR *, __int64, __int64))(*(_QWORD *)v48 + 136LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
    memset(&v58, 0, sizeof(v58));
    memset(&v57, 0, sizeof(v57));
    memset(&v56, 0, sizeof(v56));
    v26 = v25(v24, v7, v46, 36);
    if ( v26 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1B8,
        (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeesimtaskmanager.cpp",
        (const char *)(unsigned int)v26,
        (int)&v56);
    MBSettingUXLogging::Info(
      "OobeEsimTaskManager::SetTaskCellularStateSnapshotTrigger",
      0x1BAu,
      "Completed SetTaskCellularStateSnapshotTrigger to: %d",
      v2);
    SafeArrayDestroy(v52.parray);
    VariantClear(&v54);
    if ( v7 )
      SysFreeString(v7);
    if ( v6 )
      SysFreeString(v6);
    VariantClear(&v52);
    v27 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    }
    v28 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v50;
    if ( v50 )
    {
      v50 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v28)[2])(v28);
    }
    v29 = v45;
    if ( v45 )
    {
      v45 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    }
    v30 = v46;
    if ( v46 )
    {
      v46 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    }
    v31 = v47;
    if ( v47 )
    {
      v47 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    }
    v32 = v48;
    if ( v48 )
    {
      v48 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    }
    v33 = v49;
    if ( v49 )
    {
      v49 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v33 + 16LL))(v33);
    }
  }
  VariantClear(&pvarg);
  return 0;
}

```

## disassembly

```asm
0x180009290  push    rbx
0x180009292  push    rsi
0x180009293  push    rdi
0x180009294  push    r12
0x180009296  push    r13
0x180009298  push    r14
0x18000929a  push    r15
0x18000929c  sub     rsp, 190h
0x1800092a3  movaps  [rsp+1C8h+var_48], xmm6
0x1800092ab  mov     rax, cs:__security_cookie
0x1800092b2  xor     rax, rsp
0x1800092b5  mov     [rsp+1C8h+var_58], rax
0x1800092bd  movzx   r13d, dl
0x1800092c1  lea     rcx, [rsp+1C8h+pvarg]; pvarg
0x1800092c9  call    cs:__imp_VariantInit
0x1800092cf  nop
0x1800092d0  xor     esi, esi
0x1800092d2  mov     [rsp+1C8h+var_148], rsi
0x1800092da  mov     [rsp+1C8h+var_150], rsi
0x1800092df  mov     [rsp+1C8h+var_158], rsi
0x1800092e4  mov     [rsp+1C8h+var_160], rsi
0x1800092e9  mov     [rsp+1C8h+var_168], rsi
0x1800092ee  mov     [rsp+1C8h+var_140], rsi
0x1800092f6  mov     [rsp+1C8h+var_170], rsi
0x1800092fb  lea     rcx, [rsp+1C8h+var_130]; pvarg
0x180009303  call    cs:__imp_VariantInit
0x180009309  nop
0x18000930a  mov     r14d, 1Bh
0x180009310  mov     word ptr [rsp+1C8h+var_130], r14w
0x180009319  mov     qword ptr [rsp+1C8h+rgsabound.cElements], 8
0x180009325  mov     ecx, 11h; vt
0x18000932a  lea     r8, [rsp+1C8h+rgsabound]; rgsabound
0x180009332  mov     r12d, 1
0x180009338  mov     edx, r12d; cDims
0x18000933b  call    cs:__imp_SafeArrayCreate
0x180009341  mov     r9, rax
0x180009344  mov     qword ptr [rsp+1C8h+var_130+8], rax
0x18000934c  mov     [rsp+1C8h+var_60], 0A3BC1875h
0x180009357  mov     [rsp+1C8h+var_5C], 0F87193Ah
0x180009362  mov     [rsp+1C8h+rgIndices], esi
0x180009369  mov     ecx, esi
0x18000936b  movsxd  rax, ecx
0x18000936e  lea     r8, [rsp+1C8h+var_60]
0x180009376  add     r8, rax; pv
0x180009379  lea     rdx, [rsp+1C8h+rgIndices]; rgIndices
0x180009381  mov     rcx, r9; psa
0x180009384  call    cs:__imp_SafeArrayPutElement
0x18000938a  mov     ecx, [rsp+1C8h+rgIndices]
0x180009391  inc     ecx
0x180009393  mov     [rsp+1C8h+rgIndices], ecx
0x18000939a  cmp     ecx, 8
0x18000939d  jb      loc_180009AC0
0x1800093a3  lea     rcx, psz; "\\Microsoft\\Windows\\WwanSvc"
0x1800093aa  call    cs:__imp_SysAllocString
0x1800093b0  mov     rdi, rax
0x1800093b3  mov     qword ptr [rsp+1C8h+rgIndices], rax
0x1800093bb  lea     rcx, aOobediscovery; "OobeDiscovery"
0x1800093c2  call    cs:__imp_SysAllocString
0x1800093c8  mov     rbx, rax
0x1800093cb  mov     [rsp+1C8h+var_68], rax
0x1800093d3  lea     rax, [rsp+1C8h+var_148]
0x1800093db  mov     [rsp+1C8h+ppv], rax; int
0x1800093e0  lea     r9, IID_ITaskService; riid
0x1800093e7  mov     r8d, r12d; dwClsContext
0x1800093ea  xor     edx, edx; pUnkOuter
0x1800093ec  lea     rcx, CLSID_TaskScheduler; rclsid
0x1800093f3  call    cs:__imp_CoCreateInstance
0x1800093f9  mov     rcx, [rsp+1C8h]; this
0x180009401  test    eax, eax
0x180009403  js      loc_180009ACD
0x180009409  mov     rcx, [rsp+1C8h+var_148]
0x180009411  movups  xmm1, xmmword ptr [rsp+1C8h+pvarg]
0x180009419  movsd   xmm0, qword ptr [rsp+1C8h+pvarg+10h]
0x180009422  movaps  xmmword ptr [rsp+1C8h+var_108], xmm1
0x18000942a  movsd   qword ptr [rsp+1C8h+var_108+10h], xmm0
0x180009433  movaps  xmmword ptr [rsp+1C8h+var_C8], xmm1
0x18000943b  movsd   [rsp+1C8h+var_B8], xmm0
0x180009444  movaps  [rsp+1C8h+var_A8], xmm1
0x18000944c  movsd   [rsp+1C8h+var_98], xmm0
0x180009455  movaps  [rsp+1C8h+var_88], xmm1
0x18000945d  movsd   [rsp+1C8h+var_78], xmm0
0x180009466  mov     rax, [rcx]
0x180009469  lea     rdx, [rsp+1C8h+var_108]
0x180009471  mov     [rsp+1C8h+ppv], rdx; int
0x180009476  lea     r9, [rsp+1C8h+var_C8]
0x18000947e  lea     r8, [rsp+1C8h+var_A8]
0x180009486  lea     rdx, [rsp+1C8h+var_88]
0x18000948e  mov     rax, [rax+50h]
0x180009492  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009497  mov     rcx, [rsp+1C8h]; this
0x18000949f  test    eax, eax
0x1800094a1  js      loc_180009AE1
0x1800094a7  mov     rcx, [rsp+1C8h+var_148]
0x1800094af  mov     rax, [rcx]
0x1800094b2  lea     r8, [rsp+1C8h+var_150]
0x1800094b7  mov     rdx, rdi
0x1800094ba  mov     rax, [rax+38h]
0x1800094be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094c3  mov     rcx, [rsp+1C8h]; this
0x1800094cb  test    eax, eax
0x1800094cd  js      loc_180009AF5
0x1800094d3  mov     rcx, [rsp+1C8h+var_150]
0x1800094d8  mov     rax, [rcx]
0x1800094db  lea     r8, [rsp+1C8h+var_158]
0x1800094e0  mov     rdx, rbx
0x1800094e3  mov     rax, [rax+68h]
0x1800094e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094ec  mov     rcx, [rsp+1C8h]; this
0x1800094f4  test    eax, eax
0x1800094f6  js      loc_180009B09
0x1800094fc  mov     rcx, [rsp+1C8h+var_158]
0x180009501  mov     rax, [rcx]
0x180009504  lea     rdx, [rsp+1C8h+var_160]
0x180009509  mov     rax, [rax+98h]
0x180009510  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009515  mov     rcx, [rsp+1C8h]; this
0x18000951d  test    eax, eax
0x18000951f  js      loc_180009B1D
0x180009525  mov     rcx, [rsp+1C8h+var_160]
0x18000952a  mov     rax, [rcx]
0x18000952d  lea     rdx, [rsp+1C8h+var_168]
0x180009532  mov     rax, [rax+48h]
0x180009536  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000953b  mov     rcx, [rsp+1C8h]; this
0x180009543  test    eax, eax
0x180009545  js      loc_180009B31
0x18000954b  mov     [rsp+1C8h+var_178], esi
0x18000954f  mov     rcx, [rsp+1C8h+var_168]
0x180009554  mov     rax, [rcx]
0x180009557  lea     rdx, [rsp+1C8h+var_178]
0x18000955c  mov     rax, [rax+38h]
0x180009560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009565  mov     rcx, [rsp+1C8h]; this
0x18000956d  test    eax, eax
0x18000956f  js      loc_180009B45
0x180009575  cmp     r12d, [rsp+1C8h+var_178]
0x18000957a  jg      loc_1800098F9
0x180009580  lea     rcx, [rsp+1C8h+var_108]; pvarg
0x180009588  call    cs:__imp_VariantInit
0x18000958e  nop
0x18000958f  mov     word ptr [rsp+1C8h+var_108], r14w
0x180009598  mov     r15, [rsp+1C8h+var_168]
0x18000959d  mov     rax, [r15]
0x1800095a0  mov     r14, [rax+40h]
0x1800095a4  lea     rcx, [rsp+1C8h+var_140]
0x1800095ac  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800095b1  lea     r8, [rsp+1C8h+var_140]
0x1800095b9  mov     edx, r12d
0x1800095bc  mov     rcx, r15
0x1800095bf  mov     rax, r14
0x1800095c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095c7  mov     rcx, [rsp+1C8h]; this
0x1800095cf  test    eax, eax
0x1800095d1  js      loc_180009B5A
0x1800095d7  mov     r15, [rsp+1C8h+var_140]
0x1800095df  mov     rax, [r15]
0x1800095e2  mov     r14, [rax]
0x1800095e5  lea     rcx, [rsp+1C8h+var_170]
0x1800095ea  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800095ef  lea     r8, [rsp+1C8h+var_170]
0x1800095f4  lea     rdx, IID_IWnfStateChangeTrigger
0x1800095fb  mov     rcx, r15
0x1800095fe  mov     rax, r14
0x180009601  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009606  mov     rcx, [rsp+1C8h]; this
0x18000960e  test    eax, eax
0x180009610  js      loc_180009B6E
0x180009616  mov     rcx, [rsp+1C8h+var_170]
0x18000961b  mov     rax, [rcx]
0x18000961e  lea     rdx, [rsp+1C8h+var_108+8]
0x180009626  mov     rax, [rax+0B0h]
0x18000962d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009632  mov     rcx, [rsp+1C8h]; this
0x18000963a  test    eax, eax
0x18000963c  js      loc_180009B82
0x180009642  mov     r8d, esi
0x180009645  mov     r9, qword ptr [rsp+1C8h+var_130+8]
0x18000964d  mov     r10, qword ptr [rsp+1C8h+var_108+8]
0x180009655  cmp     r8d, 8
0x180009659  jb      loc_1800098C5
0x18000965f  lea     r8, aCellularstates_0; "CellularStateSnapshot Trigger found"
0x180009666  mov     edx, 1AAh; unsigned int
0x18000966b  lea     rcx, aOobeesimtaskma; "OobeEsimTaskManager::SetTaskCellularSta"...
0x180009672  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x180009677  mov     rcx, [rsp+1C8h+var_170]
0x18000967c  mov     r8, [rcx]
0x18000967f  movzx   eax, r13b
0x180009683  xor     al, 1
0x180009685  movzx   edx, al
0x180009688  dec     dx
0x18000968b  mov     rax, [r8+98h]
0x180009692  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009697  mov     rcx, [rsp+1C8h]; this
0x18000969f  test    eax, eax
0x1800096a1  js      loc_180009B9E
0x1800096a7  xorps   xmm6, xmm6
0x1800096aa  xor     r12d, r12d
0x1800096ad  mov     r15, [rsp+1C8h+var_150]
0x1800096b2  mov     rax, [r15]
0x1800096b5  mov     r14, [rax+88h]
0x1800096bc  lea     rcx, [rsp+1C8h+var_158]
0x1800096c1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800096c6  movaps  [rsp+1C8h+var_88], xmm6
0x1800096ce  mov     [rsp+1C8h+var_78], r12
0x1800096d6  movaps  [rsp+1C8h+var_A8], xmm6
0x1800096de  mov     [rsp+1C8h+var_98], r12
0x1800096e6  movaps  xmmword ptr [rsp+1C8h+var_C8], xmm6
0x1800096ee  mov     [rsp+1C8h+var_B8], r12
0x1800096f6  lea     rax, [rsp+1C8h+var_158]
0x1800096fb  mov     [rsp+1C8h+var_188], rax
0x180009700  lea     rax, [rsp+1C8h+var_88]
0x180009708  mov     [rsp+1C8h+var_190], rax
0x18000970d  mov     [rsp+1C8h+var_198], esi
0x180009711  lea     rax, [rsp+1C8h+var_A8]
0x180009719  mov     [rsp+1C8h+var_1A0], rax
0x18000971e  lea     rax, [rsp+1C8h+var_C8]
0x180009726  mov     [rsp+1C8h+ppv], rax; int
0x18000972b  mov     r9d, 24h ; '$'
0x180009731  mov     r8, [rsp+1C8h+var_160]
0x180009736  mov     rdx, rbx
0x180009739  mov     rcx, r15
0x18000973c  mov     rax, r14
0x18000973f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009744  mov     rcx, [rsp+1C8h]; this
0x18000974c  test    eax, eax
0x18000974e  js      loc_180009BB2
0x180009754  mov     r9d, r13d
0x180009757  lea     r8, aCompletedSetta; "Completed SetTaskCellularStateSnapshotT"...
0x18000975e  mov     edx, 1BAh; unsigned int
0x180009763  lea     rcx, aOobeesimtaskma; "OobeEsimTaskManager::SetTaskCellularSta"...
0x18000976a  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18000976f  mov     rcx, qword ptr [rsp+1C8h+var_130+8]; psa
0x180009777  call    cs:__imp_SafeArrayDestroy
0x18000977d  nop
0x18000977e  lea     rcx, [rsp+1C8h+var_108]; pvarg
0x180009786  call    cs:__imp_VariantClear
0x18000978c  nop
0x18000978d  test    rbx, rbx
0x180009790  jz      short loc_18000979C
0x180009792  mov     rcx, rbx; bstrString
0x180009795  call    cs:__imp_SysFreeString
0x18000979b  nop
0x18000979c  test    rdi, rdi
0x18000979f  jz      short loc_1800097AB
0x1800097a1  mov     rcx, rdi; bstrString
0x1800097a4  call    cs:__imp_SysFreeString
0x1800097aa  nop
0x1800097ab  lea     rcx, [rsp+1C8h+var_130]; pvarg
0x1800097b3  call    cs:__imp_VariantClear
0x1800097b9  nop
0x1800097ba  mov     rcx, [rsp+1C8h+var_170]
0x1800097bf  test    rcx, rcx
0x1800097c2  jz      short loc_1800097D6
0x1800097c4  mov     [rsp+1C8h+var_170], rsi
0x1800097c9  mov     rax, [rcx]
0x1800097cc  mov     rax, [rax+10h]
0x1800097d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097d5  nop
0x1800097d6  mov     rcx, [rsp+1C8h+var_140]
0x1800097de  test    rcx, rcx
0x1800097e1  jz      short loc_1800097F8
0x1800097e3  mov     [rsp+1C8h+var_140], rsi
0x1800097eb  mov     rax, [rcx]
0x1800097ee  mov     rax, [rax+10h]
0x1800097f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097f7  nop
0x1800097f8  mov     rcx, [rsp+1C8h+var_168]
0x1800097fd  test    rcx, rcx
0x180009800  jz      short loc_180009814
0x180009802  mov     [rsp+1C8h+var_168], rsi
0x180009807  mov     rax, [rcx]
0x18000980a  mov     rax, [rax+10h]
0x18000980e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009813  nop
0x180009814  mov     rcx, [rsp+1C8h+var_160]
0x180009819  test    rcx, rcx
0x18000981c  jz      short loc_180009830
0x18000981e  mov     [rsp+1C8h+var_160], rsi
0x180009823  mov     rax, [rcx]
0x180009826  mov     rax, [rax+10h]
0x18000982a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000982f  nop
0x180009830  mov     rcx, [rsp+1C8h+var_158]
0x180009835  test    rcx, rcx
0x180009838  jz      short loc_18000984C
0x18000983a  mov     [rsp+1C8h+var_158], rsi
0x18000983f  mov     rax, [rcx]
0x180009842  mov     rax, [rax+10h]
0x180009846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000984b  nop
0x18000984c  mov     rcx, [rsp+1C8h+var_150]
0x180009851  test    rcx, rcx
0x180009854  jz      short loc_180009868
0x180009856  mov     [rsp+1C8h+var_150], rsi
0x18000985b  mov     rax, [rcx]
0x18000985e  mov     rax, [rax+10h]
0x180009862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009867  nop
0x180009868  mov     rcx, [rsp+1C8h+var_148]
0x180009870  test    rcx, rcx
  ... truncated ...
```
