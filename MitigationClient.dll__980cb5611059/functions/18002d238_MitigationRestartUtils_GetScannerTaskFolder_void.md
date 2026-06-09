# MitigationRestartUtils::GetScannerTaskFolder(void)

- ea: `0x18002d238`
- end: `0x18002d4a8`
- name: `?GetScannerTaskFolder@MitigationRestartUtils@@SA?AV?$com_ptr_t@UITaskFolder@@Uerr_exception_policy@wil@@@wil@@XZ`
- size: `624`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002d6dc`

## callees

- `0x18002cf48`
- `0x18002cf78`
- `0x18002d238`
- `0x18002db58`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002d2a4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002d2a4`
- `OLEAUT32!__imp_SysAllocString` at `0x18002d3d2`
- `OLEAUT32!__imp_SysAllocString` at `0x18002d3d2`
- `OLEAUT32!__imp_VariantInit` at `0x18002d2dc`
- `OLEAUT32!__imp_VariantInit` at `0x18002d2f3`
- `OLEAUT32!__imp_VariantInit` at `0x18002d30c`
- `OLEAUT32!__imp_VariantInit` at `0x18002d323`
- `OLEAUT32!__imp_VariantInit` at `0x18002d2dc`
- `OLEAUT32!__imp_VariantInit` at `0x18002d2f3`
- `OLEAUT32!__imp_VariantInit` at `0x18002d30c`
- `OLEAUT32!__imp_VariantInit` at `0x18002d323`
- `OLEAUT32!__imp_VariantClear` at `0x18002d3a2`
- `OLEAUT32!__imp_VariantClear` at `0x18002d3ae`
- `OLEAUT32!__imp_VariantClear` at `0x18002d3ba`
- `OLEAUT32!__imp_VariantClear` at `0x18002d3c5`
- `OLEAUT32!__imp_VariantClear` at `0x18002d3a2`
- `OLEAUT32!__imp_VariantClear` at `0x18002d3ae`
- `OLEAUT32!__imp_VariantClear` at `0x18002d3ba`
- `OLEAUT32!__imp_VariantClear` at `0x18002d3c5`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
_QWORD *__fastcall MitigationRestartUtils::GetScannerTaskFolder(_QWORD *a1)
{
  HRESULT v2; // eax
  LPVOID v3; // rdi
  __int64 (__fastcall *v4)(LPVOID, VARIANTARG *, __int128 *, __int128 *); // rbx
  __int128 v5; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v7; // xmm8
  IRecordInfo *v8; // xmm9_8
  __int128 v9; // xmm6
  IRecordInfo *v10; // xmm7_8
  int v11; // eax
  BSTR v12; // rax
  LPVOID v13; // rcx
  __int64 (__fastcall *v14)(LPVOID, BSTR, _QWORD *); // r9
  int v15; // eax
  int ppv; // [rsp+20h] [rbp-E0h]
  VARIANTARG v18; // [rsp+38h] [rbp-C8h] BYREF
  VARIANTARG v19; // [rsp+50h] [rbp-B0h] BYREF
  VARIANTARG v20; // [rsp+68h] [rbp-98h] BYREF
  VARIANTARG pvarg; // [rsp+80h] [rbp-80h] BYREF
  int v22[4]; // [rsp+A0h] [rbp-60h] BYREF
  IRecordInfo *v23; // [rsp+B0h] [rbp-50h]
  __int128 v24; // [rsp+C0h] [rbp-40h] BYREF
  IRecordInfo *v25; // [rsp+D0h] [rbp-30h]
  __int128 v26; // [rsp+E0h] [rbp-20h] BYREF
  IRecordInfo *v27; // [rsp+F0h] [rbp-10h]
  VARIANTARG v28; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]
  LPVOID v30; // [rsp+1A8h] [rbp+A8h] BYREF
  BSTR v31; // [rsp+1B0h] [rbp+B0h] BYREF

  v30 = 0;
  v2 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &v30);
  if ( v2 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x9B,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\utils\\mitigationrestartutils.cpp",
      (const char *)(unsigned int)v2,
      ppv);
  v3 = v30;
  v4 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *))(*(_QWORD *)v30 + 80LL);
  VariantInit(&pvarg);
  v5 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v20);
  v7 = *(_OWORD *)&v20.vt;
  v8 = v20.pRecInfo;
  VariantInit(&v19);
  v9 = *(_OWORD *)&v19.vt;
  v10 = v19.pRecInfo;
  VariantInit(&v18);
  *(_OWORD *)v22 = v5;
  v23 = pRecInfo;
  v24 = v7;
  v25 = v8;
  v26 = v9;
  v27 = v10;
  v28 = v18;
  v11 = v4(v3, &v28, &v26, &v24);
  if ( v11 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xA0,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\utils\\mitigationrestartutils.cpp",
      (const char *)(unsigned int)v11,
      (int)v22);
  VariantClear(&v18);
  VariantClear(&v19);
  VariantClear(&v20);
  VariantClear(&pvarg);
  v12 = SysAllocString(L"\\Microsoft\\Windows\\Diagnosis");
  v31 = v12;
  if ( !v12 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xA4,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\utils\\mitigationrestartutils.cpp",
      (const char *)0x8007000ELL,
      (int)v22);
  *a1 = 0;
  v13 = v30;
  v14 = *(__int64 (__fastcall **)(LPVOID, BSTR, _QWORD *))(*(_QWORD *)v30 + 56LL);
  *a1 = 0;
  v15 = v14(v13, v12, a1);
  if ( v15 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xA7,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\utils\\mitigationrestartutils.cpp",
      (const char *)(unsigned int)v15,
      (int)v22);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v31);
  wil::com_ptr_t<IBootTrigger,wil::err_exception_policy>::~com_ptr_t<IBootTrigger,wil::err_exception_policy>((__int64 *)&v30);
  return a1;
}

```

## disassembly

```asm
0x18002d238  mov     rax, rsp
0x18002d23b  mov     [rax+20h], rbx
0x18002d23f  mov     [rax+8], rcx
0x18002d243  push    rbp
0x18002d244  push    rsi
0x18002d245  push    rdi
0x18002d246  lea     rbp, [rsp-80h]
0x18002d24b  sub     rsp, 180h
0x18002d252  movaps  xmmword ptr [rax-28h], xmm6
0x18002d256  movaps  xmmword ptr [rax-38h], xmm7
0x18002d25a  movaps  xmmword ptr [rax-48h], xmm8
0x18002d25f  movaps  xmmword ptr [rax-58h], xmm9
0x18002d264  movaps  xmmword ptr [rax-68h], xmm10
0x18002d269  movaps  xmmword ptr [rax-78h], xmm11
0x18002d26e  mov     rsi, rcx
0x18002d271  mov     [rsp+190h+var_160], 0
0x18002d279  mov     [rbp+90h+arg_8], 0
0x18002d284  lea     rax, [rbp+90h+arg_8]
0x18002d28b  mov     qword ptr [rsp+190h+ppv], rax; int
0x18002d290  lea     r9, IID_ITaskService; riid
0x18002d297  xor     edx, edx; pUnkOuter
0x18002d299  lea     r8d, [rdx+1]; dwClsContext
0x18002d29d  lea     rcx, CLSID_TaskScheduler; rclsid
0x18002d2a4  call    cs:__imp_CoCreateInstance
0x18002d2aa  mov     rcx, [rbp+98h]; this
0x18002d2b1  test    eax, eax
0x18002d2b3  jns     short loc_18002D2CA
0x18002d2b5  mov     r9d, eax; char *
0x18002d2b8  lea     r8, aOnecoreBaseDia_18; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18002d2bf  mov     edx, 9Bh; void *
0x18002d2c4  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002d2ca  mov     rdi, [rbp+90h+arg_8]
0x18002d2d1  mov     rax, [rdi]
0x18002d2d4  mov     rbx, [rax+50h]
0x18002d2d8  lea     rcx, [rbp+90h+pvarg]; pvarg
0x18002d2dc  call    cs:__imp_VariantInit
0x18002d2e2  nop
0x18002d2e3  movups  xmm10, xmmword ptr [rbp+90h+pvarg]
0x18002d2e8  movsd   xmm11, qword ptr [rbp+90h+pvarg+10h]
0x18002d2ee  lea     rcx, [rsp+190h+var_128]; pvarg
0x18002d2f3  call    cs:__imp_VariantInit
0x18002d2f9  nop
0x18002d2fa  movups  xmm8, xmmword ptr [rsp+190h+var_128]
0x18002d300  movsd   xmm9, qword ptr [rsp+190h+var_128+10h]
0x18002d307  lea     rcx, [rsp+190h+var_140]; pvarg
0x18002d30c  call    cs:__imp_VariantInit
0x18002d312  nop
0x18002d313  movups  xmm6, xmmword ptr [rsp+190h+var_140]
0x18002d318  movsd   xmm7, qword ptr [rsp+190h+var_140+10h]
0x18002d31e  lea     rcx, [rsp+190h+var_158]; pvarg
0x18002d323  call    cs:__imp_VariantInit
0x18002d329  nop
0x18002d32a  movups  xmm0, xmmword ptr [rsp+190h+var_158]
0x18002d32f  movsd   xmm1, qword ptr [rsp+190h+var_158+10h]
0x18002d335  movaps  xmmword ptr [rbp+90h+var_F0], xmm10
0x18002d33a  movsd   [rbp+90h+var_E0], xmm11
0x18002d340  movaps  [rbp+90h+var_D0], xmm8
0x18002d345  movsd   [rbp+90h+var_C0], xmm9
0x18002d34b  movaps  [rbp+90h+var_B0], xmm6
0x18002d34f  movsd   [rbp+90h+var_A0], xmm7
0x18002d354  movaps  [rbp+90h+var_90], xmm0
0x18002d358  movsd   [rbp+90h+var_80], xmm1
0x18002d35d  lea     rax, [rbp+90h+var_F0]
0x18002d361  mov     qword ptr [rsp+190h+ppv], rax; int
0x18002d366  lea     r9, [rbp+90h+var_D0]
0x18002d36a  lea     r8, [rbp+90h+var_B0]
0x18002d36e  lea     rdx, [rbp+90h+var_90]
0x18002d372  mov     rcx, rdi
0x18002d375  mov     rax, rbx
0x18002d378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d37d  mov     rcx, [rbp+98h]; this
0x18002d384  test    eax, eax
0x18002d386  jns     short loc_18002D39D
0x18002d388  mov     r9d, eax; char *
0x18002d38b  lea     r8, aOnecoreBaseDia_18; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18002d392  mov     edx, 0A0h; void *
0x18002d397  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002d39d  lea     rcx, [rsp+190h+var_158]; pvarg
0x18002d3a2  call    cs:__imp_VariantClear
0x18002d3a8  nop
0x18002d3a9  lea     rcx, [rsp+190h+var_140]; pvarg
0x18002d3ae  call    cs:__imp_VariantClear
0x18002d3b4  nop
0x18002d3b5  lea     rcx, [rsp+190h+var_128]; pvarg
0x18002d3ba  call    cs:__imp_VariantClear
0x18002d3c0  nop
0x18002d3c1  lea     rcx, [rbp+90h+pvarg]; pvarg
0x18002d3c5  call    cs:__imp_VariantClear
0x18002d3cb  lea     rcx, aMicrosoftWindo; "\\Microsoft\\Windows\\Diagnosis"
0x18002d3d2  call    cs:__imp_SysAllocString
0x18002d3d8  mov     [rbp+90h+arg_10], rax
0x18002d3df  test    rax, rax
0x18002d3e2  setz    dl
0x18002d3e5  mov     rcx, [rbp+98h]; this
0x18002d3ec  test    dl, dl
0x18002d3ee  jz      short loc_18002D408
0x18002d3f0  mov     r9d, 8007000Eh; char *
0x18002d3f6  lea     r8, aOnecoreBaseDia_18; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18002d3fd  mov     edx, 0A4h; void *
0x18002d402  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002d408  mov     qword ptr [rsi], 0
0x18002d40f  mov     [rsp+190h+var_160], 1
0x18002d417  mov     rcx, [rbp+90h+arg_8]
0x18002d41e  mov     rdx, [rcx]
0x18002d421  mov     r9, [rdx+38h]
0x18002d425  mov     qword ptr [rsi], 0
0x18002d42c  mov     r8, rsi
0x18002d42f  mov     rdx, rax
0x18002d432  mov     rax, r9
0x18002d435  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d43a  mov     rcx, [rbp+98h]; this
0x18002d441  test    eax, eax
0x18002d443  jns     short loc_18002D45A
0x18002d445  mov     r9d, eax; char *
0x18002d448  lea     r8, aOnecoreBaseDia_18; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18002d44f  mov     edx, 0A7h; void *
0x18002d454  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002d45a  lea     rcx, [rbp+90h+arg_10]
0x18002d461  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002d466  nop
0x18002d467  lea     rcx, [rbp+90h+arg_8]
0x18002d46e  call    ??1?$com_ptr_t@UIBootTrigger@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IBootTrigger,wil::err_exception_policy>::~com_ptr_t<IBootTrigger,wil::err_exception_policy>(void)
0x18002d473  mov     rax, rsi
0x18002d476  lea     r11, [rsp+190h+var_10]
0x18002d47e  mov     rbx, [r11+38h]
0x18002d482  movaps  xmm6, xmmword ptr [r11-10h]
0x18002d487  movaps  xmm7, xmmword ptr [r11-20h]
0x18002d48c  movaps  xmm8, xmmword ptr [r11-30h]
0x18002d491  movaps  xmm9, xmmword ptr [r11-40h]
0x18002d496  movaps  xmm10, xmmword ptr [r11-50h]
0x18002d49b  movaps  xmm11, xmmword ptr [r11-60h]
0x18002d4a0  mov     rsp, r11
0x18002d4a3  pop     rdi
0x18002d4a4  pop     rsi
0x18002d4a5  pop     rbp
0x18002d4a6  retn
```
