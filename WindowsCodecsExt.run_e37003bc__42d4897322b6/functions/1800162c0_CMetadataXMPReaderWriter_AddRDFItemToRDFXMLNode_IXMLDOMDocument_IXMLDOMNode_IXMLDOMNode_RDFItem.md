# CMetadataXMPReaderWriter::AddRDFItemToRDFXMLNode(IXMLDOMDocument *,IXMLDOMNode *,IXMLDOMNode *,RDFItem *)

- ea: `0x1800162c0`
- end: `0x180016aa0`
- name: `?AddRDFItemToRDFXMLNode@CMetadataXMPReaderWriter@@MEAAJPEAUIXMLDOMDocument@@PEAUIXMLDOMNode@@1PEAVRDFItem@@@Z`
- size: `2016`
- prototype: `__int64 __fastcall(CMetadataXMPReaderWriter *__hidden this, struct IXMLDOMDocument *, struct IXMLDOMNode *, struct IXMLDOMNode *, struct RDFItem *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004500`
- `0x18000e82c`
- `0x1800108fc`
- `0x1800153b8`
- `0x1800162c0`
- `0x1800171c4`
- `0x180023e34`
- `0x180024714`
- `0x180024798`
- `0x1800248cc`
- `0x180033010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800164f0`
- `OLEAUT32!__imp_SysAllocString` at `0x180016504`
- `OLEAUT32!__imp_SysAllocString` at `0x1800166e6`
- `OLEAUT32!__imp_SysAllocString` at `0x1800166fa`
- `OLEAUT32!__imp_SysAllocString` at `0x18001685b`
- `OLEAUT32!__imp_SysAllocString` at `0x1800164f0`
- `OLEAUT32!__imp_SysAllocString` at `0x180016504`
- `OLEAUT32!__imp_SysAllocString` at `0x1800166e6`
- `OLEAUT32!__imp_SysAllocString` at `0x1800166fa`
- `OLEAUT32!__imp_SysAllocString` at `0x18001685b`
- `OLEAUT32!__imp_SysStringLen` at `0x180016655`
- `OLEAUT32!__imp_SysStringLen` at `0x180016655`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001667c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001667c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800163b3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800163b3`

## string_xrefs

- `0x180016854`: `xmlns`

## pseudocode

```c
__int64 __fastcall CMetadataXMPReaderWriter::AddRDFItemToRDFXMLNode(
        CMetadataXMPReaderWriter *this,
        struct IXMLDOMDocument *a2,
        struct IXMLDOMNode *a3,
        struct IXMLDOMNode *a4,
        struct RDFItem *a5)
{
  struct RDFItem *v5; // r13
  XMLItem *v7; // r12
  __int64 v8; // rax
  __int64 (__fastcall *v9)(struct RDFItem *, LPCWSTR *); // rax
  int PrefixAsBSTR; // eax
  int v11; // edi
  int v12; // ecx
  __int64 v13; // rsi
  unsigned int i; // ebx
  __int64 v15; // r14
  int ValueAsBSTR; // eax
  __int64 v18; // rcx
  LPCWSTR v19; // rbx
  struct RDFItem *v20; // rax
  int v21; // ecx
  int v22; // eax
  int v23; // r14d
  int v24; // eax
  bool v25; // zf
  __int64 j; // rdi
  OLECHAR *v27; // rbx
  UINT v28; // eax
  LPCWSTR v29; // rdi
  struct RDFItem *v30; // rax
  struct RDFItem *v31; // rbx
  struct IXMLDOMDocument *v32; // r14
  WCHAR *v33; // rax
  int v34; // ecx
  int v35; // eax
  CMetadataRDFReaderWriter *v36; // rcx
  __int64 v37; // rcx
  struct IXMLDOMNode *v38; // rbx
  __int64 v39; // rcx
  struct IXMLDOMNode *v40; // rbx
  int v41; // eax
  __int64 v42; // rcx
  __int64 v43; // rbx
  LPCWSTR lpString2; // [rsp+38h] [rbp-61h] BYREF
  int v45; // [rsp+40h] [rbp-59h] BYREF
  __int64 v46; // [rsp+48h] [rbp-51h] BYREF
  struct IXMLDOMNode *v47; // [rsp+50h] [rbp-49h] BYREF
  unsigned __int16 *v48; // [rsp+58h] [rbp-41h] BYREF
  __int64 v49; // [rsp+60h] [rbp-39h] BYREF
  __int64 v50; // [rsp+68h] [rbp-31h] BYREF
  __int64 v51; // [rsp+70h] [rbp-29h] BYREF
  struct IXMLDOMNode *v52; // [rsp+78h] [rbp-21h] BYREF
  LPCWSTR lpString1; // [rsp+80h] [rbp-19h] BYREF
  XMLItem *v54; // [rsp+88h] [rbp-11h] BYREF
  __int64 v55; // [rsp+90h] [rbp-9h] BYREF
  __int128 v56; // [rsp+98h] [rbp-1h] BYREF
  __int64 v57; // [rsp+A8h] [rbp+Fh]

  v5 = a5;
  v54 = 0;
  v7 = 0;
  v47 = 0;
  v8 = *(_QWORD *)a5;
  v55 = 0;
  v49 = 0;
  v50 = 0;
  v9 = *(__int64 (__fastcall **)(struct RDFItem *, LPCWSTR *))(v8 + 56);
  v51 = 0;
  v52 = 0;
  v46 = 0;
  lpString1 = 0;
  lpString2 = 0;
  v48 = 0;
  v45 = 0;
  PrefixAsBSTR = v9(a5, &lpString1);
  v11 = PrefixAsBSTR;
  if ( PrefixAsBSTR < 0 )
    goto LABEL_2;
  v13 = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= *((_DWORD *)this + 72) )
      goto LABEL_36;
    v15 = *(_QWORD *)(*((_QWORD *)this + 33) + 8LL * i);
    ValueAsBSTR = Item::GetValueAsBSTR((Item *)v15, (unsigned __int16 **)&lpString2, 0);
    v11 = ValueAsBSTR;
    if ( ValueAsBSTR < 0 )
    {
      if ( g_doStackCaptures )
        DoStackCapture(ValueAsBSTR);
      goto LABEL_14;
    }
    if ( (*(_BYTE *)(v15 + 8) & 1) != 0 && !lstrcmpW(lpString1, lpString2) )
      break;
  }
  v18 = *(_QWORD *)(v15 + 24);
  if ( v18 )
  {
    v47 = *(struct IXMLDOMNode **)(v15 + 24);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(v18);
    goto LABEL_123;
  }
  v13 = v15;
LABEL_36:
  lpString2 = SysAllocString(L"rdf:Description");
  v19 = lpString2;
  v20 = (struct RDFItem *)SysAllocString(L"http://www.w3.org/1999/02/22-rdf-syntax-ns#");
  a5 = v20;
  if ( !v19 || !v20 )
    goto LABEL_37;
  v57 = 0;
  v56 = 0;
  WORD4(v56) = 1;
  LOWORD(v56) = 18;
  v22 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, __int128 *, LPCWSTR, struct RDFItem *, __int64 *))a2->lpVtbl->createNode)(
          a2,
          &v56,
          v19,
          v20,
          &v46);
  v23 = 0;
  v11 = v22;
  if ( v22 < 0 )
    goto LABEL_44;
  if ( v22 )
  {
    v11 = -2147467259;
    goto LABEL_38;
  }
  FreeBSTR((unsigned __int16 **)&a5);
  FreeBSTR((unsigned __int16 **)&lpString2);
  v24 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64, struct IXMLDOMNode **))a4->lpVtbl->appendChild)(
          a4,
          v46,
          &v47);
  v11 = v24;
  if ( v24 >= 0 )
  {
    if ( v24 )
    {
LABEL_52:
      v25 = g_doStackCaptures == 0;
      goto LABEL_53;
    }
    if ( v46 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
      v46 = 0;
    }
    for ( j = 0; (unsigned int)j < *((_DWORD *)this + 72); j = (unsigned int)(j + 1) )
    {
      v27 = *(OLECHAR **)(*(_QWORD *)(*((_QWORD *)this + 33) + 8 * j) + 40LL);
      v28 = SysStringLen(v27);
      if ( CompareStringW(0x400u, 0, v27, v28, L"about", 5) == 2 )
      {
        v23 = 1;
        break;
      }
    }
    PrefixAsBSTR = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64 *))v47->lpVtbl->get_attributes)(v47, &v49);
    v11 = PrefixAsBSTR;
    if ( PrefixAsBSTR < 0 )
    {
LABEL_2:
      if ( g_doStackCaptures )
      {
        v12 = PrefixAsBSTR;
        goto LABEL_4;
      }
      goto LABEL_14;
    }
    if ( PrefixAsBSTR )
    {
LABEL_65:
      v11 = -2147467259;
      if ( !g_doStackCaptures )
        goto LABEL_14;
      v12 = -2147467259;
LABEL_4:
      DoStackCapture(v12);
      goto LABEL_14;
    }
    if ( v23 )
    {
      v32 = a2;
      goto LABEL_80;
    }
    lpString2 = SysAllocString(L"rdf:about");
    v29 = lpString2;
    v30 = (struct RDFItem *)SysAllocString(L"uuid:faf5bdd5-ba3d-11da-ad31-d33d75182f1b");
    a5 = v30;
    v31 = v30;
    if ( v29 && v30 )
    {
      v32 = a2;
      v22 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, LPCWSTR, __int64 *))a2->lpVtbl->createAttribute)(
              a2,
              v29,
              &v50);
      v11 = v22;
      if ( v22 < 0 )
      {
LABEL_44:
        if ( !g_doStackCaptures )
          goto LABEL_41;
        v21 = v22;
        goto LABEL_40;
      }
      if ( v22 )
        goto LABEL_73;
      v22 = (*(__int64 (__fastcall **)(__int64, struct RDFItem *))(*(_QWORD *)v50 + 216LL))(v50, v31);
      v11 = v22;
      if ( v22 < 0 )
        goto LABEL_44;
      if ( v22 )
      {
LABEL_73:
        v11 = -2147467259;
LABEL_38:
        if ( !g_doStackCaptures )
        {
LABEL_41:
          FreeBSTR((unsigned __int16 **)&a5);
          FreeBSTR((unsigned __int16 **)&lpString2);
          goto LABEL_14;
        }
        v21 = v11;
LABEL_40:
        DoStackCapture(v21);
        goto LABEL_41;
      }
      FreeBSTR((unsigned __int16 **)&a5);
      FreeBSTR((unsigned __int16 **)&lpString2);
      v24 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v49 + 64LL))(v49, v50, &v46);
      v11 = v24;
      if ( v24 < 0 )
        goto LABEL_49;
      if ( v24 )
        goto LABEL_52;
      if ( v46 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
        v46 = 0;
      }
LABEL_80:
      if ( v13 )
      {
        v48 = *(unsigned __int16 **)(v13 + 40);
        v45 = 0;
      }
      else
      {
        PrefixAsBSTR = RDFItem::GetPrefixAsBSTR(v5, &v48);
        v11 = PrefixAsBSTR;
        if ( PrefixAsBSTR < 0 )
          goto LABEL_2;
        if ( v48 )
        {
          v45 = 1;
        }
        else
        {
          PrefixAsBSTR = (*(__int64 (__fastcall **)(CMetadataXMPReaderWriter *, LPCWSTR, unsigned __int16 **, __int64, int *))(*(_QWORD *)this + 248LL))(
                           this,
                           lpString1,
                           &v48,
                           1,
                           &v45);
          v11 = PrefixAsBSTR;
          if ( PrefixAsBSTR < 0 )
            goto LABEL_2;
          PrefixAsBSTR = RDFItem::SetPrefix(v5, v48);
          v11 = PrefixAsBSTR;
          if ( PrefixAsBSTR < 0 )
            goto LABEL_2;
        }
      }
      v33 = SysAllocString(L"xmlns");
      lpString2 = v33;
      if ( !v33 )
      {
        v11 = -2147024882;
        if ( g_doStackCaptures )
          DoStackCapture(-2147024882);
        goto LABEL_91;
      }
      CStackBSTR::CStackBSTR((CStackBSTR *)&a5, v33, v48);
      if ( !a5 )
      {
        v11 = -2147024882;
LABEL_94:
        if ( !g_doStackCaptures )
        {
LABEL_97:
          FreeBSTR((unsigned __int16 **)&a5);
LABEL_91:
          FreeBSTR((unsigned __int16 **)&lpString2);
          goto LABEL_14;
        }
        v34 = v11;
LABEL_96:
        DoStackCapture(v34);
        goto LABEL_97;
      }
      v35 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, struct RDFItem *, __int64 *))v32->lpVtbl->createAttribute)(
              v32,
              a5,
              &v51);
      v11 = v35;
      if ( v35 < 0 )
      {
LABEL_99:
        if ( !g_doStackCaptures )
          goto LABEL_97;
        v34 = v35;
        goto LABEL_96;
      }
      if ( !v35 )
      {
        v35 = (*(__int64 (__fastcall **)(__int64, LPCWSTR))(*(_QWORD *)v51 + 216LL))(v51, lpString1);
        v11 = v35;
        if ( v35 < 0 )
          goto LABEL_99;
        if ( !v35 )
        {
          FreeBSTR((unsigned __int16 **)&a5);
          FreeBSTR((unsigned __int16 **)&lpString2);
          PrefixAsBSTR = (*(__int64 (__fastcall **)(__int64, __int64, struct IXMLDOMNode **))(*(_QWORD *)v49 + 64LL))(
                           v49,
                           v51,
                           &v52);
          v11 = PrefixAsBSTR;
          if ( PrefixAsBSTR < 0 )
            goto LABEL_2;
          if ( !PrefixAsBSTR )
          {
            if ( v13 )
            {
              v37 = *(_QWORD *)(v13 + 24);
              v38 = v47;
              if ( v37 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
              *(_QWORD *)(v13 + 24) = v38;
              if ( v38 )
                ((void (__fastcall *)(struct IXMLDOMNode *))v38->lpVtbl->AddRef)(v38);
              v39 = *(_QWORD *)(v13 + 16);
              v40 = v52;
              if ( v39 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
              *(_QWORD *)(v13 + 16) = v40;
              if ( v40 )
                ((void (__fastcall *)(struct IXMLDOMNode *))v40->lpVtbl->AddRef)(v40);
            }
            else
            {
              v41 = CMetadataRDFReaderWriter::CreateXmlItem(v36, &v54);
              v11 = v41;
              if ( v41 < 0 )
              {
                if ( g_doStackCaptures )
                  DoStackCapture(v41);
                v7 = v54;
                goto LABEL_14;
              }
              v7 = v54;
              PrefixAsBSTR = XMLItem::InitializeFromRDFDescription(v54, v47, v52);
              v11 = PrefixAsBSTR;
              if ( PrefixAsBSTR < 0 )
                goto LABEL_2;
              PrefixAsBSTR = CMILObjectArray<RDFItem *>::Add((char *)this + 264, &v54);
              v11 = PrefixAsBSTR;
              if ( PrefixAsBSTR < 0 )
                goto LABEL_2;
              v7 = 0;
            }
LABEL_123:
            v11 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMNode *, __int64 *))v47->lpVtbl->appendChild)(
                    v47,
                    a3,
                    &v55);
            if ( v11 < 0 )
            {
              if ( !g_doStackCaptures )
                goto LABEL_14;
              goto LABEL_54;
            }
            if ( !v11 )
            {
              v42 = *((_QWORD *)v5 + 2);
              v43 = v55;
              if ( v42 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
              *((_QWORD *)v5 + 2) = v43;
              if ( v43 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 8LL))(v43);
              goto LABEL_14;
            }
            v25 = g_doStackCaptures == 0;
LABEL_53:
            v11 = -2147467259;
            if ( v25 )
              goto LABEL_14;
LABEL_54:
            v12 = v11;
            goto LABEL_4;
          }
          goto LABEL_65;
        }
      }
      v11 = -2147467259;
      goto LABEL_94;
    }
LABEL_37:
    v11 = -2147024882;
    goto LABEL_38;
  }
LABEL_49:
  if ( g_doStackCaptures )
  {
    v12 = v24;
    goto LABEL_4;
  }
LABEL_14:
  if ( v7 )
    (**(void (__fastcall ***)(XMLItem *, __int64))v7)(v7, 1);
  if ( v47 )
  {
    ((void (__fastcall *)(struct IXMLDOMNode *))v47->lpVtbl->Release)(v47);
    v47 = 0;
  }
  if ( v55 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
    v55 = 0;
  }
  if ( v49 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
    v49 = 0;
  }
  if ( v50 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    v50 = 0;
  }
  if ( v51 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    v51 = 0;
  }
  if ( v52 )
  {
    ((void (__fastcall *)(struct IXMLDOMNode *))v52->lpVtbl->Release)(v52);
    v52 = 0;
  }
  if ( v46 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    v46 = 0;
  }
  if ( v45 )
    FreeBSTR(&v48);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800162c0  mov     rax, rsp
0x1800162c3  mov     [rax+8], rbx
0x1800162c7  mov     [rax+20h], r9
0x1800162cb  mov     [rax+18h], r8
0x1800162cf  mov     [rax+10h], rdx
0x1800162d3  push    rbp
0x1800162d4  push    rsi
0x1800162d5  push    rdi
0x1800162d6  push    r12
0x1800162d8  push    r13
0x1800162da  push    r14
0x1800162dc  push    r15
0x1800162de  lea     rbp, [rax-57h]
0x1800162e2  sub     rsp, 0B0h
0x1800162e9  mov     r13, [rbp+4Fh+arg_20]
0x1800162ed  lea     rdx, [rbp+4Fh+lpString1]
0x1800162f1  xor     r14d, r14d
0x1800162f4  mov     r15, rcx
0x1800162f7  mov     rcx, r13
0x1800162fa  mov     [rbp+4Fh+var_60], r14
0x1800162fe  mov     r12d, r14d
0x180016301  mov     [rbp+4Fh+var_98], r14
0x180016305  mov     rax, [r13+0]
0x180016309  mov     [rbp+4Fh+var_58], r14
0x18001630d  mov     [rbp+4Fh+var_88], r14
0x180016311  mov     [rbp+4Fh+var_80], r14
0x180016315  mov     rax, [rax+38h]
0x180016319  mov     [rbp+4Fh+var_78], r14
0x18001631d  mov     [rbp+4Fh+var_70], r14
0x180016321  mov     [rbp+4Fh+var_A0], r14
0x180016325  mov     [rbp+4Fh+lpString1], r14
0x180016329  mov     [rbp+4Fh+lpString2], r14
0x18001632d  mov     [rbp+4Fh+var_90], r14
0x180016331  mov     [rbp+4Fh+var_A8], r14d
0x180016335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001633a  lea     ebx, [r14+1]
0x18001633e  mov     edi, eax
0x180016340  test    eax, eax
0x180016342  jns     short loc_18001635A
0x180016344  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x18001634b  jz      loc_1800163D4
0x180016351  mov     ecx, eax; int
0x180016353  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180016358  jmp     short loc_1800163D4
0x18001635a  mov     rsi, r14
0x18001635d  mov     ebx, r14d
0x180016360  mov     edi, 1
0x180016365  cmp     ebx, [r15+120h]
0x18001636c  jnb     loc_1800164E9
0x180016372  mov     rax, [r15+108h]
0x180016379  lea     rdx, [rbp+4Fh+lpString2]; unsigned __int16 **
0x18001637d  mov     ecx, ebx
0x18001637f  xor     r8d, r8d; int
0x180016382  mov     r14, [rax+rcx*8]
0x180016386  mov     rcx, r14; this
0x180016389  call    ?GetValueAsBSTR@Item@@QEAAJPEAPEAGH@Z; Item::GetValueAsBSTR(ushort * *,int)
0x18001638e  mov     edi, eax
0x180016390  test    eax, eax
0x180016392  jns     short loc_1800163A0
0x180016394  cmp     cs:?g_doStackCaptures@@3HA, esi; int g_doStackCaptures
0x18001639a  jnz     short loc_1800163C5
0x18001639c  test    eax, eax
0x18001639e  js      short loc_1800163CC
0x1800163a0  mov     edi, 1
0x1800163a5  test    [r14+8], dil
0x1800163a9  jz      short loc_1800163C1
0x1800163ab  mov     rdx, [rbp+4Fh+lpString2]; lpString2
0x1800163af  mov     rcx, [rbp+4Fh+lpString1]; lpString1
0x1800163b3  call    cs:__imp_lstrcmpW
0x1800163b9  test    eax, eax
0x1800163bb  jz      loc_1800164C5
0x1800163c1  add     ebx, edi
0x1800163c3  jmp     short loc_180016365
0x1800163c5  mov     ecx, eax; int
0x1800163c7  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800163cc  xor     r14d, r14d
0x1800163cf  mov     ebx, 1
0x1800163d4  test    r12, r12
0x1800163d7  jz      short loc_1800163EA
0x1800163d9  mov     rax, [r12]
0x1800163dd  mov     edx, ebx
0x1800163df  mov     rcx, r12
0x1800163e2  mov     rax, [rax]
0x1800163e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163ea  mov     rcx, [rbp+4Fh+var_98]
0x1800163ee  test    rcx, rcx
0x1800163f1  jz      short loc_180016403
0x1800163f3  mov     rax, [rcx]
0x1800163f6  mov     rax, [rax+10h]
0x1800163fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163ff  mov     [rbp+4Fh+var_98], r14
0x180016403  mov     rcx, [rbp+4Fh+var_58]
0x180016407  test    rcx, rcx
0x18001640a  jz      short loc_18001641C
0x18001640c  mov     rax, [rcx]
0x18001640f  mov     rax, [rax+10h]
0x180016413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016418  mov     [rbp+4Fh+var_58], r14
0x18001641c  mov     rcx, [rbp+4Fh+var_88]
0x180016420  test    rcx, rcx
0x180016423  jz      short loc_180016435
0x180016425  mov     rax, [rcx]
0x180016428  mov     rax, [rax+10h]
0x18001642c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016431  mov     [rbp+4Fh+var_88], r14
0x180016435  mov     rcx, [rbp+4Fh+var_80]
0x180016439  test    rcx, rcx
0x18001643c  jz      short loc_18001644E
0x18001643e  mov     rax, [rcx]
0x180016441  mov     rax, [rax+10h]
0x180016445  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001644a  mov     [rbp+4Fh+var_80], r14
0x18001644e  mov     rcx, [rbp+4Fh+var_78]
0x180016452  test    rcx, rcx
0x180016455  jz      short loc_180016467
0x180016457  mov     rax, [rcx]
0x18001645a  mov     rax, [rax+10h]
0x18001645e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016463  mov     [rbp+4Fh+var_78], r14
0x180016467  mov     rcx, [rbp+4Fh+var_70]
0x18001646b  test    rcx, rcx
0x18001646e  jz      short loc_180016480
0x180016470  mov     rax, [rcx]
0x180016473  mov     rax, [rax+10h]
0x180016477  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001647c  mov     [rbp+4Fh+var_70], r14
0x180016480  mov     rcx, [rbp+4Fh+var_A0]
0x180016484  test    rcx, rcx
0x180016487  jz      short loc_180016499
0x180016489  mov     rax, [rcx]
0x18001648c  mov     rax, [rax+10h]
0x180016490  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016495  mov     [rbp+4Fh+var_A0], r14
0x180016499  cmp     [rbp+4Fh+var_A8], r14d
0x18001649d  jz      short loc_1800164A8
0x18001649f  lea     rcx, [rbp+4Fh+var_90]; unsigned __int16 **
0x1800164a3  call    ?FreeBSTR@@YAXAEAPEAG@Z; FreeBSTR(ushort * &)
0x1800164a8  mov     rbx, [rsp+0E0h+arg_0]
0x1800164b0  mov     eax, edi
0x1800164b2  add     rsp, 0B0h
0x1800164b9  pop     r15
0x1800164bb  pop     r14
0x1800164bd  pop     r13
0x1800164bf  pop     r12
0x1800164c1  pop     rdi
0x1800164c2  pop     rsi
0x1800164c3  pop     rbp
0x1800164c4  retn
0x1800164c5  mov     rcx, [r14+18h]
0x1800164c9  test    rcx, rcx
0x1800164cc  jz      short loc_1800164E6
0x1800164ce  mov     [rbp+4Fh+var_98], rcx
0x1800164d2  mov     rax, [rcx]
0x1800164d5  mov     rax, [rax+8]
0x1800164d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800164de  xor     r14d, r14d
0x1800164e1  jmp     loc_180016A26
0x1800164e6  mov     rsi, r14
0x1800164e9  lea     rcx, aRdfDescription; "rdf:Description"
0x1800164f0  call    cs:__imp_SysAllocString
0x1800164f6  lea     rcx, aHttpWwwW3Org19; "http://www.w3.org/1999/02/22-rdf-syntax"...
0x1800164fd  mov     [rbp+4Fh+lpString2], rax
0x180016501  mov     rbx, rax
0x180016504  call    cs:__imp_SysAllocString
0x18001650a  xor     r14d, r14d
0x18001650d  mov     [rbp+4Fh+arg_20], rax
0x180016511  test    rbx, rbx
0x180016514  jnz     short loc_180016542
0x180016516  mov     edi, 8007000Eh
0x18001651b  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x180016522  jz      short loc_18001652B
0x180016524  mov     ecx, edi; int
0x180016526  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001652b  lea     rcx, [rbp+4Fh+arg_20]; unsigned __int16 **
0x18001652f  call    ?FreeBSTR@@YAXAEAPEAG@Z; FreeBSTR(ushort * &)
0x180016534  lea     rcx, [rbp+4Fh+lpString2]; unsigned __int16 **
0x180016538  call    ?FreeBSTR@@YAXAEAPEAG@Z; FreeBSTR(ushort * &)
0x18001653d  jmp     loc_1800163CF
0x180016542  test    rax, rax
0x180016545  jz      short loc_180016516
0x180016547  mov     r14, [rbp+4Fh+arg_8]
0x18001654b  xor     edx, edx
0x18001654d  xorps   xmm0, xmm0
0x180016550  mov     [rbp+4Fh+var_40], rdx
0x180016554  movups  [rbp+4Fh+var_50], xmm0
0x180016558  mov     word ptr [rbp+4Fh+var_50+8], di
0x18001655c  mov     r9, rax
0x18001655f  lea     ecx, [rdx+12h]
0x180016562  mov     r8, rbx
0x180016565  mov     word ptr [rbp+4Fh+var_50], cx
0x180016569  lea     rdx, [rbp+4Fh+var_50]
0x18001656d  mov     rcx, [r14]
0x180016570  movups  xmm0, [rbp+4Fh+var_50]
0x180016574  mov     r10, [rcx+1C0h]
0x18001657b  lea     rcx, [rbp+4Fh+var_A0]
0x18001657f  mov     [rsp+0E0h+var_C0], rcx
0x180016584  mov     rax, r10
0x180016587  mov     rcx, r14
0x18001658a  movaps  [rbp+4Fh+var_50], xmm0
0x18001658e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016593  xor     r14d, r14d
0x180016596  mov     edi, eax
0x180016598  test    eax, eax
0x18001659a  jns     short loc_1800165AC
0x18001659c  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x1800165a3  jz      short loc_18001652B
0x1800165a5  mov     ecx, eax
0x1800165a7  jmp     loc_180016526
0x1800165ac  jz      short loc_1800165B8
0x1800165ae  mov     edi, 80004005h
0x1800165b3  jmp     loc_18001651B
0x1800165b8  lea     rcx, [rbp+4Fh+arg_20]; unsigned __int16 **
0x1800165bc  call    ?FreeBSTR@@YAXAEAPEAG@Z; FreeBSTR(ushort * &)
0x1800165c1  lea     rcx, [rbp+4Fh+lpString2]; unsigned __int16 **
0x1800165c5  call    ?FreeBSTR@@YAXAEAPEAG@Z; FreeBSTR(ushort * &)
0x1800165ca  mov     rcx, [rbp+4Fh+arg_18]
0x1800165ce  lea     r8, [rbp+4Fh+var_98]
0x1800165d2  mov     rdx, [rbp+4Fh+var_A0]
0x1800165d6  mov     rax, [rcx]
0x1800165d9  mov     rax, [rax+0A8h]
0x1800165e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165e5  mov     edi, eax
0x1800165e7  test    eax, eax
0x1800165e9  jns     short loc_180016604
0x1800165eb  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x1800165f2  jz      loc_1800163CF
0x1800165f8  mov     ecx, eax; int
0x1800165fa  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800165ff  jmp     loc_1800163CF
0x180016604  jz      short loc_18001661C
0x180016606  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x18001660d  mov     edi, 80004005h
0x180016612  jz      loc_1800163CF
0x180016618  mov     ecx, edi
0x18001661a  jmp     short loc_1800165FA
0x18001661c  mov     rcx, [rbp+4Fh+var_A0]
0x180016620  test    rcx, rcx
0x180016623  jz      short loc_180016635
0x180016625  mov     rax, [rcx]
0x180016628  mov     rax, [rax+10h]
0x18001662c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016631  mov     [rbp+4Fh+var_A0], r12
0x180016635  xor     edi, edi
0x180016637  lea     ebx, [rdi+1]
0x18001663a  cmp     edi, [r15+120h]
0x180016641  jnb     short loc_180016693
0x180016643  mov     rax, [r15+108h]
0x18001664a  mov     rcx, [rax+rdi*8]
0x18001664e  mov     rbx, [rcx+28h]
0x180016652  mov     rcx, rbx; pbstr
0x180016655  call    cs:__imp_SysStringLen
0x18001665b  lea     rcx, aAbout; "about"
0x180016662  mov     dword ptr [rsp+28h], 5; cchCount2
0x18001666a  mov     [rsp+0E0h+var_C0], rcx; lpString2
0x18001666f  mov     r9d, eax; cchCount1
0x180016672  mov     ecx, 400h; Locale
0x180016677  mov     r8, rbx; lpString1
0x18001667a  xor     edx, edx; dwCmpFlags
0x18001667c  call    cs:__imp_CompareStringW
0x180016682  mov     ebx, 1
0x180016687  cmp     eax, 2
0x18001668a  jz      short loc_180016690
0x18001668c  add     edi, ebx
0x18001668e  jmp     short loc_18001663A
0x180016690  mov     r14d, ebx
0x180016693  mov     rcx, [rbp+4Fh+var_98]
0x180016697  lea     rdx, [rbp+4Fh+var_88]
0x18001669b  mov     rax, [rcx]
0x18001669e  mov     rax, [rax+88h]
0x1800166a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166aa  mov     edi, eax
0x1800166ac  test    eax, eax
0x1800166ae  jns     short loc_1800166B8
0x1800166b0  xor     r14d, r14d
0x1800166b3  jmp     loc_180016344
0x1800166b8  jz      short loc_1800166D6
0x1800166ba  xor     r14d, r14d
0x1800166bd  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x1800166c4  mov     edi, 80004005h
0x1800166c9  jz      loc_1800163D4
0x1800166cf  mov     ecx, edi
0x1800166d1  jmp     loc_180016353
0x1800166d6  test    r14d, r14d
0x1800166d9  jnz     loc_1800167E7
0x1800166df  lea     rcx, aRdfAbout; "rdf:about"
0x1800166e6  call    cs:__imp_SysAllocString
0x1800166ec  lea     rcx, aUuidFaf5bdd5Ba; "uuid:faf5bdd5-ba3d-11da-ad31-d33d75182f"...
0x1800166f3  mov     [rbp+4Fh+lpString2], rax
0x1800166f7  mov     rdi, rax
0x1800166fa  call    cs:__imp_SysAllocString
0x180016700  xor     r14d, r14d
0x180016703  mov     [rbp+4Fh+arg_20], rax
0x180016707  mov     rbx, rax
0x18001670a  test    rdi, rdi
0x18001670d  jz      loc_180016516
0x180016713  test    rax, rax
0x180016716  jz      loc_180016516
0x18001671c  mov     r14, [rbp+4Fh+arg_8]
0x180016720  lea     r8, [rbp+4Fh+var_80]
0x180016724  mov     rdx, rdi
  ... truncated ...
```
