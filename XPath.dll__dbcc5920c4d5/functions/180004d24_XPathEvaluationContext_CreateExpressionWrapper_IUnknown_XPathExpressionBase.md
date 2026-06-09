# XPathEvaluationContext::CreateExpressionWrapper(IUnknown *,XPathExpressionBase * *)

- ea: `0x180004d24`
- end: `0x180005061`
- name: `?CreateExpressionWrapper@XPathEvaluationContext@@CAJPEAUIUnknown@@PEAPEAVXPathExpressionBase@@@Z`
- size: `829`
- prototype: `__int64 __fastcall(struct IUnknown *, struct XPathExpressionBase **)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180005550`
- `0x1800056a0`
- `0x18000588c`

## callees

- `0x180001078`
- `0x1800020b4`
- `0x1800021a4`
- `0x180004b84`
- `0x180004d24`
- `0x180005068`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall XPathEvaluationContext::CreateExpressionWrapper(struct IUnknown *a1, struct IUnknown ***a2)
{
  struct IUnknownVtbl *lpVtbl; // rax
  int Instance; // eax
  unsigned int v6; // ebx
  struct IUnknownVtbl *v7; // rax
  int v8; // r14d
  struct IUnknown *v9; // rsi
  struct IUnknown **v10; // rax
  struct IUnknown **v11; // rbx
  struct IUnknownVtbl *v12; // rax
  struct IUnknown *v13; // rsi
  struct IUnknown **v14; // rax
  struct IUnknown **v15; // rbx
  struct IUnknownVtbl *v16; // rax
  struct IUnknown *v17; // rsi
  struct IUnknown **v18; // rax
  struct IUnknown **v19; // rbx
  struct IUnknownVtbl *v20; // rax
  int v21; // eax
  struct IUnknown *v22; // rsi
  struct IUnknown **v23; // rax
  struct IUnknown **v24; // rbx
  struct IUnknown *v26; // [rsp+20h] [rbp-10h] BYREF
  struct IUnknown *v27; // [rsp+28h] [rbp-8h] BYREF
  struct IUnknown *v28; // [rsp+60h] [rbp+30h] BYREF
  struct IUnknown *v29; // [rsp+70h] [rbp+40h] BYREF
  struct IUnknown *v30; // [rsp+78h] [rbp+48h] BYREF

  lpVtbl = a1->lpVtbl;
  v27 = 0;
  Instance = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))lpVtbl->QueryInterface)(
               a1,
               &GUID_d97fe0e8_dc26_49c3_82e2_da894705a4ac,
               &v27);
  if ( Instance >= 0 )
  {
    if ( v27 )
      Instance = XPathExpressionWrapperTemplate<XPathNodeIteratorWrapper,XPathNodeIteratorBase,IXPathNodeIterator>::CreateInstance(v27);
    goto LABEL_5;
  }
  if ( Instance == -2147467262 )
  {
    v7 = a1->lpVtbl;
    v28 = 0;
    v8 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))v7->QueryInterface)(
           a1,
           &GUID_df2bf0e5_8012_4737_ae4c_28272f66c9f7,
           &v28);
    if ( v8 >= 0 )
    {
      v9 = v28;
      if ( v28 )
      {
        v10 = (struct IUnknown **)operator new(0x18u);
        v11 = v10;
        if ( v10 )
        {
          v10[1] = 0;
          v10[2] = 0;
          *v10 = (struct IUnknown *)&SimpleIUnknownImpl<IXPathExpression>::`vftable';
          *((_DWORD *)v10 + 2) = 1;
          ModuleRefCounter::AddRef();
          v11[2] = 0;
          *v11 = (struct IUnknown *)&BooleanExpressionWrapper::`vftable';
          if ( v11[2] != v9 )
            ATL::AtlComPtrAssign(v11 + 2, v9);
          *a2 = v11;
          v6 = 0;
        }
        else
        {
          v6 = -2147024882;
        }
        goto LABEL_13;
      }
LABEL_15:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v28);
      v6 = v8;
      goto LABEL_46;
    }
    if ( v8 != -2147467262 )
      goto LABEL_15;
    v12 = a1->lpVtbl;
    v29 = 0;
    v8 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))v12->QueryInterface)(
           a1,
           &GUID_fe11aa2c_6109_4ebc_a14b_d8cf77a4998f,
           &v29);
    if ( v8 >= 0 )
    {
      v13 = v29;
      if ( v29 )
      {
        v14 = (struct IUnknown **)operator new(0x18u);
        v15 = v14;
        if ( v14 )
        {
          v14[1] = 0;
          v14[2] = 0;
          *v14 = (struct IUnknown *)&SimpleIUnknownImpl<IXPathExpression>::`vftable';
          *((_DWORD *)v14 + 2) = 1;
          ModuleRefCounter::AddRef();
          v15[2] = 0;
          *v15 = (struct IUnknown *)&NumberExpressionWrapper::`vftable';
          if ( v15[2] != v13 )
            ATL::AtlComPtrAssign(v15 + 2, v13);
          *a2 = v15;
          v6 = 0;
        }
        else
        {
          v6 = -2147024882;
        }
        goto LABEL_23;
      }
LABEL_25:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v29);
      goto LABEL_15;
    }
    if ( v8 != -2147467262 )
      goto LABEL_25;
    v16 = a1->lpVtbl;
    v30 = 0;
    v8 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))v16->QueryInterface)(
           a1,
           &GUID_7eb4b748_fa54_466b_b59c_86245f6af2bf,
           &v30);
    if ( v8 < 0 )
    {
      if ( v8 == -2147467262 )
      {
        v20 = a1->lpVtbl;
        v26 = 0;
        v21 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))v20->QueryInterface)(
                a1,
                &GUID_69010634_90e9_4e24_9568_083801973afb,
                &v26);
        v6 = v21;
        if ( v21 < 0 )
        {
          if ( v21 == -2147467262 )
          {
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v26);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v30);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v29);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v28);
            v6 = -2147024809;
            goto LABEL_46;
          }
        }
        else
        {
          v22 = v26;
          if ( v26 )
          {
            v23 = (struct IUnknown **)operator new(0x18u);
            v24 = v23;
            if ( v23 )
            {
              v23[1] = 0;
              v23[2] = 0;
              *v23 = (struct IUnknown *)&SimpleIUnknownImpl<IXPathExpression>::`vftable';
              *((_DWORD *)v23 + 2) = 1;
              ModuleRefCounter::AddRef();
              v24[2] = 0;
              *v24 = (struct IUnknown *)&CustomExpressionWrapper::`vftable';
              if ( v24[2] != v22 )
                ATL::AtlComPtrAssign(v24 + 2, v22);
              *a2 = v24;
              v6 = 0;
            }
            else
            {
              v6 = -2147024882;
            }
          }
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v26);
        goto LABEL_33;
      }
    }
    else
    {
      v17 = v30;
      if ( v30 )
      {
        v18 = (struct IUnknown **)operator new(0x18u);
        v19 = v18;
        if ( v18 )
        {
          v18[1] = 0;
          v18[2] = 0;
          *v18 = (struct IUnknown *)&SimpleIUnknownImpl<IXPathExpression>::`vftable';
          *((_DWORD *)v18 + 2) = 1;
          ModuleRefCounter::AddRef();
          v19[2] = 0;
          *v19 = (struct IUnknown *)&StringExpressionWrapper::`vftable';
          if ( v19[2] != v17 )
            ATL::AtlComPtrAssign(v19 + 2, v17);
          *a2 = v19;
          v6 = 0;
        }
        else
        {
          v6 = -2147024882;
        }
LABEL_33:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v30);
LABEL_23:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v29);
LABEL_13:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v28);
        goto LABEL_46;
      }
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v30);
    goto LABEL_25;
  }
LABEL_5:
  v6 = Instance;
LABEL_46:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v27);
  return v6;
}

```

## disassembly

```asm
0x180004d24  mov     [rsp-28h+arg_8], rbx
0x180004d29  push    rbp
0x180004d2a  push    rsi
0x180004d2b  push    rdi
0x180004d2c  push    r14
0x180004d2e  push    r15
0x180004d30  mov     rbp, rsp
0x180004d33  sub     rsp, 30h
0x180004d37  mov     rax, [rcx]
0x180004d3a  lea     r8, [rbp+var_8]
0x180004d3e  mov     rdi, rdx
0x180004d41  xor     r15d, r15d
0x180004d44  lea     rdx, _GUID_d97fe0e8_dc26_49c3_82e2_da894705a4ac
0x180004d4b  mov     [rbp+var_8], r15
0x180004d4f  mov     rbx, rcx
0x180004d52  mov     rax, [rax]
0x180004d55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d5a  test    eax, eax
0x180004d5c  js      short loc_180004D71
0x180004d5e  mov     rcx, [rbp+var_8]; struct IUnknown *
0x180004d62  test    rcx, rcx
0x180004d65  jz      short loc_180004D7A
0x180004d67  mov     rdx, rdi
0x180004d6a  call    ?CreateInstance@?$XPathExpressionWrapperTemplate@VXPathNodeIteratorWrapper@@VXPathNodeIteratorBase@@UIXPathNodeIterator@@@@SAJPEAUIXPathNodeIterator@@PEAPEAVXPathExpressionBase@@@Z; XPathExpressionWrapperTemplate<XPathNodeIteratorWrapper,XPathNodeIteratorBase,IXPathNodeIterator>::CreateInstance(IXPathNodeIterator *,XPathExpressionBase * *)
0x180004d6f  jmp     short loc_180004D7A
0x180004d71  mov     esi, 80004002h
0x180004d76  cmp     eax, esi
0x180004d78  jz      short loc_180004D81
0x180004d7a  mov     ebx, eax
0x180004d7c  jmp     loc_180005045
0x180004d81  mov     rax, [rbx]
0x180004d84  lea     r8, [rbp+arg_0]
0x180004d88  lea     rdx, _GUID_df2bf0e5_8012_4737_ae4c_28272f66c9f7
0x180004d8f  mov     [rbp+arg_0], r15
0x180004d93  mov     rcx, rbx
0x180004d96  mov     rax, [rax]
0x180004d99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d9e  mov     r14d, eax
0x180004da1  test    eax, eax
0x180004da3  js      short loc_180004E18
0x180004da5  mov     rsi, [rbp+arg_0]
0x180004da9  test    rsi, rsi
0x180004dac  jz      short loc_180004E1D
0x180004dae  mov     ecx, 18h; Size
0x180004db3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004db8  mov     rbx, rax
0x180004dbb  test    rax, rax
0x180004dbe  jz      short loc_180004E05
0x180004dc0  mov     [rax+8], r15
0x180004dc4  mov     [rax+10h], r15
0x180004dc8  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x180004dcf  mov     [rbx], rax
0x180004dd2  mov     dword ptr [rbx+8], 1
0x180004dd9  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x180004dde  mov     [rbx+10h], r15
0x180004de2  lea     rax, ??_7BooleanExpressionWrapper@@6B@; const BooleanExpressionWrapper::`vftable'
0x180004de9  lea     rcx, [rbx+10h]; struct IUnknown **
0x180004ded  mov     [rbx], rax
0x180004df0  cmp     [rcx], rsi
0x180004df3  jz      short loc_180004DFD
0x180004df5  mov     rdx, rsi; struct IUnknown *
0x180004df8  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180004dfd  mov     [rdi], rbx
0x180004e00  mov     ebx, r15d
0x180004e03  jmp     short loc_180004E0A
0x180004e05  mov     ebx, 8007000Eh
0x180004e0a  lea     rcx, [rbp+arg_0]
0x180004e0e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180004e13  jmp     loc_180005045
0x180004e18  cmp     r14d, esi
0x180004e1b  jz      short loc_180004E2E
0x180004e1d  lea     rcx, [rbp+arg_0]
0x180004e21  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180004e26  mov     ebx, r14d
0x180004e29  jmp     loc_180005045
0x180004e2e  mov     rax, [rbx]
0x180004e31  lea     r8, [rbp+arg_10]
0x180004e35  lea     rdx, _GUID_fe11aa2c_6109_4ebc_a14b_d8cf77a4998f
0x180004e3c  mov     [rbp+arg_10], r15
0x180004e40  mov     rcx, rbx
0x180004e43  mov     rax, [rax]
0x180004e46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e4b  mov     r14d, eax
0x180004e4e  test    eax, eax
0x180004e50  js      short loc_180004EC5
0x180004e52  mov     rsi, [rbp+arg_10]
0x180004e56  test    rsi, rsi
0x180004e59  jz      short loc_180004ECA
0x180004e5b  mov     ecx, 18h; Size
0x180004e60  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004e65  mov     rbx, rax
0x180004e68  test    rax, rax
0x180004e6b  jz      short loc_180004EB2
0x180004e6d  mov     [rax+8], r15
0x180004e71  mov     [rax+10h], r15
0x180004e75  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x180004e7c  mov     [rbx], rax
0x180004e7f  mov     dword ptr [rbx+8], 1
0x180004e86  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x180004e8b  mov     [rbx+10h], r15
0x180004e8f  lea     rax, ??_7NumberExpressionWrapper@@6B@; const NumberExpressionWrapper::`vftable'
0x180004e96  lea     rcx, [rbx+10h]; struct IUnknown **
0x180004e9a  mov     [rbx], rax
0x180004e9d  cmp     [rcx], rsi
0x180004ea0  jz      short loc_180004EAA
0x180004ea2  mov     rdx, rsi; struct IUnknown *
0x180004ea5  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180004eaa  mov     [rdi], rbx
0x180004ead  mov     ebx, r15d
0x180004eb0  jmp     short loc_180004EB7
0x180004eb2  mov     ebx, 8007000Eh
0x180004eb7  lea     rcx, [rbp+arg_10]
0x180004ebb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180004ec0  jmp     loc_180004E0A
0x180004ec5  cmp     r14d, esi
0x180004ec8  jz      short loc_180004ED8
0x180004eca  lea     rcx, [rbp+arg_10]
0x180004ece  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180004ed3  jmp     loc_180004E1D
0x180004ed8  mov     rax, [rbx]
0x180004edb  lea     r8, [rbp+arg_18]
0x180004edf  lea     rdx, _GUID_7eb4b748_fa54_466b_b59c_86245f6af2bf
0x180004ee6  mov     [rbp+arg_18], r15
0x180004eea  mov     rcx, rbx
0x180004eed  mov     rax, [rax]
0x180004ef0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ef5  mov     r14d, eax
0x180004ef8  test    eax, eax
0x180004efa  js      short loc_180004F6F
0x180004efc  mov     rsi, [rbp+arg_18]
0x180004f00  test    rsi, rsi
0x180004f03  jz      short loc_180004F74
0x180004f05  mov     ecx, 18h; Size
0x180004f0a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004f0f  mov     rbx, rax
0x180004f12  test    rax, rax
0x180004f15  jz      short loc_180004F5C
0x180004f17  mov     [rax+8], r15
0x180004f1b  mov     [rax+10h], r15
0x180004f1f  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x180004f26  mov     [rbx], rax
0x180004f29  mov     dword ptr [rbx+8], 1
0x180004f30  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x180004f35  mov     [rbx+10h], r15
0x180004f39  lea     rax, ??_7StringExpressionWrapper@@6B@; const StringExpressionWrapper::`vftable'
0x180004f40  lea     rcx, [rbx+10h]; struct IUnknown **
0x180004f44  mov     [rbx], rax
0x180004f47  cmp     [rcx], rsi
0x180004f4a  jz      short loc_180004F54
0x180004f4c  mov     rdx, rsi; struct IUnknown *
0x180004f4f  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180004f54  mov     [rdi], rbx
0x180004f57  mov     ebx, r15d
0x180004f5a  jmp     short loc_180004F61
0x180004f5c  mov     ebx, 8007000Eh
0x180004f61  lea     rcx, [rbp+arg_18]
0x180004f65  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180004f6a  jmp     loc_180004EB7
0x180004f6f  cmp     r14d, esi
0x180004f72  jz      short loc_180004F82
0x180004f74  lea     rcx, [rbp+arg_18]
0x180004f78  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180004f7d  jmp     loc_180004ECA
0x180004f82  mov     rax, [rbx]
0x180004f85  lea     r8, [rbp+var_10]
0x180004f89  lea     rdx, _GUID_69010634_90e9_4e24_9568_083801973afb
0x180004f90  mov     [rbp+var_10], r15
0x180004f94  mov     rcx, rbx
0x180004f97  mov     rax, [rax]
0x180004f9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f9f  mov     ebx, eax
0x180004fa1  test    eax, eax
0x180004fa3  js      short loc_180005018
0x180004fa5  mov     rsi, [rbp+var_10]
0x180004fa9  test    rsi, rsi
0x180004fac  jz      short loc_18000500A
0x180004fae  mov     ecx, 18h; Size
0x180004fb3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004fb8  mov     rbx, rax
0x180004fbb  test    rax, rax
0x180004fbe  jz      short loc_180005005
0x180004fc0  mov     [rax+8], r15
0x180004fc4  mov     [rax+10h], r15
0x180004fc8  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x180004fcf  mov     [rbx], rax
0x180004fd2  mov     dword ptr [rbx+8], 1
0x180004fd9  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x180004fde  mov     [rbx+10h], r15
0x180004fe2  lea     rax, ??_7CustomExpressionWrapper@@6B@; const CustomExpressionWrapper::`vftable'
0x180004fe9  lea     rcx, [rbx+10h]; struct IUnknown **
0x180004fed  mov     [rbx], rax
0x180004ff0  cmp     [rcx], rsi
0x180004ff3  jz      short loc_180004FFD
0x180004ff5  mov     rdx, rsi; struct IUnknown *
0x180004ff8  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180004ffd  mov     [rdi], rbx
0x180005000  mov     ebx, r15d
0x180005003  jmp     short loc_18000500A
0x180005005  mov     ebx, 8007000Eh
0x18000500a  lea     rcx, [rbp+var_10]
0x18000500e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180005013  jmp     loc_180004F61
0x180005018  cmp     eax, esi
0x18000501a  jnz     short loc_18000500A
0x18000501c  lea     rcx, [rbp+var_10]
0x180005020  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180005025  lea     rcx, [rbp+arg_18]
0x180005029  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000502e  lea     rcx, [rbp+arg_10]
0x180005032  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180005037  lea     rcx, [rbp+arg_0]
0x18000503b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180005040  mov     ebx, 80070057h
0x180005045  lea     rcx, [rbp+var_8]
0x180005049  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000504e  mov     eax, ebx
0x180005050  mov     rbx, [rsp+30h+arg_8]
0x180005055  add     rsp, 30h
0x180005059  pop     r15
0x18000505b  pop     r14
0x18000505d  pop     rdi
0x18000505e  pop     rsi
0x18000505f  pop     rbp
0x180005060  retn
```
