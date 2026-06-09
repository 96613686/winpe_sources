# SHCreateSearchIDListFromAutoList

- ea: `0x180005bf0`
- end: `0x180005f9d`
- name: `SHCreateSearchIDListFromAutoList`
- size: `941`
- prototype: `__int64 __fastcall(struct IAutoListDescription *)`
- caller_count: `6`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800055f0`
- `0x180078d00`
- `0x18008d408`
- `0x1800bbcf4`
- `0x1800bd860`
- `0x1800beab0`

## callees

- `0x180005bf0`
- `0x180006200`
- `0x1800062b4`
- `0x180006478`
- `0x180006c80`
- `0x180006d74`
- `0x180071dc0`
- `0x180071df0`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IStream_Reset` at `0x180005db0`
- `SHCORE!IStream_Reset` at `0x180005db0`
- `SHCORE!SHCreateMemStream` at `0x180005d02`
- `SHCORE!SHCreateMemStream` at `0x180005d02`
- `SHCORE!IStream_Write` at `0x180005d6e`
- `SHCORE!IStream_Write` at `0x180005d6e`
- `Windows.Storage!SHParseDisplayName` at `0x180005eca`
- `Windows.Storage!SHParseDisplayName` at `0x180005eca`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005ef5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005ef5`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x180005cc9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x180005cc9`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180005c36`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180005c36`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x180005e3d`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x180005e3d`

## pseudocode

```c
__int64 __fastcall SHCreateSearchIDListFromAutoList(struct IAutoListDescription *a1, __int64 a2, LPITEMIDLIST *a3)
{
  HRESULT v6; // ebx
  _QWORD *v7; // rax
  void *v8; // rdi
  __int64 v9; // rcx
  IStream *v10; // r14
  CDummyUnknown *v11; // r15
  LPBC v12; // rbx
  IBindCtx *v13; // rsi
  CDummyUnknown *v14; // rdi
  CDummyUnknown *v16; // rax
  CDummyUnknown *v17; // rax
  LPBC ppbc; // [rsp+30h] [rbp-50h] BYREF
  void *ppv; // [rsp+38h] [rbp-48h] BYREF
  void *v20; // [rsp+40h] [rbp-40h] BYREF
  PROPVARIANT pvar[2]; // [rsp+48h] [rbp-38h] BYREF
  __int64 v22; // [rsp+58h] [rbp-28h]
  __int128 pv; // [rsp+60h] [rbp-20h] BYREF

  *a3 = 0;
  ppv = 0;
  v6 = PSCreateMemoryPropertyStore(&GUID_71604b0f_97b0_4764_8577_2f13e98a1422, &ppv);
  if ( v6 >= 0 )
  {
    CacheBinaryAutoList(a1, (struct INamedPropertyStore *)ppv);
    v20 = 0;
    v6 = -2147024882;
    v7 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
    v8 = v7;
    if ( !v7 )
      goto LABEL_28;
    *((_DWORD *)v7 + 4) = 1;
    *v7 = &CBinaryAutoList::`vftable'{for `IObjectWithListDescription'};
    v7[1] = &CBinaryAutoList::`vftable'{for `IPersistStream'};
    v7[3] = 0;
    _InterlockedIncrement(&g_cDllRef);
    v9 = v7[3];
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
    v6 = QISearch(v8, &`CBinaryAutoList::QueryInterface'::`2'::qit, &GUID_c9b7f729_33b5_4ab8_acdd_fd0a999d790e, &v20);
    CBinaryAutoList::Release((CBinaryAutoList *)v8);
    if ( v6 < 0 )
      goto LABEL_28;
    v6 = (*(__int64 (__fastcall **)(void *, struct IAutoListDescription *))(*(_QWORD *)v20 + 32LL))(v20, a1);
    if ( v6 < 0 )
    {
LABEL_27:
      (*(void (__fastcall **)(void *))(*(_QWORD *)v20 + 16LL))(v20);
LABEL_28:
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
      return (unsigned int)v6;
    }
    v10 = SHCreateMemStream(0, 0);
    if ( !v10 )
    {
      v6 = -2147024882;
      goto LABEL_27;
    }
    ppbc = 0;
    v6 = (**(__int64 (__fastcall ***)(void *, GUID *, LPBC *))v20)(
           v20,
           &GUID_00000109_0000_0000_c000_000000000046,
           &ppbc);
    if ( v6 < 0 )
      goto LABEL_26;
    pv = 0;
    v6 = ((__int64 (__fastcall *)(LPBC, __int128 *))ppbc->lpVtbl->RegisterObjectBound)(ppbc, &pv);
    if ( v6 >= 0 )
    {
      v6 = IStream_Write(v10, &pv, 0x10u);
      if ( v6 >= 0 )
        v6 = ((__int64 (__fastcall *)(LPBC, IStream *, __int64))ppbc->lpVtbl->SetBindOptions)(ppbc, v10, 1);
    }
    ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
    if ( v6 < 0 )
    {
LABEL_26:
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)v10 + 16LL))(v10);
      goto LABEL_27;
    }
    IStream_Reset(v10);
    v22 = 0;
    pvar[0] = (PROPVARIANT)66;
    pvar[1] = v10;
    (*(void (__fastcall **)(IStream *))(*(_QWORD *)v10 + 8LL))(v10);
    v6 = (*(__int64 (__fastcall **)(void *, const WCHAR *, PROPVARIANT *))(*(_QWORD *)ppv + 32LL))(
           ppv,
           L"AutoList",
           pvar);
    if ( v6 < 0 || (*(_QWORD *)&pv = 0, v6 = SHMergePropertyStores(ppv, a2), v6 < 0) )
    {
LABEL_25:
      PropVariantClear(pvar);
      goto LABEL_26;
    }
    v11 = (CDummyUnknown *)pv;
    ppbc = 0;
    v6 = CreateBindCtx(0, &ppbc);
    if ( v6 < 0 )
    {
LABEL_24:
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)pv + 16LL))(pv);
      goto LABEL_25;
    }
    v12 = ppbc;
    v13 = 0;
    if ( v11 )
    {
      v14 = 0;
    }
    else
    {
      v16 = (CDummyUnknown *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
      if ( !v16 || (v17 = CDummyUnknown::CDummyUnknown(v16), (v14 = v17) == 0) )
      {
        v6 = -2147024882;
LABEL_22:
        ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
        if ( v6 >= 0 )
        {
          v6 = SHParseDisplayName(L"::{04731B67-D933-450a-90E6-4ACD2E9408FE},", v13, a3, 0, 0);
          ((void (__fastcall *)(IBindCtx *))v13->lpVtbl->Release)(v13);
        }
        goto LABEL_24;
      }
      v11 = v17;
    }
    v6 = ((__int64 (__fastcall *)(LPBC, const wchar_t *, CDummyUnknown *))v12->lpVtbl->RegisterObjectParam)(
           v12,
           L"DelegateNamedProperties",
           v11);
    if ( v14 )
      CDummyUnknown::Release(v14);
    if ( v6 >= 0 )
    {
      v13 = ppbc;
      ((void (__fastcall *)(LPBC))ppbc->lpVtbl->AddRef)(ppbc);
    }
    goto LABEL_22;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180005bf0  push    rbp
0x180005bf2  push    rbx
0x180005bf3  push    rsi
0x180005bf4  push    rdi
0x180005bf5  push    r12
0x180005bf7  push    r14
0x180005bf9  push    r15
0x180005bfb  mov     rbp, rsp
0x180005bfe  sub     rsp, 80h
0x180005c05  mov     rax, cs:__security_cookie
0x180005c0c  xor     rax, rsp
0x180005c0f  mov     [rbp+var_10], rax
0x180005c13  mov     r15, rdx
0x180005c16  mov     qword ptr [r8], 0
0x180005c1d  mov     rsi, rcx
0x180005c20  mov     [rbp+ppv], 0
0x180005c28  lea     rdx, [rbp+ppv]; ppv
0x180005c2c  mov     r12, r8
0x180005c2f  lea     rcx, _GUID_71604b0f_97b0_4764_8577_2f13e98a1422; riid
0x180005c36  call    cs:__imp_PSCreateMemoryPropertyStore
0x180005c3c  mov     ebx, eax
0x180005c3e  test    eax, eax
0x180005c40  js      loc_180005F2A
0x180005c46  mov     rdx, [rbp+ppv]; struct INamedPropertyStore *
0x180005c4a  mov     rcx, rsi; struct IAutoListDescription *
0x180005c4d  call    ?CacheBinaryAutoList@@YAXPEAUIAutoListDescription@@PEAUINamedPropertyStore@@@Z; CacheBinaryAutoList(IAutoListDescription *,INamedPropertyStore *)
0x180005c52  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005c59  mov     [rbp+var_40], 0
0x180005c61  mov     ecx, 28h ; '('; unsigned __int64
0x180005c66  mov     ebx, 8007000Eh
0x180005c6b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180005c70  mov     rdi, rax
0x180005c73  test    rax, rax
0x180005c76  jz      loc_180005F1A
0x180005c7c  lea     rax, ??_7CBinaryAutoList@@6BIObjectWithListDescription@@@; const CBinaryAutoList::`vftable'{for `IObjectWithListDescription'}
0x180005c83  mov     dword ptr [rdi+10h], 1
0x180005c8a  mov     [rdi], rax
0x180005c8d  lea     rax, ??_7CBinaryAutoList@@6BIPersistStream@@@; const CBinaryAutoList::`vftable'{for `IPersistStream'}
0x180005c94  mov     [rdi+8], rax
0x180005c98  mov     qword ptr [rdi+18h], 0
0x180005ca0  lock inc cs:?g_cDllRef@@3JA; long g_cDllRef
0x180005ca7  mov     rcx, [rdi+18h]
0x180005cab  test    rcx, rcx
0x180005cae  jnz     loc_180005F82
0x180005cb4  lea     r9, [rbp+var_40]; ppv
0x180005cb8  mov     rcx, rdi; that
0x180005cbb  lea     r8, _GUID_c9b7f729_33b5_4ab8_acdd_fd0a999d790e; riid
0x180005cc2  lea     rdx, ?qit@?1??QueryInterface@CBinaryAutoList@@UEAAJAEBU_GUID@@PEAPEAX@Z@4QBUQITAB@@B; pqit
0x180005cc9  call    cs:__imp_QISearch
0x180005ccf  mov     rcx, rdi; this
0x180005cd2  mov     ebx, eax
0x180005cd4  call    ?Release@CBinaryAutoList@@UEAAKXZ; CBinaryAutoList::Release(void)
0x180005cd9  test    ebx, ebx
0x180005cdb  js      loc_180005F1A
0x180005ce1  mov     rcx, [rbp+var_40]
0x180005ce5  mov     rdx, rsi
0x180005ce8  mov     rax, [rcx]
0x180005ceb  mov     rax, [rax+20h]
0x180005cef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cf4  mov     ebx, eax
0x180005cf6  test    eax, eax
0x180005cf8  js      loc_180005F0A
0x180005cfe  xor     edx, edx; cbInit
0x180005d00  xor     ecx, ecx; pInit
0x180005d02  call    cs:__imp_SHCreateMemStream
0x180005d08  mov     r14, rax
0x180005d0b  test    rax, rax
0x180005d0e  jz      loc_180005F93
0x180005d14  mov     rcx, [rbp+var_40]
0x180005d18  lea     r8, [rbp+ppbc]
0x180005d1c  lea     rdx, _GUID_00000109_0000_0000_c000_000000000046
0x180005d23  mov     [rbp+ppbc], 0
0x180005d2b  mov     rax, [rcx]
0x180005d2e  mov     rax, [rax]
0x180005d31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d36  mov     ebx, eax
0x180005d38  test    eax, eax
0x180005d3a  js      loc_180005EFB
0x180005d40  mov     rcx, [rbp+ppbc]
0x180005d44  lea     rdx, [rbp+pv]
0x180005d48  xorps   xmm0, xmm0
0x180005d4b  movups  [rbp+pv], xmm0
0x180005d4f  mov     rax, [rcx]
0x180005d52  mov     rax, [rax+18h]
0x180005d56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d5b  mov     ebx, eax
0x180005d5d  test    eax, eax
0x180005d5f  js      short loc_180005D95
0x180005d61  mov     r8d, 10h; cb
0x180005d67  lea     rdx, [rbp+pv]; pv
0x180005d6b  mov     rcx, r14; pstm
0x180005d6e  call    cs:__imp_IStream_Write
0x180005d74  mov     ebx, eax
0x180005d76  test    eax, eax
0x180005d78  js      short loc_180005D95
0x180005d7a  mov     rcx, [rbp+ppbc]
0x180005d7e  mov     r8d, 1
0x180005d84  mov     rdx, r14
0x180005d87  mov     rax, [rcx]
0x180005d8a  mov     rax, [rax+30h]
0x180005d8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d93  mov     ebx, eax
0x180005d95  mov     rcx, [rbp+ppbc]
0x180005d99  mov     rax, [rcx]
0x180005d9c  mov     rax, [rax+10h]
0x180005da0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005da5  test    ebx, ebx
0x180005da7  js      loc_180005EFB
0x180005dad  mov     rcx, r14; pstm
0x180005db0  call    cs:__imp_IStream_Reset
0x180005db6  xor     eax, eax
0x180005db8  xorps   xmm0, xmm0
0x180005dbb  mov     [rbp+var_28], rax
0x180005dbf  mov     rcx, r14
0x180005dc2  movups  xmmword ptr [rbp+pvar], xmm0
0x180005dc6  mov     eax, 42h ; 'B'
0x180005dcb  mov     [rbp+pvar+8], r14
0x180005dcf  mov     word ptr [rbp+pvar], ax
0x180005dd3  mov     rax, [r14]
0x180005dd6  mov     rax, [rax+8]
0x180005dda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ddf  mov     rcx, [rbp+ppv]
0x180005de3  lea     r8, [rbp+pvar]
0x180005de7  lea     rdx, propName; "AutoList"
0x180005dee  mov     rax, [rcx]
0x180005df1  mov     rax, [rax+20h]
0x180005df5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dfa  mov     ebx, eax
0x180005dfc  test    eax, eax
0x180005dfe  js      loc_180005EF1
0x180005e04  mov     rcx, [rbp+ppv]
0x180005e08  lea     rax, [rbp+pv]
0x180005e0c  mov     rdx, r15
0x180005e0f  mov     [rsp+80h+psfgaoOut], rax
0x180005e14  mov     qword ptr [rbp+pv], 0
0x180005e1c  call    ?SHMergePropertyStores@@YAJPEAUIUnknown@@0W4_MPS_FLAGS@@AEBU_GUID@@PEAPEAX@Z; SHMergePropertyStores(IUnknown *,IUnknown *,_MPS_FLAGS,_GUID const &,void * *)
0x180005e21  mov     ebx, eax
0x180005e23  test    eax, eax
0x180005e25  js      loc_180005EF1
0x180005e2b  mov     r15, qword ptr [rbp+pv]
0x180005e2f  lea     rdx, [rbp+ppbc]; ppbc
0x180005e33  xor     ecx, ecx; reserved
0x180005e35  mov     [rbp+ppbc], 0
0x180005e3d  call    cs:__imp_CreateBindCtx
0x180005e43  mov     ebx, eax
0x180005e45  test    eax, eax
0x180005e47  js      loc_180005EE1
0x180005e4d  mov     rbx, [rbp+ppbc]
0x180005e51  xor     esi, esi
0x180005e53  test    r15, r15
0x180005e56  jz      loc_180005F4A
0x180005e5c  xor     edi, edi
0x180005e5e  mov     rax, [rbx]
0x180005e61  lea     rdx, aDelegatenamedp; "DelegateNamedProperties"
0x180005e68  mov     r8, r15
0x180005e6b  mov     rcx, rbx
0x180005e6e  mov     rax, [rax+48h]
0x180005e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e77  mov     ebx, eax
0x180005e79  test    rdi, rdi
0x180005e7c  jz      short loc_180005E86
0x180005e7e  mov     rcx, rdi; this
0x180005e81  call    ?Release@CDummyUnknown@@UEAAKXZ; CDummyUnknown::Release(void)
0x180005e86  test    ebx, ebx
0x180005e88  js      short loc_180005E9D
0x180005e8a  mov     rsi, [rbp+ppbc]
0x180005e8e  mov     rcx, rsi
0x180005e91  mov     rax, [rsi]
0x180005e94  mov     rax, [rax+8]
0x180005e98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e9d  mov     rcx, [rbp+ppbc]
0x180005ea1  mov     rax, [rcx]
0x180005ea4  mov     rax, [rax+10h]
0x180005ea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ead  test    ebx, ebx
0x180005eaf  js      short loc_180005EE1
0x180005eb1  xor     r9d, r9d; sfgaoIn
0x180005eb4  mov     [rsp+80h+psfgaoOut], 0; psfgaoOut
0x180005ebd  mov     r8, r12; ppidl
0x180005ec0  lea     rcx, pszName; "::{04731B67-D933-450a-90E6-4ACD2E9408FE"...
0x180005ec7  mov     rdx, rsi; pbc
0x180005eca  call    cs:__imp_SHParseDisplayName
0x180005ed0  mov     ebx, eax
0x180005ed2  mov     rcx, rsi
0x180005ed5  mov     rax, [rsi]
0x180005ed8  mov     rax, [rax+10h]
0x180005edc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ee1  mov     rcx, qword ptr [rbp+pv]
0x180005ee5  mov     rax, [rcx]
0x180005ee8  mov     rax, [rax+10h]
0x180005eec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ef1  lea     rcx, [rbp+pvar]; pvar
0x180005ef5  call    cs:__imp_PropVariantClear
0x180005efb  mov     rax, [r14]
0x180005efe  mov     rcx, r14
0x180005f01  mov     rax, [rax+10h]
0x180005f05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f0a  mov     rcx, [rbp+var_40]
0x180005f0e  mov     rax, [rcx]
0x180005f11  mov     rax, [rax+10h]
0x180005f15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f1a  mov     rcx, [rbp+ppv]
0x180005f1e  mov     rax, [rcx]
0x180005f21  mov     rax, [rax+10h]
0x180005f25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f2a  mov     eax, ebx
0x180005f2c  mov     rcx, [rbp+var_10]
0x180005f30  xor     rcx, rsp; StackCookie
0x180005f33  call    __security_check_cookie
0x180005f38  add     rsp, 80h
0x180005f3f  pop     r15
0x180005f41  pop     r14
0x180005f43  pop     r12
0x180005f45  pop     rdi
0x180005f46  pop     rsi
0x180005f47  pop     rbx
0x180005f48  pop     rbp
0x180005f49  retn
0x180005f4a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005f51  mov     ecx, 40h ; '@'; unsigned __int64
0x180005f56  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180005f5b  test    rax, rax
0x180005f5e  jz      short loc_180005F78
0x180005f60  mov     rcx, rax; this
0x180005f63  call    ??0CDummyUnknown@@QEAA@XZ; CDummyUnknown::CDummyUnknown(void)
0x180005f68  mov     rdi, rax
0x180005f6b  test    rax, rax
0x180005f6e  jz      short loc_180005F78
0x180005f70  mov     r15, rax
0x180005f73  jmp     loc_180005E5E
0x180005f78  mov     ebx, 8007000Eh
0x180005f7d  jmp     loc_180005E9D
0x180005f82  mov     rax, [rcx]
0x180005f85  mov     rax, [rax+8]
0x180005f89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f8e  jmp     loc_180005CB4
0x180005f93  mov     ebx, 8007000Eh
0x180005f98  jmp     loc_180005F0A
```
