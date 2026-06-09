# CQueryResultSet::_BindToResult(unsigned __int64,IServiceProvider *,_GUID const &,void * *)

- ea: `0x18001d280`
- end: `0x18001d7f2`
- name: `?_BindToResult@CQueryResultSet@@AEAAJ_KPEAUIServiceProvider@@AEBU_GUID@@PEAPEAX@Z`
- size: `1394`
- prototype: `int(CQueryResultSet *__hidden this, unsigned __int64, struct IServiceProvider *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001def0`

## callees

- `0x180014498`
- `0x18001c700`
- `0x18001ca40`
- `0x18001d280`
- `0x18001e4c4`
- `0x1800581bc`
- `0x180063a68`
- `0x180071dc0`
- `0x180071df0`
- `0x1800b07a8`
- `0x1800b4054`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x18001d30f`
- `SHCORE!IUnknown_QueryService` at `0x18001d30f`
- `SHCORE!IStream_Reset` at `0x18001d54b`
- `SHCORE!IStream_Reset` at `0x18001d54b`
- `SHCORE!SHCreateMemStream` at `0x18001d463`
- `SHCORE!SHCreateMemStream` at `0x18001d463`
- `SHCORE!IStream_Write` at `0x18001d508`
- `SHCORE!IStream_Write` at `0x18001d508`
- `SHCORE!IUnknown_SetSite` at `0x18001d367`
- `SHCORE!IUnknown_SetSite` at `0x18001d39a`
- `SHCORE!IUnknown_SetSite` at `0x18001d367`
- `SHCORE!IUnknown_SetSite` at `0x18001d39a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d35a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d35a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d3a7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d3a7`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x18001d7e5`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x18001d7e5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CQueryResultSet::_BindToResult(
        CQueryResultSet *this,
        __int64 a2,
        IUnknown *a3,
        struct _GUID *a4,
        void **ppv)
{
  __int64 (__fastcall ***v8)(_QWORD, GUID *, IUnknown **); // rcx
  HRESULT v9; // ebx
  int v10; // ecx
  int v11; // r8d
  void *v12; // rcx
  int v13; // eax
  int v14; // ecx
  int v15; // r8d
  __int64 v16; // rdx
  int v17; // edi
  IStream *v18; // r14
  __int64 (__fastcall ***v19)(_QWORD, GUID *, void **); // rcx
  _QWORD *v20; // rdx
  unsigned int i; // ecx
  __int64 v22; // rax
  IStream *v23; // rcx
  IStream *v24; // rax
  CQueryResultSet *v26; // rcx
  struct IServiceProvider *v27; // r9
  CQueryResult *v28; // rdi
  struct IPropertyStoreCache **v29; // [rsp+20h] [rbp-91h]
  void *ppvOut; // [rsp+50h] [rbp-61h] BYREF
  unsigned int v31; // [rsp+58h] [rbp-59h]
  IUnknown *punk; // [rsp+60h] [rbp-51h] BYREF
  struct IPropertyStoreCache *v33; // [rsp+68h] [rbp-49h] BYREF
  IStream *pstm; // [rsp+70h] [rbp-41h] BYREF
  __int64 v35; // [rsp+78h] [rbp-39h] BYREF
  IID *riid; // [rsp+80h] [rbp-31h]
  struct _tagpropertykey v37; // [rsp+88h] [rbp-29h] BYREF
  __int128 pv; // [rsp+A0h] [rbp-11h] BYREF
  __int64 v39; // [rsp+B0h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+57h]

  riid = a4;
  *ppv = 0;
  v33 = 0;
  v8 = (__int64 (__fastcall ***)(_QWORD, GUID *, IUnknown **))*((_QWORD *)this + 28);
  if ( !v8 )
  {
    v9 = -2147467259;
    goto LABEL_40;
  }
  punk = 0;
  v9 = (**v8)(v8, &GUID_0c733aaf_2a1c_11ce_ade5_00aa0044773d, &punk);
  if ( v9 < 0 )
  {
LABEL_39:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x135F,
      (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
      (const char *)(unsigned int)v9,
      (int)v29);
    goto LABEL_40;
  }
  ppvOut = 0;
  if ( IUnknown_QueryService(a3, &IID_IQueryContinue, &GUID_7307055c_b24a_486b_9f25_163e597a28a9, &ppvOut) < 0 )
    goto LABEL_7;
  v12 = ppvOut;
  if ( ppvOut )
  {
    v13 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvOut + 24LL))(ppvOut);
    v12 = ppvOut;
    if ( v13 )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
      v9 = -2147023673;
      ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
      goto LABEL_39;
    }
  }
  (*(void (__fastcall **)(void *))(*(_QWORD *)v12 + 16LL))(v12);
LABEL_7:
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 0x20) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(v10, (unsigned int)DataLayer_GetRowFromHROW_Start, v11, 1, (__int64)&pv);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 13);
  IUnknown_SetSite(punk, a3);
  v29 = &v33;
  v9 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, __int64, GUID *))punk->lpVtbl[1].QueryInterface)(
         punk,
         0,
         a2,
         &GUID_3017056d_9a91_4e90_937d_746c72abbf4f);
  IUnknown_SetSite(punk, 0);
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 13);
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 0x20) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(v14, (unsigned int)DataLayer_GetRowFromHROW_Stop, v15, 1, (__int64)&pv);
  ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
  if ( v9 < 0 )
    goto LABEL_39;
  memset(&v37, 0, sizeof(v37));
  v35 = 0;
  if ( (*(int (__fastcall **)(_QWORD, struct _tagpropertykey *, GUID *, __int64 *))(**((_QWORD **)this + 46) + 56LL))(
         *((_QWORD *)this + 46),
         &v37,
         &GUID_6bc63938_8254_4965_9680_565933185060,
         &v35) >= 0 )
  {
    v17 = *((_DWORD *)this + 66);
    v31 = v17;
    v9 = IPropertyStore_SetPropertyKey(v33, v16, &v37);
    if ( v9 >= 0 && (*((_BYTE *)this + 268) & 1) != 0 )
      v9 = CQueryResultSet::_ComputeStackHashFromRows(v26, &v37, v33, v27);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    if ( v9 < 0 )
      goto LABEL_36;
  }
  else
  {
    v17 = 1;
    v31 = 1;
  }
  if ( !*((_QWORD *)this + 39) )
    goto LABEL_33;
  LODWORD(punk) = 0;
  if ( ((int (__fastcall *)(struct IPropertyStoreCache *, const PROPERTYKEY *, IUnknown **))v33->lpVtbl->GetState)(
         v33,
         &PKEY_Search_AutoSummary,
         &punk) < 0
    || (_DWORD)punk )
  {
    goto LABEL_33;
  }
  pstm = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pstm);
  v18 = SHCreateMemStream(0, 0);
  pstm = v18;
  if ( v18 )
  {
    v19 = (__int64 (__fastcall ***)(_QWORD, GUID *, void **))*((_QWORD *)this + 39);
    ppvOut = 0;
    v9 = (**v19)(v19, &GUID_00000109_0000_0000_c000_000000000046, &ppvOut);
    if ( v9 >= 0 )
    {
      pv = 0;
      v9 = (*(__int64 (__fastcall **)(void *, __int128 *))(*(_QWORD *)ppvOut + 24LL))(ppvOut, &pv);
      if ( v9 >= 0 )
      {
        for ( i = 0; ; ++i )
        {
          if ( i >= 3 )
          {
            v9 = -2147024809;
            (*(void (__fastcall **)(void *, _QWORD *, struct _GUID *const *))(*(_QWORD *)ppvOut + 16LL))(
              ppvOut,
              v20,
              &off_1800EB310);
            v31 = v17;
            goto LABEL_30;
          }
          v20 = (_QWORD *)*((_QWORD *)&off_1800EB310 + i);
          v22 = *v20 - pv;
          if ( *v20 == (_QWORD)pv )
            v22 = v20[1] - *((_QWORD *)&pv + 1);
          if ( !v22 )
            break;
        }
        v31 = v17;
        v9 = IStream_Write(v18, &pv, 0x10u);
        if ( v9 < 0 )
          v31 = v17;
        else
          v9 = (*(__int64 (__fastcall **)(void *, IStream *, __int64))(*(_QWORD *)ppvOut + 48LL))(ppvOut, v18, 1);
      }
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
      if ( v9 >= 0 )
      {
        IStream_Reset(pstm);
        *(_QWORD *)&pv = 13;
        v39 = 0;
        *((_QWORD *)&pv + 1) = pstm;
        v9 = ((__int64 (__fastcall *)(struct IPropertyStoreCache *, __int64 *, __int128 *))v33->lpVtbl->SetValue)(
               v33,
               PKEY_ItemQueryCondition,
               &pv);
      }
    }
  }
  else
  {
    v9 = -2147024882;
  }
LABEL_30:
  v23 = pstm;
  if ( pstm )
  {
    pstm = 0;
    (*(void (__fastcall **)(IStream *))(*(_QWORD *)v23 + 16LL))(v23);
  }
  if ( v9 >= 0 )
  {
LABEL_33:
    ppvOut = (void *)*((_QWORD *)this + 31);
    *ppv = 0;
    v9 = -2147024882;
    v24 = (IStream *)operator new(0xD8u, (const struct std::nothrow_t *)&std::nothrow);
    pstm = v24;
    if ( !v24 )
      goto LABEL_34;
    v28 = CQueryResult::CQueryResult(v24);
    if ( !v28 )
      goto LABEL_34;
    LODWORD(v29) = (_DWORD)ppvOut;
    v9 = CQueryResult::_InitializeResultWithStore(v28, v31, (char *)this + 560, (char *)this + 232);
    if ( v9 >= 0 )
      v9 = QISearch(v28, &`CQueryResult::QueryInterface'::`2'::qit, riid, ppv);
    CQueryResult::Release(v28);
    if ( v9 < 0 )
LABEL_34:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x460,
        (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
        (const char *)(unsigned int)v9,
        (int)v29);
  }
LABEL_36:
  ((void (__fastcall *)(struct IPropertyStoreCache *))v33->lpVtbl->Release)(v33);
  if ( v9 < 0 )
LABEL_40:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13EF,
      (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
      (const char *)(unsigned int)v9,
      (int)v29);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001d280  push    rbp
0x18001d282  push    rbx
0x18001d283  push    rsi
0x18001d284  push    rdi
0x18001d285  push    r12
0x18001d287  push    r13
0x18001d289  push    r14
0x18001d28b  push    r15
0x18001d28d  lea     rbp, [rsp-17h]
0x18001d292  sub     rsp, 0C8h
0x18001d299  mov     rax, cs:__security_cookie
0x18001d2a0  xor     rax, rsp
0x18001d2a3  mov     [rbp+4Fh+var_48], rax
0x18001d2a7  mov     [rbp+4Fh+riid], r9
0x18001d2ab  mov     r14, r8
0x18001d2ae  mov     r12, rdx
0x18001d2b1  mov     rsi, rcx
0x18001d2b4  mov     r15, [rbp+4Fh+ppv]
0x18001d2b8  xor     r13d, r13d
0x18001d2bb  mov     [r15], r13
0x18001d2be  mov     [rbp+4Fh+var_98], r13
0x18001d2c2  mov     rcx, [rcx+0E0h]
0x18001d2c9  test    rcx, rcx
0x18001d2cc  jz      loc_18001D64D
0x18001d2d2  mov     [rbp+4Fh+punk], r13
0x18001d2d6  mov     rax, [rcx]
0x18001d2d9  lea     r8, [rbp+4Fh+punk]
0x18001d2dd  lea     rdx, _GUID_0c733aaf_2a1c_11ce_ade5_00aa0044773d
0x18001d2e4  mov     rax, [rax]
0x18001d2e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2ec  mov     ebx, eax
0x18001d2ee  test    eax, eax
0x18001d2f0  js      loc_18001D654
0x18001d2f6  mov     [rbp+4Fh+ppvOut], r13
0x18001d2fa  lea     r9, [rbp+4Fh+ppvOut]; ppvOut
0x18001d2fe  lea     r8, _GUID_7307055c_b24a_486b_9f25_163e597a28a9; riid
0x18001d305  lea     rdx, IID_IQueryContinue; guidService
0x18001d30c  mov     rcx, r14; punk
0x18001d30f  call    cs:__imp_IUnknown_QueryService
0x18001d315  test    eax, eax
0x18001d317  js      short loc_18001D346
0x18001d319  mov     rcx, [rbp+4Fh+ppvOut]
0x18001d31d  test    rcx, rcx
0x18001d320  jz      short loc_18001D33A
0x18001d322  mov     rax, [rcx]
0x18001d325  mov     rax, [rax+18h]
0x18001d329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d32e  mov     rcx, [rbp+4Fh+ppvOut]
0x18001d332  test    eax, eax
0x18001d334  jnz     loc_18001D6F2
0x18001d33a  mov     rax, [rcx]
0x18001d33d  mov     rax, [rax+10h]
0x18001d341  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d346  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, 20h
0x18001d34d  jnz     loc_18001D6B5
0x18001d353  lea     rcx, [rsi+208h]; lpCriticalSection
0x18001d35a  call    cs:__imp_EnterCriticalSection
0x18001d360  mov     rdx, r14; punkSite
0x18001d363  mov     rcx, [rbp+4Fh+punk]; punk
0x18001d367  call    cs:__imp_IUnknown_SetSite
0x18001d36d  mov     rcx, [rbp+4Fh+punk]
0x18001d371  mov     rax, [rcx]
0x18001d374  lea     rdx, [rbp+4Fh+var_98]
0x18001d378  mov     qword ptr [rsp+100h+var_E0], rdx; int
0x18001d37d  lea     r9, _GUID_3017056d_9a91_4e90_937d_746c72abbf4f
0x18001d384  mov     r8, r12
0x18001d387  xor     edx, edx
0x18001d389  mov     rax, [rax+18h]
0x18001d38d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d392  mov     ebx, eax
0x18001d394  xor     edx, edx; punkSite
0x18001d396  mov     rcx, [rbp+4Fh+punk]; punk
0x18001d39a  call    cs:__imp_IUnknown_SetSite
0x18001d3a0  lea     rcx, [rsi+208h]; lpCriticalSection
0x18001d3a7  call    cs:__imp_LeaveCriticalSection
0x18001d3ad  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, 20h
0x18001d3b4  jnz     loc_18001D718
0x18001d3ba  mov     rcx, [rbp+4Fh+punk]
0x18001d3be  mov     rax, [rcx]
0x18001d3c1  mov     rax, [rax+10h]
0x18001d3c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d3ca  test    ebx, ebx
0x18001d3cc  js      loc_18001D654
0x18001d3d2  xorps   xmm0, xmm0
0x18001d3d5  xor     eax, eax
0x18001d3d7  movups  xmmword ptr [rbp+4Fh+var_78.fmtid.Data1], xmm0
0x18001d3db  mov     [rbp+4Fh+var_78.pid], eax
0x18001d3de  mov     [rbp+4Fh+var_88], r13
0x18001d3e2  mov     rcx, [rsi+170h]
0x18001d3e9  mov     rax, [rcx]
0x18001d3ec  lea     r9, [rbp+4Fh+var_88]
0x18001d3f0  lea     r8, _GUID_6bc63938_8254_4965_9680_565933185060
0x18001d3f7  lea     rdx, [rbp+4Fh+var_78]
0x18001d3fb  mov     rax, [rax+38h]
0x18001d3ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d404  test    eax, eax
0x18001d406  jns     loc_18001D738
0x18001d40c  mov     edi, 1
0x18001d411  mov     [rbp+4Fh+var_A8], edi
0x18001d414  cmp     [rsi+138h], r13
0x18001d41b  jz      loc_18001D5AA
0x18001d421  mov     dword ptr [rbp+4Fh+punk], r13d
0x18001d425  mov     rcx, [rbp+4Fh+var_98]
0x18001d429  mov     rax, [rcx]
0x18001d42c  lea     r8, [rbp+4Fh+punk]
0x18001d430  lea     rdx, PKEY_Search_AutoSummary
0x18001d437  mov     rax, [rax+40h]
0x18001d43b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d440  test    eax, eax
0x18001d442  js      loc_18001D5AA
0x18001d448  cmp     dword ptr [rbp+4Fh+punk], r13d
0x18001d44c  jnz     loc_18001D5AA
0x18001d452  mov     [rbp+4Fh+pstm], r13
0x18001d456  lea     rcx, [rbp+4Fh+pstm]
0x18001d45a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d45f  xor     edx, edx; cbInit
0x18001d461  xor     ecx, ecx; pInit
0x18001d463  call    cs:__imp_SHCreateMemStream
0x18001d469  mov     r14, rax
0x18001d46c  mov     [rbp+4Fh+pstm], rax
0x18001d470  test    rax, rax
0x18001d473  jz      loc_18001D68E
0x18001d479  mov     rcx, [rsi+138h]
0x18001d480  mov     [rbp+4Fh+ppvOut], r13
0x18001d484  mov     rdx, [rcx]
0x18001d487  mov     rax, [rdx]
0x18001d48a  lea     r8, [rbp+4Fh+ppvOut]
0x18001d48e  lea     rdx, _GUID_00000109_0000_0000_c000_000000000046
0x18001d495  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d49a  mov     ebx, eax
0x18001d49c  test    eax, eax
0x18001d49e  js      loc_18001D58C
0x18001d4a4  xorps   xmm0, xmm0
0x18001d4a7  movups  [rbp+4Fh+pv], xmm0
0x18001d4ab  mov     rcx, [rbp+4Fh+ppvOut]
0x18001d4af  mov     rax, [rcx]
0x18001d4b2  lea     rdx, [rbp+4Fh+pv]
0x18001d4b6  mov     rax, [rax+18h]
0x18001d4ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4bf  mov     ebx, eax
0x18001d4c1  test    eax, eax
0x18001d4c3  js      short loc_18001D533
0x18001d4c5  mov     ecx, r13d
0x18001d4c8  lea     r8, off_1800EB310
0x18001d4cf  cmp     ecx, 3
0x18001d4d2  jnb     loc_18001D698
0x18001d4d8  mov     eax, ecx
0x18001d4da  mov     rdx, [r8+rax*8]
0x18001d4de  mov     rax, [rdx]
0x18001d4e1  sub     rax, qword ptr [rbp+4Fh+pv]
0x18001d4e5  jnz     short loc_18001D4EF
0x18001d4e7  mov     rax, [rdx+8]
0x18001d4eb  sub     rax, qword ptr [rbp+4Fh+pv+8]
0x18001d4ef  test    rax, rax
0x18001d4f2  jz      short loc_18001D4F8
0x18001d4f4  inc     ecx
0x18001d4f6  jmp     short loc_18001D4CF
0x18001d4f8  mov     [rbp+4Fh+var_A8], edi
0x18001d4fb  mov     r8d, 10h; cb
0x18001d501  lea     rdx, [rbp+4Fh+pv]; pv
0x18001d505  mov     rcx, r14; pstm
0x18001d508  call    cs:__imp_IStream_Write
0x18001d50e  mov     ebx, eax
0x18001d510  test    eax, eax
0x18001d512  js      loc_18001D775
0x18001d518  mov     rcx, [rbp+4Fh+ppvOut]
0x18001d51c  mov     rax, [rcx]
0x18001d51f  mov     r8d, 1
0x18001d525  mov     rdx, r14
0x18001d528  mov     rax, [rax+30h]
0x18001d52c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d531  mov     ebx, eax
0x18001d533  mov     rcx, [rbp+4Fh+ppvOut]
0x18001d537  mov     rax, [rcx]
0x18001d53a  mov     rax, [rax+10h]
0x18001d53e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d543  test    ebx, ebx
0x18001d545  js      short loc_18001D58C
0x18001d547  mov     rcx, [rbp+4Fh+pstm]; pstm
0x18001d54b  call    cs:__imp_IStream_Reset
0x18001d551  mov     rcx, [rbp+4Fh+var_98]
0x18001d555  xorps   xmm0, xmm0
0x18001d558  xor     eax, eax
0x18001d55a  movups  [rbp+4Fh+pv], xmm0
0x18001d55e  mov     [rbp+4Fh+var_50], rax
0x18001d562  mov     eax, 0Dh
0x18001d567  mov     word ptr [rbp+4Fh+pv], ax
0x18001d56b  mov     rax, [rbp+4Fh+pstm]
0x18001d56f  mov     qword ptr [rbp+4Fh+pv+8], rax
0x18001d573  mov     rax, [rcx]
0x18001d576  lea     r8, [rbp+4Fh+pv]
0x18001d57a  lea     rdx, PKEY_ItemQueryCondition
0x18001d581  mov     rax, [rax+30h]
0x18001d585  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d58a  mov     ebx, eax
0x18001d58c  mov     rcx, [rbp+4Fh+pstm]
0x18001d590  test    rcx, rcx
0x18001d593  jz      short loc_18001D5A6
0x18001d595  mov     [rbp+4Fh+pstm], r13
0x18001d599  mov     rax, [rcx]
0x18001d59c  mov     rax, [rax+10h]
0x18001d5a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5a5  nop
0x18001d5a6  test    ebx, ebx
0x18001d5a8  js      short loc_18001D617
0x18001d5aa  mov     r14d, [rsi+110h]
0x18001d5b1  mov     r12d, [rsi+130h]
0x18001d5b8  mov     r13, [rbp+4Fh+var_98]
0x18001d5bc  mov     rax, [rsi+0F8h]
0x18001d5c3  mov     [rbp+4Fh+ppvOut], rax
0x18001d5c7  mov     qword ptr [r15], 0
0x18001d5ce  mov     ebx, 8007000Eh
0x18001d5d3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001d5da  mov     ecx, 0D8h; unsigned __int64
0x18001d5df  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001d5e4  mov     [rbp+4Fh+pstm], rax
0x18001d5e8  test    rax, rax
0x18001d5eb  jnz     loc_18001D77D
0x18001d5f1  mov     rcx, [rbp+57h]; this
0x18001d5f5  mov     r9d, ebx; char *
0x18001d5f8  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.storage.sear"...
0x18001d5ff  mov     edx, 460h; void *
0x18001d604  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d609  jmp     short loc_18001D617
0x18001d60b  mov     rcx, rdi; this
0x18001d60e  call    ?Release@CQueryResult@@UEAAKXZ; CQueryResult::Release(void)
0x18001d613  test    ebx, ebx
0x18001d615  js      short loc_18001D5F1
0x18001d617  mov     rcx, [rbp+4Fh+var_98]
0x18001d61b  mov     rax, [rcx]
0x18001d61e  mov     rax, [rax+10h]
0x18001d622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d627  test    ebx, ebx
0x18001d629  js      short loc_18001D674
0x18001d62b  mov     eax, ebx
0x18001d62d  mov     rcx, [rbp+4Fh+var_48]
0x18001d631  xor     rcx, rsp; StackCookie
0x18001d634  call    __security_check_cookie
0x18001d639  add     rsp, 0C8h
0x18001d640  pop     r15
0x18001d642  pop     r14
0x18001d644  pop     r13
0x18001d646  pop     r12
0x18001d648  pop     rdi
0x18001d649  pop     rsi
0x18001d64a  pop     rbx
0x18001d64b  pop     rbp
0x18001d64c  retn
0x18001d64d  mov     ebx, 80004005h
0x18001d652  jmp     short loc_18001D674
0x18001d654  mov     rcx, [rbp+57h]; this
0x18001d658  mov     r9d, ebx; char *
0x18001d65b  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.storage.sear"...
0x18001d662  mov     edx, 135Fh; void *
0x18001d667  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d66c  test    ebx, ebx
0x18001d66e  jns     loc_18001D3D2
0x18001d674  mov     rcx, [rbp+57h]; this
0x18001d678  mov     r9d, ebx; char *
0x18001d67b  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.storage.sear"...
0x18001d682  mov     edx, 13EFh; void *
0x18001d687  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d68c  jmp     short loc_18001D62B
0x18001d68e  mov     ebx, 8007000Eh
0x18001d693  jmp     loc_18001D58C
0x18001d698  mov     ebx, 80070057h
0x18001d69d  mov     rcx, [rbp+4Fh+ppvOut]
0x18001d6a1  mov     rax, [rcx]
0x18001d6a4  mov     rax, [rax+10h]
0x18001d6a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6ad  mov     [rbp+4Fh+var_A8], edi
0x18001d6b0  jmp     loc_18001D58C
0x18001d6b5  lea     rax, [rbp+4Fh+pv]
0x18001d6b9  mov     qword ptr [rsp+100h+var_E0], rax
0x18001d6be  mov     r9d, 1
0x18001d6c4  lea     rdx, DataLayer_GetRowFromHROW_Start
0x18001d6cb  call    McGenEventWrite_EtwEventWriteTransfer
0x18001d6d0  jmp     loc_18001D353
0x18001d6d5  mov     rcx, [rbp+4Fh+var_88]
0x18001d6d9  mov     rax, [rcx]
0x18001d6dc  mov     rax, [rax+10h]
0x18001d6e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6e5  test    ebx, ebx
0x18001d6e7  jns     loc_18001D414
0x18001d6ed  jmp     loc_18001D617
0x18001d6f2  mov     rax, [rcx]
0x18001d6f5  mov     rax, [rax+10h]
0x18001d6f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6fe  mov     ebx, 800704C7h
0x18001d703  mov     rcx, [rbp+4Fh+punk]
0x18001d707  mov     rax, [rcx]
0x18001d70a  mov     rax, [rax+10h]
0x18001d70e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d713  jmp     loc_18001D654
0x18001d718  lea     rax, [rbp+4Fh+pv]
0x18001d71c  mov     qword ptr [rsp+100h+var_E0], rax
0x18001d721  mov     r9d, 1
0x18001d727  lea     rdx, DataLayer_GetRowFromHROW_Stop
0x18001d72e  call    McGenEventWrite_EtwEventWriteTransfer
0x18001d733  jmp     loc_18001D3BA
  ... truncated ...
```
