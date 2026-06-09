# COpenSearchRowset::_InitializeRowset(ushort const *,ushort const *,IOpenSearchSource *)

- ea: `0x180044618`
- end: `0x180044c4d`
- name: `?_InitializeRowset@COpenSearchRowset@@AEAAJPEBG0PEAUIOpenSearchSource@@@Z`
- size: `1589`
- prototype: `__int64 __fastcall(COpenSearchRowset *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct IOpenSearchSource *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180047ba8`

## callees

- `0x1800054b0`
- `0x180005c88`
- `0x180006900`
- `0x1800120a4`
- `0x1800129ec`
- `0x1800129f8`
- `0x180021e64`
- `0x180024b88`
- `0x18003d744`
- `0x18003d7c4`
- `0x18003d82c`
- `0x1800418bc`
- `0x180044618`
- `0x180049188`
- `0x180049504`
- `0x180051010`

## import_xrefs

- `SHCORE!__imp_GUIDFromStringW` at `0x180044821`
- `SHCORE!__imp_GUIDFromStringW` at `0x180044821`
- `SHELL32!__imp_SHCoCreateInstance` at `0x1800446d5`
- `SHELL32!__imp_SHCoCreateInstance` at `0x1800446d5`
- `SHELL32!__imp_SHExtCoCreateInstance` at `0x180044854`
- `SHELL32!__imp_SHExtCoCreateInstance` at `0x180044854`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004495c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800449b7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180044a81`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180044afa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180044b46`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180044b50`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180044b5a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004495c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800449b7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180044a81`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180044afa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180044b46`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180044b50`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180044b5a`
- `PROPSYS!PropVariantToUInt32` at `0x180044950`
- `PROPSYS!PropVariantToUInt32` at `0x1800449ab`
- `PROPSYS!PropVariantToUInt32` at `0x180044a77`
- `PROPSYS!PropVariantToUInt32` at `0x180044af0`
- `PROPSYS!PropVariantToUInt32` at `0x180044950`
- `PROPSYS!PropVariantToUInt32` at `0x1800449ab`
- `PROPSYS!PropVariantToUInt32` at `0x180044a77`
- `PROPSYS!PropVariantToUInt32` at `0x180044af0`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180044b6e`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180044b6e`

## string_xrefs

- `0x180044760`: `OpenSearchListTemplate`
- `0x1800446f9`: `OpenSearchQueryTemplate`
- `0x1800449e7`: `LinkIsFilePath`
- `0x1800447f5`: `DataSourceCLSID`
- `0x180044a02`: `AllowLocalXmlFile`

## pseudocode

```c
__int64 __fastcall COpenSearchRowset::_InitializeRowset(
        COpenSearchRowset *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct IOpenSearchSource *a4)
{
  struct COpenSearchPropertyMap **v7; // rax
  __int64 v8; // rdx
  _WORD *v9; // rcx
  HRESULT Instance; // ebx
  int v11; // r8d
  int v12; // r9d
  const wchar_t **v13; // r13
  _QWORD *v14; // r15
  __int64 **v15; // rsi
  _QWORD *v16; // r12
  _QWORD *v17; // rbx
  int v18; // ebx
  _QWORD *v19; // rbx
  __int64 (__fastcall ***v20)(_QWORD, GUID *, __int64 *); // rax
  __int64 *v21; // rcx
  _DWORD *v22; // r14
  __int64 v23; // rax
  HRESULT v24; // ebx
  __int64 *v25; // rcx
  __int64 *v26; // r14
  __int64 v27; // rax
  HRESULT v28; // ebx
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // r8
  __int64 *v32; // rcx
  __int64 *v33; // rcx
  __int64 v34; // rax
  __int64 *v35; // rcx
  __int64 *v36; // rcx
  __int64 v37; // rax
  __int64 *v38; // rcx
  const wchar_t *v39; // r8
  const wchar_t *v40; // rax
  PROPVARIANT propvarIn[2]; // [rsp+40h] [rbp-69h] BYREF
  __int64 v43; // [rsp+50h] [rbp-59h]
  __int64 v44; // [rsp+58h] [rbp-51h] BYREF
  __int64 v45; // [rsp+60h] [rbp-49h] BYREF
  const unsigned __int16 *v46; // [rsp+68h] [rbp-41h]
  PROPVARIANT v47[2]; // [rsp+70h] [rbp-39h] BYREF
  __int64 v48; // [rsp+80h] [rbp-29h]
  PROPVARIANT v49[2]; // [rsp+88h] [rbp-21h] BYREF
  __int64 v50; // [rsp+98h] [rbp-11h]
  PROPVARIANT pvar[2]; // [rsp+A0h] [rbp-9h] BYREF
  __int64 v52; // [rsp+B0h] [rbp+7h]

  v46 = a3;
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      (_DWORD)this,
      (unsigned int)OpenSearch_RowsetInitialize_Start,
      (_DWORD)a3,
      (_DWORD)a4,
      (__int64)pvar);
  SHTraceSQMCount((const struct _EVENT_DESCRIPTOR *)this, (unsigned int)a2);
  v7 = (struct COpenSearchPropertyMap **)ATL::CComPtrBase<IXMLDOMDocument>::operator&((char *)this + 840);
  Instance = COpenSearchPropertyMap::CreateInstance(v7);
  if ( Instance < 0 )
    goto LABEL_65;
  v13 = (const wchar_t **)((char *)this + 768);
  if ( a2 )
  {
    Instance = _AllocString<CTCoAllocPolicy>(v9, v8, a2, (char *)this + 768);
    if ( Instance < 0 )
      goto LABEL_65;
  }
  else
  {
    *v13 = 0;
  }
  v14 = (_QWORD *)((char *)this + 848);
  Instance = SHCoCreateInstance(
               0,
               &CLSID_SecurityZoneChecker,
               0,
               &GUID_7822aba1_e0e5_4e1a_b405_a363ca5d67ac,
               (void **)this + 106);
  if ( Instance < 0 )
    goto LABEL_65;
  v15 = (__int64 **)((char *)this + 816);
  v16 = (_QWORD *)((char *)this + 752);
  if ( (int)INamedPropertyStore_GetString(*((_QWORD *)this + 102), L"OpenSearchQueryTemplate", (char *)this + 752) >= 0
    && *(_WORD *)*v16
    && (*(unsigned int (__fastcall **)(_QWORD, _QWORD, __int64, __int64, _QWORD, _QWORD, char *))(*(_QWORD *)*v14 + 24LL))(
         *v14,
         *v16,
         6158,
         1,
         0,
         0,
         (char *)this + 856) )
  {
    *((_DWORD *)this + 26) = 1;
  }
  if ( !*((_DWORD *)this + 26) )
  {
    v17 = (_QWORD *)((char *)this + 760);
    if ( (int)INamedPropertyStore_GetString(*v15, L"OpenSearchListTemplate", (char *)this + 760) >= 0
      && *(_WORD *)*v17
      && (*(unsigned int (__fastcall **)(_QWORD, _QWORD, __int64, __int64, _QWORD, _QWORD, char *))(*(_QWORD *)*v14
                                                                                                  + 24LL))(
           *v14,
           *v17,
           6158,
           1,
           0,
           0,
           (char *)this + 856) )
    {
      *((_DWORD *)this + 26) = 1;
    }
  }
  if ( a4 )
  {
    *((_DWORD *)this + 18) = 0;
    v18 = ((__int64 (__fastcall *)(struct IOpenSearchSource *, GUID *, char *))a4->lpVtbl->QueryInterface)(
            a4,
            &GUID_f0ee7333_e6fc_479b_9f25_a860c234a38e,
            (char *)this + 808);
    goto LABEL_29;
  }
  v19 = (_QWORD *)((char *)this + 800);
  if ( (int)INamedPropertyStore_GetString(*v15, L"DataSourceCLSID", (char *)this + 800) >= 0 )
  {
    v9 = (_WORD *)*v19;
    if ( *(_WORD *)*v19 )
    {
      *(_OWORD *)pvar = 0;
      if ( !(unsigned int)GUIDFromStringW(v9, pvar) )
        goto LABEL_33;
      v18 = SHExtCoCreateInstance(pvar, 0, 4);
      if ( v18 < 0 )
        goto LABEL_33;
      *((_DWORD *)this + 18) = 0;
      ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v45);
      if ( (***((int (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 101))(
             *((_QWORD *)this + 101),
             &GUID_c3e12eb5_7d8d_44f8_b6dd_0e77b34d6de4,
             &v45) >= 0 )
      {
        ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v44);
        v20 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))ATL::CComPtrBase<IStartMenuResultSetInternal>::operator->((char *)this + 816);
        v18 = (**v20)(v20, &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &v44);
        if ( v18 >= 0 )
          v18 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v45 + 24LL))(v45, v44);
        ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(&v44);
      }
      ATL::CComPtr<CPropertyMapTable>::~CComPtr<CPropertyMapTable>(&v45);
LABEL_29:
      if ( v18 < 0 )
      {
LABEL_33:
        Instance = -2147467259;
        goto LABEL_65;
      }
    }
  }
  if ( !*(_WORD *)*v16 && !**((_WORD **)this + 95) && !*((_QWORD *)this + 101) )
    goto LABEL_33;
  v21 = *v15;
  v22 = (_DWORD *)((char *)this + 52);
  *((_DWORD *)this + 13) = 0;
  v43 = 0;
  v23 = *v21;
  *(_OWORD *)propvarIn = 0;
  if ( (*(int (__fastcall **)(__int64 *, const wchar_t *, PROPVARIANT *))(v23 + 24))(
         v21,
         L"PreferredPageSize",
         propvarIn) >= 0 )
  {
    v24 = PropVariantToUInt32(propvarIn, (ULONG *)this + 13);
    PropVariantClear(propvarIn);
    if ( v24 >= 0 && !*v22 )
      *v22 = 50;
  }
  v25 = *v15;
  v26 = (__int64 *)((char *)this + 64);
  *((_DWORD *)this + 16) = 0;
  v43 = 0;
  v27 = *v25;
  *(_OWORD *)propvarIn = 0;
  if ( (*(int (__fastcall **)(__int64 *, const wchar_t *, PROPVARIANT *))(v27 + 24))(
         v25,
         L"MaximumResultCount",
         propvarIn) >= 0 )
  {
    v28 = PropVariantToUInt32(propvarIn, (ULONG *)this + 16);
    PropVariantClear(propvarIn);
    if ( v28 >= 0 )
    {
      v29 = *v26;
      if ( *v26 >= 1 )
      {
        if ( v29 >= 5000 )
          v29 = 5000;
      }
      else
      {
        v29 = 100;
      }
      *v26 = v29;
    }
  }
  INamedPropertyStore_GetBool(*v15, L"LinkIsFilePath", (char *)this + 76);
  v30 = ATL::CComPtrBase<IStartMenuResultSetInternal>::operator->((char *)this + 816);
  INamedPropertyStore_GetBool(v30, L"AllowLocalXmlFile", v31);
  v32 = *v15;
  v50 = 0;
  *(_OWORD *)v49 = 0;
  if ( (*(int (__fastcall **)(__int64 *, const wchar_t *, PROPVARIANT *))(*v32 + 24))(v32, L"BaseStartIndex", v49) >= 0 )
  {
    if ( LOWORD(v49[0]) )
    {
      v33 = *v15;
      *((_DWORD *)this + 14) = 0;
      v43 = 0;
      v34 = *v33;
      *(_OWORD *)propvarIn = 0;
      if ( (*(int (__fastcall **)(__int64 *, const wchar_t *, PROPVARIANT *))(v34 + 24))(
             v33,
             L"BaseStartIndex",
             propvarIn) >= 0 )
      {
        PropVariantToUInt32(propvarIn, (ULONG *)this + 14);
        PropVariantClear(propvarIn);
      }
    }
  }
  v35 = *v15;
  v48 = 0;
  *(_OWORD *)v47 = 0;
  if ( (*(int (__fastcall **)(__int64 *, const wchar_t *, PROPVARIANT *))(*v35 + 24))(v35, L"BaseStartPage", v47) >= 0 )
  {
    if ( LOWORD(v47[0]) )
    {
      v36 = *v15;
      *((_DWORD *)this + 15) = 0;
      v43 = 0;
      v37 = *v36;
      *(_OWORD *)propvarIn = 0;
      if ( (*(int (__fastcall **)(__int64 *, const wchar_t *, PROPVARIANT *))(v37 + 24))(
             v36,
             L"BaseStartPage",
             propvarIn) >= 0 )
      {
        PropVariantToUInt32(propvarIn, (ULONG *)this + 15);
        PropVariantClear(propvarIn);
      }
    }
  }
  v38 = *v15;
  v52 = 0;
  *(_OWORD *)pvar = 0;
  if ( (*(int (__fastcall **)(__int64 *, const wchar_t *, PROPVARIANT *))(*v38 + 24))(v38, L"PropertyMap", pvar) >= 0
    && LOWORD(pvar[0]) )
  {
    COpenSearchPropertyMap::InitializeFromPropVariant(*((COpenSearchPropertyMap **)this + 105), pvar);
    PropVariantClear(pvar);
  }
  PropVariantClear(v47);
  PropVariantClear(v49);
  Instance = PSCreateMemoryPropertyStore(&GUID_71604b0f_97b0_4764_8577_2f13e98a1422, (void **)this + 103);
  if ( Instance >= 0 )
  {
    v39 = L"*";
    if ( *v13 )
      v39 = *v13;
    Instance = INamedPropertyStore_SetString(*((_QWORD *)this + 103), L"searchTerms", v39);
    if ( Instance >= 0 )
    {
      Instance = INamedPropertyStore_SetString(*((_QWORD *)this + 103), L"inputEncoding", L"UTF-8");
      if ( Instance >= 0 )
      {
        Instance = INamedPropertyStore_SetString(*((_QWORD *)this + 103), L"outputEncoding", L"UTF-8");
        if ( Instance >= 0 )
        {
          v40 = v46;
          if ( !v46 )
            v40 = L"*";
          Instance = INamedPropertyStore_SetString(*((_QWORD *)this + 103), L"language", v40);
        }
      }
    }
  }
LABEL_65:
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      (_DWORD)v9,
      (unsigned int)OpenSearch_RowsetInitialize_Stop,
      v11,
      v12,
      (__int64)pvar);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180044618  push    rbp
0x18004461a  push    rbx
0x18004461b  push    rsi
0x18004461c  push    rdi
0x18004461d  push    r12
0x18004461f  push    r13
0x180044621  push    r14
0x180044623  push    r15
0x180044625  lea     rbp, [rsp-1Fh]
0x18004462a  sub     rsp, 0C8h
0x180044631  mov     rax, cs:__security_cookie
0x180044638  xor     rax, rsp
0x18004463b  mov     [rbp+57h+var_48], rax
0x18004463f  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x180044646  mov     r14, r9
0x180044649  mov     [rbp+57h+var_98], r8
0x18004464d  mov     rsi, rdx
0x180044650  mov     rdi, rcx
0x180044653  jz      short loc_18004466A
0x180044655  lea     rax, [rbp+57h+pvar]
0x180044659  lea     rdx, OpenSearch_RowsetInitialize_Start
0x180044660  mov     [rsp+100h+ppv], rax
0x180044665  call    McGenEventWrite_EtwEventWriteTransfer
0x18004466a  call    ?SHTraceSQMCount@@YAXPEBU_EVENT_DESCRIPTOR@@K@Z; SHTraceSQMCount(_EVENT_DESCRIPTOR const *,ulong)
0x18004466f  lea     rcx, [rdi+348h]
0x180044676  call    ??I?$CComPtrBase@UIXMLDOMDocument@@@ATL@@QEAAPEAPEAUIXMLDOMDocument@@XZ; ATL::CComPtrBase<IXMLDOMDocument>::operator&(void)
0x18004467b  mov     rcx, rax; struct COpenSearchPropertyMap **
0x18004467e  call    ?CreateInstance@COpenSearchPropertyMap@@SAJPEAPEAV1@@Z; COpenSearchPropertyMap::CreateInstance(COpenSearchPropertyMap * *)
0x180044683  xor     r12d, r12d
0x180044686  mov     ebx, eax
0x180044688  test    eax, eax
0x18004468a  js      loc_180044C0D
0x180044690  lea     r13, [rdi+300h]
0x180044697  test    rsi, rsi
0x18004469a  jz      short loc_1800446B2
0x18004469c  mov     r9, r13
0x18004469f  mov     r8, rsi
0x1800446a2  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1800446a7  mov     ebx, eax
0x1800446a9  test    eax, eax
0x1800446ab  jns     short loc_1800446B6
0x1800446ad  jmp     loc_180044C0D
0x1800446b2  mov     [r13+0], r12
0x1800446b6  lea     r15, [rdi+350h]
0x1800446bd  xor     r8d, r8d; pUnkOuter
0x1800446c0  lea     r9, _GUID_7822aba1_e0e5_4e1a_b405_a363ca5d67ac; riid
0x1800446c7  mov     [rsp+100h+ppv], r15; ppv
0x1800446cc  lea     rdx, CLSID_SecurityZoneChecker; pclsid
0x1800446d3  xor     ecx, ecx; pszCLSID
0x1800446d5  call    cs:__imp_SHCoCreateInstance
0x1800446db  mov     ebx, eax
0x1800446dd  test    eax, eax
0x1800446df  js      loc_180044C0D
0x1800446e5  lea     rsi, [rdi+330h]
0x1800446ec  mov     rcx, [rsi]
0x1800446ef  lea     r12, [rdi+2F0h]
0x1800446f6  mov     r8, r12
0x1800446f9  lea     rdx, aOpensearchquer; "OpenSearchQueryTemplate"
0x180044700  call    INamedPropertyStore_GetString
0x180044705  xor     ebx, ebx
0x180044707  test    eax, eax
0x180044709  js      short loc_18004474E
0x18004470b  mov     rdx, [r12]
0x18004470f  cmp     [rdx], bx
0x180044712  jz      short loc_18004474E
0x180044714  mov     rcx, [r15]
0x180044717  lea     r8, [rdi+358h]
0x18004471e  mov     [rsp+100h+var_D0], r8
0x180044723  lea     r9d, [rbx+1]
0x180044727  mov     [rsp+100h+var_D8], rbx
0x18004472c  mov     r8d, 180Eh
0x180044732  mov     [rsp+100h+ppv], rbx
0x180044737  mov     rax, [rcx]
0x18004473a  mov     rax, [rax+18h]
0x18004473e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044743  test    eax, eax
0x180044745  jz      short loc_18004474E
0x180044747  mov     dword ptr [rdi+68h], 1
0x18004474e  cmp     [rdi+68h], ebx
0x180044751  jnz     short loc_1800447B9
0x180044753  mov     rcx, [rsi]
0x180044756  lea     rbx, [rdi+2F8h]
0x18004475d  mov     r8, rbx
0x180044760  lea     rdx, aOpensearchlist; "OpenSearchListTemplate"
0x180044767  call    INamedPropertyStore_GetString
0x18004476c  xor     ecx, ecx
0x18004476e  test    eax, eax
0x180044770  js      short loc_1800447B9
0x180044772  mov     rdx, [rbx]
0x180044775  cmp     [rdx], cx
0x180044778  jz      short loc_1800447B9
0x18004477a  mov     rcx, [r15]
0x18004477d  lea     r9, [rdi+358h]
0x180044784  mov     [rsp+100h+var_D0], r9
0x180044789  xor     r15d, r15d
0x18004478c  mov     [rsp+100h+var_D8], r15
0x180044791  mov     r8d, 180Eh
0x180044797  mov     [rsp+100h+ppv], r15
0x18004479c  mov     rax, [rcx]
0x18004479f  lea     r9d, [r15+1]
0x1800447a3  mov     rax, [rax+18h]
0x1800447a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800447ac  test    eax, eax
0x1800447ae  jz      short loc_1800447BC
0x1800447b0  mov     dword ptr [rdi+68h], 1
0x1800447b7  jmp     short loc_1800447BC
0x1800447b9  xor     r15d, r15d
0x1800447bc  test    r14, r14
0x1800447bf  jz      short loc_1800447E8
0x1800447c1  mov     [rdi+48h], r15d
0x1800447c5  lea     r8, [rdi+328h]
0x1800447cc  mov     rax, [r14]
0x1800447cf  lea     rdx, _GUID_f0ee7333_e6fc_479b_9f25_a860c234a38e
0x1800447d6  mov     rcx, r14
0x1800447d9  mov     rax, [rax]
0x1800447dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800447e1  mov     ebx, eax
0x1800447e3  jmp     loc_1800448E9
0x1800447e8  mov     rcx, [rsi]
0x1800447eb  lea     rbx, [rdi+320h]
0x1800447f2  mov     r8, rbx
0x1800447f5  lea     rdx, aDatasourceclsi; "DataSourceCLSID"
0x1800447fc  call    INamedPropertyStore_GetString
0x180044801  test    eax, eax
0x180044803  js      loc_1800448ED
0x180044809  mov     rcx, [rbx]
0x18004480c  cmp     [rcx], r15w
0x180044810  jz      loc_1800448ED
0x180044816  xorps   xmm0, xmm0
0x180044819  lea     rdx, [rbp+57h+pvar]
0x18004481d  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180044821  call    cs:__imp_GUIDFromStringW
0x180044827  test    eax, eax
0x180044829  jz      loc_18004490D
0x18004482f  xor     r9d, r9d
0x180044832  lea     rdx, _GUID_f0ee7333_e6fc_479b_9f25_a860c234a38e
0x180044839  lea     r14, [rdi+328h]
0x180044840  mov     [rsp+100h+var_D8], r14
0x180044845  lea     rcx, [rbp+57h+pvar]
0x180044849  mov     [rsp+100h+ppv], rdx
0x18004484e  xor     edx, edx
0x180044850  lea     r8d, [r9+4]
0x180044854  call    cs:__imp_SHExtCoCreateInstance
0x18004485a  mov     ebx, eax
0x18004485c  test    eax, eax
0x18004485e  js      loc_18004490D
0x180044864  lea     rcx, [rbp+57h+var_A0]; void *
0x180044868  mov     [rdi+48h], r15d
0x18004486c  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180044871  mov     rcx, [r14]
0x180044874  lea     r8, [rbp+57h+var_A0]
0x180044878  lea     rdx, _GUID_c3e12eb5_7d8d_44f8_b6dd_0e77b34d6de4
0x18004487f  mov     rax, [rcx]
0x180044882  mov     rax, [rax]
0x180044885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004488a  test    eax, eax
0x18004488c  js      short loc_1800448E0
0x18004488e  lea     rcx, [rbp+57h+var_A8]; void *
0x180044892  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180044897  mov     rcx, rsi
0x18004489a  call    ??C?$CComPtrBase@UIStartMenuResultSetInternal@@@ATL@@QEBAPEAV?$_NoAddRefReleaseOnCComPtr@UIStartMenuResultSetInternal@@@1@XZ; ATL::CComPtrBase<IStartMenuResultSetInternal>::operator->(void)
0x18004489f  mov     r9, rax
0x1800448a2  lea     r8, [rbp+57h+var_A8]
0x1800448a6  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x1800448ad  mov     rcx, [rax]
0x1800448b0  mov     rax, [rcx]
0x1800448b3  mov     rcx, r9
0x1800448b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800448bb  mov     ebx, eax
0x1800448bd  test    eax, eax
0x1800448bf  js      short loc_1800448D7
0x1800448c1  mov     rcx, [rbp+57h+var_A0]
0x1800448c5  mov     rdx, [rbp+57h+var_A8]
0x1800448c9  mov     rax, [rcx]
0x1800448cc  mov     rax, [rax+18h]
0x1800448d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800448d5  mov     ebx, eax
0x1800448d7  lea     rcx, [rbp+57h+var_A8]
0x1800448db  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x1800448e0  lea     rcx, [rbp+57h+var_A0]
0x1800448e4  call    ??1?$CComPtr@VCPropertyMapTable@@@ATL@@QEAA@XZ; ATL::CComPtr<CPropertyMapTable>::~CComPtr<CPropertyMapTable>(void)
0x1800448e9  test    ebx, ebx
0x1800448eb  js      short loc_18004490D
0x1800448ed  mov     rax, [r12]
0x1800448f1  cmp     [rax], r15w
0x1800448f5  jnz     short loc_180044917
0x1800448f7  mov     rax, [rdi+2F8h]
0x1800448fe  cmp     [rax], r15w
0x180044902  jnz     short loc_180044917
0x180044904  cmp     [rdi+328h], r15
0x18004490b  jnz     short loc_180044917
0x18004490d  mov     ebx, 80004005h
0x180044912  jmp     loc_180044C0D
0x180044917  mov     rcx, [rsi]
0x18004491a  lea     r14, [rdi+34h]
0x18004491e  xor     eax, eax
0x180044920  mov     [r14], r15d
0x180044923  mov     [rbp+57h+var_B0], rax
0x180044927  lea     r8, [rbp+57h+propvarIn]
0x18004492b  xorps   xmm0, xmm0
0x18004492e  lea     rdx, aPreferredpages; "PreferredPageSize"
0x180044935  mov     rax, [rcx]
0x180044938  movups  xmmword ptr [rbp+57h+propvarIn], xmm0
0x18004493c  mov     rax, [rax+18h]
0x180044940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044945  test    eax, eax
0x180044947  js      short loc_180044972
0x180044949  mov     rdx, r14; pulRet
0x18004494c  lea     rcx, [rbp+57h+propvarIn]; propvarIn
0x180044950  call    cs:__imp_PropVariantToUInt32
0x180044956  lea     rcx, [rbp+57h+propvarIn]; pvar
0x18004495a  mov     ebx, eax
0x18004495c  call    cs:__imp_PropVariantClear
0x180044962  test    ebx, ebx
0x180044964  js      short loc_180044972
0x180044966  cmp     [r14], r15d
0x180044969  jnz     short loc_180044972
0x18004496b  mov     dword ptr [r14], 32h ; '2'
0x180044972  mov     rcx, [rsi]
0x180044975  lea     r14, [rdi+40h]
0x180044979  xor     eax, eax
0x18004497b  mov     [r14], r15d
0x18004497e  mov     [rbp+57h+var_B0], rax
0x180044982  lea     r8, [rbp+57h+propvarIn]
0x180044986  xorps   xmm0, xmm0
0x180044989  lea     rdx, aMaximumresultc; "MaximumResultCount"
0x180044990  mov     rax, [rcx]
0x180044993  movups  xmmword ptr [rbp+57h+propvarIn], xmm0
0x180044997  mov     rax, [rax+18h]
0x18004499b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800449a0  test    eax, eax
0x1800449a2  js      short loc_1800449E0
0x1800449a4  mov     rdx, r14; pulRet
0x1800449a7  lea     rcx, [rbp+57h+propvarIn]; propvarIn
0x1800449ab  call    cs:__imp_PropVariantToUInt32
0x1800449b1  lea     rcx, [rbp+57h+propvarIn]; pvar
0x1800449b5  mov     ebx, eax
0x1800449b7  call    cs:__imp_PropVariantClear
0x1800449bd  test    ebx, ebx
0x1800449bf  js      short loc_1800449E0
0x1800449c1  mov     rax, [r14]
0x1800449c4  cmp     rax, 1
0x1800449c8  jge     short loc_1800449D1
0x1800449ca  mov     eax, 64h ; 'd'
0x1800449cf  jmp     short loc_1800449DD
0x1800449d1  mov     ecx, 1388h
0x1800449d6  cmp     rax, rcx
0x1800449d9  jl      short loc_1800449DD
0x1800449db  mov     eax, ecx
0x1800449dd  mov     [r14], rax
0x1800449e0  mov     rcx, [rsi]
0x1800449e3  lea     r8, [rdi+4Ch]
0x1800449e7  lea     rdx, aLinkisfilepath; "LinkIsFilePath"
0x1800449ee  call    INamedPropertyStore_GetBool
0x1800449f3  mov     rcx, rsi
0x1800449f6  lea     r8, [rdi+50h]
0x1800449fa  call    ??C?$CComPtrBase@UIStartMenuResultSetInternal@@@ATL@@QEBAPEAV?$_NoAddRefReleaseOnCComPtr@UIStartMenuResultSetInternal@@@1@XZ; ATL::CComPtrBase<IStartMenuResultSetInternal>::operator->(void)
0x1800449ff  mov     rcx, rax
0x180044a02  lea     rdx, aAllowlocalxmlf; "AllowLocalXmlFile"
0x180044a09  call    INamedPropertyStore_GetBool
0x180044a0e  mov     rcx, [rsi]
0x180044a11  lea     r8, [rbp+57h+var_78]
0x180044a15  xor     eax, eax
0x180044a17  lea     rdx, aBasestartindex; "BaseStartIndex"
0x180044a1e  mov     [rbp+57h+var_68], rax
0x180044a22  xorps   xmm0, xmm0
0x180044a25  movups  xmmword ptr [rbp+57h+var_78], xmm0
0x180044a29  mov     rax, [rcx]
0x180044a2c  mov     rax, [rax+18h]
0x180044a30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044a35  test    eax, eax
0x180044a37  js      short loc_180044A87
0x180044a39  cmp     word ptr [rbp+57h+var_78], r15w
0x180044a3e  jz      short loc_180044A87
0x180044a40  mov     rcx, [rsi]
0x180044a43  lea     r8, [rbp+57h+propvarIn]
0x180044a47  xor     eax, eax
0x180044a49  mov     [rdi+38h], r15d
0x180044a4d  mov     [rbp+57h+var_B0], rax
0x180044a51  lea     rdx, aBasestartindex; "BaseStartIndex"
0x180044a58  xorps   xmm0, xmm0
0x180044a5b  mov     rax, [rcx]
0x180044a5e  movups  xmmword ptr [rbp+57h+propvarIn], xmm0
0x180044a62  mov     rax, [rax+18h]
0x180044a66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044a6b  test    eax, eax
0x180044a6d  js      short loc_180044A87
0x180044a6f  lea     rdx, [rdi+38h]; pulRet
0x180044a73  lea     rcx, [rbp+57h+propvarIn]; propvarIn
0x180044a77  call    cs:__imp_PropVariantToUInt32
0x180044a7d  lea     rcx, [rbp+57h+propvarIn]; pvar
0x180044a81  call    cs:__imp_PropVariantClear
0x180044a87  mov     rcx, [rsi]
0x180044a8a  lea     r8, [rbp+57h+var_90]
0x180044a8e  xor     eax, eax
0x180044a90  lea     rdx, aBasestartpage; "BaseStartPage"
0x180044a97  mov     [rbp+57h+var_80], rax
0x180044a9b  xorps   xmm0, xmm0
0x180044a9e  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x180044aa2  mov     rax, [rcx]
  ... truncated ...
```
