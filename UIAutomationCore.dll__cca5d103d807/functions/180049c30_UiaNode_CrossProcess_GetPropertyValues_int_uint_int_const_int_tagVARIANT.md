# UiaNode::CrossProcess_GetPropertyValues(int,uint,int const *,int,tagVARIANT *)

- ea: `0x180049c30`
- end: `0x18004a4d7`
- name: `?CrossProcess_GetPropertyValues@UiaNode@@UEAAJHIPEBHHPEAUtagVARIANT@@@Z`
- size: `2215`
- prototype: `__int64 __fastcall(UiaNode *__hidden this, int, unsigned int, const int *, int, ICreateErrorInfo *pperrinfo)`
- caller_count: `5`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x180027750`
- `0x180046be0`
- `0x180049220`
- `0x180049918`
- `0x1800e1634`

## callees

- `0x18002f580`
- `0x180048ab0`
- `0x180049c30`
- `0x18004a5c0`
- `0x180093850`
- `0x1800bf47c`
- `0x1800c88bc`
- `0x1800cc400`
- `0x180133550`
- `0x1801e8344`
- `0x1801e88a0`
- `0x1802dd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049e39`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049e39`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049e69`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a1eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049e69`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a1eb`
- `OLEAUT32!__imp_VariantInit` at `0x180049d18`
- `OLEAUT32!__imp_VariantInit` at `0x180049d81`
- `OLEAUT32!__imp_VariantInit` at `0x180049d18`
- `OLEAUT32!__imp_VariantInit` at `0x180049d81`
- `OLEAUT32!__imp_VariantClear` at `0x180049ffa`
- `OLEAUT32!__imp_VariantClear` at `0x18004a068`
- `OLEAUT32!__imp_VariantClear` at `0x18004a098`
- `OLEAUT32!__imp_VariantClear` at `0x18004a3ad`
- `OLEAUT32!__imp_VariantClear` at `0x18004a3f5`
- `OLEAUT32!__imp_VariantClear` at `0x18004a418`
- `OLEAUT32!__imp_VariantClear` at `0x180049ffa`
- `OLEAUT32!__imp_VariantClear` at `0x18004a068`
- `OLEAUT32!__imp_VariantClear` at `0x18004a098`
- `OLEAUT32!__imp_VariantClear` at `0x18004a3ad`
- `OLEAUT32!__imp_VariantClear` at `0x18004a3f5`
- `OLEAUT32!__imp_VariantClear` at `0x18004a418`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18004a24c`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18004a24c`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x18004a20d`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x18004a20d`

## string_xrefs

- `0x18004a048`: `onecore\windows\accessibletech\uiautomationcore\uianode.cpp`
- `0x18004a15c`: `onecore\windows\accessibletech\uiautomationcore\uianode.cpp`
- `0x18004a2c4`: `onecore\windows\accessibletech\uiautomationcore\uianode.cpp`
- `0x18004a329`: `onecore\windows\accessibletech\uiautomationcore\uianode.cpp`
- `0x18004a38a`: `onecore\windows\accessibletech\uiautomationcore\uianode.cpp`
- `0x18004a3d5`: `onecore\windows\accessibletech\uiautomationcore\uianode.cpp`
- `0x18004a45e`: `onecore\windows\accessibletech\uiautomationcore\uianode.cpp`
- `0x18004a36b`: `onecore\windows\accessibletech\uiautomationcore\SmartPointers.h`
- `0x18004a43f`: `onecore\windows\accessibletech\uiautomationcore\SmartPointers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall UiaNode::CrossProcess_GetPropertyValues(
        UiaNode *this,
        unsigned int a2,
        unsigned int a3,
        const int *a4,
        int a5,
        ICreateErrorInfo *pperrinfo)
{
  unsigned __int64 v7; // rax
  void *v8; // rdi
  unsigned __int64 v9; // rax
  void *v10; // rsi
  unsigned int v11; // r13d
  unsigned __int64 v12; // rax
  struct tagVARIANT *v13; // r14
  unsigned int i; // r15d
  unsigned __int64 v15; // rax
  VARIANTARG *v16; // r12
  unsigned int k; // r15d
  __int64 v18; // rbx
  __int64 v19; // rcx
  ICreateErrorInfo *v20; // r8
  unsigned __int16 **v21; // rcx
  const int *v22; // rax
  int v23; // r15d
  int v24; // r15d
  GUID **v25; // r15
  UiaNode *v26; // rcx
  __int64 v27; // rax
  unsigned int n; // ebx
  UiaNode *v29; // rcx
  int v30; // eax
  unsigned int v31; // r15d
  __int64 v32; // r8
  __int64 v33; // rdx
  VARIANTARG *v34; // r9
  IRecordInfo *pRecInfo; // xmm1_8
  unsigned int v36; // edx
  __int64 v37; // r8
  ICreateErrorInfo *v38; // r11
  VARIANTARG *v39; // r9
  ICreateErrorInfo *v40; // rcx
  __int64 nn; // rbx
  __int64 ii; // rbx
  __int64 jj; // rbx
  __int64 v45; // r9
  __int64 v46; // rdx
  __int64 v47; // rdx
  void *v48; // rcx
  int ProviderInfoString; // eax
  IErrorInfo *v50; // rax
  IErrorInfo *v51; // rbx
  struct UserDefinedPropertyInfo *m; // rax
  unsigned int j; // ebx
  __int64 kk; // rbx
  __int64 mm; // rbx
  int PropertyValues; // eax
  int v57; // [rsp+20h] [rbp-B8h]
  int v58; // [rsp+20h] [rbp-B8h]
  int v59; // [rsp+20h] [rbp-B8h]
  int v60; // [rsp+20h] [rbp-B8h]
  unsigned int v61; // [rsp+50h] [rbp-88h]
  unsigned __int16 **v62; // [rsp+58h] [rbp-80h]
  __int64 v63; // [rsp+58h] [rbp-80h]
  const int *v64; // [rsp+60h] [rbp-78h]
  unsigned int v65; // [rsp+78h] [rbp-60h] BYREF
  VARIANTARG *v66; // [rsp+80h] [rbp-58h]
  unsigned int v67; // [rsp+88h] [rbp-50h] BYREF
  struct tagVARIANT *v68; // [rsp+90h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  if ( !pperrinfo )
  {
    Error::SetError(L"Param must not be null", 0);
    return 2147942487LL;
  }
  v7 = 8LL * a3;
  if ( !is_mul_ok(a3, 8u) )
    v7 = -1;
  v8 = operator new[](v7, (const struct std::nothrow_t *)std::nothrow);
  if ( !v8 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A5,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianode.cpp",
      (const char *)0x8007000ELL,
      v57);
    operator delete(0);
    return 2147942414LL;
  }
  v9 = 4LL * a3;
  if ( !is_mul_ok(a3, 4u) )
    v9 = -1;
  v10 = operator new[](v9, (const struct std::nothrow_t *)std::nothrow);
  if ( !v10 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A7,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianode.cpp",
      (const char *)0x8007000ELL,
      v57);
    v48 = 0;
LABEL_69:
    operator delete(v48);
    operator delete(v8);
    return 2147942414LL;
  }
  v11 = 0;
  v67 = 0;
  v12 = 24LL * a3;
  if ( !is_mul_ok(a3, 0x18u) )
    v12 = -1;
  v13 = (struct tagVARIANT *)operator new[](v12, (const struct std::nothrow_t *)std::nothrow);
  v68 = v13;
  if ( !v13 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x234,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\SmartPointers.h",
      (const char *)0x8007000ELL,
      v57);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A9,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianode.cpp",
      (const char *)0x8007000ELL,
      v59);
    v48 = v10;
    goto LABEL_69;
  }
  for ( i = 0; i < a3; ++i )
  {
    VariantInit(&v13[i]);
    v13[i].llVal = 0;
  }
  v67 = a3;
  v65 = 0;
  v15 = 24LL * a3;
  if ( !is_mul_ok(a3, 0x18u) )
    v15 = -1;
  v16 = (VARIANTARG *)operator new[](v15, (const struct std::nothrow_t *)std::nothrow);
  v66 = v16;
  if ( !v16 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x234,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\SmartPointers.h",
      (const char *)0x8007000ELL,
      v57);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2AC,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianode.cpp",
      (const char *)0x8007000ELL,
      v58);
    for ( j = 0; j < a3; ++j )
      VariantClear(&v13[j]);
    operator delete(v13);
    v48 = v10;
    goto LABEL_69;
  }
  for ( k = 0; k < a3; ++k )
  {
    VariantInit(&v16[k]);
    v16[k].llVal = 0;
  }
  v65 = a3;
  v61 = 0;
  v18 = 0;
  while ( (unsigned int)v18 < a3 )
  {
    v19 = 3 * v18;
    v20 = pperrinfo;
    LOWORD(pperrinfo[v19].lpVtbl) = 13;
    v20[v19 + 1].lpVtbl = (struct ICreateErrorInfoVtbl *)g_punkNotSupportedValue;
    v21 = (unsigned __int16 **)&v16[v18];
    v62 = v21;
    *(_WORD *)v21 = 0;
    v22 = &a4[v18];
    v64 = v22;
    v23 = *v22;
    if ( *v22 == 30107 )
    {
      ProviderInfoString = UiaNode::GetProviderInfoString((UiaNode *)((char *)this - 48), v21 + 1);
      v31 = ProviderInfoString;
      if ( ProviderInfoString < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2BD,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianode.cpp",
          (const char *)(unsigned int)ProviderInfoString,
          v57);
        StructArrayPair<tagVARIANT>::SafeRelease(&v65);
        StructArrayPair<tagVARIANT>::SafeRelease(&v67);
LABEL_57:
        operator delete(v10);
        operator delete(v8);
        return v31;
      }
      *(_WORD *)v62 = 8;
      v18 = (unsigned int)(v18 + 1);
    }
    else
    {
      if ( v23 == 30008 )
      {
        v47 = *((_QWORD *)this + 26);
        if ( v47 && *(_QWORD *)(v47 + 64) )
        {
          *(_WORD *)v21 = 11;
          *((_WORD *)v21 + 4) = 0;
          goto LABEL_28;
        }
      }
      else if ( v23 == 30020 )
      {
        if ( UiaNode::IsCrossMachine(this) )
        {
          *(_WORD *)v62 = 13;
          v62[1] = (unsigned __int16 *)g_punkNotSupportedValue;
          goto LABEL_28;
        }
        v22 = v64;
      }
      *((_DWORD *)v10 + v11) = v23;
      v24 = *v22;
      if ( *v22 )
      {
        EnterCriticalSection(&_schemaLock);
        if ( (unsigned int)(v24 - 30000) > 0xAF )
        {
          for ( m = g_pUserDefinedProperties; ; m = *(struct UserDefinedPropertyInfo **)m )
          {
            if ( !m )
            {
              LeaveCriticalSection(&_schemaLock);
              *((_QWORD *)v8 + v11) = 0;
              goto LABEL_75;
            }
            if ( *((_DWORD *)m + 6) == v24 )
              break;
          }
          v25 = (GUID **)((char *)m + 16);
        }
        else
        {
          v25 = &(&off_1802DE930)[8 * (unsigned __int64)(unsigned int)(v24 - 30000)];
        }
        LeaveCriticalSection(&_schemaLock);
        *((_QWORD *)v8 + v11) = v25;
        if ( !v25 )
        {
LABEL_75:
          pperrinfo = 0;
          if ( CreateErrorInfo(&pperrinfo) >= 0 )
          {
            ((void (__fastcall *)(ICreateErrorInfo *, const unsigned __int16 *))pperrinfo->lpVtbl->SetDescription)(
              pperrinfo,
              L"Unknown property ID");
            v50 = (IErrorInfo *)QI<IErrorInfo>(pperrinfo);
            v51 = v50;
            if ( v50 )
              SetErrorInfo(0, v50);
            if ( v51 )
              ((void (__fastcall *)(IErrorInfo *))v51->lpVtbl->Release)(v51);
          }
          if ( pperrinfo )
            ((void (__fastcall *)(ICreateErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
          StructArrayPair<tagVARIANT>::SafeRelease(&v65);
          StructArrayPair<tagVARIANT>::SafeRelease(&v67);
          operator delete(v10);
          operator delete(v8);
          return 2147942487LL;
        }
      }
      else
      {
        *((_QWORD *)v8 + v11) = 0;
      }
      v11 = ++v61;
LABEL_28:
      v18 = (unsigned int)(v18 + 1);
    }
  }
  v26 = this;
  v27 = *((_QWORD *)this + 27);
  v63 = v27;
  for ( n = 0; n < *((_DWORD *)v26 + 48); ++n )
  {
    if ( n )
    {
      v45 = 0;
      v46 = 0;
      if ( v11 )
      {
        do
        {
          if ( !v13[v46].vt )
          {
            *((_DWORD *)v10 + v45) = *((_DWORD *)v10 + v46);
            *((_QWORD *)v8 + v45) = *((_QWORD *)v8 + v46);
            v45 = (unsigned int)(v45 + 1);
          }
          v46 = (unsigned int)(v46 + 1);
        }
        while ( (unsigned int)v46 < v11 );
        v27 = v63;
        v26 = this;
      }
      v11 = v45;
      v61 = v45;
    }
    if ( !v11 )
      break;
    v29 = (UiaNode *)((char *)v26 - 48);
    if ( v27 )
    {
      v30 = InProcClientAPIStub::InvokeInProcAPI(v27, 9, v29, a2);
      v31 = v30;
      if ( v30 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x30F,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianode.cpp",
          (const char *)(unsigned int)v30,
          n);
        for ( ii = 0; (unsigned int)ii < a3; ii = (unsigned int)(ii + 1) )
          VariantClear(&v16[ii]);
        operator delete(v16);
        for ( jj = 0; (unsigned int)jj < a3; jj = (unsigned int)(jj + 1) )
          VariantClear(&v13[jj]);
LABEL_56:
        operator delete(v13);
        goto LABEL_57;
      }
    }
    else
    {
      PropertyValues = UiaNode::ProviderGetPropertyValues(
                         v29,
                         a2,
                         n,
                         v11,
                         (int *)v10,
                         (const struct PropertyInfo **)v8,
                         1,
                         v13);
      v31 = PropertyValues;
      if ( PropertyValues < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x313,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianode.cpp",
          (const char *)(unsigned int)PropertyValues,
          v60);
        for ( kk = 0; (unsigned int)kk < a3; kk = (unsigned int)(kk + 1) )
          VariantClear(&v16[kk]);
        operator delete(v16);
        for ( mm = 0; (unsigned int)mm < a3; mm = (unsigned int)(mm + 1) )
          VariantClear(&v13[mm]);
        goto LABEL_56;
      }
    }
    v32 = 0;
    v33 = 0;
    if ( a3 )
    {
      do
      {
        v34 = &v16[v33];
        if ( !v34->vt )
        {
          if ( v13[v32].vt )
          {
            pRecInfo = v13[v32].pRecInfo;
            *(_OWORD *)&v34->vt = *(_OWORD *)&v13[v32].vt;
            v34->pRecInfo = pRecInfo;
            v13[v32].vt = 3;
          }
          v32 = (unsigned int)(v32 + 1);
        }
        v33 = (unsigned int)(v33 + 1);
      }
      while ( (unsigned int)v33 < a3 );
      v11 = v61;
    }
    v27 = v63;
    v26 = this;
  }
  v36 = 0;
  if ( a3 )
  {
    v37 = 0;
    v38 = pperrinfo;
    do
    {
      v39 = &v16[v37];
      v40 = &v38[3 * v37];
      *(_OWORD *)&v40->lpVtbl = *(_OWORD *)&v39->vt;
      v40[2].lpVtbl = *(struct ICreateErrorInfoVtbl **)(&v39->decVal + 1);
      if ( !a5 && !LOWORD(v40->lpVtbl) )
      {
        LOWORD(v40->lpVtbl) = 13;
        v40[1].lpVtbl = (struct ICreateErrorInfoVtbl *)g_punkNotSupportedValue;
      }
      v39->vt = 0;
      ++v36;
      ++v37;
    }
    while ( v36 < a3 );
  }
  operator delete(v16);
  for ( nn = 0; (unsigned int)nn < a3; nn = (unsigned int)(nn + 1) )
    VariantClear(&v13[nn]);
  operator delete(v13);
  operator delete(v10);
  operator delete(v8);
  return 0;
}

```

## disassembly

```asm
0x180049c30  mov     [rsp+arg_10], rbx
0x180049c35  mov     [rsp+arg_18], r9
0x180049c3a  mov     [rsp+arg_8], edx
0x180049c3e  mov     [rsp+arg_0], rcx
0x180049c43  push    rbp
0x180049c44  push    rsi
0x180049c45  push    rdi
0x180049c46  push    r12
0x180049c48  push    r13
0x180049c4a  push    r14
0x180049c4c  push    r15
0x180049c4e  sub     rsp, 0A0h
0x180049c55  mov     ebp, r8d
0x180049c58  cmp     [rsp+0D8h+pperrinfo], 0
0x180049c61  jz      loc_18004A2E7
0x180049c67  mov     r12d, ebp
0x180049c6a  mov     eax, 8
0x180049c6f  mul     rbp
0x180049c72  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180049c79  cmovb   rax, rbx
0x180049c7d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180049c84  mov     rcx, rax; unsigned __int64
0x180049c87  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180049c8c  mov     rdi, rax
0x180049c8f  mov     [rsp+0D8h+var_70], rax
0x180049c94  test    rax, rax
0x180049c97  jz      loc_18004A2B6
0x180049c9d  mov     eax, 4
0x180049ca2  mul     r12
0x180049ca5  cmovb   rax, rbx
0x180049ca9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180049cb0  mov     rcx, rax; unsigned __int64
0x180049cb3  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180049cb8  mov     rsi, rax
0x180049cbb  mov     [rsp+0D8h+var_68], rax
0x180049cc0  test    rax, rax
0x180049cc3  jz      loc_18004A14E
0x180049cc9  xor     r13d, r13d
0x180049ccc  mov     [rsp+0D8h+var_50], r13d
0x180049cd4  mov     eax, 18h
0x180049cd9  mul     r12
0x180049cdc  cmovb   rax, rbx
0x180049ce0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180049ce7  mov     rcx, rax; unsigned __int64
0x180049cea  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180049cef  mov     r14, rax
0x180049cf2  mov     [rsp+0D8h+var_48], rax
0x180049cfa  test    rax, rax
0x180049cfd  jz      loc_18004A431
0x180049d03  mov     r15d, r13d
0x180049d06  test    ebp, ebp
0x180049d08  jz      short loc_180049D31
0x180049d0a  mov     eax, r15d
0x180049d0d  lea     rcx, [rax+rax*2]
0x180049d11  lea     rbx, [r14+rcx*8]
0x180049d15  mov     rcx, rbx; pvarg
0x180049d18  call    cs:__imp_VariantInit
0x180049d1e  mov     [rbx+8], r13
0x180049d22  inc     r15d
0x180049d25  cmp     r15d, ebp
0x180049d28  jb      short loc_180049D0A
0x180049d2a  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180049d31  mov     [rsp+0D8h+var_50], ebp
0x180049d38  mov     [rsp+0D8h+var_60], r13d
0x180049d3d  mov     eax, 18h
0x180049d42  mul     r12
0x180049d45  cmovb   rax, rbx
0x180049d49  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180049d50  mov     rcx, rax; unsigned __int64
0x180049d53  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180049d58  mov     r12, rax
0x180049d5b  mov     [rsp+0D8h+var_58], rax
0x180049d63  test    rax, rax
0x180049d66  jz      loc_18004A35D
0x180049d6c  mov     r15d, r13d
0x180049d6f  test    ebp, ebp
0x180049d71  jz      short loc_180049D93
0x180049d73  mov     eax, r15d
0x180049d76  lea     rcx, [rax+rax*2]
0x180049d7a  lea     rbx, [r12+rcx*8]
0x180049d7e  mov     rcx, rbx; pvarg
0x180049d81  call    cs:__imp_VariantInit
0x180049d87  mov     [rbx+8], r13
0x180049d8b  inc     r15d
0x180049d8e  cmp     r15d, ebp
0x180049d91  jb      short loc_180049D73
0x180049d93  mov     [rsp+0D8h+var_60], ebp
0x180049d97  mov     [rsp+0D8h+var_88], r13d
0x180049d9c  xor     ebx, ebx
0x180049d9e  mov     r15d, 0Dh
0x180049da4  mov     r9d, 0Bh
0x180049daa  cmp     ebx, ebp
0x180049dac  jnb     loc_180049E9C
0x180049db2  lea     rax, [rbx+rbx*2]
0x180049db6  lea     rcx, ds:0[rax*8]
0x180049dbe  mov     r8, [rsp+0D8h+pperrinfo]
0x180049dc6  mov     [rcx+r8], r15w
0x180049dcb  mov     rax, cs:?g_punkNotSupportedValue@@3PEAUIUnknown@@EA; IUnknown * g_punkNotSupportedValue
0x180049dd2  mov     [rcx+r8+8], rax
0x180049dd7  add     rcx, r12
0x180049dda  mov     [rsp+0D8h+var_80], rcx
0x180049ddf  xor     eax, eax
0x180049de1  mov     [rcx], ax
0x180049de4  mov     rax, [rsp+0D8h+arg_18]
0x180049dec  lea     rax, [rax+rbx*4]
0x180049df0  mov     [rsp+0D8h+var_78], rax
0x180049df5  mov     r15d, [rax]
0x180049df8  cmp     r15d, 759Bh
0x180049dff  jz      loc_18004A188
0x180049e05  cmp     r15d, 7538h
0x180049e0c  jz      loc_18004A11C
0x180049e12  cmp     r15d, 7544h
0x180049e19  jz      loc_18004A1C5
0x180049e1f  mov     r13d, r13d
0x180049e22  mov     [rsi+r13*4], r15d
0x180049e26  mov     r15d, [rax]
0x180049e29  test    r15d, r15d
0x180049e2c  jz      loc_18004A0C6
0x180049e32  lea     rcx, ?_schemaLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180049e39  call    cs:__imp_EnterCriticalSection
0x180049e3f  lea     eax, [r15-7530h]
0x180049e46  cmp     eax, 0AFh
0x180049e4b  ja      loc_18004A2FF
0x180049e51  mov     r15d, eax
0x180049e54  shl     r15, 6
0x180049e58  lea     rax, off_1802DE930
0x180049e5f  add     r15, rax
0x180049e62  lea     rcx, ?_schemaLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180049e69  call    cs:__imp_LeaveCriticalSection
0x180049e6f  mov     [rdi+r13*8], r15
0x180049e73  test    r15, r15
0x180049e76  jz      loc_18004A1F9
0x180049e7c  mov     r13d, [rsp+0D8h+var_88]
0x180049e81  inc     r13d
0x180049e84  mov     [rsp+0D8h+var_88], r13d
0x180049e89  mov     r9d, 0Bh
0x180049e8f  mov     r15d, 0Dh
0x180049e95  inc     ebx
0x180049e97  jmp     loc_180049DAA
0x180049e9c  mov     rcx, [rsp+0D8h+arg_0]
0x180049ea4  mov     rax, [rcx+0D8h]
0x180049eab  mov     [rsp+0D8h+var_80], rax
0x180049eb0  xor     ebx, ebx
0x180049eb2  cmp     ebx, [rcx+0C0h]
0x180049eb8  jnb     loc_180049F82
0x180049ebe  test    ebx, ebx
0x180049ec0  jnz     loc_18004A0D3
0x180049ec6  test    r13d, r13d
0x180049ec9  jz      loc_180049F82
0x180049ecf  add     rcx, 0FFFFFFFFFFFFFFD0h; this
0x180049ed3  test    rax, rax
0x180049ed6  jz      loc_18004A49D
0x180049edc  mov     [rsp+0D8h+var_90], r14
0x180049ee1  mov     [rsp+0D8h+var_98], 1
0x180049ee9  mov     [rsp+0D8h+var_A0], rdi
0x180049eee  mov     qword ptr [rsp+0D8h+var_A8], rsi
0x180049ef3  mov     dword ptr [rsp+0D8h+var_B0], r13d
0x180049ef8  mov     dword ptr [rsp+0D8h+var_B8], ebx; int
0x180049efc  mov     r9d, [rsp+0D8h+arg_8]
0x180049f04  mov     r8, rcx
0x180049f07  mov     edx, 9
0x180049f0c  mov     rcx, rax
0x180049f0f  call    ?InvokeInProcAPI@InProcClientAPIStub@@SAJPEAUITargetContextInvoker@@W4Protocol_MethodId@@ZZ; InProcClientAPIStub::InvokeInProcAPI(ITargetContextInvoker *,Protocol_MethodId,...)
0x180049f14  mov     r15d, eax
0x180049f17  test    eax, eax
0x180049f19  js      loc_18004A03D
0x180049f1f  xor     r8d, r8d
0x180049f22  xor     edx, edx
0x180049f24  test    ebp, ebp
0x180049f26  jz      short loc_180049F6E
0x180049f28  lea     rcx, [rdx+rdx*2]
0x180049f2c  lea     r9, [r12+rcx*8]
0x180049f30  cmp     word ptr [r9], 0
0x180049f35  jnz     short loc_180049F63
0x180049f37  lea     rcx, [r8+r8*2]
0x180049f3b  cmp     word ptr [r14+rcx*8], 0
0x180049f41  jz      short loc_180049F60
0x180049f43  movups  xmm0, xmmword ptr [r14+rcx*8]
0x180049f48  movsd   xmm1, qword ptr [r14+rcx*8+10h]
0x180049f4f  movups  xmmword ptr [r9], xmm0
0x180049f53  movsd   qword ptr [r9+10h], xmm1
0x180049f59  mov     word ptr [r14+rcx*8], 3
0x180049f60  inc     r8d
0x180049f63  inc     edx
0x180049f65  cmp     edx, ebp
0x180049f67  jb      short loc_180049F28
0x180049f69  mov     r13d, [rsp+0D8h+var_88]
0x180049f6e  inc     ebx
0x180049f70  mov     rax, [rsp+0D8h+var_80]
0x180049f75  mov     rcx, [rsp+0D8h+arg_0]
0x180049f7d  jmp     loc_180049EB2
0x180049f82  xor     edx, edx
0x180049f84  test    ebp, ebp
0x180049f86  jz      short loc_180049FE3
0x180049f88  xor     r8d, r8d
0x180049f8b  mov     r10d, [rsp+0D8h+arg_20]
0x180049f93  mov     r11, [rsp+0D8h+pperrinfo]
0x180049f9b  lea     rax, [r8+r8*2]
0x180049f9f  lea     r9, [r12+rax*8]
0x180049fa3  lea     rcx, [r11+rax*8]
0x180049fa7  movups  xmm0, xmmword ptr [r9]
0x180049fab  movups  xmmword ptr [rcx], xmm0
0x180049fae  movsd   xmm1, qword ptr [r9+10h]
0x180049fb4  movsd   qword ptr [rcx+10h], xmm1
0x180049fb9  test    r10d, r10d
0x180049fbc  jnz     short loc_180049FD4
0x180049fbe  cmp     [rcx], r10w
0x180049fc2  jnz     short loc_180049FD4
0x180049fc4  mov     word ptr [rcx], 0Dh
0x180049fc9  mov     rax, cs:?g_punkNotSupportedValue@@3PEAUIUnknown@@EA; IUnknown * g_punkNotSupportedValue
0x180049fd0  mov     [rcx+8], rax
0x180049fd4  xor     eax, eax
0x180049fd6  mov     [r9], ax
0x180049fda  inc     edx
0x180049fdc  inc     r8
0x180049fdf  cmp     edx, ebp
0x180049fe1  jb      short loc_180049F9B
0x180049fe3  mov     rcx, r12; Block
0x180049fe6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180049feb  nop
0x180049fec  xor     ebx, ebx
0x180049fee  test    ebp, ebp
0x180049ff0  jz      short loc_18004A006
0x180049ff2  lea     rcx, [rbx+rbx*2]
0x180049ff6  lea     rcx, [r14+rcx*8]; pvarg
0x180049ffa  call    cs:__imp_VariantClear
0x18004a000  inc     ebx
0x18004a002  cmp     ebx, ebp
0x18004a004  jb      short loc_180049FF2
0x18004a006  mov     rcx, r14; Block
0x18004a009  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004a00e  nop
0x18004a00f  mov     rcx, rsi; Block
0x18004a012  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004a017  nop
0x18004a018  mov     rcx, rdi; Block
0x18004a01b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004a020  xor     eax, eax
0x18004a022  mov     rbx, [rsp+0D8h+arg_10]
0x18004a02a  add     rsp, 0A0h
0x18004a031  pop     r15
0x18004a033  pop     r14
0x18004a035  pop     r13
0x18004a037  pop     r12
0x18004a039  pop     rdi
0x18004a03a  pop     rsi
0x18004a03b  pop     rbp
0x18004a03c  retn
0x18004a03d  mov     rcx, [rsp+0D8h]; this
0x18004a045  mov     r9d, r15d; char *
0x18004a048  lea     r8, aOnecoreWindows_137; "onecore\\windows\\accessibletech\\uiaut"...
0x18004a04f  mov     edx, 30Fh; void *
0x18004a054  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a059  nop
0x18004a05a  xor     ebx, ebx
0x18004a05c  test    ebp, ebp
0x18004a05e  jz      short loc_18004A074
0x18004a060  lea     rcx, [rbx+rbx*2]
0x18004a064  lea     rcx, [r12+rcx*8]; pvarg
0x18004a068  call    cs:__imp_VariantClear
0x18004a06e  inc     ebx
0x18004a070  cmp     ebx, ebp
0x18004a072  jb      short loc_18004A060
0x18004a074  mov     rcx, r12; Block
0x18004a077  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004a07c  nop
0x18004a07d  xor     ebx, ebx
0x18004a07f  test    ebp, ebp
0x18004a081  jz      short loc_18004A0A4
0x18004a083  nop     dword ptr [rax+00h]
0x18004a087  nop     word ptr [rax+rax+00000000h]
0x18004a090  lea     rcx, [rbx+rbx*2]
0x18004a094  lea     rcx, [r14+rcx*8]; pvarg
0x18004a098  call    cs:__imp_VariantClear
0x18004a09e  inc     ebx
0x18004a0a0  cmp     ebx, ebp
0x18004a0a2  jb      short loc_18004A090
0x18004a0a4  mov     rcx, r14; Block
0x18004a0a7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004a0ac  nop
0x18004a0ad  mov     rcx, rsi; Block
0x18004a0b0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004a0b5  nop
0x18004a0b6  mov     rcx, rdi; Block
0x18004a0b9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004a0be  mov     eax, r15d
0x18004a0c1  jmp     loc_18004A022
0x18004a0c6  mov     qword ptr [rdi+r13*8], 0
0x18004a0ce  jmp     loc_180049E7C
0x18004a0d3  xor     r9d, r9d
0x18004a0d6  xor     edx, edx
0x18004a0d8  test    r13d, r13d
0x18004a0db  jz      short loc_18004A10F
0x18004a0dd  lea     rax, [rdx+rdx*2]
0x18004a0e1  cmp     word ptr [r14+rax*8], 0
0x18004a0e7  jnz     short loc_18004A0FB
0x18004a0e9  mov     eax, [rsi+rdx*4]
0x18004a0ec  mov     [rsi+r9*4], eax
0x18004a0f0  mov     rax, [rdi+rdx*8]
0x18004a0f4  mov     [rdi+r9*8], rax
  ... truncated ...
```
