# CViperAsyncRequest::OnCall(void)

- ea: `0x18000e460`
- end: `0x18000e7f7`
- name: `?OnCall@CViperAsyncRequest@@UEAAJXZ`
- size: `919`
- prototype: `__int64 __fastcall(CViperAsyncRequest *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000ca50`
- `0x18000e460`
- `0x18000ef60`
- `0x18000f5d0`
- `0x180011590`
- `0x180047370`
- `0x1800492e4`
- `0x1800493a0`
- `0x180062a40`
- `0x180064010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800298a7`
- `KERNEL32!HeapFree` at `0x1800298d8`
- `KERNEL32!HeapFree` at `0x1800298a7`
- `KERNEL32!HeapFree` at `0x1800298d8`
- `KERNEL32!LeaveCriticalSection` at `0x18000e4fb`
- `KERNEL32!LeaveCriticalSection` at `0x1800297a2`
- `KERNEL32!LeaveCriticalSection` at `0x18000e4fb`
- `KERNEL32!LeaveCriticalSection` at `0x1800297a2`
- `KERNEL32!SetEvent` at `0x1800297da`
- `KERNEL32!SetEvent` at `0x1800297da`
- `KERNEL32!Sleep` at `0x18002978f`
- `KERNEL32!Sleep` at `0x18002978f`
- `KERNEL32!EnterCriticalSection` at `0x18000e4a2`
- `KERNEL32!EnterCriticalSection` at `0x18000e4a2`
- `KERNEL32!GetTickCount` at `0x1800297b5`
- `KERNEL32!GetTickCount` at `0x1800297b5`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000e7db`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000e7db`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000e76e`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000e77b`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000e788`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000e795`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000e7a2`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000e7af`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000e7bc`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000e7c6`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000e76e`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000e77b`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000e788`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000e795`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000e7a2`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000e7af`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000e7bc`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000e7c6`

## pseudocode

```c
__int64 __fastcall CViperAsyncRequest::OnCall(CViperAsyncRequest *this)
{
  CViperAsyncRequest *v2; // rdx
  int v3; // ebx
  __int64 v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rcx
  unsigned int (__fastcall *v7)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD); // rax
  const struct _GUID *v8; // rdx
  CHitObj *v9; // rcx
  int v10; // edx
  CHitObj *v11; // rcx
  void *(__fastcall *v12)(CHitObj *__hidden, unsigned int); // rax
  __int64 v13; // rax
  unsigned int (__fastcall *v14)(CViperAsyncRequest *__hidden); // rax
  __int64 v15; // rax
  __int64 v16; // rcx
  unsigned int (__fastcall *v17)(__int64, __int64, GUID **, _QWORD, _QWORD); // rax
  const struct _GUID *v18; // rdx
  __int64 v19; // rax
  __int64 v20; // rcx
  unsigned int (__fastcall *v21)(__int64, __int64, GUID **, _QWORD, _QWORD); // rax
  const struct _GUID *v22; // rdx
  __int64 *v23; // rcx
  void (*v24)(void); // rax
  __int64 v25; // rcx
  __int64 v26; // r10
  unsigned int i; // edi
  __int64 v29; // rsi
  void *v30; // r8
  void *v31; // r8
  HANDLE v32; // rcx
  GUID *v33; // [rsp+30h] [rbp-38h] BYREF
  __int128 v34; // [rsp+38h] [rbp-30h]
  int v35; // [rsp+78h] [rbp+10h] BYREF
  int v36; // [rsp+80h] [rbp+18h] BYREF

  _InterlockedIncrement(&g_nThreadsExecuting);
  if ( (dword_18007D2BC & 8) == 0 && (*((_DWORD *)this + 17) & 0x1000000) != 0 )
  {
    while ( 1 )
    {
      while ( (*((_DWORD *)this + 17) & 0x2000000) != 0 )
        Sleep(0x64u);
      EnterCriticalSection(&stru_18007D2C0);
      if ( (*((_DWORD *)this + 17) & 0x2000000) == 0 )
        break;
      LeaveCriticalSection(&stru_18007D2C0);
    }
    v2 = (CViperAsyncRequest *)*((_QWORD *)this + 3);
    if ( (CViperAsyncRequest *)((char *)this + 16) == v2 )
    {
      v3 = 0;
    }
    else
    {
      v3 = 1;
      *(_QWORD *)(*((_QWORD *)this + 4) + 8LL) = v2;
      *(_QWORD *)(*((_QWORD *)this + 3) + 16LL) = *((_QWORD *)this + 4);
      *((_DWORD *)this + 17) &= ~0x2000000u;
      *((_QWORD *)this + 3) = (char *)this + 16;
      *((_QWORD *)this + 4) = (char *)this + 16;
      --dword_18007D2B8;
    }
    LeaveCriticalSection(&stru_18007D2C0);
    if ( dword_18007D2B8 >= (unsigned int)dword_18007D32C
      || dword_18007D2B8 >= (unsigned int)dword_18007D310 && GetTickCount() / 0x3E8 > dword_18007D328 )
    {
      SetEvent(hEvent);
    }
    if ( !v3 )
    {
      (*(void (__fastcall **)(CViperAsyncRequest *))(*(_QWORD *)this + 16LL))(this);
      goto LABEL_45;
    }
  }
  v4 = *(_QWORD *)(*((_QWORD *)this + 6) + 64LL);
  v35 = 0;
  if ( v4 )
  {
    _InterlockedIncrement((volatile signed __int32 *)v4);
    v5 = *(_QWORD *)(v4 + 8);
    v33 = &`ActiveServerPagesASPTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
    v6 = *(_QWORD *)(v5 + 8);
    v7 = *(unsigned int (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))(v5 + 184);
    v34 = 0;
    if ( v7(v6, 1044, &v33, 0, 0) )
    {
      if ( DWORD2(v34) )
        AspReqEvents::ASP_DEQUEUE_REQUEST::RaiseEvent(*(struct _EXTENSION_CONTROL_BLOCK **)(v4 + 8), v8);
    }
  }
  CHitObj::ViperAsyncCallback(*((CHitObj **)this + 6), &v35);
  v9 = (CHitObj *)*((_QWORD *)this + 6);
  v10 = *((_DWORD *)v9 + 2);
  if ( (v10 & 0xF0000) == 0x10000 )
  {
    if ( v35 )
      goto LABEL_20;
    if ( (v10 & 0x800) != 0 )
      goto LABEL_17;
    CHitObj::ReportServerError(v9, 0x65u);
  }
  if ( !v35 )
  {
LABEL_17:
    v11 = (CHitObj *)*((_QWORD *)this + 6);
    if ( v11 )
    {
      v12 = **(void *(__fastcall ***)(CHitObj *__hidden, unsigned int))v11;
      if ( v12 == CHitObj::`scalar deleting destructor' )
        CHitObj::`scalar deleting destructor'(v11, 1u);
      else
        v12(v11, 1u);
    }
  }
LABEL_20:
  v13 = *(_QWORD *)this;
  *((_QWORD *)this + 6) = 0;
  v14 = *(unsigned int (__fastcall **)(CViperAsyncRequest *__hidden))(v13 + 16);
  if ( v14 == CViperAsyncRequest::Release )
    CViperAsyncRequest::Release(this);
  else
    v14(this);
  if ( v4 && _InterlockedExchangeAdd((volatile signed __int32 *)v4, 0xFFFFFFFF) == 1 )
  {
    v15 = *(_QWORD *)(v4 + 8);
    if ( v15 )
    {
      v16 = *(_QWORD *)(v15 + 8);
      v17 = *(unsigned int (__fastcall **)(__int64, __int64, GUID **, _QWORD, _QWORD))(v15 + 184);
      v33 = &`ActiveServerPagesASPTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
      v34 = 0;
      if ( v17(v16, 1044, &v33, 0, 0) && DWORD2(v34) )
        AspReqEvents::ASP_DONE_PROCESSING::RaiseEvent(*(struct _EXTENSION_CONTROL_BLOCK **)(v4 + 8), v18);
      v19 = *(_QWORD *)(v4 + 8);
      v33 = &`ActiveServerPagesASPTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
      v20 = *(_QWORD *)(v19 + 8);
      v21 = *(unsigned int (__fastcall **)(__int64, __int64, GUID **, _QWORD, _QWORD))(v19 + 184);
      v34 = 0;
      if ( v21(v20, 1044, &v33, 0, 0) && DWORD2(v34) )
        AspReqEvents::ASP_END_REQUEST::RaiseEvent(*(struct _EXTENSION_CONTROL_BLOCK **)(v4 + 8), v22);
    }
    v23 = *(__int64 **)(v4 + 1248);
    if ( v23 )
    {
      v24 = *(void (**)(void))(v4 + 1256);
      if ( (char *)v24 == (char *)CResponseBufferSet::SendResponseCompletion )
        CResponseBufferSet::SendResponseCompletion(v23);
      else
        v24();
      *(_QWORD *)(v4 + 1248) = 0;
      *(_QWORD *)(v4 + 1256) = 0;
    }
    v25 = *(_QWORD *)(v4 + 1232);
    if ( v25 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      *(_QWORD *)(v4 + 1232) = 0;
    }
    if ( *(_QWORD *)(v4 + 1272) )
    {
      for ( i = 0; i < *(_DWORD *)(v4 + 1268); ++i )
      {
        v29 = 8LL * i;
        v30 = *(void **)(v29 + *(_QWORD *)(v4 + 1272));
        if ( v30 )
        {
          HeapFree(g_hDenaliHeap, 0, v30);
          *(_QWORD *)(v29 + *(_QWORD *)(v4 + 1272)) = 0;
        }
      }
      v31 = *(void **)(v4 + 1272);
      v32 = g_hDenaliHeap;
      *(_DWORD *)(v4 + 1268) = 0;
      HeapFree(v32, 0, v31);
      *(_QWORD *)(v4 + 1272) = 0;
    }
    v26 = *(_QWORD *)(v4 + 8);
    if ( v26 )
    {
      v36 = 1;
      if ( (unsigned int)(*(_DWORD *)(v26 + 16) - 500) <= 0x63 || *(_DWORD *)(v4 + 1224) == 3 && *(_DWORD *)(v4 + 1228) )
        v36 = 4;
      (*(void (__fastcall **)(_QWORD, __int64, int *, _QWORD, _QWORD))(v26 + 184))(*(_QWORD *)(v26 + 8), 4, &v36, 0, 0);
    }
    BUFFER::~BUFFER((BUFFER *)(v4 + 1176));
    BUFFER::~BUFFER((BUFFER *)(v4 + 1128));
    BUFFER::~BUFFER((BUFFER *)(v4 + 1080));
    BUFFER::~BUFFER((BUFFER *)(v4 + 776));
    BUFFER::~BUFFER((BUFFER *)(v4 + 472));
    BUFFER::~BUFFER((BUFFER *)(v4 + 424));
    BUFFER::~BUFFER((BUFFER *)(v4 + 376));
    BUFFER::~BUFFER((BUFFER *)(v4 + 72));
    if ( CIsapiReqInfo::sm_pach )
      ALLOC_CACHE_HANDLER::Free(CIsapiReqInfo::sm_pach, (void *)v4);
  }
LABEL_45:
  _InterlockedDecrement(&g_nThreadsExecuting);
  return 0;
}

```

## disassembly

```asm
0x18000e460  push    rbx
0x18000e462  push    rbp
0x18000e463  push    rdi
0x18000e464  sub     rsp, 50h
0x18000e468  mov     rdi, rcx
0x18000e46b  lock inc cs:?g_nThreadsExecuting@@3JA; long g_nThreadsExecuting
0x18000e472  xor     ebp, ebp
0x18000e474  test    byte ptr cs:dword_18007D2BC, 8
0x18000e47b  jnz     loc_18000E527
0x18000e481  test    dword ptr [rcx+44h], 1000000h
0x18000e488  jz      loc_18000E527
0x18000e48e  test    dword ptr [rdi+44h], 2000000h
0x18000e495  jnz     loc_18002978A
0x18000e49b  lea     rcx, stru_18007D2C0; lpCriticalSection
0x18000e4a2  call    cs:__imp_EnterCriticalSection
0x18000e4a8  test    dword ptr [rdi+44h], 2000000h
0x18000e4af  jnz     loc_18002979B
0x18000e4b5  mov     rdx, [rdi+18h]
0x18000e4b9  lea     rcx, [rdi+10h]
0x18000e4bd  cmp     rcx, rdx
0x18000e4c0  jz      loc_1800297AE
0x18000e4c6  mov     rax, [rcx+10h]
0x18000e4ca  mov     ebx, 1
0x18000e4cf  mov     [rax+8], rdx
0x18000e4d3  mov     rdx, [rcx+8]
0x18000e4d7  mov     rax, [rcx+10h]
0x18000e4db  mov     [rdx+10h], rax
0x18000e4df  and     dword ptr [rdi+44h], 0FDFFFFFFh
0x18000e4e6  mov     [rcx+8], rcx
0x18000e4ea  mov     [rcx+10h], rcx
0x18000e4ee  dec     cs:dword_18007D2B8
0x18000e4f4  lea     rcx, stru_18007D2C0; lpCriticalSection
0x18000e4fb  call    cs:__imp_LeaveCriticalSection
0x18000e501  mov     eax, cs:dword_18007D2B8
0x18000e507  cmp     eax, cs:dword_18007D32C
0x18000e50d  jnb     loc_1800297D3
0x18000e513  cmp     eax, cs:dword_18007D310
0x18000e519  jnb     loc_1800297B5
0x18000e51f  test    ebx, ebx
0x18000e521  jz      loc_1800297E6
0x18000e527  mov     rbx, [rdi+30h]
0x18000e52b  mov     [rsp+68h+arg_0], rsi
0x18000e530  lea     rsi, ?ProviderGuid@?1??GetProviderGuid@ActiveServerPagesASPTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `ActiveServerPagesASPTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000e537  mov     rbx, [rbx+40h]
0x18000e53b  mov     [rsp+68h+arg_8], ebp
0x18000e53f  test    rbx, rbx
0x18000e542  jz      short loc_18000E589
0x18000e544  lock inc dword ptr [rbx]
0x18000e547  mov     rax, [rbx+8]
0x18000e54b  lea     r8, [rsp+68h+var_38]
0x18000e550  xorps   xmm0, xmm0
0x18000e553  mov     [rsp+68h+var_38], rsi
0x18000e558  xor     r9d, r9d
0x18000e55b  mov     [rsp+68h+var_48], rbp
0x18000e560  mov     edx, 414h
0x18000e565  mov     rcx, [rax+8]
0x18000e569  mov     rax, [rax+0B8h]
0x18000e570  movdqu  [rsp+68h+var_30], xmm0
0x18000e576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e57b  test    eax, eax
0x18000e57d  jz      short loc_18000E589
0x18000e57f  cmp     dword ptr [rsp+68h+var_30+8], ebp
0x18000e583  jnz     loc_1800297FB
0x18000e589  mov     rcx, [rdi+30h]; this
0x18000e58d  lea     rdx, [rsp+68h+arg_8]; int *
0x18000e592  call    ?ViperAsyncCallback@CHitObj@@QEAAJPEAH@Z; CHitObj::ViperAsyncCallback(int *)
0x18000e597  mov     rcx, [rdi+30h]; this
0x18000e59b  mov     edx, [rcx+8]
0x18000e59e  mov     eax, edx
0x18000e5a0  and     eax, 0F0000h
0x18000e5a5  cmp     eax, 10000h
0x18000e5aa  jnz     loc_180029814
0x18000e5b0  cmp     [rsp+68h+arg_8], ebp
0x18000e5b4  jnz     short loc_18000E5E9
0x18000e5b6  bt      edx, 0Bh
0x18000e5ba  jnb     loc_18002980A
0x18000e5c0  mov     rcx, [rdi+30h]; this
0x18000e5c4  test    rcx, rcx
0x18000e5c7  jz      short loc_18000E5E9
0x18000e5c9  mov     rax, [rcx]
0x18000e5cc  lea     rdx, ??_GCHitObj@@UEAAPEAXI@Z; CHitObj::`scalar deleting destructor'(uint)
0x18000e5d3  mov     rax, [rax]
0x18000e5d6  cmp     rax, rdx
0x18000e5d9  mov     edx, 1; unsigned int
0x18000e5de  jnz     loc_180029823
0x18000e5e4  call    ??_GCHitObj@@UEAAPEAXI@Z; CHitObj::`scalar deleting destructor'(uint)
0x18000e5e9  mov     rax, [rdi]
0x18000e5ec  lea     rcx, ?Release@CViperAsyncRequest@@UEAAKXZ; CViperAsyncRequest::Release(void)
0x18000e5f3  mov     [rdi+30h], rbp
0x18000e5f7  mov     rax, [rax+10h]
0x18000e5fb  cmp     rax, rcx
0x18000e5fe  mov     rcx, rdi; this
0x18000e601  jnz     loc_18002982E
0x18000e607  call    ?Release@CViperAsyncRequest@@UEAAKXZ; CViperAsyncRequest::Release(void)
0x18000e60c  test    rbx, rbx
0x18000e60f  jz      loc_18000E7E1
0x18000e615  mov     eax, 0FFFFFFFFh
0x18000e61a  lock xadd [rbx], eax
0x18000e61e  cmp     eax, 1
0x18000e621  jnz     loc_18000E7E1
0x18000e627  mov     rax, [rbx+8]
0x18000e62b  test    rax, rax
0x18000e62e  jz      loc_18000E6B4
0x18000e634  mov     rcx, [rax+8]
0x18000e638  lea     r8, [rsp+68h+var_38]
0x18000e63d  mov     rax, [rax+0B8h]
0x18000e644  xorps   xmm0, xmm0
0x18000e647  xor     r9d, r9d
0x18000e64a  mov     [rsp+68h+var_38], rsi
0x18000e64f  mov     edx, 414h
0x18000e654  mov     [rsp+68h+var_48], rbp
0x18000e659  movdqu  [rsp+68h+var_30], xmm0
0x18000e65f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e664  test    eax, eax
0x18000e666  jz      short loc_18000E672
0x18000e668  cmp     dword ptr [rsp+68h+var_30+8], ebp
0x18000e66c  jnz     loc_180029839
0x18000e672  mov     rax, [rbx+8]
0x18000e676  lea     r8, [rsp+68h+var_38]
0x18000e67b  xorps   xmm0, xmm0
0x18000e67e  mov     [rsp+68h+var_38], rsi
0x18000e683  xor     r9d, r9d
0x18000e686  mov     [rsp+68h+var_48], rbp
0x18000e68b  mov     edx, 414h
0x18000e690  mov     rcx, [rax+8]
0x18000e694  mov     rax, [rax+0B8h]
0x18000e69b  movdqu  [rsp+68h+var_30], xmm0
0x18000e6a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6a6  test    eax, eax
0x18000e6a8  jz      short loc_18000E6B4
0x18000e6aa  cmp     dword ptr [rsp+68h+var_30+8], ebp
0x18000e6ae  jnz     loc_180029848
0x18000e6b4  mov     rcx, [rbx+4E0h]; void *
0x18000e6bb  test    rcx, rcx
0x18000e6be  jz      short loc_18000E6EA
0x18000e6c0  mov     rax, [rbx+4E8h]
0x18000e6c7  lea     rdx, ?SendResponseCompletion@CResponseBufferSet@@SAXPEAX@Z; CResponseBufferSet::SendResponseCompletion(void *)
0x18000e6ce  cmp     rax, rdx
0x18000e6d1  jnz     loc_180029857
0x18000e6d7  call    ?SendResponseCompletion@CResponseBufferSet@@SAXPEAX@Z; CResponseBufferSet::SendResponseCompletion(void *)
0x18000e6dc  mov     [rbx+4E0h], rbp
0x18000e6e3  mov     [rbx+4E8h], rbp
0x18000e6ea  mov     rcx, [rbx+4D0h]
0x18000e6f1  test    rcx, rcx
0x18000e6f4  jnz     loc_180029862
0x18000e6fa  cmp     [rbx+4F8h], rbp
0x18000e701  jnz     loc_18002987A
0x18000e707  mov     r10, [rbx+8]
0x18000e70b  test    r10, r10
0x18000e70e  jz      short loc_18000E767
0x18000e710  mov     [rsp+68h+arg_10], 1
0x18000e71b  mov     eax, [r10+10h]
0x18000e71f  sub     eax, 1F4h
0x18000e724  cmp     eax, 63h ; 'c'
0x18000e727  jbe     loc_1800298EA
0x18000e72d  cmp     dword ptr [rbx+4C8h], 3
0x18000e734  jnz     short loc_18000E742
0x18000e736  cmp     [rbx+4CCh], ebp
0x18000e73c  jnz     loc_1800298EA
0x18000e742  mov     rcx, [r10+8]
0x18000e746  lea     r8, [rsp+68h+arg_10]
0x18000e74e  mov     rax, [r10+0B8h]
0x18000e755  xor     r9d, r9d
0x18000e758  mov     edx, 4
0x18000e75d  mov     [rsp+68h+var_48], rbp
0x18000e762  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e767  lea     rcx, [rbx+498h]
0x18000e76e  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000e774  lea     rcx, [rbx+468h]
0x18000e77b  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000e781  lea     rcx, [rbx+438h]
0x18000e788  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000e78e  lea     rcx, [rbx+308h]
0x18000e795  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000e79b  lea     rcx, [rbx+1D8h]
0x18000e7a2  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000e7a8  lea     rcx, [rbx+1A8h]
0x18000e7af  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000e7b5  lea     rcx, [rbx+178h]
0x18000e7bc  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000e7c2  lea     rcx, [rbx+48h]
0x18000e7c6  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000e7cc  mov     rcx, cs:?sm_pach@CIsapiReqInfo@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CIsapiReqInfo::sm_pach
0x18000e7d3  test    rcx, rcx
0x18000e7d6  jz      short loc_18000E7E1
0x18000e7d8  mov     rdx, rbx
0x18000e7db  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18000e7e1  mov     rsi, [rsp+68h+arg_0]
0x18000e7e6  lock dec cs:?g_nThreadsExecuting@@3JA; long g_nThreadsExecuting
0x18000e7ed  xor     eax, eax
0x18000e7ef  add     rsp, 50h
0x18000e7f3  pop     rdi
0x18000e7f4  pop     rbp
0x18000e7f5  pop     rbx
0x18000e7f6  retn
0x18002978a  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18002978f  call    cs:__imp_Sleep
0x180029795  nop
0x180029796  jmp     loc_18000E48E
0x18002979b  lea     rcx, stru_18007D2C0; lpCriticalSection
0x1800297a2  call    cs:__imp_LeaveCriticalSection
0x1800297a8  nop
0x1800297a9  jmp     loc_18000E48E
0x1800297ae  mov     ebx, ebp
0x1800297b0  jmp     loc_18000E4F4
0x1800297b5  call    cs:__imp_GetTickCount
0x1800297bb  mov     ecx, eax
0x1800297bd  mov     eax, 10624DD3h
0x1800297c2  mul     ecx
0x1800297c4  shr     edx, 6
0x1800297c7  cmp     edx, cs:dword_18007D328
0x1800297cd  jbe     loc_18000E51F
0x1800297d3  mov     rcx, cs:hEvent; hEvent
0x1800297da  call    cs:__imp_SetEvent
0x1800297e0  nop
0x1800297e1  jmp     loc_18000E51F
0x1800297e6  mov     rax, [rdi]
0x1800297e9  mov     rcx, rdi
0x1800297ec  mov     rax, [rax+10h]
0x1800297f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800297f5  nop
0x1800297f6  jmp     loc_18000E7E6
0x1800297fb  mov     rcx, [rbx+8]; struct _EXTENSION_CONTROL_BLOCK *
0x1800297ff  call    ?RaiseEvent@ASP_DEQUEUE_REQUEST@AspReqEvents@@SAJPEAU_EXTENSION_CONTROL_BLOCK@@PEBU_GUID@@@Z; AspReqEvents::ASP_DEQUEUE_REQUEST::RaiseEvent(_EXTENSION_CONTROL_BLOCK *,_GUID const *)
0x180029804  nop
0x180029805  jmp     loc_18000E589
0x18002980a  mov     edx, 65h ; 'e'; unsigned int
0x18002980f  call    ?ReportServerError@CHitObj@@QEAAJI@Z; CHitObj::ReportServerError(uint)
0x180029814  cmp     [rsp+68h+arg_8], ebp
0x180029818  jnz     loc_18000E5E9
0x18002981e  jmp     loc_18000E5C0
0x180029823  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029828  nop
0x180029829  jmp     loc_18000E5E9
0x18002982e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029833  nop
0x180029834  jmp     loc_18000E60C
0x180029839  mov     rcx, [rbx+8]; struct _EXTENSION_CONTROL_BLOCK *
0x18002983d  call    ?RaiseEvent@ASP_DONE_PROCESSING@AspReqEvents@@SAJPEAU_EXTENSION_CONTROL_BLOCK@@PEBU_GUID@@@Z; AspReqEvents::ASP_DONE_PROCESSING::RaiseEvent(_EXTENSION_CONTROL_BLOCK *,_GUID const *)
0x180029842  nop
0x180029843  jmp     loc_18000E672
0x180029848  mov     rcx, [rbx+8]; struct _EXTENSION_CONTROL_BLOCK *
0x18002984c  call    ?RaiseEvent@ASP_END_REQUEST@AspReqEvents@@SAJPEAU_EXTENSION_CONTROL_BLOCK@@PEBU_GUID@@@Z; AspReqEvents::ASP_END_REQUEST::RaiseEvent(_EXTENSION_CONTROL_BLOCK *,_GUID const *)
0x180029851  nop
0x180029852  jmp     loc_18000E6B4
0x180029857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002985c  nop
0x18002985d  jmp     loc_18000E6DC
0x180029862  mov     rax, [rcx]
0x180029865  mov     rax, [rax+10h]
0x180029869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002986e  mov     [rbx+4D0h], rbp
0x180029875  jmp     loc_18000E6FA
0x18002987a  mov     edi, ebp
0x18002987c  cmp     [rbx+4F4h], ebp
0x180029882  jbe     short loc_1800298C2
0x180029884  mov     eax, edi
0x180029886  lea     rsi, ds:0[rax*8]
0x18002988e  mov     rax, [rbx+4F8h]
0x180029895  mov     r8, [rsi+rax]; lpMem
0x180029899  test    r8, r8
0x18002989c  jz      short loc_1800298B8
0x18002989e  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x1800298a5  xor     edx, edx; dwFlags
0x1800298a7  call    cs:__imp_HeapFree
0x1800298ad  mov     rax, [rbx+4F8h]
0x1800298b4  mov     [rsi+rax], rbp
0x1800298b8  inc     edi
0x1800298ba  cmp     edi, [rbx+4F4h]
0x1800298c0  jb      short loc_180029884
0x1800298c2  mov     r8, [rbx+4F8h]; lpMem
0x1800298c9  xor     edx, edx; dwFlags
0x1800298cb  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x1800298d2  mov     [rbx+4F4h], ebp
0x1800298d8  call    cs:__imp_HeapFree
0x1800298de  mov     [rbx+4F8h], rbp
0x1800298e5  jmp     loc_18000E707
0x1800298ea  mov     [rsp+68h+arg_10], 4
0x1800298f5  jmp     loc_18000E742
```
