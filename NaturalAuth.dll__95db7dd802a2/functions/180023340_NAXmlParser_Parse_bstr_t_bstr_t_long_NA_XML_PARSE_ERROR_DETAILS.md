# NAXmlParser::Parse(_bstr_t,_bstr_t,long *,NA_XML_PARSE_ERROR_DETAILS *)

- ea: `0x180023340`
- end: `0x18002386d`
- name: `?Parse@NAXmlParser@@QEBA?AV?$ComPtr@UIXMLDOMDocument3@@@WRL@Microsoft@@V_bstr_t@@0PEAJPEAUNA_XML_PARSE_ERROR_DETAILS@@@Z`
- size: `1325`
- prototype: `LPVOID *(int *, LPVOID *, _bstr_t *, _bstr_t *, ...)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180020370`
- `0x18002d2f0`
- `0x18002ec90`

## callees

- `0x180005140`
- `0x180009a74`
- `0x180014e7c`
- `0x18002072c`
- `0x180021df4`
- `0x1800232bc`
- `0x180023340`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002345e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800234e5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023581`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002345e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800234e5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023581`
- `OLEAUT32!__imp_SysFreeString` at `0x1800237ab`
- `OLEAUT32!__imp_SysFreeString` at `0x1800237f8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800237ab`
- `OLEAUT32!__imp_SysFreeString` at `0x1800237f8`
- `OLEAUT32!__imp_VariantClear` at `0x1800235ef`
- `OLEAUT32!__imp_VariantClear` at `0x18002364e`
- `OLEAUT32!__imp_VariantClear` at `0x1800235ef`
- `OLEAUT32!__imp_VariantClear` at `0x18002364e`

## pseudocode

```c
LPVOID *NAXmlParser::Parse(int *a1, LPVOID *a2, _bstr_t *a3, _bstr_t *a4, ...)
{
  _bstr_t *v4; // r12
  _bstr_t *v5; // r15
  LPVOID *v6; // rsi
  __int64 v8; // r14
  _OWORD *v9; // rcx
  _OWORD *v10; // rax
  __int64 v11; // rdx
  HRESULT Instance; // eax
  __int64 v13; // rdx
  int v14; // eax
  HRESULT v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  HRESULT v19; // eax
  bool v20; // r8
  struct IDispatch *v21; // rdi
  HRESULT (__stdcall *QueryInterface)(IDispatch *, const IID *const, void **); // rbx
  _variant_t *v23; // rax
  int v24; // eax
  LPVOID v25; // rdi
  __int64 (__fastcall *v26)(LPVOID, __int128 *); // rbx
  bool v27; // r8
  _variant_t *v28; // rax
  int v29; // eax
  __int64 v30; // rdx
  int v31; // eax
  LPVOID v32; // rbx
  LPVOID v33; // rdi
  __int64 (__fastcall *v34)(LPVOID, LPVOID *); // rbx
  int v35; // eax
  int v36; // eax
  int v37; // eax
  int v38; // eax
  int v39; // eax
  __int64 v41; // rbx
  LPVOID v42; // [rsp+30h] [rbp-4D8h] BYREF
  LPVOID v43; // [rsp+38h] [rbp-4D0h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-4C8h] BYREF
  struct IDispatch *v45; // [rsp+48h] [rbp-4C0h] BYREF
  struct IDispatch *ppv; // [rsp+50h] [rbp-4B8h] BYREF
  int v47; // [rsp+58h] [rbp-4B0h]
  __int128 v48; // [rsp+60h] [rbp-4A8h] BYREF
  __int64 v49; // [rsp+70h] [rbp-498h]
  VARIANTARG pvarg; // [rsp+80h] [rbp-488h] BYREF
  _DWORD v51[4]; // [rsp+98h] [rbp-470h] BYREF
  __int64 v52; // [rsp+A8h] [rbp-460h]
  _BYTE v53[1096]; // [rsp+C0h] [rbp-448h] BYREF
  __int64 v54; // [rsp+510h] [rbp+8h] BYREF
  LPVOID *v55; // [rsp+518h] [rbp+10h]
  _bstr_t *v56; // [rsp+520h] [rbp+18h]
  _bstr_t *v57; // [rsp+528h] [rbp+20h]
  unsigned __int16 *v58; // [rsp+530h] [rbp+28h] BYREF
  va_list va; // [rsp+530h] [rbp+28h]
  __int64 v60; // [rsp+538h] [rbp+30h]
  va_list va1; // [rsp+540h] [rbp+38h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  v58 = va_arg(va1, unsigned __int16 *);
  v60 = va_arg(va1, _QWORD);
  v57 = a4;
  v56 = a3;
  v55 = a2;
  v4 = a4;
  v5 = a3;
  v6 = a2;
  *a2 = 0;
  v47 = 1;
  *(_DWORD *)v58 = 0;
  memset_0(v53, 0, 0x408u);
  v8 = v60;
  v9 = (_OWORD *)v60;
  v10 = v53;
  v11 = 8;
  do
  {
    *v9 = *v10;
    v9[1] = v10[1];
    v9[2] = v10[2];
    v9[3] = v10[3];
    v9[4] = v10[4];
    v9[5] = v10[5];
    v9[6] = v10[6];
    v9[7] = v10[7];
    v9 += 8;
    v10 += 8;
    --v11;
  }
  while ( v11 );
  try
  {
    *(_QWORD *)v9 = *(_QWORD *)v10;
    *(_DWORD *)v8 = -1;
    *(_DWORD *)(v8 + 4) = -1;
    if ( *a1 < 0 )
      _com_issue_error(*a1);
    ppv = 0;
    v45 = 0;
    v42 = 0;
    LOWORD(v54) = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
    Instance = CoCreateInstance(
                 &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
                 0,
                 1u,
                 &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60,
                 (LPVOID *)&ppv);
    if ( Instance < 0 )
      _com_issue_error(Instance);
    if ( *(_QWORD *)v4 )
      v13 = **(_QWORD **)v4;
    else
      v13 = 0;
    v14 = ((__int64 (__fastcall *)(struct IDispatch *, __int64, __int64 *))ppv->lpVtbl[9].Release)(ppv, v13, &v54);
    if ( v14 < 0 )
      _com_issue_error(v14);
    if ( !(_WORD)v54 )
      _com_issue_error(-2147023537);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
    v15 = CoCreateInstance(
            &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
            0,
            1u,
            &GUID_2933bf96_7b36_11d2_b20e_00c04f983e60,
            &v42);
    if ( v15 < 0 )
      _com_issue_error(v15);
    v16 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v42 + 504LL))(v42, 0);
    if ( v16 < 0 )
      _com_issue_error(v16);
    v17 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v42 + 544LL))(v42, 0xFFFFFFFFLL);
    if ( v17 < 0 )
      _com_issue_error(v17);
    v18 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v42 + 560LL))(v42, 0);
    if ( v18 < 0 )
      _com_issue_error(v18);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
    v19 = CoCreateInstance(
            &GUID_88d96a07_f192_11d4_a65f_0040963251e5,
            0,
            1u,
            &GUID_373984c8_b845_449b_91e7_45ac83036ade,
            (LPVOID *)&v45);
    if ( v19 < 0 )
      _com_issue_error(v19);
    v21 = v45;
    QueryInterface = v45->lpVtbl[1].QueryInterface;
    v23 = _variant_t::_variant_t((_variant_t *)&pvarg, ppv, v20);
    v48 = *(_OWORD *)v23;
    v49 = *((_QWORD *)v23 + 2);
    v24 = ((__int64 (__fastcall *)(struct IDispatch *, const WCHAR *, __int128 *))QueryInterface)(v21, &Class, &v48);
    if ( v24 < 0 )
      _com_issue_error(v24);
    VariantClear(&pvarg);
    v25 = v42;
    v26 = *(__int64 (__fastcall **)(LPVOID, __int128 *))(*(_QWORD *)v42 + 624LL);
    v28 = _variant_t::_variant_t((_variant_t *)&pvarg, v45, v27);
    v48 = *(_OWORD *)v28;
    v49 = *((_QWORD *)v28 + 2);
    v29 = v26(v25, &v48);
    if ( v29 < 0 )
      _com_issue_error(v29);
    VariantClear(&pvarg);
    if ( *(_QWORD *)v5 )
      v30 = **(_QWORD **)v5;
    else
      v30 = 0;
    v31 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)v42 + 520LL))(v42, v30, &v54);
    if ( v31 < 0 )
      _com_issue_error(v31);
    if ( (_WORD)v54 == 0xFFFF )
    {
      v32 = v42;
      if ( *v6 != v42 )
      {
        if ( v42 )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v42 + 8LL))(v42);
        v43 = *v6;
        *v6 = v32;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
      }
    }
    else
    {
      v43 = 0;
      bstrString = 0;
      *(_DWORD *)v58 = -2147023431;
      v33 = v42;
      v34 = *(__int64 (__fastcall **)(LPVOID, LPVOID *))(*(_QWORD *)v42 + 480LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
      v35 = v34(v33, &v43);
      if ( v35 < 0 )
        _com_issue_error(v35);
      v36 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v43 + 88LL))(v43, v8);
      if ( v36 < 0 )
        _com_issue_error(v36);
      v37 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v43 + 96LL))(v43, v8 + 4);
      if ( v37 < 0 )
        _com_issue_error(v37);
      v38 = (*(__int64 (__fastcall **)(LPVOID, BSTR *))(*(_QWORD *)v43 + 72LL))(v43, &bstrString);
      if ( v38 < 0 )
        _com_issue_error(v38);
      if ( bstrString )
      {
        StringCchCopyW((unsigned __int16 *)(v8 + 520), 0x100u, bstrString);
        SysFreeString(bstrString);
        bstrString = 0;
      }
      v39 = (*(__int64 (__fastcall **)(LPVOID, BSTR *))(*(_QWORD *)v43 + 80LL))(v43, &bstrString);
      if ( v39 < 0 )
        _com_issue_error(v39);
      if ( bstrString )
      {
        StringCchCopyW((unsigned __int16 *)(v8 + 8), 0x100u, bstrString);
        SysFreeString(bstrString);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  }
  catch ( _com_error v51 )
  {
    *(_DWORD *)v58 = v51[2];
    v41 = v52;
    if ( v52 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 8LL))(v52);
    v54 = v41;
    if ( v41 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 8LL))(v41);
      v58 = 0;
      (*(void (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v41 + 40LL))(v41, (unsigned __int16 **)va);
      if ( v58 )
      {
        StringCchCopyW((unsigned __int16 *)(v60 + 520), 0x100u, v58);
        SysFreeString(v58);
      }
    }
    if ( v41 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    _com_error::~_com_error((_com_error *)v51);
    v4 = v57;
    v5 = v56;
    v6 = v55;
  }
  *(_QWORD *)v9 = *(_QWORD *)v10;
  *(_DWORD *)v8 = -1;
  *(_DWORD *)(v8 + 4) = -1;
}

```

## disassembly

```asm
0x180023340  mov     r11, rsp
0x180023343  mov     [r11+20h], r9
0x180023347  mov     [r11+18h], r8
0x18002334b  mov     [r11+10h], rdx
0x18002334f  push    rbx
0x180023350  push    rsi
0x180023351  push    rdi
0x180023352  push    r12
0x180023354  push    r13
0x180023356  push    r14
0x180023358  push    r15
0x18002335a  sub     rsp, 4D0h
0x180023361  mov     r12, r9
0x180023364  mov     r15, r8
0x180023367  mov     rsi, rdx
0x18002336a  mov     rbx, rcx
0x18002336d  xor     edi, edi
0x18002336f  mov     [rsp+508h+var_4B0], edi
0x180023373  mov     [rdx], rdi
0x180023376  mov     [rsp+508h+var_4B0], 1
0x18002337e  mov     rax, [rsp+508h+arg_20]
0x180023386  mov     [rax], edi
0x180023388  xor     edx, edx; Val
0x18002338a  mov     r8d, 408h; Size
0x180023390  lea     rcx, [r11-448h]; void *
0x180023397  call    memset_0
0x18002339c  mov     r14, [rsp+508h+arg_28]
0x1800233a4  mov     rcx, r14
0x1800233a7  lea     rax, [rsp+508h+var_448]
0x1800233af  lea     edx, [rdi+8]
0x1800233b2  lea     r8d, [rdx+78h]
0x1800233b6  movups  xmm0, xmmword ptr [rax]
0x1800233b9  movups  xmmword ptr [rcx], xmm0
0x1800233bc  movups  xmm1, xmmword ptr [rax+10h]
0x1800233c0  movups  xmmword ptr [rcx+10h], xmm1
0x1800233c4  movups  xmm0, xmmword ptr [rax+20h]
0x1800233c8  movups  xmmword ptr [rcx+20h], xmm0
0x1800233cc  movups  xmm1, xmmword ptr [rax+30h]
0x1800233d0  movups  xmmword ptr [rcx+30h], xmm1
0x1800233d4  movups  xmm0, xmmword ptr [rax+40h]
0x1800233d8  movups  xmmword ptr [rcx+40h], xmm0
0x1800233dc  movups  xmm1, xmmword ptr [rax+50h]
0x1800233e0  movups  xmmword ptr [rcx+50h], xmm1
0x1800233e4  movups  xmm0, xmmword ptr [rax+60h]
0x1800233e8  movups  xmmword ptr [rcx+60h], xmm0
0x1800233ec  movups  xmm1, xmmword ptr [rax+70h]
0x1800233f0  movups  xmmword ptr [rcx+70h], xmm1
0x1800233f4  add     rcx, r8
0x1800233f7  add     rax, r8
0x1800233fa  sub     rdx, 1
0x1800233fe  jnz     short loc_1800233B6
0x180023400  mov     rax, [rax]
0x180023403  mov     [rcx], rax
0x180023406  or      eax, 0FFFFFFFFh
0x180023409  mov     [r14], eax
0x18002340c  mov     [r14+4], eax
0x180023410  mov     ecx, [rbx]; int
0x180023412  test    ecx, ecx
0x180023414  jns     short loc_18002341B
0x180023416  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18002341b  mov     [rsp+508h+var_4B8], rdi
0x180023420  mov     [rsp+508h+var_4C0], rdi
0x180023425  mov     [rsp+508h+var_4D8], rdi
0x18002342a  mov     word ptr [rsp+508h+arg_0], di
0x180023432  lea     rcx, [rsp+508h+var_4B8]
0x180023437  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002343c  lea     rax, [rsp+508h+var_4B8]
0x180023441  mov     [rsp+508h+ppv], rax; ppv
0x180023446  lea     r9, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; riid
0x18002344d  mov     ebx, 1
0x180023452  mov     r8d, ebx; dwClsContext
0x180023455  xor     edx, edx; pUnkOuter
0x180023457  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x18002345e  call    cs:__imp_CoCreateInstance
0x180023464  test    eax, eax
0x180023466  jns     short loc_18002346F
0x180023468  mov     ecx, eax; int
0x18002346a  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18002346f  mov     rcx, [rsp+508h+var_4B8]
0x180023474  mov     rax, [rcx]
0x180023477  mov     r9, [rax+208h]
0x18002347e  mov     rax, [r12]
0x180023482  test    rax, rax
0x180023485  jz      short loc_18002348C
0x180023487  mov     rdx, [rax]
0x18002348a  jmp     short loc_18002348F
0x18002348c  mov     rdx, rdi
0x18002348f  lea     r8, [rsp+508h+arg_0]
0x180023497  mov     rax, r9
0x18002349a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002349f  test    eax, eax
0x1800234a1  jns     short loc_1800234AA
0x1800234a3  mov     ecx, eax; int
0x1800234a5  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800234aa  cmp     di, word ptr [rsp+508h+arg_0]
0x1800234b2  jnz     short loc_1800234BE
0x1800234b4  mov     ecx, 8007054Fh; int
0x1800234b9  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800234be  lea     rcx, [rsp+508h+var_4D8]
0x1800234c3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800234c8  lea     rax, [rsp+508h+var_4D8]
0x1800234cd  mov     [rsp+508h+ppv], rax; ppv
0x1800234d2  lea     r9, _GUID_2933bf96_7b36_11d2_b20e_00c04f983e60; riid
0x1800234d9  mov     r8d, ebx; dwClsContext
0x1800234dc  xor     edx, edx; pUnkOuter
0x1800234de  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x1800234e5  call    cs:__imp_CoCreateInstance
0x1800234eb  test    eax, eax
0x1800234ed  jns     short loc_1800234F6
0x1800234ef  mov     ecx, eax; int
0x1800234f1  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800234f6  mov     rcx, [rsp+508h+var_4D8]
0x1800234fb  mov     rax, [rcx]
0x1800234fe  xor     edx, edx
0x180023500  mov     rax, [rax+1F8h]
0x180023507  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002350c  test    eax, eax
0x18002350e  jns     short loc_180023517
0x180023510  mov     ecx, eax; int
0x180023512  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180023517  mov     rcx, [rsp+508h+var_4D8]
0x18002351c  mov     rax, [rcx]
0x18002351f  or      edx, 0FFFFFFFFh
0x180023522  mov     rax, [rax+220h]
0x180023529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002352e  test    eax, eax
0x180023530  jns     short loc_180023539
0x180023532  mov     ecx, eax; int
0x180023534  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180023539  mov     rcx, [rsp+508h+var_4D8]
0x18002353e  mov     rax, [rcx]
0x180023541  xor     edx, edx
0x180023543  mov     rax, [rax+230h]
0x18002354a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002354f  test    eax, eax
0x180023551  jns     short loc_18002355A
0x180023553  mov     ecx, eax; int
0x180023555  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18002355a  lea     rcx, [rsp+508h+var_4C0]
0x18002355f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180023564  lea     rax, [rsp+508h+var_4C0]
0x180023569  mov     [rsp+508h+ppv], rax; ppv
0x18002356e  lea     r9, _GUID_373984c8_b845_449b_91e7_45ac83036ade; riid
0x180023575  mov     r8d, ebx; dwClsContext
0x180023578  xor     edx, edx; pUnkOuter
0x18002357a  lea     rcx, _GUID_88d96a07_f192_11d4_a65f_0040963251e5; rclsid
0x180023581  call    cs:__imp_CoCreateInstance
0x180023587  test    eax, eax
0x180023589  jns     short loc_180023592
0x18002358b  mov     ecx, eax; int
0x18002358d  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180023592  mov     rdi, [rsp+508h+var_4C0]
0x180023597  mov     rax, [rdi]
0x18002359a  mov     rbx, [rax+38h]
0x18002359e  mov     rdx, [rsp+508h+var_4B8]; struct IDispatch *
0x1800235a3  lea     rcx, [rsp+508h+pvarg]; this
0x1800235ab  call    ??0_variant_t@@QEAA@PEAUIDispatch@@_N@Z; _variant_t::_variant_t(IDispatch *,bool)
0x1800235b0  nop
0x1800235b1  movups  xmm0, xmmword ptr [rax]
0x1800235b4  movaps  [rsp+508h+var_4A8], xmm0
0x1800235b9  movsd   xmm1, qword ptr [rax+10h]
0x1800235be  movsd   [rsp+508h+var_498], xmm1
0x1800235c4  lea     r8, [rsp+508h+var_4A8]
0x1800235c9  lea     rdx, Class
0x1800235d0  mov     rcx, rdi
0x1800235d3  mov     rax, rbx
0x1800235d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800235db  test    eax, eax
0x1800235dd  jns     short loc_1800235E7
0x1800235df  mov     ecx, eax; int
0x1800235e1  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800235e7  lea     rcx, [rsp+508h+pvarg]; pvarg
0x1800235ef  call    cs:__imp_VariantClear
0x1800235f5  mov     rdi, [rsp+508h+var_4D8]
0x1800235fa  mov     rax, [rdi]
0x1800235fd  mov     rbx, [rax+270h]
0x180023604  mov     rdx, [rsp+508h+var_4C0]; struct IDispatch *
0x180023609  lea     rcx, [rsp+508h+pvarg]; this
0x180023611  call    ??0_variant_t@@QEAA@PEAUIDispatch@@_N@Z; _variant_t::_variant_t(IDispatch *,bool)
0x180023616  nop
0x180023617  movups  xmm0, xmmword ptr [rax]
0x18002361a  movaps  [rsp+508h+var_4A8], xmm0
0x18002361f  movsd   xmm1, qword ptr [rax+10h]
0x180023624  movsd   [rsp+508h+var_498], xmm1
0x18002362a  lea     rdx, [rsp+508h+var_4A8]
0x18002362f  mov     rcx, rdi
0x180023632  mov     rax, rbx
0x180023635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002363a  test    eax, eax
0x18002363c  jns     short loc_180023646
0x18002363e  mov     ecx, eax; int
0x180023640  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180023646  lea     rcx, [rsp+508h+pvarg]; pvarg
0x18002364e  call    cs:__imp_VariantClear
0x180023654  mov     rcx, [rsp+508h+var_4D8]
0x180023659  mov     rax, [rcx]
0x18002365c  mov     r9, [rax+208h]
0x180023663  mov     rax, [r15]
0x180023666  test    rax, rax
0x180023669  jz      short loc_180023670
0x18002366b  mov     rdx, [rax]
0x18002366e  jmp     short loc_180023672
0x180023670  xor     edx, edx
0x180023672  lea     r8, [rsp+508h+arg_0]
0x18002367a  mov     rax, r9
0x18002367d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023682  test    eax, eax
0x180023684  jns     short loc_18002368D
0x180023686  mov     ecx, eax; int
0x180023688  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18002368d  or      eax, 0FFFFFFFFh
0x180023690  cmp     ax, word ptr [rsp+508h+arg_0]
0x180023698  jnz     short loc_1800236D7
0x18002369a  mov     rbx, [rsp+508h+var_4D8]
0x18002369f  cmp     [rsi], rbx
0x1800236a2  jz      loc_18002380A
0x1800236a8  test    rbx, rbx
0x1800236ab  jz      short loc_1800236BD
0x1800236ad  mov     rax, [rbx]
0x1800236b0  mov     rcx, rbx
0x1800236b3  mov     rax, [rax+8]
0x1800236b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800236bc  nop
0x1800236bd  mov     rax, [rsi]
0x1800236c0  mov     [rsp+508h+var_4D0], rax
0x1800236c5  mov     [rsi], rbx
0x1800236c8  lea     rcx, [rsp+508h+var_4D0]
0x1800236cd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800236d2  jmp     loc_18002380A
0x1800236d7  mov     [rsp+508h+var_4D0], 0
0x1800236e0  mov     [rsp+508h+bstrString], 0
0x1800236e9  mov     rax, [rsp+508h+arg_20]
0x1800236f1  mov     dword ptr [rax], 800705B9h
0x1800236f7  mov     rdi, [rsp+508h+var_4D8]
0x1800236fc  mov     rax, [rdi]
0x1800236ff  mov     rbx, [rax+1E0h]
0x180023706  lea     rcx, [rsp+508h+var_4D0]
0x18002370b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180023710  lea     rdx, [rsp+508h+var_4D0]
0x180023715  mov     rcx, rdi
0x180023718  mov     rax, rbx
0x18002371b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023720  test    eax, eax
0x180023722  jns     short loc_18002372B
0x180023724  mov     ecx, eax; int
0x180023726  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18002372b  mov     rcx, [rsp+508h+var_4D0]
0x180023730  mov     rax, [rcx]
0x180023733  mov     rdx, r14
0x180023736  mov     rax, [rax+58h]
0x18002373a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002373f  test    eax, eax
0x180023741  jns     short loc_18002374A
0x180023743  mov     ecx, eax; int
0x180023745  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18002374a  mov     rcx, [rsp+508h+var_4D0]
0x18002374f  mov     rax, [rcx]
0x180023752  lea     rdx, [r14+4]
0x180023756  mov     rax, [rax+60h]
0x18002375a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002375f  test    eax, eax
0x180023761  jns     short loc_18002376A
0x180023763  mov     ecx, eax; int
0x180023765  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18002376a  mov     rcx, [rsp+508h+var_4D0]
0x18002376f  mov     rax, [rcx]
0x180023772  lea     rdx, [rsp+508h+bstrString]
0x180023777  mov     rax, [rax+48h]
0x18002377b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023780  test    eax, eax
0x180023782  jns     short loc_18002378B
0x180023784  mov     ecx, eax; int
0x180023786  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18002378b  mov     r8, [rsp+508h+bstrString]; unsigned __int16 *
0x180023790  test    r8, r8
0x180023793  jz      short loc_1800237BA
0x180023795  lea     rcx, [r14+208h]; unsigned __int16 *
0x18002379c  mov     edx, 100h; unsigned __int64
0x1800237a1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800237a6  mov     rcx, [rsp+508h+bstrString]; bstrString
0x1800237ab  call    cs:__imp_SysFreeString
0x1800237b1  mov     [rsp+508h+bstrString], 0
0x1800237ba  mov     rcx, [rsp+508h+var_4D0]
0x1800237bf  mov     rax, [rcx]
0x1800237c2  lea     rdx, [rsp+508h+bstrString]
0x1800237c7  mov     rax, [rax+50h]
0x1800237cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800237d0  test    eax, eax
0x1800237d2  jns     short loc_1800237DB
0x1800237d4  mov     ecx, eax; int
0x1800237d6  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800237db  mov     r8, [rsp+508h+bstrString]; unsigned __int16 *
0x1800237e0  test    r8, r8
0x1800237e3  jz      short loc_1800237FF
0x1800237e5  lea     rcx, [r14+8]; unsigned __int16 *
0x1800237e9  mov     edx, 100h; unsigned __int64
0x1800237ee  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800237f3  mov     rcx, [rsp+508h+bstrString]; bstrString
0x1800237f8  call    cs:__imp_SysFreeString
0x1800237fe  nop
  ... truncated ...
```
