# CRequest::Release(void)

- ea: `0x18000e860`
- end: `0x18000eade`
- name: `?Release@CRequest@@UEAAKXZ`
- size: `638`
- prototype: `unsigned int __fastcall(CRequest *__hidden this)`
- caller_count: `10`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000a6d0`
- `0x18000f1d0`
- `0x18000f260`
- `0x18000f2d0`
- `0x18000f350`
- `0x18000f3d0`
- `0x18000f440`
- `0x18000f4b0`
- `0x18000f7e0`
- `0x180023f50`

## callees

- `0x18000e860`
- `0x18000f9b0`
- `0x18001e730`
- `0x18004a518`
- `0x180064010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180029a05`
- `KERNEL32!HeapFree` at `0x180029a1a`
- `KERNEL32!HeapFree` at `0x180029a5a`
- `KERNEL32!HeapFree` at `0x180029a73`
- `KERNEL32!HeapFree` at `0x180029a05`
- `KERNEL32!HeapFree` at `0x180029a1a`
- `KERNEL32!HeapFree` at `0x180029a5a`
- `KERNEL32!HeapFree` at `0x180029a73`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000eabd`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180029aca`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000eabd`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180029aca`
- `iisutil!WriteRefTraceLog` at `0x18002995a`
- `iisutil!WriteRefTraceLog` at `0x18002995a`

## pseudocode

```c
__int64 __fastcall CRequest::Release(CRequest *this)
{
  volatile signed __int32 *v2; // rdi
  unsigned int (__fastcall *v3)(CSession *__hidden); // rax
  unsigned __int32 v4; // ebx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  void *v13; // r8
  void *v14; // r8
  bool v15; // zf
  __int64 v16; // rcx
  unsigned int v17; // eax
  struct CIdHashArray *v18; // rcx

  if ( (*((_BYTE *)this + 40) & 4) == 0 )
  {
    v4 = _InterlockedDecrement((volatile signed __int32 *)this + 12);
    if ( !v4 )
    {
      CRequest::~CRequest(this);
      if ( CRequest::sm_pach )
        ALLOC_CACHE_HANDLER::Free(CRequest::sm_pach, this);
      return 0;
    }
    return v4;
  }
  v2 = (volatile signed __int32 *)*((_QWORD *)this + 6);
  v3 = *(unsigned int (__fastcall **)(CSession *__hidden))(*(_QWORD *)v2 + 16LL);
  if ( v3 != CSession::Release )
    return v3((CSession *)v2);
  v4 = _InterlockedDecrement(v2 + 22);
  if ( (g_dwDebugFlags & 0x100000) != 0 && CSession::gm_pTraceLog )
    WriteRefTraceLog(CSession::gm_pTraceLog, *((unsigned int *)v2 + 22));
  if ( v4 )
    return v4;
  v6 = *((_QWORD *)v2 + 126);
  *(_QWORD *)v2 = &CSession::`vftable';
  if ( v6 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    *((_QWORD *)v2 + 126) = 0;
  }
  v7 = *((_QWORD *)v2 + 120);
  *((_QWORD *)v2 + 113) = &CServer::`vftable';
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    *((_QWORD *)v2 + 120) = 0;
  }
  v8 = *((_QWORD *)v2 + 116);
  *((_QWORD *)v2 + 113) = &CDispatch::`vftable';
  if ( v8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    *((_QWORD *)v2 + 116) = 0;
  }
  v9 = *((_QWORD *)v2 + 112);
  *((_QWORD *)v2 + 104) = &CResponse::`vftable'{for `CDispatchImpl<IResponse>'};
  *((_QWORD *)v2 + 108) = &CResponse::`vftable'{for `IStream'};
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    *((_QWORD *)v2 + 112) = 0;
  }
  v10 = *((_QWORD *)v2 + 107);
  *((_QWORD *)v2 + 104) = &CDispatch::`vftable';
  if ( v10 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    *((_QWORD *)v2 + 107) = 0;
  }
  v11 = *((_QWORD *)v2 + 103);
  *((_QWORD *)v2 + 95) = &CRequest::`vftable'{for `CDispatchImpl<IRequest>'};
  *((_QWORD *)v2 + 99) = &CRequest::`vftable'{for `IStream'};
  if ( v11 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    *((_QWORD *)v2 + 103) = 0;
  }
  v12 = *((_QWORD *)v2 + 98);
  *((_QWORD *)v2 + 95) = &CDispatch::`vftable';
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    *((_QWORD *)v2 + 98) = 0;
  }
  *((_QWORD *)v2 + 92) = &CViperActivity::`vftable';
  if ( *((_QWORD *)v2 + 93) )
  {
    if ( *((_DWORD *)v2 + 188) > 1u )
    {
      do
      {
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v2 + 93) + 48LL))(*((_QWORD *)v2 + 93));
        v17 = *((_DWORD *)v2 + 188) - 1;
        *((_DWORD *)v2 + 188) = v17;
      }
      while ( v17 > 1 );
    }
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v2 + 93) + 16LL))(*((_QWORD *)v2 + 93));
    *((_QWORD *)v2 + 93) = 0;
  }
  *((_DWORD *)v2 + 188) = 0;
  CComponentCollection::UnInit((CComponentCollection *)(v2 + 34));
  v13 = (void *)*((_QWORD *)v2 + 89);
  if ( v13 )
    HeapFree(g_hDenaliHeap, 0, v13);
  *((_DWORD *)v2 + 176) = 0;
  *((_QWORD *)v2 + 89) = 0;
  *((_DWORD *)v2 + 180) = 0;
  v14 = (void *)*((_QWORD *)v2 + 86);
  if ( v14 )
    HeapFree(g_hDenaliHeap, 0, v14);
  *((_DWORD *)v2 + 170) = 0;
  *((_QWORD *)v2 + 86) = 0;
  *((_DWORD *)v2 + 174) = 0;
  if ( *((_WORD *)v2 + 328) )
  {
    v18 = (struct CIdHashArray *)*((_QWORD *)v2 + 83);
    if ( v18 )
      CIdHashArray::Free(v18);
    *((_QWORD *)v2 + 83) = 0;
    *((_WORD *)v2 + 328) = 0;
  }
  v15 = (v2[102] & 2) == 0;
  *((_QWORD *)v2 + 50) = &CHashTable::`vftable';
  if ( !v15 )
    HeapFree(g_hDenaliHeap, 0, *((LPVOID *)v2 + 54));
  v15 = (v2[38] & 2) == 0;
  *((_QWORD *)v2 + 18) = &CHashTable::`vftable';
  if ( !v15 )
    HeapFree(g_hDenaliHeap, 0, *((LPVOID *)v2 + 22));
  v16 = *((_QWORD *)v2 + 3);
  *(_QWORD *)v2 = &CDispatch::`vftable';
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    *((_QWORD *)v2 + 3) = 0;
  }
  if ( CSession::sm_pach )
    ALLOC_CACHE_HANDLER::Free(CSession::sm_pach, (void *)v2);
  _InterlockedDecrement(&g_nSessionObjectsActive);
  return 0;
}

```

## disassembly

```asm
0x18000e860  mov     [rsp+arg_18], rbx
0x18000e865  push    rdi
0x18000e866  sub     rsp, 20h
0x18000e86a  test    byte ptr [rcx+28h], 4
0x18000e86e  mov     rdi, rcx
0x18000e871  jz      loc_180029AA3
0x18000e877  mov     rdi, [rcx+30h]
0x18000e87b  lea     rcx, ?Release@CSession@@UEAAKXZ; CSession::Release(void)
0x18000e882  mov     rax, [rdi]
0x18000e885  mov     rax, [rax+10h]
0x18000e889  cmp     rax, rcx
0x18000e88c  jnz     loc_180029A94
0x18000e892  mov     ebx, 0FFFFFFFFh
0x18000e897  lock xadd [rdi+58h], ebx
0x18000e89c  dec     ebx
0x18000e89e  test    cs:g_dwDebugFlags, 100000h
0x18000e8a8  jnz     loc_180029944
0x18000e8ae  test    ebx, ebx
0x18000e8b0  jz      short loc_18000E8BF
0x18000e8b2  mov     eax, ebx
0x18000e8b4  mov     rbx, [rsp+28h+arg_18]
0x18000e8b9  add     rsp, 20h
0x18000e8bd  pop     rdi
0x18000e8be  retn
0x18000e8bf  mov     rcx, [rdi+3F0h]
0x18000e8c6  lea     rax, ??_7CSession@@6B@; const CSession::`vftable'
0x18000e8cd  mov     [rsp+28h+arg_0], rbp
0x18000e8d2  mov     [rsp+28h+arg_8], rsi
0x18000e8d7  xor     esi, esi
0x18000e8d9  mov     [rsp+28h+arg_10], r14
0x18000e8de  mov     [rdi], rax
0x18000e8e1  test    rcx, rcx
0x18000e8e4  jz      short loc_18000E8F9
0x18000e8e6  mov     rax, [rcx]
0x18000e8e9  mov     rax, [rax+10h]
0x18000e8ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8f2  mov     [rdi+3F0h], rsi
0x18000e8f9  mov     rcx, [rdi+3C0h]
0x18000e900  lea     rax, ??_7CServer@@6B@; const CServer::`vftable'
0x18000e907  mov     [rdi+388h], rax
0x18000e90e  test    rcx, rcx
0x18000e911  jz      short loc_18000E926
0x18000e913  mov     rax, [rcx]
0x18000e916  mov     rax, [rax+10h]
0x18000e91a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e91f  mov     [rdi+3C0h], rsi
0x18000e926  mov     rcx, [rdi+3A0h]
0x18000e92d  lea     rbp, ??_7CDispatch@@6B@; const CDispatch::`vftable'
0x18000e934  mov     [rdi+388h], rbp
0x18000e93b  test    rcx, rcx
0x18000e93e  jnz     loc_180029966
0x18000e944  mov     rcx, [rdi+380h]
0x18000e94b  lea     rax, ??_7CResponse@@6B?$CDispatchImpl@UIResponse@@@@@; const CResponse::`vftable'{for `CDispatchImpl<IResponse>'}
0x18000e952  mov     [rdi+340h], rax
0x18000e959  lea     rax, ??_7CResponse@@6BIStream@@@; const CResponse::`vftable'{for `IStream'}
0x18000e960  mov     [rdi+360h], rax
0x18000e967  test    rcx, rcx
0x18000e96a  jz      short loc_18000E97F
0x18000e96c  mov     rax, [rcx]
0x18000e96f  mov     rax, [rax+10h]
0x18000e973  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e978  mov     [rdi+380h], rsi
0x18000e97f  mov     rcx, [rdi+358h]
0x18000e986  mov     [rdi+340h], rbp
0x18000e98d  test    rcx, rcx
0x18000e990  jnz     loc_18002997E
0x18000e996  mov     rcx, [rdi+338h]
0x18000e99d  lea     rax, ??_7CRequest@@6B?$CDispatchImpl@UIRequest@@@@@; const CRequest::`vftable'{for `CDispatchImpl<IRequest>'}
0x18000e9a4  mov     [rdi+2F8h], rax
0x18000e9ab  lea     rax, ??_7CRequest@@6BIStream@@@; const CRequest::`vftable'{for `IStream'}
0x18000e9b2  mov     [rdi+318h], rax
0x18000e9b9  test    rcx, rcx
0x18000e9bc  jz      short loc_18000E9D1
0x18000e9be  mov     rax, [rcx]
0x18000e9c1  mov     rax, [rax+10h]
0x18000e9c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9ca  mov     [rdi+338h], rsi
0x18000e9d1  mov     rcx, [rdi+310h]
0x18000e9d8  mov     [rdi+2F8h], rbp
0x18000e9df  test    rcx, rcx
0x18000e9e2  jnz     loc_180029996
0x18000e9e8  lea     rax, ??_7CViperActivity@@6B@; const CViperActivity::`vftable'
0x18000e9ef  mov     [rdi+2E0h], rax
0x18000e9f6  cmp     [rdi+2E8h], rsi
0x18000e9fd  jnz     loc_1800299AE
0x18000ea03  lea     rbx, [rdi+88h]
0x18000ea0a  mov     [rdi+2F0h], esi
0x18000ea10  mov     rcx, rbx; this
0x18000ea13  call    ?UnInit@CComponentCollection@@QEAAJXZ; CComponentCollection::UnInit(void)
0x18000ea18  mov     r8, [rbx+240h]; lpMem
0x18000ea1f  test    r8, r8
0x18000ea22  jnz     loc_1800299FC
0x18000ea28  mov     [rbx+238h], esi
0x18000ea2e  mov     [rbx+240h], rsi
0x18000ea35  mov     [rbx+248h], esi
0x18000ea3b  mov     r8, [rbx+228h]; lpMem
0x18000ea42  test    r8, r8
0x18000ea45  jnz     loc_180029A11
0x18000ea4b  mov     [rbx+220h], esi
0x18000ea51  mov     [rbx+228h], rsi
0x18000ea58  mov     [rbx+230h], esi
0x18000ea5e  cmp     [rbx+208h], si
0x18000ea65  jnz     loc_180029A26
0x18000ea6b  test    byte ptr [rbx+110h], 2
0x18000ea72  lea     r14, ??_7CHashTable@@6B@; const CHashTable::`vftable'
0x18000ea79  mov     [rbx+108h], r14
0x18000ea80  jnz     loc_180029A4A
0x18000ea86  test    byte ptr [rbx+10h], 2
0x18000ea8a  mov     [rbx+8], r14
0x18000ea8e  mov     r14, [rsp+28h+arg_10]
0x18000ea93  jnz     loc_180029A66
0x18000ea99  mov     rcx, [rdi+18h]
0x18000ea9d  mov     [rdi], rbp
0x18000eaa0  mov     rbp, [rsp+28h+arg_0]
0x18000eaa5  test    rcx, rcx
0x18000eaa8  jnz     loc_180029A7F
0x18000eaae  mov     rcx, cs:?sm_pach@CSession@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CSession::sm_pach
0x18000eab5  test    rcx, rcx
0x18000eab8  jz      short loc_18000EAC3
0x18000eaba  mov     rdx, rdi
0x18000eabd  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18000eac3  lock dec cs:?g_nSessionObjectsActive@@3JA; long g_nSessionObjectsActive
0x18000eaca  mov     ebx, esi
0x18000eacc  mov     rsi, [rsp+28h+arg_8]
0x18000ead1  mov     eax, ebx
0x18000ead3  mov     rbx, [rsp+28h+arg_18]
0x18000ead8  add     rsp, 20h
0x18000eadc  pop     rdi
0x18000eadd  retn
0x180029944  mov     rcx, cs:?gm_pTraceLog@CSession@@2PEAU_TRACE_LOG@@EA; _TRACE_LOG * CSession::gm_pTraceLog
0x18002994b  test    rcx, rcx
0x18002994e  jz      loc_18000E8AE
0x180029954  mov     edx, [rdi+58h]
0x180029957  mov     r8, rdi
0x18002995a  call    cs:__imp_WriteRefTraceLog
0x180029960  nop
0x180029961  jmp     loc_18000E8AE
0x180029966  mov     rax, [rcx]
0x180029969  mov     rax, [rax+10h]
0x18002996d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029972  mov     [rdi+3A0h], rsi
0x180029979  jmp     loc_18000E944
0x18002997e  mov     rax, [rcx]
0x180029981  mov     rax, [rax+10h]
0x180029985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002998a  mov     [rdi+358h], rsi
0x180029991  jmp     loc_18000E996
0x180029996  mov     rax, [rcx]
0x180029999  mov     rax, [rax+10h]
0x18002999d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800299a2  mov     [rdi+310h], rsi
0x1800299a9  jmp     loc_18000E9E8
0x1800299ae  cmp     dword ptr [rdi+2F0h], 1
0x1800299b5  jbe     short loc_1800299DD
0x1800299b7  mov     rcx, [rdi+2E8h]
0x1800299be  mov     rax, [rcx]
0x1800299c1  mov     rax, [rax+30h]
0x1800299c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800299ca  mov     eax, [rdi+2F0h]
0x1800299d0  dec     eax
0x1800299d2  mov     [rdi+2F0h], eax
0x1800299d8  cmp     eax, 1
0x1800299db  ja      short loc_1800299B7
0x1800299dd  mov     rcx, [rdi+2E8h]
0x1800299e4  mov     rax, [rcx]
0x1800299e7  mov     rax, [rax+10h]
0x1800299eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800299f0  mov     [rdi+2E8h], rsi
0x1800299f7  jmp     loc_18000EA03
0x1800299fc  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180029a03  xor     edx, edx; dwFlags
0x180029a05  call    cs:__imp_HeapFree
0x180029a0b  nop
0x180029a0c  jmp     loc_18000EA28
0x180029a11  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180029a18  xor     edx, edx; dwFlags
0x180029a1a  call    cs:__imp_HeapFree
0x180029a20  nop
0x180029a21  jmp     loc_18000EA4B
0x180029a26  mov     rcx, [rbx+210h]; struct CIdHashArray *
0x180029a2d  test    rcx, rcx
0x180029a30  jz      short loc_180029A37
0x180029a32  call    ?Free@CIdHashArray@@SAXPEAU1@@Z; CIdHashArray::Free(CIdHashArray *)
0x180029a37  mov     [rbx+210h], rsi
0x180029a3e  mov     [rbx+208h], si
0x180029a45  jmp     loc_18000EA6B
0x180029a4a  mov     r8, [rbx+128h]; lpMem
0x180029a51  xor     edx, edx; dwFlags
0x180029a53  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180029a5a  call    cs:__imp_HeapFree
0x180029a60  nop
0x180029a61  jmp     loc_18000EA86
0x180029a66  mov     r8, [rbx+28h]; lpMem
0x180029a6a  xor     edx, edx; dwFlags
0x180029a6c  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180029a73  call    cs:__imp_HeapFree
0x180029a79  nop
0x180029a7a  jmp     loc_18000EA99
0x180029a7f  mov     rax, [rcx]
0x180029a82  mov     rax, [rax+10h]
0x180029a86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a8b  mov     [rdi+18h], rsi
0x180029a8f  jmp     loc_18000EAAE
0x180029a94  mov     rcx, rdi
0x180029a97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a9c  mov     ebx, eax
0x180029a9e  jmp     loc_18000E8B2
0x180029aa3  mov     ebx, 0FFFFFFFFh
0x180029aa8  lock xadd [rcx+30h], ebx
0x180029aad  sub     ebx, 1
0x180029ab0  jnz     loc_18000E8B2
0x180029ab6  call    ??1CRequest@@QEAA@XZ; CRequest::~CRequest(void)
0x180029abb  mov     rcx, cs:?sm_pach@CRequest@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CRequest::sm_pach
0x180029ac2  test    rcx, rcx
0x180029ac5  jz      short loc_180029AD0
0x180029ac7  mov     rdx, rdi
0x180029aca  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x180029ad0  xor     eax, eax
0x180029ad2  jmp     loc_18000E8B4
```
