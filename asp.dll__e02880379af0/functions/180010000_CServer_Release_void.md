# CServer::Release(void)

- ea: `0x180010000`
- end: `0x18001027e`
- name: `?Release@CServer@@UEAAKXZ`
- size: `638`
- prototype: `unsigned int __fastcall(CServer *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000f4b0`
- `0x18000f7e0`

## callees

- `0x18000f9b0`
- `0x180010000`
- `0x18001e730`
- `0x1800572b4`
- `0x180064010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18002a793`
- `KERNEL32!HeapFree` at `0x18002a7a8`
- `KERNEL32!HeapFree` at `0x18002a7e8`
- `KERNEL32!HeapFree` at `0x18002a801`
- `KERNEL32!HeapFree` at `0x18002a793`
- `KERNEL32!HeapFree` at `0x18002a7a8`
- `KERNEL32!HeapFree` at `0x18002a7e8`
- `KERNEL32!HeapFree` at `0x18002a801`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18001025d`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18002a858`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18001025d`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18002a858`
- `iisutil!WriteRefTraceLog` at `0x18002a6e8`
- `iisutil!WriteRefTraceLog` at `0x18002a6e8`

## pseudocode

```c
__int64 __fastcall CServer::Release(CServer *this)
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

  if ( (*((_BYTE *)this + 32) & 4) == 0 )
  {
    v4 = _InterlockedDecrement((volatile signed __int32 *)this + 10);
    if ( !v4 )
    {
      CServer::~CServer(this);
      if ( CServer::sm_pach )
        ALLOC_CACHE_HANDLER::Free(CServer::sm_pach, this);
      return 0;
    }
    return v4;
  }
  v2 = (volatile signed __int32 *)*((_QWORD *)this + 5);
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
0x180010000  mov     [rsp+arg_18], rbx
0x180010005  push    rdi
0x180010006  sub     rsp, 20h
0x18001000a  test    byte ptr [rcx+20h], 4
0x18001000e  mov     rdi, rcx
0x180010011  jz      loc_18002A831
0x180010017  mov     rdi, [rcx+28h]
0x18001001b  lea     rcx, ?Release@CSession@@UEAAKXZ; CSession::Release(void)
0x180010022  mov     rax, [rdi]
0x180010025  mov     rax, [rax+10h]
0x180010029  cmp     rax, rcx
0x18001002c  jnz     loc_18002A822
0x180010032  mov     ebx, 0FFFFFFFFh
0x180010037  lock xadd [rdi+58h], ebx
0x18001003c  dec     ebx
0x18001003e  test    cs:g_dwDebugFlags, 100000h
0x180010048  jnz     loc_18002A6D2
0x18001004e  test    ebx, ebx
0x180010050  jz      short loc_18001005F
0x180010052  mov     eax, ebx
0x180010054  mov     rbx, [rsp+28h+arg_18]
0x180010059  add     rsp, 20h
0x18001005d  pop     rdi
0x18001005e  retn
0x18001005f  mov     rcx, [rdi+3F0h]
0x180010066  lea     rax, ??_7CSession@@6B@; const CSession::`vftable'
0x18001006d  mov     [rsp+28h+arg_0], rbp
0x180010072  mov     [rsp+28h+arg_8], rsi
0x180010077  xor     esi, esi
0x180010079  mov     [rsp+28h+arg_10], r14
0x18001007e  mov     [rdi], rax
0x180010081  test    rcx, rcx
0x180010084  jz      short loc_180010099
0x180010086  mov     rax, [rcx]
0x180010089  mov     rax, [rax+10h]
0x18001008d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010092  mov     [rdi+3F0h], rsi
0x180010099  mov     rcx, [rdi+3C0h]
0x1800100a0  lea     rax, ??_7CServer@@6B@; const CServer::`vftable'
0x1800100a7  mov     [rdi+388h], rax
0x1800100ae  test    rcx, rcx
0x1800100b1  jz      short loc_1800100C6
0x1800100b3  mov     rax, [rcx]
0x1800100b6  mov     rax, [rax+10h]
0x1800100ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100bf  mov     [rdi+3C0h], rsi
0x1800100c6  mov     rcx, [rdi+3A0h]
0x1800100cd  lea     rbp, ??_7CDispatch@@6B@; const CDispatch::`vftable'
0x1800100d4  mov     [rdi+388h], rbp
0x1800100db  test    rcx, rcx
0x1800100de  jnz     loc_18002A6F4
0x1800100e4  mov     rcx, [rdi+380h]
0x1800100eb  lea     rax, ??_7CResponse@@6B?$CDispatchImpl@UIResponse@@@@@; const CResponse::`vftable'{for `CDispatchImpl<IResponse>'}
0x1800100f2  mov     [rdi+340h], rax
0x1800100f9  lea     rax, ??_7CResponse@@6BIStream@@@; const CResponse::`vftable'{for `IStream'}
0x180010100  mov     [rdi+360h], rax
0x180010107  test    rcx, rcx
0x18001010a  jz      short loc_18001011F
0x18001010c  mov     rax, [rcx]
0x18001010f  mov     rax, [rax+10h]
0x180010113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010118  mov     [rdi+380h], rsi
0x18001011f  mov     rcx, [rdi+358h]
0x180010126  mov     [rdi+340h], rbp
0x18001012d  test    rcx, rcx
0x180010130  jnz     loc_18002A70C
0x180010136  mov     rcx, [rdi+338h]
0x18001013d  lea     rax, ??_7CRequest@@6B?$CDispatchImpl@UIRequest@@@@@; const CRequest::`vftable'{for `CDispatchImpl<IRequest>'}
0x180010144  mov     [rdi+2F8h], rax
0x18001014b  lea     rax, ??_7CRequest@@6BIStream@@@; const CRequest::`vftable'{for `IStream'}
0x180010152  mov     [rdi+318h], rax
0x180010159  test    rcx, rcx
0x18001015c  jz      short loc_180010171
0x18001015e  mov     rax, [rcx]
0x180010161  mov     rax, [rax+10h]
0x180010165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001016a  mov     [rdi+338h], rsi
0x180010171  mov     rcx, [rdi+310h]
0x180010178  mov     [rdi+2F8h], rbp
0x18001017f  test    rcx, rcx
0x180010182  jnz     loc_18002A724
0x180010188  lea     rax, ??_7CViperActivity@@6B@; const CViperActivity::`vftable'
0x18001018f  mov     [rdi+2E0h], rax
0x180010196  cmp     [rdi+2E8h], rsi
0x18001019d  jnz     loc_18002A73C
0x1800101a3  lea     rbx, [rdi+88h]
0x1800101aa  mov     [rdi+2F0h], esi
0x1800101b0  mov     rcx, rbx; this
0x1800101b3  call    ?UnInit@CComponentCollection@@QEAAJXZ; CComponentCollection::UnInit(void)
0x1800101b8  mov     r8, [rbx+240h]; lpMem
0x1800101bf  test    r8, r8
0x1800101c2  jnz     loc_18002A78A
0x1800101c8  mov     [rbx+238h], esi
0x1800101ce  mov     [rbx+240h], rsi
0x1800101d5  mov     [rbx+248h], esi
0x1800101db  mov     r8, [rbx+228h]; lpMem
0x1800101e2  test    r8, r8
0x1800101e5  jnz     loc_18002A79F
0x1800101eb  mov     [rbx+220h], esi
0x1800101f1  mov     [rbx+228h], rsi
0x1800101f8  mov     [rbx+230h], esi
0x1800101fe  cmp     [rbx+208h], si
0x180010205  jnz     loc_18002A7B4
0x18001020b  test    byte ptr [rbx+110h], 2
0x180010212  lea     r14, ??_7CHashTable@@6B@; const CHashTable::`vftable'
0x180010219  mov     [rbx+108h], r14
0x180010220  jnz     loc_18002A7D8
0x180010226  test    byte ptr [rbx+10h], 2
0x18001022a  mov     [rbx+8], r14
0x18001022e  mov     r14, [rsp+28h+arg_10]
0x180010233  jnz     loc_18002A7F4
0x180010239  mov     rcx, [rdi+18h]
0x18001023d  mov     [rdi], rbp
0x180010240  mov     rbp, [rsp+28h+arg_0]
0x180010245  test    rcx, rcx
0x180010248  jnz     loc_18002A80D
0x18001024e  mov     rcx, cs:?sm_pach@CSession@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CSession::sm_pach
0x180010255  test    rcx, rcx
0x180010258  jz      short loc_180010263
0x18001025a  mov     rdx, rdi
0x18001025d  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x180010263  lock dec cs:?g_nSessionObjectsActive@@3JA; long g_nSessionObjectsActive
0x18001026a  mov     ebx, esi
0x18001026c  mov     rsi, [rsp+28h+arg_8]
0x180010271  mov     eax, ebx
0x180010273  mov     rbx, [rsp+28h+arg_18]
0x180010278  add     rsp, 20h
0x18001027c  pop     rdi
0x18001027d  retn
0x18002a6d2  mov     rcx, cs:?gm_pTraceLog@CSession@@2PEAU_TRACE_LOG@@EA; _TRACE_LOG * CSession::gm_pTraceLog
0x18002a6d9  test    rcx, rcx
0x18002a6dc  jz      loc_18001004E
0x18002a6e2  mov     edx, [rdi+58h]
0x18002a6e5  mov     r8, rdi
0x18002a6e8  call    cs:__imp_WriteRefTraceLog
0x18002a6ee  nop
0x18002a6ef  jmp     loc_18001004E
0x18002a6f4  mov     rax, [rcx]
0x18002a6f7  mov     rax, [rax+10h]
0x18002a6fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a700  mov     [rdi+3A0h], rsi
0x18002a707  jmp     loc_1800100E4
0x18002a70c  mov     rax, [rcx]
0x18002a70f  mov     rax, [rax+10h]
0x18002a713  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a718  mov     [rdi+358h], rsi
0x18002a71f  jmp     loc_180010136
0x18002a724  mov     rax, [rcx]
0x18002a727  mov     rax, [rax+10h]
0x18002a72b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a730  mov     [rdi+310h], rsi
0x18002a737  jmp     loc_180010188
0x18002a73c  cmp     dword ptr [rdi+2F0h], 1
0x18002a743  jbe     short loc_18002A76B
0x18002a745  mov     rcx, [rdi+2E8h]
0x18002a74c  mov     rax, [rcx]
0x18002a74f  mov     rax, [rax+30h]
0x18002a753  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a758  mov     eax, [rdi+2F0h]
0x18002a75e  dec     eax
0x18002a760  mov     [rdi+2F0h], eax
0x18002a766  cmp     eax, 1
0x18002a769  ja      short loc_18002A745
0x18002a76b  mov     rcx, [rdi+2E8h]
0x18002a772  mov     rax, [rcx]
0x18002a775  mov     rax, [rax+10h]
0x18002a779  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a77e  mov     [rdi+2E8h], rsi
0x18002a785  jmp     loc_1800101A3
0x18002a78a  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x18002a791  xor     edx, edx; dwFlags
0x18002a793  call    cs:__imp_HeapFree
0x18002a799  nop
0x18002a79a  jmp     loc_1800101C8
0x18002a79f  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x18002a7a6  xor     edx, edx; dwFlags
0x18002a7a8  call    cs:__imp_HeapFree
0x18002a7ae  nop
0x18002a7af  jmp     loc_1800101EB
0x18002a7b4  mov     rcx, [rbx+210h]; struct CIdHashArray *
0x18002a7bb  test    rcx, rcx
0x18002a7be  jz      short loc_18002A7C5
0x18002a7c0  call    ?Free@CIdHashArray@@SAXPEAU1@@Z; CIdHashArray::Free(CIdHashArray *)
0x18002a7c5  mov     [rbx+210h], rsi
0x18002a7cc  mov     [rbx+208h], si
0x18002a7d3  jmp     loc_18001020B
0x18002a7d8  mov     r8, [rbx+128h]; lpMem
0x18002a7df  xor     edx, edx; dwFlags
0x18002a7e1  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x18002a7e8  call    cs:__imp_HeapFree
0x18002a7ee  nop
0x18002a7ef  jmp     loc_180010226
0x18002a7f4  mov     r8, [rbx+28h]; lpMem
0x18002a7f8  xor     edx, edx; dwFlags
0x18002a7fa  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x18002a801  call    cs:__imp_HeapFree
0x18002a807  nop
0x18002a808  jmp     loc_180010239
0x18002a80d  mov     rax, [rcx]
0x18002a810  mov     rax, [rax+10h]
0x18002a814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a819  mov     [rdi+18h], rsi
0x18002a81d  jmp     loc_18001024E
0x18002a822  mov     rcx, rdi
0x18002a825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a82a  mov     ebx, eax
0x18002a82c  jmp     loc_180010052
0x18002a831  mov     ebx, 0FFFFFFFFh
0x18002a836  lock xadd [rcx+28h], ebx
0x18002a83b  sub     ebx, 1
0x18002a83e  jnz     loc_180010052
0x18002a844  call    ??1CServer@@QEAA@XZ; CServer::~CServer(void)
0x18002a849  mov     rcx, cs:?sm_pach@CServer@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CServer::sm_pach
0x18002a850  test    rcx, rcx
0x18002a853  jz      short loc_18002A85E
0x18002a855  mov     rdx, rdi
0x18002a858  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18002a85e  xor     eax, eax
0x18002a860  jmp     loc_180010054
```
