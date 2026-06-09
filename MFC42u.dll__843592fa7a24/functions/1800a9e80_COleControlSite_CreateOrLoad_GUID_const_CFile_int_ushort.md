# COleControlSite::CreateOrLoad(_GUID const &,CFile *,int,ushort *)

- ea: `0x1800a9e80`
- end: `0x1800aa2fe`
- name: `?CreateOrLoad@COleControlSite@@IEAAJAEBU_GUID@@PEAVCFile@@HPEAG@Z`
- size: `1150`
- prototype: `__int64 __usercall@<rax>(COleControlSite *__hidden this@<rcx>, const struct _GUID *@<rdx>, struct CFile *@<r8>, int@<r9d>, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800a9ab0`

## callees

- `0x1800367b0`
- `0x180036910`
- `0x1800a9e80`
- `0x1800aac80`
- `0x1800aeab0`
- `0x1800d7010`

## import_xrefs

- `KERNEL32!GlobalUnlock` at `0x1800aa1aa`
- `KERNEL32!GlobalUnlock` at `0x1800aa1aa`
- `KERNEL32!GlobalAlloc` at `0x1800aa16e`
- `KERNEL32!GlobalAlloc` at `0x1800aa16e`
- `KERNEL32!GlobalLock` at `0x1800aa183`
- `KERNEL32!GlobalLock` at `0x1800aa183`
- `api-ms-win-core-com-l2-1-1!StgCreateDocfileOnILockBytes` at `0x1800aa112`
- `api-ms-win-core-com-l2-1-1!StgCreateDocfileOnILockBytes` at `0x1800aa112`
- `api-ms-win-core-com-l2-1-1!StgOpenStorageOnILockBytes` at `0x1800aa1fa`
- `api-ms-win-core-com-l2-1-1!StgOpenStorageOnILockBytes` at `0x1800aa1fa`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x1800aa0eb`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x1800aa1ca`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x1800aa0eb`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x1800aa1ca`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall COleControlSite::CreateOrLoad(
        COleControlSite *this,
        struct _GUID *a2,
        struct CFile *a3,
        const struct _GUID *a4,
        unsigned __int16 *a5)
{
  int v5; // r12d
  _QWORD *v8; // r14
  int result; // eax
  HRESULT ILockBytesOnHGlobal; // edi
  int v11; // r13d
  unsigned int v12; // r12d
  unsigned int v13; // eax
  __int64 v14; // rcx
  IStorage *v15; // rcx
  SIZE_T v16; // rdi
  HGLOBAL v17; // rax
  void *v18; // rbx
  LPVOID v19; // rdx
  IStorage *ppstgOpen; // [rsp+30h] [rbp-91h] BYREF
  LPLOCKBYTES pplkbyt[2]; // [rsp+38h] [rbp-89h] BYREF
  __int64 v22; // [rsp+48h] [rbp-79h] BYREF
  __int64 v23; // [rsp+50h] [rbp-71h] BYREF
  _BYTE v24[176]; // [rsp+60h] [rbp-61h] BYREF
  __int64 v25; // [rsp+120h] [rbp+5Fh] BYREF

  v5 = (int)a4;
  v8 = (_QWORD *)((char *)this + 128);
  result = _AfxCoCreateInstanceLic(a2, (struct IUnknown *)a2, 3u, a4, (void **)this + 16, a5);
  ILockBytesOnHGlobal = result;
  if ( result < 0 )
    return result;
  v22 = 0;
  v23 = 0;
  v25 = 0;
  COleControlSite::GetEventIID(this, (struct _GUID *)((char *)this + 108));
  v11 = (*(__int64 (__fastcall **)(COleControlSite *))(*(_QWORD *)this + 392LL))(this);
  if ( !v11 )
  {
    (*(void (__fastcall **)(_QWORD, __int64, char *))(*(_QWORD *)*v8 + 176LL))(*v8, 1, (char *)this + 184);
    if ( (*((_DWORD *)this + 46) & 0x20000) != 0 )
    {
      ILockBytesOnHGlobal = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v8 + 24LL))(*v8, (char *)this + 296);
      if ( ILockBytesOnHGlobal < 0 )
      {
        v12 = v11 + 1;
        goto LABEL_41;
      }
    }
  }
  if ( v5 )
    goto LABEL_16;
  if ( !a3
    || (**(int (__fastcall ***)(_QWORD, GUID *, __int64 *))*v8)(*v8, &IID_IPersistMemory, &v25) < 0
    || !(*(unsigned int (__fastcall **)(struct CFile *, __int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)a3 + 176LL))(
          a3,
          3,
          0,
          0,
          0) )
  {
    if ( (**(int (__fastcall ***)(_QWORD, GUID *, __int64 *))*v8)(*v8, &IID_IPersistStreamInit, &v22) >= 0 )
    {
      if ( a3 )
      {
        v12 = 1;
        CArchive::CArchive((CArchive *)v24, a3, 1u, 4096, 0);
        pplkbyt[0] = (LPLOCKBYTES)&CArchiveStream::`vftable';
        pplkbyt[1] = (LPLOCKBYTES)v24;
        ILockBytesOnHGlobal = (*(__int64 (__fastcall **)(__int64, LPLOCKBYTES *))(*(_QWORD *)v22 + 40LL))(v22, pplkbyt);
        CArchive::~CArchive((CArchive *)v24);
      }
      else
      {
        ILockBytesOnHGlobal = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 64LL))(v22);
        v12 = 1;
      }
      v14 = v22;
      goto LABEL_34;
    }
LABEL_16:
    if ( (**(int (__fastcall ***)(_QWORD, GUID *, __int64 *))*v8)(*v8, &IID_IPersistStorage, &v23) < 0 )
    {
      v12 = 1;
      goto LABEL_40;
    }
    if ( !a3 )
    {
      pplkbyt[0] = 0;
      v12 = 1;
      ILockBytesOnHGlobal = CreateILockBytesOnHGlobal(0, 1, pplkbyt);
      if ( ILockBytesOnHGlobal >= 0 )
      {
        ppstgOpen = 0;
        ILockBytesOnHGlobal = StgCreateDocfileOnILockBytes(pplkbyt[0], 0x1012u, 0, &ppstgOpen);
        if ( ILockBytesOnHGlobal >= 0 )
        {
          ILockBytesOnHGlobal = (*(__int64 (__fastcall **)(__int64, IStorage *))(*(_QWORD *)v23 + 40LL))(v23, ppstgOpen);
          ((void (__fastcall *)(IStorage *))ppstgOpen->lpVtbl->Release)(ppstgOpen);
        }
        v15 = (IStorage *)pplkbyt[0];
LABEL_29:
        ((void (__fastcall *)(IStorage *))v15->lpVtbl->Release)(v15);
        goto LABEL_33;
      }
      goto LABEL_33;
    }
    if ( v5 )
    {
      v16 = (*(unsigned int (__fastcall **)(struct CFile *))(*(_QWORD *)a3 + 112LL))(a3);
      v17 = GlobalAlloc(0, v16);
      v18 = v17;
      if ( v17 )
      {
        v19 = GlobalLock(v17);
        if ( v19 )
        {
          (*(void (__fastcall **)(struct CFile *, LPVOID, _QWORD))(*(_QWORD *)a3 + 120LL))(a3, v19, (unsigned int)v16);
          GlobalUnlock(v18);
          ppstgOpen = 0;
          v12 = 1;
          ILockBytesOnHGlobal = CreateILockBytesOnHGlobal(v18, 1, (LPLOCKBYTES *)&ppstgOpen);
          if ( ILockBytesOnHGlobal >= 0 )
          {
            pplkbyt[0] = 0;
            ILockBytesOnHGlobal = StgOpenStorageOnILockBytes(
                                    (ILockBytes *)ppstgOpen,
                                    0,
                                    0x12u,
                                    0,
                                    0,
                                    (IStorage **)pplkbyt);
            if ( ILockBytesOnHGlobal >= 0 )
            {
              ILockBytesOnHGlobal = (*(__int64 (__fastcall **)(__int64, LPLOCKBYTES))(*(_QWORD *)v23 + 48LL))(
                                      v23,
                                      pplkbyt[0]);
              ((void (__fastcall *)(LPLOCKBYTES))pplkbyt[0]->lpVtbl->Release)(pplkbyt[0]);
            }
            v15 = ppstgOpen;
            goto LABEL_29;
          }
LABEL_33:
          v14 = v23;
LABEL_34:
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
          goto LABEL_35;
        }
      }
      ILockBytesOnHGlobal = -2147024882;
    }
    else
    {
      ILockBytesOnHGlobal = -2147418113;
    }
    v12 = 1;
    goto LABEL_33;
  }
  pplkbyt[0] = 0;
  ppstgOpen = 0;
  v13 = (*(__int64 (__fastcall **)(struct CFile *, _QWORD, __int64, LPLOCKBYTES *, IStorage **))(*(_QWORD *)a3 + 176LL))(
          a3,
          0,
          0xFFFFFFFFLL,
          pplkbyt,
          &ppstgOpen);
  ILockBytesOnHGlobal = (*(__int64 (__fastcall **)(__int64, LPLOCKBYTES, _QWORD))(*(_QWORD *)v25 + 40LL))(
                          v25,
                          pplkbyt[0],
                          v13);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  v25 = 0;
  v12 = 1;
LABEL_35:
  if ( ILockBytesOnHGlobal < 0 )
    goto LABEL_41;
  if ( !v11 && (*((_DWORD *)this + 46) & 0x20000) == 0 )
    ILockBytesOnHGlobal = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v8 + 24LL))(*v8, (char *)this + 296);
LABEL_40:
  if ( ILockBytesOnHGlobal < 0 )
  {
LABEL_41:
    if ( *v8 )
    {
      (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v8 + 48LL))(*v8, v12);
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 16LL))(*v8);
      *v8 = 0;
    }
  }
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  if ( v11 )
  {
    if ( ILockBytesOnHGlobal >= 0 )
      return v12;
  }
  return ILockBytesOnHGlobal;
}

```

## disassembly

```asm
0x1800a9e80  push    rbp
0x1800a9e82  push    rbx
0x1800a9e83  push    rsi
0x1800a9e84  push    rdi
0x1800a9e85  push    r12
0x1800a9e87  push    r13
0x1800a9e89  push    r14
0x1800a9e8b  push    r15
0x1800a9e8d  lea     rbp, [rsp-17h]
0x1800a9e92  sub     rsp, 0D8h
0x1800a9e99  mov     r12d, r9d
0x1800a9e9c  mov     rsi, r8
0x1800a9e9f  mov     r15, rcx
0x1800a9ea2  lea     r14, [rcx+80h]
0x1800a9ea9  mov     rax, [rbp+4Fh+arg_20]
0x1800a9ead  mov     [rsp+110h+var_E8], rax; unsigned __int16 *
0x1800a9eb2  mov     qword ptr [rsp+110h+reserved], r14; void **
0x1800a9eb7  mov     r8d, 3; unsigned int
0x1800a9ebd  mov     rcx, rdx; struct _GUID *
0x1800a9ec0  call    ?_AfxCoCreateInstanceLic@@YAJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAXPEAG@Z; _AfxCoCreateInstanceLic(_GUID const &,IUnknown *,ulong,_GUID const &,void * *,ushort *)
0x1800a9ec5  mov     edi, eax
0x1800a9ec7  xor     ebx, ebx
0x1800a9ec9  test    eax, eax
0x1800a9ecb  js      loc_1800AA2EA
0x1800a9ed1  mov     [rbp+4Fh+var_C8], rbx
0x1800a9ed5  mov     [rbp+4Fh+var_C0], rbx
0x1800a9ed9  mov     [rbp+4Fh+arg_0], rbx
0x1800a9edd  lea     rdx, [r15+6Ch]; struct _GUID *
0x1800a9ee1  mov     rcx, r15; this
0x1800a9ee4  call    ?GetEventIID@COleControlSite@@QEAAHPEAU_GUID@@@Z; COleControlSite::GetEventIID(_GUID *)
0x1800a9ee9  mov     rax, [r15]
0x1800a9eec  mov     rcx, r15
0x1800a9eef  mov     rax, [rax+188h]
0x1800a9ef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9efb  mov     r13d, eax
0x1800a9efe  test    eax, eax
0x1800a9f00  jnz     short loc_1800A9F53
0x1800a9f02  mov     rcx, [r14]
0x1800a9f05  lea     rbx, [r15+0B8h]
0x1800a9f0c  mov     rdx, [rcx]
0x1800a9f0f  mov     rax, [rdx+0B0h]
0x1800a9f16  mov     r8, rbx
0x1800a9f19  lea     edx, [r13+1]
0x1800a9f1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9f22  test    dword ptr [rbx], 20000h
0x1800a9f28  jz      short loc_1800A9F51
0x1800a9f2a  mov     rcx, [r14]
0x1800a9f2d  mov     rax, [rcx]
0x1800a9f30  lea     rdx, [r15+128h]
0x1800a9f37  mov     rax, [rax+18h]
0x1800a9f3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9f40  mov     edi, eax
0x1800a9f42  xor     ebx, ebx
0x1800a9f44  test    eax, eax
0x1800a9f46  jns     short loc_1800A9F53
0x1800a9f48  lea     r12d, [r13+1]
0x1800a9f4c  jmp     loc_1800AA29F
0x1800a9f51  xor     ebx, ebx
0x1800a9f53  test    r12d, r12d
0x1800a9f56  jnz     loc_1800AA0B2
0x1800a9f5c  test    rsi, rsi
0x1800a9f5f  jz      loc_1800AA019
0x1800a9f65  mov     rcx, [r14]
0x1800a9f68  mov     rax, [rcx]
0x1800a9f6b  lea     r8, [rbp+4Fh+arg_0]
0x1800a9f6f  lea     rdx, IID_IPersistMemory
0x1800a9f76  mov     rax, [rax]
0x1800a9f79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9f7e  test    eax, eax
0x1800a9f80  js      loc_1800AA019
0x1800a9f86  mov     rax, [rsi]
0x1800a9f89  mov     qword ptr [rsp+110h+reserved], rbx
0x1800a9f8e  xor     r9d, r9d
0x1800a9f91  xor     r8d, r8d
0x1800a9f94  lea     edx, [r12+3]
0x1800a9f99  mov     rcx, rsi
0x1800a9f9c  mov     rax, [rax+0B0h]
0x1800a9fa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9fa8  test    eax, eax
0x1800a9faa  jz      short loc_1800AA019
0x1800a9fac  mov     [rsp+110h+pplkbyt], rbx
0x1800a9fb1  mov     [rsp+110h+ppstgOpen], rbx
0x1800a9fb6  mov     rax, [rsi]
0x1800a9fb9  lea     rcx, [rsp+110h+ppstgOpen]
0x1800a9fbe  mov     qword ptr [rsp+110h+reserved], rcx
0x1800a9fc3  lea     r9, [rsp+110h+pplkbyt]
0x1800a9fc8  or      r8d, 0FFFFFFFFh
0x1800a9fcc  xor     edx, edx
0x1800a9fce  mov     rcx, rsi
0x1800a9fd1  mov     rax, [rax+0B0h]
0x1800a9fd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9fdd  mov     rcx, [rbp+4Fh+arg_0]
0x1800a9fe1  mov     rdx, [rcx]
0x1800a9fe4  mov     r9, [rdx+28h]
0x1800a9fe8  mov     r8d, eax
0x1800a9feb  mov     rdx, [rsp+110h+pplkbyt]
0x1800a9ff0  mov     rax, r9
0x1800a9ff3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9ff8  mov     edi, eax
0x1800a9ffa  mov     rcx, [rbp+4Fh+arg_0]
0x1800a9ffe  mov     rax, [rcx]
0x1800aa001  mov     rax, [rax+10h]
0x1800aa005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa00a  mov     [rbp+4Fh+arg_0], rbx
0x1800aa00e  mov     r12d, 1
0x1800aa014  jmp     loc_1800AA265
0x1800aa019  mov     rcx, [r14]
0x1800aa01c  mov     rax, [rcx]
0x1800aa01f  lea     r8, [rbp+4Fh+var_C8]
0x1800aa023  lea     rdx, IID_IPersistStreamInit
0x1800aa02a  mov     rax, [rax]
0x1800aa02d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa032  test    eax, eax
0x1800aa034  js      short loc_1800AA0B2
0x1800aa036  test    rsi, rsi
0x1800aa039  jnz     short loc_1800AA053
0x1800aa03b  mov     rcx, [rbp+4Fh+var_C8]
0x1800aa03f  mov     rax, [rcx]
0x1800aa042  mov     rax, [rax+40h]
0x1800aa046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa04b  mov     edi, eax
0x1800aa04d  lea     r12d, [rsi+1]
0x1800aa051  jmp     short loc_1800AA0A9
0x1800aa053  mov     qword ptr [rsp+110h+reserved], rbx; void *
0x1800aa058  mov     r9d, 1000h; int
0x1800aa05e  mov     r12d, 1
0x1800aa064  mov     r8d, r12d; unsigned int
0x1800aa067  mov     rdx, rsi; struct CFile *
0x1800aa06a  lea     rcx, [rbp+4Fh+var_B0]; this
0x1800aa06e  call    ??0CArchive@@QEAA@PEAVCFile@@IHPEAX@Z; CArchive::CArchive(CFile *,uint,int,void *)
0x1800aa073  nop
0x1800aa074  lea     rax, ??_7CArchiveStream@@6B@; const CArchiveStream::`vftable'
0x1800aa07b  mov     [rsp+110h+pplkbyt], rax
0x1800aa080  lea     rax, [rbp+4Fh+var_B0]
0x1800aa084  mov     [rsp+110h+var_D0], rax
0x1800aa089  mov     rcx, [rbp+4Fh+var_C8]
0x1800aa08d  mov     rax, [rcx]
0x1800aa090  lea     rdx, [rsp+110h+pplkbyt]
0x1800aa095  mov     rax, [rax+28h]
0x1800aa099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa09e  mov     edi, eax
0x1800aa0a0  lea     rcx, [rbp+4Fh+var_B0]; this
0x1800aa0a4  call    ??1CArchive@@QEAA@XZ; CArchive::~CArchive(void)
0x1800aa0a9  mov     rcx, [rbp+4Fh+var_C8]
0x1800aa0ad  jmp     loc_1800AA259
0x1800aa0b2  mov     rcx, [r14]
0x1800aa0b5  mov     rax, [rcx]
0x1800aa0b8  lea     r8, [rbp+4Fh+var_C0]
0x1800aa0bc  lea     rdx, IID_IPersistStorage
0x1800aa0c3  mov     rax, [rax]
0x1800aa0c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa0cb  test    eax, eax
0x1800aa0cd  js      loc_1800AA295
0x1800aa0d3  test    rsi, rsi
0x1800aa0d6  jnz     short loc_1800AA150
0x1800aa0d8  mov     [rsp+110h+pplkbyt], rbx
0x1800aa0dd  lea     r8, [rsp+110h+pplkbyt]; pplkbyt
0x1800aa0e2  lea     r12d, [rsi+1]
0x1800aa0e6  mov     edx, r12d; fDeleteOnRelease
0x1800aa0e9  xor     ecx, ecx; hGlobal
0x1800aa0eb  call    cs:__imp_CreateILockBytesOnHGlobal
0x1800aa0f1  mov     edi, eax
0x1800aa0f3  test    eax, eax
0x1800aa0f5  js      loc_1800AA255
0x1800aa0fb  mov     [rsp+110h+ppstgOpen], rbx
0x1800aa100  lea     r9, [rsp+110h+ppstgOpen]; ppstgOpen
0x1800aa105  xor     r8d, r8d; reserved
0x1800aa108  mov     edx, 1012h; grfMode
0x1800aa10d  mov     rcx, [rsp+110h+pplkbyt]; plkbyt
0x1800aa112  call    cs:__imp_StgCreateDocfileOnILockBytes
0x1800aa118  mov     edi, eax
0x1800aa11a  test    eax, eax
0x1800aa11c  js      short loc_1800AA146
0x1800aa11e  mov     rcx, [rbp+4Fh+var_C0]
0x1800aa122  mov     rax, [rcx]
0x1800aa125  mov     rdx, [rsp+110h+ppstgOpen]
0x1800aa12a  mov     rax, [rax+28h]
0x1800aa12e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa133  mov     edi, eax
0x1800aa135  mov     rcx, [rsp+110h+ppstgOpen]
0x1800aa13a  mov     rax, [rcx]
0x1800aa13d  mov     rax, [rax+10h]
0x1800aa141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa146  mov     rcx, [rsp+110h+pplkbyt]
0x1800aa14b  jmp     loc_1800AA233
0x1800aa150  test    r12d, r12d
0x1800aa153  jz      loc_1800AA24A
0x1800aa159  mov     rax, [rsi]
0x1800aa15c  mov     rcx, rsi
0x1800aa15f  mov     rax, [rax+70h]
0x1800aa163  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa168  mov     edi, eax
0x1800aa16a  mov     edx, eax; dwBytes
0x1800aa16c  xor     ecx, ecx; uFlags
0x1800aa16e  call    cs:__imp_GlobalAlloc
0x1800aa174  mov     rbx, rax
0x1800aa177  test    rax, rax
0x1800aa17a  jz      loc_1800AA241
0x1800aa180  mov     rcx, rax; hMem
0x1800aa183  call    cs:__imp_GlobalLock
0x1800aa189  mov     rdx, rax
0x1800aa18c  test    rax, rax
0x1800aa18f  jz      loc_1800AA241
0x1800aa195  mov     rcx, [rsi]
0x1800aa198  mov     rax, [rcx+78h]
0x1800aa19c  mov     r8d, edi
0x1800aa19f  mov     rcx, rsi
0x1800aa1a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa1a7  mov     rcx, rbx; hMem
0x1800aa1aa  call    cs:__imp_GlobalUnlock
0x1800aa1b0  mov     [rsp+110h+ppstgOpen], 0
0x1800aa1b9  lea     r8, [rsp+110h+ppstgOpen]; pplkbyt
0x1800aa1be  mov     r12d, 1
0x1800aa1c4  mov     edx, r12d; fDeleteOnRelease
0x1800aa1c7  mov     rcx, rbx; hGlobal
0x1800aa1ca  call    cs:__imp_CreateILockBytesOnHGlobal
0x1800aa1d0  mov     edi, eax
0x1800aa1d2  xor     ebx, ebx
0x1800aa1d4  test    eax, eax
0x1800aa1d6  js      short loc_1800AA255
0x1800aa1d8  mov     [rsp+110h+pplkbyt], rbx
0x1800aa1dd  lea     rax, [rsp+110h+pplkbyt]
0x1800aa1e2  mov     [rsp+110h+var_E8], rax; ppstgOpen
0x1800aa1e7  mov     [rsp+110h+reserved], ebx; reserved
0x1800aa1eb  xor     r9d, r9d; snbExclude
0x1800aa1ee  xor     edx, edx; pstgPriority
0x1800aa1f0  lea     r8d, [r12+11h]; grfMode
0x1800aa1f5  mov     rcx, [rsp+110h+ppstgOpen]; plkbyt
0x1800aa1fa  call    cs:__imp_StgOpenStorageOnILockBytes
0x1800aa200  mov     edi, eax
0x1800aa202  test    eax, eax
0x1800aa204  js      short loc_1800AA22E
0x1800aa206  mov     rcx, [rbp+4Fh+var_C0]
0x1800aa20a  mov     rax, [rcx]
0x1800aa20d  mov     rdx, [rsp+110h+pplkbyt]
0x1800aa212  mov     rax, [rax+30h]
0x1800aa216  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa21b  mov     edi, eax
0x1800aa21d  mov     rcx, [rsp+110h+pplkbyt]
0x1800aa222  mov     rax, [rcx]
0x1800aa225  mov     rax, [rax+10h]
0x1800aa229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa22e  mov     rcx, [rsp+110h+ppstgOpen]
0x1800aa233  mov     rax, [rcx]
0x1800aa236  mov     rax, [rax+10h]
0x1800aa23a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa23f  jmp     short loc_1800AA255
0x1800aa241  mov     edi, 8007000Eh
0x1800aa246  xor     ebx, ebx
0x1800aa248  jmp     short loc_1800AA24F
0x1800aa24a  mov     edi, 8000FFFFh
0x1800aa24f  mov     r12d, 1
0x1800aa255  mov     rcx, [rbp+4Fh+var_C0]
0x1800aa259  mov     rax, [rcx]
0x1800aa25c  mov     rax, [rax+10h]
0x1800aa260  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa265  test    edi, edi
0x1800aa267  js      short loc_1800AA29F
0x1800aa269  test    r13d, r13d
0x1800aa26c  jnz     short loc_1800AA29B
0x1800aa26e  test    dword ptr [r15+0B8h], 20000h
0x1800aa279  jnz     short loc_1800AA29B
0x1800aa27b  mov     rcx, [r14]
0x1800aa27e  mov     rax, [rcx]
0x1800aa281  lea     rdx, [r15+128h]
0x1800aa288  mov     rax, [rax+18h]
0x1800aa28c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa291  mov     edi, eax
0x1800aa293  jmp     short loc_1800AA29B
0x1800aa295  mov     r12d, 1
0x1800aa29b  test    edi, edi
0x1800aa29d  jns     short loc_1800AA2C8
0x1800aa29f  mov     rcx, [r14]
0x1800aa2a2  test    rcx, rcx
0x1800aa2a5  jz      short loc_1800AA2C8
0x1800aa2a7  mov     rax, [rcx]
0x1800aa2aa  mov     edx, r12d
0x1800aa2ad  mov     rax, [rax+30h]
0x1800aa2b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa2b6  mov     rcx, [r14]
0x1800aa2b9  mov     rax, [rcx]
0x1800aa2bc  mov     rax, [rax+10h]
0x1800aa2c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa2c5  mov     [r14], rbx
0x1800aa2c8  mov     rcx, [rbp+4Fh+arg_0]
0x1800aa2cc  test    rcx, rcx
0x1800aa2cf  jz      short loc_1800AA2DD
0x1800aa2d1  mov     rax, [rcx]
0x1800aa2d4  mov     rax, [rax+10h]
0x1800aa2d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa2dd  test    r13d, r13d
0x1800aa2e0  jz      short loc_1800AA2E8
0x1800aa2e2  test    edi, edi
0x1800aa2e4  cmovns  edi, r12d
0x1800aa2e8  mov     eax, edi
0x1800aa2ea  add     rsp, 0D8h
0x1800aa2f1  pop     r15
0x1800aa2f3  pop     r14
0x1800aa2f5  pop     r13
0x1800aa2f7  pop     r12
  ... truncated ...
```
