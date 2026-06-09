# OSIntegration::Tools::ConvertAttributesIntoStringBufferArrayForQuery(IXMLDOMElement *,ushort const *,ushort const *,Common::Array<Common::StringBuffer,Common::ContainerOperations<Common::StringBuffer,Common::StringBuffer>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::StringBuffer>,Common::ArrayOperations<Common::StringBuffer,Common::NoKey>> &,OSIntegration::Tools::ItemVerifier *,bool)

- ea: `0x18000ff80`
- end: `0x180010882`
- name: `?ConvertAttributesIntoStringBufferArrayForQuery@Tools@OSIntegration@@YAJPEAUIXMLDOMElement@@PEBG1AEAV?$Array@VStringBuffer@Common@@V?$ContainerOperations@VStringBuffer@Common@@V12@@2@VNoKey@2@V?$ContainerOperations@VNoKey@Common@@VStringBuffer@2@@2@V?$ArrayOperations@VStringBuffer@Common@@VNoKey@2@@2@@Common@@PEAVItemVerifier@12@_N@Z`
- size: `2306`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800df120`
- `0x1800e0950`

## callees

- `0x180006970`
- `0x18000ff80`
- `0x180010fdc`
- `0x180012fc8`
- `0x180017ba0`
- `0x18001adb4`
- `0x1800af1bc`
- `0x1800af1fc`
- `0x1800af220`
- `0x1800ba475`
- `0x1801ac010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x180010053`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001032b`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180010053`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001032b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fff7`
- `OLEAUT32!__imp_SysFreeString` at `0x18001010b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800102e8`
- `OLEAUT32!__imp_SysFreeString` at `0x18001039f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fff7`
- `OLEAUT32!__imp_SysFreeString` at `0x18001010b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800102e8`
- `OLEAUT32!__imp_SysFreeString` at `0x18001039f`
- `OLEAUT32!__imp_VariantClear` at `0x1800103b0`
- `OLEAUT32!__imp_VariantClear` at `0x1800103b0`

## string_xrefs

- `0x18000ffc4`: `onecore\admin\appmodel\osim\src\deh\appx\common\xmltools.cpp`
- `0x180010189`: `onecore\admin\appmodel\osim\src\deh\appx\common\xmltools.cpp`
- `0x1800101c7`: `onecore\admin\appmodel\osim\src\deh\appx\common\xmltools.cpp`
- `0x18001045b`: `onecore\admin\appmodel\osim\src\deh\appx\common\xmltools.cpp`
- `0x1800104f1`: `onecore\admin\appmodel\osim\src\deh\appx\common\xmltools.cpp`
- `0x18001060c`: `onecore\admin\appmodel\osim\src\deh\appx\common\xmltools.cpp`
- `0x180010771`: `onecore\admin\appmodel\osim\src\deh\appx\common\xmltools.cpp`
- `0x180010845`: `onecore\admin\appmodel\osim\src\deh\appx\common\xmltools.cpp`
- `0x18001059e`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x1800105ef`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x1800106f3`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x18001070c`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x180010736`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x1800107e6`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x180010806`: `onecore\base\appmodel\common\widestring.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 OSIntegration::Tools::ConvertAttributesIntoStringBufferArrayForQuery(
        __int64 a1,
        const OLECHAR *a2,
        OLECHAR *a3,
        __int64 a4,
        ...)
{
  __int64 v7; // rcx
  OLECHAR *v8; // rbx
  __int64 v9; // rcx
  const OLECHAR *v10; // rax
  int v11; // edi
  unsigned int v12; // r14d
  int v13; // eax
  int v14; // eax
  __int64 v15; // rax
  __int64 v16; // rcx
  int v17; // eax
  unsigned __int64 v18; // rcx
  unsigned __int64 v19; // rbx
  void *v20; // rax
  void *v21; // rdi
  __int64 v23; // rcx
  __int64 v24; // rcx
  const struct std::nothrow_t *v25; // rdx
  int v26; // r15d
  int i; // r12d
  int v28; // eax
  unsigned int v29; // ebx
  unsigned int *v30; // r14
  __int64 v31; // rsi
  OLECHAR *v32; // rbx
  OLECHAR *v33; // rdi
  __int64 v34; // rcx
  OLECHAR *v35; // rax
  int v36; // edi
  int v37; // eax
  __int64 v38; // rax
  bool v39; // zf
  __int64 v40; // rax
  _BYTE *v41; // rcx
  const struct std::nothrow_t *v42; // rdx
  __int64 v43; // r15
  unsigned __int64 v44; // rcx
  unsigned __int64 v45; // rax
  unsigned __int64 v46; // rbx
  void *v47; // rax
  void *v48; // rdi
  unsigned int v49; // ebx
  const struct std::nothrow_t *v50; // rdx
  void *v51; // rcx
  __int64 v52; // rcx
  OLECHAR *v53; // rcx
  __int64 v54; // rcx
  const struct std::nothrow_t *v55; // rdx
  void *v56; // rcx
  __int64 v57; // rcx
  OLECHAR *v58; // rcx
  __int64 v59; // rcx
  BSTR bstrVal; // rax
  unsigned int v61; // r8d
  OLECHAR *v62; // rcx
  __int64 v63; // rcx
  const struct std::nothrow_t *v64; // rdx
  __int64 v65; // rcx
  OLECHAR *v66; // rcx
  __int64 v67; // rcx
  OLECHAR *v68; // rcx
  __int64 v69; // rcx
  OLECHAR *v70; // [rsp+20h] [rbp-40h] BYREF
  __int64 v71; // [rsp+28h] [rbp-38h] BYREF
  OLECHAR *v72; // [rsp+30h] [rbp-30h]
  unsigned int *v73; // [rsp+38h] [rbp-28h]
  VARIANTARG pvarg; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  int v76; // [rsp+A0h] [rbp+40h] BYREF
  OLECHAR *strIn; // [rsp+B0h] [rbp+50h]
  __int64 v78; // [rsp+B8h] [rbp+58h]
  __int64 v79; // [rsp+C0h] [rbp+60h] BYREF
  va_list va; // [rsp+C0h] [rbp+60h]
  __int64 v81; // [rsp+C8h] [rbp+68h]
  va_list va1; // [rsp+D0h] [rbp+70h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  va_arg(va1, _QWORD);
  v81 = va_arg(va1, _QWORD);
  v78 = a4;
  strIn = a3;
  v76 = 0;
  v79 = 0;
  if ( !a1 || !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAE,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\xmltools.cpp",
      (const char *)0x80070057LL,
      (int)v70);
    v7 = v79;
    if ( v79 )
    {
      v79 = 0;
LABEL_88:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    return 2147942487LL;
  }
  v71 = 0;
  SysFreeString(0);
  v8 = 0;
  v70 = 0;
  v9 = 0x7FFFFFFF;
  v10 = a2;
  while ( *v10 )
  {
    ++v10;
    if ( !--v9 )
    {
      v11 = -2147024809;
      v12 = -2147024882;
      goto LABEL_12;
    }
  }
  v12 = -2147024882;
  if ( (unsigned int)(0x7FFFFFFF - v9) > 0x3FFFFFFF )
  {
    v11 = -2147024809;
  }
  else
  {
    v8 = SysAllocStringLen(a2, 0x7FFFFFFF - (int)v9);
    v70 = v8;
    v11 = 0;
    if ( !v8 )
      v11 = -2147024882;
  }
LABEL_12:
  if ( v11 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x27,
      (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
      (const char *)(unsigned int)v11,
      (int)v70);
  }
  else
  {
    v13 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, __int64 *))(*(_QWORD *)a1 + 288LL))(a1, v8, &v71);
    v11 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2B,
        (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
        (const char *)(unsigned int)v13,
        (int)v70);
    }
    else
    {
      v14 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v71 + 64LL))(v71, &v76);
      v11 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2D,
          (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
          (const char *)(unsigned int)v14,
          (int)v70);
      }
      else
      {
        v15 = v71;
        v71 = 0;
        v79 = v15;
      }
    }
  }
  v16 = v71;
  if ( v71 )
  {
    v71 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  SysFreeString(v8);
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB0,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\xmltools.cpp",
      (const char *)(unsigned int)v11,
      (int)v70);
    v23 = v79;
    if ( v79 )
    {
      v79 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    return (unsigned int)v11;
  }
  else
  {
    v17 = v76;
    if ( v76 <= 0 )
    {
LABEL_33:
      v24 = v79;
      if ( v79 )
      {
        v79 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      }
      return 0;
    }
    else
    {
      v18 = *(_QWORD *)(a4 + 8);
      if ( v76 > v18 )
      {
        if ( v18 == 0x3FFFFFFF )
        {
          v12 = -2147483637;
LABEL_29:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xB4,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\xmltools.cpp",
            (const char *)v12,
            (int)v70);
          Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease((__int64 *)va);
          return v12;
        }
        if ( v18 )
          v19 = ((3 * v18) >> 1) + 1;
        else
          v19 = 16;
        if ( v76 > v19 )
          v19 = v76;
        if ( v19 > 0x3FFFFFFF )
          v19 = 0x3FFFFFFF;
        v20 = operator new[](8 * v19, (const struct std::nothrow_t *)&std::nothrow);
        v21 = v20;
        if ( !v20 )
          goto LABEL_29;
        if ( *(_QWORD *)a4 )
        {
          memmove_0(v20, *(const void **)a4, 8LL * *(_QWORD *)(a4 + 16));
          operator delete(*(void **)a4, v25);
        }
        *(_QWORD *)a4 = v21;
        *(_QWORD *)(a4 + 8) = v19;
        v17 = v76;
      }
      v26 = 0;
      for ( i = 0; ; ++i )
      {
        if ( i >= v17 )
          goto LABEL_33;
        v70 = 0;
        v28 = (*(__int64 (__fastcall **)(__int64, _QWORD, OLECHAR **))(*(_QWORD *)v79 + 56LL))(
                v79,
                (unsigned int)i,
                &v70);
        v29 = v28;
        if ( v28 < 0 )
          break;
        v71 = 0;
        (**(void (__fastcall ***)(OLECHAR *, GUID *, __int64 *))v70)(
          v70,
          &GUID_2933bf86_7b36_11d2_b20e_00c04f983e60,
          &v71);
        v30 = (unsigned int *)operator new(0x18u);
        *((_QWORD *)v30 + 2) = 0;
        *(_OWORD *)v30 = 0;
        v73 = v30;
        v31 = v71;
        memset(&pvarg, 0, sizeof(pvarg));
        pvarg.vt = 0;
        v32 = 0;
        if ( v71 && (v33 = strIn) != 0 )
        {
          SysFreeString(0);
          v32 = 0;
          v72 = 0;
          v34 = 0x7FFFFFFF;
          v35 = v33;
          while ( *v35 )
          {
            ++v35;
            if ( !--v34 )
            {
              v36 = -2147024809;
              goto LABEL_52;
            }
          }
          if ( (unsigned int)(0x7FFFFFFF - v34) > 0x3FFFFFFF )
          {
            v36 = -2147024809;
          }
          else
          {
            v32 = SysAllocStringLen(v33, 0x7FFFFFFF - (int)v34);
            v72 = v32;
            if ( v32 )
              v36 = 0;
            else
              v36 = -2147024882;
          }
LABEL_52:
          if ( v36 < 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x134,
              (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
              (const char *)(unsigned int)v36,
              (int)v70);
          }
          else
          {
            v37 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, VARIANTARG *))(*(_QWORD *)v31 + 352LL))(
                    v31,
                    v32,
                    &pvarg);
            v36 = v37;
            if ( v37 < 0 )
            {
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x135,
                (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
                (const char *)(unsigned int)v37,
                (int)v70);
            }
            else if ( pvarg.llVal )
            {
              v59 = 1073741822;
              bstrVal = pvarg.bstrVal;
              while ( *bstrVal )
              {
                ++bstrVal;
                if ( !--v59 )
                {
                  v61 = 0;
                  v36 = -2147024809;
                  goto LABEL_96;
                }
              }
              v36 = 0;
              v61 = 1073741822 - v59;
LABEL_96:
              if ( v36 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x249,
                  (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
                  (const char *)(unsigned int)v36,
                  (int)v70);
              else
                v36 = Common::StringBuffer::SetValue((Common::StringBuffer *)v30, pvarg.bstrVal, v61);
              if ( v36 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x13D,
                  (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
                  (const char *)(unsigned int)v36,
                  (int)v70);
              else
                v26 = 1;
            }
            else
            {
              v38 = *v30;
              v39 = 2 * v38 == 0;
              v40 = 2 * v38;
              v41 = (_BYTE *)*((_QWORD *)v30 + 1);
              if ( !v39 )
              {
                do
                {
                  *v41++ = 0;
                  --v40;
                }
                while ( v40 );
              }
            }
          }
        }
        else
        {
          v36 = -2147024809;
        }
        SysFreeString(v32);
        VariantClear(&pvarg);
        if ( v36 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xCA,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\xmltools.cpp",
            (const char *)(unsigned int)v36,
            (int)v70);
          Common::AutoPtrDeallocate<Common::StringBuffer>(v30);
          v67 = v71;
          if ( v71 )
          {
            v71 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
          }
          v68 = v70;
          if ( v70 )
          {
            v70 = 0;
            (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)v68 + 16LL))(v68);
          }
          v69 = v79;
          if ( v79 )
          {
            v79 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
          }
          return (unsigned int)v36;
        }
        if ( (_BYTE)v81 )
        {
          if ( !v26 || !*v30 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xCE,
              (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\xmltools.cpp",
              (const char *)0x80070057LL,
              (int)v70);
            v56 = (void *)*((_QWORD *)v30 + 1);
            if ( v56 )
              operator delete(v56, v55);
            operator delete(v30, (const struct std::nothrow_t *)0x18);
            v57 = v71;
            if ( v71 )
            {
              v71 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
            }
            v58 = v70;
            if ( v70 )
            {
              v70 = 0;
              (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)v58 + 16LL))(v58);
            }
            v7 = v79;
            if ( v79 )
            {
              v79 = 0;
              goto LABEL_88;
            }
            return 2147942487LL;
          }
        }
        else if ( v26 )
        {
          if ( !*v30 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xD2,
              (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\xmltools.cpp",
              (const char *)0x80070057LL,
              (int)v70);
            Common::AutoPtrDeallocate<Common::StringBuffer>(v30);
            Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v71);
            Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v70);
            Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease((__int64 *)va);
            return 2147942487LL;
          }
        }
        else
        {
          operator delete(*((void **)v30 + 1), v42);
          *((_QWORD *)v30 + 1) = 0;
          *v30 = 0;
          v30[4] = 0;
        }
        v43 = v78;
        v44 = *(_QWORD *)(v78 + 16) + 1LL;
        v45 = *(_QWORD *)(v78 + 8);
        if ( v44 > v45 )
        {
          if ( v45 == 0x3FFFFFFF )
          {
            v49 = -2147483637;
            goto LABEL_70;
          }
          if ( v45 )
            v46 = ((3 * v45) >> 1) + 1;
          else
            v46 = 16;
          if ( v44 > v46 )
            v46 = *(_QWORD *)(v78 + 16) + 1LL;
          if ( v46 > 0x3FFFFFFF )
            v46 = 0x3FFFFFFF;
          v47 = operator new[](8 * v46, (const struct std::nothrow_t *)&std::nothrow);
          v48 = v47;
          if ( !v47 )
          {
            v49 = -2147024882;
LABEL_70:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xE1,
              (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\xmltools.cpp",
              (const char *)v49,
              (int)v70);
            v51 = (void *)*((_QWORD *)v30 + 1);
            if ( v51 )
              operator delete(v51, v50);
            operator delete(v30, (const struct std::nothrow_t *)0x18);
            v52 = v71;
            if ( v71 )
            {
              v71 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
            }
            v53 = v70;
            if ( v70 )
            {
              v70 = 0;
              (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)v53 + 16LL))(v53);
            }
            v54 = v79;
            if ( v79 )
            {
              v79 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
            }
            return v49;
          }
          if ( *(_QWORD *)v43 )
          {
            memmove_0(v47, *(const void **)v43, 8LL * *(_QWORD *)(v43 + 16));
            operator delete(*(void **)v43, v64);
          }
          *(_QWORD *)v43 = v48;
          *(_QWORD *)(v43 + 8) = v46;
        }
        *(_QWORD *)(*(_QWORD *)v43 + 8LL * (*(_QWORD *)(v43 + 16))++) = v30;
        v65 = v71;
        v26 = 0;
        if ( v71 )
        {
          v71 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
        }
        v66 = v70;
        if ( v70 )
        {
          v70 = 0;
          (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)v66 + 16LL))(v66);
        }
        v17 = v76;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB9,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\xmltools.cpp",
        (const char *)(unsigned int)v28,
        (int)v70);
      v62 = v70;
      if ( v70 )
      {
        v70 = 0;
        (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)v62 + 16LL))(v62);
      }
      v63 = v79;
      if ( v79 )
      {
        v79 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
      }
      return v29;
    }
  }
}

```

## disassembly

```asm
0x18000ff80  mov     [rsp-38h+arg_8], rbx
0x18000ff85  mov     [rsp-38h+arg_18], r9
0x18000ff8a  mov     [rsp-38h+strIn], r8
0x18000ff8f  push    rbp
0x18000ff90  push    rsi
0x18000ff91  push    rdi
0x18000ff92  push    r12
0x18000ff94  push    r13
0x18000ff96  push    r14
0x18000ff98  push    r15
0x18000ff9a  mov     rbp, rsp
0x18000ff9d  sub     rsp, 60h
0x18000ffa1  mov     r15, r9
0x18000ffa4  mov     rdi, rdx
0x18000ffa7  mov     rsi, rcx
0x18000ffaa  xor     r12d, r12d
0x18000ffad  mov     [rbp+arg_0], r12d
0x18000ffb1  mov     [rbp+arg_20], r12
0x18000ffb5  test    rcx, rcx
0x18000ffb8  jnz     short loc_18000FFEC
0x18000ffba  mov     rcx, [rbp+38h]; this
0x18000ffbe  mov     r9d, 80070057h; char *
0x18000ffc4  lea     r8, aOnecoreAdminAp_17; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18000ffcb  mov     edx, 0AEh; void *
0x18000ffd0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ffd5  nop
0x18000ffd6  mov     rcx, [rbp+arg_20]
0x18000ffda  test    rcx, rcx
0x18000ffdd  jz      loc_18001056F
0x18000ffe3  mov     [rbp+arg_20], r12
0x18000ffe7  jmp     loc_180010562
0x18000ffec  test    rdi, rdi
0x18000ffef  jz      short loc_18000FFBA
0x18000fff1  mov     [rbp+var_38], r12
0x18000fff5  xor     ecx, ecx; bstrString
0x18000fff7  call    cs:__imp_SysFreeString
0x18000fffe  nop     dword ptr [rax+rax+00h]
0x180010003  mov     rbx, r12
0x180010006  mov     [rbp+var_40], rbx
0x18001000a  mov     ecx, 7FFFFFFFh
0x18001000f  mov     rax, rdi
0x180010012  cmp     [rax], bx
0x180010015  jz      short loc_180010034
0x180010017  add     rax, 2
0x18001001b  sub     rcx, 1
0x18001001f  jnz     short loc_180010012
0x180010021  mov     edi, 80070057h
0x180010026  mov     r13d, 3FFFFFFFh
0x18001002c  mov     r14d, 8007000Eh
0x180010032  jmp     short loc_180010070
0x180010034  mov     edx, 7FFFFFFFh
0x180010039  sub     edx, ecx; ui
0x18001003b  mov     r14d, 8007000Eh
0x180010041  mov     r13d, 3FFFFFFFh
0x180010047  cmp     edx, r13d
0x18001004a  ja      loc_180010756
0x180010050  mov     rcx, rdi; strIn
0x180010053  call    cs:__imp_SysAllocStringLen
0x18001005a  nop     dword ptr [rax+rax+00h]
0x18001005f  mov     rbx, rax
0x180010062  mov     [rbp+var_40], rax
0x180010066  mov     edi, r12d
0x180010069  test    rax, rax
0x18001006c  cmovz   edi, r14d
0x180010070  mov     rcx, [rbp+38h]; this
0x180010074  test    edi, edi
0x180010076  js      loc_1800107E3
0x18001007c  mov     rax, [rsi]
0x18001007f  mov     rdi, [rax+120h]
0x180010086  mov     rcx, [rbp+var_38]
0x18001008a  test    rcx, rcx
0x18001008d  jz      short loc_1800100A0
0x18001008f  mov     [rbp+var_38], r12
0x180010093  mov     rax, [rcx]
0x180010096  mov     rax, [rax+10h]
0x18001009a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001009f  nop
0x1800100a0  lea     r8, [rbp+var_38]
0x1800100a4  mov     rdx, rbx
0x1800100a7  mov     rcx, rsi
0x1800100aa  mov     rax, rdi
0x1800100ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100b2  mov     edi, eax
0x1800100b4  mov     rcx, [rbp+38h]; this
0x1800100b8  test    eax, eax
0x1800100ba  js      loc_1800106F0
0x1800100c0  mov     rcx, [rbp+var_38]
0x1800100c4  mov     rax, [rcx]
0x1800100c7  lea     rdx, [rbp+arg_0]
0x1800100cb  mov     rax, [rax+40h]
0x1800100cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100d4  mov     edi, eax
0x1800100d6  mov     rcx, [rbp+38h]; this
0x1800100da  test    eax, eax
0x1800100dc  js      loc_180010709
0x1800100e2  mov     rax, [rbp+var_38]
0x1800100e6  mov     [rbp+var_38], r12
0x1800100ea  mov     [rbp+arg_20], rax
0x1800100ee  mov     rcx, [rbp+var_38]
0x1800100f2  test    rcx, rcx
0x1800100f5  jz      short loc_180010108
0x1800100f7  mov     [rbp+var_38], r12
0x1800100fb  mov     rax, [rcx]
0x1800100fe  mov     rax, [rax+10h]
0x180010102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010107  nop
0x180010108  mov     rcx, rbx; bstrString
0x18001010b  call    cs:__imp_SysFreeString
0x180010112  nop     dword ptr [rax+rax+00h]
0x180010117  test    edi, edi
0x180010119  js      loc_1800101C0
0x18001011f  movsxd  rax, [rbp+arg_0]
0x180010123  test    eax, eax
0x180010125  jle     loc_1800101F7
0x18001012b  mov     rcx, [r15+8]
0x18001012f  cmp     rax, rcx
0x180010132  jbe     loc_18001024C
0x180010138  cmp     rcx, r13
0x18001013b  jz      loc_1800106E5
0x180010141  test    rcx, rcx
0x180010144  jz      loc_180010218
0x18001014a  lea     rbx, [rcx+rcx*2]
0x18001014e  shr     rbx, 1
0x180010151  inc     rbx
0x180010154  cmp     rax, rbx
0x180010157  cmova   rbx, rax
0x18001015b  cmp     rbx, r13
0x18001015e  cmova   rbx, r13
0x180010162  lea     rcx, ds:0[rbx*8]; unsigned __int64
0x18001016a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180010171  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180010176  mov     rdi, rax
0x180010179  test    rax, rax
0x18001017c  jnz     loc_180010222
0x180010182  mov     rcx, [rbp+38h]; this
0x180010186  mov     r9d, r14d; char *
0x180010189  lea     r8, aOnecoreAdminAp_17; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180010190  mov     edx, 0B4h; void *
0x180010195  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001019a  nop
0x18001019b  lea     rcx, [rbp+arg_20]
0x18001019f  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x1800101a4  mov     eax, r14d
0x1800101a7  mov     rbx, [rsp+60h+arg_8]
0x1800101af  add     rsp, 60h
0x1800101b3  pop     r15
0x1800101b5  pop     r14
0x1800101b7  pop     r13
0x1800101b9  pop     r12
0x1800101bb  pop     rdi
0x1800101bc  pop     rsi
0x1800101bd  pop     rbp
0x1800101be  retn
0x1800101c0  mov     rcx, [rbp+38h]; this
0x1800101c4  mov     r9d, edi; char *
0x1800101c7  lea     r8, aOnecoreAdminAp_17; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800101ce  mov     edx, 0B0h; void *
0x1800101d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800101d8  nop
0x1800101d9  mov     rcx, [rbp+arg_20]
0x1800101dd  test    rcx, rcx
0x1800101e0  jz      short loc_1800101F3
0x1800101e2  mov     [rbp+arg_20], r12
0x1800101e6  mov     rax, [rcx]
0x1800101e9  mov     rax, [rax+10h]
0x1800101ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101f2  nop
0x1800101f3  mov     eax, edi
0x1800101f5  jmp     short loc_1800101A7
0x1800101f7  xor     r15d, r15d
0x1800101fa  mov     rcx, [rbp+arg_20]
0x1800101fe  test    rcx, rcx
0x180010201  jz      short loc_180010214
0x180010203  mov     [rbp+arg_20], r15
0x180010207  mov     rax, [rcx]
0x18001020a  mov     rax, [rax+10h]
0x18001020e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010213  nop
0x180010214  xor     eax, eax
0x180010216  jmp     short loc_1800101A7
0x180010218  mov     ebx, 10h
0x18001021d  jmp     loc_180010154
0x180010222  mov     rdx, [r15]; Src
0x180010225  test    rdx, rdx
0x180010228  jz      short loc_180010242
0x18001022a  mov     r8, [r15+10h]
0x18001022e  shl     r8, 3; Size
0x180010232  mov     rcx, rdi; void *
0x180010235  call    memmove_0
0x18001023a  mov     rcx, [r15]; void *
0x18001023d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180010242  mov     [r15], rdi
0x180010245  mov     [r15+8], rbx
0x180010249  mov     eax, [rbp+arg_0]
0x18001024c  xor     r15d, r15d
0x18001024f  mov     r12d, r15d
0x180010252  cmp     r12d, eax
0x180010255  jge     short loc_1800101FA
0x180010257  mov     [rbp+var_40], r15
0x18001025b  mov     rcx, [rbp+arg_20]
0x18001025f  mov     rax, [rcx]
0x180010262  lea     r8, [rbp+var_40]
0x180010266  mov     edx, r12d
0x180010269  mov     rax, [rax+38h]
0x18001026d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010272  mov     ebx, eax
0x180010274  test    eax, eax
0x180010276  js      loc_180010605
0x18001027c  mov     [rbp+var_38], r15
0x180010280  mov     rcx, [rbp+var_40]
0x180010284  mov     rax, [rcx]
0x180010287  lea     r8, [rbp+var_38]
0x18001028b  lea     rdx, _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60
0x180010292  mov     rax, [rax]
0x180010295  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001029a  nop
0x18001029b  mov     ecx, 18h; Size
0x1800102a0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800102a5  mov     r14, rax
0x1800102a8  mov     qword ptr [rax+10h], 0
0x1800102b0  xorps   xmm0, xmm0
0x1800102b3  movups  xmmword ptr [rax], xmm0
0x1800102b6  mov     [rbp+var_28], rax
0x1800102ba  mov     rsi, [rbp+var_38]
0x1800102be  xor     eax, eax
0x1800102c0  movups  xmmword ptr [rbp+pvarg], xmm0
0x1800102c4  mov     qword ptr [rbp+pvarg+10h], rax
0x1800102c8  mov     word ptr [rbp+pvarg], r15w
0x1800102cd  mov     rbx, r15
0x1800102d0  test    rsi, rsi
0x1800102d3  jz      loc_18001074C
0x1800102d9  mov     rdi, [rbp+strIn]
0x1800102dd  test    rdi, rdi
0x1800102e0  jz      loc_18001074C
0x1800102e6  xor     ecx, ecx; bstrString
0x1800102e8  call    cs:__imp_SysFreeString
0x1800102ef  nop     dword ptr [rax+rax+00h]
0x1800102f4  xor     ebx, ebx
0x1800102f6  mov     [rbp+var_30], rbx
0x1800102fa  mov     ecx, 7FFFFFFFh
0x1800102ff  mov     rax, rdi
0x180010302  cmp     [rax], bx
0x180010305  jz      short loc_180010318
0x180010307  add     rax, 2
0x18001030b  sub     rcx, 1
0x18001030f  jnz     short loc_180010302
0x180010311  mov     edi, 80070057h
0x180010316  jmp     short loc_18001034C
0x180010318  mov     edx, 7FFFFFFFh
0x18001031d  sub     edx, ecx; ui
0x18001031f  cmp     edx, r13d
0x180010322  ja      loc_180010760
0x180010328  mov     rcx, rdi; strIn
0x18001032b  call    cs:__imp_SysAllocStringLen
0x180010332  nop     dword ptr [rax+rax+00h]
0x180010337  mov     rbx, rax
0x18001033a  mov     [rbp+var_30], rax
0x18001033e  test    rax, rax
0x180010341  jnz     loc_1800107FC
0x180010347  mov     edi, 8007000Eh
0x18001034c  mov     rcx, [rbp+38h]; this
0x180010350  test    edi, edi
0x180010352  js      loc_18001059B
0x180010358  mov     rax, [rsi]
0x18001035b  lea     r8, [rbp+pvarg]
0x18001035f  mov     rdx, rbx
0x180010362  mov     rcx, rsi
0x180010365  mov     rax, [rax+160h]
0x18001036c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010371  mov     edi, eax
0x180010373  mov     rcx, [rbp+38h]; this
0x180010377  test    eax, eax
0x180010379  js      loc_1800105EC
0x18001037f  mov     rdx, qword ptr [rbp+pvarg+8]; unsigned __int16 *
0x180010383  test    rdx, rdx
0x180010386  jnz     loc_180010579
0x18001038c  mov     eax, [r14]
0x18001038f  add     rax, rax
0x180010392  mov     rcx, [r14+8]
0x180010396  jnz     loc_18001081C
0x18001039c  mov     rcx, rbx; bstrString
0x18001039f  call    cs:__imp_SysFreeString
0x1800103a6  nop     dword ptr [rax+rax+00h]
0x1800103ab  nop
0x1800103ac  lea     rcx, [rbp+pvarg]; pvarg
0x1800103b0  call    cs:__imp_VariantClear
0x1800103b7  nop     dword ptr [rax+rax+00h]
0x1800103bc  test    edi, edi
0x1800103be  js      loc_18001076A
0x1800103c4  cmp     byte ptr [rbp+arg_28], 0
0x1800103c8  jnz     loc_1800104DE
0x1800103ce  test    r15d, r15d
0x1800103d1  jnz     loc_18001082E
0x1800103d7  mov     rcx, [r14+8]; void *
0x1800103db  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800103e0  xor     esi, esi
0x1800103e2  mov     [r14+8], rsi
0x1800103e6  mov     [r14], esi
0x1800103e9  mov     [r14+10h], esi
0x1800103ed  mov     r15, [rbp+arg_18]
  ... truncated ...
```
