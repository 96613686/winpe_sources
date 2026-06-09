# ScheduledTaskUtils::DeleteNotificationTask(void)

- ea: `0x180054354`
- end: `0x1800546a3`
- name: `?DeleteNotificationTask@ScheduledTaskUtils@@SAJXZ`
- size: `847`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180035590`

## callees

- `0x18000abc4`
- `0x18001055c`
- `0x18001208c`
- `0x180053c18`
- `0x180053d00`
- `0x180054354`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800543b9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800543b9`
- `OLEAUT32!__imp_SysFreeString` at `0x180054556`
- `OLEAUT32!__imp_SysFreeString` at `0x18005461c`
- `OLEAUT32!__imp_SysFreeString` at `0x180054556`
- `OLEAUT32!__imp_SysFreeString` at `0x18005461c`
- `OLEAUT32!__imp_VariantInit` at `0x1800543e5`
- `OLEAUT32!__imp_VariantInit` at `0x1800543fd`
- `OLEAUT32!__imp_VariantInit` at `0x180054416`
- `OLEAUT32!__imp_VariantInit` at `0x18005442d`
- `OLEAUT32!__imp_VariantInit` at `0x1800543e5`
- `OLEAUT32!__imp_VariantInit` at `0x1800543fd`
- `OLEAUT32!__imp_VariantInit` at `0x180054416`
- `OLEAUT32!__imp_VariantInit` at `0x18005442d`

## string_xrefs

- `0x1800544c0`: `onecore\base\diagnosis\mitigation\client\libs\utils\scheduledtaskutils.cpp`
- `0x18005458f`: `onecore\base\diagnosis\mitigation\client\libs\utils\scheduledtaskutils.cpp`
- `0x1800545c7`: `RecommendedTroubleshootingNotifier`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 ScheduledTaskUtils::DeleteNotificationTask(void)
{
  HRESULT v0; // eax
  int v1; // ebx
  unsigned __int64 v2; // r9
  __int64 v3; // rdx
  LPVOID v4; // rdi
  __int64 (__fastcall *v5)(LPVOID, VARIANTARG *, __int128 *, __int128 *); // rbx
  __int128 v6; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v8; // xmm8
  IRecordInfo *v9; // xmm9_8
  __int128 v10; // xmm6
  IRecordInfo *v11; // xmm7_8
  LPVOID v12; // rbx
  __int64 (__fastcall *v13)(LPVOID, _QWORD *, __int64 *); // rdi
  _QWORD *v14; // rdx
  unsigned __int64 v15; // rdx
  int v16; // edi
  BSTR *v17; // rbx
  BSTR v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rbx
  __int64 (__fastcall *v21)(__int64, _QWORD *, _QWORD); // rdi
  _QWORD *v22; // rdx
  unsigned __int64 v23; // rdx
  BSTR *v24; // rbx
  BSTR v25; // rcx
  int *ppv; // [rsp+20h] [rbp-E0h]
  VARIANTARG v28; // [rsp+30h] [rbp-D0h] BYREF
  VARIANTARG v29; // [rsp+48h] [rbp-B8h] BYREF
  VARIANTARG v30; // [rsp+60h] [rbp-A0h] BYREF
  VARIANTARG pvarg; // [rsp+78h] [rbp-88h] BYREF
  int v32[4]; // [rsp+90h] [rbp-70h] BYREF
  IRecordInfo *v33; // [rsp+A0h] [rbp-60h]
  __int128 v34; // [rsp+B0h] [rbp-50h] BYREF
  IRecordInfo *v35; // [rsp+C0h] [rbp-40h]
  __int128 v36; // [rsp+D0h] [rbp-30h] BYREF
  IRecordInfo *v37; // [rsp+E0h] [rbp-20h]
  VARIANTARG v38; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]
  __int64 v40; // [rsp+198h] [rbp+98h] BYREF
  LPVOID v41; // [rsp+1A0h] [rbp+A0h] BYREF
  void *v42; // [rsp+1A8h] [rbp+A8h] BYREF

  v41 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v41);
  v0 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &v41);
  v1 = v0;
  if ( v0 < 0 )
  {
    v2 = (unsigned int)v0;
    v3 = 80;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\utils\\scheduledtaskutils.cpp",
      (const char *)v2,
      (int)ppv);
    goto LABEL_32;
  }
  v4 = v41;
  v5 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *))(*(_QWORD *)v41 + 80LL);
  VariantInit(&pvarg);
  v6 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v30);
  v8 = *(_OWORD *)&v30.vt;
  v9 = v30.pRecInfo;
  VariantInit(&v29);
  v10 = *(_OWORD *)&v29.vt;
  v11 = v29.pRecInfo;
  VariantInit(&v28);
  *(_OWORD *)v32 = v6;
  v33 = pRecInfo;
  v34 = v8;
  v35 = v9;
  v36 = v10;
  v37 = v11;
  v38 = v28;
  ppv = v32;
  v1 = v5(v4, &v38, &v36, &v34);
  _variant_t::~_variant_t((_variant_t *)&v28);
  _variant_t::~_variant_t((_variant_t *)&v29);
  _variant_t::~_variant_t((_variant_t *)&v30);
  _variant_t::~_variant_t((_variant_t *)&pvarg);
  if ( v1 < 0 )
  {
    v2 = (unsigned int)v1;
    v3 = 81;
    goto LABEL_5;
  }
  v40 = 0;
  v12 = v41;
  v13 = *(__int64 (__fastcall **)(LPVOID, _QWORD *, __int64 *))(*(_QWORD *)v41 + 56LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v40);
  v14 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)&v42, L"\\Microsoft\\Windows\\Diagnosis");
  if ( v14 )
    v14 = (_QWORD *)*v14;
  v16 = v13(v12, v14, &v40);
  v17 = (BSTR *)v42;
  if ( v42 && _InterlockedExchangeAdd((volatile signed __int32 *)v42 + 4, 0xFFFFFFFF) == 1 && v17 )
  {
    if ( *v17 )
    {
      SysFreeString(*v17);
      *v17 = 0;
    }
    v18 = v17[1];
    if ( v18 )
    {
      operator delete(v18, v15);
      v17[1] = 0;
    }
    operator delete(v17, 0x18u);
  }
  if ( v16 >= 0 )
  {
    v20 = v40;
    v21 = *(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD))(*(_QWORD *)v40 + 120LL);
    v22 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)&v42, L"RecommendedTroubleshootingNotifier");
    if ( v22 )
      v22 = (_QWORD *)*v22;
    v16 = v21(v20, v22, 0);
    v24 = (BSTR *)v42;
    if ( v42 && _InterlockedExchangeAdd((volatile signed __int32 *)v42 + 4, 0xFFFFFFFF) == 1 && v24 )
    {
      if ( *v24 )
      {
        SysFreeString(*v24);
        *v24 = 0;
      }
      v25 = v24[1];
      if ( v25 )
      {
        operator delete(v25, v23);
        v24[1] = 0;
      }
      operator delete(v24, 0x18u);
    }
    if ( v16 >= 0 )
    {
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v40);
      v1 = 0;
      goto LABEL_32;
    }
    v19 = 86;
  }
  else
  {
    v19 = 84;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v19,
    (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\utils\\scheduledtaskutils.cpp",
    (const char *)(unsigned int)v16,
    (int)v32);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v40);
  v1 = v16;
LABEL_32:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v41);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180054354  mov     rax, rsp
0x180054357  push    rbp
0x180054358  push    rbx
0x180054359  push    rdi
0x18005435a  lea     rbp, [rsp-70h]
0x18005435f  sub     rsp, 170h
0x180054366  movaps  xmmword ptr [rax-28h], xmm6
0x18005436a  movaps  xmmword ptr [rax-38h], xmm7
0x18005436e  movaps  xmmword ptr [rax-48h], xmm8
0x180054373  movaps  xmmword ptr [rax-58h], xmm9
0x180054378  movaps  xmmword ptr [rax-68h], xmm10
0x18005437d  movaps  xmmword ptr [rax-78h], xmm11
0x180054382  mov     [rbp+80h+arg_10], 0
0x18005438d  lea     rcx, [rbp+80h+arg_10]
0x180054394  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180054399  lea     rax, [rbp+80h+arg_10]
0x1800543a0  mov     [rsp+180h+ppv], rax; ppv
0x1800543a5  lea     r9, IID_ITaskService; riid
0x1800543ac  xor     edx, edx; pUnkOuter
0x1800543ae  lea     r8d, [rdx+1]; dwClsContext
0x1800543b2  lea     rcx, CLSID_TaskScheduler; rclsid
0x1800543b9  call    cs:__imp_CoCreateInstance
0x1800543bf  mov     ebx, eax
0x1800543c1  test    eax, eax
0x1800543c3  jns     short loc_1800543D2
0x1800543c5  mov     r9d, eax
0x1800543c8  mov     edx, 50h ; 'P'
0x1800543cd  jmp     loc_1800544C0
0x1800543d2  mov     rdi, [rbp+80h+arg_10]
0x1800543d9  mov     rax, [rdi]
0x1800543dc  mov     rbx, [rax+50h]
0x1800543e0  lea     rcx, [rsp+180h+pvarg]; pvarg
0x1800543e5  call    cs:__imp_VariantInit
0x1800543eb  nop
0x1800543ec  movups  xmm10, xmmword ptr [rsp+180h+pvarg]
0x1800543f2  movsd   xmm11, qword ptr [rbp+80h+pvarg+10h]
0x1800543f8  lea     rcx, [rsp+180h+var_120]; pvarg
0x1800543fd  call    cs:__imp_VariantInit
0x180054403  nop
0x180054404  movups  xmm8, xmmword ptr [rsp+180h+var_120]
0x18005440a  movsd   xmm9, qword ptr [rsp+180h+var_120+10h]
0x180054411  lea     rcx, [rsp+180h+var_138]; pvarg
0x180054416  call    cs:__imp_VariantInit
0x18005441c  nop
0x18005441d  movups  xmm6, xmmword ptr [rsp+180h+var_138]
0x180054422  movsd   xmm7, qword ptr [rsp+180h+var_138+10h]
0x180054428  lea     rcx, [rsp+180h+var_150]; pvarg
0x18005442d  call    cs:__imp_VariantInit
0x180054433  nop
0x180054434  movups  xmm0, xmmword ptr [rsp+180h+var_150]
0x180054439  movsd   xmm1, qword ptr [rsp+180h+var_150+10h]
0x18005443f  movaps  xmmword ptr [rbp+80h+var_F0], xmm10
0x180054444  movsd   [rbp+80h+var_E0], xmm11
0x18005444a  movaps  [rbp+80h+var_D0], xmm8
0x18005444f  movsd   [rbp+80h+var_C0], xmm9
0x180054455  movaps  [rbp+80h+var_B0], xmm6
0x180054459  movsd   [rbp+80h+var_A0], xmm7
0x18005445e  movaps  [rbp+80h+var_90], xmm0
0x180054462  movsd   [rbp+80h+var_80], xmm1
0x180054467  lea     rax, [rbp+80h+var_F0]
0x18005446b  mov     [rsp+180h+ppv], rax; int
0x180054470  lea     r9, [rbp+80h+var_D0]
0x180054474  lea     r8, [rbp+80h+var_B0]
0x180054478  lea     rdx, [rbp+80h+var_90]
0x18005447c  mov     rcx, rdi
0x18005447f  mov     rax, rbx
0x180054482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054487  mov     ebx, eax
0x180054489  lea     rcx, [rsp+180h+var_150]; this
0x18005448e  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180054493  nop
0x180054494  lea     rcx, [rsp+180h+var_138]; this
0x180054499  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18005449e  nop
0x18005449f  lea     rcx, [rsp+180h+var_120]; this
0x1800544a4  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800544a9  nop
0x1800544aa  lea     rcx, [rsp+180h+pvarg]; this
0x1800544af  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800544b4  test    ebx, ebx
0x1800544b6  jns     short loc_1800544D8
0x1800544b8  mov     r9d, ebx; char *
0x1800544bb  mov     edx, 51h ; 'Q'; void *
0x1800544c0  lea     r8, aOnecoreBaseDia_26; "onecore\\base\\diagnosis\\mitigation\\c"...
0x1800544c7  mov     rcx, [rbp+88h]; this
0x1800544ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800544d3  jmp     loc_180054668
0x1800544d8  mov     [rbp+80h+arg_8], 0
0x1800544e3  mov     rbx, [rbp+80h+arg_10]
0x1800544ea  mov     rax, [rbx]
0x1800544ed  mov     rdi, [rax+38h]
0x1800544f1  lea     rcx, [rbp+80h+arg_8]
0x1800544f8  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800544fd  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\Diagnosis"
0x180054504  lea     rcx, [rbp+80h+arg_18]; this
0x18005450b  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180054510  nop
0x180054511  mov     rdx, [rax]
0x180054514  test    rdx, rdx
0x180054517  jz      short loc_18005451C
0x180054519  mov     rdx, [rdx]
0x18005451c  lea     r8, [rbp+80h+arg_8]
0x180054523  mov     rcx, rbx
0x180054526  mov     rax, rdi
0x180054529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005452e  mov     edi, eax
0x180054530  mov     rbx, [rbp+80h+arg_18]
0x180054537  test    rbx, rbx
0x18005453a  jz      short loc_180054586
0x18005453c  or      ecx, 0FFFFFFFFh
0x18005453f  lock xadd [rbx+10h], ecx
0x180054544  cmp     ecx, 1
0x180054547  jnz     short loc_180054586
0x180054549  test    rbx, rbx
0x18005454c  jz      short loc_180054586
0x18005454e  mov     rcx, [rbx]; bstrString
0x180054551  test    rcx, rcx
0x180054554  jz      short loc_180054563
0x180054556  call    cs:__imp_SysFreeString
0x18005455c  mov     qword ptr [rbx], 0
0x180054563  mov     rcx, [rbx+8]; void *
0x180054567  test    rcx, rcx
0x18005456a  jz      short loc_180054579
0x18005456c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180054571  mov     qword ptr [rbx+8], 0
0x180054579  mov     edx, 18h; unsigned __int64
0x18005457e  mov     rcx, rbx; void *
0x180054581  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180054586  test    edi, edi
0x180054588  jns     short loc_1800545B9
0x18005458a  mov     edx, 54h ; 'T'; void *
0x18005458f  lea     r8, aOnecoreBaseDia_26; "onecore\\base\\diagnosis\\mitigation\\c"...
0x180054596  mov     r9d, edi; char *
0x180054599  mov     rcx, [rbp+88h]; this
0x1800545a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800545a5  nop
0x1800545a6  lea     rcx, [rbp+80h+arg_8]
0x1800545ad  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800545b2  mov     ebx, edi
0x1800545b4  jmp     loc_180054668
0x1800545b9  mov     rbx, [rbp+80h+arg_8]
0x1800545c0  mov     rax, [rbx]
0x1800545c3  mov     rdi, [rax+78h]
0x1800545c7  lea     rdx, aRecommendedtro_1; "RecommendedTroubleshootingNotifier"
0x1800545ce  lea     rcx, [rbp+80h+arg_18]; this
0x1800545d5  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800545da  nop
0x1800545db  mov     rdx, [rax]
0x1800545de  test    rdx, rdx
0x1800545e1  jz      short loc_1800545E6
0x1800545e3  mov     rdx, [rdx]
0x1800545e6  xor     r8d, r8d
0x1800545e9  mov     rcx, rbx
0x1800545ec  mov     rax, rdi
0x1800545ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800545f4  mov     edi, eax
0x1800545f6  mov     rbx, [rbp+80h+arg_18]
0x1800545fd  test    rbx, rbx
0x180054600  jz      short loc_18005464C
0x180054602  or      ecx, 0FFFFFFFFh
0x180054605  lock xadd [rbx+10h], ecx
0x18005460a  cmp     ecx, 1
0x18005460d  jnz     short loc_18005464C
0x18005460f  test    rbx, rbx
0x180054612  jz      short loc_18005464C
0x180054614  mov     rcx, [rbx]; bstrString
0x180054617  test    rcx, rcx
0x18005461a  jz      short loc_180054629
0x18005461c  call    cs:__imp_SysFreeString
0x180054622  mov     qword ptr [rbx], 0
0x180054629  mov     rcx, [rbx+8]; void *
0x18005462d  test    rcx, rcx
0x180054630  jz      short loc_18005463F
0x180054632  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180054637  mov     qword ptr [rbx+8], 0
0x18005463f  mov     edx, 18h; unsigned __int64
0x180054644  mov     rcx, rbx; void *
0x180054647  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005464c  test    edi, edi
0x18005464e  jns     short loc_18005465A
0x180054650  mov     edx, 56h ; 'V'
0x180054655  jmp     loc_18005458F
0x18005465a  lea     rcx, [rbp+80h+arg_8]
0x180054661  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180054666  xor     ebx, ebx
0x180054668  lea     rcx, [rbp+80h+arg_10]
0x18005466f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180054674  mov     eax, ebx
0x180054676  lea     r11, [rsp+180h+var_10]
0x18005467e  movaps  xmm6, xmmword ptr [r11-10h]
0x180054683  movaps  xmm7, xmmword ptr [r11-20h]
0x180054688  movaps  xmm8, xmmword ptr [r11-30h]
0x18005468d  movaps  xmm9, xmmword ptr [r11-40h]
0x180054692  movaps  xmm10, xmmword ptr [r11-50h]
0x180054697  movaps  xmm11, xmmword ptr [r11-60h]
0x18005469c  mov     rsp, r11
0x18005469f  pop     rdi
0x1800546a0  pop     rbx
0x1800546a1  pop     rbp
0x1800546a2  retn
```
