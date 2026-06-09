# Appx::Packaging::XmlValidationHelper::SetSelectionNamespaces(IXMLDOMDocument2 *,XmlNamespaceAlias *,ulong)

- ea: `0x180024c74`
- end: `0x1800254ba`
- name: `?SetSelectionNamespaces@XmlValidationHelper@Packaging@Appx@@SAJPEAUIXMLDOMDocument2@@PEAUXmlNamespaceAlias@@K@Z`
- size: `2118`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *, struct XmlNamespaceAlias *, unsigned int)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800093b4`
- `0x180023d10`
- `0x18006b8a4`

## callees

- `0x1800133fc`
- `0x180024c74`
- `0x180026580`
- `0x180071f50`
- `0x1800992d0`
- `0x18009d729`
- `0x180106010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800252b5`
- `OLEAUT32!__imp_SysAllocString` at `0x1800252d1`
- `OLEAUT32!__imp_SysAllocString` at `0x1800252b5`
- `OLEAUT32!__imp_SysAllocString` at `0x1800252d1`
- `OLEAUT32!__imp_SysFreeString` at `0x180025334`
- `OLEAUT32!__imp_SysFreeString` at `0x180025343`
- `OLEAUT32!__imp_SysFreeString` at `0x18002537d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800253d6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800253e5`
- `OLEAUT32!__imp_SysFreeString` at `0x180025418`
- `OLEAUT32!__imp_SysFreeString` at `0x180025334`
- `OLEAUT32!__imp_SysFreeString` at `0x180025343`
- `OLEAUT32!__imp_SysFreeString` at `0x18002537d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800253d6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800253e5`
- `OLEAUT32!__imp_SysFreeString` at `0x180025418`

## string_xrefs

- `0x180024cf6`: `xmlns`
- `0x180024d7c`: `xmlns`
- `0x180025143`: `onecore\printscan\appxpackaging\lib\core\src\xmlvalidationhelper.cpp`
- `0x180025362`: `onecore\printscan\appxpackaging\lib\core\src\xmlvalidationhelper.cpp`
- `0x180025394`: `onecore\printscan\appxpackaging\lib\core\src\xmlvalidationhelper.cpp`
- `0x1800253bf`: `onecore\printscan\appxpackaging\lib\core\src\xmlvalidationhelper.cpp`
- `0x1800253fd`: `onecore\printscan\appxpackaging\lib\core\src\xmlvalidationhelper.cpp`
- `0x180024ef6`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x180024f06`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x180025036`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x180025046`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x180025075`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x180025095`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x1800250bf`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x1800250cf`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x1800250f9`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x180025109`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x180025126`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x1800251f6`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x180025247`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x180025267`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x180025298`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x18002543f`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x180025470`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x18002549c`: `onecore\base\appmodel\common\stringbuilder.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::XmlValidationHelper::SetSelectionNamespaces(
        struct IXMLDOMDocument2 *a1,
        struct XmlNamespaceAlias *a2,
        unsigned int a3)
{
  struct XmlNamespaceAlias *v3; // r15
  unsigned int v4; // ebx
  const OLECHAR **v5; // rax
  const OLECHAR **v6; // rsi
  unsigned int v7; // r13d
  __int64 v8; // rdx
  const unsigned __int16 *v9; // rax
  signed int v10; // ebx
  __int64 v11; // rdi
  __int64 v12; // r14
  int v13; // eax
  int v14; // eax
  _WORD *v15; // r15
  _WORD *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rdi
  __int64 v19; // r14
  __int64 v20; // rdx
  int v21; // eax
  __int64 v22; // rdi
  int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // r9
  const void *v26; // r15
  _WORD *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rdi
  __int64 v30; // r14
  int v31; // eax
  __int64 v32; // rdi
  int v33; // eax
  __int64 v34; // rdx
  __int64 v35; // r9
  __int64 v36; // rdx
  __int64 v37; // r9
  __int64 v38; // rdx
  __int64 v39; // r9
  __int64 v40; // rdx
  __int64 v42; // rdi
  int v43; // eax
  OLECHAR *v44; // rbx
  BSTR v45; // rax
  OLECHAR *v46; // rdi
  int v47; // eax
  signed int v48; // r14d
  OLECHAR *v49; // rcx
  void **v50; // [rsp+20h] [rbp-40h] BYREF
  const OLECHAR **v51; // [rsp+28h] [rbp-38h]
  const OLECHAR **v52; // [rsp+30h] [rbp-30h]
  _QWORD v53[4]; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]

  v3 = a2;
  v4 = a3;
  v5 = (const OLECHAR **)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v6 = v5;
  if ( !v5 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2DB,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\xmlvalidationhelper.cpp",
      (const char *)0x8007000ELL,
      (int)v50);
    Common::AutoPtrDeallocate<Common::StringBuffer>(0);
    return 2147942414LL;
  }
  v5[2] = 0;
  *(_OWORD *)v5 = 0;
  v51 = v5;
  v7 = 0;
  v52 = v5;
  v50 = &Common::StringBufferBuilder::`vftable';
  while ( v7 < v4 )
  {
    if ( v7 )
    {
      v42 = *(unsigned int *)v51;
      if ( (_DWORD)v42 == -1 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x107,
          (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
          (const char *)0x80070216LL,
          (int)v50);
        v10 = -2147024362;
      }
      else if ( (unsigned int)(v42 + 1) > 0x3FFFFFFF )
      {
        v10 = -2147023613;
      }
      else
      {
        v43 = ((__int64 (__fastcall *)(void ***))*v50)(&v50);
        v10 = v43;
        if ( v43 >= 0 )
        {
          v51[1][v42] = 32;
          goto LABEL_5;
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x10D,
          (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
          (const char *)(unsigned int)v43,
          (int)v50);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x79,
        (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
        (const char *)(unsigned int)v10,
        (int)v50);
      if ( v10 < 0 )
      {
        v40 = 739;
        goto LABEL_61;
      }
    }
LABEL_5:
    v8 = 0x3FFFFFFF;
    v9 = L"xmlns";
    do
    {
      if ( !*v9 )
        break;
      ++v9;
      --v8;
    }
    while ( v8 );
    v10 = v8 == 0 ? 0x80070057 : 0;
    v11 = (0x3FFFFFFF - v8) & -(__int64)(v8 != 0);
    if ( !v8 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x35,
        (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
        (const char *)(unsigned int)v10,
        (int)v50);
LABEL_101:
      v40 = 741;
      goto LABEL_61;
    }
    v12 = *(unsigned int *)v51;
    if ( (unsigned int)v12 > ~(_DWORD)v11 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x107,
        (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
        (const char *)0x80070216LL,
        (int)v50);
      v10 = -2147024362;
    }
    else if ( (unsigned int)(v11 + v12) > 0x3FFFFFFF )
    {
      v10 = -2147023613;
    }
    else
    {
      v13 = ((__int64 (__fastcall *)(void ***))*v50)(&v50);
      v10 = v13;
      if ( v13 >= 0 )
      {
        memcpy_0((void *)&v51[1][v12], L"xmlns", 2LL * (unsigned int)v11);
        v10 = 0;
        goto LABEL_13;
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x10D,
        (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
        (const char *)(unsigned int)v13,
        (int)v50);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x79,
      (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)(unsigned int)v10,
      (int)v50);
LABEL_13:
    if ( v10 < 0 )
      goto LABEL_101;
    if ( *(_DWORD *)v51 == 0x3FFFFFFF )
    {
      v10 = -2147023613;
LABEL_60:
      v40 = 742;
LABEL_61:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v40,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\xmlvalidationhelper.cpp",
        (const char *)(unsigned int)v10,
        (int)v50);
LABEL_62:
      Common::AutoPtrDeallocate<Common::StringBuffer>(v6);
      return (unsigned int)v10;
    }
    v14 = ((__int64 (__fastcall *)(void ***, _QWORD))*v50)(&v50, (unsigned int)(*(_DWORD *)v51 + 1));
    v10 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1B,
        (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
        (const char *)(unsigned int)v14,
        (int)v50);
      goto LABEL_60;
    }
    v51[1][*(_DWORD *)v51 - 1] = 58;
    v15 = (_WORD *)*((_QWORD *)v3 + 2 * v7);
    if ( !v15 )
    {
      v10 = -2147024809;
LABEL_97:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x35,
        (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
        (const char *)(unsigned int)v10,
        (int)v50);
LABEL_98:
      v40 = 743;
      goto LABEL_61;
    }
    v16 = v15;
    v17 = 0x3FFFFFFF;
    do
    {
      if ( !*v16 )
        break;
      ++v16;
      --v17;
    }
    while ( v17 );
    v10 = v17 == 0 ? 0x80070057 : 0;
    v18 = (0x3FFFFFFF - v17) & -(__int64)(v17 != 0);
    if ( !v17 )
      goto LABEL_97;
    v19 = *(unsigned int *)v51;
    if ( (unsigned int)v19 > ~(_DWORD)v18 )
    {
      v10 = -2147024362;
      v36 = 263;
      v37 = 2147942934LL;
    }
    else
    {
      v20 = (unsigned int)(v18 + v19);
      if ( (unsigned int)v20 > 0x3FFFFFFF )
      {
        v10 = -2147023613;
        goto LABEL_55;
      }
      v21 = ((__int64 (__fastcall *)(void ***, __int64, _QWORD))*v50)(&v50, v20, 0);
      v10 = v21;
      if ( v21 >= 0 )
      {
        memcpy_0((void *)&v51[1][v19], v15, 2LL * (unsigned int)v18);
        v10 = 0;
        goto LABEL_25;
      }
      v37 = (unsigned int)v21;
      v36 = 269;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v36,
      (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)v37,
      (int)v50);
LABEL_55:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x79,
      (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)(unsigned int)v10,
      (int)v50);
LABEL_25:
    if ( v10 < 0 )
      goto LABEL_98;
    v22 = *(unsigned int *)v51;
    if ( (unsigned int)v22 > 0xFFFFFFFD )
    {
      v10 = -2147024362;
      v24 = 263;
      v25 = 2147942934LL;
LABEL_31:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v24,
        (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
        (const char *)v25,
        (int)v50);
      goto LABEL_32;
    }
    if ( (unsigned int)(v22 + 2) <= 0x3FFFFFFF )
    {
      v23 = ((__int64 (__fastcall *)(void ***))*v50)(&v50);
      v10 = v23;
      if ( v23 >= 0 )
      {
        *(_DWORD *)&v51[1][v22] = 2228285;
        goto LABEL_33;
      }
      v25 = (unsigned int)v23;
      v24 = 269;
      goto LABEL_31;
    }
    v10 = -2147023613;
LABEL_32:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x79,
      (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)(unsigned int)v10,
      (int)v50);
    if ( v10 < 0 )
    {
      v40 = 744;
      goto LABEL_61;
    }
LABEL_33:
    v26 = (const void *)*((_QWORD *)a2 + 2 * v7 + 1);
    if ( !v26 )
    {
      v10 = -2147024809;
LABEL_93:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x35,
        (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
        (const char *)(unsigned int)v10,
        (int)v50);
LABEL_94:
      v40 = 745;
      goto LABEL_61;
    }
    v27 = (_WORD *)*((_QWORD *)a2 + 2 * v7 + 1);
    v28 = 0x3FFFFFFF;
    do
    {
      if ( !*v27 )
        break;
      ++v27;
      --v28;
    }
    while ( v28 );
    v10 = v28 == 0 ? 0x80070057 : 0;
    v29 = (0x3FFFFFFF - v28) & -(__int64)(v28 != 0);
    if ( !v28 )
      goto LABEL_93;
    v30 = *(unsigned int *)v51;
    if ( (unsigned int)v30 > ~(_DWORD)v29 )
    {
      v10 = -2147024362;
      v38 = 263;
      v39 = 2147942934LL;
    }
    else
    {
      if ( (unsigned int)(v29 + v30) > 0x3FFFFFFF )
      {
        v10 = -2147023613;
        goto LABEL_58;
      }
      v31 = ((__int64 (__fastcall *)(void ***))*v50)(&v50);
      v10 = v31;
      if ( v31 >= 0 )
      {
        memcpy_0((void *)&v51[1][v30], v26, 2LL * (unsigned int)v29);
        v10 = 0;
        goto LABEL_42;
      }
      v39 = (unsigned int)v31;
      v38 = 269;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v38,
      (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)v39,
      (int)v50);
LABEL_58:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x79,
      (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)(unsigned int)v10,
      (int)v50);
LABEL_42:
    if ( v10 < 0 )
      goto LABEL_94;
    v32 = *(unsigned int *)v51;
    if ( (_DWORD)v32 == -1 )
    {
      v10 = -2147024362;
      v34 = 263;
      v35 = 2147942934LL;
LABEL_48:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v34,
        (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
        (const char *)v35,
        (int)v50);
      goto LABEL_49;
    }
    if ( (unsigned int)(v32 + 1) <= 0x3FFFFFFF )
    {
      v33 = ((__int64 (__fastcall *)(void ***))*v50)(&v50);
      v10 = v33;
      if ( v33 >= 0 )
      {
        v51[1][v32] = 34;
        goto LABEL_50;
      }
      v35 = (unsigned int)v33;
      v34 = 269;
      goto LABEL_48;
    }
    v10 = -2147023613;
LABEL_49:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x79,
      (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)(unsigned int)v10,
      (int)v50);
    if ( v10 < 0 )
    {
      v40 = 746;
      goto LABEL_61;
    }
LABEL_50:
    v3 = a2;
    ++v7;
    v4 = a3;
  }
  v44 = SysAllocString(L"SelectionNamespaces");
  if ( !v44 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2EF,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\xmlvalidationhelper.cpp",
      (const char *)0x8007000ELL,
      (int)v50);
    v49 = 0;
LABEL_87:
    SysFreeString(v49);
    v10 = -2147024882;
    goto LABEL_62;
  }
  v45 = SysAllocString(v6[1]);
  v46 = v45;
  if ( !v45 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F2,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\xmlvalidationhelper.cpp",
      (const char *)0x8007000ELL,
      (int)v50);
    SysFreeString(0);
    v49 = v44;
    goto LABEL_87;
  }
  v53[0] = 8;
  v53[1] = v45;
  v53[2] = 0;
  v47 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, OLECHAR *, _QWORD *))a1->lpVtbl->setProperty)(a1, v44, v53);
  v48 = v47;
  if ( v47 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F7,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\xmlvalidationhelper.cpp",
      (const char *)(unsigned int)v47,
      (int)v50);
    SysFreeString(v46);
    SysFreeString(v44);
    v10 = v48;
    goto LABEL_62;
  }
  SysFreeString(v46);
  SysFreeString(v44);
  Common::AutoPtrDeallocate<Common::StringBuffer>(v6);
  return 0;
}

```

## disassembly

```asm
0x180024c74  mov     rax, rsp
0x180024c77  mov     [rax+20h], rbx
0x180024c7b  mov     [rax+18h], r8d
0x180024c7f  mov     [rax+10h], rdx
0x180024c83  mov     [rax+8], rcx
0x180024c87  push    rbp
0x180024c88  push    rsi
0x180024c89  push    rdi
0x180024c8a  push    r12
0x180024c8c  push    r13
0x180024c8e  push    r14
0x180024c90  push    r15
0x180024c92  mov     rbp, rsp
0x180024c95  sub     rsp, 60h
0x180024c99  mov     r15, rdx
0x180024c9c  mov     ecx, 18h; unsigned __int64
0x180024ca1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180024ca8  mov     ebx, r8d
0x180024cab  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180024cb0  xor     r12d, r12d
0x180024cb3  mov     rsi, rax
0x180024cb6  test    rax, rax
0x180024cb9  jz      loc_180025390
0x180024cbf  mov     [rax+10h], r12
0x180024cc3  xorps   xmm0, xmm0
0x180024cc6  movups  xmmword ptr [rax], xmm0
0x180024cc9  mov     [rbp+var_38], rax
0x180024ccd  mov     r13d, r12d
0x180024cd0  lea     rax, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x180024cd7  mov     [rbp+var_30], rsi
0x180024cdb  mov     [rbp+var_40], rax
0x180024cdf  cmp     r13d, ebx
0x180024ce2  jnb     loc_1800252AE
0x180024ce8  test    r13d, r13d
0x180024ceb  jnz     loc_1800251A7
0x180024cf1  mov     edx, 3FFFFFFFh
0x180024cf6  lea     rax, ?XmlNamespacePrefix@Manifest@Packaging@Appx@@3QBGB; "xmlns"
0x180024cfd  cmp     [rax], r12w
0x180024d01  jz      short loc_180024D0D
0x180024d03  add     rax, 2
0x180024d07  sub     rdx, 1
0x180024d0b  jnz     short loc_180024CFD
0x180024d0d  mov     rax, rdx
0x180024d10  mov     ecx, 3FFFFFFFh
0x180024d15  neg     rax
0x180024d18  mov     rax, rdx
0x180024d1b  sbb     ebx, ebx
0x180024d1d  sub     rcx, rdx
0x180024d20  not     ebx
0x180024d22  and     ebx, 80070057h
0x180024d28  neg     rax
0x180024d2b  sbb     rdi, rdi
0x180024d2e  and     rdi, rcx
0x180024d31  test    rdx, rdx
0x180024d34  jz      loc_180025498
0x180024d3a  mov     rax, [rbp+var_38]
0x180024d3e  mov     r14d, [rax]
0x180024d41  mov     eax, edi
0x180024d43  not     eax
0x180024d45  cmp     r14d, eax
0x180024d48  ja      loc_180025071
0x180024d4e  lea     edx, [rdi+r14]
0x180024d52  cmp     edx, 3FFFFFFFh
0x180024d58  ja      loc_180025175
0x180024d5e  mov     rax, [rbp+var_40]
0x180024d62  lea     rcx, [rbp+var_40]
0x180024d66  mov     rax, [rax]
0x180024d69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d6e  mov     ebx, eax
0x180024d70  test    eax, eax
0x180024d72  js      loc_1800251F2
0x180024d78  mov     rax, [rbp+var_38]
0x180024d7c  lea     rdx, ?XmlNamespacePrefix@Manifest@Packaging@Appx@@3QBGB; "xmlns"
0x180024d83  mov     r8d, edi
0x180024d86  add     r8, r8; Size
0x180024d89  mov     rcx, [rax+8]
0x180024d8d  lea     rcx, [rcx+r14*2]; void *
0x180024d91  call    memcpy_0
0x180024d96  mov     ebx, r12d
0x180024d99  test    ebx, ebx
0x180024d9b  js      loc_1800254B0
0x180024da1  mov     rax, [rbp+var_38]
0x180024da5  mov     edx, [rax]
0x180024da7  cmp     edx, 3FFFFFFFh
0x180024dad  jz      loc_18002548E
0x180024db3  mov     rax, [rbp+var_40]
0x180024db7  lea     rcx, [rbp+var_40]
0x180024dbb  inc     edx
0x180024dbd  mov     rax, [rax]
0x180024dc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024dc5  mov     ebx, eax
0x180024dc7  test    eax, eax
0x180024dc9  js      loc_180025122
0x180024dcf  mov     rdx, [rbp+var_38]
0x180024dd3  xor     r8d, r8d
0x180024dd6  mov     r12d, r13d
0x180024dd9  mov     ecx, [rdx]
0x180024ddb  mov     rax, [rdx+8]
0x180024ddf  dec     ecx
0x180024de1  mov     word ptr [rax+rcx*2], 3Ah ; ':'
0x180024de7  mov     eax, r13d
0x180024dea  add     rax, rax
0x180024ded  mov     r15, [r15+rax*8]
0x180024df1  test    r15, r15
0x180024df4  jz      loc_180025467
0x180024dfa  mov     r9d, 3FFFFFFFh
0x180024e00  mov     rax, r15
0x180024e03  mov     edx, r9d
0x180024e06  cmp     [rax], r8w
0x180024e0a  jz      short loc_180024E16
0x180024e0c  add     rax, 2
0x180024e10  sub     rdx, 1
0x180024e14  jnz     short loc_180024E06
0x180024e16  mov     rax, rdx
0x180024e19  mov     rcx, r9
0x180024e1c  neg     rax
0x180024e1f  mov     rax, rdx
0x180024e22  sbb     ebx, ebx
0x180024e24  sub     rcx, rdx
0x180024e27  not     ebx
0x180024e29  and     ebx, 80070057h
0x180024e2f  neg     rax
0x180024e32  sbb     rdi, rdi
0x180024e35  and     rdi, rcx
0x180024e38  test    rdx, rdx
0x180024e3b  jz      loc_18002546C
0x180024e41  mov     rax, [rbp+var_38]
0x180024e45  mov     r14d, [rax]
0x180024e48  mov     eax, edi
0x180024e4a  not     eax
0x180024e4c  cmp     r14d, eax
0x180024e4f  ja      loc_1800250AE
0x180024e55  lea     edx, [rdi+r14]
0x180024e59  cmp     edx, r9d
0x180024e5c  ja      loc_18002517F
0x180024e62  mov     rax, [rbp+var_40]
0x180024e66  lea     rcx, [rbp+var_40]
0x180024e6a  mov     rax, [rax]
0x180024e6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e72  mov     ebx, eax
0x180024e74  test    eax, eax
0x180024e76  js      loc_18002520F
0x180024e7c  mov     rax, [rbp+var_38]
0x180024e80  mov     rdx, r15; Src
0x180024e83  mov     r8d, edi
0x180024e86  add     r8, r8; Size
0x180024e89  mov     rcx, [rax+8]
0x180024e8d  lea     rcx, [rcx+r14*2]; void *
0x180024e91  call    memcpy_0
0x180024e96  xor     ebx, ebx
0x180024e98  test    ebx, ebx
0x180024e9a  js      loc_180025484
0x180024ea0  mov     rax, [rbp+var_38]
0x180024ea4  mov     edi, [rax]
0x180024ea6  cmp     edi, 0FFFFFFFDh
0x180024ea9  ja      short loc_180024EE5
0x180024eab  lea     edx, [rdi+2]
0x180024eae  cmp     edx, 3FFFFFFFh
0x180024eb4  ja      loc_180025189
0x180024eba  mov     rax, [rbp+var_40]
0x180024ebe  lea     rcx, [rbp+var_40]
0x180024ec2  mov     rax, [rax]
0x180024ec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024eca  mov     ebx, eax
0x180024ecc  test    eax, eax
0x180024ece  js      loc_18002521C
0x180024ed4  mov     rax, [rbp+var_38]
0x180024ed8  mov     rcx, [rax+8]
0x180024edc  mov     dword ptr [rcx+rdi*2], 22003Dh
0x180024ee3  jmp     short loc_180024F22
0x180024ee5  mov     ebx, 80070216h
0x180024eea  mov     edx, 107h; void *
0x180024eef  mov     r9d, ebx; char *
0x180024ef2  mov     rcx, [rbp+38h]; this
0x180024ef6  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\string"...
0x180024efd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180024f02  mov     rcx, [rbp+38h]; this
0x180024f06  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\string"...
0x180024f0d  mov     r9d, ebx; char *
0x180024f10  mov     edx, 79h ; 'y'; void *
0x180024f15  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180024f1a  test    ebx, ebx
0x180024f1c  js      loc_18002545D
0x180024f22  mov     r15, [rbp+arg_8]
0x180024f26  add     r12, r12
0x180024f29  mov     r15, [r15+r12*8+8]
0x180024f2e  xor     r12d, r12d
0x180024f31  test    r15, r15
0x180024f34  jz      loc_180025436
0x180024f3a  mov     r8d, 3FFFFFFFh
0x180024f40  mov     rax, r15
0x180024f43  mov     edx, r8d
0x180024f46  cmp     [rax], r12w
0x180024f4a  jz      short loc_180024F56
0x180024f4c  add     rax, 2
0x180024f50  sub     rdx, 1
0x180024f54  jnz     short loc_180024F46
0x180024f56  mov     rax, rdx
0x180024f59  mov     rcx, r8
0x180024f5c  neg     rax
0x180024f5f  mov     rax, rdx
0x180024f62  sbb     ebx, ebx
0x180024f64  sub     rcx, rdx
0x180024f67  not     ebx
0x180024f69  and     ebx, 80070057h
0x180024f6f  neg     rax
0x180024f72  sbb     rdi, rdi
0x180024f75  and     rdi, rcx
0x180024f78  test    rdx, rdx
0x180024f7b  jz      loc_18002543B
0x180024f81  mov     rax, [rbp+var_38]
0x180024f85  mov     r14d, [rax]
0x180024f88  mov     eax, edi
0x180024f8a  not     eax
0x180024f8c  cmp     r14d, eax
0x180024f8f  ja      loc_1800250E8
0x180024f95  lea     edx, [rdi+r14]
0x180024f99  cmp     edx, r8d
0x180024f9c  ja      loc_180025193
0x180024fa2  mov     rax, [rbp+var_40]
0x180024fa6  lea     rcx, [rbp+var_40]
0x180024faa  mov     rax, [rax]
0x180024fad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024fb2  mov     ebx, eax
0x180024fb4  test    eax, eax
0x180024fb6  js      loc_180025229
0x180024fbc  mov     rax, [rbp+var_38]
0x180024fc0  mov     rdx, r15; Src
0x180024fc3  mov     r8d, edi
0x180024fc6  add     r8, r8; Size
0x180024fc9  mov     rcx, [rax+8]
0x180024fcd  lea     rcx, [rcx+r14*2]; void *
0x180024fd1  call    memcpy_0
0x180024fd6  mov     ebx, r12d
0x180024fd9  test    ebx, ebx
0x180024fdb  js      loc_180025453
0x180024fe1  mov     rax, [rbp+var_38]
0x180024fe5  mov     edi, [rax]
0x180024fe7  cmp     edi, 0FFFFFFFEh
0x180024fea  ja      short loc_180025025
0x180024fec  lea     edx, [rdi+1]
0x180024fef  cmp     edx, 3FFFFFFFh
0x180024ff5  ja      loc_18002519D
0x180024ffb  mov     rax, [rbp+var_40]
0x180024fff  lea     rcx, [rbp+var_40]
0x180025003  mov     rax, [rax]
0x180025006  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002500b  mov     ebx, eax
0x18002500d  test    eax, eax
0x18002500f  js      loc_180025236
0x180025015  mov     rax, [rbp+var_38]
0x180025019  mov     rcx, [rax+8]
0x18002501d  mov     word ptr [rcx+rdi*2], 22h ; '"'
0x180025023  jmp     short loc_180025062
0x180025025  mov     ebx, 80070216h
0x18002502a  mov     edx, 107h; void *
0x18002502f  mov     r9d, ebx; char *
0x180025032  mov     rcx, [rbp+38h]; this
0x180025036  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\string"...
0x18002503d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180025042  mov     rcx, [rbp+38h]; this
0x180025046  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\string"...
0x18002504d  mov     r9d, ebx; char *
0x180025050  mov     edx, 79h ; 'y'; void *
0x180025055  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002505a  test    ebx, ebx
0x18002505c  js      loc_18002542C
0x180025062  mov     r15, [rbp+arg_8]
0x180025066  inc     r13d
0x180025069  mov     ebx, [rbp+arg_10]
0x18002506c  jmp     loc_180024CDF
0x180025071  mov     rcx, [rbp+38h]; this
0x180025075  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\string"...
0x18002507c  mov     r9d, 80070216h; char *
0x180025082  mov     edx, 107h; void *
0x180025087  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002508c  mov     ebx, 80070216h
0x180025091  mov     rcx, [rbp+38h]; this
0x180025095  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\string"...
0x18002509c  mov     r9d, ebx; char *
0x18002509f  mov     edx, 79h ; 'y'; void *
0x1800250a4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800250a9  jmp     loc_180024D99
0x1800250ae  mov     ebx, 80070216h
0x1800250b3  mov     edx, 107h; void *
0x1800250b8  mov     r9d, ebx; char *
0x1800250bb  mov     rcx, [rbp+38h]; this
0x1800250bf  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\string"...
0x1800250c6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800250cb  mov     rcx, [rbp+38h]; this
0x1800250cf  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\string"...
0x1800250d6  mov     r9d, ebx; char *
0x1800250d9  mov     edx, 79h ; 'y'; void *
0x1800250de  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800250e3  jmp     loc_180024E98
0x1800250e8  mov     ebx, 80070216h
0x1800250ed  mov     edx, 107h; void *
0x1800250f2  mov     r9d, ebx; char *
0x1800250f5  mov     rcx, [rbp+38h]; this
0x1800250f9  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\string"...
  ... truncated ...
```
