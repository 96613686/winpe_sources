# CheckScopeExcludedStoresandICSCleanup(ATL::CSimpleArray<CMapiStore *,ATL::CSimpleArrayEqualHelper<CMapiStore *>> &,ulong)

- ea: `0x18002d654`
- end: `0x18002d930`
- name: `?CheckScopeExcludedStoresandICSCleanup@@YAJAEAV?$CSimpleArray@PEAVCMapiStore@@V?$CSimpleArrayEqualHelper@PEAVCMapiStore@@@ATL@@@ATL@@K@Z`
- size: `732`
- prototype: `__int64 __fastcall(__int64, char)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002e1c8`
- `0x180035898`

## callees

- `0x18000ad14`
- `0x18000e6e0`
- `0x18000ebac`
- `0x180011884`
- `0x180013c20`
- `0x180017810`
- `0x180022a78`
- `0x180022b98`
- `0x1800256a0`
- `0x180025768`
- `0x18002beb0`
- `0x18002d654`
- `0x180031f3c`
- `0x180033a38`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002d6a8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002d6a8`

## pseudocode

```c
__int64 __fastcall CheckScopeExcludedStoresandICSCleanup(__int64 a1, char a2)
{
  HRESULT v4; // eax
  int DisplayName; // edi
  int v6; // r15d
  int v7; // r13d
  int v8; // r14d
  __int64 v9; // rsi
  wchar_t *v10; // rbx
  int v11; // edx
  BOOL v12; // eax
  LPVOID *ppv; // [rsp+20h] [rbp-108h]
  __int64 v15; // [rsp+30h] [rbp-F8h] BYREF
  __int64 v16; // [rsp+38h] [rbp-F0h] BYREF
  LPVOID v17; // [rsp+40h] [rbp-E8h] BYREF
  __int64 v18; // [rsp+48h] [rbp-E0h] BYREF
  __int128 v19; // [rsp+50h] [rbp-D8h] BYREF
  __int64 v20; // [rsp+60h] [rbp-C8h]
  __int128 v21; // [rsp+68h] [rbp-C0h]
  int v22; // [rsp+78h] [rbp-B0h]
  ATL::CAtlException *v23; // [rsp+80h] [rbp-A8h] BYREF
  _BYTE v24[152]; // [rsp+90h] [rbp-98h] BYREF
  void *retaddr; // [rsp+128h] [rbp+0h]
  unsigned int v27; // [rsp+140h] [rbp+18h] BYREF
  wchar_t *v28; // [rsp+148h] [rbp+20h] BYREF

  v17 = 0;
  v16 = 0;
  v15 = 0;
  v4 = CoCreateInstance(
         &GUID_7d096c5f_ac08_4f1f_beb7_5c22c517ce39,
         0,
         4u,
         &GUID_ab310581_ac80_11d1_8df3_00c04fb6ef69,
         &v17);
  try
  {
    DisplayName = v4;
    if ( v4 >= 0 )
    {
      DisplayName = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int64 *))(*(_QWORD *)v17 + 80LL))(
                      v17,
                      L"SystemIndex",
                      &v16);
      if ( DisplayName >= 0 )
        DisplayName = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v16 + 224LL))(v16, &v15);
      if ( DisplayName >= 0 )
      {
        v19 = 0;
        v20 = 0;
        v21 = 0;
        v22 = 10;
        v6 = 0;
        v7 = a2 & 4;
        v8 = v7;
        while ( DisplayName >= 0 )
        {
          v8 = v7;
          if ( v6 >= *(_DWORD *)(a1 + 8) )
            break;
          ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(&v28);
          v27 = 1;
          v9 = *(_QWORD *)ATL::CSimpleArray<CMapiStore *,ATL::CSimpleArrayEqualHelper<CMapiStore *>>::operator[](
                            a1,
                            (unsigned int)v6);
          DisplayName = CMapiStore::GetDisplayName(v9, &v28);
          if ( DisplayName < 0 )
          {
            v10 = v28;
          }
          else
          {
            CMapiUrl::CMapiUrl((CMapiUrl *)v24);
            v10 = v28;
            CMapiUrl::SetStore((CMapiUrl *)v24, v28);
            CMapiUrl::GetURL(v24, &v18);
            DisplayName = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v15 + 104LL))(
                            v15,
                            v18,
                            &v27);
            if ( DisplayName >= 0 )
            {
              if ( v27 || (a2 & 2) == 0 )
              {
                ++v6;
              }
              else if ( v6 >= 0 )
              {
                v11 = *(_DWORD *)(a1 + 8);
                if ( v6 < v11 )
                {
                  if ( v6 != v11 - 1 )
                    ATL::Checked::memmove_s(
                      (ATL::Checked *)(*(_QWORD *)a1 + 8LL * v6),
                      (void *)(8LL * (v11 - v6)),
                      *(_QWORD *)a1 + 8LL * v6 + 8,
                      (const void *)(8LL * (v11 - v6 - 1)),
                      (unsigned __int64)ppv);
                  --*(_DWORD *)(a1 + 8);
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
                  v9 = 0;
                }
              }
            }
            ATL::CStringData::Release((ATL::CStringData *)(v18 - 24));
            CMapiUrl::~CMapiUrl((CMapiUrl *)v24);
          }
          v12 = v9 && (!*(_QWORD *)(v9 + 48) || v27 && (*(_DWORD *)(v9 + 104) || *(_DWORD *)(v9 + 112)));
          v8 = a2 & 4;
          if ( (a2 & 4) != 0 )
          {
            if ( v12 )
              ATL::CAtlList<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::AddTail(
                &v19,
                *(_QWORD *)(v9 + 40));
          }
          ATL::CStringData::Release((ATL::CStringData *)(v10 - 12));
        }
        if ( v8 )
          CMapiSupport::ReconcileICSCacheInRegistry(&v19);
        ATL::CAtlList<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::RemoveAll(&v19);
      }
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v15);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v17);
  }
  catch ( ATL::CAtlException *v23 )
  {
    v27 = *(_DWORD *)v23;
    return v27;
  }
  catch ( ... )
  {
    indexer::result::details::result_from_caught_exception<0>(
      retaddr,
      113,
      "onecoreuap\\base\\appmodel\\search\\common\\mapilib\\include\\indexutil.h");
  }
  return (unsigned int)DisplayName;
}

```

## disassembly

```asm
0x18002d654  mov     [rsp+arg_8], edx
0x18002d658  push    rbx
0x18002d659  push    rsi
0x18002d65a  push    rdi
0x18002d65b  push    r12
0x18002d65d  push    r13
0x18002d65f  push    r14
0x18002d661  push    r15
0x18002d663  sub     rsp, 0F0h
0x18002d66a  mov     ebx, edx
0x18002d66c  mov     r12, rcx
0x18002d66f  mov     [rsp+128h+var_E8], 0
0x18002d678  mov     [rsp+128h+var_F0], 0
0x18002d681  mov     [rsp+128h+var_F8], 0
0x18002d68a  lea     rax, [rsp+128h+var_E8]
0x18002d68f  mov     [rsp+128h+ppv], rax; unsigned __int64
0x18002d694  lea     r9, _GUID_ab310581_ac80_11d1_8df3_00c04fb6ef69; riid
0x18002d69b  xor     edx, edx; pUnkOuter
0x18002d69d  lea     r8d, [rdx+4]; dwClsContext
0x18002d6a1  lea     rcx, _GUID_7d096c5f_ac08_4f1f_beb7_5c22c517ce39; rclsid
0x18002d6a8  call    cs:__imp_CoCreateInstance
0x18002d6ae  mov     edi, eax
0x18002d6b0  test    eax, eax
0x18002d6b2  js      loc_18002D8EF
0x18002d6b8  mov     rcx, [rsp+128h+var_E8]
0x18002d6bd  mov     rax, [rcx]
0x18002d6c0  lea     r8, [rsp+128h+var_F0]
0x18002d6c5  lea     rdx, aSystemindex; "SystemIndex"
0x18002d6cc  mov     rax, [rax+50h]
0x18002d6d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d6d5  mov     edi, eax
0x18002d6d7  test    eax, eax
0x18002d6d9  js      short loc_18002D6F6
0x18002d6db  mov     rcx, [rsp+128h+var_F0]
0x18002d6e0  mov     rax, [rcx]
0x18002d6e3  lea     rdx, [rsp+128h+var_F8]
0x18002d6e8  mov     rax, [rax+0E0h]
0x18002d6ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d6f4  mov     edi, eax
0x18002d6f6  test    edi, edi
0x18002d6f8  js      loc_18002D8EF
0x18002d6fe  xorps   xmm0, xmm0
0x18002d701  movdqu  [rsp+128h+var_D8], xmm0
0x18002d707  mov     [rsp+128h+var_C8], 0
0x18002d710  xorps   xmm1, xmm1
0x18002d713  movdqu  [rsp+128h+var_C0], xmm1
0x18002d719  mov     [rsp+128h+var_B0], 0Ah
0x18002d721  xor     r15d, r15d
0x18002d724  mov     r13d, ebx
0x18002d727  and     r13d, 4
0x18002d72b  mov     r14d, r13d
0x18002d72e  test    edi, edi
0x18002d730  js      loc_18002D8D4
0x18002d736  mov     r14d, r13d
0x18002d739  cmp     r15d, [r12+8]
0x18002d73e  jge     loc_18002D8D4
0x18002d744  lea     rcx, [rsp+128h+arg_18]
0x18002d74c  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x18002d751  nop
0x18002d752  mov     [rsp+128h+arg_10], 1
0x18002d75d  mov     edx, r15d
0x18002d760  mov     rcx, r12
0x18002d763  call    ??A?$CSimpleArray@PEAVCMapiStore@@V?$CSimpleArrayEqualHelper@PEAVCMapiStore@@@ATL@@@ATL@@QEAAAEAPEAVCMapiStore@@H@Z; ATL::CSimpleArray<CMapiStore *,ATL::CSimpleArrayEqualHelper<CMapiStore *>>::operator[](int)
0x18002d768  mov     rsi, [rax]
0x18002d76b  lea     rdx, [rsp+128h+arg_18]
0x18002d773  mov     rcx, rsi
0x18002d776  call    ?GetDisplayName@CMapiStore@@QEAAJAEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z; CMapiStore::GetDisplayName(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)
0x18002d77b  mov     edi, eax
0x18002d77d  xor     r14d, r14d
0x18002d780  test    eax, eax
0x18002d782  js      loc_18002D872
0x18002d788  lea     rcx, [rsp+128h+var_98]; this
0x18002d790  call    ??0CMapiUrl@@QEAA@XZ; CMapiUrl::CMapiUrl(void)
0x18002d795  nop
0x18002d796  mov     rbx, [rsp+128h+arg_18]
0x18002d79e  mov     rdx, rbx; wchar_t *
0x18002d7a1  lea     rcx, [rsp+128h+var_98]; this
0x18002d7a9  call    ?SetStore@CMapiUrl@@QEAAXPEB_W@Z; CMapiUrl::SetStore(wchar_t const *)
0x18002d7ae  lea     rdx, [rsp+128h+var_E0]
0x18002d7b3  lea     rcx, [rsp+128h+var_98]
0x18002d7bb  call    ?GetURL@CMapiUrl@@QEAA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@XZ; CMapiUrl::GetURL(void)
0x18002d7c0  nop
0x18002d7c1  mov     rcx, [rsp+128h+var_F8]
0x18002d7c6  mov     rax, [rcx]
0x18002d7c9  lea     r8, [rsp+128h+arg_10]
0x18002d7d1  mov     rdx, [rsp+128h+var_E0]
0x18002d7d6  mov     rax, [rax+68h]
0x18002d7da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d7df  mov     edi, eax
0x18002d7e1  test    eax, eax
0x18002d7e3  js      short loc_18002D854
0x18002d7e5  cmp     [rsp+128h+arg_10], r14d
0x18002d7ed  jnz     short loc_18002D851
0x18002d7ef  test    byte ptr [rsp+128h+arg_8], 2
0x18002d7f7  jz      short loc_18002D851
0x18002d7f9  test    r15d, r15d
0x18002d7fc  js      short loc_18002D854
0x18002d7fe  mov     edx, [r12+8]
0x18002d803  cmp     r15d, edx
0x18002d806  jge     short loc_18002D854
0x18002d808  lea     eax, [rdx-1]
0x18002d80b  cmp     r15d, eax
0x18002d80e  jz      short loc_18002D838
0x18002d810  movsxd  rcx, r15d
0x18002d813  mov     rax, [r12]
0x18002d817  lea     rcx, [rax+rcx*8]; this
0x18002d81b  sub     edx, r15d
0x18002d81e  lea     eax, [rdx-1]
0x18002d821  movsxd  r9, eax
0x18002d824  shl     r9, 3; void *
0x18002d828  lea     r8, [rcx+8]; unsigned __int64
0x18002d82c  movsxd  rdx, edx
0x18002d82f  shl     rdx, 3; void *
0x18002d833  call    ?memmove_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memmove_s(void *,unsigned __int64,void const *,unsigned __int64)
0x18002d838  dec     dword ptr [r12+8]
0x18002d83d  mov     rax, [rsi]
0x18002d840  mov     rcx, rsi
0x18002d843  mov     rax, [rax+10h]
0x18002d847  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d84c  mov     rsi, r14
0x18002d84f  jmp     short loc_18002D854
0x18002d851  inc     r15d
0x18002d854  mov     rcx, [rsp+128h+var_E0]
0x18002d859  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002d85d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002d862  nop
0x18002d863  lea     rcx, [rsp+128h+var_98]; this
0x18002d86b  call    ??1CMapiUrl@@QEAA@XZ; CMapiUrl::~CMapiUrl(void)
0x18002d870  jmp     short loc_18002D87A
0x18002d872  mov     rbx, [rsp+128h+arg_18]
0x18002d87a  test    rsi, rsi
0x18002d87d  jz      short loc_18002D8A2
0x18002d87f  cmp     [rsi+30h], r14
0x18002d883  jz      short loc_18002D89B
0x18002d885  cmp     [rsp+128h+arg_10], r14d
0x18002d88d  jz      short loc_18002D8A2
0x18002d88f  cmp     [rsi+68h], r14d
0x18002d893  jnz     short loc_18002D89B
0x18002d895  cmp     [rsi+70h], r14d
0x18002d899  jz      short loc_18002D8A2
0x18002d89b  mov     eax, 1
0x18002d8a0  jmp     short loc_18002D8A5
0x18002d8a2  mov     eax, r14d
0x18002d8a5  mov     r14d, [rsp+128h+arg_8]
0x18002d8ad  and     r14d, 4
0x18002d8b1  jz      short loc_18002D8C6
0x18002d8b3  test    eax, eax
0x18002d8b5  jz      short loc_18002D8C6
0x18002d8b7  mov     rdx, [rsi+28h]
0x18002d8bb  lea     rcx, [rsp+128h+var_D8]
0x18002d8c0  call    ?AddTail@?$CAtlList@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@PEB_W@Z; ATL::CAtlList<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::AddTail(wchar_t const *)
0x18002d8c5  nop
0x18002d8c6  lea     rcx, [rbx-18h]; this
0x18002d8ca  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002d8cf  jmp     loc_18002D72E
0x18002d8d4  test    r14d, r14d
0x18002d8d7  jz      short loc_18002D8E4
0x18002d8d9  lea     rcx, [rsp+128h+var_D8]
0x18002d8de  call    ?ReconcileICSCacheInRegistry@CMapiSupport@@SAJPEAV?$CAtlList@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@@ATL@@@Z; CMapiSupport::ReconcileICSCacheInRegistry(ATL::CAtlList<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>> *)
0x18002d8e3  nop
0x18002d8e4  lea     rcx, [rsp+128h+var_D8]
0x18002d8e9  call    ?RemoveAll@?$CAtlList@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::RemoveAll(void)
0x18002d8ee  nop
0x18002d8ef  lea     rcx, [rsp+128h+var_F8]
0x18002d8f4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002d8f9  nop
0x18002d8fa  lea     rcx, [rsp+128h+var_F0]
0x18002d8ff  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002d904  nop
0x18002d905  lea     rcx, [rsp+128h+var_E8]
0x18002d90a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002d90f  nop
0x18002d910  jmp     short loc_18002D91B
0x18002d912  jmp     short $+2
0x18002d914  mov     edi, [rsp+128h+arg_10]
0x18002d91b  mov     eax, edi
0x18002d91d  add     rsp, 0F0h
0x18002d924  pop     r15
0x18002d926  pop     r14
0x18002d928  pop     r13
0x18002d92a  pop     r12
0x18002d92c  pop     rdi
0x18002d92d  pop     rsi
0x18002d92e  pop     rbx
0x18002d92f  retn
```
