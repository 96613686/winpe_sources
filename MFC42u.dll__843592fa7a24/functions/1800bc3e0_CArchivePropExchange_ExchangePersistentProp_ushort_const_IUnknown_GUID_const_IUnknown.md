# CArchivePropExchange::ExchangePersistentProp(ushort const *,IUnknown * *,_GUID const &,IUnknown *)

- ea: `0x1800bc3e0`
- end: `0x1800bc728`
- name: `?ExchangePersistentProp@CArchivePropExchange@@UEAAHPEBGPEAPEAUIUnknown@@AEBU_GUID@@PEAU2@@Z`
- size: `840`
- prototype: `int(CArchivePropExchange *__hidden this, const unsigned __int16 *, struct IUnknown **, const struct _GUID *, struct IUnknown *)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000a150`
- `0x180031340`
- `0x1800316a0`
- `0x180036a10`
- `0x180036a60`
- `0x180036ab0`
- `0x180036c00`
- `0x1800371e0`
- `0x1800bc3e0`
- `0x1800bd234`
- `0x1800bd2ec`
- `0x1800d1f6e`
- `0x1800d1fe0`
- `0x1800d7010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800bc541`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800bc55d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800bc541`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800bc55d`
- `OLEAUT32!__imp_OleLoadPicture` at `0x1800bc605`
- `OLEAUT32!__imp_OleLoadPicture` at `0x1800bc605`
- `OLE32!OleSaveToStream` at `0x1800bc6ca`
- `OLE32!OleSaveToStream` at `0x1800bc6ca`
- `api-ms-win-core-com-l2-1-1!ReadClassStm` at `0x1800bc521`
- `api-ms-win-core-com-l2-1-1!ReadClassStm` at `0x1800bc521`

## pseudocode

```c
__int64 __fastcall CArchivePropExchange::ExchangePersistentProp(
        CArchivePropExchange *this,
        const unsigned __int16 *a2,
        struct IUnknown **a3,
        const struct _GUID *a4,
        struct IUnknown *a5)
{
  bool v5; // zf
  __int64 v9; // rcx
  __int64 v10; // rcx
  IStream *v11; // rbx
  IStream v12; // rax
  struct IUnknown *v13; // rcx
  int v14; // ebx
  int IsSameUnknownObject; // eax
  __int64 v16; // rdx
  __int64 v17; // rcx
  struct IUnknown *v18; // rcx
  IStream *ArchiveStream; // rax
  BOOL v20; // ebx
  _BYTE v22[8]; // [rsp+30h] [rbp-40h] BYREF
  LPPERSISTSTREAM pPStm; // [rsp+38h] [rbp-38h] BYREF
  _QWORD v24[2]; // [rsp+40h] [rbp-30h] BYREF
  CLSID Buf1; // [rsp+50h] [rbp-20h] BYREF

  v5 = *((_DWORD *)this + 2) == 0;
  v24[0] = &CArchiveStream::`vftable';
  v24[1] = *((_QWORD *)this + 3);
  if ( v5 )
  {
    IsSameUnknownObject = _AfxIsSameUnknownObject(a4, *a3, a5);
    v17 = *((_QWORD *)this + 3);
    if ( IsSameUnknownObject )
    {
      LOBYTE(v16) = -1;
      CArchive::operator<<(v17, v16);
      return 1;
    }
    CArchive::operator<<(v17, 0);
    v18 = *a3;
    if ( *a3 )
    {
      pPStm = 0;
      if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, LPPERSISTSTREAM *))v18->lpVtbl->QueryInterface)(
             v18,
             &IID_IPersistStream,
             &pPStm) >= 0
        || ((__int64 (__fastcall *)(_QWORD, GUID *, LPPERSISTSTREAM *))(*a3)->lpVtbl->QueryInterface)(
             *a3,
             &IID_IPersistStreamInit,
             &pPStm) >= 0 )
      {
        ArchiveStream = _AfxGetArchiveStream(*((struct CArchive **)this + 3), (struct CArchiveStream *)v24);
        v20 = OleSaveToStream(pPStm, ArchiveStream) >= 0;
        ((void (__fastcall *)(LPPERSISTSTREAM))pPStm->lpVtbl->Release)(pPStm);
        if ( v20 )
          return 1;
      }
    }
    else
    {
      CArchive::Write(*((CArchive **)this + 3), &GUID_NULL, 0x10u);
    }
LABEL_26:
    AfxThrowArchiveException(1, 0);
  }
  _AfxRelease(a3);
  *a3 = 0;
  v9 = *((_QWORD *)this + 3);
  v22[0] = 0;
  CArchive::operator>>(v9, v22);
  if ( v22[0] == 0xFF )
  {
    if ( !a5
      || ((__int64 (__fastcall *)(struct IUnknown *, const struct _GUID *, struct IUnknown **))a5->lpVtbl->QueryInterface)(
           a5,
           a4,
           a3) >= 0 )
    {
      return 1;
    }
    goto LABEL_26;
  }
  v10 = *((_QWORD *)this + 3);
  Buf1 = 0;
  CArchive::operator>>(v10, &Buf1);
  CArchive::operator>>(*((_QWORD *)this + 3), &Buf1.Data2);
  CArchive::operator>>(*((_QWORD *)this + 3), &Buf1.Data3);
  CArchive::Read(*((CArchive **)this + 3), Buf1.Data4, 8u);
  if ( !memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
    return 1;
  v11 = _AfxGetArchiveStream(*((struct CArchive **)this + 3), (struct CArchiveStream *)v24);
  if ( !memcmp_0(&Buf1, &CLSID_StdPicture, 0x10u) || !memcmp_0(&Buf1, &_afx_CLSID_StdPicture2_V1, 0x10u) )
  {
    if ( OleLoadPicture(v11, 0, 0, a4, (LPVOID *)a3) >= 0 )
      return 1;
    goto LABEL_26;
  }
  v12.lpVtbl = v11->lpVtbl;
  pPStm = (LPPERSISTSTREAM)-16LL;
  ((void (__fastcall *)(IStream *, __int64, __int64, _QWORD))v12.lpVtbl->Seek)(v11, -16, 1, 0);
  if ( ReadClassStm(v11, &Buf1) < 0
    || CoCreateInstance(&Buf1, 0, 0x15u, a4, (LPVOID *)a3) < 0 && CoCreateInstance(&Buf1, 0, 5u, a4, (LPVOID *)a3) < 0 )
  {
    goto LABEL_26;
  }
  v13 = *a3;
  pPStm = 0;
  if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, LPPERSISTSTREAM *))v13->lpVtbl->QueryInterface)(
         v13,
         &IID_IPersistStream,
         &pPStm) < 0
    && ((__int64 (__fastcall *)(_QWORD, GUID *, LPPERSISTSTREAM *))(*a3)->lpVtbl->QueryInterface)(
         *a3,
         &IID_IPersistStreamInit,
         &pPStm) < 0
    || (v14 = ((__int64 (__fastcall *)(LPPERSISTSTREAM, IStream *))pPStm->lpVtbl->Load)(pPStm, v11),
        ((void (__fastcall *)(LPPERSISTSTREAM))pPStm->lpVtbl->Release)(pPStm),
        v14 < 0) )
  {
    ((void (__fastcall *)(_QWORD))(*a3)->lpVtbl->Release)(*a3);
    *a3 = 0;
    goto LABEL_26;
  }
  return 1;
}

```

## disassembly

```asm
0x1800bc3e0  push    rbp
0x1800bc3e2  push    rbx
0x1800bc3e3  push    rsi
0x1800bc3e4  push    rdi
0x1800bc3e5  push    r14
0x1800bc3e7  mov     rbp, rsp
0x1800bc3ea  sub     rsp, 70h
0x1800bc3ee  mov     rax, cs:__security_cookie
0x1800bc3f5  xor     rax, rsp
0x1800bc3f8  mov     [rbp+var_10], rax
0x1800bc3fc  cmp     dword ptr [rcx+8], 0
0x1800bc400  lea     rax, ??_7CArchiveStream@@6B@; const CArchiveStream::`vftable'
0x1800bc407  mov     r14, [rbp+arg_20]
0x1800bc40b  mov     rsi, r9
0x1800bc40e  mov     [rbp+var_30], rax
0x1800bc412  mov     rdi, r8
0x1800bc415  mov     rax, [rcx+18h]
0x1800bc419  mov     rbx, rcx
0x1800bc41c  mov     [rbp+var_28], rax
0x1800bc420  jz      loc_1800BC642
0x1800bc426  mov     rcx, r8; struct IUnknown **
0x1800bc429  call    ?_AfxRelease@@YAKPEAPEAUIUnknown@@@Z; _AfxRelease(IUnknown * *)
0x1800bc42e  mov     qword ptr [rdi], 0
0x1800bc435  lea     rdx, [rbp+var_40]
0x1800bc439  mov     rcx, [rbx+18h]
0x1800bc43d  mov     [rbp+var_40], 0
0x1800bc441  call    ??5CArchive@@QEAAAEAV0@AEAE@Z; CArchive::operator>>(uchar &)
0x1800bc446  cmp     [rbp+var_40], 0FFh
0x1800bc44a  jz      loc_1800BC618
0x1800bc450  mov     rcx, [rbx+18h]
0x1800bc454  lea     rdx, [rbp+Buf1]
0x1800bc458  xorps   xmm0, xmm0
0x1800bc45b  movups  [rbp+Buf1], xmm0
0x1800bc45f  call    ??5CArchive@@QEAAAEAV0@AEAM@Z; CArchive::operator>>(float &)
0x1800bc464  mov     rcx, [rbx+18h]
0x1800bc468  lea     rdx, [rbp+Buf1+4]
0x1800bc46c  call    ??5CArchive@@QEAAAEAV0@AEAG@Z; CArchive::operator>>(ushort &)
0x1800bc471  mov     rcx, [rbx+18h]
0x1800bc475  lea     rdx, [rbp+Buf1+6]
0x1800bc479  call    ??5CArchive@@QEAAAEAV0@AEAG@Z; CArchive::operator>>(ushort &)
0x1800bc47e  mov     rcx, [rbx+18h]; this
0x1800bc482  lea     rdx, [rbp+Buf1+8]; void *
0x1800bc486  mov     r8d, 8; unsigned int
0x1800bc48c  call    ?Read@CArchive@@QEAAIPEAXI@Z; CArchive::Read(void *,uint)
0x1800bc491  mov     r14d, 10h
0x1800bc497  lea     rdx, GUID_NULL; Buf2
0x1800bc49e  mov     r8d, r14d; Size
0x1800bc4a1  lea     rcx, [rbp+Buf1]; Buf1
0x1800bc4a5  call    memcmp_0
0x1800bc4aa  test    eax, eax
0x1800bc4ac  jz      loc_1800BC6EB
0x1800bc4b2  mov     rcx, [rbx+18h]; struct CArchive *
0x1800bc4b6  lea     rdx, [rbp+var_30]; struct CArchiveStream *
0x1800bc4ba  call    ?_AfxGetArchiveStream@@YAPEAUIStream@@AEAVCArchive@@AEAVCArchiveStream@@@Z; _AfxGetArchiveStream(CArchive &,CArchiveStream &)
0x1800bc4bf  mov     r8d, r14d; Size
0x1800bc4c2  lea     rdx, CLSID_StdPicture; Buf2
0x1800bc4c9  lea     rcx, [rbp+Buf1]; Buf1
0x1800bc4cd  mov     rbx, rax
0x1800bc4d0  call    memcmp_0
0x1800bc4d5  test    eax, eax
0x1800bc4d7  jz      loc_1800BC5F5
0x1800bc4dd  mov     r8d, r14d; Size
0x1800bc4e0  lea     rdx, ?_afx_CLSID_StdPicture2_V1@@3U_GUID@@B; Buf2
0x1800bc4e7  lea     rcx, [rbp+Buf1]; Buf1
0x1800bc4eb  call    memcmp_0
0x1800bc4f0  test    eax, eax
0x1800bc4f2  jz      loc_1800BC5F5
0x1800bc4f8  mov     rax, [rbx]
0x1800bc4fb  lea     r8d, [r14-0Fh]
0x1800bc4ff  mov     [rbp+pPStm], 0FFFFFFFFFFFFFFF0h
0x1800bc507  xor     r9d, r9d
0x1800bc50a  mov     rdx, [rbp+pPStm]
0x1800bc50e  mov     rcx, rbx
0x1800bc511  mov     rax, [rax+28h]
0x1800bc515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc51a  lea     rdx, [rbp+Buf1]; pclsid
0x1800bc51e  mov     rcx, rbx; pStm
0x1800bc521  call    cs:__imp_ReadClassStm
0x1800bc527  test    eax, eax
0x1800bc529  js      loc_1800BC71D
0x1800bc52f  mov     r9, rsi; riid
0x1800bc532  mov     [rsp+70h+ppv], rdi; ppv
0x1800bc537  xor     edx, edx; pUnkOuter
0x1800bc539  lea     r8d, [r14+5]; dwClsContext
0x1800bc53d  lea     rcx, [rbp+Buf1]; rclsid
0x1800bc541  call    cs:__imp_CoCreateInstance
0x1800bc547  test    eax, eax
0x1800bc549  jns     short loc_1800BC56B
0x1800bc54b  mov     r9, rsi; riid
0x1800bc54e  mov     [rsp+70h+ppv], rdi; ppv
0x1800bc553  xor     edx, edx; pUnkOuter
0x1800bc555  lea     r8d, [r14-0Bh]; dwClsContext
0x1800bc559  lea     rcx, [rbp+Buf1]; rclsid
0x1800bc55d  call    cs:__imp_CoCreateInstance
0x1800bc563  test    eax, eax
0x1800bc565  js      loc_1800BC71D
0x1800bc56b  mov     rcx, [rdi]
0x1800bc56e  lea     r8, [rbp+pPStm]
0x1800bc572  mov     [rbp+pPStm], 0
0x1800bc57a  lea     rdx, IID_IPersistStream
0x1800bc581  mov     rax, [rcx]
0x1800bc584  mov     rax, [rax]
0x1800bc587  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc58c  test    eax, eax
0x1800bc58e  jns     short loc_1800BC5AD
0x1800bc590  mov     rcx, [rdi]
0x1800bc593  lea     r8, [rbp+pPStm]
0x1800bc597  lea     rdx, IID_IPersistStreamInit
0x1800bc59e  mov     rax, [rcx]
0x1800bc5a1  mov     rax, [rax]
0x1800bc5a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc5a9  test    eax, eax
0x1800bc5ab  js      short loc_1800BC5DA
0x1800bc5ad  mov     rcx, [rbp+pPStm]
0x1800bc5b1  mov     rdx, rbx
0x1800bc5b4  mov     rax, [rcx]
0x1800bc5b7  mov     rax, [rax+28h]
0x1800bc5bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc5c0  mov     rcx, [rbp+pPStm]
0x1800bc5c4  mov     ebx, eax
0x1800bc5c6  mov     rax, [rcx]
0x1800bc5c9  mov     rax, [rax+10h]
0x1800bc5cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc5d2  test    ebx, ebx
0x1800bc5d4  jns     loc_1800BC6EB
0x1800bc5da  mov     rcx, [rdi]
0x1800bc5dd  mov     rax, [rcx]
0x1800bc5e0  mov     rax, [rax+10h]
0x1800bc5e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc5e9  mov     qword ptr [rdi], 0
0x1800bc5f0  jmp     loc_1800BC71D
0x1800bc5f5  mov     r9, rsi; riid
0x1800bc5f8  mov     [rsp+70h+ppv], rdi; lplpvObj
0x1800bc5fd  xor     r8d, r8d; fRunmode
0x1800bc600  xor     edx, edx; lSize
0x1800bc602  mov     rcx, rbx; lpstream
0x1800bc605  call    cs:__imp_OleLoadPicture
0x1800bc60b  test    eax, eax
0x1800bc60d  js      loc_1800BC71D
0x1800bc613  jmp     loc_1800BC6EB
0x1800bc618  test    r14, r14
0x1800bc61b  jz      loc_1800BC6EB
0x1800bc621  mov     rax, [r14]
0x1800bc624  mov     r8, rdi
0x1800bc627  mov     rdx, rsi
0x1800bc62a  mov     rcx, r14
0x1800bc62d  mov     rax, [rax]
0x1800bc630  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc635  test    eax, eax
0x1800bc637  jns     loc_1800BC6EB
0x1800bc63d  jmp     loc_1800BC71D
0x1800bc642  mov     rdx, [rdi]; struct IUnknown *
0x1800bc645  mov     r8, r14; struct IUnknown *
0x1800bc648  mov     rcx, rsi; struct _GUID *
0x1800bc64b  call    ?_AfxIsSameUnknownObject@@YAHAEBU_GUID@@PEAUIUnknown@@1@Z; _AfxIsSameUnknownObject(_GUID const &,IUnknown *,IUnknown *)
0x1800bc650  mov     rcx, [rbx+18h]
0x1800bc654  test    eax, eax
0x1800bc656  jz      short loc_1800BC664
0x1800bc658  mov     dl, 0FFh
0x1800bc65a  call    ??6CArchive@@QEAAAEAV0@E@Z; CArchive::operator<<(uchar)
0x1800bc65f  jmp     loc_1800BC6EB
0x1800bc664  xor     edx, edx
0x1800bc666  call    ??6CArchive@@QEAAAEAV0@E@Z; CArchive::operator<<(uchar)
0x1800bc66b  mov     rcx, [rdi]
0x1800bc66e  test    rcx, rcx
0x1800bc671  jz      loc_1800BC707
0x1800bc677  mov     [rbp+pPStm], 0
0x1800bc67f  lea     r8, [rbp+pPStm]
0x1800bc683  mov     rax, [rcx]
0x1800bc686  lea     rdx, IID_IPersistStream
0x1800bc68d  mov     rax, [rax]
0x1800bc690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc695  test    eax, eax
0x1800bc697  jns     short loc_1800BC6B6
0x1800bc699  mov     rcx, [rdi]
0x1800bc69c  lea     r8, [rbp+pPStm]
0x1800bc6a0  lea     rdx, IID_IPersistStreamInit
0x1800bc6a7  mov     rax, [rcx]
0x1800bc6aa  mov     rax, [rax]
0x1800bc6ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc6b2  test    eax, eax
0x1800bc6b4  js      short loc_1800BC71D
0x1800bc6b6  mov     rcx, [rbx+18h]; struct CArchive *
0x1800bc6ba  lea     rdx, [rbp+var_30]; struct CArchiveStream *
0x1800bc6be  call    ?_AfxGetArchiveStream@@YAPEAUIStream@@AEAVCArchive@@AEAVCArchiveStream@@@Z; _AfxGetArchiveStream(CArchive &,CArchiveStream &)
0x1800bc6c3  mov     rcx, [rbp+pPStm]; pPStm
0x1800bc6c7  mov     rdx, rax; pStm
0x1800bc6ca  call    cs:__imp_OleSaveToStream
0x1800bc6d0  mov     rcx, [rbp+pPStm]
0x1800bc6d4  mov     ebx, eax
0x1800bc6d6  not     ebx
0x1800bc6d8  shr     ebx, 1Fh
0x1800bc6db  mov     rdx, [rcx]
0x1800bc6de  mov     rax, [rdx+10h]
0x1800bc6e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc6e7  test    ebx, ebx
0x1800bc6e9  jz      short loc_1800BC71D
0x1800bc6eb  mov     eax, 1
0x1800bc6f0  mov     rcx, [rbp+var_10]
0x1800bc6f4  xor     rcx, rsp; StackCookie
0x1800bc6f7  call    __security_check_cookie
0x1800bc6fc  add     rsp, 70h
0x1800bc700  pop     r14
0x1800bc702  pop     rdi
0x1800bc703  pop     rsi
0x1800bc704  pop     rbx
0x1800bc705  pop     rbp
0x1800bc706  retn
0x1800bc707  mov     rcx, [rbx+18h]; this
0x1800bc70b  lea     rdx, GUID_NULL; void *
0x1800bc712  mov     r8d, 10h; unsigned int
0x1800bc718  call    ?Write@CArchive@@QEAAXPEBXI@Z; CArchive::Write(void const *,uint)
0x1800bc71d  xor     edx, edx; unsigned __int16 *
0x1800bc71f  lea     ecx, [rdx+1]; int
0x1800bc722  call    ?AfxThrowArchiveException@@YAXHPEBG@Z; AfxThrowArchiveException(int,ushort const *)
```
