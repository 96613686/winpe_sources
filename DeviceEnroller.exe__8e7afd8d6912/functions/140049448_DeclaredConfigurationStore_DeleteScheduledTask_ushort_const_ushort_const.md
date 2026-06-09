# DeclaredConfigurationStore_DeleteScheduledTask(ushort const *,ushort const *)

- ea: `0x140049448`
- end: `0x14004997d`
- name: `?DeclaredConfigurationStore_DeleteScheduledTask@@YAJPEBG0@Z`
- size: `1333`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140019a6c`

## callees

- `0x1400042f0`
- `0x140004610`
- `0x1400095b4`
- `0x14000a0fc`
- `0x14001ea48`
- `0x14001ef20`
- `0x140049448`
- `0x140049da8`
- `0x14005890c`
- `0x14005d010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1400497ea`
- `OLEAUT32!__imp_SysAllocString` at `0x1400497ea`
- `OLEAUT32!__imp_VariantInit` at `0x140049541`
- `OLEAUT32!__imp_VariantInit` at `0x140049560`
- `OLEAUT32!__imp_VariantInit` at `0x14004957c`
- `OLEAUT32!__imp_VariantInit` at `0x140049593`
- `OLEAUT32!__imp_VariantInit` at `0x140049541`
- `OLEAUT32!__imp_VariantInit` at `0x140049560`
- `OLEAUT32!__imp_VariantInit` at `0x14004957c`
- `OLEAUT32!__imp_VariantInit` at `0x140049593`
- `OLEAUT32!__imp_VariantClear` at `0x140049624`
- `OLEAUT32!__imp_VariantClear` at `0x140049637`
- `OLEAUT32!__imp_VariantClear` at `0x14004964a`
- `OLEAUT32!__imp_VariantClear` at `0x140049660`
- `OLEAUT32!__imp_VariantClear` at `0x140049624`
- `OLEAUT32!__imp_VariantClear` at `0x140049637`
- `OLEAUT32!__imp_VariantClear` at `0x14004964a`
- `OLEAUT32!__imp_VariantClear` at `0x140049660`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400494c3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400494c3`

## string_xrefs

- `0x1400494d7`: `Failed to create instance for CLSID_TaskScheduler`
- `0x14004967a`: `Failed to Connect to TaskService`
- `0x140049832`: `Failed to Get task folder %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DeclaredConfigurationStore_DeleteScheduledTask(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2)
{
  HRESULT v4; // ebx
  LPVOID v6; // rdi
  __int64 (__fastcall *v7)(LPVOID, VARIANTARG *, __int128 *, __int128 *); // rbx
  __int128 v8; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v10; // xmm8
  IRecordInfo *v11; // xmm9_8
  __int128 v12; // xmm6
  IRecordInfo *v13; // xmm7_8
  int v14; // ebx
  HRESULT v15; // eax
  HRESULT v16; // eax
  HRESULT v17; // eax
  HRESULT v18; // eax
  int v19; // eax
  unsigned int v20; // ebx
  int v21; // eax
  unsigned int v22; // ebx
  LPVOID v23; // rsi
  __int64 v24; // r14
  BSTR *v25; // rbx
  BSTR v26; // rax
  int v27; // ebx
  __int64 *v28; // rbx
  __int64 v29; // rdi
  __int64 *v30; // rax
  __int64 v31; // rdx
  unsigned int v32; // edi
  unsigned int v33; // ebx
  char *v34; // [rsp+28h] [rbp-3A0h]
  LPVOID ppv; // [rsp+30h] [rbp-398h] BYREF
  __int64 *v36; // [rsp+38h] [rbp-390h] BYREF
  BSTR *v37; // [rsp+40h] [rbp-388h] BYREF
  VARIANTARG v38; // [rsp+48h] [rbp-380h] BYREF
  VARIANTARG v39; // [rsp+60h] [rbp-368h] BYREF
  VARIANTARG v40; // [rsp+78h] [rbp-350h] BYREF
  VARIANTARG pvarg; // [rsp+90h] [rbp-338h] BYREF
  int v42[4]; // [rsp+B0h] [rbp-318h] BYREF
  IRecordInfo *v43; // [rsp+C0h] [rbp-308h]
  __int128 v44; // [rsp+D0h] [rbp-2F8h] BYREF
  IRecordInfo *v45; // [rsp+E0h] [rbp-2E8h]
  __int128 v46; // [rsp+F0h] [rbp-2D8h] BYREF
  IRecordInfo *v47; // [rsp+100h] [rbp-2C8h]
  VARIANTARG v48; // [rsp+110h] [rbp-2B8h] BYREF
  OLECHAR psz[264]; // [rsp+130h] [rbp-298h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3C8h] [rbp+0h]

  ppv = 0;
  v36 = 0;
  v4 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &ppv);
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xC6F,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\objectmodel\\lib\\cdndownloadapi.cpp",
      (const char *)(unsigned int)v4,
      (int)"Failed to create instance for CLSID_TaskScheduler",
      v34);
    if ( v36 )
      (*(void (__fastcall **)(__int64 *))(*v36 + 16))(v36);
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return (unsigned int)v4;
  }
  v6 = ppv;
  v7 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *))(*(_QWORD *)ppv + 80LL);
  VariantInit(&pvarg);
  v8 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v40);
  v10 = *(_OWORD *)&v40.vt;
  v11 = v40.pRecInfo;
  VariantInit(&v39);
  v12 = *(_OWORD *)&v39.vt;
  v13 = v39.pRecInfo;
  VariantInit(&v38);
  *(_OWORD *)v42 = v8;
  v43 = pRecInfo;
  v44 = v10;
  v45 = v11;
  v46 = v12;
  v47 = v13;
  v48 = v38;
  v14 = v7(v6, &v48, &v46, &v44);
  v15 = VariantClear(&v38);
  if ( v15 < 0 )
    _com_issue_error(v15);
  v16 = VariantClear(&v39);
  if ( v16 < 0 )
    _com_issue_error(v16);
  v17 = VariantClear(&v40);
  if ( v17 < 0 )
    _com_issue_error(v17);
  v18 = VariantClear(&pvarg);
  if ( v18 < 0 )
    _com_issue_error(v18);
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xC72,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\objectmodel\\lib\\cdndownloadapi.cpp",
      (const char *)(unsigned int)v14,
      (int)"Failed to Connect to TaskService",
      v34);
    if ( v36 )
      (*(void (__fastcall **)(__int64 *))(*v36 + 16))(v36);
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return (unsigned int)v14;
  }
  if ( a2 )
  {
    v19 = StringCchPrintfW(psz, 0x104u, L"\\Microsoft\\Windows\\EnterpriseMgmt\\%s", a2);
    v20 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC79,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\objectmodel\\lib\\cdndownloadapi.cpp",
        (const char *)(unsigned int)v19,
        (int)v42);
      if ( v36 )
        (*(void (__fastcall **)(__int64 *))(*v36 + 16))(v36);
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      return v20;
    }
    goto LABEL_30;
  }
  v21 = StringCchPrintfW(psz, 0x104u, L"\\Microsoft\\Windows\\EnterpriseMgmt");
  v22 = v21;
  if ( v21 >= 0 )
  {
LABEL_30:
    v23 = ppv;
    v24 = *(_QWORD *)ppv;
    v25 = (BSTR *)operator new(0x18u);
    v37 = v25;
    v25[1] = 0;
    *((_DWORD *)v25 + 4) = 1;
    v26 = SysAllocString(psz);
    *v25 = v26;
    if ( !v26 )
      _com_issue_error(-2147024882);
    v37 = v25;
    v27 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int64 **))(v24 + 56))(v23, v26, &v36);
    _bstr_t::~_bstr_t((_bstr_t *)&v37);
    if ( v27 >= 0 )
    {
      v28 = v36;
      v29 = *v36;
      v30 = *(__int64 **)_bstr_t::_bstr_t((_bstr_t *)&v37, a1);
      if ( v30 )
        v31 = *v30;
      else
        v31 = 0;
      v32 = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD))(v29 + 120))(v28, v31, 0);
      _bstr_t::~_bstr_t((_bstr_t *)&v37);
      v33 = 0;
      if ( v32 != -2147024894 )
        v33 = v32;
      if ( v36 )
        (*(void (__fastcall **)(__int64 *))(*v36 + 16))(v36);
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      return v33;
    }
    else
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xC83,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\objectmodel\\lib\\cdndownloadapi.cpp",
        (const char *)(unsigned int)v27,
        (int)"Failed to Get task folder %ws",
        (const char *)L"\\Microsoft\\Windows\\EnterpriseMgmt");
      if ( v36 )
        (*(void (__fastcall **)(__int64 *))(*v36 + 16))(v36);
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      return (unsigned int)v27;
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xC7F,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\objectmodel\\lib\\cdndownloadapi.cpp",
    (const char *)(unsigned int)v21,
    (int)v42);
  if ( v36 )
    (*(void (__fastcall **)(__int64 *))(*v36 + 16))(v36);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return v22;
}

```

## disassembly

```asm
0x140049448  mov     rax, rsp
0x14004944b  mov     [rax+18h], rbx
0x14004944f  mov     [rax+20h], rsi
0x140049453  push    rdi
0x140049454  push    r14
0x140049456  push    r15
0x140049458  sub     rsp, 3B0h
0x14004945f  movaps  xmmword ptr [rax-28h], xmm6
0x140049463  movaps  xmmword ptr [rax-38h], xmm7
0x140049467  movaps  xmmword ptr [rax-48h], xmm8
0x14004946c  movaps  xmmword ptr [rax-58h], xmm9
0x140049471  movaps  xmmword ptr [rax-68h], xmm10
0x140049476  movaps  xmmword ptr [rax-78h], xmm11
0x14004947b  mov     rax, cs:__security_cookie
0x140049482  xor     rax, rsp
0x140049485  mov     [rsp+3C8h+var_88], rax
0x14004948d  mov     rsi, rdx
0x140049490  mov     r15, rcx
0x140049493  mov     [rsp+3C8h+var_398], 0
0x14004949c  mov     [rsp+3C8h+var_390], 0
0x1400494a5  lea     rax, [rsp+3C8h+var_398]
0x1400494aa  mov     [rsp+3C8h+ppv], rax; ppv
0x1400494af  lea     r9, IID_ITaskService; riid
0x1400494b6  xor     edx, edx; pUnkOuter
0x1400494b8  lea     r8d, [rdx+1]; dwClsContext
0x1400494bc  lea     rcx, CLSID_TaskScheduler; rclsid
0x1400494c3  call    cs:__imp_CoCreateInstance
0x1400494c9  mov     ebx, eax
0x1400494cb  test    eax, eax
0x1400494cd  jns     short loc_14004952D
0x1400494cf  mov     rcx, [rsp+3C8h]; this
0x1400494d7  lea     rax, aFailedToCreate; "Failed to create instance for CLSID_Tas"...
0x1400494de  mov     [rsp+3C8h+ppv], rax; int
0x1400494e3  mov     r9d, ebx; char *
0x1400494e6  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x1400494ed  mov     edx, 0C6Fh; void *
0x1400494f2  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1400494f7  nop
0x1400494f8  mov     rcx, [rsp+3C8h+var_390]
0x1400494fd  test    rcx, rcx
0x140049500  jz      short loc_14004950F
0x140049502  mov     rax, [rcx]
0x140049505  mov     rax, [rax+10h]
0x140049509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004950e  nop
0x14004950f  mov     rcx, [rsp+3C8h+var_398]
0x140049514  test    rcx, rcx
0x140049517  jz      short loc_140049526
0x140049519  mov     rax, [rcx]
0x14004951c  mov     rax, [rax+10h]
0x140049520  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140049525  nop
0x140049526  mov     eax, ebx
0x140049528  jmp     loc_14004990A
0x14004952d  mov     rdi, [rsp+3C8h+var_398]
0x140049532  mov     rax, [rdi]
0x140049535  mov     rbx, [rax+50h]
0x140049539  lea     rcx, [rsp+3C8h+pvarg]; pvarg
0x140049541  call    cs:__imp_VariantInit
0x140049547  nop
0x140049548  movups  xmm10, xmmword ptr [rsp+3C8h+pvarg]
0x140049551  movsd   xmm11, qword ptr [rsp+3C8h+pvarg+10h]
0x14004955b  lea     rcx, [rsp+3C8h+var_350]; pvarg
0x140049560  call    cs:__imp_VariantInit
0x140049566  nop
0x140049567  movups  xmm8, xmmword ptr [rsp+3C8h+var_350]
0x14004956d  movsd   xmm9, qword ptr [rsp+3C8h+var_350+10h]
0x140049577  lea     rcx, [rsp+3C8h+var_368]; pvarg
0x14004957c  call    cs:__imp_VariantInit
0x140049582  nop
0x140049583  movups  xmm6, xmmword ptr [rsp+3C8h+var_368]
0x140049588  movsd   xmm7, qword ptr [rsp+3C8h+var_368+10h]
0x14004958e  lea     rcx, [rsp+3C8h+var_380]; pvarg
0x140049593  call    cs:__imp_VariantInit
0x140049599  nop
0x14004959a  movups  xmm0, xmmword ptr [rsp+3C8h+var_380]
0x14004959f  movsd   xmm1, qword ptr [rsp+3C8h+var_380+10h]
0x1400495a5  movaps  xmmword ptr [rsp+3C8h+var_318], xmm10
0x1400495ae  movsd   [rsp+3C8h+var_308], xmm11
0x1400495b8  movaps  [rsp+3C8h+var_2F8], xmm8
0x1400495c1  movsd   [rsp+3C8h+var_2E8], xmm9
0x1400495cb  movaps  [rsp+3C8h+var_2D8], xmm6
0x1400495d3  movsd   [rsp+3C8h+var_2C8], xmm7
0x1400495dc  movaps  [rsp+3C8h+var_2B8], xmm0
0x1400495e4  movsd   [rsp+3C8h+var_2A8], xmm1
0x1400495ed  lea     rax, [rsp+3C8h+var_318]
0x1400495f5  mov     [rsp+3C8h+ppv], rax; int
0x1400495fa  lea     r9, [rsp+3C8h+var_2F8]
0x140049602  lea     r8, [rsp+3C8h+var_2D8]
0x14004960a  lea     rdx, [rsp+3C8h+var_2B8]
0x140049612  mov     rcx, rdi
0x140049615  mov     rax, rbx
0x140049618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004961d  mov     ebx, eax
0x14004961f  lea     rcx, [rsp+3C8h+var_380]; pvarg
0x140049624  call    cs:__imp_VariantClear
0x14004962a  test    eax, eax
0x14004962c  js      loc_140049951
0x140049632  lea     rcx, [rsp+3C8h+var_368]; pvarg
0x140049637  call    cs:__imp_VariantClear
0x14004963d  test    eax, eax
0x14004963f  js      loc_140049959
0x140049645  lea     rcx, [rsp+3C8h+var_350]; pvarg
0x14004964a  call    cs:__imp_VariantClear
0x140049650  test    eax, eax
0x140049652  js      loc_140049961
0x140049658  lea     rcx, [rsp+3C8h+pvarg]; pvarg
0x140049660  call    cs:__imp_VariantClear
0x140049666  test    eax, eax
0x140049668  js      loc_140049969
0x14004966e  test    ebx, ebx
0x140049670  jns     short loc_1400496D0
0x140049672  mov     rcx, [rsp+3C8h]; this
0x14004967a  lea     rax, aFailedToConnec; "Failed to Connect to TaskService"
0x140049681  mov     [rsp+3C8h+ppv], rax; int
0x140049686  mov     r9d, ebx; char *
0x140049689  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x140049690  mov     edx, 0C72h; void *
0x140049695  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x14004969a  nop
0x14004969b  mov     rcx, [rsp+3C8h+var_390]
0x1400496a0  test    rcx, rcx
0x1400496a3  jz      short loc_1400496B2
0x1400496a5  mov     rax, [rcx]
0x1400496a8  mov     rax, [rax+10h]
0x1400496ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400496b1  nop
0x1400496b2  mov     rcx, [rsp+3C8h+var_398]
0x1400496b7  test    rcx, rcx
0x1400496ba  jz      short loc_1400496C9
0x1400496bc  mov     rax, [rcx]
0x1400496bf  mov     rax, [rax+10h]
0x1400496c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400496c8  nop
0x1400496c9  mov     eax, ebx
0x1400496cb  jmp     loc_14004990A
0x1400496d0  mov     edx, 104h; unsigned __int64
0x1400496d5  lea     rcx, [rsp+3C8h+psz]; unsigned __int16 *
0x1400496dd  test    rsi, rsi
0x1400496e0  jz      short loc_140049752
0x1400496e2  mov     r9, rsi
0x1400496e5  lea     r8, aMicrosoftWindo_3; "\\Microsoft\\Windows\\EnterpriseMgmt\\%"...
0x1400496ec  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400496f1  mov     ebx, eax
0x1400496f3  test    eax, eax
0x1400496f5  jns     short loc_140049749
0x1400496f7  mov     rcx, [rsp+3C8h]; this
0x1400496ff  mov     r9d, eax; char *
0x140049702  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x140049709  mov     edx, 0C79h; void *
0x14004970e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140049713  nop
0x140049714  mov     rcx, [rsp+3C8h+var_390]
0x140049719  test    rcx, rcx
0x14004971c  jz      short loc_14004972B
0x14004971e  mov     rax, [rcx]
0x140049721  mov     rax, [rax+10h]
0x140049725  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004972a  nop
0x14004972b  mov     rcx, [rsp+3C8h+var_398]
0x140049730  test    rcx, rcx
0x140049733  jz      short loc_140049742
0x140049735  mov     rax, [rcx]
0x140049738  mov     rax, [rax+10h]
0x14004973c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140049741  nop
0x140049742  mov     eax, ebx
0x140049744  jmp     loc_14004990A
0x140049749  lea     rdi, aMicrosoftWindo_4; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x140049750  jmp     short loc_1400497B9
0x140049752  lea     rdi, aMicrosoftWindo_4; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x140049759  mov     r8, rdi; unsigned __int16 *
0x14004975c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140049761  mov     ebx, eax
0x140049763  test    eax, eax
0x140049765  jns     short loc_1400497B9
0x140049767  mov     rcx, [rsp+3C8h]; this
0x14004976f  mov     r9d, eax; char *
0x140049772  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x140049779  mov     edx, 0C7Fh; void *
0x14004977e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140049783  nop
0x140049784  mov     rcx, [rsp+3C8h+var_390]
0x140049789  test    rcx, rcx
0x14004978c  jz      short loc_14004979B
0x14004978e  mov     rax, [rcx]
0x140049791  mov     rax, [rax+10h]
0x140049795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004979a  nop
0x14004979b  mov     rcx, [rsp+3C8h+var_398]
0x1400497a0  test    rcx, rcx
0x1400497a3  jz      short loc_1400497B2
0x1400497a5  mov     rax, [rcx]
0x1400497a8  mov     rax, [rax+10h]
0x1400497ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400497b1  nop
0x1400497b2  mov     eax, ebx
0x1400497b4  jmp     loc_14004990A
0x1400497b9  mov     rsi, [rsp+3C8h+var_398]
0x1400497be  mov     r14, [rsi]
0x1400497c1  mov     ecx, 18h; Size
0x1400497c6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400497cb  mov     rbx, rax
0x1400497ce  mov     [rsp+3C8h+var_388], rax
0x1400497d3  mov     qword ptr [rax+8], 0
0x1400497db  mov     dword ptr [rax+10h], 1
0x1400497e2  lea     rcx, [rsp+3C8h+psz]; psz
0x1400497ea  call    cs:__imp_SysAllocString
0x1400497f0  mov     [rbx], rax
0x1400497f3  test    rax, rax
0x1400497f6  jz      loc_140049971
0x1400497fc  mov     [rsp+3C8h+var_388], rbx
0x140049801  lea     r8, [rsp+3C8h+var_390]
0x140049806  mov     rdx, rax
0x140049809  mov     rcx, rsi
0x14004980c  mov     rax, [r14+38h]
0x140049810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140049815  mov     ebx, eax
0x140049817  lea     rcx, [rsp+3C8h+var_388]; this
0x14004981c  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x140049821  test    ebx, ebx
0x140049823  jns     short loc_140049888
0x140049825  mov     rcx, [rsp+3C8h]; this
0x14004982d  mov     [rsp+3C8h+var_3A0], rdi; char *
0x140049832  lea     rax, aFailedToGetTas; "Failed to Get task folder %ws"
0x140049839  mov     [rsp+3C8h+ppv], rax; int
0x14004983e  mov     r9d, ebx; char *
0x140049841  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x140049848  mov     edx, 0C83h; void *
0x14004984d  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x140049852  nop
0x140049853  mov     rcx, [rsp+3C8h+var_390]
0x140049858  test    rcx, rcx
0x14004985b  jz      short loc_14004986A
0x14004985d  mov     rax, [rcx]
0x140049860  mov     rax, [rax+10h]
0x140049864  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140049869  nop
0x14004986a  mov     rcx, [rsp+3C8h+var_398]
0x14004986f  test    rcx, rcx
0x140049872  jz      short loc_140049881
0x140049874  mov     rax, [rcx]
0x140049877  mov     rax, [rax+10h]
0x14004987b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140049880  nop
0x140049881  mov     eax, ebx
0x140049883  jmp     loc_14004990A
0x140049888  mov     rbx, [rsp+3C8h+var_390]
0x14004988d  mov     rdi, [rbx]
0x140049890  mov     rdx, r15; unsigned __int16 *
0x140049893  lea     rcx, [rsp+3C8h+var_388]; this
0x140049898  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14004989d  nop
0x14004989e  mov     rax, [rax]
0x1400498a1  test    rax, rax
0x1400498a4  jz      short loc_1400498AB
0x1400498a6  mov     rdx, [rax]
0x1400498a9  jmp     short loc_1400498AD
0x1400498ab  xor     edx, edx
0x1400498ad  xor     r8d, r8d
0x1400498b0  mov     rcx, rbx
0x1400498b3  mov     rax, [rdi+78h]
0x1400498b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400498bc  mov     edi, eax
0x1400498be  lea     rcx, [rsp+3C8h+var_388]; this
0x1400498c3  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1400498c8  nop
0x1400498c9  xor     ebx, ebx
0x1400498cb  cmp     edi, 80070002h
0x1400498d1  cmovnz  ebx, edi
0x1400498d4  mov     rcx, [rsp+3C8h+var_390]
0x1400498d9  test    rcx, rcx
0x1400498dc  jz      short loc_1400498EB
0x1400498de  mov     rax, [rcx]
0x1400498e1  mov     rax, [rax+10h]
0x1400498e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400498ea  nop
0x1400498eb  mov     rcx, [rsp+3C8h+var_398]
0x1400498f0  test    rcx, rcx
0x1400498f3  jz      short loc_140049902
0x1400498f5  mov     rax, [rcx]
0x1400498f8  mov     rax, [rax+10h]
0x1400498fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140049901  nop
0x140049902  jmp     short loc_140049908
0x140049904  mov     ebx, dword ptr [rsp+3C8h+var_398]
0x140049908  mov     eax, ebx
0x14004990a  mov     rcx, [rsp+3C8h+var_88]
0x140049912  xor     rcx, rsp; StackCookie
0x140049915  call    __security_check_cookie
0x14004991a  lea     r11, [rsp+3C8h+var_18]
0x140049922  mov     rbx, [r11+30h]
0x140049926  mov     rsi, [r11+38h]
0x14004992a  movaps  xmm6, xmmword ptr [r11-10h]
0x14004992f  movaps  xmm7, xmmword ptr [r11-20h]
0x140049934  movaps  xmm8, xmmword ptr [r11-30h]
0x140049939  movaps  xmm9, xmmword ptr [r11-40h]
0x14004993e  movaps  xmm10, xmmword ptr [r11-50h]
0x140049943  movaps  xmm11, xmmword ptr [r11-60h]
0x140049948  mov     rsp, r11
  ... truncated ...
```
