# CSession::Release(void)

- ea: `0x18000e1f0`
- end: `0x18000e44d`
- name: `?Release@CSession@@UEAAKXZ`
- size: `605`
- prototype: `unsigned int __fastcall(CSession *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000f4b0`
- `0x18000fce0`

## callees

- `0x18000e1f0`
- `0x18000f9b0`
- `0x18001e730`
- `0x180064010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800296fb`
- `KERNEL32!HeapFree` at `0x180029710`
- `KERNEL32!HeapFree` at `0x180029750`
- `KERNEL32!HeapFree` at `0x180029769`
- `KERNEL32!HeapFree` at `0x1800296fb`
- `KERNEL32!HeapFree` at `0x180029710`
- `KERNEL32!HeapFree` at `0x180029750`
- `KERNEL32!HeapFree` at `0x180029769`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000e439`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000e439`
- `iisutil!WriteRefTraceLog` at `0x18002965c`
- `iisutil!WriteRefTraceLog` at `0x18002965c`

## pseudocode

```c
__int64 __fastcall CSession::Release(CSession *this)
{
  unsigned __int32 v2; // ebx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  unsigned int *v11; // rbx
  void *v12; // r8
  void *v13; // r8
  bool v14; // zf
  __int64 v15; // rcx
  unsigned int v16; // eax
  struct CIdHashArray *v17; // rcx

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 22);
  if ( (g_dwDebugFlags & 0x100000) != 0 && CSession::gm_pTraceLog )
    WriteRefTraceLog(CSession::gm_pTraceLog, *((unsigned int *)this + 22));
  if ( v2 )
    return v2;
  if ( this )
  {
    v4 = *((_QWORD *)this + 126);
    *(_QWORD *)this = &CSession::`vftable';
    if ( v4 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
      *((_QWORD *)this + 126) = 0;
    }
    v5 = *((_QWORD *)this + 120);
    *((_QWORD *)this + 113) = &CServer::`vftable';
    if ( v5 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      *((_QWORD *)this + 120) = 0;
    }
    v6 = *((_QWORD *)this + 116);
    *((_QWORD *)this + 113) = &CDispatch::`vftable';
    if ( v6 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
      *((_QWORD *)this + 116) = 0;
    }
    v7 = *((_QWORD *)this + 112);
    *((_QWORD *)this + 104) = &CResponse::`vftable'{for `CDispatchImpl<IResponse>'};
    *((_QWORD *)this + 108) = &CResponse::`vftable'{for `IStream'};
    if ( v7 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      *((_QWORD *)this + 112) = 0;
    }
    v8 = *((_QWORD *)this + 107);
    *((_QWORD *)this + 104) = &CDispatch::`vftable';
    if ( v8 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      *((_QWORD *)this + 107) = 0;
    }
    v9 = *((_QWORD *)this + 103);
    *((_QWORD *)this + 95) = &CRequest::`vftable'{for `CDispatchImpl<IRequest>'};
    *((_QWORD *)this + 99) = &CRequest::`vftable'{for `IStream'};
    if ( v9 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      *((_QWORD *)this + 103) = 0;
    }
    v10 = *((_QWORD *)this + 98);
    *((_QWORD *)this + 95) = &CDispatch::`vftable';
    if ( v10 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      *((_QWORD *)this + 98) = 0;
    }
    v11 = (unsigned int *)((char *)this + 752);
    *((_QWORD *)this + 92) = &CViperActivity::`vftable';
    if ( *((_QWORD *)this + 93) )
    {
      if ( *v11 > 1 )
      {
        do
        {
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 93) + 48LL))(*((_QWORD *)this + 93));
          v16 = *v11 - 1;
          *v11 = v16;
        }
        while ( v16 > 1 );
      }
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 93) + 16LL))(*((_QWORD *)this + 93));
      *((_QWORD *)this + 93) = 0;
    }
    *v11 = 0;
    CComponentCollection::UnInit((CSession *)((char *)this + 136));
    v12 = (void *)*((_QWORD *)this + 89);
    if ( v12 )
      HeapFree(g_hDenaliHeap, 0, v12);
    *((_DWORD *)this + 176) = 0;
    *((_QWORD *)this + 89) = 0;
    *((_DWORD *)this + 180) = 0;
    v13 = (void *)*((_QWORD *)this + 86);
    if ( v13 )
      HeapFree(g_hDenaliHeap, 0, v13);
    *((_DWORD *)this + 170) = 0;
    *((_QWORD *)this + 86) = 0;
    *((_DWORD *)this + 174) = 0;
    if ( *((_WORD *)this + 328) )
    {
      v17 = (struct CIdHashArray *)*((_QWORD *)this + 83);
      if ( v17 )
        CIdHashArray::Free(v17);
      *((_QWORD *)this + 83) = 0;
      *((_WORD *)this + 328) = 0;
    }
    v14 = (*((_BYTE *)this + 408) & 2) == 0;
    *((_QWORD *)this + 50) = &CHashTable::`vftable';
    if ( !v14 )
      HeapFree(g_hDenaliHeap, 0, *((LPVOID *)this + 54));
    v14 = (*((_BYTE *)this + 152) & 2) == 0;
    *((_QWORD *)this + 18) = &CHashTable::`vftable';
    if ( !v14 )
      HeapFree(g_hDenaliHeap, 0, *((LPVOID *)this + 22));
    v15 = *((_QWORD *)this + 3);
    *(_QWORD *)this = &CDispatch::`vftable';
    if ( v15 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      *((_QWORD *)this + 3) = 0;
    }
    if ( CSession::sm_pach )
      ALLOC_CACHE_HANDLER::Free(CSession::sm_pach, this);
  }
  _InterlockedDecrement(&g_nSessionObjectsActive);
  return 0;
}

```

## disassembly

```asm
0x18000e1f0  mov     [rsp+arg_18], rbx
0x18000e1f5  push    rdi
0x18000e1f6  sub     rsp, 20h
0x18000e1fa  mov     rdi, rcx
0x18000e1fd  mov     ebx, 0FFFFFFFFh
0x18000e202  lock xadd [rcx+58h], ebx
0x18000e207  dec     ebx
0x18000e209  test    cs:g_dwDebugFlags, 100000h
0x18000e213  jnz     loc_180029646
0x18000e219  test    ebx, ebx
0x18000e21b  jz      short loc_18000E22A
0x18000e21d  mov     eax, ebx
0x18000e21f  mov     rbx, [rsp+28h+arg_18]
0x18000e224  add     rsp, 20h
0x18000e228  pop     rdi
0x18000e229  retn
0x18000e22a  test    rdi, rdi
0x18000e22d  jz      loc_18000E43F
0x18000e233  mov     rcx, [rdi+3F0h]
0x18000e23a  lea     rax, ??_7CSession@@6B@; const CSession::`vftable'
0x18000e241  mov     [rsp+28h+arg_0], rbp
0x18000e246  mov     [rsp+28h+arg_8], rsi
0x18000e24b  xor     esi, esi
0x18000e24d  mov     [rsp+28h+arg_10], r14
0x18000e252  mov     [rdi], rax
0x18000e255  test    rcx, rcx
0x18000e258  jz      short loc_18000E26D
0x18000e25a  mov     rax, [rcx]
0x18000e25d  mov     rax, [rax+10h]
0x18000e261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e266  mov     [rdi+3F0h], rsi
0x18000e26d  mov     rcx, [rdi+3C0h]
0x18000e274  lea     rax, ??_7CServer@@6B@; const CServer::`vftable'
0x18000e27b  mov     [rdi+388h], rax
0x18000e282  test    rcx, rcx
0x18000e285  jz      short loc_18000E29A
0x18000e287  mov     rax, [rcx]
0x18000e28a  mov     rax, [rax+10h]
0x18000e28e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e293  mov     [rdi+3C0h], rsi
0x18000e29a  mov     rcx, [rdi+3A0h]
0x18000e2a1  lea     rbp, ??_7CDispatch@@6B@; const CDispatch::`vftable'
0x18000e2a8  mov     [rdi+388h], rbp
0x18000e2af  test    rcx, rcx
0x18000e2b2  jnz     loc_180029668
0x18000e2b8  mov     rcx, [rdi+380h]
0x18000e2bf  lea     rax, ??_7CResponse@@6B?$CDispatchImpl@UIResponse@@@@@; const CResponse::`vftable'{for `CDispatchImpl<IResponse>'}
0x18000e2c6  mov     [rdi+340h], rax
0x18000e2cd  lea     rax, ??_7CResponse@@6BIStream@@@; const CResponse::`vftable'{for `IStream'}
0x18000e2d4  mov     [rdi+360h], rax
0x18000e2db  test    rcx, rcx
0x18000e2de  jz      short loc_18000E2F3
0x18000e2e0  mov     rax, [rcx]
0x18000e2e3  mov     rax, [rax+10h]
0x18000e2e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2ec  mov     [rdi+380h], rsi
0x18000e2f3  mov     rcx, [rdi+358h]
0x18000e2fa  mov     [rdi+340h], rbp
0x18000e301  test    rcx, rcx
0x18000e304  jnz     loc_180029680
0x18000e30a  mov     rcx, [rdi+338h]
0x18000e311  lea     rax, ??_7CRequest@@6B?$CDispatchImpl@UIRequest@@@@@; const CRequest::`vftable'{for `CDispatchImpl<IRequest>'}
0x18000e318  mov     [rdi+2F8h], rax
0x18000e31f  lea     rax, ??_7CRequest@@6BIStream@@@; const CRequest::`vftable'{for `IStream'}
0x18000e326  mov     [rdi+318h], rax
0x18000e32d  test    rcx, rcx
0x18000e330  jz      short loc_18000E345
0x18000e332  mov     rax, [rcx]
0x18000e335  mov     rax, [rax+10h]
0x18000e339  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e33e  mov     [rdi+338h], rsi
0x18000e345  mov     rcx, [rdi+310h]
0x18000e34c  mov     [rdi+2F8h], rbp
0x18000e353  test    rcx, rcx
0x18000e356  jnz     loc_180029698
0x18000e35c  lea     rax, ??_7CViperActivity@@6B@; const CViperActivity::`vftable'
0x18000e363  lea     rbx, [rdi+2F0h]
0x18000e36a  mov     [rdi+2E0h], rax
0x18000e371  cmp     [rdi+2E8h], rsi
0x18000e378  jnz     loc_1800296B0
0x18000e37e  mov     [rbx], esi
0x18000e380  lea     rbx, [rdi+88h]
0x18000e387  mov     rcx, rbx; this
0x18000e38a  call    ?UnInit@CComponentCollection@@QEAAJXZ; CComponentCollection::UnInit(void)
0x18000e38f  mov     r8, [rbx+240h]; lpMem
0x18000e396  test    r8, r8
0x18000e399  jnz     loc_1800296F2
0x18000e39f  mov     [rbx+238h], esi
0x18000e3a5  mov     [rbx+240h], rsi
0x18000e3ac  mov     [rbx+248h], esi
0x18000e3b2  mov     r8, [rbx+228h]; lpMem
0x18000e3b9  test    r8, r8
0x18000e3bc  jnz     loc_180029707
0x18000e3c2  mov     [rbx+220h], esi
0x18000e3c8  mov     [rbx+228h], rsi
0x18000e3cf  mov     [rbx+230h], esi
0x18000e3d5  cmp     [rbx+208h], si
0x18000e3dc  jnz     loc_18002971C
0x18000e3e2  test    byte ptr [rbx+110h], 2
0x18000e3e9  lea     r14, ??_7CHashTable@@6B@; const CHashTable::`vftable'
0x18000e3f0  mov     [rbx+108h], r14
0x18000e3f7  jnz     loc_180029740
0x18000e3fd  test    byte ptr [rbx+10h], 2
0x18000e401  mov     [rbx+8], r14
0x18000e405  mov     r14, [rsp+28h+arg_10]
0x18000e40a  jnz     loc_18002975C
0x18000e410  mov     rcx, [rdi+18h]
0x18000e414  mov     [rdi], rbp
0x18000e417  mov     rbp, [rsp+28h+arg_0]
0x18000e41c  test    rcx, rcx
0x18000e41f  jnz     loc_180029775
0x18000e425  mov     rcx, cs:?sm_pach@CSession@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CSession::sm_pach
0x18000e42c  mov     rsi, [rsp+28h+arg_8]
0x18000e431  test    rcx, rcx
0x18000e434  jz      short loc_18000E43F
0x18000e436  mov     rdx, rdi
0x18000e439  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18000e43f  lock dec cs:?g_nSessionObjectsActive@@3JA; long g_nSessionObjectsActive
0x18000e446  xor     eax, eax
0x18000e448  jmp     loc_18000E21F
0x180029646  mov     rcx, cs:?gm_pTraceLog@CSession@@2PEAU_TRACE_LOG@@EA; _TRACE_LOG * CSession::gm_pTraceLog
0x18002964d  test    rcx, rcx
0x180029650  jz      loc_18000E219
0x180029656  mov     edx, [rdi+58h]
0x180029659  mov     r8, rdi
0x18002965c  call    cs:__imp_WriteRefTraceLog
0x180029662  nop
0x180029663  jmp     loc_18000E219
0x180029668  mov     rax, [rcx]
0x18002966b  mov     rax, [rax+10h]
0x18002966f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029674  mov     [rdi+3A0h], rsi
0x18002967b  jmp     loc_18000E2B8
0x180029680  mov     rax, [rcx]
0x180029683  mov     rax, [rax+10h]
0x180029687  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002968c  mov     [rdi+358h], rsi
0x180029693  jmp     loc_18000E30A
0x180029698  mov     rax, [rcx]
0x18002969b  mov     rax, [rax+10h]
0x18002969f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800296a4  mov     [rdi+310h], rsi
0x1800296ab  jmp     loc_18000E35C
0x1800296b0  cmp     dword ptr [rbx], 1
0x1800296b3  jbe     short loc_1800296D3
0x1800296b5  mov     rcx, [rdi+2E8h]
0x1800296bc  mov     rax, [rcx]
0x1800296bf  mov     rax, [rax+30h]
0x1800296c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800296c8  mov     eax, [rbx]
0x1800296ca  dec     eax
0x1800296cc  mov     [rbx], eax
0x1800296ce  cmp     eax, 1
0x1800296d1  ja      short loc_1800296B5
0x1800296d3  mov     rcx, [rdi+2E8h]
0x1800296da  mov     rax, [rcx]
0x1800296dd  mov     rax, [rax+10h]
0x1800296e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800296e6  mov     [rdi+2E8h], rsi
0x1800296ed  jmp     loc_18000E37E
0x1800296f2  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x1800296f9  xor     edx, edx; dwFlags
0x1800296fb  call    cs:__imp_HeapFree
0x180029701  nop
0x180029702  jmp     loc_18000E39F
0x180029707  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x18002970e  xor     edx, edx; dwFlags
0x180029710  call    cs:__imp_HeapFree
0x180029716  nop
0x180029717  jmp     loc_18000E3C2
0x18002971c  mov     rcx, [rbx+210h]; struct CIdHashArray *
0x180029723  test    rcx, rcx
0x180029726  jz      short loc_18002972D
0x180029728  call    ?Free@CIdHashArray@@SAXPEAU1@@Z; CIdHashArray::Free(CIdHashArray *)
0x18002972d  mov     [rbx+210h], rsi
0x180029734  mov     [rbx+208h], si
0x18002973b  jmp     loc_18000E3E2
0x180029740  mov     r8, [rbx+128h]; lpMem
0x180029747  xor     edx, edx; dwFlags
0x180029749  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180029750  call    cs:__imp_HeapFree
0x180029756  nop
0x180029757  jmp     loc_18000E3FD
0x18002975c  mov     r8, [rbx+28h]; lpMem
0x180029760  xor     edx, edx; dwFlags
0x180029762  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180029769  call    cs:__imp_HeapFree
0x18002976f  nop
0x180029770  jmp     loc_18000E410
0x180029775  mov     rax, [rcx]
0x180029778  mov     rax, [rax+10h]
0x18002977c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029781  mov     [rdi+18h], rsi
0x180029785  jmp     loc_18000E425
```
