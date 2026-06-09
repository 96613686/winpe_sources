# CGrepWdsResolver::_TryResolveToGrep(IScope *,FULLTEXT_HANDLE_TYPE,SCOPE_ITEM_FLAGS,IServiceProvider *,int *,_GUID const &,void * *)

- ea: `0x18003da00`
- end: `0x18003dfa1`
- name: `?_TryResolveToGrep@CGrepWdsResolver@@AEAAJPEAUIScope@@W4FULLTEXT_HANDLE_TYPE@@W4SCOPE_ITEM_FLAGS@@PEAUIServiceProvider@@PEAHAEBU_GUID@@PEAPEAX@Z`
- size: `1441`
- prototype: `int __high(struct IScope *, enum FULLTEXT_HANDLE_TYPE, enum SCOPE_ITEM_FLAGS, struct IServiceProvider *, int *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180060340`

## callees

- `0x18003d55c`
- `0x18003da00`
- `0x18003e1dc`
- `0x18003e3b4`
- `0x18003e8e0`
- `0x18003e928`
- `0x180062160`
- `0x180063a68`
- `0x180071df0`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IUnknown_Set` at `0x18003da85`
- `SHCORE!IUnknown_Set` at `0x18003da85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dc23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dc8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dea4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dc23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dc8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dea4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003dbf6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003dbf6`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x18003dd48`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x18003dd48`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18003da53`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18003da53`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CGrepWdsResolver::_TryResolveToGrep(
        __int64 a1,
        IUnknown *a2,
        int a3,
        __int16 a4,
        __int64 a5,
        _DWORD *a6,
        __int64 a7,
        void *ppv)
{
  _QWORD *v12; // r12
  _DWORD *v13; // r13
  HRESULT v14; // edi
  __int16 v15; // ax
  __int16 v16; // ax
  __int16 v17; // ax
  __int16 v18; // ax
  void *v19; // rbx
  LPVOID v20; // rax
  void *v21; // rcx
  __int64 v22; // r15
  unsigned int v23; // esi
  _QWORD *v24; // rax
  void *v25; // rdi
  char IsEnabled; // al
  const QITAB *v27; // rdx
  HRESULT v28; // r14d
  _QWORD *v29; // rax
  _QWORD *v30; // rsi
  int v32; // [rsp+20h] [rbp-61h]
  LPVOID pv[2]; // [rsp+50h] [rbp-31h] BYREF
  __int64 v34; // [rsp+60h] [rbp-21h]
  IUnknown *ppunk[2]; // [rsp+68h] [rbp-19h] BYREF
  __int64 v36; // [rsp+78h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+47h]

  v12 = ppv;
  *(_QWORD *)ppv = 0;
  v13 = a6;
  *a6 = 0;
  a5 = 0;
  ppv = 0;
  v14 = PSCreateMemoryPropertyStore(&GUID_71604b0f_97b0_4764_8577_2f13e98a1422, &ppv);
  if ( v14 >= 0 )
  {
    *(_OWORD *)ppunk = 0;
    v36 = 0;
    if ( a2 )
    {
      LOWORD(ppunk[0]) = 13;
      IUnknown_Set(&ppunk[1], a2);
    }
    v14 = (*(__int64 (__fastcall **)(void *, const wchar_t *, IUnknown **))(*(_QWORD *)ppv + 32LL))(
            ppv,
            L"Scope",
            ppunk);
    if ( v14 >= 0 )
    {
      v15 = 0;
      *(_OWORD *)pv = 0;
      v34 = 0;
      LOWORD(pv[0]) = 11;
      if ( (a4 & 4) != 0 )
        v15 = -1;
      LOWORD(pv[1]) = v15;
      v14 = (*(__int64 (__fastcall **)(void *, const wchar_t *, LPVOID *))(*(_QWORD *)ppv + 32LL))(
              ppv,
              L"FastPropertiesOnly",
              pv);
      if ( v14 >= 0 )
      {
        v16 = 0;
        *(_OWORD *)pv = 0;
        v34 = 0;
        LOWORD(pv[0]) = 11;
        if ( (a4 & 8) != 0 )
          v16 = -1;
        LOWORD(pv[1]) = v16;
        v14 = (*(__int64 (__fastcall **)(void *, const wchar_t *, LPVOID *))(*(_QWORD *)ppv + 32LL))(
                ppv,
                L"FastItems",
                pv);
        if ( v14 >= 0 )
        {
          v17 = 0;
          *(_OWORD *)pv = 0;
          v34 = 0;
          LOWORD(pv[0]) = 11;
          if ( (a4 & 0x80u) != 0 )
            v17 = -1;
          LOWORD(pv[1]) = v17;
          v14 = (*(__int64 (__fastcall **)(void *, const wchar_t *, LPVOID *))(*(_QWORD *)ppv + 32LL))(
                  ppv,
                  L"WinRTDataModel",
                  pv);
          if ( v14 >= 0 )
          {
            v18 = 0;
            *(_OWORD *)pv = 0;
            v34 = 0;
            LOWORD(pv[0]) = 11;
            if ( (a4 & 0x200) != 0 )
              v18 = -1;
            LOWORD(pv[1]) = v18;
            v14 = (*(__int64 (__fastcall **)(void *, const wchar_t *, LPVOID *))(*(_QWORD *)ppv + 32LL))(
                    ppv,
                    L"ExcludeIndexed",
                    pv);
            if ( v14 >= 0 )
            {
              if ( a3 != 1 || (v14 = INamedPropertyStore_SetBool(ppv, L"ForceFullText", 1), v14 >= 0) )
                v14 = (**(__int64 (__fastcall ***)(void *, GUID *, __int64 *))ppv)(
                        ppv,
                        &GUID_71604b0f_97b0_4764_8577_2f13e98a1422,
                        &a5);
            }
          }
        }
      }
    }
    PropVariantClear((PROPVARIANT *)ppunk);
  }
  if ( ppv )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v14 >= 0 )
  {
    CoTaskMemFree(0);
    v19 = 0;
    pv[0] = 0;
    pv[1] = 0;
    v34 = 0;
    v14 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(
            pv,
            L"Merge Any",
            9);
    if ( v14 < 0 )
      goto LABEL_50;
    if ( *(_DWORD *)(a1 + 40) )
    {
      v14 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(pv, L".");
      if ( v14 < 0 )
        goto LABEL_50;
      v14 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(pv, a1 + 60);
      if ( v14 < 0 )
        goto LABEL_50;
    }
    v19 = 0;
    v14 = 0;
    v20 = pv[0];
    if ( !pv[0] )
    {
      v14 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
              pv,
              &pszFormat,
              -1);
      if ( v14 < 0 )
      {
LABEL_50:
        v21 = pv[0];
LABEL_27:
        if ( v21 )
          CoTaskMemFree(v21);
        if ( v14 < 0 )
          goto LABEL_45;
        v22 = a5;
        *v12 = 0;
        ppv = 0;
        v23 = -2147024882;
        v24 = operator new(0x78u, (const struct std::nothrow_t *)&std::nothrow);
        v25 = v24;
        a6 = v24;
        if ( v24 )
        {
          *v24 = &CProviderConfig::`vftable'{for `IProviderCloudSearchConfig'};
          v24[1] = &CProviderConfig::`vftable'{for `IInitializeProviderCloudSearchConfig'};
          v24[2] = &CProviderConfig::`vftable'{for `IInitializeProviderConfig'};
          v24[3] = &CProviderConfig::`vftable'{for `ICloneConfiguration'};
          *((_DWORD *)v24 + 8) = 1;
          v24[13] = 0;
          v24[14] = 0;
          _InterlockedIncrement(&g_cDllRef);
          IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FI45690266>::GetImpl'::`2'::impl);
          v27 = (const QITAB *)&`CProviderConfig::QueryInterface'::`5'::qitWithCloudSearch;
          if ( !IsEnabled )
            v27 = &`CProviderConfig::QueryInterface'::`7'::qit;
          v28 = QISearch(v25, v27, &GUID_628880f3_0dc6_4359_a29b_15ef9aecbd23, &ppv);
          CProviderConfig::Release((CProviderConfig *)v25);
          if ( v28 >= 0 )
          {
            v14 = (*(__int64 (__fastcall **)(void *, GUID *, void *, __int64, _QWORD, _QWORD))(*(_QWORD *)ppv + 24LL))(
                    ppv,
                    &GUID_1685d4ab_a51b_4af1_a4e5_cee87002431d,
                    v19,
                    v22,
                    0,
                    0);
            if ( v14 >= 0 )
            {
              a6 = 0;
              v14 = -2147024882;
              v29 = operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
              v30 = v29;
              if ( v29 )
              {
                *v29 = &CEnumerableObjectCollection::`vftable'{for `IObjectCollection'};
                v29[1] = &CEnumerableObjectCollection::`vftable'{for `IEnumObjects'};
                v29[2] = &CEnumerableObjectCollection::`vftable'{for `IEnumUnknown'};
                *((_DWORD *)v29 + 6) = 1;
                *(_QWORD *)((char *)v29 + 28) = 4;
                v29[5] = 0;
                v29[6] = 0;
                v29[7] = 0;
                v29[8] = 0;
                v14 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, _DWORD **))*v29)(
                        v29,
                        &GUID_5632b1a4_e38a_400a_928a_d4cd63230295,
                        &a6);
                (*(void (__fastcall **)(_QWORD *))(*v30 + 16LL))(v30);
                if ( v14 >= 0 )
                {
                  v14 = (*(__int64 (__fastcall **)(_DWORD *, void *))(*(_QWORD *)a6 + 40LL))(a6, ppv);
                  if ( v14 >= 0 )
                    v14 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))a6)(a6, a7, v12);
                }
              }
              if ( a6 )
                (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)a6 + 16LL))(a6);
            }
            goto LABEL_41;
          }
          v23 = v28;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1F60,
          (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
          (const char *)v23,
          v32);
        v14 = v23;
LABEL_41:
        if ( ppv )
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
        if ( v14 >= 0 )
          *v13 = 1;
LABEL_45:
        CoTaskMemFree(v19);
        goto LABEL_46;
      }
      v20 = pv[0];
    }
    v19 = v20;
    v21 = 0;
    goto LABEL_27;
  }
LABEL_46:
  if ( a5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a5 + 16LL))(a5);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18003da00  push    rbp
0x18003da02  push    rbx
0x18003da03  push    rsi
0x18003da04  push    rdi
0x18003da05  push    r12
0x18003da07  push    r13
0x18003da09  push    r14
0x18003da0b  push    r15
0x18003da0d  lea     rbp, [rsp-7]
0x18003da12  sub     rsp, 88h
0x18003da19  mov     esi, r9d
0x18003da1c  mov     r14d, r8d
0x18003da1f  mov     rbx, rdx
0x18003da22  mov     r15, rcx
0x18003da25  xor     eax, eax
0x18003da27  mov     r12, [rbp+3Fh+ppv]
0x18003da2e  mov     [r12], rax
0x18003da32  mov     r13, [rbp+3Fh+arg_28]
0x18003da36  mov     [r13+0], eax
0x18003da3a  mov     [rbp+3Fh+arg_20], rax
0x18003da3e  mov     [rbp+3Fh+ppv], rax
0x18003da45  lea     rdx, [rbp+3Fh+ppv]; ppv
0x18003da4c  lea     rcx, _GUID_71604b0f_97b0_4764_8577_2f13e98a1422; riid
0x18003da53  call    cs:__imp_PSCreateMemoryPropertyStore
0x18003da59  mov     edi, eax
0x18003da5b  test    eax, eax
0x18003da5d  js      loc_18003DBFD
0x18003da63  xorps   xmm0, xmm0
0x18003da66  xor     eax, eax
0x18003da68  movups  xmmword ptr [rbp+3Fh+ppunk], xmm0
0x18003da6c  mov     [rbp+3Fh+var_48], rax
0x18003da70  test    rbx, rbx
0x18003da73  jz      short loc_18003DA8B
0x18003da75  mov     eax, 0Dh
0x18003da7a  mov     word ptr [rbp+3Fh+ppunk], ax
0x18003da7e  mov     rdx, rbx; punk
0x18003da81  lea     rcx, [rbp+3Fh+ppunk+8]; ppunk
0x18003da85  call    cs:__imp_IUnknown_Set
0x18003da8b  mov     rcx, [rbp+3Fh+ppv]
0x18003da92  mov     rax, [rcx]
0x18003da95  lea     r8, [rbp+3Fh+ppunk]
0x18003da99  lea     rdx, aScope_0; "Scope"
0x18003daa0  mov     rax, [rax+20h]
0x18003daa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003daa9  mov     edi, eax
0x18003daab  test    eax, eax
0x18003daad  js      loc_18003DBF2
0x18003dab3  mov     rcx, [rbp+3Fh+ppv]
0x18003daba  xorps   xmm0, xmm0
0x18003dabd  xor     eax, eax
0x18003dabf  movups  xmmword ptr [rbp+3Fh+pv], xmm0
0x18003dac3  mov     [rbp+3Fh+var_60], rax
0x18003dac7  lea     ebx, [rax+0Bh]
0x18003daca  mov     word ptr [rbp+3Fh+pv], bx
0x18003dace  test    sil, 4
0x18003dad2  jnz     loc_18003DED7
0x18003dad8  mov     word ptr [rbp+3Fh+pv+8], ax
0x18003dadc  mov     rax, [rcx]
0x18003dadf  lea     r8, [rbp+3Fh+pv]
0x18003dae3  lea     rdx, aFastproperties; "FastPropertiesOnly"
0x18003daea  mov     rax, [rax+20h]
0x18003daee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003daf3  mov     edi, eax
0x18003daf5  test    eax, eax
0x18003daf7  js      loc_18003DBF2
0x18003dafd  mov     rcx, [rbp+3Fh+ppv]
0x18003db04  xorps   xmm0, xmm0
0x18003db07  xor     eax, eax
0x18003db09  movups  xmmword ptr [rbp+3Fh+pv], xmm0
0x18003db0d  mov     [rbp+3Fh+var_60], rax
0x18003db11  mov     word ptr [rbp+3Fh+pv], bx
0x18003db15  test    sil, 8
0x18003db19  jnz     loc_18003DEE0
0x18003db1f  mov     word ptr [rbp+3Fh+pv+8], ax
0x18003db23  mov     rax, [rcx]
0x18003db26  lea     r8, [rbp+3Fh+pv]
0x18003db2a  lea     rdx, aFastitems; "FastItems"
0x18003db31  mov     rax, [rax+20h]
0x18003db35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003db3a  mov     edi, eax
0x18003db3c  test    eax, eax
0x18003db3e  js      loc_18003DBF2
0x18003db44  mov     rcx, [rbp+3Fh+ppv]
0x18003db4b  xorps   xmm0, xmm0
0x18003db4e  xor     eax, eax
0x18003db50  movups  xmmword ptr [rbp+3Fh+pv], xmm0
0x18003db54  mov     [rbp+3Fh+var_60], rax
0x18003db58  mov     word ptr [rbp+3Fh+pv], bx
0x18003db5c  test    sil, sil
0x18003db5f  js      loc_18003DEE9
0x18003db65  mov     word ptr [rbp+3Fh+pv+8], ax
0x18003db69  mov     rax, [rcx]
0x18003db6c  lea     r8, [rbp+3Fh+pv]
0x18003db70  lea     rdx, aWinrtdatamodel; "WinRTDataModel"
0x18003db77  mov     rax, [rax+20h]
0x18003db7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003db80  mov     edi, eax
0x18003db82  test    eax, eax
0x18003db84  js      short loc_18003DBF2
0x18003db86  mov     rcx, [rbp+3Fh+ppv]
0x18003db8d  xorps   xmm0, xmm0
0x18003db90  xor     eax, eax
0x18003db92  movups  xmmword ptr [rbp+3Fh+pv], xmm0
0x18003db96  mov     [rbp+3Fh+var_60], rax
0x18003db9a  mov     word ptr [rbp+3Fh+pv], bx
0x18003db9e  bt      esi, 9
0x18003dba2  jb      loc_18003DEF2
0x18003dba8  mov     word ptr [rbp+3Fh+pv+8], ax
0x18003dbac  mov     rax, [rcx]
0x18003dbaf  lea     r8, [rbp+3Fh+pv]
0x18003dbb3  lea     rdx, aExcludeindexed; "ExcludeIndexed"
0x18003dbba  mov     rax, [rax+20h]
0x18003dbbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dbc3  mov     edi, eax
0x18003dbc5  test    eax, eax
0x18003dbc7  js      short loc_18003DBF2
0x18003dbc9  cmp     r14d, 1
0x18003dbcd  jz      loc_18003DF1B
0x18003dbd3  mov     rcx, [rbp+3Fh+ppv]
0x18003dbda  mov     rax, [rcx]
0x18003dbdd  lea     r8, [rbp+3Fh+arg_20]
0x18003dbe1  lea     rdx, _GUID_71604b0f_97b0_4764_8577_2f13e98a1422
0x18003dbe8  mov     rax, [rax]
0x18003dbeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dbf0  mov     edi, eax
0x18003dbf2  lea     rcx, [rbp+3Fh+ppunk]; pvar
0x18003dbf6  call    cs:__imp_PropVariantClear
0x18003dbfc  nop
0x18003dbfd  mov     rcx, [rbp+3Fh+ppv]
0x18003dc04  xor     r14d, r14d
0x18003dc07  test    rcx, rcx
0x18003dc0a  jz      short loc_18003DC19
0x18003dc0c  mov     rax, [rcx]
0x18003dc0f  mov     rax, [rax+10h]
0x18003dc13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dc18  nop
0x18003dc19  test    edi, edi
0x18003dc1b  js      loc_18003DEAB
0x18003dc21  xor     ecx, ecx; pv
0x18003dc23  call    cs:__imp_CoTaskMemFree
0x18003dc29  mov     rbx, r14
0x18003dc2c  mov     [rbp+3Fh+var_80], rbx
0x18003dc30  mov     [rbp+3Fh+pv], r14
0x18003dc34  mov     [rbp+3Fh+pv+8], r14
0x18003dc38  mov     [rbp+3Fh+var_60], r14
0x18003dc3c  mov     r8d, 9
0x18003dc42  lea     rdx, aMergeAny; "Merge Any"
0x18003dc49  lea     rcx, [rbp+3Fh+pv]
0x18003dc4d  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x18003dc52  mov     edi, eax
0x18003dc54  test    eax, eax
0x18003dc56  js      loc_18003DF12
0x18003dc5c  cmp     [r15+28h], r14d
0x18003dc60  jnz     loc_18003DF43
0x18003dc66  mov     rbx, r14
0x18003dc69  mov     [rbp+3Fh+var_80], rbx
0x18003dc6d  mov     edi, r14d
0x18003dc70  mov     rax, [rbp+3Fh+pv]
0x18003dc74  test    rax, rax
0x18003dc77  jz      loc_18003DF5B
0x18003dc7d  mov     rbx, rax
0x18003dc80  mov     rcx, r14; pv
0x18003dc83  mov     [rbp+3Fh+var_80], rax
0x18003dc87  test    rcx, rcx
0x18003dc8a  jz      short loc_18003DC92
0x18003dc8c  call    cs:__imp_CoTaskMemFree
0x18003dc92  test    edi, edi
0x18003dc94  js      loc_18003DEA1
0x18003dc9a  mov     r15, [rbp+3Fh+arg_20]
0x18003dc9e  mov     [r12], r14
0x18003dca2  mov     [rbp+3Fh+ppv], r14
0x18003dca9  mov     esi, 8007000Eh
0x18003dcae  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003dcb5  mov     ecx, 78h ; 'x'; unsigned __int64
0x18003dcba  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003dcbf  mov     rdi, rax
0x18003dcc2  mov     [rbp+3Fh+arg_28], rax
0x18003dcc6  test    rax, rax
0x18003dcc9  jz      loc_18003DF81
0x18003dccf  lea     rax, ??_7CProviderConfig@@6BIProviderCloudSearchConfig@@@; const CProviderConfig::`vftable'{for `IProviderCloudSearchConfig'}
0x18003dcd6  mov     [rdi], rax
0x18003dcd9  lea     rax, ??_7CProviderConfig@@6BIInitializeProviderCloudSearchConfig@@@; const CProviderConfig::`vftable'{for `IInitializeProviderCloudSearchConfig'}
0x18003dce0  mov     [rdi+8], rax
0x18003dce4  lea     rax, ??_7CProviderConfig@@6BIInitializeProviderConfig@@@; const CProviderConfig::`vftable'{for `IInitializeProviderConfig'}
0x18003dceb  mov     [rdi+10h], rax
0x18003dcef  lea     rax, ??_7CProviderConfig@@6BICloneConfiguration@@@; const CProviderConfig::`vftable'{for `ICloneConfiguration'}
0x18003dcf6  mov     [rdi+18h], rax
0x18003dcfa  mov     dword ptr [rdi+20h], 1
0x18003dd01  mov     [rdi+68h], r14
0x18003dd05  mov     [rdi+70h], r14
0x18003dd09  lock inc cs:?g_cDllRef@@3JA; long g_cDllRef
0x18003dd10  test    rdi, rdi
0x18003dd13  jz      loc_18003DF81
0x18003dd19  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FI45690266@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FI45690266@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266> `wil::Feature<__WilFeatureTraits_Feature_FI45690266>::GetImpl(void)'::`2'::impl
0x18003dd20  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FI45690266@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266>::__private_IsEnabled(void)
0x18003dd25  lea     r9, [rbp+3Fh+ppv]; ppv
0x18003dd2c  lea     r8, _GUID_628880f3_0dc6_4359_a29b_15ef9aecbd23; riid
0x18003dd33  mov     rcx, rdi; that
0x18003dd36  test    al, al
0x18003dd38  lea     rdx, ?qitWithCloudSearch@?4??QueryInterface@CProviderConfig@@UEAAJAEBU_GUID@@PEAPEAX@Z@4QBUQITAB@@B; QITAB const near * const `CProviderConfig::QueryInterface(_GUID const &,void * *)'::`5'::qitWithCloudSearch
0x18003dd3f  jnz     short loc_18003DD48
0x18003dd41  lea     rdx, ?qit@?6??QueryInterface@CProviderConfig@@UEAAJAEBU_GUID@@PEAPEAX@Z@4QBUQITAB@@B; pqit
0x18003dd48  call    cs:__imp_QISearch
0x18003dd4e  mov     r14d, eax
0x18003dd51  mov     rcx, rdi; this
0x18003dd54  call    ?Release@CProviderConfig@@UEAAKXZ; CProviderConfig::Release(void)
0x18003dd59  test    r14d, r14d
0x18003dd5c  js      loc_18003DF7E
0x18003dd62  mov     rcx, [rbp+3Fh+ppv]
0x18003dd69  mov     rax, [rcx]
0x18003dd6c  xor     r14d, r14d
0x18003dd6f  mov     [rsp+0C0h+var_98], r14
0x18003dd74  mov     [rsp+0C0h+var_A0], r14
0x18003dd79  mov     r9, r15
0x18003dd7c  mov     r8, rbx
0x18003dd7f  lea     rdx, _GUID_1685d4ab_a51b_4af1_a4e5_cee87002431d
0x18003dd86  mov     rax, [rax+18h]
0x18003dd8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dd8f  mov     edi, eax
0x18003dd91  test    eax, eax
0x18003dd93  js      loc_18003DE7C
0x18003dd99  mov     [rbp+3Fh+arg_28], r14
0x18003dd9d  mov     edi, esi
0x18003dd9f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003dda6  lea     ecx, [r14+48h]; unsigned __int64
0x18003ddaa  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003ddaf  mov     rsi, rax
0x18003ddb2  mov     [rbp+3Fh+var_78], rax
0x18003ddb6  test    rax, rax
0x18003ddb9  jz      loc_18003DE66
0x18003ddbf  lea     rax, ??_7CEnumerableObjectCollection@@6BIObjectCollection@@@; const CEnumerableObjectCollection::`vftable'{for `IObjectCollection'}
0x18003ddc6  mov     [rsi], rax
0x18003ddc9  lea     rax, ??_7CEnumerableObjectCollection@@6BIEnumObjects@@@; const CEnumerableObjectCollection::`vftable'{for `IEnumObjects'}
0x18003ddd0  mov     [rsi+8], rax
0x18003ddd4  lea     rax, ??_7CEnumerableObjectCollection@@6BIEnumUnknown@@@; const CEnumerableObjectCollection::`vftable'{for `IEnumUnknown'}
0x18003dddb  mov     [rsi+10h], rax
0x18003dddf  mov     dword ptr [rsi+18h], 1
0x18003dde6  mov     qword ptr [rsi+1Ch], 4
0x18003ddee  mov     [rsi+28h], r14
0x18003ddf2  mov     [rsi+30h], r14
0x18003ddf6  mov     [rsi+38h], r14
0x18003ddfa  mov     [rsi+40h], r14
0x18003ddfe  test    rsi, rsi
0x18003de01  jz      short loc_18003DE66
0x18003de03  mov     rax, [rsi]
0x18003de06  lea     r8, [rbp+3Fh+arg_28]
0x18003de0a  lea     rdx, _GUID_5632b1a4_e38a_400a_928a_d4cd63230295
0x18003de11  mov     rcx, rsi
0x18003de14  mov     rax, [rax]
0x18003de17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003de1c  mov     edi, eax
0x18003de1e  mov     rax, [rsi]
0x18003de21  mov     rcx, rsi
0x18003de24  mov     rax, [rax+10h]
0x18003de28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003de2d  test    edi, edi
0x18003de2f  js      short loc_18003DE66
0x18003de31  mov     rcx, [rbp+3Fh+arg_28]
0x18003de35  mov     rax, [rcx]
0x18003de38  mov     rdx, [rbp+3Fh+ppv]
0x18003de3f  mov     rax, [rax+28h]
0x18003de43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003de48  mov     edi, eax
0x18003de4a  test    eax, eax
0x18003de4c  js      short loc_18003DE66
0x18003de4e  mov     rcx, [rbp+3Fh+arg_28]
0x18003de52  mov     rax, [rcx]
0x18003de55  mov     r8, r12
0x18003de58  mov     rdx, [rbp+3Fh+arg_30]
0x18003de5c  mov     rax, [rax]
0x18003de5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003de64  mov     edi, eax
0x18003de66  mov     rcx, [rbp+3Fh+arg_28]
0x18003de6a  test    rcx, rcx
0x18003de6d  jz      short loc_18003DE7C
0x18003de6f  mov     rax, [rcx]
0x18003de72  mov     rax, [rax+10h]
0x18003de76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003de7b  nop
0x18003de7c  mov     rcx, [rbp+3Fh+ppv]
0x18003de83  test    rcx, rcx
0x18003de86  jz      short loc_18003DE95
0x18003de88  mov     rax, [rcx]
0x18003de8b  mov     rax, [rax+10h]
0x18003de8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003de94  nop
0x18003de95  test    edi, edi
0x18003de97  js      short loc_18003DEA1
0x18003de99  mov     dword ptr [r13+0], 1
0x18003dea1  mov     rcx, rbx; pv
0x18003dea4  call    cs:__imp_CoTaskMemFree
0x18003deaa  nop
0x18003deab  mov     rcx, [rbp+3Fh+arg_20]
0x18003deaf  test    rcx, rcx
0x18003deb2  jz      short loc_18003DEC1
0x18003deb4  mov     rdx, [rcx]
0x18003deb7  mov     rax, [rdx+10h]
0x18003debb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dec0  nop
0x18003dec1  mov     eax, edi
  ... truncated ...
```
