# CQueryResultSet::FetchResultAt(uint,IServiceProvider *,_GUID const &,void * *)

- ea: `0x18001cb30`
- end: `0x18001d277`
- name: `?FetchResultAt@CQueryResultSet@@UEAAJIPEAUIServiceProvider@@AEBU_GUID@@PEAPEAX@Z`
- size: `1863`
- prototype: `int(CQueryResultSet *__hidden this, unsigned int, struct IServiceProvider *, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001ec80`
- `0x18001f67c`

## callees

- `0x180014498`
- `0x18001c700`
- `0x18001ca40`
- `0x18001cb30`
- `0x18001db40`
- `0x18001e4c4`
- `0x18004e270`
- `0x1800581bc`
- `0x180063a68`
- `0x180071dc0`
- `0x180071df0`
- `0x1800b07a8`
- `0x1800b4054`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IStream_Reset` at `0x18001ce23`
- `SHCORE!IStream_Reset` at `0x18001ce23`
- `SHCORE!SHCreateMemStream` at `0x18001cde8`
- `SHCORE!SHCreateMemStream` at `0x18001cde8`
- `SHCORE!IUnknown_SetSite` at `0x18001cbdd`
- `SHCORE!IUnknown_SetSite` at `0x18001cc31`
- `SHCORE!IUnknown_SetSite` at `0x18001ccd5`
- `SHCORE!IUnknown_SetSite` at `0x18001cd0b`
- `SHCORE!IUnknown_SetSite` at `0x18001cbdd`
- `SHCORE!IUnknown_SetSite` at `0x18001cc31`
- `SHCORE!IUnknown_SetSite` at `0x18001ccd5`
- `SHCORE!IUnknown_SetSite` at `0x18001cd0b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001cbcc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ccc7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001cbcc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ccc7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001cc3a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001cd14`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001cc3a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001cd14`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x18001d249`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x18001d249`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CQueryResultSet::FetchResultAt(
        CQueryResultSet *this,
        unsigned int a2,
        IUnknown *a3,
        struct _GUID *a4,
        void **ppv)
{
  char v7; // al
  __int64 v8; // rbx
  IUnknown *v9; // r12
  int ContinueOnSite; // ebx
  int v11; // ecx
  int v12; // r8d
  __int64 (__fastcall ***v13)(_QWORD, GUID *, IUnknown **); // rcx
  __int64 v14; // rsi
  int v15; // ecx
  int v16; // r8d
  int v17; // ecx
  int v18; // r8d
  __int64 v19; // rdx
  unsigned int v20; // r15d
  IUnknown *v21; // rax
  IUnknown *v22; // rcx
  int v23; // r12d
  int v24; // r13d
  CQueryResult *v25; // rax
  CQueryResult *v26; // rsi
  CQueryResultSet *v28; // rcx
  struct IServiceProvider *v29; // r9
  void *v30; // [rsp+20h] [rbp-118h]
  int v31; // [rsp+50h] [rbp-E8h] BYREF
  IUnknown *punk; // [rsp+58h] [rbp-E0h] BYREF
  struct IPropertyStoreCache *v33; // [rsp+60h] [rbp-D8h] BYREF
  __int64 v34; // [rsp+68h] [rbp-D0h] BYREF
  __int64 v35; // [rsp+70h] [rbp-C8h]
  __int64 *v36; // [rsp+78h] [rbp-C0h] BYREF
  __int64 v37; // [rsp+80h] [rbp-B8h] BYREF
  IID *riid; // [rsp+88h] [rbp-B0h]
  _QWORD v39[4]; // [rsp+90h] [rbp-A8h] BYREF
  _BYTE v40[24]; // [rsp+B0h] [rbp-88h] BYREF
  __int64 v41; // [rsp+C8h] [rbp-70h]
  __int64 *v42; // [rsp+D0h] [rbp-68h]
  __int64 v43; // [rsp+D8h] [rbp-60h]
  struct IPropertyStoreCache **v44; // [rsp+E0h] [rbp-58h]
  __int64 v45; // [rsp+E8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  riid = a4;
  *ppv = 0;
  if ( *((_DWORD *)this + 94) )
  {
    ContinueOnSite = 1;
    if ( a2 >= *((_DWORD *)this + 95) )
      return (unsigned int)ContinueOnSite;
  }
  v7 = Microsoft_Windows_Shell_CoreEnableBits;
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
  {
    LODWORD(v33) = 1;
    LODWORD(v34) = a2;
    *(_QWORD *)&v40[16] = (char *)this + 232;
    v41 = 16;
    v42 = &v34;
    v43 = 4;
    v44 = &v33;
    v45 = 4;
    McGenEventWrite_EtwEventWriteTransfer(4, (unsigned int)DataLayer_RowsetGetRows_Start, (_DWORD)a3, 4, (__int64)v40);
    v7 = Microsoft_Windows_Shell_CoreEnableBits;
  }
  v37 = 0;
  v35 = 0;
  v36 = &v37;
  v8 = *((_QWORD *)this + 35);
  v9 = (IUnknown *)*((_QWORD *)this + 28);
  if ( (v7 & 0x10) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      (unsigned int)&v37,
      (unsigned int)DataLayer_GetRowsAt_Start,
      (_DWORD)a3,
      1,
      (__int64)v39);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 13);
  LOBYTE(v31) = 1;
  IUnknown_SetSite(v9, a3);
  v30 = &v31;
  ContinueOnSite = ((__int64 (__fastcall *)(IUnknown *, _QWORD, __int64, __int64))v9->lpVtbl[3].QueryInterface)(
                     v9,
                     0,
                     v8,
                     1);
  IUnknown_SetSite(v9, 0);
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 13);
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 0x10) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(v11, (unsigned int)DataLayer_GetRowsAt_Stop, v12, 1, (__int64)v39);
  if ( ContinueOnSite < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1517,
      (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
      (const char *)(unsigned int)ContinueOnSite,
      (int)v30);
    goto LABEL_37;
  }
  if ( v35 )
  {
    *ppv = 0;
    v33 = 0;
    v13 = (__int64 (__fastcall ***)(_QWORD, GUID *, IUnknown **))*((_QWORD *)this + 28);
    if ( !v13 )
    {
      ContinueOnSite = -2147467259;
      goto LABEL_45;
    }
    v14 = v37;
    punk = 0;
    ContinueOnSite = (**v13)(v13, &GUID_0c733aaf_2a1c_11ce_ade5_00aa0044773d, &punk);
    if ( ContinueOnSite < 0 )
      goto LABEL_46;
    ContinueOnSite = QueryContinueOnSite(a3);
    if ( ContinueOnSite >= 0 )
    {
      if ( (Microsoft_Windows_Shell_CoreEnableBits & 0x20) != 0 )
        McGenEventWrite_EtwEventWriteTransfer(v15, (unsigned int)DataLayer_GetRowFromHROW_Start, v16, 1, (__int64)v39);
      EnterCriticalSection((LPCRITICAL_SECTION)this + 13);
      IUnknown_SetSite(punk, a3);
      v30 = &v33;
      ContinueOnSite = ((__int64 (__fastcall *)(IUnknown *, _QWORD, __int64, GUID *))punk->lpVtbl[1].QueryInterface)(
                         punk,
                         0,
                         v14,
                         &GUID_3017056d_9a91_4e90_937d_746c72abbf4f);
      IUnknown_SetSite(punk, 0);
      LeaveCriticalSection((LPCRITICAL_SECTION)this + 13);
      if ( (Microsoft_Windows_Shell_CoreEnableBits & 0x20) != 0 )
        McGenEventWrite_EtwEventWriteTransfer(v17, (unsigned int)DataLayer_GetRowFromHROW_Stop, v18, 1, (__int64)v39);
    }
    ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
    if ( ContinueOnSite < 0 )
    {
LABEL_46:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x135F,
        (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
        (const char *)(unsigned int)ContinueOnSite,
        (int)v30);
      goto LABEL_45;
    }
    memset(v40, 0, 20);
    v36 = 0;
    if ( (*(int (__fastcall **)(_QWORD, _BYTE *, GUID *, __int64 **))(**((_QWORD **)this + 46) + 56LL))(
           *((_QWORD *)this + 46),
           v40,
           &GUID_6bc63938_8254_4965_9680_565933185060,
           &v36) >= 0 )
    {
      v20 = *((_DWORD *)this + 66);
      ContinueOnSite = IPropertyStore_SetPropertyKey(v33, v19, v40);
      if ( ContinueOnSite >= 0 && (*((_BYTE *)this + 268) & 1) != 0 )
        ContinueOnSite = CQueryResultSet::_ComputeStackHashFromRows(v28, (const struct _tagpropertykey *)v40, v33, v29);
      (*(void (__fastcall **)(__int64 *))(*v36 + 16))(v36);
      if ( ContinueOnSite < 0 )
      {
LABEL_35:
        ((void (__fastcall *)(struct IPropertyStoreCache *))v33->lpVtbl->Release)(v33);
        if ( ContinueOnSite >= 0 )
        {
LABEL_36:
          LODWORD(v30) = 0;
          (*(void (__fastcall **)(_QWORD, __int64, __int64 *, _QWORD))(**((_QWORD **)this + 28) + 48LL))(
            *((_QWORD *)this + 28),
            v35,
            &v37,
            0);
          goto LABEL_37;
        }
LABEL_45:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x13EF,
          (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
          (const char *)(unsigned int)ContinueOnSite,
          (int)v30);
        goto LABEL_36;
      }
    }
    else
    {
      v20 = 1;
    }
    if ( !*((_QWORD *)this + 39) )
      goto LABEL_30;
    LODWORD(v34) = 0;
    if ( ((int (__fastcall *)(struct IPropertyStoreCache *, const PROPERTYKEY *, __int64 *))v33->lpVtbl->GetState)(
           v33,
           &PKEY_Search_AutoSummary,
           &v34) < 0
      || (_DWORD)v34 )
    {
      goto LABEL_30;
    }
    punk = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&punk);
    v21 = (IUnknown *)SHCreateMemStream(0, 0);
    punk = v21;
    if ( v21 )
    {
      ContinueOnSite = IUnknown_SaveKnownImplToStream(
                         (struct IStream *)v21,
                         (const struct _GUID *const *)&off_1800EB310,
                         3u,
                         *((struct IUnknown **)this + 39));
      if ( ContinueOnSite >= 0 )
      {
        IStream_Reset((IStream *)punk);
        v39[0] = 13;
        v39[2] = 0;
        v39[1] = punk;
        ContinueOnSite = ((__int64 (__fastcall *)(struct IPropertyStoreCache *, __int64 *, _QWORD *))v33->lpVtbl->SetValue)(
                           v33,
                           PKEY_ItemQueryCondition,
                           v39);
      }
    }
    else
    {
      ContinueOnSite = -2147024882;
    }
    v22 = punk;
    if ( punk )
    {
      punk = 0;
      ((void (__fastcall *)(IUnknown *))v22->lpVtbl->Release)(v22);
    }
    if ( ContinueOnSite >= 0 )
    {
LABEL_30:
      v23 = *((_DWORD *)this + 68);
      v24 = *((_DWORD *)this + 76);
      punk = (IUnknown *)v33;
      v34 = *((_QWORD *)this + 31);
      *ppv = 0;
      ContinueOnSite = -2147024882;
      v25 = (CQueryResult *)operator new(0xD8u, (const struct std::nothrow_t *)&std::nothrow);
      v39[0] = v25;
      if ( !v25 )
        goto LABEL_32;
      v26 = CQueryResult::CQueryResult(v25);
      if ( !v26 )
        goto LABEL_32;
      ContinueOnSite = CQueryResult::_InitializeResultWithStore(
                         (__int64)v26,
                         v20,
                         (__int64)this + 560,
                         (__int64)this + 232,
                         v34,
                         v24,
                         0,
                         punk,
                         v23);
      if ( ContinueOnSite >= 0 )
        ContinueOnSite = QISearch(v26, &`CQueryResult::QueryInterface'::`2'::qit, riid, ppv);
      CQueryResult::Release(v26);
      if ( ContinueOnSite < 0 )
LABEL_32:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x460,
          (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
          (const char *)(unsigned int)ContinueOnSite,
          (int)v30);
    }
    goto LABEL_35;
  }
  ContinueOnSite = 1;
LABEL_37:
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
  {
    LODWORD(v33) = v35;
    *(_QWORD *)&v40[16] = &v33;
    v41 = 4;
    McGenEventWrite_EtwEventWriteTransfer(v11, (unsigned int)DataLayer_RowsetGetRows_Stop, v12, 2, (__int64)v40);
  }
  if ( ContinueOnSite < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1538,
      (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
      (const char *)(unsigned int)ContinueOnSite,
      (int)v30);
  return (unsigned int)ContinueOnSite;
}

```

## disassembly

```asm
0x18001cb30  push    rbx
0x18001cb32  push    rsi
0x18001cb33  push    rdi
0x18001cb34  push    r12
0x18001cb36  push    r13
0x18001cb38  push    r14
0x18001cb3a  push    r15
0x18001cb3c  sub     rsp, 100h
0x18001cb43  mov     rax, cs:__security_cookie
0x18001cb4a  xor     rax, rsp
0x18001cb4d  mov     [rsp+138h+var_48], rax
0x18001cb55  mov     [rsp+138h+riid], r9
0x18001cb5d  mov     r15, r8
0x18001cb60  mov     esi, edx
0x18001cb62  mov     rdi, rcx
0x18001cb65  mov     r14, [rsp+138h+ppv]
0x18001cb6d  xor     ebx, ebx
0x18001cb6f  mov     [r14], rbx
0x18001cb72  cmp     [rcx+178h], ebx
0x18001cb78  jnz     loc_18001D02A
0x18001cb7e  mov     rax, cs:Microsoft_Windows_Shell_CoreEnableBits
0x18001cb85  mov     ecx, 4
0x18001cb8a  test    al, 1
0x18001cb8c  jnz     loc_18001CFB1
0x18001cb92  mov     [rsp+138h+var_B8], rbx
0x18001cb9a  mov     [rsp+138h+var_C8], rbx
0x18001cb9f  lea     rcx, [rsp+138h+var_B8]
0x18001cba7  mov     [rsp+138h+var_C0], rcx
0x18001cbac  mov     rbx, [rdi+118h]
0x18001cbb3  mov     r12, [rdi+0E0h]
0x18001cbba  test    al, 10h
0x18001cbbc  jnz     loc_18001D115
0x18001cbc2  lea     r13, [rdi+208h]
0x18001cbc9  mov     rcx, r13; lpCriticalSection
0x18001cbcc  call    cs:__imp_EnterCriticalSection
0x18001cbd2  mov     byte ptr [rsp+138h+var_E8], 1
0x18001cbd7  mov     rdx, r15; punkSite
0x18001cbda  mov     rcx, r12; punk
0x18001cbdd  call    cs:__imp_IUnknown_SetSite
0x18001cbe3  mov     rax, [r12]
0x18001cbe7  lea     rcx, [rsp+138h+var_C0]
0x18001cbec  mov     [rsp+138h+var_F8], rcx
0x18001cbf1  lea     rcx, [rsp+138h+var_C8]
0x18001cbf6  mov     [rsp+138h+var_100], rcx
0x18001cbfb  mov     [rsp+138h+var_108], 1
0x18001cc04  mov     [rsp+138h+var_110], rsi
0x18001cc09  lea     rcx, [rsp+138h+var_E8]
0x18001cc0e  mov     qword ptr [rsp+138h+var_118], rcx; int
0x18001cc13  mov     r9d, 1
0x18001cc19  mov     r8, rbx
0x18001cc1c  xor     edx, edx
0x18001cc1e  mov     rcx, r12
0x18001cc21  mov     rax, [rax+48h]
0x18001cc25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc2a  mov     ebx, eax
0x18001cc2c  xor     edx, edx; punkSite
0x18001cc2e  mov     rcx, r12; punk
0x18001cc31  call    cs:__imp_IUnknown_SetSite
0x18001cc37  mov     rcx, r13; lpCriticalSection
0x18001cc3a  call    cs:__imp_LeaveCriticalSection
0x18001cc40  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, 10h
0x18001cc47  jnz     loc_18001D139
0x18001cc4d  xor     r12d, r12d
0x18001cc50  test    ebx, ebx
0x18001cc52  js      loc_18001D15D
0x18001cc58  cmp     [rsp+138h+var_C8], r12
0x18001cc5d  jz      loc_18001CF1E
0x18001cc63  mov     [r14], r12
0x18001cc66  mov     [rsp+138h+var_D8], r12
0x18001cc6b  mov     rcx, [rdi+0E0h]
0x18001cc72  test    rcx, rcx
0x18001cc75  jz      loc_18001D087
0x18001cc7b  mov     rsi, [rsp+138h+var_B8]
0x18001cc83  mov     [rsp+138h+punk], r12
0x18001cc88  mov     rax, [rcx]
0x18001cc8b  lea     r8, [rsp+138h+punk]
0x18001cc90  lea     rdx, _GUID_0c733aaf_2a1c_11ce_ade5_00aa0044773d
0x18001cc97  mov     rax, [rax]
0x18001cc9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc9f  mov     ebx, eax
0x18001cca1  test    eax, eax
0x18001cca3  js      loc_18001D0B5
0x18001cca9  mov     rcx, r15; struct IUnknown *
0x18001ccac  call    ?QueryContinueOnSite@@YAJPEAUIUnknown@@@Z; QueryContinueOnSite(IUnknown *)
0x18001ccb1  mov     ebx, eax
0x18001ccb3  test    eax, eax
0x18001ccb5  js      short loc_18001CD27
0x18001ccb7  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, 20h
0x18001ccbe  jnz     loc_18001D0D3
0x18001ccc4  mov     rcx, r13; lpCriticalSection
0x18001ccc7  call    cs:__imp_EnterCriticalSection
0x18001cccd  mov     rdx, r15; punkSite
0x18001ccd0  mov     rcx, [rsp+138h+punk]; punk
0x18001ccd5  call    cs:__imp_IUnknown_SetSite
0x18001ccdb  mov     rcx, [rsp+138h+punk]
0x18001cce0  mov     rax, [rcx]
0x18001cce3  lea     rdx, [rsp+138h+var_D8]
0x18001cce8  mov     qword ptr [rsp+138h+var_118], rdx; int
0x18001cced  lea     r9, _GUID_3017056d_9a91_4e90_937d_746c72abbf4f
0x18001ccf4  mov     r8, rsi
0x18001ccf7  xor     edx, edx
0x18001ccf9  mov     rax, [rax+18h]
0x18001ccfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd02  mov     ebx, eax
0x18001cd04  xor     edx, edx; punkSite
0x18001cd06  mov     rcx, [rsp+138h+punk]; punk
0x18001cd0b  call    cs:__imp_IUnknown_SetSite
0x18001cd11  mov     rcx, r13; lpCriticalSection
0x18001cd14  call    cs:__imp_LeaveCriticalSection
0x18001cd1a  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, 20h
0x18001cd21  jnz     loc_18001D17E
0x18001cd27  mov     rcx, [rsp+138h+punk]
0x18001cd2c  mov     rax, [rcx]
0x18001cd2f  mov     rax, [rax+10h]
0x18001cd33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd38  test    ebx, ebx
0x18001cd3a  js      loc_18001D0B5
0x18001cd40  xorps   xmm0, xmm0
0x18001cd43  xor     eax, eax
0x18001cd45  movups  xmmword ptr [rsp+138h+var_88], xmm0
0x18001cd4d  mov     dword ptr [rsp+138h+var_88+10h], eax
0x18001cd54  mov     [rsp+138h+var_C0], r12
0x18001cd59  mov     rcx, [rdi+170h]
0x18001cd60  mov     rax, [rcx]
0x18001cd63  lea     r9, [rsp+138h+var_C0]
0x18001cd68  lea     r8, _GUID_6bc63938_8254_4965_9680_565933185060
0x18001cd6f  lea     rdx, [rsp+138h+var_88]
0x18001cd77  mov     rax, [rax+38h]
0x18001cd7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd80  test    eax, eax
0x18001cd82  jns     loc_18001D1A2
0x18001cd88  mov     r15d, 1
0x18001cd8e  mov     esi, 8007000Eh
0x18001cd93  cmp     [rdi+138h], r12
0x18001cd9a  jz      loc_18001CE9E
0x18001cda0  mov     dword ptr [rsp+138h+var_D0], r12d
0x18001cda5  mov     rcx, [rsp+138h+var_D8]
0x18001cdaa  mov     rax, [rcx]
0x18001cdad  lea     r8, [rsp+138h+var_D0]
0x18001cdb2  lea     rdx, PKEY_Search_AutoSummary
0x18001cdb9  mov     rax, [rax+40h]
0x18001cdbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cdc2  test    eax, eax
0x18001cdc4  js      loc_18001CE9E
0x18001cdca  cmp     dword ptr [rsp+138h+var_D0], r12d
0x18001cdcf  jnz     loc_18001CE9E
0x18001cdd5  mov     [rsp+138h+punk], r12
0x18001cdda  lea     rcx, [rsp+138h+punk]
0x18001cddf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001cde4  xor     edx, edx; cbInit
0x18001cde6  xor     ecx, ecx; pInit
0x18001cde8  call    cs:__imp_SHCreateMemStream
0x18001cdee  mov     [rsp+138h+punk], rax
0x18001cdf3  test    rax, rax
0x18001cdf6  jnz     short loc_18001CDFC
0x18001cdf8  mov     ebx, esi
0x18001cdfa  jmp     short loc_18001CE7A
0x18001cdfc  mov     r9, [rdi+138h]; struct IUnknown *
0x18001ce03  mov     r8d, 3; unsigned int
0x18001ce09  lea     rdx, off_1800EB310; struct _GUID **
0x18001ce10  mov     rcx, rax; pstm
0x18001ce13  call    ?IUnknown_SaveKnownImplToStream@@YAJPEAUIStream@@PEBQEBU_GUID@@IPEAUIUnknown@@@Z; IUnknown_SaveKnownImplToStream(IStream *,_GUID const * const *,uint,IUnknown *)
0x18001ce18  mov     ebx, eax
0x18001ce1a  test    eax, eax
0x18001ce1c  js      short loc_18001CE7A
0x18001ce1e  mov     rcx, [rsp+138h+punk]; pstm
0x18001ce23  call    cs:__imp_IStream_Reset
0x18001ce29  mov     rcx, [rsp+138h+var_D8]
0x18001ce2e  xorps   xmm0, xmm0
0x18001ce31  xor     eax, eax
0x18001ce33  movups  [rsp+138h+var_A8], xmm0
0x18001ce3b  mov     [rsp+138h+var_98], rax
0x18001ce43  mov     eax, 0Dh
0x18001ce48  mov     word ptr [rsp+138h+var_A8], ax
0x18001ce50  mov     rax, [rsp+138h+punk]
0x18001ce55  mov     qword ptr [rsp+138h+var_A8+8], rax
0x18001ce5d  mov     rax, [rcx]
0x18001ce60  lea     r8, [rsp+138h+var_A8]
0x18001ce68  lea     rdx, PKEY_ItemQueryCondition
0x18001ce6f  mov     rax, [rax+30h]
0x18001ce73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce78  mov     ebx, eax
0x18001ce7a  mov     rcx, [rsp+138h+punk]
0x18001ce7f  test    rcx, rcx
0x18001ce82  jz      short loc_18001CE96
0x18001ce84  mov     [rsp+138h+punk], r12
0x18001ce89  mov     rax, [rcx]
0x18001ce8c  mov     rax, [rax+10h]
0x18001ce90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce95  nop
0x18001ce96  test    ebx, ebx
0x18001ce98  js      loc_18001CF31
0x18001ce9e  mov     r12d, [rdi+110h]
0x18001cea5  mov     r13d, [rdi+130h]
0x18001ceac  mov     rax, [rsp+138h+var_D8]
0x18001ceb1  mov     [rsp+138h+punk], rax
0x18001ceb6  mov     rax, [rdi+0F8h]
0x18001cebd  mov     [rsp+138h+var_D0], rax
0x18001cec2  mov     qword ptr [r14], 0
0x18001cec9  mov     ebx, esi
0x18001cecb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001ced2  mov     ecx, 0D8h; unsigned __int64
0x18001ced7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001cedc  mov     qword ptr [rsp+138h+var_A8], rax
0x18001cee4  test    rax, rax
0x18001cee7  jz      short loc_18001CEFD
0x18001cee9  mov     rcx, rax; this
0x18001ceec  call    ??0CQueryResult@@AEAA@XZ; CQueryResult::CQueryResult(void)
0x18001cef1  mov     rsi, rax
0x18001cef4  test    rax, rax
0x18001cef7  jnz     loc_18001D1EB
0x18001cefd  xor     r12d, r12d
0x18001cf00  mov     rcx, [rsp+138h]; this
0x18001cf08  mov     r9d, ebx; char *
0x18001cf0b  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.storage.sear"...
0x18001cf12  mov     edx, 460h; void *
0x18001cf17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cf1c  jmp     short loc_18001CF31
0x18001cf1e  mov     ebx, 1
0x18001cf23  jmp     short loc_18001CF77
0x18001cf25  mov     rcx, rsi; this
0x18001cf28  call    ?Release@CQueryResult@@UEAAKXZ; CQueryResult::Release(void)
0x18001cf2d  test    ebx, ebx
0x18001cf2f  js      short loc_18001CF00
0x18001cf31  mov     rcx, [rsp+138h+var_D8]
0x18001cf36  mov     rax, [rcx]
0x18001cf39  mov     rax, [rax+10h]
0x18001cf3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf42  test    ebx, ebx
0x18001cf44  js      loc_18001D094
0x18001cf4a  mov     rcx, [rdi+0E0h]
0x18001cf51  mov     rax, [rcx]
0x18001cf54  mov     [rsp+138h+var_110], r12
0x18001cf59  mov     qword ptr [rsp+138h+var_118], r12; int
0x18001cf5e  xor     r9d, r9d
0x18001cf61  lea     r8, [rsp+138h+var_B8]
0x18001cf69  mov     rdx, [rsp+138h+var_C8]
0x18001cf6e  mov     rax, [rax+30h]
0x18001cf72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf77  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x18001cf7e  jnz     loc_18001D042
0x18001cf84  test    ebx, ebx
0x18001cf86  js      loc_18001D256
0x18001cf8c  mov     eax, ebx
0x18001cf8e  mov     rcx, [rsp+138h+var_48]
0x18001cf96  xor     rcx, rsp; StackCookie
0x18001cf99  call    __security_check_cookie
0x18001cf9e  add     rsp, 100h
0x18001cfa5  pop     r15
0x18001cfa7  pop     r14
0x18001cfa9  pop     r13
0x18001cfab  pop     r12
0x18001cfad  pop     rdi
0x18001cfae  pop     rsi
0x18001cfaf  pop     rbx
0x18001cfb0  retn
0x18001cfb1  mov     dword ptr [rsp+138h+var_D8], 1
0x18001cfb9  mov     dword ptr [rsp+138h+var_D0], esi
0x18001cfbd  lea     rax, [rdi+0E8h]
0x18001cfc4  mov     qword ptr [rsp+138h+var_88+10h], rax
0x18001cfcc  mov     [rsp+138h+var_70], 10h
0x18001cfd8  lea     rax, [rsp+138h+var_D0]
0x18001cfdd  mov     [rsp+138h+var_68], rax
0x18001cfe5  mov     [rsp+138h+var_60], rcx
0x18001cfed  lea     rax, [rsp+138h+var_D8]
0x18001cff2  mov     [rsp+138h+var_58], rax
0x18001cffa  mov     [rsp+138h+var_50], rcx
0x18001d002  lea     rax, [rsp+138h+var_88]
0x18001d00a  mov     qword ptr [rsp+138h+var_118], rax
0x18001d00f  mov     r9d, ecx
0x18001d012  lea     rdx, DataLayer_RowsetGetRows_Start
0x18001d019  call    McGenEventWrite_EtwEventWriteTransfer
0x18001d01e  mov     rax, cs:Microsoft_Windows_Shell_CoreEnableBits
0x18001d025  jmp     loc_18001CB92
0x18001d02a  mov     ebx, 1
0x18001d02f  cmp     esi, [rcx+17Ch]
0x18001d035  jnb     loc_18001CF8C
0x18001d03b  xor     ebx, ebx
0x18001d03d  jmp     loc_18001CB7E
0x18001d042  mov     eax, dword ptr [rsp+138h+var_C8]
0x18001d046  mov     dword ptr [rsp+138h+var_D8], eax
0x18001d04a  lea     rax, [rsp+138h+var_D8]
0x18001d04f  mov     qword ptr [rsp+138h+var_88+10h], rax
0x18001d057  mov     [rsp+138h+var_70], 4
0x18001d063  lea     rax, [rsp+138h+var_88]
0x18001d06b  mov     qword ptr [rsp+138h+var_118], rax
0x18001d070  mov     r9d, 2
0x18001d076  lea     rdx, DataLayer_RowsetGetRows_Stop
0x18001d07d  call    McGenEventWrite_EtwEventWriteTransfer
0x18001d082  jmp     loc_18001CF84
0x18001d087  mov     ebx, 80004005h
0x18001d08c  test    ebx, ebx
0x18001d08e  jns     loc_18001CD40
0x18001d094  mov     rcx, [rsp+138h]; this
0x18001d09c  mov     r9d, ebx; char *
0x18001d09f  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.storage.sear"...
0x18001d0a6  mov     edx, 13EFh; void *
0x18001d0ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d0b0  jmp     loc_18001CF4A
0x18001d0b5  mov     rcx, [rsp+138h]; this
  ... truncated ...
```
