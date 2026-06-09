# CAppln::UnInit(void)

- ea: `0x1800328b4`
- end: `0x180032c96`
- name: `?UnInit@CAppln@@QEAAJXZ`
- size: `994`
- prototype: `__int64 __fastcall(LPUNKNOWN pUnk)`
- caller_count: `4`
- callee_count: `17`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180006c80`
- `0x18000ca50`
- `0x180031358`
- `0x180031488`

## callees

- `0x1800075e0`
- `0x18000f690`
- `0x1800134f0`
- `0x180019f44`
- `0x180030df0`
- `0x180030f10`
- `0x18003131c`
- `0x180031548`
- `0x1800328b4`
- `0x180032cfc`
- `0x180034160`
- `0x180035134`
- `0x180047b9c`
- `0x180047d98`
- `0x180047e2c`
- `0x1800586ac`
- `0x180064010`

## import_xrefs

- `ole32!CoDisconnectObject` at `0x180032c83`
- `ole32!CoDisconnectObject` at `0x180032c83`
- `KERNEL32!HeapFree` at `0x180032b39`
- `KERNEL32!HeapFree` at `0x180032bb1`
- `KERNEL32!HeapFree` at `0x180032bd0`
- `KERNEL32!HeapFree` at `0x180032bec`
- `KERNEL32!HeapFree` at `0x180032c08`
- `KERNEL32!HeapFree` at `0x180032c24`
- `KERNEL32!HeapFree` at `0x180032b39`
- `KERNEL32!HeapFree` at `0x180032bb1`
- `KERNEL32!HeapFree` at `0x180032bd0`
- `KERNEL32!HeapFree` at `0x180032bec`
- `KERNEL32!HeapFree` at `0x180032c08`
- `KERNEL32!HeapFree` at `0x180032c24`
- `KERNEL32!LeaveCriticalSection` at `0x18003290c`
- `KERNEL32!LeaveCriticalSection` at `0x180032919`
- `KERNEL32!LeaveCriticalSection` at `0x1800329b7`
- `KERNEL32!LeaveCriticalSection` at `0x18003290c`
- `KERNEL32!LeaveCriticalSection` at `0x180032919`
- `KERNEL32!LeaveCriticalSection` at `0x1800329b7`
- `KERNEL32!EnterCriticalSection` at `0x1800328e6`
- `KERNEL32!EnterCriticalSection` at `0x1800328f3`
- `KERNEL32!EnterCriticalSection` at `0x18003292d`
- `KERNEL32!EnterCriticalSection` at `0x1800328e6`
- `KERNEL32!EnterCriticalSection` at `0x1800328f3`
- `KERNEL32!EnterCriticalSection` at `0x18003292d`
- `KERNEL32!DeleteCriticalSection` at `0x180032c3b`
- `KERNEL32!DeleteCriticalSection` at `0x180032c4e`
- `KERNEL32!DeleteCriticalSection` at `0x180032c3b`
- `KERNEL32!DeleteCriticalSection` at `0x180032c4e`

## pseudocode

```c
__int64 __fastcall CAppln::UnInit(CScriptManager *pUnk)
{
  struct IUnknownVtbl *v1; // rdx
  int v3; // edi
  HRESULT (__stdcall *v4)(IUnknown *, const IID *const, void **); // rsi
  int v5; // ebp
  CPtrArray *v6; // rsi
  CPtrArray *v7; // rdi
  CApplnMgr *v8; // rcx
  unsigned int v9; // edx
  struct IUnknownVtbl *v10; // rcx
  struct IUnknownVtbl *v11; // rcx
  struct IUnknownVtbl *v12; // rcx
  struct IUnknownVtbl *v13; // rcx
  struct IUnknownVtbl *v14; // rcx
  struct IUnknownVtbl *v15; // rdi
  struct IUnknownVtbl *v16; // rcx
  struct IUnknownVtbl *v17; // rdx
  struct IUnknownVtbl *v18; // r8
  struct IUnknownVtbl *v19; // r8
  struct IUnknownVtbl *v20; // r8
  struct IUnknownVtbl *v21; // r8
  struct IUnknownVtbl *v22; // rcx

  v1 = (struct IUnknownVtbl *)*((_QWORD *)pUnk + 16);
  if ( v1 )
    CScriptManager::FlushCache(pUnk, (const unsigned __int16 *)v1);
  if ( *((_QWORD *)pUnk + 17) )
  {
    EnterCriticalSection(&stru_180079DF0);
    EnterCriticalSection(&g_IncFileMap);
    CTemplate::End(*((CTemplate **)pUnk + 17));
    LeaveCriticalSection(&stru_180079DF0);
    LeaveCriticalSection(&g_IncFileMap);
    *((_QWORD *)pUnk + 17) = 0;
  }
  EnterCriticalSection(&stru_18007A148);
  v3 = *((_DWORD *)pUnk + 82);
  if ( v3 <= 0 )
  {
    v6 = (CScriptManager *)((char *)pUnk + 312);
  }
  else
  {
    do
    {
      v4 = (HRESULT (__stdcall *)(IUnknown *, const IID *const, void **))**((_QWORD **)pUnk + 40);
      v5 = CPtrArray::Remove((CPtrArray *)((char *)v4 + 48), pUnk);
      if ( !*((_DWORD *)v4 + 16) )
      {
        CHashTable::RemoveElem((CHashTable *)&g_FileAppMap, (struct CLinkElem *)v4);
        (**(void (__fastcall ***)(HRESULT (__stdcall *)(IUnknown *, const IID *const, void **), __int64))v4)(v4, 1);
      }
      if ( !v5 )
        (*(void (__fastcall **)(CScriptManager *))(*(_QWORD *)pUnk + 16LL))(pUnk);
      v6 = (CScriptManager *)((char *)pUnk + 312);
      CPtrArray::Remove((CScriptManager *)((char *)pUnk + 312), 0);
      --v3;
    }
    while ( v3 > 0 );
  }
  LeaveCriticalSection(&stru_18007A148);
  CPtrArray::Clear(v6);
  (*(void (__fastcall **)(CScriptManager *))(*(_QWORD *)pUnk + 80LL))(pUnk);
  if ( *((_DWORD *)pUnk + 76) )
  {
    do
    {
      (*(void (__fastcall **)(HRESULT (__stdcall *)(IUnknown *, const IID *const, void **)))(***((_QWORD ***)pUnk + 37)
                                                                                           + 16LL))(**((HRESULT (__stdcall ***)(IUnknown *, const IID *const, void **))pUnk + 37));
      v7 = (CScriptManager *)((char *)pUnk + 288);
      CPtrArray::Remove((CScriptManager *)((char *)pUnk + 288), 0);
    }
    while ( *((_DWORD *)pUnk + 76) );
  }
  else
  {
    v7 = (CScriptManager *)((char *)pUnk + 288);
  }
  CPtrArray::Clear(v7);
  (*(void (__fastcall **)(CScriptManager *))(*(_QWORD *)pUnk + 88LL))(pUnk);
  if ( (*((_BYTE *)pUnk + 72) & 0x20) != 0 )
    CApplnMgr::CleanupEngines(v8);
  CAppln::DisconnectObjects((LPUNKNOWN)pUnk);
  v10 = (struct IUnknownVtbl *)*((_QWORD *)pUnk + 21);
  if ( v10 )
  {
    CSessionVariants::UnInit((CSessionVariants *)v10);
    (*(void (__fastcall **)(struct IUnknownVtbl *))(**((_QWORD **)pUnk + 21) + 16LL))(*((struct IUnknownVtbl **)pUnk + 21));
    *((_QWORD *)pUnk + 21) = 0;
  }
  v11 = (struct IUnknownVtbl *)*((_QWORD *)pUnk + 22);
  if ( v11 )
  {
    CSessionVariants::UnInit((CSessionVariants *)v11);
    (*(void (__fastcall **)(struct IUnknownVtbl *))(**((_QWORD **)pUnk + 22) + 16LL))(*((struct IUnknownVtbl **)pUnk + 22));
    *((_QWORD *)pUnk + 22) = 0;
  }
  if ( (*((_BYTE *)pUnk + 72) & 0x20) != 0 )
    CTemplateCacheManager::RemoveApplicationFromDebuggerUI((CTemplateCacheManager *)v11, pUnk);
  v12 = (struct IUnknownVtbl *)*((_QWORD *)pUnk + 48);
  if ( v12 )
  {
    (*((void (__fastcall **)(struct IUnknownVtbl *))v12->QueryInterface + 11))(v12);
    (*(void (__fastcall **)(struct IUnknownVtbl *))(**((_QWORD **)pUnk + 48) + 72LL))(*((struct IUnknownVtbl **)pUnk + 48));
    (*(void (__fastcall **)(struct IUnknownVtbl *))(**((_QWORD **)pUnk + 48) + 16LL))(*((struct IUnknownVtbl **)pUnk + 48));
    *((_QWORD *)pUnk + 48) = 0;
  }
  v13 = (struct IUnknownVtbl *)*((_QWORD *)pUnk + 20);
  if ( v13 )
  {
    CComponentCollection::`scalar deleting destructor'((CComponentCollection *)v13, v9);
    *((_QWORD *)pUnk + 20) = 0;
  }
  v14 = (struct IUnknownVtbl *)*((_QWORD *)pUnk + 23);
  if ( v14 )
  {
    CViperActivity::`scalar deleting destructor'((CViperActivity *)v14, v9);
    *((_QWORD *)pUnk + 23) = 0;
  }
  v15 = (struct IUnknownVtbl *)*((_QWORD *)pUnk + 18);
  if ( v15 )
  {
    CSessionMgr::~CSessionMgr(*((CSessionMgr **)pUnk + 18));
    HeapFree(g_hDenaliHeap, 0, v15);
    *((_QWORD *)pUnk + 18) = 0;
  }
  if ( *((_QWORD *)pUnk + 19) )
  {
    CAppConfig::Release(*((CAppConfig **)pUnk + 19));
    *((_QWORD *)pUnk + 19) = 0;
  }
  v16 = (struct IUnknownVtbl *)*((_QWORD *)pUnk + 42);
  if ( v16 )
  {
    (*((void (__fastcall **)(struct IUnknownVtbl *))v16->QueryInterface + 2))(v16);
    *((_QWORD *)pUnk + 42) = 0;
  }
  v17 = (struct IUnknownVtbl *)*((_QWORD *)pUnk + 16);
  if ( v17 )
  {
    if ( (*((_BYTE *)pUnk + 72) & 4) != 0 )
      CTemplateCacheManager::Flush((CTemplateCacheManager *)v16, (const unsigned __int16 *)v17, 0xFFFBAD1D);
    HeapFree(g_hDenaliHeap, 0, *((LPVOID *)pUnk + 16));
    *((_QWORD *)pUnk + 16) = 0;
  }
  v18 = (struct IUnknownVtbl *)*((_QWORD *)pUnk + 12);
  if ( v18 )
  {
    HeapFree(g_hDenaliHeap, 0, v18);
    *((_QWORD *)pUnk + 12) = 0;
  }
  v19 = (struct IUnknownVtbl *)*((_QWORD *)pUnk + 13);
  if ( v19 )
  {
    HeapFree(g_hDenaliHeap, 0, v19);
    *((_QWORD *)pUnk + 13) = 0;
  }
  v20 = (struct IUnknownVtbl *)*((_QWORD *)pUnk + 14);
  if ( v20 )
  {
    HeapFree(g_hDenaliHeap, 0, v20);
    *((_QWORD *)pUnk + 14) = 0;
  }
  v21 = (struct IUnknownVtbl *)*((_QWORD *)pUnk + 15);
  if ( v21 )
  {
    HeapFree(g_hDenaliHeap, 0, v21);
    *((_QWORD *)pUnk + 15) = 0;
  }
  if ( (*((_BYTE *)pUnk + 72) & 0x40) != 0 )
    DeleteCriticalSection((LPCRITICAL_SECTION)pUnk + 5);
  if ( *((char *)pUnk + 72) < 0 )
    DeleteCriticalSection((LPCRITICAL_SECTION)pUnk + 6);
  v22 = (struct IUnknownVtbl *)*((_QWORD *)pUnk + 24);
  if ( v22 )
  {
    (*((void (__fastcall **)(struct IUnknownVtbl *))v22->QueryInterface + 2))(v22);
    *((_QWORD *)pUnk + 24) = 0;
  }
  *((_DWORD *)pUnk + 18) |= 0x10u;
  _InterlockedDecrement((volatile signed __int32 *)&g_nApplications);
  CoDisconnectObject((LPUNKNOWN)pUnk, 0);
  return 0;
}

```

## disassembly

```asm
0x1800328b4  push    rbx
0x1800328b6  push    rbp
0x1800328b7  push    rsi
0x1800328b8  push    rdi
0x1800328b9  push    r14
0x1800328bb  sub     rsp, 20h
0x1800328bf  mov     rdx, [rcx+80h]; unsigned __int16 *
0x1800328c6  xor     r14d, r14d
0x1800328c9  mov     rbx, rcx
0x1800328cc  test    rdx, rdx
0x1800328cf  jz      short loc_1800328D6
0x1800328d1  call    ?FlushCache@CScriptManager@@QEAAJPEBG@Z; CScriptManager::FlushCache(ushort const *)
0x1800328d6  cmp     [rbx+88h], r14
0x1800328dd  jz      short loc_180032926
0x1800328df  lea     rcx, stru_180079DF0; lpCriticalSection
0x1800328e6  call    cs:__imp_EnterCriticalSection
0x1800328ec  lea     rcx, ?g_IncFileMap@@3VCIncFileMap@@A; lpCriticalSection
0x1800328f3  call    cs:__imp_EnterCriticalSection
0x1800328f9  mov     rcx, [rbx+88h]; this
0x180032900  call    ?End@CTemplate@@QEAAKXZ; CTemplate::End(void)
0x180032905  lea     rcx, stru_180079DF0; lpCriticalSection
0x18003290c  call    cs:__imp_LeaveCriticalSection
0x180032912  lea     rcx, ?g_IncFileMap@@3VCIncFileMap@@A; lpCriticalSection
0x180032919  call    cs:__imp_LeaveCriticalSection
0x18003291f  mov     [rbx+88h], r14
0x180032926  lea     rcx, stru_18007A148; lpCriticalSection
0x18003292d  call    cs:__imp_EnterCriticalSection
0x180032933  mov     edi, [rbx+148h]
0x180032939  test    edi, edi
0x18003293b  jle     short loc_1800329A9
0x18003293d  mov     rax, [rbx+140h]
0x180032944  mov     rdx, rbx; void *
0x180032947  mov     rsi, [rax]
0x18003294a  lea     rcx, [rsi+30h]; this
0x18003294e  call    ?Remove@CPtrArray@@QEAAJPEAX@Z; CPtrArray::Remove(void *)
0x180032953  mov     ebp, eax
0x180032955  cmp     [rsi+40h], r14d
0x180032959  jnz     short loc_18003297D
0x18003295b  mov     rdx, rsi; struct CLinkElem *
0x18003295e  lea     rcx, ?g_FileAppMap@@3VCFileApplicationMap@@A; this
0x180032965  call    ?RemoveElem@CHashTable@@QEAAPEAUCLinkElem@@PEAU2@@Z; CHashTable::RemoveElem(CLinkElem *)
0x18003296a  mov     rdx, [rsi]
0x18003296d  mov     rcx, rsi
0x180032970  mov     rax, [rdx]
0x180032973  mov     edx, 1
0x180032978  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003297d  test    ebp, ebp
0x18003297f  jnz     short loc_180032990
0x180032981  mov     rax, [rbx]
0x180032984  mov     rcx, rbx
0x180032987  mov     rax, [rax+10h]
0x18003298b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032990  lea     rsi, [rbx+138h]
0x180032997  xor     edx, edx; int
0x180032999  mov     rcx, rsi; this
0x18003299c  call    ?Remove@CPtrArray@@QEAAJH@Z; CPtrArray::Remove(int)
0x1800329a1  dec     edi
0x1800329a3  test    edi, edi
0x1800329a5  jg      short loc_18003293D
0x1800329a7  jmp     short loc_1800329B0
0x1800329a9  lea     rsi, [rbx+138h]
0x1800329b0  lea     rcx, stru_18007A148; lpCriticalSection
0x1800329b7  call    cs:__imp_LeaveCriticalSection
0x1800329bd  mov     rcx, rsi; this
0x1800329c0  call    ?Clear@CPtrArray@@QEAAJXZ; CPtrArray::Clear(void)
0x1800329c5  mov     rax, [rbx]
0x1800329c8  mov     rcx, rbx
0x1800329cb  mov     rax, [rax+50h]
0x1800329cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800329d4  cmp     [rbx+130h], r14d
0x1800329db  jz      short loc_180032A0F
0x1800329dd  mov     rax, [rbx+128h]
0x1800329e4  mov     rcx, [rax]
0x1800329e7  mov     rax, [rcx]
0x1800329ea  mov     rax, [rax+10h]
0x1800329ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800329f3  lea     rdi, [rbx+120h]
0x1800329fa  xor     edx, edx; int
0x1800329fc  mov     rcx, rdi; this
0x1800329ff  call    ?Remove@CPtrArray@@QEAAJH@Z; CPtrArray::Remove(int)
0x180032a04  cmp     [rbx+130h], r14d
0x180032a0b  jnz     short loc_1800329DD
0x180032a0d  jmp     short loc_180032A16
0x180032a0f  lea     rdi, [rbx+120h]
0x180032a16  mov     rcx, rdi; this
0x180032a19  call    ?Clear@CPtrArray@@QEAAJXZ; CPtrArray::Clear(void)
0x180032a1e  mov     rax, [rbx]
0x180032a21  mov     rcx, rbx
0x180032a24  mov     rax, [rax+58h]
0x180032a28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032a2d  test    byte ptr [rbx+48h], 20h
0x180032a31  jz      short loc_180032A38
0x180032a33  call    ?CleanupEngines@CApplnMgr@@QEAAXXZ; CApplnMgr::CleanupEngines(void)
0x180032a38  mov     rcx, rbx; pUnk
0x180032a3b  call    ?DisconnectObjects@CAppln@@QEAAJXZ; CAppln::DisconnectObjects(void)
0x180032a40  mov     rcx, [rbx+0A8h]; this
0x180032a47  test    rcx, rcx
0x180032a4a  jz      short loc_180032A6B
0x180032a4c  call    ?UnInit@CSessionVariants@@QEAAJXZ; CSessionVariants::UnInit(void)
0x180032a51  mov     rcx, [rbx+0A8h]
0x180032a58  mov     rax, [rcx]
0x180032a5b  mov     rax, [rax+10h]
0x180032a5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032a64  mov     [rbx+0A8h], r14
0x180032a6b  mov     rcx, [rbx+0B0h]; this
0x180032a72  test    rcx, rcx
0x180032a75  jz      short loc_180032A96
0x180032a77  call    ?UnInit@CSessionVariants@@QEAAJXZ; CSessionVariants::UnInit(void)
0x180032a7c  mov     rcx, [rbx+0B0h]
0x180032a83  mov     rax, [rcx]
0x180032a86  mov     rax, [rax+10h]
0x180032a8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032a8f  mov     [rbx+0B0h], r14
0x180032a96  test    byte ptr [rbx+48h], 20h
0x180032a9a  jz      short loc_180032AA4
0x180032a9c  mov     rdx, rbx; struct CAppln *
0x180032a9f  call    ?RemoveApplicationFromDebuggerUI@CTemplateCacheManager@@QEAAXPEAVCAppln@@@Z; CTemplateCacheManager::RemoveApplicationFromDebuggerUI(CAppln *)
0x180032aa4  mov     rcx, [rbx+180h]
0x180032aab  test    rcx, rcx
0x180032aae  jz      short loc_180032AE9
0x180032ab0  mov     rax, [rcx]
0x180032ab3  mov     rax, [rax+58h]
0x180032ab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032abc  mov     rcx, [rbx+180h]
0x180032ac3  mov     rax, [rcx]
0x180032ac6  mov     rax, [rax+48h]
0x180032aca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032acf  mov     rcx, [rbx+180h]
0x180032ad6  mov     rax, [rcx]
0x180032ad9  mov     rax, [rax+10h]
0x180032add  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032ae2  mov     [rbx+180h], r14
0x180032ae9  mov     rcx, [rbx+0A0h]; this
0x180032af0  test    rcx, rcx
0x180032af3  jz      short loc_180032B01
0x180032af5  call    ??_GCComponentCollection@@QEAAPEAXI@Z; CComponentCollection::`scalar deleting destructor'(uint)
0x180032afa  mov     [rbx+0A0h], r14
0x180032b01  mov     rcx, [rbx+0B8h]; this
0x180032b08  test    rcx, rcx
0x180032b0b  jz      short loc_180032B19
0x180032b0d  call    ??_GCViperActivity@@QEAAPEAXI@Z; CViperActivity::`scalar deleting destructor'(uint)
0x180032b12  mov     [rbx+0B8h], r14
0x180032b19  mov     rdi, [rbx+90h]
0x180032b20  test    rdi, rdi
0x180032b23  jz      short loc_180032B46
0x180032b25  mov     rcx, rdi; this
0x180032b28  call    ??1CSessionMgr@@QEAA@XZ; CSessionMgr::~CSessionMgr(void)
0x180032b2d  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180032b34  mov     r8, rdi; lpMem
0x180032b37  xor     edx, edx; dwFlags
0x180032b39  call    cs:__imp_HeapFree
0x180032b3f  mov     [rbx+90h], r14
0x180032b46  mov     rax, [rbx+98h]
0x180032b4d  test    rax, rax
0x180032b50  jz      short loc_180032B65
0x180032b52  mov     rcx, [rbx+98h]; this
0x180032b59  call    ?Release@CAppConfig@@QEAAKXZ; CAppConfig::Release(void)
0x180032b5e  mov     [rbx+98h], r14
0x180032b65  mov     rcx, [rbx+150h]
0x180032b6c  test    rcx, rcx
0x180032b6f  jz      short loc_180032B84
0x180032b71  mov     rax, [rcx]
0x180032b74  mov     rax, [rax+10h]
0x180032b78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032b7d  mov     [rbx+150h], r14
0x180032b84  mov     rdx, [rbx+80h]; unsigned __int16 *
0x180032b8b  test    rdx, rdx
0x180032b8e  jz      short loc_180032BBE
0x180032b90  test    byte ptr [rbx+48h], 4
0x180032b94  jz      short loc_180032BA1
0x180032b96  mov     r8d, 0FFFBAD1Dh; unsigned int
0x180032b9c  call    ?Flush@CTemplateCacheManager@@QEAAXPEBGK@Z; CTemplateCacheManager::Flush(ushort const *,ulong)
0x180032ba1  mov     r8, [rbx+80h]; lpMem
0x180032ba8  xor     edx, edx; dwFlags
0x180032baa  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180032bb1  call    cs:__imp_HeapFree
0x180032bb7  mov     [rbx+80h], r14
0x180032bbe  mov     r8, [rbx+60h]; lpMem
0x180032bc2  test    r8, r8
0x180032bc5  jz      short loc_180032BDA
0x180032bc7  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180032bce  xor     edx, edx; dwFlags
0x180032bd0  call    cs:__imp_HeapFree
0x180032bd6  mov     [rbx+60h], r14
0x180032bda  mov     r8, [rbx+68h]; lpMem
0x180032bde  test    r8, r8
0x180032be1  jz      short loc_180032BF6
0x180032be3  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180032bea  xor     edx, edx; dwFlags
0x180032bec  call    cs:__imp_HeapFree
0x180032bf2  mov     [rbx+68h], r14
0x180032bf6  mov     r8, [rbx+70h]; lpMem
0x180032bfa  test    r8, r8
0x180032bfd  jz      short loc_180032C12
0x180032bff  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180032c06  xor     edx, edx; dwFlags
0x180032c08  call    cs:__imp_HeapFree
0x180032c0e  mov     [rbx+70h], r14
0x180032c12  mov     r8, [rbx+78h]; lpMem
0x180032c16  test    r8, r8
0x180032c19  jz      short loc_180032C2E
0x180032c1b  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180032c22  xor     edx, edx; dwFlags
0x180032c24  call    cs:__imp_HeapFree
0x180032c2a  mov     [rbx+78h], r14
0x180032c2e  test    byte ptr [rbx+48h], 40h
0x180032c32  jz      short loc_180032C41
0x180032c34  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180032c3b  call    cs:__imp_DeleteCriticalSection
0x180032c41  test    byte ptr [rbx+48h], 80h
0x180032c45  jz      short loc_180032C54
0x180032c47  lea     rcx, [rbx+0F0h]; lpCriticalSection
0x180032c4e  call    cs:__imp_DeleteCriticalSection
0x180032c54  mov     rcx, [rbx+0C0h]
0x180032c5b  test    rcx, rcx
0x180032c5e  jz      short loc_180032C73
0x180032c60  mov     rax, [rcx]
0x180032c63  mov     rax, [rax+10h]
0x180032c67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032c6c  mov     [rbx+0C0h], r14
0x180032c73  or      dword ptr [rbx+48h], 10h
0x180032c77  xor     edx, edx; dwReserved
0x180032c79  lock dec cs:?g_nApplications@@3KA; ulong g_nApplications
0x180032c80  mov     rcx, rbx; pUnk
0x180032c83  call    cs:__imp_CoDisconnectObject
0x180032c89  xor     eax, eax
0x180032c8b  add     rsp, 20h
0x180032c8f  pop     r14
0x180032c91  pop     rdi
0x180032c92  pop     rsi
0x180032c93  pop     rbp
0x180032c94  pop     rbx
0x180032c95  retn
```
