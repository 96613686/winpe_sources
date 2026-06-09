# CGrepDataSource::_GetScopeAndGrepOptsFromProperies(IScope * *,INamedPropertyStore * *)

- ea: `0x1800309dc`
- end: `0x180030e67`
- name: `?_GetScopeAndGrepOptsFromProperies@CGrepDataSource@@AEAAJPEAPEAUIScope@@PEAPEAUINamedPropertyStore@@@Z`
- size: `1163`
- prototype: `int(CGrepDataSource *__hidden this, struct IScope **, struct INamedPropertyStore **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180030870`

## callees

- `0x18001173c`
- `0x1800309dc`
- `0x180030e70`
- `0x180042b90`
- `0x180057058`
- `0x18006c7c8`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IUnknown_Set` at `0x180030e26`
- `SHCORE!IUnknown_Set` at `0x180030e33`
- `SHCORE!IUnknown_Set` at `0x180030e26`
- `SHCORE!IUnknown_Set` at `0x180030e33`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180030e55`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180030e55`
- `OLEAUT32!__imp_VariantClear` at `0x180030b92`
- `OLEAUT32!__imp_VariantClear` at `0x180030b92`
- `OLEAUT32!__imp_VariantCopy` at `0x180030a73`
- `OLEAUT32!__imp_VariantCopy` at `0x180030af1`
- `OLEAUT32!__imp_VariantCopy` at `0x180030a73`
- `OLEAUT32!__imp_VariantCopy` at `0x180030af1`

## pseudocode

```c
__int64 __fastcall CGrepDataSource::_GetScopeAndGrepOptsFromProperies(
        CGrepDataSource *this,
        IUnknown **a2,
        IUnknown **a3)
{
  int Instance; // ebx
  HRESULT v7; // edi
  int i; // esi
  struct _DSA *v9; // rcx
  int v10; // eax
  char *ItemPtr; // rdx
  __int64 v12; // rax
  int m; // edi
  struct _DSA *v14; // rcx
  int v15; // eax
  char *v16; // rax
  __int64 v17; // rcx
  struct INamedPropertyStore *v18; // rcx
  struct INamedPropertyStoreVtbl *lpVtbl; // rax
  CGrepDataSource *v20; // rcx
  int GrepQueryFactoryOptions; // eax
  void *v22; // rcx
  struct IUnknown *v24; // rcx
  unsigned int j; // esi
  __int64 v26; // rdx
  __int64 v27; // r8
  CGrepDataSource *v28; // rcx
  unsigned int k; // edi
  IUnknown *v30; // rcx
  IUnknown *v31; // [rsp+30h] [rbp-49h] BYREF
  __int64 v32; // [rsp+38h] [rbp-41h] BYREF
  struct INamedPropertyStore *v33; // [rsp+40h] [rbp-39h] BYREF
  VARIANTARG pvargDest; // [rsp+48h] [rbp-31h] BYREF
  __int64 v35; // [rsp+60h] [rbp-19h] BYREF
  __int64 v36; // [rsp+68h] [rbp-11h] BYREF
  struct tagPROPVARIANT pvar[4]; // [rsp+70h] [rbp-9h] BYREF
  struct INamedPropertyStore *v38; // [rsp+E0h] [rbp+67h] BYREF
  unsigned int v39; // [rsp+E8h] [rbp+6Fh] BYREF
  __int64 v40; // [rsp+F0h] [rbp+77h] BYREF
  IUnknown *punk; // [rsp+F8h] [rbp+7Fh] BYREF

  *a2 = 0;
  Instance = -2147023728;
  pvargDest.pRecInfo = 0;
  *a3 = 0;
  *(_OWORD *)&pvargDest.vt = 0;
  v7 = -2147023728;
  for ( i = 0; ; ++i )
  {
    v9 = (struct _DSA *)*((_QWORD *)this + 5);
    v10 = v9 ? *(_DWORD *)v9 : 0;
    if ( i >= v10 )
      break;
    ItemPtr = (char *)g_pfn_DSA_GetItemPtr(v9, i);
    v12 = *(_QWORD *)ItemPtr - *(_QWORD *)&DBPROPSET_DBINIT.Data1;
    if ( !v12 )
      v12 = *((_QWORD *)ItemPtr + 1) - *(_QWORD *)DBPROPSET_DBINIT.Data4;
    if ( !v12 && *((_DWORD *)ItemPtr + 4) == 0x10000 && !*((_DWORD *)ItemPtr + 6) )
    {
      v7 = VariantCopy(&pvargDest, (const VARIANTARG *)(ItemPtr + 64));
      if ( v7 >= 0 )
      {
        v40 = 0;
        if ( pvargDest.vt == 13 && pvargDest.llVal || (Instance = -2147467262, pvargDest.vt == 9) && pvargDest.llVal )
        {
          Instance = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, __int64 *))pvargDest.llVal)(
                       pvargDest.llVal,
                       &GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9,
                       &v40);
          if ( Instance >= 0 )
          {
            punk = 0;
            v31 = 0;
            Instance = CScope_CreateInstance(v24, 0, &GUID_655d1685_2bfd_4f7f_ad22_5ab61c8d8798, (void **)&punk);
            if ( Instance >= 0 )
            {
              v39 = 0;
              Instance = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v40 + 24LL))(v40, &v39);
              for ( j = 0; j < v39; ++j )
              {
                if ( Instance < 0 )
                  break;
                v33 = 0;
                Instance = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, struct INamedPropertyStore **))(*(_QWORD *)v40 + 32LL))(
                             v40,
                             j,
                             &GUID_71604b0f_97b0_4764_8577_2f13e98a1422,
                             &v33);
                if ( Instance >= 0 )
                {
                  v36 = 0;
                  if ( (int)GetObjectFromConfigPropStore(v33, v26, v27, &v36) >= 0 )
                  {
                    v32 = 0;
                    Instance = (*(__int64 (__fastcall **)(__int64, __int64, GUID *, __int64 *))(*(_QWORD *)v36 + 64LL))(
                                 v36,
                                 4096,
                                 &GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9,
                                 &v32);
                    if ( Instance >= 0 )
                    {
                      LODWORD(v38) = 0;
                      Instance = (*(__int64 (__fastcall **)(__int64, struct INamedPropertyStore **))(*(_QWORD *)v32 + 24LL))(
                                   v32,
                                   &v38);
                      for ( k = 0; k < (unsigned int)v38; ++k )
                      {
                        if ( Instance < 0 )
                          break;
                        v35 = 0;
                        Instance = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v32 + 32LL))(
                                     v32,
                                     k,
                                     &GUID_dd400ff4_a119_405f_970e_a9a5e7e828c0,
                                     &v35);
                        if ( Instance >= 0 )
                        {
                          Instance = ((__int64 (__fastcall *)(IUnknown *, __int64))punk->lpVtbl[1].QueryInterface)(
                                       punk,
                                       v35);
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
                        }
                      }
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
                    }
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
                  }
                  if ( !v31 )
                    Instance = CGrepDataSource::_CreateGrepQueryFactoryOptions(v28, v33, &v31);
                  ((void (__fastcall *)(struct INamedPropertyStore *))v33->lpVtbl->Release)(v33);
                }
              }
            }
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
            if ( Instance >= 0 )
            {
              IUnknown_Set(a2, punk);
              IUnknown_Set(a3, v31);
            }
            v30 = punk;
            punk = 0;
            if ( v30 )
              ((void (__fastcall *)(IUnknown *))v30->lpVtbl->Release)(v30);
            v22 = v31;
            v31 = 0;
            if ( v22 )
LABEL_30:
              (*(void (__fastcall **)(void *))(*(_QWORD *)v22 + 16LL))(v22);
          }
        }
LABEL_31:
        VariantClear(&pvargDest);
        return (unsigned int)Instance;
      }
      break;
    }
  }
  if ( v7 == -2147023728 )
  {
    memset(&pvargDest, 0, sizeof(pvargDest));
    for ( m = 0; ; ++m )
    {
      v14 = (struct _DSA *)*((_QWORD *)this + 5);
      v15 = v14 ? *(_DWORD *)v14 : 0;
      if ( m >= v15 )
        break;
      v16 = (char *)g_pfn_DSA_GetItemPtr(v14, m);
      v17 = *(_QWORD *)v16 - *(_QWORD *)&DBPROPSET_DBINIT.Data1;
      if ( *(_QWORD *)v16 == *(_QWORD *)&DBPROPSET_DBINIT.Data1 )
        v17 = *((_QWORD *)v16 + 1) - *(_QWORD *)DBPROPSET_DBINIT.Data4;
      if ( !v17 && *((_DWORD *)v16 + 4) == 0x20000 && !*((_DWORD *)v16 + 6) )
      {
        Instance = VariantCopy(&pvargDest, (const VARIANTARG *)(v16 + 64));
        if ( Instance < 0 )
          return (unsigned int)Instance;
        v38 = 0;
        if ( pvargDest.vt == 13 && pvargDest.llVal || (Instance = -2147467262, pvargDest.vt == 9) && pvargDest.llVal )
        {
          Instance = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, struct INamedPropertyStore **))pvargDest.llVal)(
                       pvargDest.llVal,
                       &GUID_71604b0f_97b0_4764_8577_2f13e98a1422,
                       &v38);
          if ( Instance >= 0 )
          {
            v18 = v38;
            *a2 = 0;
            lpVtbl = v18->lpVtbl;
            memset(pvar, 0, 24);
            if ( ((int (__fastcall *)(struct INamedPropertyStore *, const wchar_t *, struct tagPROPVARIANT *))lpVtbl->GetNamedValue)(
                   v18,
                   L"Scope",
                   pvar) >= 0 )
            {
              QueryInterfacePropVariant(pvar, &GUID_655d1685_2bfd_4f7f_ad22_5ab61c8d8798, (void **)a2);
              PropVariantClear((PROPVARIANT *)pvar);
            }
            GrepQueryFactoryOptions = CGrepDataSource::_CreateGrepQueryFactoryOptions(v20, v38, a3);
            v22 = v38;
            Instance = GrepQueryFactoryOptions;
            goto LABEL_30;
          }
        }
        goto LABEL_31;
      }
    }
  }
  else
  {
    return (unsigned int)v7;
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800309dc  push    rbp
0x1800309de  push    rbx
0x1800309df  push    rsi
0x1800309e0  push    rdi
0x1800309e1  push    r12
0x1800309e3  push    r13
0x1800309e5  push    r14
0x1800309e7  push    r15
0x1800309e9  lea     rbp, [rsp-1Fh]
0x1800309ee  sub     rsp, 98h
0x1800309f5  xor     r13d, r13d
0x1800309f8  xorps   xmm0, xmm0
0x1800309fb  xor     eax, eax
0x1800309fd  mov     [rdx], r13
0x180030a00  mov     ebx, 80070490h
0x180030a05  mov     qword ptr [rbp+57h+pvargDest+10h], rax
0x180030a09  mov     r12, r8
0x180030a0c  mov     [r8], r13
0x180030a0f  mov     r15, rdx
0x180030a12  mov     r14, rcx
0x180030a15  movups  xmmword ptr [rbp+57h+pvargDest], xmm0
0x180030a19  mov     edi, ebx
0x180030a1b  mov     esi, r13d
0x180030a1e  mov     rcx, [r14+28h]; hdsa
0x180030a22  test    rcx, rcx
0x180030a25  jz      loc_180030BAE
0x180030a2b  mov     eax, [rcx]
0x180030a2d  cmp     esi, eax
0x180030a2f  jge     short loc_180030A83
0x180030a31  mov     edx, esi; i
0x180030a33  call    cs:g_pfn_DSA_GetItemPtr
0x180030a39  mov     rdx, rax
0x180030a3c  mov     rax, [rax]
0x180030a3f  sub     rax, qword ptr cs:DBPROPSET_DBINIT.Data1
0x180030a46  jnz     short loc_180030A53
0x180030a48  mov     rax, [rdx+8]
0x180030a4c  sub     rax, qword ptr cs:DBPROPSET_DBINIT.Data4
0x180030a53  test    rax, rax
0x180030a56  jnz     short loc_180030A61
0x180030a58  cmp     dword ptr [rdx+10h], 10000h
0x180030a5f  jz      short loc_180030A65
0x180030a61  inc     esi
0x180030a63  jmp     short loc_180030A1E
0x180030a65  cmp     [rdx+18h], r13d
0x180030a69  jnz     short loc_180030A61
0x180030a6b  add     rdx, 40h ; '@'; pvargSrc
0x180030a6f  lea     rcx, [rbp+57h+pvargDest]; pvargDest
0x180030a73  call    cs:__imp_VariantCopy
0x180030a79  mov     edi, eax
0x180030a7b  test    eax, eax
0x180030a7d  jns     loc_180030BD8
0x180030a83  cmp     edi, ebx
0x180030a85  jnz     loc_180030E60
0x180030a8b  xorps   xmm0, xmm0
0x180030a8e  xor     eax, eax
0x180030a90  movups  xmmword ptr [rbp+57h+pvargDest], xmm0
0x180030a94  mov     qword ptr [rbp+57h+pvargDest+10h], rax
0x180030a98  mov     edi, r13d
0x180030a9b  mov     rcx, [r14+28h]; hdsa
0x180030a9f  test    rcx, rcx
0x180030aa2  jz      loc_180030BB6
0x180030aa8  mov     eax, [rcx]
0x180030aaa  cmp     edi, eax
0x180030aac  jge     loc_180030B98
0x180030ab2  mov     edx, edi; i
0x180030ab4  call    cs:g_pfn_DSA_GetItemPtr
0x180030aba  mov     rcx, [rax]
0x180030abd  sub     rcx, qword ptr cs:DBPROPSET_DBINIT.Data1
0x180030ac4  jnz     short loc_180030AD1
0x180030ac6  mov     rcx, [rax+8]
0x180030aca  sub     rcx, qword ptr cs:DBPROPSET_DBINIT.Data4
0x180030ad1  test    rcx, rcx
0x180030ad4  jnz     short loc_180030ADF
0x180030ad6  cmp     dword ptr [rax+10h], 20000h
0x180030add  jz      short loc_180030AE3
0x180030adf  inc     edi
0x180030ae1  jmp     short loc_180030A9B
0x180030ae3  cmp     [rax+18h], r13d
0x180030ae7  jnz     short loc_180030ADF
0x180030ae9  lea     rdx, [rax+40h]; pvargSrc
0x180030aed  lea     rcx, [rbp+57h+pvargDest]; pvargDest
0x180030af1  call    cs:__imp_VariantCopy
0x180030af7  mov     ebx, eax
0x180030af9  test    eax, eax
0x180030afb  js      loc_180030B98
0x180030b01  mov     rcx, qword ptr [rbp+57h+pvargDest+8]
0x180030b05  mov     eax, 0Dh
0x180030b0a  mov     [rbp+57h+arg_0], r13
0x180030b0e  cmp     ax, word ptr [rbp+57h+pvargDest]
0x180030b12  jnz     loc_180030BBE
0x180030b18  test    rcx, rcx
0x180030b1b  jz      loc_180030BBE
0x180030b21  mov     rax, [rcx]
0x180030b24  lea     r8, [rbp+57h+arg_0]
0x180030b28  lea     rdx, _GUID_71604b0f_97b0_4764_8577_2f13e98a1422
0x180030b2f  mov     rax, [rax]
0x180030b32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b37  mov     ebx, eax
0x180030b39  test    eax, eax
0x180030b3b  js      short loc_180030B8E
0x180030b3d  mov     rcx, [rbp+57h+arg_0]
0x180030b41  lea     r8, [rbp+57h+pvar]
0x180030b45  xor     eax, eax
0x180030b47  mov     [r15], r13
0x180030b4a  mov     [rbp+57h+var_50], rax
0x180030b4e  lea     rdx, aScope_0; "Scope"
0x180030b55  xorps   xmm0, xmm0
0x180030b58  mov     rax, [rcx]
0x180030b5b  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180030b5f  mov     rax, [rax+18h]
0x180030b63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b68  test    eax, eax
0x180030b6a  jns     loc_180030E3E
0x180030b70  mov     rdx, [rbp+57h+arg_0]; struct INamedPropertyStore *
0x180030b74  mov     r8, r12; struct INamedPropertyStore **
0x180030b77  call    ?_CreateGrepQueryFactoryOptions@CGrepDataSource@@AEAAJPEAUINamedPropertyStore@@PEAPEAU2@@Z; CGrepDataSource::_CreateGrepQueryFactoryOptions(INamedPropertyStore *,INamedPropertyStore * *)
0x180030b7c  mov     rcx, [rbp+57h+arg_0]
0x180030b80  mov     ebx, eax
0x180030b82  mov     rax, [rcx]
0x180030b85  mov     rax, [rax+10h]
0x180030b89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b8e  lea     rcx, [rbp+57h+pvargDest]; pvarg
0x180030b92  call    cs:__imp_VariantClear
0x180030b98  mov     eax, ebx
0x180030b9a  add     rsp, 98h
0x180030ba1  pop     r15
0x180030ba3  pop     r14
0x180030ba5  pop     r13
0x180030ba7  pop     r12
0x180030ba9  pop     rdi
0x180030baa  pop     rsi
0x180030bab  pop     rbx
0x180030bac  pop     rbp
0x180030bad  retn
0x180030bae  mov     eax, r13d
0x180030bb1  jmp     loc_180030A2D
0x180030bb6  mov     eax, r13d
0x180030bb9  jmp     loc_180030AAA
0x180030bbe  mov     eax, 9
0x180030bc3  mov     ebx, 80004002h
0x180030bc8  cmp     ax, word ptr [rbp+57h+pvargDest]
0x180030bcc  jnz     short loc_180030B8E
0x180030bce  test    rcx, rcx
0x180030bd1  jz      short loc_180030B8E
0x180030bd3  jmp     loc_180030B21
0x180030bd8  mov     rcx, qword ptr [rbp+57h+pvargDest+8]
0x180030bdc  mov     eax, 0Dh
0x180030be1  mov     [rbp+57h+arg_10], r13
0x180030be5  cmp     ax, word ptr [rbp+57h+pvargDest]
0x180030be9  jnz     loc_180030DE9
0x180030bef  test    rcx, rcx
0x180030bf2  jz      loc_180030DE9
0x180030bf8  mov     rax, [rcx]
0x180030bfb  lea     r8, [rbp+57h+arg_10]
0x180030bff  lea     rdx, _GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9
0x180030c06  mov     rax, [rax]
0x180030c09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030c0e  mov     ebx, eax
0x180030c10  test    eax, eax
0x180030c12  js      loc_180030B8E
0x180030c18  lea     r9, [rbp+57h+punk]; void **
0x180030c1c  mov     [rbp+57h+punk], r13
0x180030c20  lea     r8, _GUID_655d1685_2bfd_4f7f_ad22_5ab61c8d8798; struct _GUID *
0x180030c27  mov     [rbp+57h+var_A0], r13
0x180030c2b  xor     edx, edx; struct ICompositionProcessor *
0x180030c2d  call    ?CScope_CreateInstance@@YAJPEAUIUnknown@@PEAUICompositionProcessor@@AEBU_GUID@@PEAPEAX@Z; CScope_CreateInstance(IUnknown *,ICompositionProcessor *,_GUID const &,void * *)
0x180030c32  mov     ebx, eax
0x180030c34  test    eax, eax
0x180030c36  js      loc_180030D77
0x180030c3c  mov     rcx, [rbp+57h+arg_10]
0x180030c40  lea     rdx, [rbp+57h+arg_8]
0x180030c44  mov     [rbp+57h+arg_8], r13d
0x180030c48  mov     rax, [rcx]
0x180030c4b  mov     rax, [rax+18h]
0x180030c4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030c54  mov     ebx, eax
0x180030c56  mov     esi, r13d
0x180030c59  cmp     [rbp+57h+arg_8], r13d
0x180030c5d  jbe     loc_180030D77
0x180030c63  test    ebx, ebx
0x180030c65  js      loc_180030D77
0x180030c6b  mov     rcx, [rbp+57h+arg_10]
0x180030c6f  lea     r9, [rbp+57h+var_90]
0x180030c73  mov     [rbp+57h+var_90], r13
0x180030c77  lea     r8, _GUID_71604b0f_97b0_4764_8577_2f13e98a1422
0x180030c7e  mov     edx, esi
0x180030c80  mov     rax, [rcx]
0x180030c83  mov     rax, [rax+20h]
0x180030c87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030c8c  mov     ebx, eax
0x180030c8e  test    eax, eax
0x180030c90  js      loc_180030D6C
0x180030c96  mov     rcx, [rbp+57h+var_90]
0x180030c9a  lea     r9, [rbp+57h+var_68]
0x180030c9e  mov     [rbp+57h+var_68], r13
0x180030ca2  call    GetObjectFromConfigPropStore
0x180030ca7  test    eax, eax
0x180030ca9  js      loc_180030D52
0x180030caf  mov     rcx, [rbp+57h+var_68]
0x180030cb3  lea     r9, [rbp+57h+var_98]
0x180030cb7  mov     [rbp+57h+var_98], r13
0x180030cbb  lea     r8, _GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9
0x180030cc2  mov     edx, 1000h
0x180030cc7  mov     rax, [rcx]
0x180030cca  mov     rax, [rax+40h]
0x180030cce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030cd3  mov     ebx, eax
0x180030cd5  test    eax, eax
0x180030cd7  js      short loc_180030D42
0x180030cd9  mov     rcx, [rbp+57h+var_98]
0x180030cdd  lea     rdx, [rbp+57h+arg_0]
0x180030ce1  mov     dword ptr [rbp+57h+arg_0], r13d
0x180030ce5  mov     rax, [rcx]
0x180030ce8  mov     rax, [rax+18h]
0x180030cec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030cf1  mov     ebx, eax
0x180030cf3  mov     edi, r13d
0x180030cf6  cmp     dword ptr [rbp+57h+arg_0], r13d
0x180030cfa  jbe     short loc_180030D32
0x180030cfc  test    ebx, ebx
0x180030cfe  js      short loc_180030D32
0x180030d00  mov     rcx, [rbp+57h+var_98]
0x180030d04  lea     r9, [rbp+57h+var_70]
0x180030d08  mov     [rbp+57h+var_70], r13
0x180030d0c  lea     r8, _GUID_dd400ff4_a119_405f_970e_a9a5e7e828c0
0x180030d13  mov     edx, edi
0x180030d15  mov     rax, [rcx]
0x180030d18  mov     rax, [rax+20h]
0x180030d1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030d21  mov     ebx, eax
0x180030d23  test    eax, eax
0x180030d25  jns     loc_180030DBE
0x180030d2b  inc     edi
0x180030d2d  cmp     edi, dword ptr [rbp+57h+arg_0]
0x180030d30  jb      short loc_180030CFC
0x180030d32  mov     rcx, [rbp+57h+var_98]
0x180030d36  mov     rax, [rcx]
0x180030d39  mov     rax, [rax+10h]
0x180030d3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030d42  mov     rcx, [rbp+57h+var_68]
0x180030d46  mov     rax, [rcx]
0x180030d49  mov     rax, [rax+10h]
0x180030d4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030d52  cmp     [rbp+57h+var_A0], r13
0x180030d56  jz      loc_180030E0B
0x180030d5c  mov     rcx, [rbp+57h+var_90]
0x180030d60  mov     rax, [rcx]
0x180030d63  mov     rax, [rax+10h]
0x180030d67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030d6c  inc     esi
0x180030d6e  cmp     esi, [rbp+57h+arg_8]
0x180030d71  jb      loc_180030C63
0x180030d77  mov     rcx, [rbp+57h+arg_10]
0x180030d7b  mov     rax, [rcx]
0x180030d7e  mov     rax, [rax+10h]
0x180030d82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030d87  test    ebx, ebx
0x180030d89  jns     loc_180030E1F
0x180030d8f  mov     rcx, [rbp+57h+punk]
0x180030d93  mov     [rbp+57h+punk], r13
0x180030d97  test    rcx, rcx
0x180030d9a  jz      short loc_180030DA8
0x180030d9c  mov     rax, [rcx]
0x180030d9f  mov     rax, [rax+10h]
0x180030da3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030da8  mov     rcx, [rbp+57h+var_A0]
0x180030dac  mov     [rbp+57h+var_A0], r13
0x180030db0  test    rcx, rcx
0x180030db3  jnz     loc_180030B82
0x180030db9  jmp     loc_180030B8E
0x180030dbe  mov     rcx, [rbp+57h+punk]
0x180030dc2  mov     rdx, [rbp+57h+var_70]
0x180030dc6  mov     rax, [rcx]
0x180030dc9  mov     rax, [rax+18h]
0x180030dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030dd2  mov     rcx, [rbp+57h+var_70]
0x180030dd6  mov     ebx, eax
0x180030dd8  mov     rax, [rcx]
0x180030ddb  mov     rax, [rax+10h]
0x180030ddf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030de4  jmp     loc_180030D2B
0x180030de9  mov     eax, 9
0x180030dee  mov     ebx, 80004002h
0x180030df3  cmp     ax, word ptr [rbp+57h+pvargDest]
0x180030df7  jnz     loc_180030B8E
0x180030dfd  test    rcx, rcx
0x180030e00  jz      loc_180030B8E
0x180030e06  jmp     loc_180030BF8
0x180030e0b  mov     rdx, [rbp+57h+var_90]; struct INamedPropertyStore *
0x180030e0f  lea     r8, [rbp+57h+var_A0]; struct INamedPropertyStore **
0x180030e13  call    ?_CreateGrepQueryFactoryOptions@CGrepDataSource@@AEAAJPEAUINamedPropertyStore@@PEAPEAU2@@Z; CGrepDataSource::_CreateGrepQueryFactoryOptions(INamedPropertyStore *,INamedPropertyStore * *)
0x180030e18  mov     ebx, eax
0x180030e1a  jmp     loc_180030D5C
0x180030e1f  mov     rdx, [rbp+57h+punk]; punk
0x180030e23  mov     rcx, r15; ppunk
0x180030e26  call    cs:__imp_IUnknown_Set
0x180030e2c  mov     rdx, [rbp+57h+var_A0]; punk
0x180030e30  mov     rcx, r12; ppunk
0x180030e33  call    cs:__imp_IUnknown_Set
0x180030e39  jmp     loc_180030D8F
  ... truncated ...
```
