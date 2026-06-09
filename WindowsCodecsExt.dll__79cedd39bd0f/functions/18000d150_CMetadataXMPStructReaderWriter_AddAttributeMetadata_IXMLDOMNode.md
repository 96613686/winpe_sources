# CMetadataXMPStructReaderWriter::AddAttributeMetadata(IXMLDOMNode *)

- ea: `0x18000d150`
- end: `0x18000d543`
- name: `?AddAttributeMetadata@CMetadataXMPStructReaderWriter@@MEAAJPEAUIXMLDOMNode@@@Z`
- size: `1011`
- prototype: `__int64 __fastcall(CMetadataXMPStructReaderWriter *__hidden this, struct IXMLDOMNode *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000d150`
- `0x18000e21c`
- `0x18000e82c`
- `0x1800171c4`
- `0x180033010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000d1be`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d1d1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d1be`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d1d1`
- `OLEAUT32!__imp_SysStringLen` at `0x18000d3d3`
- `OLEAUT32!__imp_SysStringLen` at `0x18000d3d3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000d3f8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000d3f8`

## pseudocode

```c
__int64 __fastcall CMetadataXMPStructReaderWriter::AddAttributeMetadata(
        CMetadataXMPStructReaderWriter *this,
        struct IXMLDOMNode *a2)
{
  struct IXMLDOMNodeVtbl *lpVtbl; // rax
  HRESULT (__stdcall *get_nodeType)(IXMLDOMNode *, DOMNodeType *); // rax
  int v6; // eax
  signed int v7; // ebx
  int v8; // ecx
  unsigned int v9; // eax
  unsigned int i; // edi
  int v11; // eax
  int v13; // ecx
  const WCHAR *v14; // rax
  __int64 v15; // rcx
  __int64 cchCount2; // r15
  int v17; // edi
  UINT v18; // eax
  BSTR bstrString; // [rsp+40h] [rbp-30h] BYREF
  __int64 v20; // [rsp+48h] [rbp-28h] BYREF
  __int64 v21; // [rsp+50h] [rbp-20h] BYREF
  void (__fastcall ***v22)(_QWORD, __int64); // [rsp+58h] [rbp-18h] BYREF
  BSTR String1[2]; // [rsp+60h] [rbp-10h] BYREF
  int v24; // [rsp+B8h] [rbp+48h] BYREF
  int v25; // [rsp+C0h] [rbp+50h] BYREF
  int v26; // [rsp+C8h] [rbp+58h] BYREF

  lpVtbl = a2->lpVtbl;
  v24 = 0;
  v25 = 0;
  v20 = 0;
  get_nodeType = lpVtbl->get_nodeType;
  v21 = 0;
  v22 = 0;
  bstrString = 0;
  String1[0] = 0;
  v26 = 0;
  v6 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, int *))get_nodeType)(a2, &v26);
  v7 = v6;
  if ( v6 < 0 )
    goto LABEL_2;
  if ( v6 )
  {
    if ( g_doStackCaptures )
      DoStackCapture(-2147467259);
    v7 = -2147467259;
  }
  else
  {
    if ( v26 == 8 )
    {
      v17 = 1;
      goto LABEL_48;
    }
    v14 = L"Description";
    v15 = 0x7FFFFFFF;
    do
    {
      if ( !*v14 )
        break;
      ++v14;
      --v15;
    }
    while ( v15 );
    v7 = v15 == 0 ? 0x80070057 : 0;
    cchCount2 = (0x7FFFFFFF - v15) & -(__int64)(v15 != 0);
    if ( v15 )
    {
      v6 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))a2->lpVtbl->get_baseName)(a2, &bstrString);
      v7 = v6;
      if ( v6 < 0 )
        goto LABEL_2;
      v17 = 0;
      if ( !v6 )
      {
        v18 = SysStringLen(bstrString);
        if ( CompareStringW(0x400u, 0, bstrString, v18, L"Description", cchCount2) == 2 )
        {
          v6 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))a2->lpVtbl->get_namespaceURI)(a2, String1);
          v7 = v6;
          if ( v6 >= 0 )
          {
            if ( !v6 )
              v17 = XMPSchemaURIsMatch(String1[0], (wchar_t *)L"http://www.w3.org/1999/02/22-rdf-syntax-ns#");
            goto LABEL_48;
          }
LABEL_2:
          if ( !g_doStackCaptures )
            goto LABEL_3;
          v13 = v6;
          goto LABEL_35;
        }
      }
LABEL_48:
      v24 = v17;
      v7 = 0;
      goto LABEL_3;
    }
    if ( g_doStackCaptures )
    {
      v13 = v15 == 0 ? 0x80070057 : 0;
LABEL_35:
      DoStackCapture(v13);
    }
  }
LABEL_3:
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( String1[0] )
    SysFreeString(String1[0]);
  if ( v7 < 0 )
    goto LABEL_8;
  if ( !v24 )
  {
    v11 = (*(__int64 (__fastcall **)(CMetadataXMPStructReaderWriter *, struct IXMLDOMNode *, const WCHAR *, int *))(*(_QWORD *)this + 256LL))(
            this,
            a2,
            L"Resource",
            &v24);
    v7 = v11;
    if ( v11 < 0 )
    {
      if ( g_doStackCaptures )
      {
LABEL_56:
        v8 = v11;
LABEL_10:
        DoStackCapture(v8);
        goto LABEL_23;
      }
      goto LABEL_23;
    }
    if ( !v24 )
      *((_DWORD *)this + 62) = 0;
  }
  if ( ((int (__fastcall *)(struct IXMLDOMNode *, __int64 *))a2->lpVtbl->get_attributes)(a2, &v20) < 0
    || (v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v20 + 88LL))(v20, &v25), v7 < 0) )
  {
LABEL_68:
    v7 = -2003292317;
LABEL_8:
    if ( !g_doStackCaptures )
      goto LABEL_23;
LABEL_9:
    v8 = v7;
    goto LABEL_10;
  }
  v9 = v25;
  if ( v25 > 0 )
  {
    for ( i = 0; i < v9; ++i )
    {
      v26 = 0;
      v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v20 + 80LL))(v20, i, &v21);
      if ( v7 < 0 )
      {
        if ( g_doStackCaptures )
          goto LABEL_9;
        goto LABEL_23;
      }
      if ( v7 )
      {
        if ( g_doStackCaptures )
          DoStackCapture(-2147467259);
        v7 = -2147467259;
        goto LABEL_23;
      }
      v11 = (*(__int64 (__fastcall **)(CMetadataXMPStructReaderWriter *, __int64, struct IXMLDOMNode *, void (__fastcall ****)(_QWORD, __int64), int *, _QWORD, _QWORD))(*(_QWORD *)this + 344LL))(
              this,
              v21,
              a2,
              &v22,
              &v26,
              0,
              0);
      v7 = v11;
      if ( v11 < 0 )
      {
        if ( g_doStackCaptures )
          goto LABEL_56;
        goto LABEL_23;
      }
      if ( v26 )
      {
        v11 = CMILObjectArray<RDFItem *>::Add((__int64 *)this + 26, &v22);
        v7 = v11;
        if ( v11 < 0 )
        {
          if ( g_doStackCaptures )
            goto LABEL_56;
          goto LABEL_23;
        }
        ++*((_DWORD *)this + 43);
        v22 = 0;
      }
      if ( v21 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        v21 = 0;
      }
      v9 = v25;
    }
    if ( v7 >= 0 )
      goto LABEL_23;
    goto LABEL_68;
  }
LABEL_23:
  if ( v22 )
    (**v22)(v22, 1);
  if ( v20 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v20 = 0;
  }
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000d150  push    rbp
0x18000d152  push    rbx
0x18000d153  push    rsi
0x18000d154  push    rdi
0x18000d155  push    r12
0x18000d157  push    r14
0x18000d159  push    r15
0x18000d15b  mov     rbp, rsp
0x18000d15e  sub     rsp, 70h
0x18000d162  mov     rax, [rdx]
0x18000d165  xor     r12d, r12d
0x18000d168  mov     rsi, rdx
0x18000d16b  mov     [rbp+arg_8], r12d
0x18000d16f  mov     r14, rcx
0x18000d172  mov     [rbp+arg_10], r12d
0x18000d176  lea     rdx, [rbp+arg_18]
0x18000d17a  mov     [rbp+var_28], r12
0x18000d17e  mov     rax, [rax+50h]
0x18000d182  mov     rcx, rsi
0x18000d185  mov     [rbp+var_20], r12
0x18000d189  mov     [rbp+var_18], r12
0x18000d18d  mov     [rbp+bstrString], r12
0x18000d191  mov     [rbp+String1], r12
0x18000d195  mov     [rbp+arg_18], r12d
0x18000d199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d19e  mov     ebx, eax
0x18000d1a0  test    eax, eax
0x18000d1a2  jns     loc_18000D354
0x18000d1a8  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18000d1af  jnz     loc_18000D348
0x18000d1b5  mov     rcx, [rbp+bstrString]; bstrString
0x18000d1b9  test    rcx, rcx
0x18000d1bc  jz      short loc_18000D1C8
0x18000d1be  call    cs:__imp_SysFreeString
0x18000d1c4  mov     [rbp+bstrString], r12
0x18000d1c8  mov     rcx, [rbp+String1]; bstrString
0x18000d1cc  test    rcx, rcx
0x18000d1cf  jz      short loc_18000D1D7
0x18000d1d1  call    cs:__imp_SysFreeString
0x18000d1d7  test    ebx, ebx
0x18000d1d9  jns     short loc_18000D1F4
0x18000d1db  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18000d1e2  jz      loc_18000D2CF
0x18000d1e8  mov     ecx, ebx; int
0x18000d1ea  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000d1ef  jmp     loc_18000D2CF
0x18000d1f4  cmp     [rbp+arg_8], r12d
0x18000d1f8  jz      loc_18000D473
0x18000d1fe  mov     rax, [rsi]
0x18000d201  lea     rdx, [rbp+var_28]
0x18000d205  mov     rcx, rsi
0x18000d208  mov     rax, [rax+88h]
0x18000d20f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d214  test    eax, eax
0x18000d216  js      loc_18000D524
0x18000d21c  mov     rcx, [rbp+var_28]
0x18000d220  lea     rdx, [rbp+arg_10]
0x18000d224  mov     rax, [rcx]
0x18000d227  mov     rax, [rax+58h]
0x18000d22b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d230  mov     ebx, eax
0x18000d232  test    eax, eax
0x18000d234  js      loc_18000D524
0x18000d23a  mov     eax, [rbp+arg_10]
0x18000d23d  test    eax, eax
0x18000d23f  jle     loc_18000D2CF
0x18000d245  mov     edi, r12d
0x18000d248  cmp     edi, eax
0x18000d24a  jnb     loc_18000D51C
0x18000d250  mov     rcx, [rbp+var_28]
0x18000d254  lea     r8, [rbp+var_20]
0x18000d258  mov     [rbp+arg_18], r12d
0x18000d25c  mov     edx, edi
0x18000d25e  mov     rax, [rcx]
0x18000d261  mov     rax, [rax+50h]
0x18000d265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d26a  mov     ebx, eax
0x18000d26c  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18000d272  test    ebx, ebx
0x18000d274  jns     short loc_18000D282
0x18000d276  test    eax, eax
0x18000d278  jnz     loc_18000D1E8
0x18000d27e  test    ebx, ebx
0x18000d280  js      short loc_18000D2CF
0x18000d282  jnz     loc_18000D4E4
0x18000d288  mov     rax, [r14]
0x18000d28b  lea     rcx, [rbp+arg_18]
0x18000d28f  mov     rdx, [rbp+var_20]
0x18000d293  lea     r9, [rbp+var_18]
0x18000d297  mov     [rsp+70h+var_40], r12
0x18000d29c  mov     r8, rsi
0x18000d29f  mov     qword ptr [rsp+70h+cchCount2], r12
0x18000d2a4  mov     rax, [rax+158h]
0x18000d2ab  mov     [rsp+70h+lpString2], rcx
0x18000d2b0  mov     rcx, r14
0x18000d2b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2b8  mov     ebx, eax
0x18000d2ba  test    eax, eax
0x18000d2bc  jns     short loc_18000D31B
0x18000d2be  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18000d2c5  jnz     loc_18000D4A6
0x18000d2cb  test    eax, eax
0x18000d2cd  jns     short loc_18000D31B
0x18000d2cf  mov     rcx, [rbp+var_18]
0x18000d2d3  test    rcx, rcx
0x18000d2d6  jnz     loc_18000D52E
0x18000d2dc  mov     rcx, [rbp+var_28]
0x18000d2e0  test    rcx, rcx
0x18000d2e3  jz      short loc_18000D2F5
0x18000d2e5  mov     rax, [rcx]
0x18000d2e8  mov     rax, [rax+10h]
0x18000d2ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2f1  mov     [rbp+var_28], r12
0x18000d2f5  mov     rcx, [rbp+var_20]
0x18000d2f9  test    rcx, rcx
0x18000d2fc  jz      short loc_18000D30A
0x18000d2fe  mov     rax, [rcx]
0x18000d301  mov     rax, [rax+10h]
0x18000d305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d30a  mov     eax, ebx
0x18000d30c  add     rsp, 70h
0x18000d310  pop     r15
0x18000d312  pop     r14
0x18000d314  pop     r12
0x18000d316  pop     rdi
0x18000d317  pop     rsi
0x18000d318  pop     rbx
0x18000d319  pop     rbp
0x18000d31a  retn
0x18000d31b  cmp     [rbp+arg_18], r12d
0x18000d31f  jnz     loc_18000D4AD
0x18000d325  mov     rcx, [rbp+var_20]
0x18000d329  test    rcx, rcx
0x18000d32c  jz      short loc_18000D33E
0x18000d32e  mov     rax, [rcx]
0x18000d331  mov     rax, [rax+10h]
0x18000d335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d33a  mov     [rbp+var_20], r12
0x18000d33e  mov     eax, [rbp+arg_10]
0x18000d341  inc     edi
0x18000d343  jmp     loc_18000D248
0x18000d348  mov     ecx, eax; int
0x18000d34a  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000d34f  jmp     loc_18000D1B5
0x18000d354  jnz     loc_18000D442
0x18000d35a  cmp     [rbp+arg_18], 8
0x18000d35e  jz      loc_18000D4FC
0x18000d364  mov     edx, 7FFFFFFFh
0x18000d369  lea     rax, aDescription; "Description"
0x18000d370  mov     ecx, edx
0x18000d372  cmp     [rax], r12w
0x18000d376  jz      short loc_18000D382
0x18000d378  add     rax, 2
0x18000d37c  sub     rcx, 1
0x18000d380  jnz     short loc_18000D372
0x18000d382  mov     rax, rcx
0x18000d385  neg     rax
0x18000d388  mov     rax, rcx
0x18000d38b  sbb     ebx, ebx
0x18000d38d  sub     rdx, rcx
0x18000d390  not     ebx
0x18000d392  and     ebx, 80070057h
0x18000d398  neg     rax
0x18000d39b  sbb     r15, r15
0x18000d39e  and     r15, rdx
0x18000d3a1  test    rcx, rcx
0x18000d3a4  jz      loc_18000D45F
0x18000d3aa  mov     rax, [rsi]
0x18000d3ad  lea     rdx, [rbp+bstrString]
0x18000d3b1  mov     rcx, rsi
0x18000d3b4  mov     rax, [rax+148h]
0x18000d3bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3c0  mov     ebx, eax
0x18000d3c2  test    eax, eax
0x18000d3c4  js      loc_18000D1A8
0x18000d3ca  mov     edi, r12d
0x18000d3cd  jnz     short loc_18000D437
0x18000d3cf  mov     rcx, [rbp+bstrString]; pbstr
0x18000d3d3  call    cs:__imp_SysStringLen
0x18000d3d9  mov     r8, [rbp+bstrString]; lpString1
0x18000d3dd  lea     rcx, aDescription; "Description"
0x18000d3e4  mov     [rsp+70h+cchCount2], r15d; cchCount2
0x18000d3e9  mov     r9d, eax; cchCount1
0x18000d3ec  mov     [rsp+70h+lpString2], rcx; lpString2
0x18000d3f1  xor     edx, edx; dwCmpFlags
0x18000d3f3  mov     ecx, 400h; Locale
0x18000d3f8  call    cs:__imp_CompareStringW
0x18000d3fe  cmp     eax, 2
0x18000d401  jnz     short loc_18000D437
0x18000d403  mov     rax, [rsi]
0x18000d406  lea     rdx, [rbp+String1]
0x18000d40a  mov     rcx, rsi
0x18000d40d  mov     rax, [rax+138h]
0x18000d414  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d419  mov     ebx, eax
0x18000d41b  test    eax, eax
0x18000d41d  js      loc_18000D1A8
0x18000d423  jnz     short loc_18000D437
0x18000d425  mov     rcx, [rbp+String1]; String1
0x18000d429  lea     rdx, aHttpWwwW3Org19; "http://www.w3.org/1999/02/22-rdf-syntax"...
0x18000d430  call    ?XMPSchemaURIsMatch@@YAHPEBG0@Z; XMPSchemaURIsMatch(ushort const *,ushort const *)
0x18000d435  mov     edi, eax
0x18000d437  mov     [rbp+arg_8], edi
0x18000d43a  mov     ebx, r12d
0x18000d43d  jmp     loc_18000D1B5
0x18000d442  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18000d449  jz      short loc_18000D455
0x18000d44b  mov     ecx, 80004005h; int
0x18000d450  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000d455  mov     ebx, 80004005h
0x18000d45a  jmp     loc_18000D1B5
0x18000d45f  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18000d466  jz      loc_18000D1B5
0x18000d46c  mov     ecx, ebx
0x18000d46e  jmp     loc_18000D34A
0x18000d473  mov     rax, [r14]
0x18000d476  lea     r9, [rbp+arg_8]
0x18000d47a  lea     r8, aResource; "Resource"
0x18000d481  mov     rdx, rsi
0x18000d484  mov     rcx, r14
0x18000d487  mov     rax, [rax+100h]
0x18000d48e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d493  mov     ebx, eax
0x18000d495  test    eax, eax
0x18000d497  jns     short loc_18000D506
0x18000d499  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18000d4a0  jz      loc_18000D2CF
0x18000d4a6  mov     ecx, eax
0x18000d4a8  jmp     loc_18000D1EA
0x18000d4ad  lea     rcx, [r14+0D0h]
0x18000d4b4  lea     rdx, [rbp+var_18]
0x18000d4b8  call    ?Add@?$CMILObjectArray@PEAVRDFItem@@@@QEAAJAEAPEAVRDFItem@@@Z; CMILObjectArray<RDFItem *>::Add(RDFItem * &)
0x18000d4bd  mov     ebx, eax
0x18000d4bf  test    eax, eax
0x18000d4c1  jns     short loc_18000D4D4
0x18000d4c3  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18000d4ca  jnz     short loc_18000D4A6
0x18000d4cc  test    eax, eax
0x18000d4ce  js      loc_18000D2CF
0x18000d4d4  inc     dword ptr [r14+0ACh]
0x18000d4db  mov     [rbp+var_18], r12
0x18000d4df  jmp     loc_18000D325
0x18000d4e4  test    eax, eax
0x18000d4e6  jz      short loc_18000D4F2
0x18000d4e8  mov     ecx, 80004005h; int
0x18000d4ed  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000d4f2  mov     ebx, 80004005h
0x18000d4f7  jmp     loc_18000D2CF
0x18000d4fc  mov     edi, 1
0x18000d501  jmp     loc_18000D437
0x18000d506  cmp     [rbp+arg_8], r12d
0x18000d50a  jnz     loc_18000D1FE
0x18000d510  mov     [r14+0F8h], r12d
0x18000d517  jmp     loc_18000D1FE
0x18000d51c  test    ebx, ebx
0x18000d51e  jns     loc_18000D2CF
0x18000d524  mov     ebx, 88982F63h
0x18000d529  jmp     loc_18000D1DB
0x18000d52e  mov     rax, [rcx]
0x18000d531  mov     edx, 1
0x18000d536  mov     rax, [rax]
0x18000d539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d53e  jmp     loc_18000D2DC
```
