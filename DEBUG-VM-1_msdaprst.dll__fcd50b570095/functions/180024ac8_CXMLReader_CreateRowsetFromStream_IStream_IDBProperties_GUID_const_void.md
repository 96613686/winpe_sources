# CXMLReader::CreateRowsetFromStream(IStream *,IDBProperties *,_GUID const &,void * *)

- ea: `0x180024ac8`
- end: `0x1800250e4`
- name: `?CreateRowsetFromStream@CXMLReader@@QEAAJPEAUIStream@@PEAUIDBProperties@@AEBU_GUID@@PEAPEAX@Z`
- size: `1564`
- prototype: `__int64 __usercall@<rax>(CXMLReader *__hidden this@<rcx>, struct IStream *@<rdx>, struct IDBProperties *@<r8>, const struct _GUID *@<r9>, void **)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800146d0`

## callees

- `0x180001d94`
- `0x18000266c`
- `0x180015fb4`
- `0x18001a6c8`
- `0x1800204bc`
- `0x180024ac8`
- `0x180026028`
- `0x1800263a4`
- `0x1800278b8`
- `0x180028fb0`
- `0x180028fe4`
- `0x18002cd54`
- `0x180030010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180024ddb`
- `ole32!CoCreateInstance` at `0x180024ddb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CXMLReader::CreateRowsetFromStream(
        CXMLReader *this,
        struct IStream *a2,
        struct IDBProperties *a3,
        const struct _GUID *a4,
        void **a5)
{
  unsigned int v7; // r12d
  struct IDataConvert **v8; // rcx
  int DataConvert; // eax
  int v10; // esi
  int v11; // eax
  int v12; // esi
  int v13; // eax
  unsigned int v14; // edx
  int v15; // esi
  unsigned __int8 *v16; // rax
  int v17; // eax
  int v18; // esi
  int v19; // eax
  int v20; // esi
  int v21; // eax
  int v22; // esi
  int Maps; // eax
  int v24; // esi
  _QWORD *v25; // r15
  HRESULT Instance; // eax
  int v27; // esi
  int v28; // eax
  int v29; // r14d
  int v30; // eax
  int v31; // r14d
  int v32; // eax
  int inited; // eax
  int v34; // r14d
  int v35; // eax
  int v36; // r14d
  unsigned int v37; // ebx
  int v39; // [rsp+30h] [rbp-58h]
  int v40; // [rsp+40h] [rbp-48h] BYREF
  _QWORD v41[8]; // [rsp+48h] [rbp-40h] BYREF

  v7 = 0;
  v39 = 0;
  v41[0] = 0;
  v8 = (struct IDataConvert **)((char *)this + 488);
  try
  {
    DataConvert = GetDataConvert(v8);
    v10 = DataConvert;
    if ( DataConvert < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_180048DD0[0] )
          bidTraceW(off_180048208[0], 294912, off_180048DD0[0], (unsigned int)DataConvert, 288);
      }
      ThrowHR(v10);
    }
    v11 = CCollectionList::Reserve((CXMLReader *)((char *)this + 160), 5u);
    v12 = v11;
    if ( v11 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180048DC8[0] )
        bidTraceW(off_180048208[0], 297984, off_180048DC8[0], (unsigned int)v11, 291);
      ThrowHR(v12);
    }
    v13 = CDynamicArray::Reserve((CXMLReader *)((char *)this + 416), 0xAu);
    v15 = v13;
    if ( v13 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180048DC0[0] )
        bidTraceW(off_180048208[0], 299008, off_180048DC0[0], (unsigned int)v13, 292);
      ThrowHR(v15);
    }
    v16 = MMMAlloc(0x20u, v14);
    if ( v16 )
    {
      *((_QWORD *)v16 + 2) = 0;
      *((_QWORD *)v16 + 3) = 0;
      *(_QWORD *)v16 = 0;
      *((_QWORD *)v16 + 1) = 0;
    }
    else
    {
      v16 = 0;
    }
    *((_QWORD *)this + 51) = v16;
    if ( !v16 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180048DB8[0] )
        bidTraceW(off_180048208[0], 305152, off_180048DB8[0], 2147942414LL, 298);
      ThrowHR(-2147024882);
    }
    v17 = CNodePool::Reserve((CNodePool *)v16, 0xFu);
    v18 = v17;
    if ( v17 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180048DB0[0] )
        bidTraceW(off_180048208[0], 308224, off_180048DB0[0], (unsigned int)v17, 301);
      ThrowHR(v18);
    }
    v19 = CCollectionList::Reserve((CXMLReader *)((char *)this + 24), 5u);
    v20 = v19;
    if ( v19 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180048DA8[0] )
        bidTraceW(off_180048208[0], 310272, off_180048DA8[0], (unsigned int)v19, 303);
      ThrowHR(v20);
    }
    v21 = CCollectionList::Reserve((CXMLReader *)((char *)this + 80), 5u);
    v22 = v21;
    if ( v21 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180048DA0[0] )
        bidTraceW(off_180048208[0], 311296, off_180048DA0[0], (unsigned int)v21, 304);
      ThrowHR(v22);
    }
    Maps = CXMLReader::LoadMaps(this);
    v24 = Maps;
    if ( Maps < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180048D98[0] )
        bidTraceW(off_180048208[0], 314368, off_180048D98[0], (unsigned int)Maps, 307);
      ThrowHR(v24);
    }
    v25 = (_QWORD *)((char *)this + 448);
    Instance = CoCreateInstance(
                 &GUID_f5078f31_c551_11d3_89b9_0000f81fe221,
                 0,
                 1u,
                 &GUID_d242361e_51a0_11d2_9caf_0060b0ec3d39,
                 (LPVOID *)this + 56);
    v27 = Instance;
    if ( Instance == -2147221164 || Instance == -2147467262 )
    {
      v7 = 138;
      v39 = 138;
    }
    if ( Instance < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180048D90[0] )
        bidTraceW(off_180048208[0], 338944, off_180048D90[0], (unsigned int)Instance, 331);
      ThrowHR(v27);
    }
    (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v25 + 224LL))(*v25, 983312);
    v28 = (*(__int64 (__fastcall **)(_QWORD, struct IStream *))(*(_QWORD *)*v25 + 128LL))(*v25, a2);
    v29 = v28;
    if ( v28 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180048D88[0] )
        bidTraceW(off_180048208[0], 343040, off_180048D88[0], (unsigned int)v28, 335);
      ThrowHR(v29);
    }
    (*(void (__fastcall **)(_QWORD, CXMLReader *))(*(_QWORD *)*v25 + 24LL))(*v25, this);
    v30 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v25 + 192LL))(*v25, 0xFFFFFFFFLL);
    v31 = v30;
    if ( v30 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180048D80[0] )
        bidTraceW(off_180048208[0], 347136, off_180048D80[0], (unsigned int)v30, 339);
      ThrowHR(v31);
    }
    v32 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v25 + 200LL))(*v25);
    if ( (v32 & 0xFFFFFFFA) == 0 && v32 != 4 )
    {
      inited = CXMLReader::InitRowsets(this, (char *)this + 24, a2, v41);
      v34 = inited;
      if ( inited < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180048D78[0] )
          bidTraceW(off_180048208[0], 360448, off_180048D78[0], (unsigned int)inited, 352);
        ThrowHR(v34);
      }
    }
    if ( !v41[0] )
    {
      if ( (bidGblFlags & 2) != 0 && off_180048D70[0] )
        bidTraceW(off_180048208[0], 367616, off_180048D70[0], 2147500037LL, 359);
      ThrowHR(-2147467259);
    }
    *(_QWORD *)(v41[0] + 536LL) = a3;
    ((void (__fastcall *)(struct IDBProperties *))a3->lpVtbl->AddRef)(a3);
    v35 = (**(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))v41[0])(v41[0], a4, a5);
    v36 = v35;
    if ( v35 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180048D68[0] )
        bidTraceW(off_180048208[0], 374784, off_180048D68[0], (unsigned int)v35, 366);
      ThrowHR(v36);
    }
    *((_QWORD *)this + 17) = (char *)this + 24;
  }
  catch ( long v40 )
  {
    v25 = (_QWORD *)((char *)this + 448);
    v27 = v40;
    v7 = v39;
  }
  catch ( ... )
  {
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(v41);
    return 2147500037LL;
  }
  if ( *v25 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v25 + 16LL))(*v25);
  v37 = Exit(v27, v7);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(v41);
  return v37;
}

```

## disassembly

```asm
0x180024ac8  mov     rax, rsp
0x180024acb  mov     [rax+20h], r9
0x180024acf  mov     [rax+18h], r8
0x180024ad3  mov     [rax+10h], rdx
0x180024ad7  mov     [rax+8], rcx
0x180024adb  push    rbx
0x180024adc  push    rsi
0x180024add  push    rdi
0x180024ade  push    r12
0x180024ae0  push    r13
0x180024ae2  push    r14
0x180024ae4  push    r15
0x180024ae6  sub     rsp, 50h
0x180024aea  mov     r14, rdx
0x180024aed  mov     rdi, rcx
0x180024af0  xor     ebx, ebx
0x180024af2  mov     r12d, ebx
0x180024af5  mov     [rsp+88h+var_58], ebx
0x180024af9  mov     [rax-40h], rbx
0x180024afd  add     rcx, 1E8h; struct IDataConvert **
0x180024b04  call    ?GetDataConvert@@YAJPEAPEAUIDataConvert@@@Z; GetDataConvert(IDataConvert * *)
0x180024b09  mov     esi, eax
0x180024b0b  test    eax, eax
0x180024b0d  jns     short loc_180024B4E
0x180024b0f  test    byte ptr cs:_bidGblFlags, 2
0x180024b16  jz      short loc_180024B47
0x180024b18  mov     rcx, cs:off_180048DD0; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x180024b1f  test    rcx, rcx
0x180024b22  jz      short loc_180024B47
0x180024b24  mov     dword ptr [rsp+88h+ppv], 120h
0x180024b2c  mov     r9d, eax
0x180024b2f  mov     r8, cs:off_180048DD0; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x180024b36  mov     edx, 48000h
0x180024b3b  mov     rcx, cs:off_180048208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180024b42  call    _bidTraceW
0x180024b47  mov     ecx, esi; int
0x180024b49  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180024b4e  lea     rcx, [rdi+0A0h]; this
0x180024b55  mov     r15d, 5
0x180024b5b  mov     edx, r15d; unsigned int
0x180024b5e  call    ?Reserve@CCollectionList@@QEAAJK@Z; CCollectionList::Reserve(ulong)
0x180024b63  mov     esi, eax
0x180024b65  test    eax, eax
0x180024b67  jns     short loc_180024BA8
0x180024b69  test    byte ptr cs:_bidGblFlags, 2
0x180024b70  jz      short loc_180024BA1
0x180024b72  mov     rcx, cs:off_180048DC8; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x180024b79  test    rcx, rcx
0x180024b7c  jz      short loc_180024BA1
0x180024b7e  mov     dword ptr [rsp+88h+ppv], 123h
0x180024b86  mov     r9d, eax
0x180024b89  mov     r8, cs:off_180048DC8; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x180024b90  mov     edx, 48C00h
0x180024b95  mov     rcx, cs:off_180048208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180024b9c  call    _bidTraceW
0x180024ba1  mov     ecx, esi; int
0x180024ba3  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180024ba8  lea     rcx, [rdi+1A0h]; this
0x180024baf  mov     edx, 0Ah; unsigned int
0x180024bb4  call    ?Reserve@CDynamicArray@@QEAAJK@Z; CDynamicArray::Reserve(ulong)
0x180024bb9  mov     esi, eax
0x180024bbb  test    eax, eax
0x180024bbd  jns     short loc_180024BFE
0x180024bbf  test    byte ptr cs:_bidGblFlags, 2
0x180024bc6  jz      short loc_180024BF7
0x180024bc8  mov     rcx, cs:off_180048DC0; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x180024bcf  test    rcx, rcx
0x180024bd2  jz      short loc_180024BF7
0x180024bd4  mov     dword ptr [rsp+88h+ppv], 124h
0x180024bdc  mov     r9d, eax
0x180024bdf  mov     r8, cs:off_180048DC0; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x180024be6  mov     edx, 49000h
0x180024beb  mov     rcx, cs:off_180048208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180024bf2  call    _bidTraceW
0x180024bf7  mov     ecx, esi; int
0x180024bf9  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180024bfe  mov     ecx, 20h ; ' '; unsigned int
0x180024c03  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x180024c08  mov     [rsp+88h+var_50], rax
0x180024c0d  test    rax, rax
0x180024c10  jz      short loc_180024C23
0x180024c12  mov     [rax+10h], rbx
0x180024c16  mov     [rax+18h], rbx
0x180024c1a  mov     [rax], rbx
0x180024c1d  mov     [rax+8], rbx
0x180024c21  jmp     short loc_180024C26
0x180024c23  mov     rax, rbx
0x180024c26  mov     [rdi+198h], rax
0x180024c2d  test    rax, rax
0x180024c30  jnz     short loc_180024C77
0x180024c32  test    byte ptr cs:_bidGblFlags, 2
0x180024c39  jz      short loc_180024C6D
0x180024c3b  mov     rax, cs:off_180048DB8; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x180024c42  test    rax, rax
0x180024c45  jz      short loc_180024C6D
0x180024c47  mov     dword ptr [rsp+88h+ppv], 12Ah
0x180024c4f  mov     r9d, 8007000Eh
0x180024c55  mov     r8, cs:off_180048DB8; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x180024c5c  mov     edx, 4A800h
0x180024c61  mov     rcx, cs:off_180048208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180024c68  call    _bidTraceW
0x180024c6d  mov     ecx, 8007000Eh; int
0x180024c72  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180024c77  mov     edx, 0Fh; unsigned int
0x180024c7c  mov     rcx, rax; this
0x180024c7f  call    ?Reserve@CNodePool@@QEAAJK@Z; CNodePool::Reserve(ulong)
0x180024c84  mov     esi, eax
0x180024c86  test    eax, eax
0x180024c88  jns     short loc_180024CC9
0x180024c8a  test    byte ptr cs:_bidGblFlags, 2
0x180024c91  jz      short loc_180024CC2
0x180024c93  mov     rcx, cs:off_180048DB0; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x180024c9a  test    rcx, rcx
0x180024c9d  jz      short loc_180024CC2
0x180024c9f  mov     dword ptr [rsp+88h+ppv], 12Dh
0x180024ca7  mov     r9d, eax
0x180024caa  mov     r8, cs:off_180048DB0; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x180024cb1  mov     edx, 4B400h
0x180024cb6  mov     rcx, cs:off_180048208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180024cbd  call    _bidTraceW
0x180024cc2  mov     ecx, esi; int
0x180024cc4  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180024cc9  lea     r13, [rdi+18h]
0x180024ccd  mov     edx, r15d; unsigned int
0x180024cd0  mov     rcx, r13; this
0x180024cd3  call    ?Reserve@CCollectionList@@QEAAJK@Z; CCollectionList::Reserve(ulong)
0x180024cd8  mov     esi, eax
0x180024cda  test    eax, eax
0x180024cdc  jns     short loc_180024D1D
0x180024cde  test    byte ptr cs:_bidGblFlags, 2
0x180024ce5  jz      short loc_180024D16
0x180024ce7  mov     rcx, cs:off_180048DA8; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x180024cee  test    rcx, rcx
0x180024cf1  jz      short loc_180024D16
0x180024cf3  mov     dword ptr [rsp+88h+ppv], 12Fh
0x180024cfb  mov     r9d, eax
0x180024cfe  mov     r8, cs:off_180048DA8; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x180024d05  mov     edx, 4BC00h
0x180024d0a  mov     rcx, cs:off_180048208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180024d11  call    _bidTraceW
0x180024d16  mov     ecx, esi; int
0x180024d18  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180024d1d  lea     rcx, [rdi+50h]; this
0x180024d21  mov     edx, r15d; unsigned int
0x180024d24  call    ?Reserve@CCollectionList@@QEAAJK@Z; CCollectionList::Reserve(ulong)
0x180024d29  mov     esi, eax
0x180024d2b  test    eax, eax
0x180024d2d  jns     short loc_180024D6E
0x180024d2f  test    byte ptr cs:_bidGblFlags, 2
0x180024d36  jz      short loc_180024D67
0x180024d38  mov     rcx, cs:off_180048DA0; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x180024d3f  test    rcx, rcx
0x180024d42  jz      short loc_180024D67
0x180024d44  mov     dword ptr [rsp+88h+ppv], 130h
0x180024d4c  mov     r9d, eax
0x180024d4f  mov     r8, cs:off_180048DA0; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x180024d56  mov     edx, 4C000h
0x180024d5b  mov     rcx, cs:off_180048208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180024d62  call    _bidTraceW
0x180024d67  mov     ecx, esi; int
0x180024d69  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180024d6e  mov     rcx, rdi; this
0x180024d71  call    ?LoadMaps@CXMLReader@@AEAAJXZ; CXMLReader::LoadMaps(void)
0x180024d76  mov     esi, eax
0x180024d78  test    eax, eax
0x180024d7a  jns     short loc_180024DBB
0x180024d7c  test    byte ptr cs:_bidGblFlags, 2
0x180024d83  jz      short loc_180024DB4
0x180024d85  mov     rcx, cs:off_180048D98; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x180024d8c  test    rcx, rcx
0x180024d8f  jz      short loc_180024DB4
0x180024d91  mov     dword ptr [rsp+88h+ppv], 133h
0x180024d99  mov     r9d, eax
0x180024d9c  mov     r8, cs:off_180048D98; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x180024da3  mov     edx, 4CC00h
0x180024da8  mov     rcx, cs:off_180048208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180024daf  call    _bidTraceW
0x180024db4  mov     ecx, esi; int
0x180024db6  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180024dbb  lea     r15, [rdi+1C0h]
0x180024dc2  mov     [rsp+88h+ppv], r15; ppv
0x180024dc7  lea     r9, _GUID_d242361e_51a0_11d2_9caf_0060b0ec3d39; riid
0x180024dce  xor     edx, edx; pUnkOuter
0x180024dd0  lea     r8d, [rdx+1]; dwClsContext
0x180024dd4  lea     rcx, _GUID_f5078f31_c551_11d3_89b9_0000f81fe221; rclsid
0x180024ddb  call    cs:__imp_CoCreateInstance
0x180024de1  mov     esi, eax
0x180024de3  cmp     eax, 80040154h
0x180024de8  jz      short loc_180024DF1
0x180024dea  cmp     eax, 80004002h
0x180024def  jnz     short loc_180024DFC
0x180024df1  mov     r12d, 8Ah
0x180024df7  mov     [rsp+88h+var_58], r12d
0x180024dfc  test    esi, esi
0x180024dfe  jns     short loc_180024E3F
0x180024e00  test    byte ptr cs:_bidGblFlags, 2
0x180024e07  jz      short loc_180024E38
0x180024e09  mov     rax, cs:off_180048D90; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x180024e10  test    rax, rax
0x180024e13  jz      short loc_180024E38
0x180024e15  mov     dword ptr [rsp+88h+ppv], 14Bh
0x180024e1d  mov     r9d, esi
0x180024e20  mov     r8, cs:off_180048D90; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x180024e27  mov     edx, 52C00h
0x180024e2c  mov     rcx, cs:off_180048208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180024e33  call    _bidTraceW
0x180024e38  mov     ecx, esi; int
0x180024e3a  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180024e3f  mov     rcx, [r15]
0x180024e42  mov     rax, [rcx]
0x180024e45  mov     edx, 0F0110h
0x180024e4a  mov     rax, [rax+0E0h]
0x180024e51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e56  mov     rcx, [r15]
0x180024e59  mov     rax, [rcx]
0x180024e5c  mov     rdx, r14
0x180024e5f  mov     rax, [rax+80h]
0x180024e66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e6b  mov     r14d, eax
0x180024e6e  test    eax, eax
0x180024e70  jns     short loc_180024EB2
0x180024e72  test    byte ptr cs:_bidGblFlags, 2
0x180024e79  jz      short loc_180024EAA
0x180024e7b  mov     rcx, cs:off_180048D88; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x180024e82  test    rcx, rcx
0x180024e85  jz      short loc_180024EAA
0x180024e87  mov     dword ptr [rsp+88h+ppv], 14Fh
0x180024e8f  mov     r9d, eax
0x180024e92  mov     r8, cs:off_180048D88; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x180024e99  mov     edx, 53C00h
0x180024e9e  mov     rcx, cs:off_180048208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180024ea5  call    _bidTraceW
0x180024eaa  mov     ecx, r14d; int
0x180024ead  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180024eb2  mov     rcx, [r15]
0x180024eb5  mov     rax, [rcx]
0x180024eb8  mov     rdx, rdi
0x180024ebb  mov     rax, [rax+18h]
0x180024ebf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ec4  mov     rcx, [r15]
0x180024ec7  mov     rax, [rcx]
0x180024eca  or      edx, 0FFFFFFFFh
0x180024ecd  mov     rax, [rax+0C0h]
0x180024ed4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ed9  mov     r14d, eax
0x180024edc  test    eax, eax
0x180024ede  jns     short loc_180024F20
0x180024ee0  test    byte ptr cs:_bidGblFlags, 2
0x180024ee7  jz      short loc_180024F18
0x180024ee9  mov     rcx, cs:off_180048D80; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x180024ef0  test    rcx, rcx
0x180024ef3  jz      short loc_180024F18
0x180024ef5  mov     dword ptr [rsp+88h+ppv], 153h
0x180024efd  mov     r9d, eax
0x180024f00  mov     r8, cs:off_180048D80; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x180024f07  mov     edx, 54C00h
0x180024f0c  mov     rcx, cs:off_180048208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180024f13  call    _bidTraceW
0x180024f18  mov     ecx, r14d; int
0x180024f1b  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180024f20  mov     rcx, [r15]
0x180024f23  mov     rax, [rcx]
0x180024f26  mov     rax, [rax+0C8h]
0x180024f2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f32  test    eax, 0FFFFFFFAh
0x180024f37  jnz     short loc_180024F9D
0x180024f39  cmp     eax, 4
0x180024f3c  jz      short loc_180024F9D
0x180024f3e  lea     r9, [rsp+88h+var_40]
0x180024f43  mov     r8, [rsp+88h+arg_8]
0x180024f4b  mov     rdx, r13
0x180024f4e  mov     rcx, rdi
0x180024f51  call    ?InitRowsets@CXMLReader@@AEAAJPEAVCScope@@PEAUIStream@@PEAPEAV?$CComObject@VCXMLRowset@@@ATL@@@Z; CXMLReader::InitRowsets(CScope *,IStream *,ATL::CComObject<CXMLRowset> * *)
0x180024f56  mov     r14d, eax
0x180024f59  test    eax, eax
0x180024f5b  jns     short loc_180024F9D
0x180024f5d  test    byte ptr cs:_bidGblFlags, 2
0x180024f64  jz      short loc_180024F95
0x180024f66  mov     rcx, cs:off_180048D78; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x180024f6d  test    rcx, rcx
0x180024f70  jz      short loc_180024F95
0x180024f72  mov     dword ptr [rsp+88h+ppv], 160h
0x180024f7a  mov     r9d, eax
0x180024f7d  mov     r8, cs:off_180048D78; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x180024f84  mov     edx, 58000h
0x180024f89  mov     rcx, cs:off_180048208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180024f90  call    _bidTraceW
0x180024f95  mov     ecx, r14d; int
0x180024f98  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180024f9d  mov     rax, [rsp+88h+var_40]
0x180024fa2  test    rax, rax
0x180024fa5  jnz     short loc_180024FF4
0x180024fa7  mov     [rsp+88h+var_58], 91h
0x180024faf  test    byte ptr cs:_bidGblFlags, 2
0x180024fb6  jz      short loc_180024FEA
0x180024fb8  mov     rax, cs:off_180048D70; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x180024fbf  test    rax, rax
0x180024fc2  jz      short loc_180024FEA
0x180024fc4  mov     dword ptr [rsp+88h+ppv], 167h
0x180024fcc  mov     r9d, 80004005h
  ... truncated ...
```
