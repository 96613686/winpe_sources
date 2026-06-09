# CQueryResult::Initialize(IShellItem *,ulong)

- ea: `0x18004ef90`
- end: `0x18004f199`
- name: `?Initialize@CQueryResult@@UEAAJPEAUIShellItem@@K@Z`
- size: `521`
- prototype: `__int64 __fastcall(CQueryResult *__hidden this, struct IShellItem *, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001c9a8`
- `0x18001c9e0`
- `0x18004ef90`
- `0x180063a68`
- `0x180071df0`
- `0x1800b4054`
- `0x1800ea010`

## import_xrefs

- `Windows.Storage!ILFree` at `0x18004f13d`
- `Windows.Storage!ILFree` at `0x18004f13d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f157`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f157`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x18004f12b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x18004f12b`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18004efba`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18004efba`

## pseudocode

```c
__int64 __fastcall CQueryResult::Initialize(CQueryResult *this, struct IShellItem *a2)
{
  int v4; // ebx
  struct IShellItemVtbl *lpVtbl; // rax
  struct IShellItemVtbl *v6; // rax
  CChildId *v7; // rax
  CChildId *v8; // rax
  CChildId *v9; // rdi
  int v11; // [rsp+20h] [rbp-29h]
  void *ppv; // [rsp+50h] [rbp+7h] BYREF
  __int64 v13; // [rsp+58h] [rbp+Fh] BYREF
  LPVOID pv; // [rsp+60h] [rbp+17h] BYREF
  _QWORD v15[7]; // [rsp+68h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]
  LPITEMIDLIST pidl; // [rsp+C8h] [rbp+7Fh] BYREF

  ppv = 0;
  v4 = PSCreateMemoryPropertyStore(&GUID_3017056d_9a91_4e90_937d_746c72abbf4f, &ppv);
  if ( v4 < 0 )
    goto LABEL_15;
  lpVtbl = a2->lpVtbl;
  pv = 0;
  v4 = ((__int64 (__fastcall *)(struct IShellItem *, __int64, LPVOID *))lpVtbl->GetDisplayName)(a2, 2147647488LL, &pv);
  if ( v4 >= 0 )
  {
    v15[2] = 0;
    v15[0] = 31;
    v15[1] = pv;
    v4 = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, _QWORD *))(*(_QWORD *)ppv + 48LL))(
           ppv,
           &PKEY_ItemId,
           v15);
    if ( v4 >= 0 )
    {
      v4 = CQueryResult::_InitializeResultWithStore(
             (__int64)this - 32,
             1u,
             (__int64)&PKEY_ResultSourceId,
             (__int64)&GUID_1685d4ab_a51b_4af1_a4e5_cee87002431d,
             (__int64)L"Merge Any",
             64,
             0,
             (IUnknown *)ppv,
             0);
      if ( v4 >= 0 )
      {
        v6 = a2->lpVtbl;
        v13 = 0;
        if ( ((__int64 (__fastcall *)(struct IShellItem *, GUID *, __int64 *))v6->QueryInterface)(
               a2,
               &GUID_b3a4b685_b685_4805_99d9_5dead2873236,
               &v13) >= 0 )
        {
          pidl = 0;
          if ( (*(int (__fastcall **)(__int64, _QWORD, _QWORD, LPITEMIDLIST *))(*(_QWORD *)v13 + 32LL))(
                 v13,
                 0,
                 0,
                 &pidl) >= 0 )
          {
            *((_QWORD *)this + 10) = 0;
            v7 = (CChildId *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
            if ( v7 )
            {
              v8 = CChildId::CChildId(v7);
              v9 = v8;
              if ( v8 )
              {
                *((_QWORD *)v8 + 2) = pidl;
                pidl = 0;
                QISearch(
                  v8,
                  &`CChildId::QueryInterface'::`2'::qit,
                  &GUID_c412bf5b_91ea_4904_b34a_855504fbbf0b,
                  (void **)this + 10);
                CChildId::Release(v9);
              }
            }
            ILFree(pidl);
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        }
      }
    }
    CoTaskMemFree(pv);
  }
  (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v4 < 0 )
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5B,
      (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
      (const char *)(unsigned int)v4,
      v11);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18004ef90  push    rbp
0x18004ef92  push    rbx
0x18004ef93  push    rsi
0x18004ef94  push    rdi
0x18004ef95  lea     rbp, [rsp-3Fh]
0x18004ef9a  sub     rsp, 88h
0x18004efa1  mov     rdi, rdx
0x18004efa4  mov     [rbp+57h+ppv], 0
0x18004efac  mov     rsi, rcx
0x18004efaf  lea     rdx, [rbp+57h+ppv]; ppv
0x18004efb3  lea     rcx, _GUID_3017056d_9a91_4e90_937d_746c72abbf4f; riid
0x18004efba  call    cs:__imp_PSCreateMemoryPropertyStore
0x18004efc0  mov     ebx, eax
0x18004efc2  test    eax, eax
0x18004efc4  js      loc_18004F17F
0x18004efca  mov     rax, [rdi]
0x18004efcd  lea     r8, [rbp+57h+pv]
0x18004efd1  mov     edx, 80028000h
0x18004efd6  mov     [rbp+57h+pv], 0
0x18004efde  mov     rcx, rdi
0x18004efe1  mov     rax, [rax+28h]
0x18004efe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004efea  mov     ebx, eax
0x18004efec  test    eax, eax
0x18004efee  js      loc_18004F15D
0x18004eff4  mov     rcx, [rbp+57h+ppv]
0x18004eff8  lea     r8, [rbp+57h+var_38]
0x18004effc  xor     eax, eax
0x18004effe  lea     rdx, PKEY_ItemId
0x18004f005  mov     [rbp+57h+var_28], rax
0x18004f009  xorps   xmm0, xmm0
0x18004f00c  movups  [rbp+57h+var_38], xmm0
0x18004f010  mov     eax, 1Fh
0x18004f015  mov     word ptr [rbp+57h+var_38], ax
0x18004f019  mov     rax, [rbp+57h+pv]
0x18004f01d  mov     qword ptr [rbp+57h+var_38+8], rax
0x18004f021  mov     rax, [rcx]
0x18004f024  mov     rax, [rax+30h]
0x18004f028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f02d  mov     ebx, eax
0x18004f02f  test    eax, eax
0x18004f031  js      loc_18004F153
0x18004f037  mov     rax, [rbp+57h+ppv]
0x18004f03b  lea     rcx, [rsi-20h]
0x18004f03f  mov     [rsp+0A0h+var_60], 0
0x18004f047  lea     r9, _GUID_1685d4ab_a51b_4af1_a4e5_cee87002431d
0x18004f04e  mov     [rsp+0A0h+var_68], rax
0x18004f053  lea     r8, PKEY_ResultSourceId
0x18004f05a  mov     [rsp+0A0h+var_70], 0
0x18004f062  lea     rax, aMergeAny; "Merge Any"
0x18004f069  mov     [rsp+0A0h+var_78], 40h ; '@'
0x18004f071  mov     edx, 1
0x18004f076  mov     [rsp+0A0h+var_80], rax
0x18004f07b  call    ?_InitializeResultWithStore@CQueryResult@@AEAAJW4QUERY_RESULT_TYPE@@AEBU_tagpropertykey@@AEBU_GUID@@PEBGW4PROVIDER_CAPABILITIES@@W4STACK_ITEMID_MODE@@PEAUIPropertyStoreCache@@W4QR_CMP_FLAGS@@@Z; CQueryResult::_InitializeResultWithStore(QUERY_RESULT_TYPE,_tagpropertykey const &,_GUID const &,ushort const *,PROVIDER_CAPABILITIES,STACK_ITEMID_MODE,IPropertyStoreCache *,QR_CMP_FLAGS)
0x18004f080  mov     ebx, eax
0x18004f082  test    eax, eax
0x18004f084  js      loc_18004F153
0x18004f08a  mov     rax, [rdi]
0x18004f08d  lea     r8, [rbp+57h+var_48]
0x18004f091  lea     rdx, _GUID_b3a4b685_b685_4805_99d9_5dead2873236
0x18004f098  mov     [rbp+57h+var_48], 0
0x18004f0a0  mov     rcx, rdi
0x18004f0a3  mov     rax, [rax]
0x18004f0a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f0ab  test    eax, eax
0x18004f0ad  js      loc_18004F153
0x18004f0b3  mov     rcx, [rbp+57h+var_48]
0x18004f0b7  lea     r9, [rbp+57h+pidl]
0x18004f0bb  mov     [rbp+57h+pidl], 0
0x18004f0c3  xor     r8d, r8d
0x18004f0c6  xor     edx, edx
0x18004f0c8  mov     rax, [rcx]
0x18004f0cb  mov     rax, [rax+20h]
0x18004f0cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f0d4  test    eax, eax
0x18004f0d6  js      short loc_18004F143
0x18004f0d8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004f0df  mov     qword ptr [rsi+50h], 0
0x18004f0e7  mov     ecx, 18h; unsigned __int64
0x18004f0ec  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004f0f1  test    rax, rax
0x18004f0f4  jz      short loc_18004F139
0x18004f0f6  mov     rcx, rax; this
0x18004f0f9  call    ??0CChildId@@QEAA@XZ; CChildId::CChildId(void)
0x18004f0fe  mov     rdi, rax
0x18004f101  test    rax, rax
0x18004f104  jz      short loc_18004F139
0x18004f106  mov     rcx, [rbp+57h+pidl]
0x18004f10a  lea     r9, [rsi+50h]; ppv
0x18004f10e  mov     [rax+10h], rcx
0x18004f112  lea     r8, _GUID_c412bf5b_91ea_4904_b34a_855504fbbf0b; riid
0x18004f119  mov     rcx, rax; that
0x18004f11c  mov     [rbp+57h+pidl], 0
0x18004f124  lea     rdx, ?qit@?1??QueryInterface@CChildId@@UEAAJAEBU_GUID@@PEAPEAX@Z@4QBUQITAB@@B; pqit
0x18004f12b  call    cs:__imp_QISearch
0x18004f131  mov     rcx, rdi; this
0x18004f134  call    ?Release@CChildId@@UEAAKXZ; CChildId::Release(void)
0x18004f139  mov     rcx, [rbp+57h+pidl]; pidl
0x18004f13d  call    cs:__imp_ILFree
0x18004f143  mov     rcx, [rbp+57h+var_48]
0x18004f147  mov     rax, [rcx]
0x18004f14a  mov     rax, [rax+10h]
0x18004f14e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f153  mov     rcx, [rbp+57h+pv]; pv
0x18004f157  call    cs:__imp_CoTaskMemFree
0x18004f15d  mov     rcx, [rbp+57h+ppv]
0x18004f161  mov     rax, [rcx]
0x18004f164  mov     rax, [rax+10h]
0x18004f168  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f16d  test    ebx, ebx
0x18004f16f  js      short loc_18004F17F
0x18004f171  mov     eax, ebx
0x18004f173  add     rsp, 88h
0x18004f17a  pop     rdi
0x18004f17b  pop     rsi
0x18004f17c  pop     rbx
0x18004f17d  pop     rbp
0x18004f17e  retn
0x18004f17f  mov     rcx, [rbp+5Fh]; this
0x18004f183  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.storage.sear"...
0x18004f18a  mov     r9d, ebx; char *
0x18004f18d  mov     edx, 0A5Bh; void *
0x18004f192  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f197  jmp     short loc_18004F171
```
