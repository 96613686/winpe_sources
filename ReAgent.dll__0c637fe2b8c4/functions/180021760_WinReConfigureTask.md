# WinReConfigureTask

- ea: `0x180021760`
- end: `0x180021de9`
- name: `WinReConfigureTask`
- size: `1673`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180001f94`
- `0x1800055c8`
- `0x180005694`
- `0x1800059fc`
- `0x18001c3bc`
- `0x180021760`
- `0x18005cf30`
- `0x18005f010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18002187a`
- `ole32!CoCreateInstance` at `0x18002187a`
- `ole32!CoUninitialize` at `0x180021d86`
- `ole32!CoUninitialize` at `0x180021d86`
- `ole32!CoInitializeEx` at `0x180021813`
- `ole32!CoInitializeEx` at `0x180021813`
- `OLEAUT32!__imp_SysFreeString` at `0x1800219e9`
- `OLEAUT32!__imp_SysFreeString` at `0x180021a81`
- `OLEAUT32!__imp_SysFreeString` at `0x180021b26`
- `OLEAUT32!__imp_SysFreeString` at `0x180021be3`
- `OLEAUT32!__imp_SysFreeString` at `0x180021c90`
- `OLEAUT32!__imp_SysFreeString` at `0x1800219e9`
- `OLEAUT32!__imp_SysFreeString` at `0x180021a81`
- `OLEAUT32!__imp_SysFreeString` at `0x180021b26`
- `OLEAUT32!__imp_SysFreeString` at `0x180021be3`
- `OLEAUT32!__imp_SysFreeString` at `0x180021c90`
- `OLEAUT32!__imp_VariantInit` at `0x1800218a6`
- `OLEAUT32!__imp_VariantInit` at `0x1800218bc`
- `OLEAUT32!__imp_VariantInit` at `0x1800218d3`
- `OLEAUT32!__imp_VariantInit` at `0x1800218e9`
- `OLEAUT32!__imp_VariantInit` at `0x1800218a6`
- `OLEAUT32!__imp_VariantInit` at `0x1800218bc`
- `OLEAUT32!__imp_VariantInit` at `0x1800218d3`
- `OLEAUT32!__imp_VariantInit` at `0x1800218e9`
- `OLEAUT32!__imp_VariantClear` at `0x18002194a`
- `OLEAUT32!__imp_VariantClear` at `0x180021955`
- `OLEAUT32!__imp_VariantClear` at `0x180021960`
- `OLEAUT32!__imp_VariantClear` at `0x18002196a`
- `OLEAUT32!__imp_VariantClear` at `0x18002194a`
- `OLEAUT32!__imp_VariantClear` at `0x180021955`
- `OLEAUT32!__imp_VariantClear` at `0x180021960`
- `OLEAUT32!__imp_VariantClear` at `0x18002196a`

## string_xrefs

- `0x180021831`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x180021b5d`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x180021cfb`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x1800217d3`: `Enter WinReConfigureTask`
- `0x1800217f0`: `Parameters: TaskFolder: %s, TaskName: %s, WinReTaskAction, %d`
- `0x180021840`: `WinReConfigureTask %s (0x%x) in file %S line %d`
- `0x180021b6c`: `WinReConfigureTask %s (0x%x) in file %S line %d`
- `0x180021d0a`: `WinReConfigureTask %s (0x%x) in file %S line %d`
- `0x18002188e`: `failed to create task schedule instance`
- `0x18002197c`: `failed to connect to task service`
- `0x180021ab0`: `failed to get task folder`
- `0x180021b56`: `failed to delete task`
- `0x180021c17`: `failed to delete folder`
- `0x180021cc0`: `failed to get winre task`
- `0x180021cf4`: `failed to set winre task state`
- `0x180021d8f`: `Exit WinReConfigureTask return error code: 0x%x`

## pseudocode

```c
__int64 __fastcall WinReConfigureTask(unsigned __int16 *a1, unsigned __int16 *a2, unsigned int a3)
{
  const unsigned __int16 *v6; // r9
  const unsigned __int16 *v7; // r8
  HRESULT v8; // ebx
  int v9; // esi
  const wchar_t *v10; // r8
  __int64 (__fastcall *v11)(LPVOID, __int128 *, __int128 *, __int128 *, __int128 *); // rbx
  __int128 v12; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v14; // xmm8
  __int64 v15; // xmm9_8
  __int128 v16; // xmm6
  __int64 v17; // xmm7_8
  __int64 (__fastcall *v18)(LPVOID, __int64, __int64 *); // rbx
  _bstr_t *v19; // rax
  __int64 v20; // rdx
  int v21; // eax
  __int64 v22; // rbx
  int v23; // edi
  void *v24; // rcx
  const wchar_t *v25; // r8
  __int64 (__fastcall *v26)(LPVOID, __int64, __int64 *); // rbx
  _bstr_t *v27; // rax
  __int64 v28; // rdx
  int v29; // eax
  __int64 v30; // rbx
  void *v31; // rcx
  __int64 (__fastcall *v32)(__int64, __int64, _QWORD); // rdi
  _bstr_t *v33; // rax
  __int64 v34; // rdx
  int v35; // eax
  __int64 v36; // rdi
  int v37; // r14d
  void *v38; // rcx
  const wchar_t *v39; // r8
  __int64 (__fastcall *v40)(__int64, __int64, _QWORD); // rdi
  _bstr_t *v41; // rax
  __int64 v42; // rdx
  int v43; // eax
  __int64 v44; // rdi
  void *v45; // rcx
  __int64 (__fastcall *v46)(__int64, __int64, __int64 *); // rdi
  _bstr_t *v47; // rax
  __int64 v48; // rdx
  int v49; // eax
  __int64 v50; // rdx
  __int64 v51; // rdi
  void *v52; // rcx
  int v54; // [rsp+30h] [rbp-D8h]
  int v55; // [rsp+30h] [rbp-D8h]
  int v56; // [rsp+30h] [rbp-D8h]
  VARIANTARG v57; // [rsp+40h] [rbp-C8h] BYREF
  VARIANTARG v58; // [rsp+58h] [rbp-B0h] BYREF
  VARIANTARG v59; // [rsp+70h] [rbp-98h] BYREF
  __int64 v60; // [rsp+88h] [rbp-80h]
  VARIANTARG pvarg; // [rsp+90h] [rbp-78h] BYREF
  __int128 v62; // [rsp+A8h] [rbp-60h] BYREF
  IRecordInfo *v63; // [rsp+B8h] [rbp-50h]
  __int128 v64; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v65; // [rsp+D8h] [rbp-30h]
  __int128 v66; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v67; // [rsp+F8h] [rbp-10h]
  __int128 v68; // [rsp+108h] [rbp+0h] BYREF
  __int64 v69; // [rsp+118h] [rbp+10h]
  LPVOID ppv; // [rsp+128h] [rbp+20h] BYREF
  __int64 v71; // [rsp+130h] [rbp+28h] BYREF
  __int64 v72; // [rsp+138h] [rbp+30h] BYREF
  __int64 v73; // [rsp+140h] [rbp+38h] BYREF

  ppv = 0;
  v72 = 0;
  v71 = 0;
  v73 = 0;
  UnattendInitializeLogEx2(0);
  UnattendLogW(0, L"Enter WinReConfigureTask");
  v6 = a2;
  v7 = a1;
  if ( !a2 )
    v6 = L"NULL";
  if ( !a1 )
    v7 = L"NULL";
  UnattendLogW(0, L"Parameters: TaskFolder: %s, TaskName: %s, WinReTaskAction, %d", v7, v6, a3);
  v8 = CoInitializeEx(0, 0);
  if ( v8 < 0 )
  {
    v9 = 0;
    v54 = 2640;
    v10 = L"failed to call coinitialize";
LABEL_7:
    UnattendLogW(
      2,
      L"WinReConfigureTask %s (0x%x) in file %S line %d",
      v10,
      (unsigned int)v8,
      "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
      v54);
    v8 = (unsigned __int16)v8;
    goto LABEL_84;
  }
  v9 = 1;
  v8 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &ppv);
  if ( v8 < 0 )
  {
    v54 = 2648;
    v10 = L"failed to create task schedule instance";
    goto LABEL_7;
  }
  v11 = *(__int64 (__fastcall **)(LPVOID, __int128 *, __int128 *, __int128 *, __int128 *))(*(_QWORD *)ppv + 80LL);
  VariantInit(&pvarg);
  v12 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit((VARIANTARG *)&v59.decVal.8);
  v14 = *(_OWORD *)&v59.decVal.Lo32;
  v15 = v60;
  VariantInit((VARIANTARG *)&v58.decVal.8);
  v16 = *(_OWORD *)&v58.decVal.Lo32;
  v17 = *(_QWORD *)&v59.vt;
  VariantInit((VARIANTARG *)&v57.decVal.8);
  v68 = *(_OWORD *)&v57.decVal.Lo32;
  v62 = v12;
  v63 = pRecInfo;
  v64 = v14;
  v65 = v15;
  v66 = v16;
  v67 = v17;
  v69 = *(_QWORD *)&v58.vt;
  v8 = v11(ppv, &v68, &v66, &v64, &v62);
  VariantClear((VARIANTARG *)&v57.decVal.8);
  VariantClear((VARIANTARG *)&v58.decVal.8);
  VariantClear((VARIANTARG *)&v59.decVal.8);
  VariantClear(&pvarg);
  if ( v8 < 0 )
  {
    v54 = 2654;
    v10 = L"failed to connect to task service";
    goto LABEL_7;
  }
  v18 = *(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 56LL);
  v19 = _bstr_t::_bstr_t((_bstr_t *)&v57, L"\\");
  if ( *(_QWORD *)v19 )
    v20 = **(_QWORD **)v19;
  else
    v20 = 0;
  v21 = v18(ppv, v20, &v72);
  v22 = *(_QWORD *)&v57.vt;
  v23 = v21;
  if ( *(_QWORD *)&v57.vt
    && _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v57.vt + 16LL), 0xFFFFFFFF) == 1
    && v22 )
  {
    if ( *(_QWORD *)v22 )
    {
      SysFreeString(*(BSTR *)v22);
      *(_QWORD *)v22 = 0;
    }
    v24 = *(void **)(v22 + 8);
    if ( v24 )
    {
      operator delete(v24);
      *(_QWORD *)(v22 + 8) = 0;
    }
    operator delete((void *)v22);
  }
  if ( v23 < 0 )
  {
    v55 = 2657;
    v25 = L"failed to get root folder";
LABEL_83:
    UnattendLogW(
      2,
      L"WinReConfigureTask %s (0x%x) in file %S line %d",
      v25,
      (unsigned int)v23,
      "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
      v55);
    v8 = (unsigned __int16)v23;
    goto LABEL_84;
  }
  v26 = *(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 56LL);
  v27 = _bstr_t::_bstr_t((_bstr_t *)&v57, a1);
  if ( *(_QWORD *)v27 )
    v28 = **(_QWORD **)v27;
  else
    v28 = 0;
  v29 = v26(ppv, v28, &v71);
  v30 = *(_QWORD *)&v57.vt;
  v23 = v29;
  if ( *(_QWORD *)&v57.vt
    && _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v57.vt + 16LL), 0xFFFFFFFF) == 1
    && v30 )
  {
    if ( *(_QWORD *)v30 )
    {
      SysFreeString(*(BSTR *)v30);
      *(_QWORD *)v30 = 0;
    }
    v31 = *(void **)(v30 + 8);
    if ( v31 )
    {
      operator delete(v31);
      *(_QWORD *)(v30 + 8) = 0;
    }
    operator delete((void *)v30);
  }
  if ( v23 < 0 )
  {
    v55 = 2660;
    v25 = L"failed to get task folder";
    goto LABEL_83;
  }
  v8 = 0;
  if ( a3 != 2 )
  {
    if ( a3 > 1 )
    {
      v8 = 87;
      goto LABEL_84;
    }
    v46 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v71 + 104LL);
    v47 = _bstr_t::_bstr_t((_bstr_t *)&v57, a2);
    if ( *(_QWORD *)v47 )
      v48 = **(_QWORD **)v47;
    else
      v48 = 0;
    v49 = v46(v71, v48, &v73);
    v51 = *(_QWORD *)&v57.vt;
    v37 = v49;
    if ( *(_QWORD *)&v57.vt
      && _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v57.vt + 16LL), 0xFFFFFFFF) == 1
      && v51 )
    {
      if ( *(_QWORD *)v51 )
      {
        SysFreeString(*(BSTR *)v51);
        *(_QWORD *)v51 = 0;
      }
      v52 = *(void **)(v51 + 8);
      if ( v52 )
      {
        operator delete(v52);
        *(_QWORD *)(v51 + 8) = 0;
      }
      operator delete((void *)v51);
    }
    if ( v37 >= 0 )
    {
      LOWORD(v50) = -(a3 != 1);
      v23 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v73 + 88LL))(v73, v50);
      if ( v23 >= 0 )
        goto LABEL_84;
      v55 = 2680;
      v25 = L"failed to set winre task state";
      goto LABEL_83;
    }
    v56 = 2673;
    v39 = L"failed to get winre task";
LABEL_52:
    UnattendLogW(
      2,
      L"WinReConfigureTask %s (0x%x) in file %S line %d",
      v39,
      (unsigned int)v37,
      "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
      v56);
    v8 = (unsigned __int16)v37;
    goto LABEL_84;
  }
  v32 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v71 + 120LL);
  v33 = _bstr_t::_bstr_t((_bstr_t *)&v57, a2);
  if ( *(_QWORD *)v33 )
    v34 = **(_QWORD **)v33;
  else
    v34 = 0;
  v35 = v32(v71, v34, 0);
  v36 = *(_QWORD *)&v57.vt;
  v37 = v35;
  if ( *(_QWORD *)&v57.vt
    && _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v57.vt + 16LL), 0xFFFFFFFF) == 1
    && v36 )
  {
    if ( *(_QWORD *)v36 )
    {
      SysFreeString(*(BSTR *)v36);
      *(_QWORD *)v36 = 0;
    }
    v38 = *(void **)(v36 + 8);
    if ( v38 )
    {
      operator delete(v38);
      *(_QWORD *)(v36 + 8) = 0;
    }
    operator delete((void *)v36);
  }
  if ( v37 < 0 )
  {
    v56 = 2665;
    v39 = L"failed to delete task";
    goto LABEL_52;
  }
  v40 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v72 + 96LL);
  v41 = _bstr_t::_bstr_t((_bstr_t *)&v57, a1);
  if ( *(_QWORD *)v41 )
    v42 = **(_QWORD **)v41;
  else
    v42 = 0;
  v43 = v40(v72, v42, 0);
  v44 = *(_QWORD *)&v57.vt;
  v37 = v43;
  if ( *(_QWORD *)&v57.vt
    && _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v57.vt + 16LL), 0xFFFFFFFF) == 1
    && v44 )
  {
    if ( *(_QWORD *)v44 )
    {
      SysFreeString(*(BSTR *)v44);
      *(_QWORD *)v44 = 0;
    }
    v45 = *(void **)(v44 + 8);
    if ( v45 )
    {
      operator delete(v45);
      *(_QWORD *)(v44 + 8) = 0;
    }
    operator delete((void *)v44);
  }
  if ( v37 < 0 )
  {
    v56 = 2668;
    v39 = L"failed to delete folder";
    goto LABEL_52;
  }
LABEL_84:
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v72 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
    v72 = 0;
  }
  if ( v71 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
    v71 = 0;
  }
  if ( v73 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
    v73 = 0;
  }
  if ( v9 )
    CoUninitialize();
  UnattendLogW(0, L"Exit WinReConfigureTask return error code: 0x%x", (unsigned int)v8);
  UnattendFinalizeLog();
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180021760  mov     rax, rsp
0x180021763  mov     [rax+20h], rbx
0x180021767  push    rbp
0x180021768  push    rsi
0x180021769  push    rdi
0x18002176a  push    r12
0x18002176c  push    r13
0x18002176e  push    r14
0x180021770  push    r15
0x180021772  lea     rbp, [rax-0E8h]
0x180021779  sub     rsp, 1B0h
0x180021780  movaps  xmmword ptr [rax-48h], xmm6
0x180021784  movaps  xmmword ptr [rax-58h], xmm7
0x180021788  movaps  xmmword ptr [rax-68h], xmm8
0x18002178d  movaps  xmmword ptr [rax-78h], xmm9
0x180021792  movaps  xmmword ptr [rax-88h], xmm10
0x18002179a  movaps  xmmword ptr [rax-98h], xmm11
0x1800217a2  mov     rax, cs:__security_cookie
0x1800217a9  xor     rax, rsp
0x1800217ac  mov     [rbp+0E0h+var_A0], rax
0x1800217b0  xor     r13d, r13d
0x1800217b3  mov     r12, rcx
0x1800217b6  xor     ecx, ecx
0x1800217b8  mov     [rbp+0E0h+var_C0], r13
0x1800217bc  mov     [rbp+0E0h+var_B0], r13
0x1800217c0  mov     r15d, r8d
0x1800217c3  mov     [rbp+0E0h+var_B8], r13
0x1800217c7  mov     r14, rdx
0x1800217ca  mov     [rbp+0E0h+var_A8], r13
0x1800217ce  call    UnattendInitializeLogEx2
0x1800217d3  lea     rdx, aEnterWinreconf; "Enter WinReConfigureTask"
0x1800217da  xor     ecx, ecx
0x1800217dc  call    UnattendLogW
0x1800217e1  lea     rax, aNull_0; "NULL"
0x1800217e8  mov     dword ptr [rsp+1E0h+ppv], r15d
0x1800217ed  test    r14, r14
0x1800217f0  lea     rdx, aParametersTask; "Parameters: TaskFolder: %s, TaskName: %"...
0x1800217f7  mov     r9, r14
0x1800217fa  mov     r8, r12
0x1800217fd  cmovz   r9, rax
0x180021801  test    r12, r12
0x180021804  cmovz   r8, rax
0x180021808  xor     ecx, ecx
0x18002180a  call    UnattendLogW
0x18002180f  xor     edx, edx; dwCoInit
0x180021811  xor     ecx, ecx; pvReserved
0x180021813  call    cs:__imp_CoInitializeEx
0x180021819  mov     ebx, eax
0x18002181b  test    eax, eax
0x18002181d  jns     short loc_180021859
0x18002181f  mov     esi, r13d
0x180021822  mov     [rsp+1E0h+var_1B8], 0A50h
0x18002182a  lea     r8, aFailedToCallCo; "failed to call coinitialize"
0x180021831  lea     rcx, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180021838  mov     r9d, ebx
0x18002183b  mov     [rsp+1E0h+ppv], rcx
0x180021840  lea     rdx, aWinreconfigure_0; "WinReConfigureTask %s (0x%x) in file %S"...
0x180021847  mov     ecx, 2
0x18002184c  call    UnattendLogW
0x180021851  movzx   ebx, bx
0x180021854  jmp     loc_180021D1E
0x180021859  lea     rax, [rbp+0E0h+var_C0]
0x18002185d  mov     esi, 1
0x180021862  mov     r8d, esi; dwClsContext
0x180021865  mov     [rsp+1E0h+ppv], rax; ppv
0x18002186a  lea     r9, IID_ITaskService; riid
0x180021871  xor     edx, edx; pUnkOuter
0x180021873  lea     rcx, CLSID_TaskScheduler; rclsid
0x18002187a  call    cs:__imp_CoCreateInstance
0x180021880  mov     ebx, eax
0x180021882  test    eax, eax
0x180021884  jns     short loc_180021897
0x180021886  mov     [rsp+1E0h+var_1B8], 0A58h
0x18002188e  lea     r8, aFailedToCreate_26; "failed to create task schedule instance"
0x180021895  jmp     short loc_180021831
0x180021897  mov     rax, [rbp+0E0h+var_C0]
0x18002189b  mov     rcx, [rax]
0x18002189e  mov     rbx, [rcx+50h]
0x1800218a2  lea     rcx, [rbp+0E0h+pvarg]; pvarg
0x1800218a6  call    cs:__imp_VariantInit
0x1800218ac  movups  xmm10, xmmword ptr [rbp+0E0h+pvarg]
0x1800218b1  lea     rcx, [rsp+1E0h+var_178+8]; pvarg
0x1800218b6  movsd   xmm11, qword ptr [rbp+0E0h+pvarg+10h]
0x1800218bc  call    cs:__imp_VariantInit
0x1800218c2  movups  xmm8, xmmword ptr [rsp+1E0h+var_178+8]
0x1800218c8  lea     rcx, [rsp+1E0h+var_190+8]; pvarg
0x1800218cd  movsd   xmm9, [rbp+0E0h+var_160]
0x1800218d3  call    cs:__imp_VariantInit
0x1800218d9  movups  xmm6, xmmword ptr [rsp+1E0h+var_190+8]
0x1800218de  lea     rcx, [rsp+1E0h+var_1A8+8]; pvarg
0x1800218e3  movsd   xmm7, qword ptr [rsp+1E0h+var_178]
0x1800218e9  call    cs:__imp_VariantInit
0x1800218ef  movups  xmm0, xmmword ptr [rsp+1E0h+var_1A8+8]
0x1800218f4  lea     rax, [rbp+0E0h+var_140]
0x1800218f8  mov     rcx, [rbp+0E0h+var_C0]
0x1800218fc  movsd   xmm1, qword ptr [rsp+1E0h+var_190]
0x180021902  lea     r9, [rbp+0E0h+var_120]
0x180021906  mov     [rsp+1E0h+ppv], rax
0x18002190b  lea     r8, [rbp+0E0h+var_100]
0x18002190f  mov     rax, rbx
0x180021912  movaps  [rbp+0E0h+var_E0], xmm0
0x180021916  lea     rdx, [rbp+0E0h+var_E0]
0x18002191a  movaps  [rbp+0E0h+var_140], xmm10
0x18002191f  movsd   [rbp+0E0h+var_130], xmm11
0x180021925  movaps  [rbp+0E0h+var_120], xmm8
0x18002192a  movsd   [rbp+0E0h+var_110], xmm9
0x180021930  movaps  [rbp+0E0h+var_100], xmm6
0x180021934  movsd   [rbp+0E0h+var_F0], xmm7
0x180021939  movsd   [rbp+0E0h+var_D0], xmm1
0x18002193e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021943  lea     rcx, [rsp+1E0h+var_1A8+8]; pvarg
0x180021948  mov     ebx, eax
0x18002194a  call    cs:__imp_VariantClear
0x180021950  lea     rcx, [rsp+1E0h+var_190+8]; pvarg
0x180021955  call    cs:__imp_VariantClear
0x18002195b  lea     rcx, [rsp+1E0h+var_178+8]; pvarg
0x180021960  call    cs:__imp_VariantClear
0x180021966  lea     rcx, [rbp+0E0h+pvarg]; pvarg
0x18002196a  call    cs:__imp_VariantClear
0x180021970  test    ebx, ebx
0x180021972  jns     short loc_180021988
0x180021974  mov     [rsp+1E0h+var_1B8], 0A5Eh
0x18002197c  lea     r8, aFailedToConnec; "failed to connect to task service"
0x180021983  jmp     loc_180021831
0x180021988  mov     rax, [rbp+0E0h+var_C0]
0x18002198c  lea     rdx, pszSrc; "\\"
0x180021993  mov     rcx, [rax]
0x180021996  mov     rbx, [rcx+38h]
0x18002199a  lea     rcx, [rsp+1E0h+var_1A8]; this
0x18002199f  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800219a4  mov     rdx, [rax]
0x1800219a7  test    rdx, rdx
0x1800219aa  jz      short loc_1800219B1
0x1800219ac  mov     rdx, [rdx]
0x1800219af  jmp     short loc_1800219B4
0x1800219b1  mov     rdx, r13
0x1800219b4  mov     rcx, [rbp+0E0h+var_C0]
0x1800219b8  lea     r8, [rbp+0E0h+var_B0]
0x1800219bc  mov     rax, rbx
0x1800219bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800219c4  mov     rbx, qword ptr [rsp+1E0h+var_1A8]
0x1800219c9  mov     edi, eax
0x1800219cb  test    rbx, rbx
0x1800219ce  jz      short loc_180021A0C
0x1800219d0  or      ecx, 0FFFFFFFFh
0x1800219d3  lock xadd [rbx+10h], ecx
0x1800219d8  cmp     ecx, esi
0x1800219da  jnz     short loc_180021A0C
0x1800219dc  test    rbx, rbx
0x1800219df  jz      short loc_180021A0C
0x1800219e1  mov     rcx, [rbx]; bstrString
0x1800219e4  test    rcx, rcx
0x1800219e7  jz      short loc_1800219F2
0x1800219e9  call    cs:__imp_SysFreeString
0x1800219ef  mov     [rbx], r13
0x1800219f2  mov     rcx, [rbx+8]; Block
0x1800219f6  test    rcx, rcx
0x1800219f9  jz      short loc_180021A04
0x1800219fb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021a00  mov     [rbx+8], r13
0x180021a04  mov     rcx, rbx; Block
0x180021a07  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021a0c  test    edi, edi
0x180021a0e  jns     short loc_180021A24
0x180021a10  mov     [rsp+1E0h+var_1B8], 0A61h
0x180021a18  lea     r8, aFailedToGetRoo; "failed to get root folder"
0x180021a1f  jmp     loc_180021CFB
0x180021a24  mov     rax, [rbp+0E0h+var_C0]
0x180021a28  mov     rdx, r12; unsigned __int16 *
0x180021a2b  mov     rcx, [rax]
0x180021a2e  mov     rbx, [rcx+38h]
0x180021a32  lea     rcx, [rsp+1E0h+var_1A8]; this
0x180021a37  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180021a3c  mov     rdx, [rax]
0x180021a3f  test    rdx, rdx
0x180021a42  jz      short loc_180021A49
0x180021a44  mov     rdx, [rdx]
0x180021a47  jmp     short loc_180021A4C
0x180021a49  mov     rdx, r13
0x180021a4c  mov     rcx, [rbp+0E0h+var_C0]
0x180021a50  lea     r8, [rbp+0E0h+var_B8]
0x180021a54  mov     rax, rbx
0x180021a57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a5c  mov     rbx, qword ptr [rsp+1E0h+var_1A8]
0x180021a61  mov     edi, eax
0x180021a63  test    rbx, rbx
0x180021a66  jz      short loc_180021AA4
0x180021a68  or      ecx, 0FFFFFFFFh
0x180021a6b  lock xadd [rbx+10h], ecx
0x180021a70  cmp     ecx, esi
0x180021a72  jnz     short loc_180021AA4
0x180021a74  test    rbx, rbx
0x180021a77  jz      short loc_180021AA4
0x180021a79  mov     rcx, [rbx]; bstrString
0x180021a7c  test    rcx, rcx
0x180021a7f  jz      short loc_180021A8A
0x180021a81  call    cs:__imp_SysFreeString
0x180021a87  mov     [rbx], r13
0x180021a8a  mov     rcx, [rbx+8]; Block
0x180021a8e  test    rcx, rcx
0x180021a91  jz      short loc_180021A9C
0x180021a93  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021a98  mov     [rbx+8], r13
0x180021a9c  mov     rcx, rbx; Block
0x180021a9f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021aa4  test    edi, edi
0x180021aa6  jns     short loc_180021ABC
0x180021aa8  mov     [rsp+1E0h+var_1B8], 0A64h
0x180021ab0  lea     r8, aFailedToGetTas; "failed to get task folder"
0x180021ab7  jmp     loc_180021CFB
0x180021abc  mov     ebx, r13d
0x180021abf  cmp     r15d, 2
0x180021ac3  jnz     loc_180021C23
0x180021ac9  mov     rax, [rbp+0E0h+var_B8]
0x180021acd  mov     rdx, r14; unsigned __int16 *
0x180021ad0  mov     rcx, [rax]
0x180021ad3  mov     rdi, [rcx+78h]
0x180021ad7  lea     rcx, [rsp+1E0h+var_1A8]; this
0x180021adc  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180021ae1  mov     rdx, [rax]
0x180021ae4  test    rdx, rdx
0x180021ae7  jz      short loc_180021AEE
0x180021ae9  mov     rdx, [rdx]
0x180021aec  jmp     short loc_180021AF1
0x180021aee  mov     rdx, r13
0x180021af1  mov     rcx, [rbp+0E0h+var_B8]
0x180021af5  xor     r8d, r8d
0x180021af8  mov     rax, rdi
0x180021afb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b00  mov     rdi, qword ptr [rsp+1E0h+var_1A8]
0x180021b05  mov     r14d, eax
0x180021b08  test    rdi, rdi
0x180021b0b  jz      short loc_180021B49
0x180021b0d  or      ecx, 0FFFFFFFFh
0x180021b10  lock xadd [rdi+10h], ecx
0x180021b15  cmp     ecx, esi
0x180021b17  jnz     short loc_180021B49
0x180021b19  test    rdi, rdi
0x180021b1c  jz      short loc_180021B49
0x180021b1e  mov     rcx, [rdi]; bstrString
0x180021b21  test    rcx, rcx
0x180021b24  jz      short loc_180021B2F
0x180021b26  call    cs:__imp_SysFreeString
0x180021b2c  mov     [rdi], r13
0x180021b2f  mov     rcx, [rdi+8]; Block
0x180021b33  test    rcx, rcx
0x180021b36  jz      short loc_180021B41
0x180021b38  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021b3d  mov     [rdi+8], r13
0x180021b41  mov     rcx, rdi; Block
0x180021b44  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021b49  test    r14d, r14d
0x180021b4c  jns     short loc_180021B86
0x180021b4e  mov     [rsp+1E0h+var_1B8], 0A69h
0x180021b56  lea     r8, aFailedToDelete_2; "failed to delete task"
0x180021b5d  lea     rcx, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180021b64  mov     r9d, r14d
0x180021b67  mov     [rsp+1E0h+ppv], rcx
0x180021b6c  lea     rdx, aWinreconfigure_0; "WinReConfigureTask %s (0x%x) in file %S"...
0x180021b73  mov     ecx, 2
0x180021b78  call    UnattendLogW
0x180021b7d  movzx   ebx, r14w
0x180021b81  jmp     loc_180021D1E
0x180021b86  mov     rax, [rbp+0E0h+var_B0]
0x180021b8a  mov     rdx, r12; unsigned __int16 *
0x180021b8d  mov     rcx, [rax]
0x180021b90  mov     rdi, [rcx+60h]
0x180021b94  lea     rcx, [rsp+1E0h+var_1A8]; this
0x180021b99  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180021b9e  mov     rdx, [rax]
0x180021ba1  test    rdx, rdx
0x180021ba4  jz      short loc_180021BAB
0x180021ba6  mov     rdx, [rdx]
0x180021ba9  jmp     short loc_180021BAE
0x180021bab  mov     rdx, r13
0x180021bae  mov     rcx, [rbp+0E0h+var_B0]
0x180021bb2  xor     r8d, r8d
0x180021bb5  mov     rax, rdi
0x180021bb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021bbd  mov     rdi, qword ptr [rsp+1E0h+var_1A8]
0x180021bc2  mov     r14d, eax
0x180021bc5  test    rdi, rdi
0x180021bc8  jz      short loc_180021C06
0x180021bca  or      ecx, 0FFFFFFFFh
0x180021bcd  lock xadd [rdi+10h], ecx
0x180021bd2  cmp     ecx, esi
0x180021bd4  jnz     short loc_180021C06
0x180021bd6  test    rdi, rdi
0x180021bd9  jz      short loc_180021C06
0x180021bdb  mov     rcx, [rdi]; bstrString
0x180021bde  test    rcx, rcx
0x180021be1  jz      short loc_180021BEC
0x180021be3  call    cs:__imp_SysFreeString
0x180021be9  mov     [rdi], r13
0x180021bec  mov     rcx, [rdi+8]; Block
0x180021bf0  test    rcx, rcx
0x180021bf3  jz      short loc_180021BFE
0x180021bf5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021bfa  mov     [rdi+8], r13
0x180021bfe  mov     rcx, rdi; Block
  ... truncated ...
```
