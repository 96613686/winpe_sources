# CSessionMgr::DeleteSession(CSession *,int)

- ea: `0x18000fce0`
- end: `0x18000fff5`
- name: `?DeleteSession@CSessionMgr@@QEAAJPEAVCSession@@H@Z`
- size: `789`
- prototype: `int(CSessionMgr *__hidden this, struct CSession *, int)`
- caller_count: `3`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010290`
- `0x18001bdf8`
- `0x180058950`

## callees

- `0x18000a160`
- `0x18000ca50`
- `0x18000e1f0`
- `0x18000f9b0`
- `0x18000fce0`
- `0x18001a600`
- `0x180032cfc`
- `0x180040568`
- `0x180045dc0`
- `0x1800473b0`
- `0x18004ad84`
- `0x18004baf4`
- `0x180058a8c`
- `0x1800590b8`
- `0x1800591d0`
- `0x180064010`

## import_xrefs

- `ole32!CoDisconnectObject` at `0x18000fdd0`
- `ole32!CoDisconnectObject` at `0x18000fdf5`
- `ole32!CoDisconnectObject` at `0x18000fe0d`
- `ole32!CoDisconnectObject` at `0x18000fe32`
- `ole32!CoDisconnectObject` at `0x18000fe49`
- `ole32!CoDisconnectObject` at `0x18000fe61`
- `ole32!CoDisconnectObject` at `0x18000fe6d`
- `ole32!CoDisconnectObject` at `0x18000fe96`
- `ole32!CoDisconnectObject` at `0x18000fea7`
- `ole32!CoDisconnectObject` at `0x18000febf`
- `ole32!CoDisconnectObject` at `0x18000fee6`
- `ole32!CoDisconnectObject` at `0x18000fefa`
- `ole32!CoDisconnectObject` at `0x18000ff09`
- `ole32!CoDisconnectObject` at `0x18000ff14`
- `ole32!CoDisconnectObject` at `0x18000ffa8`
- `ole32!CoDisconnectObject` at `0x18002a58d`
- `ole32!CoDisconnectObject` at `0x18002a685`
- `ole32!CoDisconnectObject` at `0x18000fdd0`
- `ole32!CoDisconnectObject` at `0x18000fdf5`
- `ole32!CoDisconnectObject` at `0x18000fe0d`
- `ole32!CoDisconnectObject` at `0x18000fe32`
- `ole32!CoDisconnectObject` at `0x18000fe49`
- `ole32!CoDisconnectObject` at `0x18000fe61`
- `ole32!CoDisconnectObject` at `0x18000fe6d`
- `ole32!CoDisconnectObject` at `0x18000fe96`
- `ole32!CoDisconnectObject` at `0x18000fea7`
- `ole32!CoDisconnectObject` at `0x18000febf`
- `ole32!CoDisconnectObject` at `0x18000fee6`
- `ole32!CoDisconnectObject` at `0x18000fefa`
- `ole32!CoDisconnectObject` at `0x18000ff09`
- `ole32!CoDisconnectObject` at `0x18000ff14`
- `ole32!CoDisconnectObject` at `0x18000ffa8`
- `ole32!CoDisconnectObject` at `0x18002a58d`
- `ole32!CoDisconnectObject` at `0x18002a685`
- `KERNEL32!GetTickCount` at `0x18000ff63`
- `KERNEL32!GetTickCount` at `0x18000ff63`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18002a5ef`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18002a5ef`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18002a435`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18002a435`

## pseudocode

```c
__int64 __fastcall CSessionMgr::DeleteSession(CSessionMgr *this, struct CSession *a2, int a3)
{
  int v6; // edx
  CSessionVariants *v7; // rcx
  CSessionVariants *v8; // rcx
  unsigned int *v9; // rdi
  int v10; // eax
  IUnknown *v11; // rcx
  IUnknown *v12; // rcx
  IUnknown *v13; // rcx
  CResponse *v14; // rsi
  IUnknown *v15; // rcx
  IUnknown *v16; // rcx
  IUnknown *v17; // rcx
  IUnknown *v18; // rcx
  __int64 v19; // r14
  int v20; // eax
  int v21; // eax
  IUnknown *v22; // rcx
  IUnknown *v23; // rcx
  IUnknown *v24; // rcx
  IUnknown *v25; // rcx
  IUnknown *v26; // rcx
  volatile signed __int32 *v27; // rax
  DWORD TickCount; // eax
  unsigned int v29; // ecx
  __int32 v30; // edx
  volatile __int32 *v31; // rax
  unsigned int (__fastcall *v32)(CSession *__hidden); // rax
  CHitObj *v34; // rax
  CHitObj *v35; // rax
  CHitObj *v36; // rsi
  int v37; // edi
  unsigned int v38; // eax
  int v39; // eax
  void **v40; // rdi
  int v41; // [rsp+80h] [rbp+18h] BYREF
  CHitObj *v42; // [rsp+88h] [rbp+20h]

  (*(void (__fastcall **)(struct CSession *))(*(_QWORD *)a2 + 160LL))(a2);
  v6 = *((_DWORD *)a2 + 8);
  if ( !a3
    && (v6 & 0x800) != 0
    && (*((_WORD *)a2 + 365) || *((_WORD *)a2 + 367) || *((_WORD *)a2 + 366) && (*((_BYTE *)a2 + 136) & 0x40) != 0)
    || (v6 & 0x14) == 0x10 )
  {
    (*(void (__fastcall **)(struct CSession *))(*(_QWORD *)a2 + 8LL))(a2);
    v34 = (CHitObj *)ALLOC_CACHE_HANDLER::Alloc(CHitObj::sm_pach);
    if ( !v34 )
    {
      v36 = 0;
      v42 = 0;
      goto LABEL_94;
    }
    v35 = CHitObj::CHitObj(v34);
    v36 = v35;
    v42 = v35;
    if ( !v35 )
      goto LABEL_94;
    CHitObj::SessionCleanupInit(v35, a2);
    if ( a3 )
    {
      v37 = 0;
      v41 = 0;
      CHitObj::ViperAsyncCallback(v36, &v41);
      (**(void (__fastcall ***)(CHitObj *, __int64))v36)(v36, 1);
    }
    else
    {
      v37 = CHitObj::PostViperAsyncCall(v36);
      if ( v37 >= 0 )
        goto LABEL_91;
      _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)this + 2) + 84LL));
      (**(void (__fastcall ***)(CHitObj *, __int64))v36)(v36, 1);
    }
    v42 = 0;
    v36 = 0;
LABEL_91:
    if ( v37 >= 0 )
    {
LABEL_96:
      (*(void (__fastcall **)(struct CSession *))(*(_QWORD *)a2 + 16LL))(a2);
      return 0;
    }
LABEL_94:
    CSession::UnInit((LPUNKNOWN)a2);
    _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)this + 2) + 84LL));
    (*(void (__fastcall **)(struct CSession *))(*(_QWORD *)a2 + 16LL))(a2);
    if ( v36 )
      _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)this + 2) + 84LL));
    goto LABEL_96;
  }
  if ( (v6 & 0x400) != 0 )
    CSessionMgr::RemoveSessionFromTOBucket(*(CSessionMgr **)(*((_QWORD *)a2 + 5) + 144LL), a2, 1);
  v7 = (CSessionVariants *)*((_QWORD *)a2 + 7);
  if ( v7 )
  {
    CSessionVariants::UnInit(v7);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)a2 + 7) + 16LL))(*((_QWORD *)a2 + 7));
    *((_QWORD *)a2 + 7) = 0;
  }
  v8 = (CSessionVariants *)*((_QWORD *)a2 + 8);
  if ( v8 )
  {
    CSessionVariants::UnInit(v8);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)a2 + 8) + 16LL))(*((_QWORD *)a2 + 8));
    *((_QWORD *)a2 + 8) = 0;
  }
  if ( (*((_DWORD *)a2 + 8) & 0x800) != 0 )
  {
    CComponentCollection::UnInit((struct CSession *)((char *)a2 + 136));
    *((_DWORD *)a2 + 8) &= ~0x800u;
  }
  v9 = (unsigned int *)((char *)a2 + 752);
  if ( *((_QWORD *)a2 + 93) )
  {
    if ( *v9 > 1 )
    {
      do
      {
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)a2 + 93) + 48LL))(*((_QWORD *)a2 + 93));
        v38 = *v9 - 1;
        *v9 = v38;
      }
      while ( v38 > 1 );
    }
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)a2 + 93) + 16LL))(*((_QWORD *)a2 + 93));
    *((_QWORD *)a2 + 93) = 0;
  }
  *v9 = 0;
  v10 = *((_DWORD *)a2 + 8);
  if ( (v10 & 0x8000) != 0 )
  {
    v14 = (struct CSession *)((char *)a2 + 760);
  }
  else
  {
    *((_DWORD *)a2 + 8) = v10 | 0x8000;
    v11 = (IUnknown *)*((_QWORD *)a2 + 7);
    if ( v11 )
      CSessionVariants::DisconnectObjects(v11);
    v12 = (IUnknown *)*((_QWORD *)a2 + 8);
    if ( v12 )
      CSessionVariants::DisconnectObjects(v12);
    v13 = (IUnknown *)*((_QWORD *)a2 + 126);
    if ( v13 )
      CoDisconnectObject(v13, 0);
    v14 = (struct CSession *)((char *)a2 + 760);
    if ( !*((_DWORD *)a2 + 201) )
    {
      *((_DWORD *)a2 + 201) = 1;
      v15 = (IUnknown *)*((_QWORD *)a2 + 103);
      if ( v15 )
        CoDisconnectObject(v15, 0);
      v16 = (IUnknown *)*((_QWORD *)a2 + 102);
      if ( v16 )
        CRequestData::DisconnectObjects(v16);
      CoDisconnectObject((LPUNKNOWN)a2 + 95, 0);
    }
    if ( !*((_DWORD *)a2 + 219) )
    {
      *((_DWORD *)a2 + 219) = 1;
      v17 = (IUnknown *)*((_QWORD *)a2 + 112);
      if ( v17 )
        CoDisconnectObject(v17, 0);
      if ( (*((_BYTE *)a2 + 872) & 4) != 0 )
      {
        v18 = (IUnknown *)*((_QWORD *)a2 + 110);
        if ( v18 )
          CoDisconnectObject(v18, 0);
      }
      v19 = *((_QWORD *)a2 + 111);
      if ( v19 )
      {
        v39 = *(_DWORD *)(v19 + 280);
        if ( (v39 & 0x200) == 0 )
        {
          *(_DWORD *)(v19 + 280) = v39 | 0x200;
          CSupportErrorInfo::DisconnectObjects((LPUNKNOWN)(v19 + 8));
          CoDisconnectObject((LPUNKNOWN)v19, 0);
        }
      }
      CoDisconnectObject((LPUNKNOWN)a2 + 104, 0);
      CoDisconnectObject((LPUNKNOWN)a2 + 108, 0);
    }
    v20 = *((_DWORD *)a2 + 234);
    if ( (v20 & 8) == 0 )
    {
      v21 = v20 | 8;
      *((_DWORD *)a2 + 234) = v21;
      if ( (v21 & 4) != 0 )
      {
        v22 = (IUnknown *)*((_QWORD *)a2 + 118);
        if ( v22 )
          CoDisconnectObject(v22, 0);
      }
      v23 = (IUnknown *)*((_QWORD *)a2 + 120);
      if ( v23 )
        CoDisconnectObject(v23, 0);
      v24 = (IUnknown *)*((_QWORD *)a2 + 119);
      if ( v24 )
        CSupportErrorInfo::DisconnectObjects(v24);
      CoDisconnectObject((LPUNKNOWN)a2 + 113, 0);
    }
    if ( !*((_DWORD *)a2 + 250) )
    {
      *((_DWORD *)a2 + 250) = 1;
      v25 = (IUnknown *)*((_QWORD *)a2 + 122);
      if ( v25 )
        CoDisconnectObject(v25, 0);
      v26 = (IUnknown *)*((_QWORD *)a2 + 123);
      if ( v26 )
        CoDisconnectObject(v26, 0);
      CoDisconnectObject((LPUNKNOWN)a2 + 121, 0);
    }
    CoDisconnectObject((LPUNKNOWN)a2, 0);
  }
  if ( (*((_BYTE *)v14 + 40) & 1) != 0 )
  {
    CResponse::CleanUp(v14);
    *((_DWORD *)v14 + 10) &= ~1u;
  }
  if ( (*((_BYTE *)a2 + 872) & 1) != 0 )
  {
    CResponse::CleanUp((struct CSession *)((char *)a2 + 832));
    *((_DWORD *)a2 + 218) &= ~1u;
  }
  if ( (*((_BYTE *)a2 + 936) & 1) != 0 )
  {
    v8 = CServerData::sm_pach;
    v40 = (void **)((char *)a2 + 952);
    if ( CServerData::sm_pach )
      ALLOC_CACHE_HANDLER::Free(CServerData::sm_pach, *v40);
    *v40 = 0;
    *((_DWORD *)a2 + 234) &= ~1u;
  }
  if ( (*((_BYTE *)a2 + 32) & 0x20) != 0 )
    _InterlockedIncrement((volatile signed __int32 *)CPerfData::PDWCounter(v8, 23));
  if ( (dword_18007CB28 & 1) != 0 )
    v27 = (volatile signed __int32 *)(qword_18007CB88 + 92);
  else
    v27 = (volatile signed __int32 *)&qword_18007CBF0;
  _InterlockedDecrement(v27);
  TickCount = GetTickCount();
  v29 = *((_DWORD *)a2 + 32);
  v30 = TickCount - v29;
  if ( TickCount < v29 )
    --v30;
  if ( (dword_18007CB28 & 1) != 0 )
    v31 = (volatile __int32 *)(qword_18007CB88 + 88);
  else
    v31 = &dword_18007CBEC;
  _InterlockedExchange(v31, v30);
  _InterlockedDecrement((volatile signed __int32 *)&g_nSessions);
  *((_QWORD *)a2 + 5) = 0;
  *((_QWORD *)a2 + 6) = 0;
  *((_DWORD *)a2 + 8) |= 0x200u;
  CoDisconnectObject((LPUNKNOWN)a2, 0);
  v32 = *(unsigned int (__fastcall **)(CSession *__hidden))(*(_QWORD *)a2 + 16LL);
  if ( v32 == CSession::Release )
    CSession::Release(a2);
  else
    v32(a2);
  _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)this + 2) + 84LL));
  return 0;
}

```

## disassembly

```asm
0x18000fce0  mov     [rsp+pUnk], rdx
0x18000fce5  mov     [rsp+arg_0], rcx
0x18000fcea  push    rbx
0x18000fceb  push    rsi
0x18000fcec  push    rdi
0x18000fced  push    r13
0x18000fcef  push    r14
0x18000fcf1  push    r15
0x18000fcf3  sub     rsp, 38h
0x18000fcf7  mov     edi, r8d
0x18000fcfa  mov     rbx, rdx
0x18000fcfd  mov     r13, rcx
0x18000fd00  mov     rax, [rdx]
0x18000fd03  mov     rcx, rdx
0x18000fd06  mov     rax, [rax+0A0h]
0x18000fd0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd12  mov     edx, [rbx+20h]
0x18000fd15  test    edi, edi
0x18000fd17  jz      loc_18002A3E6
0x18000fd1d  mov     eax, edx
0x18000fd1f  and     al, 14h
0x18000fd21  cmp     al, 10h
0x18000fd23  jz      loc_18002A41F
0x18000fd29  bt      edx, 0Ah
0x18000fd2d  jb      loc_18002A4A9
0x18000fd33  mov     rcx, [rbx+38h]; this
0x18000fd37  test    rcx, rcx
0x18000fd3a  jnz     loc_18002A4C8
0x18000fd40  xor     r15d, r15d
0x18000fd43  mov     rcx, [rbx+40h]; this
0x18000fd47  test    rcx, rcx
0x18000fd4a  jnz     loc_18002A4E9
0x18000fd50  test    dword ptr [rbx+20h], 800h
0x18000fd57  jnz     loc_18002A507
0x18000fd5d  lea     rdi, [rbx+2F0h]
0x18000fd64  cmp     qword ptr [rbx+2E8h], 0
0x18000fd6c  jz      short loc_18000FD91
0x18000fd6e  cmp     dword ptr [rdi], 1
0x18000fd71  ja      loc_18002A51F
0x18000fd77  mov     rcx, [rbx+2E8h]
0x18000fd7e  mov     rax, [rcx]
0x18000fd81  mov     rax, [rax+10h]
0x18000fd85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd8a  mov     [rbx+2E8h], r15
0x18000fd91  mov     [rdi], r15d
0x18000fd94  mov     eax, [rbx+20h]
0x18000fd97  bt      eax, 0Fh
0x18000fd9b  jb      loc_18002A5A4
0x18000fda1  bts     eax, 0Fh
0x18000fda5  mov     [rbx+20h], eax
0x18000fda8  mov     rcx, [rbx+38h]; pUnk
0x18000fdac  test    rcx, rcx
0x18000fdaf  jnz     loc_18002A542
0x18000fdb5  mov     rcx, [rbx+40h]; pUnk
0x18000fdb9  test    rcx, rcx
0x18000fdbc  jnz     loc_18002A54D
0x18000fdc2  mov     rcx, [rbx+3F0h]; pUnk
0x18000fdc9  test    rcx, rcx
0x18000fdcc  jz      short loc_18000FDD6
0x18000fdce  xor     edx, edx; dwReserved
0x18000fdd0  call    cs:__imp_CoDisconnectObject
0x18000fdd6  lea     rsi, [rbx+2F8h]
0x18000fddd  cmp     dword ptr [rsi+2Ch], 0
0x18000fde1  jnz     short loc_18000FE13
0x18000fde3  mov     dword ptr [rsi+2Ch], 1
0x18000fdea  mov     rcx, [rsi+40h]; pUnk
0x18000fdee  test    rcx, rcx
0x18000fdf1  jz      short loc_18000FDFB
0x18000fdf3  xor     edx, edx; dwReserved
0x18000fdf5  call    cs:__imp_CoDisconnectObject
0x18000fdfb  mov     rcx, [rsi+38h]; pUnk
0x18000fdff  test    rcx, rcx
0x18000fe02  jnz     loc_18002A558
0x18000fe08  xor     edx, edx; dwReserved
0x18000fe0a  mov     rcx, rsi; pUnk
0x18000fe0d  call    cs:__imp_CoDisconnectObject
0x18000fe13  lea     rdi, [rbx+340h]
0x18000fe1a  cmp     dword ptr [rdi+2Ch], 0
0x18000fe1e  jnz     short loc_18000FE73
0x18000fe20  mov     dword ptr [rdi+2Ch], 1
0x18000fe27  mov     rcx, [rdi+40h]; pUnk
0x18000fe2b  test    rcx, rcx
0x18000fe2e  jz      short loc_18000FE38
0x18000fe30  xor     edx, edx; dwReserved
0x18000fe32  call    cs:__imp_CoDisconnectObject
0x18000fe38  test    byte ptr [rdi+28h], 4
0x18000fe3c  jz      short loc_18000FE4F
0x18000fe3e  mov     rcx, [rdi+30h]; pUnk
0x18000fe42  test    rcx, rcx
0x18000fe45  jz      short loc_18000FE4F
0x18000fe47  xor     edx, edx; dwReserved
0x18000fe49  call    cs:__imp_CoDisconnectObject
0x18000fe4f  mov     r14, [rdi+38h]
0x18000fe53  test    r14, r14
0x18000fe56  jnz     loc_18002A563
0x18000fe5c  xor     edx, edx; dwReserved
0x18000fe5e  mov     rcx, rdi; pUnk
0x18000fe61  call    cs:__imp_CoDisconnectObject
0x18000fe67  lea     rcx, [rdi+20h]; pUnk
0x18000fe6b  xor     edx, edx; dwReserved
0x18000fe6d  call    cs:__imp_CoDisconnectObject
0x18000fe73  lea     rdi, [rbx+388h]
0x18000fe7a  mov     eax, [rdi+20h]
0x18000fe7d  test    al, 8
0x18000fe7f  jnz     short loc_18000FEC5
0x18000fe81  or      eax, 8
0x18000fe84  mov     [rdi+20h], eax
0x18000fe87  test    al, 4
0x18000fe89  jz      short loc_18000FE9C
0x18000fe8b  mov     rcx, [rdi+28h]; pUnk
0x18000fe8f  test    rcx, rcx
0x18000fe92  jz      short loc_18000FE9C
0x18000fe94  xor     edx, edx; dwReserved
0x18000fe96  call    cs:__imp_CoDisconnectObject
0x18000fe9c  mov     rcx, [rdi+38h]; pUnk
0x18000fea0  test    rcx, rcx
0x18000fea3  jz      short loc_18000FEAD
0x18000fea5  xor     edx, edx; dwReserved
0x18000fea7  call    cs:__imp_CoDisconnectObject
0x18000fead  mov     rcx, [rdi+30h]; pUnk
0x18000feb1  test    rcx, rcx
0x18000feb4  jnz     loc_18002A599
0x18000feba  xor     edx, edx; dwReserved
0x18000febc  mov     rcx, rdi; pUnk
0x18000febf  call    cs:__imp_CoDisconnectObject
0x18000fec5  cmp     dword ptr [rbx+3E8h], 0
0x18000fecc  jnz     short loc_18000FF0F
0x18000fece  mov     dword ptr [rbx+3E8h], 1
0x18000fed8  mov     rcx, [rbx+3D0h]; pUnk
0x18000fedf  test    rcx, rcx
0x18000fee2  jz      short loc_18000FEEC
0x18000fee4  xor     edx, edx; dwReserved
0x18000fee6  call    cs:__imp_CoDisconnectObject
0x18000feec  mov     rcx, [rbx+3D8h]; pUnk
0x18000fef3  test    rcx, rcx
0x18000fef6  jz      short loc_18000FF00
0x18000fef8  xor     edx, edx; dwReserved
0x18000fefa  call    cs:__imp_CoDisconnectObject
0x18000ff00  xor     edx, edx; dwReserved
0x18000ff02  lea     rcx, [rbx+3C8h]; pUnk
0x18000ff09  call    cs:__imp_CoDisconnectObject
0x18000ff0f  xor     edx, edx; dwReserved
0x18000ff11  mov     rcx, rbx; pUnk
0x18000ff14  call    cs:__imp_CoDisconnectObject
0x18000ff1a  test    byte ptr [rsi+28h], 1
0x18000ff1e  jnz     loc_18002A5B0
0x18000ff24  test    byte ptr [rbx+368h], 1
0x18000ff2b  jnz     loc_18002A5C1
0x18000ff31  test    byte ptr [rbx+3A8h], 1
0x18000ff38  jnz     loc_18002A5D9
0x18000ff3e  test    byte ptr [rbx+20h], 20h
0x18000ff42  jnz     loc_18002A604
0x18000ff48  test    byte ptr cs:dword_18007CB28, 1
0x18000ff4f  jz      loc_18002A616
0x18000ff55  mov     rax, cs:qword_18007CB88
0x18000ff5c  add     rax, 5Ch ; '\'
0x18000ff60  lock dec dword ptr [rax]
0x18000ff63  call    cs:__imp_GetTickCount
0x18000ff69  mov     ecx, [rbx+80h]
0x18000ff6f  mov     edx, eax
0x18000ff71  sub     edx, ecx
0x18000ff73  cmp     eax, ecx
0x18000ff75  jb      short loc_18000FFE1
0x18000ff77  test    byte ptr cs:dword_18007CB28, 1
0x18000ff7e  jz      short loc_18000FFE5
0x18000ff80  mov     rax, cs:qword_18007CB88
0x18000ff87  add     rax, 58h ; 'X'
0x18000ff8b  xchg    edx, [rax]
0x18000ff8d  lock dec cs:?g_nSessions@@3KA; ulong g_nSessions
0x18000ff94  mov     [rbx+28h], r15
0x18000ff98  mov     [rbx+30h], r15
0x18000ff9c  or      dword ptr [rbx+20h], 200h
0x18000ffa3  xor     edx, edx; dwReserved
0x18000ffa5  mov     rcx, rbx; pUnk
0x18000ffa8  call    cs:__imp_CoDisconnectObject
0x18000ffae  mov     rax, [rbx]
0x18000ffb1  mov     rax, [rax+10h]
0x18000ffb5  lea     rcx, ?Release@CSession@@UEAAKXZ; CSession::Release(void)
0x18000ffbc  cmp     rax, rcx
0x18000ffbf  mov     rcx, rbx; this
0x18000ffc2  jnz     short loc_18000FFEE
0x18000ffc4  call    ?Release@CSession@@UEAAKXZ; CSession::Release(void)
0x18000ffc9  mov     rax, [r13+10h]
0x18000ffcd  lock dec dword ptr [rax+54h]
0x18000ffd1  xor     eax, eax
0x18000ffd3  add     rsp, 38h
0x18000ffd7  pop     r15
0x18000ffd9  pop     r14
0x18000ffdb  pop     r13
0x18000ffdd  pop     rdi
0x18000ffde  pop     rsi
0x18000ffdf  pop     rbx
0x18000ffe0  retn
0x18000ffe1  dec     edx
0x18000ffe3  jmp     short loc_18000FF77
0x18000ffe5  lea     rax, dword_18007CBEC
0x18000ffec  jmp     short loc_18000FF8B
0x18000ffee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fff3  jmp     short loc_18000FFC9
0x18002a3e6  bt      edx, 0Bh
0x18002a3ea  jnb     loc_18000FD1D
0x18002a3f0  cmp     word ptr [rbx+2DAh], 0
0x18002a3f8  ja      short loc_18002A41F
0x18002a3fa  cmp     word ptr [rbx+2DEh], 0
0x18002a402  ja      short loc_18002A41F
0x18002a404  cmp     word ptr [rbx+2DCh], 0
0x18002a40c  jbe     loc_18000FD1D
0x18002a412  test    byte ptr [rbx+88h], 40h
0x18002a419  jz      loc_18000FD1D
0x18002a41f  mov     rax, [rbx]
0x18002a422  mov     rcx, rbx
0x18002a425  mov     rax, [rax+8]
0x18002a429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a42e  mov     rcx, cs:?sm_pach@CHitObj@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CHitObj::sm_pach
0x18002a435  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x18002a43b  test    rax, rax
0x18002a43e  jz      loc_18002A65C
0x18002a444  mov     rcx, rax; this
0x18002a447  call    ??0CHitObj@@QEAA@XZ; CHitObj::CHitObj(void)
0x18002a44c  mov     rsi, rax
0x18002a44f  mov     [rsp+68h+arg_18], rax
0x18002a457  test    rax, rax
0x18002a45a  jz      loc_18002A66A
0x18002a460  mov     rdx, rbx; struct CSession *
0x18002a463  mov     rcx, rax; this
0x18002a466  call    ?SessionCleanupInit@CHitObj@@QEAAXPEAVCSession@@@Z; CHitObj::SessionCleanupInit(CSession *)
0x18002a46b  mov     rcx, rsi; this
0x18002a46e  test    edi, edi
0x18002a470  jz      loc_18002A622
0x18002a476  xor     r15d, r15d
0x18002a479  mov     edi, r15d
0x18002a47c  mov     [rsp+68h+arg_10], r15d
0x18002a484  lea     rdx, [rsp+68h+arg_10]; int *
0x18002a48c  call    ?ViperAsyncCallback@CHitObj@@QEAAJPEAH@Z; CHitObj::ViperAsyncCallback(int *)
0x18002a491  mov     rax, [rsi]
0x18002a494  mov     edx, 1
0x18002a499  mov     rcx, rsi
0x18002a49c  mov     rax, [rax]
0x18002a49f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a4a4  jmp     loc_18002A64B
0x18002a4a9  mov     rcx, [rbx+28h]
0x18002a4ad  mov     r8d, 1; int
0x18002a4b3  mov     rdx, rbx; struct CSession *
0x18002a4b6  mov     rcx, [rcx+90h]; this
0x18002a4bd  call    ?RemoveSessionFromTOBucket@CSessionMgr@@QEAAJPEAVCSession@@H@Z; CSessionMgr::RemoveSessionFromTOBucket(CSession *,int)
0x18002a4c2  nop
0x18002a4c3  jmp     loc_18000FD33
0x18002a4c8  call    ?UnInit@CSessionVariants@@QEAAJXZ; CSessionVariants::UnInit(void)
0x18002a4cd  mov     rcx, [rbx+38h]
0x18002a4d1  mov     rax, [rcx]
0x18002a4d4  mov     rax, [rax+10h]
0x18002a4d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a4dd  xor     r15d, r15d
0x18002a4e0  mov     [rbx+38h], r15
0x18002a4e4  jmp     loc_18000FD43
0x18002a4e9  call    ?UnInit@CSessionVariants@@QEAAJXZ; CSessionVariants::UnInit(void)
0x18002a4ee  mov     rcx, [rbx+40h]
0x18002a4f2  mov     rax, [rcx]
0x18002a4f5  mov     rax, [rax+10h]
0x18002a4f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a4fe  mov     [rbx+40h], r15
0x18002a502  jmp     loc_18000FD50
0x18002a507  lea     rcx, [rbx+88h]; this
0x18002a50e  call    ?UnInit@CComponentCollection@@QEAAJXZ; CComponentCollection::UnInit(void)
0x18002a513  and     dword ptr [rbx+20h], 0FFFFF7FFh
0x18002a51a  jmp     loc_18000FD5D
0x18002a51f  mov     rcx, [rbx+2E8h]
0x18002a526  mov     rax, [rcx]
0x18002a529  mov     rax, [rax+30h]
0x18002a52d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a532  mov     eax, [rdi]
0x18002a534  dec     eax
0x18002a536  mov     [rdi], eax
0x18002a538  cmp     eax, 1
0x18002a53b  ja      short loc_18002A51F
0x18002a53d  jmp     loc_18000FD77
0x18002a542  call    ?DisconnectObjects@CSessionVariants@@QEAAJXZ; CSessionVariants::DisconnectObjects(void)
0x18002a547  nop
0x18002a548  jmp     loc_18000FDB5
0x18002a54d  call    ?DisconnectObjects@CSessionVariants@@QEAAJXZ; CSessionVariants::DisconnectObjects(void)
0x18002a552  nop
0x18002a553  jmp     loc_18000FDC2
0x18002a558  call    ?DisconnectObjects@CRequestData@@AEAAJXZ; CRequestData::DisconnectObjects(void)
0x18002a55d  nop
0x18002a55e  jmp     loc_18000FE08
0x18002a563  mov     eax, [r14+118h]
0x18002a56a  bt      eax, 9
0x18002a56e  jb      loc_18000FE5C
0x18002a574  bts     eax, 9
0x18002a578  mov     [r14+118h], eax
0x18002a57f  lea     rcx, [r14+8]; pUnk
0x18002a583  call    ?DisconnectObjects@CSupportErrorInfo@@QEAAJXZ; CSupportErrorInfo::DisconnectObjects(void)
0x18002a588  xor     edx, edx; dwReserved
0x18002a58a  mov     rcx, r14; pUnk
0x18002a58d  call    cs:__imp_CoDisconnectObject
0x18002a593  nop
0x18002a594  jmp     loc_18000FE5C
0x18002a599  call    ?DisconnectObjects@CSupportErrorInfo@@QEAAJXZ; CSupportErrorInfo::DisconnectObjects(void)
0x18002a59e  nop
0x18002a59f  jmp     loc_18000FEBA
  ... truncated ...
```
