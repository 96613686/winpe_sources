# CoEffectGraph::LoadFromStream(IStream *,wchar_t const *)

- ea: `0x180557c40`
- end: `0x180558527`
- name: `?LoadFromStream@CoEffectGraph@@AEAAXPEAUIStream@@PEB_W@Z`
- size: `2279`
- prototype: `void(CoEffectGraph *__hidden this, struct IStream *, const wchar_t *)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180558530`
- `0x180558660`

## callees

- `0x18001397c`
- `0x1804c6944`
- `0x18053ecd8`
- `0x18054c328`
- `0x180556608`
- `0x180557330`
- `0x180557af0`
- `0x180557c40`
- `0x18055ddb0`
- `0x18056dce0`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x180557ed6`
- `KERNEL32!CompareStringW` at `0x180557f02`
- `KERNEL32!CompareStringW` at `0x180557fa5`
- `KERNEL32!CompareStringW` at `0x18055800d`
- `KERNEL32!CompareStringW` at `0x180557ed6`
- `KERNEL32!CompareStringW` at `0x180557f02`
- `KERNEL32!CompareStringW` at `0x180557fa5`
- `KERNEL32!CompareStringW` at `0x18055800d`
- `OLEAUT32!__imp_SysAllocString` at `0x180557f28`
- `OLEAUT32!__imp_SysAllocString` at `0x180557f28`
- `OLEAUT32!__imp_SysFreeString` at `0x180557f57`
- `OLEAUT32!__imp_SysFreeString` at `0x180558125`
- `OLEAUT32!__imp_SysFreeString` at `0x180558130`
- `OLEAUT32!__imp_SysFreeString` at `0x18055813b`
- `OLEAUT32!__imp_SysFreeString` at `0x1805581b1`
- `OLEAUT32!__imp_SysFreeString` at `0x1805581d4`
- `OLEAUT32!__imp_SysFreeString` at `0x180558336`
- `OLEAUT32!__imp_SysFreeString` at `0x180558369`
- `OLEAUT32!__imp_SysFreeString` at `0x180557f57`
- `OLEAUT32!__imp_SysFreeString` at `0x180558125`
- `OLEAUT32!__imp_SysFreeString` at `0x180558130`
- `OLEAUT32!__imp_SysFreeString` at `0x18055813b`
- `OLEAUT32!__imp_SysFreeString` at `0x1805581b1`
- `OLEAUT32!__imp_SysFreeString` at `0x1805581d4`
- `OLEAUT32!__imp_SysFreeString` at `0x180558336`
- `OLEAUT32!__imp_SysFreeString` at `0x180558369`
- `OLEAUT32!__imp_SysStringLen` at `0x180557ea5`
- `OLEAUT32!__imp_SysStringLen` at `0x180557ea5`
- `OLEAUT32!__imp_VariantInit` at `0x180558070`
- `OLEAUT32!__imp_VariantInit` at `0x1805580b2`
- `OLEAUT32!__imp_VariantInit` at `0x180558070`
- `OLEAUT32!__imp_VariantInit` at `0x1805580b2`
- `OLEAUT32!__imp_VariantClear` at `0x18055810f`
- `OLEAUT32!__imp_VariantClear` at `0x180558119`
- `OLEAUT32!__imp_VariantClear` at `0x18055810f`
- `OLEAUT32!__imp_VariantClear` at `0x180558119`
- `OLEAUT32!__imp_VarBstrCmp` at `0x180557f4b`
- `OLEAUT32!__imp_VarBstrCmp` at `0x180557f4b`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180557c93`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180557c93`

## string_xrefs

- `0x180557eba`: `http://schemas.microsoft.com/expression/imaging/2008/core/`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
void __fastcall CoEffectGraph::LoadFromStream(CoEffectGraph *this, struct IStream *a2, const wchar_t *a3)
{
  const wchar_t *v3; // rsi
  CoEffectGraph *v4; // r15
  int v5; // r13d
  struct IEffectHost *v6; // rdi
  void *v7; // rax
  __int64 v8; // rax
  EffectCollection *v9; // r12
  __int64 v10; // r14
  int v11; // eax
  int v12; // ebx
  int i; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  struct IEffectHost *v22; // rsi
  OLECHAR *v23; // rax
  OLECHAR *v24; // rbx
  HRESULT v25; // r15d
  int v26; // eax
  struct IEffectHost *v27; // rbx
  __int64 (__fastcall *v28)(struct IEffectHost *, _QWORD); // rsi
  unsigned int v29; // eax
  int v30; // eax
  struct IEffectHost *v31; // rbx
  __int64 (__fastcall *v32)(struct IEffectHost *, _QWORD); // rsi
  unsigned int v33; // eax
  int v34; // eax
  int v35; // eax
  __int64 v36; // rax
  int v37; // eax
  struct IEffectHost *v38; // rdx
  PCNZWCH v39; // rbx
  int v40; // eax
  int v41; // eax
  int v42; // eax
  int v43; // eax
  unsigned int v44; // r15d
  BSTR j; // rsi
  int v46; // eax
  OLECHAR *v47; // rcx
  int v48; // eax
  int v49; // eax
  int v50; // eax
  struct IEffectHost *v51; // [rsp+30h] [rbp-D0h] BYREF
  BSTR v52; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v53; // [rsp+40h] [rbp-C0h] BYREF
  BSTR pbstr; // [rsp+48h] [rbp-B8h] BYREF
  PCNZWCH v55; // [rsp+50h] [rbp-B0h] BYREF
  BSTR v56; // [rsp+58h] [rbp-A8h] BYREF
  PCNZWCH lpString1; // [rsp+60h] [rbp-A0h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp-98h] BYREF
  int v59; // [rsp+70h] [rbp-90h]
  BSTR v60; // [rsp+78h] [rbp-88h] BYREF
  __int64 v61; // [rsp+80h] [rbp-80h]
  VARIANTARG v62; // [rsp+88h] [rbp-78h] BYREF
  struct IEffectHost *v63; // [rsp+A0h] [rbp-60h]
  __int16 v64; // [rsp+A8h] [rbp-58h] BYREF
  VARIANTARG pvarg; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v66; // [rsp+C8h] [rbp-38h]
  __int64 v67; // [rsp+D0h] [rbp-30h]
  VARIANTARG v68; // [rsp+E0h] [rbp-20h] BYREF
  int v70; // [rsp+158h] [rbp+58h] BYREF
  const wchar_t *v71; // [rsp+160h] [rbp+60h]
  void *v72; // [rsp+168h] [rbp+68h] BYREF

  v71 = a3;
  v3 = a3;
  v4 = this;
  v5 = 0;
  if ( !a2 )
    ATL::BaseAtlThrow(-2147467261);
  v61 = 0;
  sub_180557AF0(a2);
  v6 = 0;
  v63 = 0;
  v7 = malloc(0xA0u);
  if ( !v7 )
    ThrowOOM();
  v72 = v7;
  v8 = ATL::CComObject<EffectCollection>::CComObject<EffectCollection>(v7);
  v9 = (EffectCollection *)v8;
  v67 = v8;
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
  v70 = 0;
  v10 = v61;
  v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v61 + 72LL))(v61, &v70);
  if ( v11 < 0 )
    ATL::BaseAtlThrow(v11);
  v12 = 0;
  v59 = 0;
  for ( i = v70; v12 < v70; i = v70 )
  {
    v52 = 0;
    v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, BSTR *))(*(_QWORD *)v10 + 96LL))(v10, (unsigned int)v12, &v52);
    if ( v14 < 0 )
      ATL::BaseAtlThrow(v14);
    v56 = 0;
    v15 = (*(__int64 (__fastcall **)(BSTR, BSTR *))(*(_QWORD *)v52 + 96LL))(v52, &v56);
    if ( v15 < 0 )
      ATL::BaseAtlThrow(v15);
    v51 = 0;
    v16 = (*(__int64 (__fastcall **)(__int64, BSTR, struct IEffectHost **))(*((_QWORD *)v4 + 4) + 160LL))(
            (__int64)v4 + 32,
            v56,
            &v51);
    if ( v16 < 0 )
      ATL::BaseAtlThrow(v16);
    bstrString = 0;
    v17 = (*(__int64 (__fastcall **)(BSTR, BSTR *))(*(_QWORD *)v52 + 88LL))(v52, &bstrString);
    if ( v17 < 0 )
      ATL::BaseAtlThrow(v17);
    v18 = (*(__int64 (__fastcall **)(struct IEffectHost *, BSTR))(*(_QWORD *)v51 + 384LL))(v51, bstrString);
    if ( v18 < 0 )
      ATL::BaseAtlThrow(v18);
    if ( v3 )
      (*(void (__fastcall **)(struct IEffectHost *, const wchar_t *))(*(_QWORD *)v51 + 288LL))(v51, v3);
    LODWORD(v72) = 0;
    v19 = (*(__int64 (__fastcall **)(BSTR, void **))(*(_QWORD *)v52 + 56LL))(v52, &v72);
    if ( v19 < 0 )
      ATL::BaseAtlThrow(v19);
    if ( (int)v72 > 0 )
    {
      do
      {
        v53 = 0;
        v20 = (*(__int64 (__fastcall **)(BSTR, _QWORD, __int64 *))(*(_QWORD *)v52 + 80LL))(v52, (unsigned int)v5, &v53);
        if ( v20 < 0 )
          ATL::BaseAtlThrow(v20);
        lpString1 = 0;
        v55 = 0;
        pbstr = 0;
        v21 = (*(__int64 (__fastcall **)(__int64, PCNZWCH *))(*(_QWORD *)v53 + 56LL))(v53, &lpString1);
        if ( v21 < 0 )
          ATL::BaseAtlThrow(v21);
        if ( (*(int (__fastcall **)(__int64, PCNZWCH *))(*(_QWORD *)v53 + 64LL))(v53, &v55) < 0 )
          ATL::BaseAtlThrow(-2045247228);
        if ( (*(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v53 + 72LL))(v53, &pbstr) < 0 )
          ATL::BaseAtlThrow(-2045247227);
        if ( SysStringLen(pbstr) )
        {
          if ( CompareStringW(
                 0x7Fu,
                 1u,
                 lpString1,
                 -1,
                 L"http://schemas.microsoft.com/expression/imaging/2008/core/",
                 -1) == 2 )
          {
            if ( CompareStringW(0x7Fu, 1u, v55, -1, L"Enabled", -1) == 2 )
            {
              v22 = v51;
              v60 = *(BSTR *)(*(_QWORD *)v51 + 192LL);
              v23 = SysAllocString(L"0");
              v24 = v23;
              if ( !v23 )
                ATL::BaseAtlThrow(-2147024882);
              v25 = VarBstrCmp(pbstr, v23, 0x400u, 0);
              SysFreeString(v24);
              v26 = ((__int64 (__fastcall *)(struct IEffectHost *, bool))v60)(v22, v25 != 1);
              if ( v26 < 0 )
                ATL::BaseAtlThrow(v26);
            }
            else if ( CompareStringW(0x7Fu, 1u, v55, -1, L"SoftwareFormat", -1) == 2 )
            {
              v27 = v51;
              v28 = *(__int64 (__fastcall **)(struct IEffectHost *, _QWORD))(*(_QWORD *)v51 + 208LL);
              v60 = pbstr;
              v29 = sub_180557330(&v60);
              v30 = v28(v27, v29);
              if ( v30 < 0 )
                ATL::BaseAtlThrow(v30);
            }
            else if ( CompareStringW(0x7Fu, 1u, v55, -1, L"HardwareFormat", -1) == 2 )
            {
              v31 = v51;
              v32 = *(__int64 (__fastcall **)(struct IEffectHost *, _QWORD))(*(_QWORD *)v51 + 224LL);
              v60 = pbstr;
              v33 = sub_180557330(&v60);
              v34 = v32(v31, v33);
              if ( v34 < 0 )
                ATL::BaseAtlThrow(v34);
            }
          }
          else
          {
            v64 = 0;
            memset(&pvarg, 0, sizeof(pvarg));
            VariantInit(&pvarg);
            v66 = 0;
            v35 = (*(__int64 (__fastcall **)(struct IEffectHost *, PCNZWCH, __int16 *))(*(_QWORD *)v51 + 80LL))(
                    v51,
                    v55,
                    &v64);
            if ( v35 < 0 )
              ATL::BaseAtlThrow(v35);
            memset(&v62, 0, sizeof(v62));
            VariantInit(&v62);
            sub_18054C328(pbstr);
            v36 = *(_QWORD *)v51;
            v68 = v62;
            v37 = (*(__int64 (__fastcall **)(struct IEffectHost *, PCNZWCH, VARIANTARG *))(v36 + 104))(v51, v55, &v68);
            if ( v37 < 0 )
              ATL::BaseAtlThrow(v37);
            VariantClear(&v62);
            VariantClear(&pvarg);
          }
        }
        SysFreeString(pbstr);
        SysFreeString((BSTR)v55);
        SysFreeString((BSTR)lpString1);
        if ( v53 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
        ++v5;
      }
      while ( v5 < (int)v72 );
      v12 = v59;
      v3 = v71;
      v4 = this;
    }
    v5 = 0;
    v38 = v51;
    if ( !v6 && v51 )
    {
      v6 = v51;
      (*(void (__fastcall **)(struct IEffectHost *))(*(_QWORD *)v51 + 8LL))(v51);
      v38 = v51;
      v63 = v6;
    }
    EffectCollection::Add(v9, v38);
    SysFreeString(bstrString);
    if ( v51 )
      (*(void (__fastcall **)(struct IEffectHost *))(*(_QWORD *)v51 + 16LL))(v51);
    SysFreeString(v56);
    if ( v52 )
      (*(void (__fastcall **)(BSTR))(*(_QWORD *)v52 + 16LL))(v52);
    v59 = ++v12;
  }
  v39 = 0;
  if ( i > 0 )
  {
    do
    {
      v53 = 0;
      v40 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v10 + 96LL))(v10, (unsigned int)v5, &v53);
      if ( v40 < 0 )
        ATL::BaseAtlThrow(v40);
      v56 = 0;
      bstrString = 0;
      v41 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v53 + 88LL))(v53, &v56);
      if ( v41 < 0 )
        ATL::BaseAtlThrow(v41);
      v42 = sub_180556608(v9, v56, &bstrString);
      if ( v42 < 0 )
        ATL::BaseAtlThrow(v42);
      LODWORD(v72) = 0;
      v43 = (*(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v53 + 104LL))(v53, &v72);
      if ( v43 < 0 )
        ATL::BaseAtlThrow(v43);
      v44 = 0;
      for ( j = bstrString; (int)v44 < (int)v72; v39 = 0 )
      {
        v52 = 0;
        lpString1 = 0;
        v46 = (*(__int64 (__fastcall **)(__int64, _QWORD, BSTR *))(*(_QWORD *)v53 + 120LL))(v53, v44, &v52);
        if ( v46 < 0 )
          ATL::BaseAtlThrow(v46);
        v47 = v52;
        if ( v52 )
        {
          v48 = sub_180556608(v9, v52, &lpString1);
          if ( v48 < 0 )
            ATL::BaseAtlThrow(v48);
          v39 = lpString1;
          v49 = (*(__int64 (__fastcall **)(BSTR, _QWORD, PCNZWCH))(*(_QWORD *)j + 120LL))(j, v44, lpString1);
          if ( v49 < 0 )
            ATL::BaseAtlThrow(v49);
          v47 = v52;
        }
        if ( v39 )
        {
          (*(void (__fastcall **)(PCNZWCH))(*(_QWORD *)v39 + 16LL))(v39);
          v47 = v52;
        }
        SysFreeString(v47);
        ++v44;
      }
      if ( j )
        (*(void (__fastcall **)(BSTR))(*(_QWORD *)j + 16LL))(j);
      SysFreeString(v56);
      if ( v53 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
      ++v5;
    }
    while ( v5 < v70 );
  }
  v50 = (*(__int64 (__fastcall **)(char *, struct IEffectHost *))(*((_QWORD *)this + 4) + 64LL))((char *)this + 32, v6);
  if ( v50 < 0 )
    ATL::BaseAtlThrow(v50);
  if ( v9 )
    (*(void (__fastcall **)(EffectCollection *))(*(_QWORD *)v9 + 16LL))(v9);
  if ( v6 )
    (*(void (__fastcall **)(struct IEffectHost *))(*(_QWORD *)v6 + 16LL))(v6);
}

```

## disassembly

```asm
0x180557c40  mov     [rsp-8+arg_10], r8
0x180557c45  mov     [rsp-8+arg_0], rcx
0x180557c4a  push    rbp
0x180557c4b  push    rbx
0x180557c4c  push    rsi
0x180557c4d  push    rdi
0x180557c4e  push    r12
0x180557c50  push    r13
0x180557c52  push    r14
0x180557c54  push    r15
0x180557c56  lea     rbp, [rsp-8]
0x180557c5b  sub     rsp, 108h
0x180557c62  mov     rsi, r8
0x180557c65  mov     rax, rdx
0x180557c68  mov     r15, rcx
0x180557c6b  xor     r13d, r13d
0x180557c6e  test    rdx, rdx
0x180557c71  jz      loc_18055843D
0x180557c77  mov     [rbp+40h+var_C0], r13
0x180557c7b  lea     rdx, [rbp+40h+var_C0]
0x180557c7f  mov     rcx, rax; struct IStream *
0x180557c82  call    sub_180557AF0
0x180557c87  mov     edi, r13d
0x180557c8a  mov     [rbp+40h+var_A0], r13
0x180557c8e  mov     ecx, 0A0h; Size
0x180557c93  call    cs:__imp_malloc
0x180557c99  test    rax, rax
0x180557c9c  jz      loc_18055844B
0x180557ca2  mov     [rbp+40h+arg_18], rax
0x180557ca6  mov     rcx, rax
0x180557ca9  call    ??0?$CComObject@VEffectCollection@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<EffectCollection>::CComObject<EffectCollection>(void *)
0x180557cae  mov     r12, rax
0x180557cb1  mov     [rbp+40h+var_70], rax
0x180557cb5  test    rax, rax
0x180557cb8  jz      short loc_180557CCB
0x180557cba  mov     rcx, [rax]
0x180557cbd  mov     rax, [rcx+8]
0x180557cc1  mov     rcx, r12
0x180557cc4  call    cs:__guard_dispatch_icall_fptr
0x180557cca  nop
0x180557ccb  mov     [rbp+40h+arg_8], r13d
0x180557ccf  mov     r14, [rbp+40h+var_C0]
0x180557cd3  mov     rax, [r14]
0x180557cd6  lea     rdx, [rbp+40h+arg_8]
0x180557cda  mov     rcx, r14
0x180557cdd  mov     rax, [rax+48h]
0x180557ce1  call    cs:__guard_dispatch_icall_fptr
0x180557ce7  test    eax, eax
0x180557ce9  js      loc_180558431
0x180557cef  mov     ebx, r13d
0x180557cf2  mov     [rsp+140h+var_D0], ebx
0x180557cf6  mov     eax, [rbp+40h+arg_8]
0x180557cf9  test    eax, eax
0x180557cfb  jle     loc_180558202
0x180557d01  mov     [rsp+140h+var_108], r13
0x180557d06  mov     rax, [r14]
0x180557d09  lea     r8, [rsp+140h+var_108]
0x180557d0e  mov     edx, ebx
0x180557d10  mov     rcx, r14
0x180557d13  mov     rax, [rax+60h]
0x180557d17  call    cs:__guard_dispatch_icall_fptr
0x180557d1d  test    eax, eax
0x180557d1f  js      loc_1805584E7
0x180557d25  mov     [rsp+140h+var_E8], r13
0x180557d2a  mov     rcx, [rsp+140h+var_108]
0x180557d2f  mov     rax, [rcx]
0x180557d32  lea     rdx, [rsp+140h+var_E8]
0x180557d37  mov     rax, [rax+60h]
0x180557d3b  call    cs:__guard_dispatch_icall_fptr
0x180557d41  test    eax, eax
0x180557d43  js      loc_1805584DB
0x180557d49  mov     [rsp+140h+var_110], r13
0x180557d4e  lea     rcx, [r15+20h]
0x180557d52  mov     rax, [rcx]
0x180557d55  lea     r8, [rsp+140h+var_110]
0x180557d5a  mov     rdx, [rsp+140h+var_E8]
0x180557d5f  mov     rax, [rax+0A0h]
0x180557d66  call    cs:__guard_dispatch_icall_fptr
0x180557d6c  test    eax, eax
0x180557d6e  js      loc_1805584CF
0x180557d74  mov     [rsp+140h+bstrString], r13
0x180557d79  mov     rcx, [rsp+140h+var_108]
0x180557d7e  mov     rax, [rcx]
0x180557d81  lea     rdx, [rsp+140h+bstrString]
0x180557d86  mov     rax, [rax+58h]
0x180557d8a  call    cs:__guard_dispatch_icall_fptr
0x180557d90  test    eax, eax
0x180557d92  js      loc_1805584C3
0x180557d98  mov     rcx, [rsp+140h+var_110]
0x180557d9d  mov     rax, [rcx]
0x180557da0  mov     rdx, [rsp+140h+bstrString]
0x180557da5  mov     rax, [rax+180h]
0x180557dac  call    cs:__guard_dispatch_icall_fptr
0x180557db2  test    eax, eax
0x180557db4  js      loc_1805584BB
0x180557dba  test    rsi, rsi
0x180557dbd  jz      short loc_180557DD7
0x180557dbf  mov     rcx, [rsp+140h+var_110]
0x180557dc4  mov     rax, [rcx]
0x180557dc7  mov     rdx, rsi
0x180557dca  mov     rax, [rax+120h]
0x180557dd1  call    cs:__guard_dispatch_icall_fptr
0x180557dd7  mov     dword ptr [rbp+40h+arg_18], r13d
0x180557ddb  mov     rcx, [rsp+140h+var_108]
0x180557de0  mov     rax, [rcx]
0x180557de3  lea     rdx, [rbp+40h+arg_18]
0x180557de7  mov     rax, [rax+38h]
0x180557deb  call    cs:__guard_dispatch_icall_fptr
0x180557df1  test    eax, eax
0x180557df3  js      loc_1805584B3
0x180557df9  xor     ecx, ecx
0x180557dfb  cmp     dword ptr [rbp+40h+arg_18], ecx
0x180557dfe  jle     loc_180558176
0x180557e04  xor     r15d, r15d
0x180557e07  mov     [rsp+140h+var_100], r15
0x180557e0c  mov     rcx, [rsp+140h+var_108]
0x180557e11  mov     rax, [rcx]
0x180557e14  lea     r8, [rsp+140h+var_100]
0x180557e19  mov     edx, r13d
0x180557e1c  mov     rax, [rax+50h]
0x180557e20  call    cs:__guard_dispatch_icall_fptr
0x180557e26  test    eax, eax
0x180557e28  js      loc_1805584A7
0x180557e2e  mov     [rsp+140h+lpString1], r15
0x180557e33  mov     [rsp+140h+var_F0], r15
0x180557e38  mov     [rsp+140h+pbstr], r15
0x180557e3d  mov     rcx, [rsp+140h+var_100]
0x180557e42  mov     rax, [rcx]
0x180557e45  lea     rdx, [rsp+140h+lpString1]
0x180557e4a  mov     rax, [rax+38h]
0x180557e4e  call    cs:__guard_dispatch_icall_fptr
0x180557e54  test    eax, eax
0x180557e56  js      loc_18055849B
0x180557e5c  mov     rcx, [rsp+140h+var_100]
0x180557e61  mov     rax, [rcx]
0x180557e64  lea     rdx, [rsp+140h+var_F0]
0x180557e69  mov     rax, [rax+40h]
0x180557e6d  call    cs:__guard_dispatch_icall_fptr
0x180557e73  shr     eax, 1Fh
0x180557e76  test    al, al
0x180557e78  jnz     loc_180558490
0x180557e7e  mov     rcx, [rsp+140h+var_100]
0x180557e83  mov     rax, [rcx]
0x180557e86  lea     rdx, [rsp+140h+pbstr]
0x180557e8b  mov     rax, [rax+48h]
0x180557e8f  call    cs:__guard_dispatch_icall_fptr
0x180557e95  shr     eax, 1Fh
0x180557e98  test    al, al
0x180557e9a  jnz     loc_180558485
0x180557ea0  mov     rcx, [rsp+140h+pbstr]; pbstr
0x180557ea5  call    cs:__imp_SysStringLen
0x180557eab  test    eax, eax
0x180557ead  jz      loc_180558120
0x180557eb3  or      ebx, 0FFFFFFFFh
0x180557eb6  mov     [rsp+140h+cchCount2], ebx; cchCount2
0x180557eba  lea     rax, aHttpSchemasMic; "http://schemas.microsoft.com/expression"...
0x180557ec1  mov     [rsp+140h+lpString2], rax; lpString2
0x180557ec6  mov     r9d, ebx; cchCount1
0x180557ec9  mov     r8, [rsp+140h+lpString1]; lpString1
0x180557ece  lea     edx, [rbx+2]; dwCmpFlags
0x180557ed1  lea     esi, [rdx+7Eh]
0x180557ed4  mov     ecx, esi; Locale
0x180557ed6  call    cs:__imp_CompareStringW
0x180557edc  cmp     eax, 2
0x180557edf  jnz     loc_18055805A
0x180557ee5  mov     [rsp+140h+cchCount2], ebx; cchCount2
0x180557ee9  lea     rax, aEnabled; "Enabled"
0x180557ef0  mov     [rsp+140h+lpString2], rax; lpString2
0x180557ef5  mov     r9d, ebx; cchCount1
0x180557ef8  mov     r8, [rsp+140h+var_F0]; lpString1
0x180557efd  lea     edx, [rbx+2]; dwCmpFlags
0x180557f00  mov     ecx, esi; Locale
0x180557f02  call    cs:__imp_CompareStringW
0x180557f08  cmp     eax, 2
0x180557f0b  jnz     short loc_180557F86
0x180557f0d  mov     rsi, [rsp+140h+var_110]
0x180557f12  mov     rax, [rsi]
0x180557f15  mov     rax, [rax+0C0h]
0x180557f1c  mov     [rsp+140h+var_C8], rax
0x180557f21  lea     rcx, a0_0; "0"
0x180557f28  call    cs:__imp_SysAllocString
0x180557f2e  mov     rbx, rax
0x180557f31  test    rax, rax
0x180557f34  jz      loc_18055845F
0x180557f3a  xor     r9d, r9d; dwFlags
0x180557f3d  mov     r8d, 400h; lcid
0x180557f43  mov     rdx, rax; bstrRight
0x180557f46  mov     rcx, [rsp+140h+pbstr]; bstrLeft
0x180557f4b  call    cs:__imp_VarBstrCmp
0x180557f51  mov     r15d, eax
0x180557f54  mov     rcx, rbx; bstrString
0x180557f57  call    cs:__imp_SysFreeString
0x180557f5d  xor     ecx, ecx
0x180557f5f  mov     edx, ecx
0x180557f61  cmp     r15d, 1
0x180557f65  setnz   dl
0x180557f68  mov     rcx, rsi
0x180557f6b  mov     rax, [rsp+140h+var_C8]
0x180557f70  call    cs:__guard_dispatch_icall_fptr
0x180557f76  xor     r15d, r15d
0x180557f79  test    eax, eax
0x180557f7b  js      loc_180558415
0x180557f81  jmp     loc_180558120
0x180557f86  mov     [rsp+140h+cchCount2], ebx; cchCount2
0x180557f8a  lea     rax, aSoftwareformat; "SoftwareFormat"
0x180557f91  mov     [rsp+140h+lpString2], rax; lpString2
0x180557f96  mov     r9d, ebx; cchCount1
0x180557f99  mov     r8, [rsp+140h+var_F0]; lpString1
0x180557f9e  mov     edx, 1; dwCmpFlags
0x180557fa3  mov     ecx, esi; Locale
0x180557fa5  call    cs:__imp_CompareStringW
0x180557fab  cmp     eax, 2
0x180557fae  jnz     short loc_180557FEE
0x180557fb0  mov     rbx, [rsp+140h+var_110]
0x180557fb5  mov     rax, [rbx]
0x180557fb8  mov     rsi, [rax+0D0h]
0x180557fbf  mov     rcx, [rsp+140h+pbstr]
0x180557fc4  mov     [rsp+140h+var_C8], rcx
0x180557fc9  lea     rcx, [rsp+140h+var_C8]
0x180557fce  call    sub_180557330
0x180557fd3  mov     edx, eax
0x180557fd5  mov     rcx, rbx
0x180557fd8  mov     rax, rsi
0x180557fdb  call    cs:__guard_dispatch_icall_fptr
0x180557fe1  test    eax, eax
0x180557fe3  js      loc_18055841D
0x180557fe9  jmp     loc_180558120
0x180557fee  mov     [rsp+140h+cchCount2], ebx; cchCount2
0x180557ff2  lea     rax, aHardwareformat; "HardwareFormat"
0x180557ff9  mov     [rsp+140h+lpString2], rax; lpString2
0x180557ffe  mov     r9d, ebx; cchCount1
0x180558001  mov     r8, [rsp+140h+var_F0]; lpString1
0x180558006  mov     edx, 1; dwCmpFlags
0x18055800b  mov     ecx, esi; Locale
0x18055800d  call    cs:__imp_CompareStringW
0x180558013  cmp     eax, 2
0x180558016  jnz     loc_180558120
0x18055801c  mov     rbx, [rsp+140h+var_110]
0x180558021  mov     rax, [rbx]
0x180558024  mov     rsi, [rax+0E0h]
0x18055802b  mov     rcx, [rsp+140h+pbstr]
0x180558030  mov     [rsp+140h+var_C8], rcx
0x180558035  lea     rcx, [rsp+140h+var_C8]
0x18055803a  call    sub_180557330
0x18055803f  mov     edx, eax
0x180558041  mov     rcx, rbx
0x180558044  mov     rax, rsi
0x180558047  call    cs:__guard_dispatch_icall_fptr
0x18055804d  test    eax, eax
0x18055804f  js      loc_180558425
0x180558055  jmp     loc_180558120
0x18055805a  mov     [rbp+40h+var_98], r15w
0x18055805f  xorps   xmm0, xmm0
0x180558062  xor     eax, eax
0x180558064  movups  xmmword ptr [rbp+40h+pvarg], xmm0
0x180558068  mov     qword ptr [rbp+40h+pvarg+10h], rax
0x18055806c  lea     rcx, [rbp+40h+pvarg]; pvarg
0x180558070  call    cs:__imp_VariantInit
0x180558076  mov     [rbp+40h+var_78], 0
0x18055807e  mov     rcx, [rsp+140h+var_110]
0x180558083  mov     rax, [rcx]
0x180558086  lea     r8, [rbp+40h+var_98]
0x18055808a  mov     rdx, [rsp+140h+var_F0]
0x18055808f  mov     rax, [rax+50h]
0x180558093  call    cs:__guard_dispatch_icall_fptr
0x180558099  test    eax, eax
0x18055809b  js      loc_180558479
0x1805580a1  xorps   xmm0, xmm0
0x1805580a4  xor     eax, eax
0x1805580a6  movups  xmmword ptr [rbp+40h+var_B8], xmm0
0x1805580aa  mov     qword ptr [rbp+40h+var_B8+10h], rax
0x1805580ae  lea     rcx, [rbp+40h+var_B8]; pvarg
0x1805580b2  call    cs:__imp_VariantInit
0x1805580b8  mov     edx, 8
0x1805580bd  movzx   eax, [rbp+40h+var_98]
0x1805580c1  test    ax, ax
0x1805580c4  cmovnz  dx, ax
0x1805580c8  lea     r8, [rbp+40h+var_B8]
0x1805580cc  mov     rcx, [rsp+140h+pbstr]; wchar_t *
0x1805580d1  call    sub_18054C328
0x1805580d6  mov     rcx, [rsp+140h+var_110]
0x1805580db  mov     rax, [rcx]
0x1805580de  movups  xmm0, xmmword ptr [rbp+40h+var_B8]
0x1805580e2  movaps  [rbp+40h+var_60], xmm0
0x1805580e6  movsd   xmm1, qword ptr [rbp+40h+var_B8+10h]
0x1805580eb  movsd   [rbp+40h+var_50], xmm1
0x1805580f0  lea     r8, [rbp+40h+var_60]
0x1805580f4  mov     rdx, [rsp+140h+var_F0]
0x1805580f9  mov     rax, [rax+68h]
0x1805580fd  call    cs:__guard_dispatch_icall_fptr
0x180558103  test    eax, eax
0x180558105  js      loc_18055846D
0x18055810b  lea     rcx, [rbp+40h+var_B8]; pvarg
0x18055810f  call    cs:__imp_VariantClear
0x180558115  lea     rcx, [rbp+40h+pvarg]; pvarg
0x180558119  call    cs:__imp_VariantClear
0x18055811f  nop
0x180558120  mov     rcx, [rsp+140h+pbstr]; bstrString
0x180558125  call    cs:__imp_SysFreeString
0x18055812b  mov     rcx, [rsp+140h+var_F0]; bstrString
  ... truncated ...
```
