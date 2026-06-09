# CRowset::~CRowset(void)

- ea: `0x18001fcdc`
- end: `0x18001feca`
- name: `??1CRowset@@UEAA@XZ`
- size: `494`
- prototype: `void __fastcall(CRowset *__hidden this)`
- caller_count: `3`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x18000a49c`
- `0x18001fed0`
- `0x180027f4c`

## callees

- `0x180001dd8`
- `0x1800026a0`
- `0x180011250`
- `0x180016d94`
- `0x18001fcdc`
- `0x180020880`
- `0x18002d828`
- `0x180030010`

## import_xrefs

- `KERNEL32!VirtualFree` at `0x18001fdd0`
- `KERNEL32!VirtualFree` at `0x18001fdd0`
- `ole32!CoTaskMemFree` at `0x18001fdb6`
- `ole32!CoTaskMemFree` at `0x18001fdb6`
- `MSDART!MPDeleteCriticalSection` at `0x18001fe5a`
- `MSDART!MPDeleteCriticalSection` at `0x18001fe5a`
- `MSDART!MPDeleteCriticalSection` at `0x18001fec3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CRowset::~CRowset(CRowset *this)
{
  __int64 v2; // rcx
  unsigned __int8 *v3; // rcx
  unsigned __int8 *v4; // rcx
  unsigned __int8 *v5; // rcx
  unsigned __int8 *v6; // rcx
  unsigned __int8 *v7; // rcx
  unsigned __int8 *v8; // rcx
  unsigned __int8 *v9; // rcx
  unsigned __int8 *v10; // rdi
  void *v11; // rcx
  __int64 v12; // rax
  unsigned int v13; // esi
  unsigned int i; // edi
  unsigned __int8 *v15; // rdi
  unsigned __int8 *v16; // [rsp+40h] [rbp+8h] BYREF

  *(_QWORD *)this = &CRowset::`vftable';
  v2 = *((_QWORD *)this + 49);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  ReleaseDataConvert(*((struct IDataConvert **)this + 66));
  v3 = (unsigned __int8 *)*((_QWORD *)this + 21);
  if ( v3 )
    MMMFree(v3);
  v4 = (unsigned __int8 *)*((_QWORD *)this + 20);
  if ( v4 )
    MMMFree(v4);
  v5 = (unsigned __int8 *)*((_QWORD *)this + 22);
  if ( v5 )
    MMMFree(v5);
  v6 = (unsigned __int8 *)*((_QWORD *)this + 23);
  if ( v6 )
    MMMFree(v6);
  v7 = (unsigned __int8 *)*((_QWORD *)this + 35);
  if ( v7 )
    MMMFree(v7);
  v8 = (unsigned __int8 *)*((_QWORD *)this + 36);
  if ( v8 )
    MMMFree(v8);
  v9 = (unsigned __int8 *)*((_QWORD *)this + 37);
  if ( v9 )
    MMMFree(v9);
  v10 = (unsigned __int8 *)*((_QWORD *)this + 26);
  if ( v10 )
  {
    CExtBuffer::~CExtBuffer(*((CExtBuffer **)this + 26));
    MMMFree(v10);
  }
  CoTaskMemFree(*((LPVOID *)this + 47));
  v11 = (void *)*((_QWORD *)this + 25);
  if ( v11 )
    VirtualFree(v11, 0, 0x8000u);
  v12 = *((_QWORD *)this + 24);
  if ( v12 )
  {
    v16 = 0;
    v13 = *(_DWORD *)(v12 + 4);
    for ( i = 1; i <= v13; ++i )
    {
      CExtBuffer::GetItemOfExtBuffer(*((CExtBuffer **)this + 24), i, &v16);
      if ( v16 )
        MMMFree(v16);
    }
    v15 = (unsigned __int8 *)*((_QWORD *)this + 24);
    if ( v15 )
    {
      CExtBuffer::~CExtBuffer(*((CExtBuffer **)this + 24));
      MMMFree(v15);
    }
  }
  CProps::~CProps((CRowset *)((char *)this + 400));
  CMetaData::~CMetaData((CRowset *)((char *)this + 304));
  MPDeleteCriticalSection((char *)this + 128);
  *((_QWORD *)this + 14) = &CRowset::CNotUpdt_BidGeneric::`vftable';
  if ( *((_DWORD *)this + 30) && bidID != -1 )
    ((void (__fastcall *)(__int64, wchar_t *, __int64, _QWORD, _QWORD))off_180042128)(
      bidID,
      `CRowset::CNotUpdt_BidGeneric::BidRecycleID'::`7'::_bidPtrSA_053_221[0],
      7,
      *((int *)this + 30),
      0);
  *((_DWORD *)this + 30) = 0;
  MPDeleteCriticalSection((char *)this + 16);
}

```

## disassembly

```asm
0x18001fcdc  mov     [rsp+arg_8], rbx
0x18001fce1  mov     [rsp+arg_10], rsi
0x18001fce6  push    rdi
0x18001fce7  sub     rsp, 30h
0x18001fceb  mov     rbx, rcx
0x18001fcee  lea     rax, ??_7CRowset@@6B@; const CRowset::`vftable'
0x18001fcf5  mov     [rcx], rax
0x18001fcf8  mov     rcx, [rcx+188h]
0x18001fcff  test    rcx, rcx
0x18001fd02  jz      short loc_18001FD10
0x18001fd04  mov     rax, [rcx]
0x18001fd07  mov     rax, [rax+10h]
0x18001fd0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd10  mov     rcx, [rbx+210h]; struct IDataConvert *
0x18001fd17  call    ?ReleaseDataConvert@@YAXPEAUIDataConvert@@@Z; ReleaseDataConvert(IDataConvert *)
0x18001fd1c  mov     rcx, [rbx+0A8h]; unsigned __int8 *
0x18001fd23  test    rcx, rcx
0x18001fd26  jz      short loc_18001FD2D
0x18001fd28  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x18001fd2d  mov     rcx, [rbx+0A0h]; unsigned __int8 *
0x18001fd34  test    rcx, rcx
0x18001fd37  jz      short loc_18001FD3E
0x18001fd39  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x18001fd3e  mov     rcx, [rbx+0B0h]; unsigned __int8 *
0x18001fd45  test    rcx, rcx
0x18001fd48  jz      short loc_18001FD4F
0x18001fd4a  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x18001fd4f  mov     rcx, [rbx+0B8h]; unsigned __int8 *
0x18001fd56  test    rcx, rcx
0x18001fd59  jz      short loc_18001FD60
0x18001fd5b  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x18001fd60  mov     rcx, [rbx+118h]; unsigned __int8 *
0x18001fd67  test    rcx, rcx
0x18001fd6a  jz      short loc_18001FD71
0x18001fd6c  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x18001fd71  mov     rcx, [rbx+120h]; unsigned __int8 *
0x18001fd78  test    rcx, rcx
0x18001fd7b  jz      short loc_18001FD82
0x18001fd7d  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x18001fd82  mov     rcx, [rbx+128h]; unsigned __int8 *
0x18001fd89  test    rcx, rcx
0x18001fd8c  jz      short loc_18001FD93
0x18001fd8e  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x18001fd93  mov     rdi, [rbx+0D0h]
0x18001fd9a  test    rdi, rdi
0x18001fd9d  jz      short loc_18001FDAF
0x18001fd9f  mov     rcx, rdi; this
0x18001fda2  call    ??1CExtBuffer@@QEAA@XZ; CExtBuffer::~CExtBuffer(void)
0x18001fda7  mov     rcx, rdi; unsigned __int8 *
0x18001fdaa  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x18001fdaf  mov     rcx, [rbx+178h]; pv
0x18001fdb6  call    cs:__imp_CoTaskMemFree
0x18001fdbc  mov     rcx, [rbx+0C8h]; lpAddress
0x18001fdc3  test    rcx, rcx
0x18001fdc6  jz      short loc_18001FDD6
0x18001fdc8  xor     edx, edx; dwSize
0x18001fdca  mov     r8d, 8000h; dwFreeType
0x18001fdd0  call    cs:__imp_VirtualFree
0x18001fdd6  mov     rax, [rbx+0C0h]
0x18001fddd  test    rax, rax
0x18001fde0  jz      short loc_18001FE3B
0x18001fde2  mov     [rsp+38h+arg_0], 0
0x18001fdeb  mov     esi, [rax+4]
0x18001fdee  mov     edi, 1
0x18001fdf3  cmp     esi, edi
0x18001fdf5  jb      short loc_18001FE1F
0x18001fdf7  lea     r8, [rsp+38h+arg_0]; void *
0x18001fdfc  mov     edx, edi; unsigned int
0x18001fdfe  mov     rcx, [rbx+0C0h]; this
0x18001fe05  call    ?GetItemOfExtBuffer@CExtBuffer@@QEAAJKPEAX@Z; CExtBuffer::GetItemOfExtBuffer(ulong,void *)
0x18001fe0a  mov     rcx, [rsp+38h+arg_0]; unsigned __int8 *
0x18001fe0f  test    rcx, rcx
0x18001fe12  jz      short loc_18001FE19
0x18001fe14  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x18001fe19  inc     edi
0x18001fe1b  cmp     edi, esi
0x18001fe1d  jbe     short loc_18001FDF7
0x18001fe1f  mov     rdi, [rbx+0C0h]
0x18001fe26  test    rdi, rdi
0x18001fe29  jz      short loc_18001FE3B
0x18001fe2b  mov     rcx, rdi; this
0x18001fe2e  call    ??1CExtBuffer@@QEAA@XZ; CExtBuffer::~CExtBuffer(void)
0x18001fe33  mov     rcx, rdi; unsigned __int8 *
0x18001fe36  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x18001fe3b  lea     rcx, [rbx+190h]; this
0x18001fe42  call    ??1CProps@@UEAA@XZ; CProps::~CProps(void)
0x18001fe47  lea     rcx, [rbx+130h]; this
0x18001fe4e  call    ??1CMetaData@@QEAA@XZ; CMetaData::~CMetaData(void)
0x18001fe53  lea     rcx, [rbx+80h]
0x18001fe5a  call    cs:__imp_MPDeleteCriticalSection
0x18001fe60  nop
0x18001fe61  lea     rax, ??_7CNotUpdt_BidGeneric@CRowset@@6B@; const CRowset::CNotUpdt_BidGeneric::`vftable'
0x18001fe68  mov     [rbx+70h], rax
0x18001fe6c  cmp     dword ptr [rbx+78h], 0
0x18001fe70  jz      short loc_18001FEA9
0x18001fe72  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x18001fe7a  jz      short loc_18001FEA9
0x18001fe7c  mov     rax, cs:off_180042128
0x18001fe83  movsxd  r9, dword ptr [rbx+78h]
0x18001fe87  mov     [rsp+38h+var_18], 0
0x18001fe90  mov     r8d, 7
0x18001fe96  mov     rdx, cs:?_bidPtrSA_053_221@?6??BidRecycleID@CNotUpdt_BidGeneric@CRowset@@AEAAHXZ@4REBGEB; ushort const * const `CRowset::CNotUpdt_BidGeneric::BidRecycleID(void)'::`7'::_bidPtrSA_053_221
0x18001fe9d  mov     rcx, cs:_bidID
0x18001fea4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fea9  mov     dword ptr [rbx+78h], 0
0x18001feb0  lea     rcx, [rbx+10h]
0x18001feb4  mov     rbx, [rsp+38h+arg_8]
0x18001feb9  mov     rsi, [rsp+38h+arg_10]
0x18001febe  add     rsp, 30h
0x18001fec2  pop     rdi
0x18001fec3  jmp     cs:__imp_MPDeleteCriticalSection
```
