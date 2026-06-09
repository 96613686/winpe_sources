# CMetadataRDFReaderWriter::ProcessAttribute(IXMLDOMNode *,IXMLDOMNode *,RDFItem * *,int *,XMLItem * *,int *)

- ea: `0x18000c7b0`
- end: `0x18000cad3`
- name: `?ProcessAttribute@CMetadataRDFReaderWriter@@MEAAJPEAUIXMLDOMNode@@0PEAPEAVRDFItem@@PEAHPEAPEAVXMLItem@@2@Z`
- size: `803`
- prototype: `int(CMetadataRDFReaderWriter *__hidden this, struct IXMLDOMNode *, struct IXMLDOMNode *, struct RDFItem **, int *, struct XMLItem **, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c6a0`

## callees

- `0x18000c7b0`
- `0x18000cae0`
- `0x1800171c4`
- `0x1800215e8`
- `0x180033010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000c86b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c86b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000c99f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000c9d3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000c99f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000c9d3`

## string_xrefs

- `0x18000c97e`: `xmlns`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::ProcessAttribute(
        CMetadataRDFReaderWriter *this,
        struct IXMLDOMNode *a2,
        struct IXMLDOMNode *a3,
        struct RDFItem **a4,
        int *a5,
        struct XMLItem **a6,
        int *a7)
{
  struct XMLItem *v10; // rbx
  struct XMLItem **v11; // r15
  int v12; // eax
  int v13; // edi
  int v14; // ecx
  int v16; // eax
  struct XMLItem *v17; // rax
  int v18; // ebp
  int v19; // eax
  struct RDFItem *v20; // rbp
  __int64 v21; // rcx
  struct RDFItem *v22; // [rsp+70h] [rbp+8h] BYREF
  BSTR bstrString; // [rsp+88h] [rbp+20h] BYREF

  v10 = 0;
  v22 = 0;
  bstrString = 0;
  if ( a4 )
    *a4 = 0;
  v11 = a6;
  if ( a6 )
    *a6 = 0;
  v12 = (*(__int64 (__fastcall **)(CMetadataRDFReaderWriter *, struct RDFItem **))(*(_QWORD *)this + 384LL))(this, &v22);
  v13 = v12;
  if ( v12 < 0 )
  {
    if ( !g_doStackCaptures )
      goto LABEL_10;
    v14 = v12;
    goto LABEL_8;
  }
  v16 = (*(__int64 (__fastcall **)(struct RDFItem *, struct IXMLDOMNode *))(*(_QWORD *)v22 + 8LL))(v22, a2);
  v13 = v16;
  if ( v16 < 0 )
  {
    if ( !g_doStackCaptures )
      goto LABEL_10;
    goto LABEL_19;
  }
  v17 = (struct XMLItem *)operator new(0x30u);
  v10 = v17;
  if ( v17 )
  {
    *((_DWORD *)v17 + 2) = 0;
    *((_QWORD *)v17 + 4) = 0;
    *((_QWORD *)v17 + 2) = 0;
    v18 = 0;
    *((_QWORD *)v17 + 3) = 0;
    *(_QWORD *)v17 = &XMLItem::`vftable';
    *((_QWORD *)v17 + 5) = 0;
    v16 = XMLItem::InitializeFromXMPItem(v17, v22, a3);
    v13 = v16;
    if ( v16 >= 0 )
    {
      v13 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))a2->lpVtbl->get_nodeName)(a2, &bstrString);
      if ( v13 < 0 )
      {
        if ( !g_doStackCaptures )
          goto LABEL_10;
LABEL_47:
        v14 = v13;
LABEL_8:
        DoStackCapture(v14);
        goto LABEL_10;
      }
      if ( v13 )
      {
        v13 = -2147467259;
        if ( !g_doStackCaptures )
          goto LABEL_10;
        goto LABEL_47;
      }
      if ( CompareStringW(0x400u, 0, bstrString, 5, L"xmlns", 5) == 2
        || CompareStringW(0x400u, 0, bstrString, 3, L"rdf", 3) == 2
        || (*((_BYTE *)v10 + 8) & 4) != 0 )
      {
        v19 = 0;
        v18 = 1;
      }
      else
      {
        v19 = 1;
      }
      goto LABEL_31;
    }
    if ( v16 == -2003292351 )
    {
      v13 = 0;
      v19 = 1;
LABEL_31:
      if ( a7 )
      {
        *a7 = v18;
        if ( v18 )
        {
          *v11 = v10;
          v10 = 0;
        }
      }
      if ( a5 )
      {
        *a5 = v19;
        if ( v19 )
        {
          if ( a4 )
          {
            v20 = v22;
            v21 = *((_QWORD *)v22 + 3);
            if ( v21 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
            *((_QWORD *)v20 + 3) = a3;
            if ( a3 )
              ((void (__fastcall *)(struct IXMLDOMNode *))a3->lpVtbl->AddRef)(a3);
            *a4 = v22;
            v22 = 0;
          }
        }
      }
      goto LABEL_10;
    }
    if ( g_doStackCaptures )
LABEL_19:
      DoStackCapture(v16);
  }
  else
  {
    v10 = 0;
    v13 = -2147024882;
    if ( g_doStackCaptures )
    {
      DoStackCapture(-2147024882);
      if ( g_doStackCaptures )
        goto LABEL_47;
    }
  }
LABEL_10:
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v22 )
    (**(void (__fastcall ***)(struct RDFItem *, __int64))v22)(v22, 1);
  if ( v10 )
    (**(void (__fastcall ***)(struct XMLItem *, __int64))v10)(v10, 1);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18000c7b0  mov     rax, rsp
0x18000c7b3  push    rbx
0x18000c7b4  push    rdi
0x18000c7b5  sub     rsp, 58h
0x18000c7b9  mov     [rax-18h], rsi
0x18000c7bd  mov     rsi, r8
0x18000c7c0  mov     [rax-20h], r12
0x18000c7c4  mov     r12, rdx
0x18000c7c7  mov     [rax-28h], r13
0x18000c7cb  xor     r13d, r13d
0x18000c7ce  mov     [rax-30h], r14
0x18000c7d2  mov     r14, r9
0x18000c7d5  mov     [rax-38h], r15
0x18000c7d9  mov     ebx, r13d
0x18000c7dc  mov     [rax+8], r13
0x18000c7e0  mov     [rax+20h], r13
0x18000c7e4  test    r9, r9
0x18000c7e7  jz      short loc_18000C7EC
0x18000c7e9  mov     [r9], r13
0x18000c7ec  mov     r15, [rsp+68h+arg_28]
0x18000c7f4  test    r15, r15
0x18000c7f7  jz      short loc_18000C7FC
0x18000c7f9  mov     [r15], r13
0x18000c7fc  mov     rax, [rcx]
0x18000c7ff  lea     rdx, [rsp+68h+arg_0]
0x18000c804  mov     [rsp+68h+arg_8], rbp
0x18000c809  mov     rax, [rax+180h]
0x18000c810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c815  mov     edi, eax
0x18000c817  test    eax, eax
0x18000c819  jns     loc_18000C8B9
0x18000c81f  cmp     cs:?g_doStackCaptures@@3HA, ebx; int g_doStackCaptures
0x18000c825  jz      short loc_18000C845
0x18000c827  mov     ecx, eax; int
0x18000c829  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000c82e  jmp     short loc_18000C845
0x18000c830  mov     ecx, edi; int
0x18000c832  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000c837  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18000c83d  test    eax, eax
0x18000c83f  jnz     loc_18000CAB1
0x18000c845  mov     rcx, [rsp+68h+bstrString]; bstrString
0x18000c84d  mov     r15, [rsp+68h+var_38]
0x18000c852  mov     r14, [rsp+68h+var_30]
0x18000c857  mov     r12, [rsp+68h+var_20]
0x18000c85c  mov     rsi, [rsp+68h+var_18]
0x18000c861  mov     rbp, [rsp+68h+arg_8]
0x18000c866  test    rcx, rcx
0x18000c869  jz      short loc_18000C879
0x18000c86b  call    cs:__imp_SysFreeString
0x18000c871  mov     [rsp+68h+bstrString], r13
0x18000c879  mov     rcx, [rsp+68h+arg_0]
0x18000c87e  mov     r13, [rsp+68h+var_28]
0x18000c883  test    rcx, rcx
0x18000c886  jz      short loc_18000C898
0x18000c888  mov     rax, [rcx]
0x18000c88b  mov     edx, 1
0x18000c890  mov     rax, [rax]
0x18000c893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c898  test    rbx, rbx
0x18000c89b  jz      short loc_18000C8B0
0x18000c89d  mov     rax, [rbx]
0x18000c8a0  mov     edx, 1
0x18000c8a5  mov     rcx, rbx
0x18000c8a8  mov     rax, [rax]
0x18000c8ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8b0  mov     eax, edi
0x18000c8b2  add     rsp, 58h
0x18000c8b6  pop     rdi
0x18000c8b7  pop     rbx
0x18000c8b8  retn
0x18000c8b9  mov     rcx, [rsp+68h+arg_0]
0x18000c8be  mov     rdx, r12
0x18000c8c1  mov     rax, [rcx]
0x18000c8c4  mov     rax, [rax+8]
0x18000c8c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8cd  mov     edi, eax
0x18000c8cf  test    eax, eax
0x18000c8d1  jns     short loc_18000C8EB
0x18000c8d3  cmp     cs:?g_doStackCaptures@@3HA, ebx; int g_doStackCaptures
0x18000c8d9  jz      loc_18000C845
0x18000c8df  mov     ecx, eax; int
0x18000c8e1  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000c8e6  jmp     loc_18000C845
0x18000c8eb  mov     ecx, 30h ; '0'; Size
0x18000c8f0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c8f5  mov     rbx, rax
0x18000c8f8  test    rax, rax
0x18000c8fb  jz      loc_18000CAB8
0x18000c901  mov     [rax+8], r13d
0x18000c905  mov     r8, rsi; struct IXMLDOMNode *
0x18000c908  mov     [rax+20h], r13
0x18000c90c  mov     rcx, rbx; this
0x18000c90f  mov     [rax+10h], r13
0x18000c913  mov     ebp, r13d
0x18000c916  mov     [rax+18h], r13
0x18000c91a  lea     rax, ??_7XMLItem@@6B@; const XMLItem::`vftable'
0x18000c921  mov     [rbx], rax
0x18000c924  mov     [rbx+28h], r13
0x18000c928  mov     rdx, [rsp+68h+arg_0]; struct RDFItem *
0x18000c92d  call    ?InitializeFromXMPItem@XMLItem@@QEAAJPEAVRDFItem@@PEAUIXMLDOMNode@@@Z; XMLItem::InitializeFromXMPItem(RDFItem *,IXMLDOMNode *)
0x18000c932  mov     edi, eax
0x18000c934  test    eax, eax
0x18000c936  js      loc_18000CA6A
0x18000c93c  mov     rax, [r12]
0x18000c940  lea     rdx, [rsp+68h+bstrString]
0x18000c948  mov     rcx, r12
0x18000c94b  mov     rax, [rax+38h]
0x18000c94f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c954  mov     edi, eax
0x18000c956  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18000c95c  test    edi, edi
0x18000c95e  jns     short loc_18000C970
0x18000c960  test    eax, eax
0x18000c962  jnz     loc_18000CAB1
0x18000c968  test    edi, edi
0x18000c96a  js      loc_18000C845
0x18000c970  jnz     loc_18000CAA4
0x18000c976  mov     r8, [rsp+68h+bstrString]; lpString1
0x18000c97e  lea     rax, aXmlns; "xmlns"
0x18000c985  mov     [rsp+68h+cchCount2], 5; cchCount2
0x18000c98d  mov     r9d, 5; cchCount1
0x18000c993  xor     edx, edx; dwCmpFlags
0x18000c995  mov     [rsp+68h+lpString2], rax; lpString2
0x18000c99a  mov     ecx, 400h; Locale
0x18000c99f  call    cs:__imp_CompareStringW
0x18000c9a5  cmp     eax, 2
0x18000c9a8  jz      short loc_18000C9EB
0x18000c9aa  mov     r8, [rsp+68h+bstrString]; lpString1
0x18000c9b2  lea     rax, aRdf_0; "rdf"
0x18000c9b9  mov     [rsp+68h+cchCount2], 3; cchCount2
0x18000c9c1  mov     r9d, 3; cchCount1
0x18000c9c7  xor     edx, edx; dwCmpFlags
0x18000c9c9  mov     [rsp+68h+lpString2], rax; lpString2
0x18000c9ce  mov     ecx, 400h; Locale
0x18000c9d3  call    cs:__imp_CompareStringW
0x18000c9d9  cmp     eax, 2
0x18000c9dc  jz      short loc_18000C9EB
0x18000c9de  test    byte ptr [rbx+8], 4
0x18000c9e2  jnz     short loc_18000C9EB
0x18000c9e4  mov     eax, 1
0x18000c9e9  jmp     short loc_18000C9F3
0x18000c9eb  mov     eax, r13d
0x18000c9ee  mov     ebp, 1
0x18000c9f3  mov     rcx, [rsp+68h+arg_30]
0x18000c9fb  test    rcx, rcx
0x18000c9fe  jz      short loc_18000CA06
0x18000ca00  mov     [rcx], ebp
0x18000ca02  test    ebp, ebp
0x18000ca04  jnz     short loc_18000CA62
0x18000ca06  mov     rcx, [rsp+68h+arg_20]
0x18000ca0e  test    rcx, rcx
0x18000ca11  jz      loc_18000C845
0x18000ca17  mov     [rcx], eax
0x18000ca19  test    eax, eax
0x18000ca1b  jz      loc_18000C845
0x18000ca21  test    r14, r14
0x18000ca24  jz      loc_18000C845
0x18000ca2a  mov     rbp, [rsp+68h+arg_0]
0x18000ca2f  mov     rcx, [rbp+18h]
0x18000ca33  test    rcx, rcx
0x18000ca36  jnz     short loc_18000CA89
0x18000ca38  mov     [rbp+18h], rsi
0x18000ca3c  test    rsi, rsi
0x18000ca3f  jz      short loc_18000CA50
0x18000ca41  mov     rax, [rsi]
0x18000ca44  mov     rcx, rsi
0x18000ca47  mov     rax, [rax+8]
0x18000ca4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca50  mov     rax, [rsp+68h+arg_0]
0x18000ca55  mov     [r14], rax
0x18000ca58  mov     [rsp+68h+arg_0], r13
0x18000ca5d  jmp     loc_18000C845
0x18000ca62  mov     [r15], rbx
0x18000ca65  mov     rbx, r13
0x18000ca68  jmp     short loc_18000CA06
0x18000ca6a  cmp     eax, 88982F41h
0x18000ca6f  jz      short loc_18000CA97
0x18000ca71  cmp     cs:?g_doStackCaptures@@3HA, ebp; int g_doStackCaptures
0x18000ca77  jz      loc_18000C845
0x18000ca7d  mov     ecx, eax; int
0x18000ca7f  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000ca84  jmp     loc_18000C845
0x18000ca89  mov     rax, [rcx]
0x18000ca8c  mov     rax, [rax+10h]
0x18000ca90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca95  jmp     short loc_18000CA38
0x18000ca97  mov     edi, r13d
0x18000ca9a  mov     eax, 1
0x18000ca9f  jmp     loc_18000C9F3
0x18000caa4  mov     edi, 80004005h
0x18000caa9  test    eax, eax
0x18000caab  jz      loc_18000C845
0x18000cab1  mov     ecx, edi
0x18000cab3  jmp     loc_18000C829
0x18000cab8  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18000cabe  mov     rbx, r13
0x18000cac1  mov     edi, 8007000Eh
0x18000cac6  test    eax, eax
0x18000cac8  jz      loc_18000C845
0x18000cace  jmp     loc_18000C830
```
