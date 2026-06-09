# OSIntegration::Tools::ConvertElementsIntoStringBufferArrayForQuery(IXMLDOMElement *,ushort const *,Common::Array<Common::StringBuffer,Common::ContainerOperations<Common::StringBuffer,Common::StringBuffer>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::StringBuffer>,Common::ArrayOperations<Common::StringBuffer,Common::NoKey>> &,OSIntegration::Tools::ItemVerifier *)

- ea: `0x180010890`
- end: `0x180010fd6`
- name: `?ConvertElementsIntoStringBufferArrayForQuery@Tools@OSIntegration@@YAJPEAUIXMLDOMElement@@PEBGAEAV?$Array@VStringBuffer@Common@@V?$ContainerOperations@VStringBuffer@Common@@V12@@2@VNoKey@2@V?$ContainerOperations@VNoKey@Common@@VStringBuffer@2@@2@V?$ArrayOperations@VStringBuffer@Common@@VNoKey@2@@2@@Common@@PEAVItemVerifier@12@@Z`
- size: `1862`
- prototype: ``
- caller_count: `5`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180018300`
- `0x180055570`
- `0x18009acb0`
- `0x1800df120`
- `0x1800e0950`

## callees

- `0x180006970`
- `0x180009dc0`
- `0x180010890`
- `0x180010fdc`
- `0x180012fc8`
- `0x18001adb4`
- `0x1800af1bc`
- `0x1800af1fc`
- `0x1800af220`
- `0x1800ba475`
- `0x1801ac010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001096a`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001096a`
- `OLEAUT32!__imp_SysFreeString` at `0x180010913`
- `OLEAUT32!__imp_SysFreeString` at `0x180010a21`
- `OLEAUT32!__imp_SysFreeString` at `0x180010cb9`
- `OLEAUT32!__imp_SysFreeString` at `0x180010913`
- `OLEAUT32!__imp_SysFreeString` at `0x180010a21`
- `OLEAUT32!__imp_SysFreeString` at `0x180010cb9`

## string_xrefs

- `0x1800108cf`: `onecore\admin\appmodel\osim\src\deh\appx\common\xmltools.cpp`
- `0x180010a65`: `onecore\admin\appmodel\osim\src\deh\appx\common\xmltools.cpp`
- `0x180010b20`: `onecore\admin\appmodel\osim\src\deh\appx\common\xmltools.cpp`
- `0x180010c42`: `onecore\admin\appmodel\osim\src\deh\appx\common\xmltools.cpp`
- `0x180010d5e`: `onecore\admin\appmodel\osim\src\deh\appx\common\xmltools.cpp`
- `0x180010e31`: `onecore\admin\appmodel\osim\src\deh\appx\common\xmltools.cpp`
- `0x180010ec7`: `onecore\admin\appmodel\osim\src\deh\appx\common\xmltools.cpp`
- `0x180010fa2`: `onecore\admin\appmodel\osim\src\deh\appx\common\xmltools.cpp`
- `0x180010a9b`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x180010ab4`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x180010f46`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x180010f69`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x180010f82`: `onecore\admin\appmodel\common\xmltools.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall OSIntegration::Tools::ConvertElementsIntoStringBufferArrayForQuery(
        __int64 a1,
        const OLECHAR *a2,
        __int64 a3,
        __int64 (__fastcall ***a4)(_QWORD, void *, __int64, _QWORD))
{
  int v7; // r15d
  OLECHAR *v9; // rbx
  __int64 v10; // rcx
  const OLECHAR *v11; // rax
  int v12; // edi
  unsigned int v13; // esi
  int v14; // eax
  int v15; // eax
  __int64 v16; // rax
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rcx
  unsigned __int64 v21; // rcx
  unsigned __int64 v22; // rbx
  void *v23; // rax
  void *v24; // rdi
  const struct std::nothrow_t *v25; // rdx
  int i; // r14d
  int v27; // eax
  unsigned int v28; // ebx
  OLECHAR *v29; // rdi
  int v30; // eax
  int v31; // ebx
  void (__fastcall ***v32)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v33; // rcx
  int v34; // eax
  int v35; // eax
  unsigned int v36; // ebx
  unsigned __int64 v37; // rcx
  unsigned __int64 v38; // rax
  unsigned __int64 v39; // rbx
  void *v40; // rax
  void *v41; // r15
  const struct std::nothrow_t *v42; // rdx
  __int64 v43; // rcx
  void (__fastcall ***v44)(_QWORD, GUID *, _QWORD *); // rcx
  const struct std::nothrow_t *v45; // rdx
  void *v46; // rcx
  __int64 v47; // rcx
  void (__fastcall ***v48)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v49; // rcx
  __int64 v50; // rcx
  void (__fastcall ***v51)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v52; // rcx
  int v53; // [rsp+20h] [rbp-40h]
  __int64 v54; // [rsp+30h] [rbp-30h] BYREF
  void (__fastcall ***v55)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-28h] BYREF
  __int64 v56; // [rsp+40h] [rbp-20h] BYREF
  BSTR bstrString[3]; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  int v59; // [rsp+A0h] [rbp+40h] BYREF
  __int64 (__fastcall ***v60)(_QWORD, void *, __int64, _QWORD); // [rsp+B8h] [rbp+58h]

  v60 = a4;
  v7 = 0;
  v59 = 0;
  v54 = 0;
  if ( a1 && a2 )
  {
    v56 = 0;
    SysFreeString(0);
    v9 = 0;
    bstrString[0] = 0;
    v10 = 0x7FFFFFFF;
    v11 = a2;
    while ( *v11 )
    {
      ++v11;
      if ( !--v10 )
      {
        v12 = -2147024809;
        v13 = -2147024882;
        goto LABEL_12;
      }
    }
    v13 = -2147024882;
    if ( (unsigned int)(0x7FFFFFFF - v10) > 0x3FFFFFFF )
    {
      v12 = -2147024809;
    }
    else
    {
      v9 = SysAllocStringLen(a2, 0x7FFFFFFF - (int)v10);
      bstrString[0] = v9;
      v12 = 0;
      if ( !v9 )
        v12 = -2147024882;
    }
LABEL_12:
    if ( v12 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x27,
        (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
        (const char *)(unsigned int)v12,
        v53);
    }
    else
    {
      v14 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, __int64 *))(*(_QWORD *)a1 + 288LL))(a1, v9, &v56);
      v12 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2B,
          (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
          (const char *)(unsigned int)v14,
          v53);
      }
      else
      {
        v15 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v56 + 64LL))(v56, &v59);
        v12 = v15;
        if ( v15 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x2D,
            (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
            (const char *)(unsigned int)v15,
            v53);
        }
        else
        {
          v16 = v56;
          v56 = 0;
          v54 = v16;
        }
      }
    }
    v17 = v56;
    if ( v56 )
    {
      v56 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    SysFreeString(v9);
    if ( v12 >= 0 )
    {
      v18 = v59;
      if ( v59 <= 0 )
      {
LABEL_20:
        v19 = v54;
        if ( v54 )
        {
          v54 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        }
        return 0;
      }
      v21 = *(_QWORD *)(a3 + 8);
      if ( v59 > v21 )
      {
        if ( v21 == 0x3FFFFFFF )
        {
          v13 = -2147483637;
LABEL_37:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x78,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\xmltools.cpp",
            (const char *)v13,
            v53);
          Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v54);
          return v13;
        }
        if ( v21 )
          v22 = ((3 * v21) >> 1) + 1;
        else
          v22 = 16;
        if ( v59 > v22 )
          v22 = v59;
        if ( v22 > 0x3FFFFFFF )
          v22 = 0x3FFFFFFF;
        v23 = operator new[](8 * v22, (const struct std::nothrow_t *)&std::nothrow);
        v24 = v23;
        if ( !v23 )
          goto LABEL_37;
        if ( *(_QWORD *)a3 )
        {
          memmove_0(v23, *(const void **)a3, 8LL * *(_QWORD *)(a3 + 16));
          operator delete(*(void **)a3, v25);
        }
        *(_QWORD *)a3 = v24;
        *(_QWORD *)(a3 + 8) = v22;
        v18 = v59;
      }
      for ( i = 0; i < v18; ++i )
      {
        v55 = 0;
        v27 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v54 + 56LL))(v54, (unsigned int)i, &v55);
        v28 = v27;
        if ( v27 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x7D,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\xmltools.cpp",
            (const char *)(unsigned int)v27,
            v53);
          v32 = v55;
          if ( v55 )
          {
            v55 = 0;
            ((void (__fastcall *)(void (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v32)[2])(v32);
          }
          v33 = v54;
          if ( v54 )
          {
            v54 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
          }
          return v28;
        }
        v56 = 0;
        (**v55)(v55, &GUID_2933bf86_7b36_11d2_b20e_00c04f983e60, &v56);
        v29 = (OLECHAR *)operator new(0x18u);
        *((_QWORD *)v29 + 2) = 0;
        *(_OWORD *)v29 = 0;
        bstrString[1] = v29;
        bstrString[0] = 0;
        if ( v56 )
        {
          v30 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v56 + 208LL))(v56, bstrString);
          v31 = v30;
          if ( v30 < 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x35B,
              (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
              (const char *)(unsigned int)v30,
              v53);
          }
          else if ( bstrString[0] )
          {
            v34 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)v29, bstrString[0]);
            v31 = v34;
            if ( v34 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x361,
                (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
                (const char *)(unsigned int)v34,
                v53);
            else
              v7 = 1;
          }
          else
          {
            v31 = -2147024883;
          }
        }
        else
        {
          v31 = -2147024809;
        }
        SysFreeString(bstrString[0]);
        if ( v31 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x8D,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\xmltools.cpp",
            (const char *)(unsigned int)v31,
            v53);
          Common::AutoPtrDeallocate<Common::StringBuffer>(v29);
          v50 = v56;
          if ( v56 )
          {
            v56 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
          }
          v51 = v55;
          if ( v55 )
          {
            v55 = 0;
            ((void (__fastcall *)(void (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v51)[2])(v51);
          }
          v52 = v54;
          if ( v54 )
          {
            v54 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
          }
          return (unsigned int)v31;
        }
        if ( !v7 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x8F,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\xmltools.cpp",
            (const char *)0x80070057LL,
            v53);
          Common::AutoPtrDeallocate<Common::StringBuffer>(v29);
          Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v56);
          Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v55);
          goto LABEL_3;
        }
        if ( v60 )
        {
          v35 = (**v60)(v60, v29, v56, 0);
          v36 = v35;
          if ( v35 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x97,
              (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\xmltools.cpp",
              (const char *)(unsigned int)v35,
              v53);
            v46 = (void *)*((_QWORD *)v29 + 1);
            if ( v46 )
              operator delete(v46, v45);
            operator delete(v29, (const struct std::nothrow_t *)0x18);
            v47 = v56;
            if ( v56 )
            {
              v56 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
            }
            v48 = v55;
            if ( v55 )
            {
              v55 = 0;
              ((void (__fastcall *)(void (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v48)[2])(v48);
            }
            v49 = v54;
            if ( v54 )
            {
              v54 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
            }
            return v36;
          }
        }
        v37 = *(_QWORD *)(a3 + 16) + 1LL;
        v38 = *(_QWORD *)(a3 + 8);
        if ( v37 > v38 )
        {
          if ( v38 == 0x3FFFFFFF )
          {
            v13 = -2147483637;
LABEL_71:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x99,
              (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\xmltools.cpp",
              (const char *)v13,
              v53);
            Common::AutoPtrDeallocate<Common::StringBuffer>(v29);
            Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v56);
            Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v55);
            Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v54);
            return v13;
          }
          if ( v38 )
            v39 = ((3 * v38) >> 1) + 1;
          else
            v39 = 16;
          if ( v37 > v39 )
            v39 = *(_QWORD *)(a3 + 16) + 1LL;
          if ( v39 > 0x3FFFFFFF )
            v39 = 0x3FFFFFFF;
          v40 = operator new[](8 * v39, (const struct std::nothrow_t *)&std::nothrow);
          v41 = v40;
          if ( !v40 )
            goto LABEL_71;
          if ( *(_QWORD *)a3 )
          {
            memmove_0(v40, *(const void **)a3, 8LL * *(_QWORD *)(a3 + 16));
            operator delete(*(void **)a3, v42);
          }
          *(_QWORD *)a3 = v41;
          *(_QWORD *)(a3 + 8) = v39;
        }
        *(_QWORD *)(*(_QWORD *)a3 + 8LL * (*(_QWORD *)(a3 + 16))++) = v29;
        v43 = v56;
        v7 = 0;
        if ( v56 )
        {
          v56 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
        }
        v44 = v55;
        if ( v55 )
        {
          v55 = 0;
          ((void (__fastcall *)(void (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v44)[2])(v44);
        }
        v18 = v59;
      }
      goto LABEL_20;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x74,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\xmltools.cpp",
      (const char *)(unsigned int)v12,
      v53);
    v20 = v54;
    if ( v54 )
    {
      v54 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    return (unsigned int)v12;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x72,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\xmltools.cpp",
      (const char *)0x80070057LL,
      v53);
LABEL_3:
    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v54);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180010890  mov     [rsp-38h+arg_8], rbx
0x180010895  mov     [rsp-38h+arg_18], r9
0x18001089a  push    rbp
0x18001089b  push    rsi
0x18001089c  push    rdi
0x18001089d  push    r12
0x18001089f  push    r13
0x1800108a1  push    r14
0x1800108a3  push    r15
0x1800108a5  mov     rbp, rsp
0x1800108a8  sub     rsp, 60h
0x1800108ac  mov     r13, r8
0x1800108af  mov     rdi, rdx
0x1800108b2  mov     r14, rcx
0x1800108b5  xor     r15d, r15d
0x1800108b8  mov     [rbp+arg_0], r15d
0x1800108bc  mov     [rbp+var_30], r15
0x1800108c0  test    rcx, rcx
0x1800108c3  jnz     short loc_180010908
0x1800108c5  mov     rcx, [rbp+38h]; this
0x1800108c9  mov     r9d, 80070057h; char *
0x1800108cf  lea     r8, aOnecoreAdminAp_17; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800108d6  mov     edx, 72h ; 'r'; void *
0x1800108db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800108e0  nop
0x1800108e1  lea     rcx, [rbp+var_30]
0x1800108e5  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x1800108ea  mov     eax, 80070057h
0x1800108ef  mov     rbx, [rsp+60h+arg_8]
0x1800108f7  add     rsp, 60h
0x1800108fb  pop     r15
0x1800108fd  pop     r14
0x1800108ff  pop     r13
0x180010901  pop     r12
0x180010903  pop     rdi
0x180010904  pop     rsi
0x180010905  pop     rbp
0x180010906  retn
0x180010908  test    rdi, rdi
0x18001090b  jz      short loc_1800108C5
0x18001090d  mov     [rbp+var_20], r15
0x180010911  xor     ecx, ecx; bstrString
0x180010913  call    cs:__imp_SysFreeString
0x18001091a  nop     dword ptr [rax+rax+00h]
0x18001091f  mov     rbx, r15
0x180010922  mov     [rbp+bstrString], rbx
0x180010926  mov     edx, 7FFFFFFFh
0x18001092b  mov     ecx, edx
0x18001092d  mov     rax, rdi
0x180010930  cmp     [rax], bx
0x180010933  jz      short loc_180010951
0x180010935  add     rax, 2
0x180010939  sub     rcx, 1
0x18001093d  jnz     short loc_180010930
0x18001093f  mov     edi, 80070057h
0x180010944  mov     esi, 8007000Eh
0x180010949  mov     r12d, 3FFFFFFFh
0x18001094f  jmp     short loc_180010986
0x180010951  sub     edx, ecx; ui
0x180010953  mov     esi, 8007000Eh
0x180010958  mov     r12d, 3FFFFFFFh
0x18001095e  cmp     edx, r12d
0x180010961  ja      loc_180010C8F
0x180010967  mov     rcx, rdi; strIn
0x18001096a  call    cs:__imp_SysAllocStringLen
0x180010971  nop     dword ptr [rax+rax+00h]
0x180010976  mov     rbx, rax
0x180010979  mov     [rbp+bstrString], rax
0x18001097d  mov     edi, r15d
0x180010980  test    rax, rax
0x180010983  cmovz   edi, esi
0x180010986  mov     rcx, [rbp+38h]; this
0x18001098a  test    edi, edi
0x18001098c  js      loc_180010F43
0x180010992  mov     rax, [r14]
0x180010995  mov     rdi, [rax+120h]
0x18001099c  mov     rcx, [rbp+var_20]
0x1800109a0  test    rcx, rcx
0x1800109a3  jz      short loc_1800109B6
0x1800109a5  mov     [rbp+var_20], r15
0x1800109a9  mov     rax, [rcx]
0x1800109ac  mov     rax, [rax+10h]
0x1800109b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109b5  nop
0x1800109b6  lea     r8, [rbp+var_20]
0x1800109ba  mov     rdx, rbx
0x1800109bd  mov     rcx, r14
0x1800109c0  mov     rax, rdi
0x1800109c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109c8  mov     edi, eax
0x1800109ca  mov     rcx, [rbp+38h]; this
0x1800109ce  test    eax, eax
0x1800109d0  js      loc_180010A98
0x1800109d6  mov     rcx, [rbp+var_20]
0x1800109da  mov     rax, [rcx]
0x1800109dd  lea     rdx, [rbp+arg_0]
0x1800109e1  mov     rax, [rax+40h]
0x1800109e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109ea  mov     edi, eax
0x1800109ec  mov     rcx, [rbp+38h]; this
0x1800109f0  test    eax, eax
0x1800109f2  js      loc_180010AB1
0x1800109f8  mov     rax, [rbp+var_20]
0x1800109fc  mov     [rbp+var_20], r15
0x180010a00  mov     [rbp+var_30], rax
0x180010a04  mov     rcx, [rbp+var_20]
0x180010a08  test    rcx, rcx
0x180010a0b  jz      short loc_180010A1E
0x180010a0d  mov     [rbp+var_20], r15
0x180010a11  mov     rax, [rcx]
0x180010a14  mov     rax, [rax+10h]
0x180010a18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a1d  nop
0x180010a1e  mov     rcx, rbx; bstrString
0x180010a21  call    cs:__imp_SysFreeString
0x180010a28  nop     dword ptr [rax+rax+00h]
0x180010a2d  test    edi, edi
0x180010a2f  js      short loc_180010A5E
0x180010a31  movsxd  rax, [rbp+arg_0]
0x180010a35  test    eax, eax
0x180010a37  jg      loc_180010ACA
0x180010a3d  mov     rcx, [rbp+var_30]
0x180010a41  test    rcx, rcx
0x180010a44  jz      short loc_180010A57
0x180010a46  mov     [rbp+var_30], r15
0x180010a4a  mov     rax, [rcx]
0x180010a4d  mov     rax, [rax+10h]
0x180010a51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a56  nop
0x180010a57  xor     eax, eax
0x180010a59  jmp     loc_1800108EF
0x180010a5e  mov     rcx, [rbp+38h]; this
0x180010a62  mov     r9d, edi; char *
0x180010a65  lea     r8, aOnecoreAdminAp_17; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180010a6c  mov     edx, 74h ; 't'; void *
0x180010a71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010a76  nop
0x180010a77  mov     rcx, [rbp+var_30]
0x180010a7b  test    rcx, rcx
0x180010a7e  jz      short loc_180010A91
0x180010a80  mov     [rbp+var_30], r15
0x180010a84  mov     rax, [rcx]
0x180010a87  mov     rax, [rax+10h]
0x180010a8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a90  nop
0x180010a91  mov     eax, edi
0x180010a93  jmp     loc_1800108EF
0x180010a98  mov     r9d, eax; char *
0x180010a9b  lea     r8, aOnecoreAdminAp_120; "onecore\\admin\\appmodel\\common\\xmlto"...
0x180010aa2  mov     edx, 2Bh ; '+'; void *
0x180010aa7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180010aac  jmp     loc_180010A04
0x180010ab1  mov     r9d, eax; char *
0x180010ab4  lea     r8, aOnecoreAdminAp_120; "onecore\\admin\\appmodel\\common\\xmlto"...
0x180010abb  mov     edx, 2Dh ; '-'; void *
0x180010ac0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180010ac5  jmp     loc_180010A04
0x180010aca  mov     rcx, [r13+8]
0x180010ace  cmp     rax, rcx
0x180010ad1  jbe     loc_180010B76
0x180010ad7  cmp     rcx, r12
0x180010ada  jz      loc_180010C31
0x180010ae0  test    rcx, rcx
0x180010ae3  jz      short loc_180010B42
0x180010ae5  lea     rbx, [rcx+rcx*2]
0x180010ae9  shr     rbx, 1
0x180010aec  inc     rbx
0x180010aef  cmp     rax, rbx
0x180010af2  cmova   rbx, rax
0x180010af6  cmp     rbx, r12
0x180010af9  cmova   rbx, r12
0x180010afd  lea     rcx, ds:0[rbx*8]; unsigned __int64
0x180010b05  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180010b0c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180010b11  mov     rdi, rax
0x180010b14  test    rax, rax
0x180010b17  jnz     short loc_180010B49
0x180010b19  mov     rcx, [rbp+38h]; this
0x180010b1d  mov     r9d, esi; char *
0x180010b20  lea     r8, aOnecoreAdminAp_17; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180010b27  mov     edx, 78h ; 'x'; void *
0x180010b2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010b31  nop
0x180010b32  lea     rcx, [rbp+var_30]
0x180010b36  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x180010b3b  mov     eax, esi
0x180010b3d  jmp     loc_1800108EF
0x180010b42  mov     ebx, 10h
0x180010b47  jmp     short loc_180010AEF
0x180010b49  mov     rdx, [r13+0]; Src
0x180010b4d  test    rdx, rdx
0x180010b50  jz      short loc_180010B6B
0x180010b52  mov     r8, [r13+10h]
0x180010b56  shl     r8, 3; Size
0x180010b5a  mov     rcx, rdi; void *
0x180010b5d  call    memmove_0
0x180010b62  mov     rcx, [r13+0]; void *
0x180010b66  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180010b6b  mov     [r13+0], rdi
0x180010b6f  mov     [r13+8], rbx
0x180010b73  mov     eax, [rbp+arg_0]
0x180010b76  mov     r14d, r15d
0x180010b79  nop     dword ptr [rax+00000000h]
0x180010b80  cmp     r14d, eax
0x180010b83  jge     loc_180010A3D
0x180010b89  mov     [rbp+var_28], r15
0x180010b8d  mov     rcx, [rbp+var_30]
0x180010b91  mov     rax, [rcx]
0x180010b94  lea     r8, [rbp+var_28]
0x180010b98  mov     edx, r14d
0x180010b9b  mov     rax, [rax+38h]
0x180010b9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ba4  mov     ebx, eax
0x180010ba6  test    eax, eax
0x180010ba8  js      loc_180010C3B
0x180010bae  mov     [rbp+var_20], r15
0x180010bb2  mov     rcx, [rbp+var_28]
0x180010bb6  mov     rax, [rcx]
0x180010bb9  lea     r8, [rbp+var_20]
0x180010bbd  lea     rdx, _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60
0x180010bc4  mov     rax, [rax]
0x180010bc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010bcc  nop
0x180010bcd  mov     ecx, 18h; Size
0x180010bd2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010bd7  mov     rdi, rax
0x180010bda  mov     qword ptr [rax+10h], 0
0x180010be2  xorps   xmm0, xmm0
0x180010be5  movups  xmmword ptr [rax], xmm0
0x180010be8  mov     [rbp+var_10], rax
0x180010bec  mov     rcx, [rbp+var_20]
0x180010bf0  mov     [rbp+bstrString], r15
0x180010bf4  test    rcx, rcx
0x180010bf7  jz      loc_180010F5C
0x180010bfd  mov     rax, [rcx]
0x180010c00  lea     rdx, [rbp+bstrString]
0x180010c04  mov     rax, [rax+0D0h]
0x180010c0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c10  mov     ebx, eax
0x180010c12  mov     rcx, [rbp+38h]; this
0x180010c16  test    eax, eax
0x180010c18  js      loc_180010F66
0x180010c1e  mov     rdx, [rbp+bstrString]; unsigned __int16 *
0x180010c22  test    rdx, rdx
0x180010c25  jnz     short loc_180010C99
0x180010c27  mov     ebx, 8007000Dh
0x180010c2c  jmp     loc_180010CB5
0x180010c31  mov     esi, 8000000Bh
0x180010c36  jmp     loc_180010B19
0x180010c3b  mov     rcx, [rbp+38h]; this
0x180010c3f  mov     r9d, ebx; char *
0x180010c42  lea     r8, aOnecoreAdminAp_17; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180010c49  mov     edx, 7Dh ; '}'; void *
0x180010c4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010c53  nop
0x180010c54  mov     rcx, [rbp+var_28]
0x180010c58  test    rcx, rcx
0x180010c5b  jz      short loc_180010C6E
0x180010c5d  mov     [rbp+var_28], r15
0x180010c61  mov     rax, [rcx]
0x180010c64  mov     rax, [rax+10h]
0x180010c68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c6d  nop
0x180010c6e  mov     rcx, [rbp+var_30]
0x180010c72  test    rcx, rcx
0x180010c75  jz      short loc_180010C88
0x180010c77  mov     [rbp+var_30], r15
0x180010c7b  mov     rax, [rcx]
0x180010c7e  mov     rax, [rax+10h]
0x180010c82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c87  nop
0x180010c88  mov     eax, ebx
0x180010c8a  jmp     loc_1800108EF
0x180010c8f  mov     edi, 80070057h
0x180010c94  jmp     loc_180010986
0x180010c99  mov     rcx, rdi; this
0x180010c9c  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x180010ca1  mov     ebx, eax
0x180010ca3  mov     rcx, [rbp+38h]; this
0x180010ca7  test    eax, eax
0x180010ca9  js      loc_180010F7F
0x180010caf  mov     r15d, 1
0x180010cb5  mov     rcx, [rbp+bstrString]; bstrString
0x180010cb9  call    cs:__imp_SysFreeString
0x180010cc0  nop     dword ptr [rax+rax+00h]
0x180010cc5  test    ebx, ebx
0x180010cc7  js      loc_180010EC0
0x180010ccd  test    r15d, r15d
0x180010cd0  jz      loc_180010F98
0x180010cd6  mov     r15, [rbp+arg_18]
0x180010cda  test    r15, r15
0x180010cdd  jz      short loc_180010D01
0x180010cdf  mov     rax, [r15]
0x180010ce2  xor     r9d, r9d
0x180010ce5  mov     r8, [rbp+var_20]
0x180010ce9  mov     rdx, rdi
0x180010cec  mov     rcx, r15
0x180010cef  mov     rax, [rax]
0x180010cf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010cf7  mov     ebx, eax
  ... truncated ...
```
