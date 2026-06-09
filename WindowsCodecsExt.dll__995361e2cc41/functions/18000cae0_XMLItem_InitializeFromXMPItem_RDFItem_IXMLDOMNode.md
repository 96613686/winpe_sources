# XMLItem::InitializeFromXMPItem(RDFItem *,IXMLDOMNode *)

- ea: `0x18000cae0`
- end: `0x18000cf77`
- name: `?InitializeFromXMPItem@XMLItem@@QEAAJPEAVRDFItem@@PEAUIXMLDOMNode@@@Z`
- size: `1175`
- prototype: `__int64 __fastcall(XMLItem *__hidden this, struct RDFItem *, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c7b0`

## callees

- `0x18000cae0`
- `0x1800171c4`
- `0x180033010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000cd03`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ce1b`
- `OLEAUT32!__imp_SysAllocString` at `0x18000cd03`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ce1b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cb59`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cf68`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cb59`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cf68`
- `OLEAUT32!__imp_SysStringLen` at `0x18000cbd5`
- `OLEAUT32!__imp_SysStringLen` at `0x18000cc6f`
- `OLEAUT32!__imp_SysStringLen` at `0x18000ceb2`
- `OLEAUT32!__imp_SysStringLen` at `0x18000cef6`
- `OLEAUT32!__imp_SysStringLen` at `0x18000cbd5`
- `OLEAUT32!__imp_SysStringLen` at `0x18000cc6f`
- `OLEAUT32!__imp_SysStringLen` at `0x18000ceb2`
- `OLEAUT32!__imp_SysStringLen` at `0x18000cef6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000cbfd`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000cc97`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000ceda`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000cf1e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000cbfd`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000cc97`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000ceda`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000cf1e`
- `WindowsCodecs!WICMapSchemaToName` at `0x18000cc22`
- `WindowsCodecs!WICMapSchemaToName` at `0x18000cc22`

## string_xrefs

- `0x18000cbdf`: `xmlns`
- `0x18000cebc`: `xmlns`

## pseudocode

```c
__int64 __fastcall XMLItem::InitializeFromXMPItem(XMLItem *this, struct RDFItem *a2, struct IXMLDOMNode *a3)
{
  __int64 v3; // rax
  __int64 v4; // rdi
  __int64 (__fastcall *v7)(struct RDFItem *, LPWSTR *); // rax
  int v9; // eax
  unsigned int v10; // ebx
  __int64 (__fastcall *v12)(__int64, BSTR *); // rax
  UINT v13; // eax
  UINT v14; // eax
  BSTR v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rcx
  UINT v18; // eax
  UINT v19; // eax
  LPWSTR pwzSchema; // [rsp+30h] [rbp-20h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-18h] BYREF
  BSTR v22; // [rsp+40h] [rbp-10h] BYREF
  OLECHAR *psz; // [rsp+48h] [rbp-8h] BYREF
  UINT pcchActual; // [rsp+88h] [rbp+38h] BYREF
  BSTR pbstr; // [rsp+98h] [rbp+48h] BYREF

  v3 = *(_QWORD *)a2;
  v4 = *((_QWORD *)a2 + 2);
  pbstr = 0;
  bstrString = 0;
  v7 = *(__int64 (__fastcall **)(struct RDFItem *, LPWSTR *))(v3 + 56);
  pwzSchema = 0;
  v22 = 0;
  psz = 0;
  v9 = v7(a2, &pwzSchema);
  v10 = v9;
  if ( v9 < 0 )
  {
    if ( !g_doStackCaptures )
      goto LABEL_4;
    goto LABEL_3;
  }
  if ( pwzSchema && !*pwzSchema )
  {
    v9 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v4 + 320LL))(v4, &pbstr);
    v10 = v9;
    if ( v9 < 0 )
    {
      if ( g_doStackCaptures )
        goto LABEL_3;
      goto LABEL_4;
    }
    if ( !v9 )
    {
      v18 = SysStringLen(pbstr);
      if ( CompareStringW(0x400u, 0, pbstr, v18, L"xmlns", 5) != 2 )
        goto LABEL_24;
      *((_DWORD *)this + 2) |= 1u;
      goto LABEL_20;
    }
    v10 = -2147467259;
    if ( !g_doStackCaptures )
      goto LABEL_4;
    goto LABEL_47;
  }
  v12 = *(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v4 + 320LL);
  if ( pwzSchema )
  {
    pcchActual = 0;
    v9 = v12(v4, &pbstr);
    v10 = v9;
    if ( v9 < 0 )
    {
      if ( g_doStackCaptures )
      {
LABEL_3:
        DoStackCapture(v9);
        goto LABEL_4;
      }
      goto LABEL_4;
    }
    if ( !v9 )
    {
      v13 = SysStringLen(pbstr);
      if ( CompareStringW(0x400u, 0, pbstr, v13, L"xmlns", 5) == 2 )
      {
        *((_DWORD *)this + 2) |= 1u;
      }
      else
      {
        if ( WICMapSchemaToName(&GUID_MetadataFormatXMP, pwzSchema, 0, 0, &pcchActual) < 0 )
        {
          v14 = SysStringLen(pwzSchema);
          if ( CompareStringW(0x400u, 0, pwzSchema, v14, L"http://www.w3.org/1999/02/22-rdf-syntax-ns#", 43) != 2 )
            goto LABEL_24;
        }
        *((_DWORD *)this + 2) |= 2u;
      }
      goto LABEL_20;
    }
    v10 = -2147467259;
    if ( !g_doStackCaptures )
      goto LABEL_4;
LABEL_47:
    DoStackCapture(-2147467259);
    goto LABEL_4;
  }
  v9 = v12(v4, &pbstr);
  v10 = v9;
  if ( v9 < 0 )
  {
    if ( g_doStackCaptures )
      goto LABEL_3;
    goto LABEL_4;
  }
  if ( !v9 )
  {
    v10 = -2003292351;
    if ( !g_doStackCaptures )
      goto LABEL_4;
LABEL_25:
    DoStackCapture(-2003292351);
    goto LABEL_4;
  }
  v9 = (*(__int64 (__fastcall **)(struct RDFItem *, BSTR *))(*(_QWORD *)a2 + 32LL))(a2, &v22);
  v10 = v9;
  if ( v9 < 0 )
  {
    if ( g_doStackCaptures )
      goto LABEL_3;
    goto LABEL_4;
  }
  v19 = SysStringLen(v22);
  if ( CompareStringW(0x400u, 0, v22, v19, L"about", 5) != 2 )
  {
LABEL_24:
    v10 = -2003292351;
    if ( !g_doStackCaptures )
      goto LABEL_4;
    goto LABEL_25;
  }
  *((_DWORD *)this + 2) |= 6u;
LABEL_20:
  v9 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v4 + 208LL))(v4, &bstrString);
  v10 = v9;
  if ( v9 >= 0 )
  {
    if ( v9 != 1 || (bstrString = SysAllocString(&word_180037ED4)) != 0 )
    {
      v9 = (*(__int64 (__fastcall **)(struct RDFItem *, OLECHAR **))(*(_QWORD *)a2 + 24LL))(a2, &psz);
      v10 = v9;
      if ( v9 < 0 )
      {
        if ( g_doStackCaptures )
          goto LABEL_3;
        goto LABEL_4;
      }
      v15 = SysAllocString(psz);
      if ( v15 )
      {
        *((_QWORD *)this + 5) = v15;
        *((_QWORD *)this + 4) = bstrString;
        v16 = *((_QWORD *)this + 2);
        bstrString = 0;
        if ( v16 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
        *((_QWORD *)this + 2) = v4;
        if ( v4 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
        v17 = *((_QWORD *)this + 3);
        if ( v17 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
        *((_QWORD *)this + 3) = a3;
        if ( a3 )
          ((void (__fastcall *)(struct IXMLDOMNode *))a3->lpVtbl->AddRef)(a3);
        goto LABEL_4;
      }
      v10 = -2147024882;
      if ( !g_doStackCaptures )
        goto LABEL_4;
    }
    else
    {
      v10 = -2147024882;
      if ( !g_doStackCaptures )
        goto LABEL_4;
    }
    DoStackCapture(-2147024882);
    goto LABEL_4;
  }
  if ( g_doStackCaptures )
    goto LABEL_3;
LABEL_4:
  if ( pbstr )
  {
    SysFreeString(pbstr);
    pbstr = 0;
  }
  if ( bstrString )
    SysFreeString(bstrString);
  return v10;
}

```

## disassembly

```asm
0x18000cae0  mov     [rsp-28h+arg_0], rbx
0x18000cae5  mov     [rsp-28h+arg_10], rsi
0x18000caea  push    rbp
0x18000caeb  push    rdi
0x18000caec  push    r12
0x18000caee  push    r14
0x18000caf0  push    r15
0x18000caf2  mov     rbp, rsp
0x18000caf5  sub     rsp, 50h
0x18000caf9  mov     rax, [rdx]
0x18000cafc  xor     r12d, r12d
0x18000caff  mov     rdi, [rdx+10h]
0x18000cb03  mov     r14, rdx
0x18000cb06  mov     rsi, rcx
0x18000cb09  mov     [rbp+pbstr], r12
0x18000cb0d  lea     rdx, [rbp+pwzSchema]
0x18000cb11  mov     [rbp+bstrString], r12
0x18000cb15  mov     rax, [rax+38h]
0x18000cb19  mov     rcx, r14
0x18000cb1c  mov     r15, r8
0x18000cb1f  mov     [rbp+pwzSchema], r12
0x18000cb23  mov     [rbp+var_10], r12
0x18000cb27  mov     [rbp+psz], r12
0x18000cb2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb30  mov     ebx, eax
0x18000cb32  test    eax, eax
0x18000cb34  jns     short loc_18000CB7A
0x18000cb36  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18000cb3d  jnz     loc_18000CCC0
0x18000cb43  mov     rcx, [rbp+pbstr]; bstrString
0x18000cb47  test    rcx, rcx
0x18000cb4a  jnz     loc_18000CF68
0x18000cb50  mov     rcx, [rbp+bstrString]; bstrString
0x18000cb54  test    rcx, rcx
0x18000cb57  jz      short loc_18000CB5F
0x18000cb59  call    cs:__imp_SysFreeString
0x18000cb5f  lea     r11, [rsp+50h+var_s0]
0x18000cb64  mov     eax, ebx
0x18000cb66  mov     rbx, [r11+30h]
0x18000cb6a  mov     rsi, [r11+40h]
0x18000cb6e  mov     rsp, r11
0x18000cb71  pop     r15
0x18000cb73  pop     r14
0x18000cb75  pop     r12
0x18000cb77  pop     rdi
0x18000cb78  pop     rbp
0x18000cb79  retn
0x18000cb7a  mov     rcx, [rbp+pwzSchema]
0x18000cb7e  test    rcx, rcx
0x18000cb81  jz      short loc_18000CB8D
0x18000cb83  cmp     [rcx], r12w
0x18000cb87  jz      loc_18000CD95
0x18000cb8d  mov     rax, [rdi]
0x18000cb90  lea     rdx, [rbp+pbstr]
0x18000cb94  test    rcx, rcx
0x18000cb97  mov     rcx, rdi
0x18000cb9a  mov     rax, [rax+140h]
0x18000cba1  jz      loc_18000CDCE
0x18000cba7  mov     [rbp+pcchActual], r12d
0x18000cbab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbb0  mov     ebx, eax
0x18000cbb2  test    eax, eax
0x18000cbb4  jns     short loc_18000CBCB
0x18000cbb6  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18000cbbd  jz      short loc_18000CB43
0x18000cbbf  mov     ecx, eax; int
0x18000cbc1  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000cbc6  jmp     loc_18000CB43
0x18000cbcb  jnz     loc_18000CDF6
0x18000cbd1  mov     rcx, [rbp+pbstr]; pbstr
0x18000cbd5  call    cs:__imp_SysStringLen
0x18000cbdb  mov     r8, [rbp+pbstr]; lpString1
0x18000cbdf  lea     rcx, aXmlns; "xmlns"
0x18000cbe6  mov     [rsp+50h+cchCount2], 5; cchCount2
0x18000cbee  mov     r9d, eax; cchCount1
0x18000cbf1  mov     [rsp+50h+lpString2], rcx; lpString2
0x18000cbf6  xor     edx, edx; dwCmpFlags
0x18000cbf8  mov     ecx, 400h; Locale
0x18000cbfd  call    cs:__imp_CompareStringW
0x18000cc03  cmp     eax, 2
0x18000cc06  jz      short loc_18000CC32
0x18000cc08  mov     rdx, [rbp+pwzSchema]; pwzSchema
0x18000cc0c  lea     rax, [rbp+pcchActual]
0x18000cc10  xor     r9d, r9d; wzName
0x18000cc13  mov     [rsp+50h+lpString2], rax; pcchActual
0x18000cc18  xor     r8d, r8d; cchName
0x18000cc1b  lea     rcx, GUID_MetadataFormatXMP; guidMetadataFormat
0x18000cc22  call    cs:__imp_WICMapSchemaToName
0x18000cc28  test    eax, eax
0x18000cc2a  js      short loc_18000CC6B
0x18000cc2c  or      dword ptr [rsi+8], 2
0x18000cc30  jmp     short loc_18000CC36
0x18000cc32  or      dword ptr [rsi+8], 1
0x18000cc36  mov     rax, [rdi]
0x18000cc39  lea     rdx, [rbp+bstrString]
0x18000cc3d  mov     rcx, rdi
0x18000cc40  mov     rax, [rax+0D0h]
0x18000cc47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc4c  mov     ebx, eax
0x18000cc4e  test    eax, eax
0x18000cc50  jns     short loc_18000CCCC
0x18000cc52  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18000cc59  jz      loc_18000CB43
0x18000cc5f  mov     ecx, eax; int
0x18000cc61  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000cc66  jmp     loc_18000CB43
0x18000cc6b  mov     rcx, [rbp+pwzSchema]; pbstr
0x18000cc6f  call    cs:__imp_SysStringLen
0x18000cc75  mov     r8, [rbp+pwzSchema]; lpString1
0x18000cc79  lea     rcx, aHttpWwwW3Org19; "http://www.w3.org/1999/02/22-rdf-syntax"...
0x18000cc80  mov     [rsp+50h+cchCount2], 2Bh ; '+'; cchCount2
0x18000cc88  mov     r9d, eax; cchCount1
0x18000cc8b  mov     [rsp+50h+lpString2], rcx; lpString2
0x18000cc90  xor     edx, edx; dwCmpFlags
0x18000cc92  mov     ecx, 400h; Locale
0x18000cc97  call    cs:__imp_CompareStringW
0x18000cc9d  cmp     eax, 2
0x18000cca0  jz      short loc_18000CC2C
0x18000cca2  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18000cca9  mov     ebx, 88982F41h
0x18000ccae  jz      loc_18000CB43
0x18000ccb4  mov     ecx, ebx; int
0x18000ccb6  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000ccbb  jmp     loc_18000CB43
0x18000ccc0  mov     ecx, eax; int
0x18000ccc2  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000ccc7  jmp     loc_18000CB43
0x18000cccc  cmp     eax, 1
0x18000cccf  jz      loc_18000CE14
0x18000ccd5  mov     rax, [r14]
0x18000ccd8  lea     rdx, [rbp+psz]
0x18000ccdc  mov     rcx, r14
0x18000ccdf  mov     rax, [rax+18h]
0x18000cce3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cce8  mov     ebx, eax
0x18000ccea  test    eax, eax
0x18000ccec  jns     short loc_18000CCFF
0x18000ccee  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18000ccf5  jnz     short loc_18000CD6D
0x18000ccf7  test    eax, eax
0x18000ccf9  js      loc_18000CB43
0x18000ccff  mov     rcx, [rbp+psz]; psz
0x18000cd03  call    cs:__imp_SysAllocString
0x18000cd09  test    rax, rax
0x18000cd0c  jz      loc_18000CE4C
0x18000cd12  mov     [rsi+28h], rax
0x18000cd16  mov     rax, [rbp+bstrString]
0x18000cd1a  mov     [rsi+20h], rax
0x18000cd1e  mov     rcx, [rsi+10h]
0x18000cd22  mov     [rbp+bstrString], r12
0x18000cd26  test    rcx, rcx
0x18000cd29  jnz     short loc_18000CD79
0x18000cd2b  mov     [rsi+10h], rdi
0x18000cd2f  test    rdi, rdi
0x18000cd32  jz      short loc_18000CD43
0x18000cd34  mov     rax, [rdi]
0x18000cd37  mov     rcx, rdi
0x18000cd3a  mov     rax, [rax+8]
0x18000cd3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd43  mov     rcx, [rsi+18h]
0x18000cd47  test    rcx, rcx
0x18000cd4a  jnz     short loc_18000CD87
0x18000cd4c  mov     [rsi+18h], r15
0x18000cd50  test    r15, r15
0x18000cd53  jz      loc_18000CB43
0x18000cd59  mov     rax, [r15]
0x18000cd5c  mov     rcx, r15
0x18000cd5f  mov     rax, [rax+8]
0x18000cd63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd68  jmp     loc_18000CB43
0x18000cd6d  mov     ecx, eax; int
0x18000cd6f  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000cd74  jmp     loc_18000CB43
0x18000cd79  mov     rax, [rcx]
0x18000cd7c  mov     rax, [rax+10h]
0x18000cd80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd85  jmp     short loc_18000CD2B
0x18000cd87  mov     rax, [rcx]
0x18000cd8a  mov     rax, [rax+10h]
0x18000cd8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd93  jmp     short loc_18000CD4C
0x18000cd95  mov     rax, [rdi]
0x18000cd98  lea     rdx, [rbp+pbstr]
0x18000cd9c  mov     rcx, rdi
0x18000cd9f  mov     rax, [rax+140h]
0x18000cda6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdab  mov     ebx, eax
0x18000cdad  test    eax, eax
0x18000cdaf  jns     loc_18000CE6A
0x18000cdb5  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18000cdbc  jz      loc_18000CB43
0x18000cdc2  mov     ecx, eax; int
0x18000cdc4  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000cdc9  jmp     loc_18000CB43
0x18000cdce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdd3  mov     ebx, eax
0x18000cdd5  test    eax, eax
0x18000cdd7  jns     loc_18000CE8A
0x18000cddd  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18000cde4  jz      loc_18000CB43
0x18000cdea  mov     ecx, eax; int
0x18000cdec  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000cdf1  jmp     loc_18000CB43
0x18000cdf6  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18000cdfd  mov     ebx, 80004005h
0x18000ce02  jz      loc_18000CB43
0x18000ce08  mov     ecx, ebx; int
0x18000ce0a  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000ce0f  jmp     loc_18000CB43
0x18000ce14  lea     rcx, word_180037ED4; psz
0x18000ce1b  call    cs:__imp_SysAllocString
0x18000ce21  mov     [rbp+bstrString], rax
0x18000ce25  test    rax, rax
0x18000ce28  jnz     loc_18000CCD5
0x18000ce2e  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18000ce35  mov     ebx, 8007000Eh
0x18000ce3a  jz      loc_18000CB43
0x18000ce40  mov     ecx, ebx; int
0x18000ce42  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000ce47  jmp     loc_18000CB43
0x18000ce4c  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18000ce53  mov     ebx, 8007000Eh
0x18000ce58  jz      loc_18000CB43
0x18000ce5e  mov     ecx, ebx; int
0x18000ce60  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000ce65  jmp     loc_18000CB43
0x18000ce6a  jz      short loc_18000CEAE
0x18000ce6c  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18000ce73  mov     ebx, 80004005h
0x18000ce78  jz      loc_18000CB43
0x18000ce7e  mov     ecx, ebx; int
0x18000ce80  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000ce85  jmp     loc_18000CB43
0x18000ce8a  jnz     loc_18000CF36
0x18000ce90  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18000ce97  mov     ebx, 88982F41h
0x18000ce9c  jz      loc_18000CB43
0x18000cea2  mov     ecx, ebx; int
0x18000cea4  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000cea9  jmp     loc_18000CB43
0x18000ceae  mov     rcx, [rbp+pbstr]; pbstr
0x18000ceb2  call    cs:__imp_SysStringLen
0x18000ceb8  mov     r8, [rbp+pbstr]; lpString1
0x18000cebc  lea     rcx, aXmlns; "xmlns"
0x18000cec3  mov     [rsp+50h+cchCount2], 5; cchCount2
0x18000cecb  mov     r9d, eax; cchCount1
0x18000cece  mov     [rsp+50h+lpString2], rcx; lpString2
0x18000ced3  xor     edx, edx; dwCmpFlags
0x18000ced5  mov     ecx, 400h; Locale
0x18000ceda  call    cs:__imp_CompareStringW
0x18000cee0  cmp     eax, 2
0x18000cee3  jnz     loc_18000CCA2
0x18000cee9  or      dword ptr [rsi+8], 1
0x18000ceed  jmp     loc_18000CC36
0x18000cef2  mov     rcx, [rbp+var_10]; pbstr
0x18000cef6  call    cs:__imp_SysStringLen
0x18000cefc  mov     r8, [rbp+var_10]; lpString1
0x18000cf00  lea     rcx, aAbout; "about"
0x18000cf07  mov     [rsp+50h+cchCount2], 5; cchCount2
0x18000cf0f  mov     r9d, eax; cchCount1
0x18000cf12  mov     [rsp+50h+lpString2], rcx; lpString2
0x18000cf17  xor     edx, edx; dwCmpFlags
0x18000cf19  mov     ecx, 400h; Locale
0x18000cf1e  call    cs:__imp_CompareStringW
0x18000cf24  cmp     eax, 2
0x18000cf27  jnz     loc_18000CCA2
0x18000cf2d  or      dword ptr [rsi+8], 6
0x18000cf31  jmp     loc_18000CC36
0x18000cf36  mov     rax, [r14]
0x18000cf39  lea     rdx, [rbp+var_10]
0x18000cf3d  mov     rcx, r14
0x18000cf40  mov     rax, [rax+20h]
0x18000cf44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf49  mov     ebx, eax
0x18000cf4b  test    eax, eax
0x18000cf4d  jns     short loc_18000CEF2
0x18000cf4f  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18000cf56  jz      loc_18000CB43
0x18000cf5c  mov     ecx, eax; int
0x18000cf5e  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000cf63  jmp     loc_18000CB43
0x18000cf68  call    cs:__imp_SysFreeString
0x18000cf6e  mov     [rbp+pbstr], r12
0x18000cf72  jmp     loc_18000CB50
```
