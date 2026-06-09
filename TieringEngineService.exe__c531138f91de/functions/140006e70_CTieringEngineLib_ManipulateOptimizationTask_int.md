# CTieringEngineLib::ManipulateOptimizationTask(int)

- ea: `0x140006e70`
- end: `0x1400073bb`
- name: `?ManipulateOptimizationTask@CTieringEngineLib@@QEAAJH@Z`
- size: `1355`
- prototype: `HRESULT __fastcall(CTieringEngineLib *this, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140005698`

## callees

- `0x140001a18`
- `0x140004a68`
- `0x140004aa8`
- `0x1400055ec`
- `0x140006e70`
- `0x140009844`
- `0x140041010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1400070ab`
- `OLEAUT32!__imp_SysAllocString` at `0x140007179`
- `OLEAUT32!__imp_SysAllocString` at `0x1400070ab`
- `OLEAUT32!__imp_SysAllocString` at `0x140007179`
- `OLEAUT32!__imp_VariantInit` at `0x140006f00`
- `OLEAUT32!__imp_VariantInit` at `0x140006f1f`
- `OLEAUT32!__imp_VariantInit` at `0x140006f3b`
- `OLEAUT32!__imp_VariantInit` at `0x140006f52`
- `OLEAUT32!__imp_VariantInit` at `0x140006f00`
- `OLEAUT32!__imp_VariantInit` at `0x140006f1f`
- `OLEAUT32!__imp_VariantInit` at `0x140006f3b`
- `OLEAUT32!__imp_VariantInit` at `0x140006f52`
- `OLEAUT32!__imp_VariantClear` at `0x140006fe5`
- `OLEAUT32!__imp_VariantClear` at `0x140006ff8`
- `OLEAUT32!__imp_VariantClear` at `0x14000700b`
- `OLEAUT32!__imp_VariantClear` at `0x140007021`
- `OLEAUT32!__imp_VariantClear` at `0x140006fe5`
- `OLEAUT32!__imp_VariantClear` at `0x140006ff8`
- `OLEAUT32!__imp_VariantClear` at `0x14000700b`
- `OLEAUT32!__imp_VariantClear` at `0x140007021`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140006ede`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140006ede`

## pseudocode

```c
HRESULT __fastcall CTieringEngineLib::ManipulateOptimizationTask(CTieringEngineLib *this, unsigned int a2)
{
  HRESULT result; // eax
  __int64 (__fastcall *v5)(LPVOID, VARIANTARG *, __int128 *, __int128 *, __int128 *); // rbx
  __int128 v6; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v8; // xmm8
  IRecordInfo *v9; // xmm9_8
  __int128 v10; // xmm6
  IRecordInfo *v11; // xmm7_8
  int v12; // ebx
  HRESULT v13; // eax
  HRESULT v14; // eax
  HRESULT v15; // eax
  HRESULT v16; // eax
  __int64 v17; // r13
  const OLECHAR *v18; // rsi
  BSTR *v19; // rax
  BSTR *v20; // rbx
  BSTR v21; // rax
  __int64 v22; // r13
  const OLECHAR *v23; // rsi
  BSTR *v24; // rax
  BSTR *v25; // rbx
  BSTR v26; // rax
  int v27; // eax
  int v28; // eax
  LPVOID ppv; // [rsp+30h] [rbp-188h] BYREF
  __int64 v30; // [rsp+38h] [rbp-180h] BYREF
  __int64 *v31; // [rsp+40h] [rbp-178h] BYREF
  VARIANTARG v32; // [rsp+48h] [rbp-170h] BYREF
  VARIANTARG v33; // [rsp+60h] [rbp-158h] BYREF
  VARIANTARG v34; // [rsp+78h] [rbp-140h] BYREF
  VARIANTARG pvarg; // [rsp+90h] [rbp-128h] BYREF
  __int128 v36; // [rsp+B0h] [rbp-108h] BYREF
  IRecordInfo *v37; // [rsp+C0h] [rbp-F8h]
  __int128 v38; // [rsp+D0h] [rbp-E8h] BYREF
  IRecordInfo *v39; // [rsp+E0h] [rbp-D8h]
  __int128 v40; // [rsp+F0h] [rbp-C8h] BYREF
  IRecordInfo *v41; // [rsp+100h] [rbp-B8h]
  VARIANTARG v42; // [rsp+110h] [rbp-A8h] BYREF
  __int16 v43; // [rsp+1D0h] [rbp+18h] BYREF
  BSTR *v44; // [rsp+1D8h] [rbp+20h] BYREF

  ppv = 0;
  v31 = 0;
  v30 = 0;
  v43 = 0;
  result = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &ppv);
  if ( result < 0 )
    return result;
  v5 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *, __int128 *))(*(_QWORD *)ppv + 80LL);
  VariantInit(&pvarg);
  v6 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v34);
  v8 = *(_OWORD *)&v34.vt;
  v9 = v34.pRecInfo;
  VariantInit(&v33);
  v10 = *(_OWORD *)&v33.vt;
  v11 = v33.pRecInfo;
  VariantInit(&v32);
  v36 = v6;
  v37 = pRecInfo;
  v38 = v8;
  v39 = v9;
  v40 = v10;
  v41 = v11;
  v42 = v32;
  v12 = v5(ppv, &v42, &v40, &v38, &v36);
  v13 = VariantClear(&v32);
  if ( v13 < 0 )
    _com_issue_error(v13);
  v14 = VariantClear(&v33);
  if ( v14 < 0 )
    _com_issue_error(v14);
  v15 = VariantClear(&v34);
  if ( v15 < 0 )
    _com_issue_error(v15);
  v16 = VariantClear(&pvarg);
  if ( v16 < 0 )
    _com_issue_error(v16);
  if ( v12 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 131, &WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids, a2, v12);
    }
    goto LABEL_47;
  }
  v17 = *(_QWORD *)ppv;
  v18 = (const OLECHAR *)*((_QWORD *)this + 23);
  v19 = (BSTR *)operator new(0x18u);
  v20 = v19;
  v44 = v19;
  if ( v19 )
  {
    v19[1] = 0;
    *((_DWORD *)v19 + 4) = 1;
    v21 = SysAllocString(v18);
    *v20 = v21;
    if ( !v21 && v18 )
      _com_issue_error(-2147024882);
  }
  else
  {
    v20 = 0;
  }
  v44 = v20;
  if ( !v20 )
    _com_issue_error(-2147024882);
  v12 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int64 **))(v17 + 56))(ppv, *v20, &v31);
  _bstr_t::~_bstr_t((_bstr_t *)&v44);
  if ( v12 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 132, &WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids, a2, v12);
    }
    goto LABEL_47;
  }
  v22 = *v31;
  v23 = (const OLECHAR *)*((_QWORD *)this + 22);
  v24 = (BSTR *)operator new(0x18u);
  v25 = v24;
  v44 = v24;
  if ( v24 )
  {
    v24[1] = 0;
    *((_DWORD *)v24 + 4) = 1;
    v26 = SysAllocString(v23);
    *v25 = v26;
    if ( !v26 && v23 )
      _com_issue_error(-2147024882);
  }
  else
  {
    v25 = 0;
  }
  v44 = v25;
  if ( !v25 )
    _com_issue_error(-2147024882);
  v12 = (*(__int64 (__fastcall **)(__int64 *, BSTR, __int64 *))(v22 + 104))(v31, *v25, &v30);
  _bstr_t::~_bstr_t((_bstr_t *)&v44);
  if ( v12 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 133, &WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids, a2, v12);
    }
    goto LABEL_47;
  }
  v27 = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v30 + 80LL))(v30, &v43);
  v12 = v27;
  if ( v27 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        134,
        &WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids,
        (unsigned int)v27);
    }
    goto LABEL_43;
  }
  if ( a2 )
  {
    if ( v43 )
      goto LABEL_47;
LABEL_43:
    v43 = -(a2 != 0);
    v28 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 88LL))(v30);
    v12 = v28;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 135, &WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids, a2, v28);
    }
    goto LABEL_47;
  }
  if ( v43 )
    goto LABEL_43;
LABEL_47:
  if ( v30 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  if ( v31 )
    (*(void (__fastcall **)(__int64 *))(*v31 + 16))(v31);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return v12;
}

```

## disassembly

```asm
0x140006e70  mov     rax, rsp
0x140006e73  mov     [rax+8], rbx
0x140006e77  push    rsi
0x140006e78  push    rdi
0x140006e79  push    r13
0x140006e7b  push    r14
0x140006e7d  push    r15
0x140006e7f  sub     rsp, 190h
0x140006e86  movaps  xmmword ptr [rax-38h], xmm6
0x140006e8a  movaps  xmmword ptr [rax-48h], xmm7
0x140006e8e  movaps  xmmword ptr [rax-58h], xmm8
0x140006e93  movaps  xmmword ptr [rax-68h], xmm9
0x140006e98  movaps  xmmword ptr [rax-78h], xmm10
0x140006e9d  movaps  xmmword ptr [rax-88h], xmm11
0x140006ea5  mov     r14d, edx
0x140006ea8  mov     r15, rcx
0x140006eab  xor     edi, edi
0x140006ead  mov     [rsp+1B8h+var_188], rdi
0x140006eb2  mov     [rsp+1B8h+var_178], rdi
0x140006eb7  mov     [rsp+1B8h+var_180], rdi
0x140006ebc  mov     [rax+18h], di
0x140006ec0  lea     rax, [rsp+1B8h+var_188]
0x140006ec5  mov     [rsp+1B8h+ppv], rax; ppv
0x140006eca  lea     r9, IID_ITaskService; riid
0x140006ed1  xor     edx, edx; pUnkOuter
0x140006ed3  lea     r8d, [rdi+1]; dwClsContext
0x140006ed7  lea     rcx, CLSID_TaskScheduler; rclsid
0x140006ede  call    cs:__imp_CoCreateInstance
0x140006ee4  test    eax, eax
0x140006ee6  js      loc_140007338
0x140006eec  mov     rax, [rsp+1B8h+var_188]
0x140006ef1  mov     rcx, [rax]
0x140006ef4  mov     rbx, [rcx+50h]
0x140006ef8  lea     rcx, [rsp+1B8h+pvarg]; pvarg
0x140006f00  call    cs:__imp_VariantInit
0x140006f06  nop
0x140006f07  movups  xmm10, xmmword ptr [rsp+1B8h+pvarg]
0x140006f10  movsd   xmm11, qword ptr [rsp+1B8h+pvarg+10h]
0x140006f1a  lea     rcx, [rsp+1B8h+var_140]; pvarg
0x140006f1f  call    cs:__imp_VariantInit
0x140006f25  nop
0x140006f26  movups  xmm8, xmmword ptr [rsp+1B8h+var_140]
0x140006f2c  movsd   xmm9, qword ptr [rsp+1B8h+var_140+10h]
0x140006f36  lea     rcx, [rsp+1B8h+var_158]; pvarg
0x140006f3b  call    cs:__imp_VariantInit
0x140006f41  nop
0x140006f42  movups  xmm6, xmmword ptr [rsp+1B8h+var_158]
0x140006f47  movsd   xmm7, qword ptr [rsp+1B8h+var_158+10h]
0x140006f4d  lea     rcx, [rsp+1B8h+var_170]; pvarg
0x140006f52  call    cs:__imp_VariantInit
0x140006f58  nop
0x140006f59  movups  xmm0, xmmword ptr [rsp+1B8h+var_170]
0x140006f5e  movsd   xmm1, qword ptr [rsp+1B8h+var_170+10h]
0x140006f64  movaps  [rsp+1B8h+var_108], xmm10
0x140006f6d  movsd   [rsp+1B8h+var_F8], xmm11
0x140006f77  movaps  [rsp+1B8h+var_E8], xmm8
0x140006f80  movsd   [rsp+1B8h+var_D8], xmm9
0x140006f8a  movaps  [rsp+1B8h+var_C8], xmm6
0x140006f92  movsd   [rsp+1B8h+var_B8], xmm7
0x140006f9b  movaps  [rsp+1B8h+var_A8], xmm0
0x140006fa3  movsd   [rsp+1B8h+var_98], xmm1
0x140006fac  lea     rax, [rsp+1B8h+var_108]
0x140006fb4  mov     [rsp+1B8h+ppv], rax
0x140006fb9  lea     r9, [rsp+1B8h+var_E8]
0x140006fc1  lea     r8, [rsp+1B8h+var_C8]
0x140006fc9  lea     rdx, [rsp+1B8h+var_A8]
0x140006fd1  mov     rcx, [rsp+1B8h+var_188]
0x140006fd6  mov     rax, rbx
0x140006fd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006fde  mov     ebx, eax
0x140006fe0  lea     rcx, [rsp+1B8h+var_170]; pvarg
0x140006fe5  call    cs:__imp_VariantClear
0x140006feb  test    eax, eax
0x140006fed  js      loc_14000736E
0x140006ff3  lea     rcx, [rsp+1B8h+var_158]; pvarg
0x140006ff8  call    cs:__imp_VariantClear
0x140006ffe  test    eax, eax
0x140007000  js      loc_140007376
0x140007006  lea     rcx, [rsp+1B8h+var_140]; pvarg
0x14000700b  call    cs:__imp_VariantClear
0x140007011  test    eax, eax
0x140007013  js      loc_14000737E
0x140007019  lea     rcx, [rsp+1B8h+pvarg]; pvarg
0x140007021  call    cs:__imp_VariantClear
0x140007027  test    eax, eax
0x140007029  js      loc_140007386
0x14000702f  test    ebx, ebx
0x140007031  jns     short loc_140007074
0x140007033  lea     rsi, WPP_GLOBAL_Control
0x14000703a  mov     rcx, cs:WPP_GLOBAL_Control
0x140007041  cmp     rcx, rsi
0x140007044  jz      short loc_14000706F
0x140007046  test    byte ptr [rcx+1Ch], 1
0x14000704a  jz      short loc_14000706F
0x14000704c  cmp     byte ptr [rcx+19h], 2
0x140007050  jb      short loc_14000706F
0x140007052  mov     edx, 83h
0x140007057  mov     dword ptr [rsp+1B8h+ppv], ebx
0x14000705b  mov     r9d, r14d
0x14000705e  lea     r8, WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids
0x140007065  mov     rcx, [rcx+10h]
0x140007069  call    WPP_SF_Dd
0x14000706e  nop
0x14000706f  jmp     loc_1400072F4
0x140007074  mov     rax, [rsp+1B8h+var_188]
0x140007079  mov     r13, [rax]
0x14000707c  mov     rsi, [r15+0B8h]
0x140007083  mov     ecx, 18h; Size
0x140007088  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000708d  mov     rbx, rax
0x140007090  mov     [rsp+1B8h+arg_18], rax
0x140007098  test    rax, rax
0x14000709b  jz      short loc_1400070C4
0x14000709d  mov     [rax+8], rdi
0x1400070a1  mov     dword ptr [rax+10h], 1
0x1400070a8  mov     rcx, rsi; psz
0x1400070ab  call    cs:__imp_SysAllocString
0x1400070b1  mov     [rbx], rax
0x1400070b4  test    rax, rax
0x1400070b7  jnz     short loc_1400070C7
0x1400070b9  test    rsi, rsi
0x1400070bc  jnz     loc_14000738E
0x1400070c2  jmp     short loc_1400070C7
0x1400070c4  mov     rbx, rdi
0x1400070c7  mov     [rsp+1B8h+arg_18], rbx
0x1400070cf  test    rbx, rbx
0x1400070d2  jz      loc_140007399
0x1400070d8  lea     r8, [rsp+1B8h+var_178]
0x1400070dd  mov     rdx, [rbx]
0x1400070e0  mov     rcx, [rsp+1B8h+var_188]
0x1400070e5  mov     rax, [r13+38h]
0x1400070e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400070ee  mov     ebx, eax
0x1400070f0  lea     rcx, [rsp+1B8h+arg_18]; this
0x1400070f8  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1400070fd  test    ebx, ebx
0x1400070ff  jns     short loc_140007142
0x140007101  lea     rsi, WPP_GLOBAL_Control
0x140007108  mov     rcx, cs:WPP_GLOBAL_Control
0x14000710f  cmp     rcx, rsi
0x140007112  jz      short loc_14000713D
0x140007114  test    byte ptr [rcx+1Ch], 1
0x140007118  jz      short loc_14000713D
0x14000711a  cmp     byte ptr [rcx+19h], 2
0x14000711e  jb      short loc_14000713D
0x140007120  mov     edx, 84h
0x140007125  mov     dword ptr [rsp+1B8h+ppv], ebx
0x140007129  mov     r9d, r14d
0x14000712c  lea     r8, WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids
0x140007133  mov     rcx, [rcx+10h]
0x140007137  call    WPP_SF_Dd
0x14000713c  nop
0x14000713d  jmp     loc_1400072F4
0x140007142  mov     rax, [rsp+1B8h+var_178]
0x140007147  mov     r13, [rax]
0x14000714a  mov     rsi, [r15+0B0h]
0x140007151  mov     ecx, 18h; Size
0x140007156  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000715b  mov     rbx, rax
0x14000715e  mov     [rsp+1B8h+arg_18], rax
0x140007166  test    rax, rax
0x140007169  jz      short loc_140007192
0x14000716b  mov     [rax+8], rdi
0x14000716f  mov     dword ptr [rax+10h], 1
0x140007176  mov     rcx, rsi; psz
0x140007179  call    cs:__imp_SysAllocString
0x14000717f  mov     [rbx], rax
0x140007182  test    rax, rax
0x140007185  jnz     short loc_140007195
0x140007187  test    rsi, rsi
0x14000718a  jnz     loc_1400073A4
0x140007190  jmp     short loc_140007195
0x140007192  mov     rbx, rdi
0x140007195  mov     [rsp+1B8h+arg_18], rbx
0x14000719d  test    rbx, rbx
0x1400071a0  jz      loc_1400073AF
0x1400071a6  lea     r8, [rsp+1B8h+var_180]
0x1400071ab  mov     rdx, [rbx]
0x1400071ae  mov     rcx, [rsp+1B8h+var_178]
0x1400071b3  mov     rax, [r13+68h]
0x1400071b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400071bc  mov     ebx, eax
0x1400071be  lea     rcx, [rsp+1B8h+arg_18]; this
0x1400071c6  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1400071cb  test    ebx, ebx
0x1400071cd  jns     short loc_140007210
0x1400071cf  lea     rsi, WPP_GLOBAL_Control
0x1400071d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400071dd  cmp     rcx, rsi
0x1400071e0  jz      short loc_14000720B
0x1400071e2  test    byte ptr [rcx+1Ch], 1
0x1400071e6  jz      short loc_14000720B
0x1400071e8  cmp     byte ptr [rcx+19h], 2
0x1400071ec  jb      short loc_14000720B
0x1400071ee  mov     edx, 85h
0x1400071f3  mov     dword ptr [rsp+1B8h+ppv], ebx
0x1400071f7  mov     r9d, r14d
0x1400071fa  lea     r8, WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids
0x140007201  mov     rcx, [rcx+10h]
0x140007205  call    WPP_SF_Dd
0x14000720a  nop
0x14000720b  jmp     loc_1400072F4
0x140007210  mov     rcx, [rsp+1B8h+var_180]
0x140007215  mov     rax, [rcx]
0x140007218  lea     rdx, [rsp+1B8h+arg_10]
0x140007220  mov     rax, [rax+50h]
0x140007224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007229  mov     ebx, eax
0x14000722b  test    eax, eax
0x14000722d  js      short loc_14000725C
0x14000722f  movzx   eax, [rsp+1B8h+arg_10]
0x140007237  test    r14d, r14d
0x14000723a  jz      short loc_14000724A
0x14000723c  test    ax, ax
0x14000723f  jz      short loc_140007253
0x140007241  test    r14d, r14d
0x140007244  jnz     loc_1400072EB
0x14000724a  test    ax, ax
0x14000724d  jz      loc_1400072EB
0x140007253  lea     rsi, WPP_GLOBAL_Control
0x14000725a  jmp     short loc_140007293
0x14000725c  lea     rsi, WPP_GLOBAL_Control
0x140007263  mov     rcx, cs:WPP_GLOBAL_Control
0x14000726a  cmp     rcx, rsi
0x14000726d  jz      short loc_140007293
0x14000726f  test    byte ptr [rcx+1Ch], 1
0x140007273  jz      short loc_140007293
0x140007275  cmp     byte ptr [rcx+19h], 2
0x140007279  jb      short loc_140007293
0x14000727b  mov     edx, 86h
0x140007280  mov     r9d, eax
0x140007283  lea     r8, WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids
0x14000728a  mov     rcx, [rcx+10h]
0x14000728e  call    WPP_SF_d
0x140007293  mov     eax, r14d
0x140007296  neg     eax
0x140007298  sbb     dx, dx
0x14000729b  mov     [rsp+1B8h+arg_10], dx
0x1400072a3  mov     rcx, [rsp+1B8h+var_180]
0x1400072a8  mov     rax, [rcx]
0x1400072ab  mov     rax, [rax+58h]
0x1400072af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400072b4  mov     ebx, eax
0x1400072b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400072bd  cmp     rcx, rsi
0x1400072c0  jz      short loc_1400072EB
0x1400072c2  test    byte ptr [rcx+1Ch], 1
0x1400072c6  jz      short loc_1400072EB
0x1400072c8  cmp     byte ptr [rcx+19h], 2
0x1400072cc  jb      short loc_1400072EB
0x1400072ce  mov     edx, 87h
0x1400072d3  mov     dword ptr [rsp+1B8h+ppv], eax
0x1400072d7  mov     r9d, r14d
0x1400072da  lea     r8, WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids
0x1400072e1  mov     rcx, [rcx+10h]
0x1400072e5  call    WPP_SF_Dd
0x1400072ea  nop
0x1400072eb  jmp     short loc_1400072F4
0x1400072ed  mov     ebx, dword ptr [rsp+1B8h+arg_18]
0x1400072f4  mov     rcx, [rsp+1B8h+var_180]
0x1400072f9  test    rcx, rcx
0x1400072fc  jz      short loc_14000730A
0x1400072fe  mov     rax, [rcx]
0x140007301  mov     rax, [rax+10h]
0x140007305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000730a  mov     rcx, [rsp+1B8h+var_178]
0x14000730f  test    rcx, rcx
0x140007312  jz      short loc_140007320
0x140007314  mov     rax, [rcx]
0x140007317  mov     rax, [rax+10h]
0x14000731b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007320  mov     rcx, [rsp+1B8h+var_188]
0x140007325  test    rcx, rcx
0x140007328  jz      short loc_140007336
0x14000732a  mov     rdx, [rcx]
0x14000732d  mov     rax, [rdx+10h]
0x140007331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007336  mov     eax, ebx
0x140007338  lea     r11, [rsp+1B8h+var_28]
0x140007340  mov     rbx, [r11+30h]
0x140007344  movaps  xmm6, xmmword ptr [r11-10h]
0x140007349  movaps  xmm7, xmmword ptr [r11-20h]
0x14000734e  movaps  xmm8, xmmword ptr [r11-30h]
0x140007353  movaps  xmm9, xmmword ptr [r11-40h]
0x140007358  movaps  xmm10, xmmword ptr [r11-50h]
0x14000735d  movaps  xmm11, xmmword ptr [r11-60h]
0x140007362  mov     rsp, r11
0x140007365  pop     r15
0x140007367  pop     r14
0x140007369  pop     r13
0x14000736b  pop     rdi
0x14000736c  pop     rsi
0x14000736d  retn
0x14000736e  mov     ecx, eax; int
0x140007370  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x140007376  mov     ecx, eax; int
0x140007378  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x14000737e  mov     ecx, eax; int
0x140007380  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x140007386  mov     ecx, eax; int
  ... truncated ...
```
