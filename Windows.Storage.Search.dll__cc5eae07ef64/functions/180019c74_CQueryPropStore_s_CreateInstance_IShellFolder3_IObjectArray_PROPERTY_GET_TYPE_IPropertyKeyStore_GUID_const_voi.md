# CQueryPropStore::s_CreateInstance(IShellFolder3 *,IObjectArray *,PROPERTY_GET_TYPE,IPropertyKeyStore *,_GUID const &,void * *)

- ea: `0x180019c74`
- end: `0x180019ec5`
- name: `?s_CreateInstance@CQueryPropStore@@SAJPEAUIShellFolder3@@PEAUIObjectArray@@W4PROPERTY_GET_TYPE@@PEAUIPropertyKeyStore@@AEBU_GUID@@PEAPEAX@Z`
- size: `593`
- prototype: `static int __high(struct IShellFolder3 *, struct IObjectArray *, enum PROPERTY_GET_TYPE, struct IPropertyKeyStore *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x18008af5c`

## callees

- `0x180019c74`
- `0x180019f18`
- `0x18002e0ec`
- `0x180071df0`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IUnknown_Set` at `0x180019d97`
- `SHCORE!IUnknown_Set` at `0x180019d97`
- `Windows.Storage!ILFree` at `0x180019da1`
- `Windows.Storage!ILFree` at `0x180019da1`
- `Windows.Storage!SHGetIDListFromObject` at `0x180019d69`
- `Windows.Storage!SHGetIDListFromObject` at `0x180019d69`
- `Windows.Storage!SHCreateItemFromIDList` at `0x180019d84`
- `Windows.Storage!SHCreateItemFromIDList` at `0x180019d84`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x180019dbc`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x180019dbc`
- `PROPSYS!__imp_PSCreateAggregatePropertyProvider` at `0x180019e2f`
- `PROPSYS!__imp_PSCreateAggregatePropertyProvider` at `0x180019e2f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CQueryPropStore::s_CreateInstance(void *a1, void *a2, int a3, IUnknown *a4, IID *riid, void **ppv)
{
  void **v10; // r14
  HRESULT v11; // ebx
  void **v12; // rax
  void **v13; // rdi
  unsigned int v15; // esi
  __int64 v16; // [rsp+30h] [rbp-18h] BYREF
  LPITEMIDLIST ppidl[2]; // [rsp+38h] [rbp-10h] BYREF

  v10 = ppv;
  *ppv = 0;
  v11 = -2147024882;
  v12 = (void **)operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
  v13 = v12;
  ppv = v12;
  if ( v12 )
  {
    *v12 = &CQueryPropStore::`vftable'{for `IPropertyStoreCache'};
    v12[1] = &CQueryPropStore::`vftable'{for `IBatchedPropertyReader'};
    v12[2] = &CQueryPropStore::`vftable'{for `IObjectWithClassIdentity'};
    v12[3] = &CQueryPropStore::`vftable'{for `IObjectProvider'};
    *((_DWORD *)v12 + 8) = 1;
    *((_DWORD *)v12 + 9) = a3;
    v12[5] = a2;
    v12[11] = a1;
    _InterlockedIncrement(&g_cDllRef);
    (*(void (__fastcall **)(void *))(*(_QWORD *)v12[11] + 8LL))(v12[11]);
    (*(void (__fastcall **)(void *))(*(_QWORD *)v13[5] + 8LL))(v13[5]);
  }
  else
  {
    v13 = 0;
  }
  if ( v13 )
  {
    LODWORD(ppv) = 0;
    v11 = (*(__int64 (__fastcall **)(void *, void ***))(*(_QWORD *)v13[5] + 24LL))(v13[5], &ppv);
    if ( v11 >= 0 )
    {
      if ( (unsigned int)ppv <= 1 )
        goto LABEL_6;
      v16 = 0;
      v11 = PSCreateAggregatePropertyProvider(&GUID_b8158717_9161_46fd_b8d2_26d42185bc69, &v16);
      if ( v11 >= 0 )
      {
        v15 = 0;
        if ( (_DWORD)ppv )
        {
          while ( v11 >= 0 )
          {
            ppidl[0] = 0;
            v11 = (*(__int64 (__fastcall **)(void *, _QWORD, GUID *, LPITEMIDLIST *))(*(_QWORD *)v13[5] + 32LL))(
                    v13[5],
                    v15,
                    &GUID_656c5e34_f857_40d6_9d5c_9c5e6873e160,
                    ppidl);
            if ( v11 >= 0 )
            {
              v11 = (*(__int64 (__fastcall **)(__int64, LPITEMIDLIST))(*(_QWORD *)v16 + 24LL))(v16, ppidl[0]);
              (*(void (__fastcall **)(LPITEMIDLIST))(*(_QWORD *)ppidl[0] + 16LL))(ppidl[0]);
            }
            if ( ++v15 >= (unsigned int)ppv )
            {
              if ( v11 < 0 )
                break;
              goto LABEL_24;
            }
          }
        }
        else
        {
LABEL_24:
          v11 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64))v16)(
                  v16,
                  &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
                  (__int64)(v13 + 10));
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
        if ( v11 >= 0 )
        {
LABEL_6:
          ppidl[0] = 0;
          v11 = SHGetIDListFromObject((IUnknown *)v13[11], ppidl);
          if ( v11 >= 0 )
          {
            v11 = SHCreateItemFromIDList(ppidl[0], &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, v13 + 12);
            if ( v11 >= 0 )
              IUnknown_Set((IUnknown **)v13 + 9, a4);
            ILFree(ppidl[0]);
            if ( v11 >= 0 )
              v11 = QISearch(v13, &`CQueryPropStore::QueryInterface'::`2'::qit, riid, v10);
          }
        }
      }
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v13 + 8, 0xFFFFFFFF) == 1 )
    {
      CQueryPropStore::~CQueryPropStore((CQueryPropStore *)v13);
      operator delete(v13, (const struct std::nothrow_t *)0x68);
    }
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180019c74  push    rbp
0x180019c76  push    rbx
0x180019c77  push    rsi
0x180019c78  push    rdi
0x180019c79  push    r12
0x180019c7b  push    r13
0x180019c7d  push    r14
0x180019c7f  push    r15
0x180019c81  mov     rbp, rsp
0x180019c84  sub     rsp, 48h
0x180019c88  mov     r13, r9
0x180019c8b  mov     esi, r8d
0x180019c8e  mov     r15, rdx
0x180019c91  mov     r12, rcx
0x180019c94  mov     r14, [rbp+ppv]
0x180019c98  mov     qword ptr [r14], 0
0x180019c9f  mov     ebx, 8007000Eh
0x180019ca4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180019cab  mov     ecx, 68h ; 'h'; unsigned __int64
0x180019cb0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180019cb5  mov     rdi, rax
0x180019cb8  mov     [rbp+ppv], rax
0x180019cbc  test    rax, rax
0x180019cbf  jz      loc_180019DFB
0x180019cc5  lea     rax, ??_7CQueryPropStore@@6BIPropertyStoreCache@@@; const CQueryPropStore::`vftable'{for `IPropertyStoreCache'}
0x180019ccc  mov     [rdi], rax
0x180019ccf  lea     rax, ??_7CQueryPropStore@@6BIBatchedPropertyReader@@@; const CQueryPropStore::`vftable'{for `IBatchedPropertyReader'}
0x180019cd6  mov     [rdi+8], rax
0x180019cda  lea     rax, ??_7CQueryPropStore@@6BIObjectWithClassIdentity@@@; const CQueryPropStore::`vftable'{for `IObjectWithClassIdentity'}
0x180019ce1  mov     [rdi+10h], rax
0x180019ce5  lea     rax, ??_7CQueryPropStore@@6BIObjectProvider@@@; const CQueryPropStore::`vftable'{for `IObjectProvider'}
0x180019cec  mov     [rdi+18h], rax
0x180019cf0  mov     dword ptr [rdi+20h], 1
0x180019cf7  mov     [rdi+24h], esi
0x180019cfa  mov     [rdi+28h], r15
0x180019cfe  mov     [rdi+58h], r12
0x180019d02  lock inc cs:?g_cDllRef@@3JA; long g_cDllRef
0x180019d09  mov     rcx, [rdi+58h]
0x180019d0d  mov     rax, [rcx]
0x180019d10  mov     rax, [rax+8]
0x180019d14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d19  mov     rcx, [rdi+28h]
0x180019d1d  mov     rax, [rcx]
0x180019d20  mov     rax, [rax+8]
0x180019d24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d29  xor     r15d, r15d
0x180019d2c  test    rdi, rdi
0x180019d2f  jz      loc_180019DD1
0x180019d35  mov     dword ptr [rbp+ppv], r15d
0x180019d39  mov     rcx, [rdi+28h]
0x180019d3d  mov     rax, [rcx]
0x180019d40  lea     rdx, [rbp+ppv]
0x180019d44  mov     rax, [rax+18h]
0x180019d48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d4d  mov     ebx, eax
0x180019d4f  test    eax, eax
0x180019d51  js      short loc_180019DC4
0x180019d53  cmp     dword ptr [rbp+ppv], 1
0x180019d57  ja      loc_180019E20
0x180019d5d  mov     [rbp+ppidl], r15
0x180019d61  lea     rdx, [rbp+ppidl]; ppidl
0x180019d65  mov     rcx, [rdi+58h]; punk
0x180019d69  call    cs:__imp_SHGetIDListFromObject
0x180019d6f  mov     ebx, eax
0x180019d71  test    eax, eax
0x180019d73  js      short loc_180019DC4
0x180019d75  lea     r8, [rdi+60h]; ppv
0x180019d79  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180019d80  mov     rcx, [rbp+ppidl]; pidl
0x180019d84  call    cs:__imp_SHCreateItemFromIDList
0x180019d8a  mov     ebx, eax
0x180019d8c  test    eax, eax
0x180019d8e  js      short loc_180019D9D
0x180019d90  lea     rcx, [rdi+48h]; ppunk
0x180019d94  mov     rdx, r13; punk
0x180019d97  call    cs:__imp_IUnknown_Set
0x180019d9d  mov     rcx, [rbp+ppidl]; pidl
0x180019da1  call    cs:__imp_ILFree
0x180019da7  test    ebx, ebx
0x180019da9  js      short loc_180019DC4
0x180019dab  mov     r9, r14; ppv
0x180019dae  mov     r8, [rbp+riid]; riid
0x180019db2  lea     rdx, ?qit@?1??QueryInterface@CQueryPropStore@@UEAAJAEBU_GUID@@PEAPEAX@Z@4QBUQITAB@@B; pqit
0x180019db9  mov     rcx, rdi; that
0x180019dbc  call    cs:__imp_QISearch
0x180019dc2  mov     ebx, eax
0x180019dc4  or      eax, 0FFFFFFFFh
0x180019dc7  lock xadd [rdi+20h], eax
0x180019dcc  cmp     eax, 1
0x180019dcf  jz      short loc_180019DE4
0x180019dd1  mov     eax, ebx
0x180019dd3  add     rsp, 48h
0x180019dd7  pop     r15
0x180019dd9  pop     r14
0x180019ddb  pop     r13
0x180019ddd  pop     r12
0x180019ddf  pop     rdi
0x180019de0  pop     rsi
0x180019de1  pop     rbx
0x180019de2  pop     rbp
0x180019de3  retn
0x180019de4  mov     rcx, rdi; this
0x180019de7  call    ??1CQueryPropStore@@AEAA@XZ; CQueryPropStore::~CQueryPropStore(void)
0x180019dec  mov     edx, 68h ; 'h'; struct std::nothrow_t *
0x180019df1  mov     rcx, rdi; void *
0x180019df4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180019df9  jmp     short loc_180019DD1
0x180019dfb  xor     r15d, r15d
0x180019dfe  mov     edi, r15d
0x180019e01  jmp     loc_180019D2C
0x180019e06  mov     rcx, [rbp+var_18]
0x180019e0a  mov     rax, [rcx]
0x180019e0d  mov     rax, [rax+10h]
0x180019e11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e16  test    ebx, ebx
0x180019e18  jns     loc_180019D5D
0x180019e1e  jmp     short loc_180019DC4
0x180019e20  mov     [rbp+var_18], r15
0x180019e24  lea     rdx, [rbp+var_18]
0x180019e28  lea     rcx, _GUID_b8158717_9161_46fd_b8d2_26d42185bc69
0x180019e2f  call    cs:__imp_PSCreateAggregatePropertyProvider
0x180019e35  mov     ebx, eax
0x180019e37  test    eax, eax
0x180019e39  js      short loc_180019DC4
0x180019e3b  mov     esi, r15d
0x180019e3e  cmp     dword ptr [rbp+ppv], r15d
0x180019e42  jbe     short loc_180019EA4
0x180019e44  test    ebx, ebx
0x180019e46  js      short loc_180019E06
0x180019e48  mov     [rbp+ppidl], r15
0x180019e4c  mov     rcx, [rdi+28h]
0x180019e50  mov     rax, [rcx]
0x180019e53  lea     r9, [rbp+ppidl]
0x180019e57  lea     r8, _GUID_656c5e34_f857_40d6_9d5c_9c5e6873e160
0x180019e5e  mov     edx, esi
0x180019e60  mov     rax, [rax+20h]
0x180019e64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e69  mov     ebx, eax
0x180019e6b  test    eax, eax
0x180019e6d  js      short loc_180019E95
0x180019e6f  mov     rcx, [rbp+var_18]
0x180019e73  mov     rax, [rcx]
0x180019e76  mov     rdx, [rbp+ppidl]
0x180019e7a  mov     rax, [rax+18h]
0x180019e7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e83  mov     ebx, eax
0x180019e85  mov     rcx, [rbp+ppidl]
0x180019e89  mov     rax, [rcx]
0x180019e8c  mov     rax, [rax+10h]
0x180019e90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e95  inc     esi
0x180019e97  cmp     esi, dword ptr [rbp+ppv]
0x180019e9a  jb      short loc_180019E44
0x180019e9c  test    ebx, ebx
0x180019e9e  js      loc_180019E06
0x180019ea4  mov     rcx, [rbp+var_18]
0x180019ea8  mov     rax, [rcx]
0x180019eab  lea     r8, [rdi+50h]
0x180019eaf  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x180019eb6  mov     rax, [rax]
0x180019eb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ebe  mov     ebx, eax
0x180019ec0  jmp     loc_180019E06
```
