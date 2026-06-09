# CResponse::Release(void)

- ea: `0x18000eaf0`
- end: `0x18000ed6e`
- name: `?Release@CResponse@@UEAAKXZ`
- size: `638`
- prototype: `unsigned int __fastcall(CResponse *__hidden this)`
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000f1d0`
- `0x18000f4b0`
- `0x18000f7e0`
- `0x180023f80`

## callees

- `0x18000eaf0`
- `0x18000f9b0`
- `0x18001e730`
- `0x180050ad4`
- `0x180064010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180029b99`
- `KERNEL32!HeapFree` at `0x180029bae`
- `KERNEL32!HeapFree` at `0x180029bee`
- `KERNEL32!HeapFree` at `0x180029c07`
- `KERNEL32!HeapFree` at `0x180029b99`
- `KERNEL32!HeapFree` at `0x180029bae`
- `KERNEL32!HeapFree` at `0x180029bee`
- `KERNEL32!HeapFree` at `0x180029c07`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000ed4d`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180029c5e`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000ed4d`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180029c5e`
- `iisutil!WriteRefTraceLog` at `0x180029aee`
- `iisutil!WriteRefTraceLog` at `0x180029aee`

## pseudocode

```c
__int64 __fastcall CResponse::Release(CResponse *this)
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
      CResponse::~CResponse(this);
      if ( CResponse::sm_pach )
        ALLOC_CACHE_HANDLER::Free(CResponse::sm_pach, this);
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
0x18000eaf0  mov     [rsp+arg_18], rbx
0x18000eaf5  push    rdi
0x18000eaf6  sub     rsp, 20h
0x18000eafa  test    byte ptr [rcx+28h], 4
0x18000eafe  mov     rdi, rcx
0x18000eb01  jz      loc_180029C37
0x18000eb07  mov     rdi, [rcx+30h]
0x18000eb0b  lea     rcx, ?Release@CSession@@UEAAKXZ; CSession::Release(void)
0x18000eb12  mov     rax, [rdi]
0x18000eb15  mov     rax, [rax+10h]
0x18000eb19  cmp     rax, rcx
0x18000eb1c  jnz     loc_180029C28
0x18000eb22  mov     ebx, 0FFFFFFFFh
0x18000eb27  lock xadd [rdi+58h], ebx
0x18000eb2c  dec     ebx
0x18000eb2e  test    cs:g_dwDebugFlags, 100000h
0x18000eb38  jnz     loc_180029AD8
0x18000eb3e  test    ebx, ebx
0x18000eb40  jz      short loc_18000EB4F
0x18000eb42  mov     eax, ebx
0x18000eb44  mov     rbx, [rsp+28h+arg_18]
0x18000eb49  add     rsp, 20h
0x18000eb4d  pop     rdi
0x18000eb4e  retn
0x18000eb4f  mov     rcx, [rdi+3F0h]
0x18000eb56  lea     rax, ??_7CSession@@6B@; const CSession::`vftable'
0x18000eb5d  mov     [rsp+28h+arg_0], rbp
0x18000eb62  mov     [rsp+28h+arg_8], rsi
0x18000eb67  xor     esi, esi
0x18000eb69  mov     [rsp+28h+arg_10], r14
0x18000eb6e  mov     [rdi], rax
0x18000eb71  test    rcx, rcx
0x18000eb74  jz      short loc_18000EB89
0x18000eb76  mov     rax, [rcx]
0x18000eb79  mov     rax, [rax+10h]
0x18000eb7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb82  mov     [rdi+3F0h], rsi
0x18000eb89  mov     rcx, [rdi+3C0h]
0x18000eb90  lea     rax, ??_7CServer@@6B@; const CServer::`vftable'
0x18000eb97  mov     [rdi+388h], rax
0x18000eb9e  test    rcx, rcx
0x18000eba1  jz      short loc_18000EBB6
0x18000eba3  mov     rax, [rcx]
0x18000eba6  mov     rax, [rax+10h]
0x18000ebaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebaf  mov     [rdi+3C0h], rsi
0x18000ebb6  mov     rcx, [rdi+3A0h]
0x18000ebbd  lea     rbp, ??_7CDispatch@@6B@; const CDispatch::`vftable'
0x18000ebc4  mov     [rdi+388h], rbp
0x18000ebcb  test    rcx, rcx
0x18000ebce  jnz     loc_180029AFA
0x18000ebd4  mov     rcx, [rdi+380h]
0x18000ebdb  lea     rax, ??_7CResponse@@6B?$CDispatchImpl@UIResponse@@@@@; const CResponse::`vftable'{for `CDispatchImpl<IResponse>'}
0x18000ebe2  mov     [rdi+340h], rax
0x18000ebe9  lea     rax, ??_7CResponse@@6BIStream@@@; const CResponse::`vftable'{for `IStream'}
0x18000ebf0  mov     [rdi+360h], rax
0x18000ebf7  test    rcx, rcx
0x18000ebfa  jz      short loc_18000EC0F
0x18000ebfc  mov     rax, [rcx]
0x18000ebff  mov     rax, [rax+10h]
0x18000ec03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec08  mov     [rdi+380h], rsi
0x18000ec0f  mov     rcx, [rdi+358h]
0x18000ec16  mov     [rdi+340h], rbp
0x18000ec1d  test    rcx, rcx
0x18000ec20  jnz     loc_180029B12
0x18000ec26  mov     rcx, [rdi+338h]
0x18000ec2d  lea     rax, ??_7CRequest@@6B?$CDispatchImpl@UIRequest@@@@@; const CRequest::`vftable'{for `CDispatchImpl<IRequest>'}
0x18000ec34  mov     [rdi+2F8h], rax
0x18000ec3b  lea     rax, ??_7CRequest@@6BIStream@@@; const CRequest::`vftable'{for `IStream'}
0x18000ec42  mov     [rdi+318h], rax
0x18000ec49  test    rcx, rcx
0x18000ec4c  jz      short loc_18000EC61
0x18000ec4e  mov     rax, [rcx]
0x18000ec51  mov     rax, [rax+10h]
0x18000ec55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec5a  mov     [rdi+338h], rsi
0x18000ec61  mov     rcx, [rdi+310h]
0x18000ec68  mov     [rdi+2F8h], rbp
0x18000ec6f  test    rcx, rcx
0x18000ec72  jnz     loc_180029B2A
0x18000ec78  lea     rax, ??_7CViperActivity@@6B@; const CViperActivity::`vftable'
0x18000ec7f  mov     [rdi+2E0h], rax
0x18000ec86  cmp     [rdi+2E8h], rsi
0x18000ec8d  jnz     loc_180029B42
0x18000ec93  lea     rbx, [rdi+88h]
0x18000ec9a  mov     [rdi+2F0h], esi
0x18000eca0  mov     rcx, rbx; this
0x18000eca3  call    ?UnInit@CComponentCollection@@QEAAJXZ; CComponentCollection::UnInit(void)
0x18000eca8  mov     r8, [rbx+240h]; lpMem
0x18000ecaf  test    r8, r8
0x18000ecb2  jnz     loc_180029B90
0x18000ecb8  mov     [rbx+238h], esi
0x18000ecbe  mov     [rbx+240h], rsi
0x18000ecc5  mov     [rbx+248h], esi
0x18000eccb  mov     r8, [rbx+228h]; lpMem
0x18000ecd2  test    r8, r8
0x18000ecd5  jnz     loc_180029BA5
0x18000ecdb  mov     [rbx+220h], esi
0x18000ece1  mov     [rbx+228h], rsi
0x18000ece8  mov     [rbx+230h], esi
0x18000ecee  cmp     [rbx+208h], si
0x18000ecf5  jnz     loc_180029BBA
0x18000ecfb  test    byte ptr [rbx+110h], 2
0x18000ed02  lea     r14, ??_7CHashTable@@6B@; const CHashTable::`vftable'
0x18000ed09  mov     [rbx+108h], r14
0x18000ed10  jnz     loc_180029BDE
0x18000ed16  test    byte ptr [rbx+10h], 2
0x18000ed1a  mov     [rbx+8], r14
0x18000ed1e  mov     r14, [rsp+28h+arg_10]
0x18000ed23  jnz     loc_180029BFA
0x18000ed29  mov     rcx, [rdi+18h]
0x18000ed2d  mov     [rdi], rbp
0x18000ed30  mov     rbp, [rsp+28h+arg_0]
0x18000ed35  test    rcx, rcx
0x18000ed38  jnz     loc_180029C13
0x18000ed3e  mov     rcx, cs:?sm_pach@CSession@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CSession::sm_pach
0x18000ed45  test    rcx, rcx
0x18000ed48  jz      short loc_18000ED53
0x18000ed4a  mov     rdx, rdi
0x18000ed4d  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18000ed53  lock dec cs:?g_nSessionObjectsActive@@3JA; long g_nSessionObjectsActive
0x18000ed5a  mov     ebx, esi
0x18000ed5c  mov     rsi, [rsp+28h+arg_8]
0x18000ed61  mov     eax, ebx
0x18000ed63  mov     rbx, [rsp+28h+arg_18]
0x18000ed68  add     rsp, 20h
0x18000ed6c  pop     rdi
0x18000ed6d  retn
0x180029ad8  mov     rcx, cs:?gm_pTraceLog@CSession@@2PEAU_TRACE_LOG@@EA; _TRACE_LOG * CSession::gm_pTraceLog
0x180029adf  test    rcx, rcx
0x180029ae2  jz      loc_18000EB3E
0x180029ae8  mov     edx, [rdi+58h]
0x180029aeb  mov     r8, rdi
0x180029aee  call    cs:__imp_WriteRefTraceLog
0x180029af4  nop
0x180029af5  jmp     loc_18000EB3E
0x180029afa  mov     rax, [rcx]
0x180029afd  mov     rax, [rax+10h]
0x180029b01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029b06  mov     [rdi+3A0h], rsi
0x180029b0d  jmp     loc_18000EBD4
0x180029b12  mov     rax, [rcx]
0x180029b15  mov     rax, [rax+10h]
0x180029b19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029b1e  mov     [rdi+358h], rsi
0x180029b25  jmp     loc_18000EC26
0x180029b2a  mov     rax, [rcx]
0x180029b2d  mov     rax, [rax+10h]
0x180029b31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029b36  mov     [rdi+310h], rsi
0x180029b3d  jmp     loc_18000EC78
0x180029b42  cmp     dword ptr [rdi+2F0h], 1
0x180029b49  jbe     short loc_180029B71
0x180029b4b  mov     rcx, [rdi+2E8h]
0x180029b52  mov     rax, [rcx]
0x180029b55  mov     rax, [rax+30h]
0x180029b59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029b5e  mov     eax, [rdi+2F0h]
0x180029b64  dec     eax
0x180029b66  mov     [rdi+2F0h], eax
0x180029b6c  cmp     eax, 1
0x180029b6f  ja      short loc_180029B4B
0x180029b71  mov     rcx, [rdi+2E8h]
0x180029b78  mov     rax, [rcx]
0x180029b7b  mov     rax, [rax+10h]
0x180029b7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029b84  mov     [rdi+2E8h], rsi
0x180029b8b  jmp     loc_18000EC93
0x180029b90  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180029b97  xor     edx, edx; dwFlags
0x180029b99  call    cs:__imp_HeapFree
0x180029b9f  nop
0x180029ba0  jmp     loc_18000ECB8
0x180029ba5  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180029bac  xor     edx, edx; dwFlags
0x180029bae  call    cs:__imp_HeapFree
0x180029bb4  nop
0x180029bb5  jmp     loc_18000ECDB
0x180029bba  mov     rcx, [rbx+210h]; struct CIdHashArray *
0x180029bc1  test    rcx, rcx
0x180029bc4  jz      short loc_180029BCB
0x180029bc6  call    ?Free@CIdHashArray@@SAXPEAU1@@Z; CIdHashArray::Free(CIdHashArray *)
0x180029bcb  mov     [rbx+210h], rsi
0x180029bd2  mov     [rbx+208h], si
0x180029bd9  jmp     loc_18000ECFB
0x180029bde  mov     r8, [rbx+128h]; lpMem
0x180029be5  xor     edx, edx; dwFlags
0x180029be7  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180029bee  call    cs:__imp_HeapFree
0x180029bf4  nop
0x180029bf5  jmp     loc_18000ED16
0x180029bfa  mov     r8, [rbx+28h]; lpMem
0x180029bfe  xor     edx, edx; dwFlags
0x180029c00  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180029c07  call    cs:__imp_HeapFree
0x180029c0d  nop
0x180029c0e  jmp     loc_18000ED29
0x180029c13  mov     rax, [rcx]
0x180029c16  mov     rax, [rax+10h]
0x180029c1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029c1f  mov     [rdi+18h], rsi
0x180029c23  jmp     loc_18000ED3E
0x180029c28  mov     rcx, rdi
0x180029c2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029c30  mov     ebx, eax
0x180029c32  jmp     loc_18000EB42
0x180029c37  mov     ebx, 0FFFFFFFFh
0x180029c3c  lock xadd [rcx+30h], ebx
0x180029c41  sub     ebx, 1
0x180029c44  jnz     loc_18000EB42
0x180029c4a  call    ??1CResponse@@QEAA@XZ; CResponse::~CResponse(void)
0x180029c4f  mov     rcx, cs:?sm_pach@CResponse@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CResponse::sm_pach
0x180029c56  test    rcx, rcx
0x180029c59  jz      short loc_180029C64
0x180029c5b  mov     rdx, rdi
0x180029c5e  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x180029c64  xor     eax, eax
0x180029c66  jmp     loc_18000EB44
```
