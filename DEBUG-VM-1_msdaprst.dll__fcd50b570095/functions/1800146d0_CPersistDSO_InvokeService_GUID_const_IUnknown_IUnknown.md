# CPersistDSO::InvokeService(_GUID const &,IUnknown *,IUnknown * *)

- ea: `0x1800146d0`
- end: `0x180014cc5`
- name: `?InvokeService@CPersistDSO@@UEAAJAEBU_GUID@@PEAUIUnknown@@PEAPEAU3@@Z`
- size: `1525`
- prototype: `int(CPersistDSO *__hidden this, const struct _GUID *, struct IUnknown *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800022f8`
- `0x18000266c`
- `0x18000b738`
- `0x180013d20`
- `0x180013dec`
- `0x180013ea4`
- `0x1800146d0`
- `0x180014ccc`
- `0x180015fb4`
- `0x18001a6c8`
- `0x18001a77c`
- `0x18001a7d4`
- `0x18001b768`
- `0x180022ad8`
- `0x180024ac8`
- `0x18002cd54`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SetErrorInfo` at `0x180014720`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180014720`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPersistDSO::InvokeService(
        CPersistDSO *this,
        const struct _GUID *a2,
        struct IUnknown *a3,
        struct IUnknown **a4)
{
  __int64 v8; // rax
  BOOL v9; // edi
  unsigned int v10; // edx
  __int64 v11; // rax
  __int64 v12; // rax
  int RowsetFromStream; // ebx
  int v14; // eax
  int v15; // ebx
  int v16; // eax
  int v17; // ebx
  int BidObjectID; // ebx
  CXMLReader *v19; // rdi
  unsigned int v20; // eax
  unsigned __int64 v21; // rcx
  int v22; // eax
  int v23; // ebx
  int v24; // ebx
  CXMLReader *v25; // rdi
  unsigned int v26; // eax
  int PropertyValueLong; // edi
  unsigned int v28; // edx
  unsigned __int64 PropertyValueLongLong; // r13
  CPersistDSO *v30; // rcx
  int v31; // eax
  int v32; // edi
  struct IStream *v33; // rdi
  int v34; // eax
  int v35; // edi
  int v36; // esi
  unsigned int v37; // eax
  int v38; // ecx
  int v40; // [rsp+30h] [rbp-38h] BYREF
  CXMLReader *v41; // [rsp+38h] [rbp-30h] BYREF
  struct IStream *v42; // [rsp+70h] [rbp+8h] BYREF
  struct IUnknown **v43; // [rsp+88h] [rbp+20h]

  v43 = a4;
  v8 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IRowset.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IRowset.Data1 )
    v8 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IRowset.Data4;
  v9 = v8 == 0;
  SetErrorInfo(0, 0);
  *(GUID *)((char *)this - 4424) = IID_IRDSService;
  *((_DWORD *)this - 77) = 0;
  if ( !v9 )
  {
    v11 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IPersistStream.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IPersistStream.Data1 )
      v11 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IPersistStream.Data4;
    if ( v11 )
    {
      v12 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IPersistStreamInit.Data1;
      if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IPersistStreamInit.Data1 )
        v12 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IPersistStreamInit.Data4;
      if ( v12 )
        goto LABEL_72;
    }
  }
  if ( !a4 || (RowsetFromStream = 0, !a3) )
  {
LABEL_72:
    v38 = -2147024809;
    return Exit(v38, 0);
  }
  try
  {
    if ( v9 )
    {
      v42 = 0;
      v14 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IStream **))a3->lpVtbl->QueryInterface)(
              a3,
              &IID_IStream,
              &v42);
      v15 = v14;
      if ( v14 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( off_1800489E0[0] )
            bidTraceW(off_1800481E0[0], 399360, off_1800489E0[0], (unsigned int)v14, 390);
        }
        ThrowHR(v15);
      }
      v41 = 0;
      if ( IsADTGStream(&v42) )
      {
        v16 = ATL::CComObject<CADTGRowset>::CreateInstance(&v41);
        v17 = v16;
        if ( v16 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_1800489D8[0] )
            bidTraceW(off_1800481E0[0], 406528, off_1800489D8[0], (unsigned int)v16, 397);
          ThrowHR(v17);
        }
        if ( (bidGblFlags & 2) != 0 && off_1800489D0[0] )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CPersistDSO *)((char *)this + 64));
          v19 = v41;
          v20 = CBidGenericBase::GetBidObjectID((CXMLReader *)((char *)v41 + 112));
          bidTraceW(off_1800481E0[0], 409600, off_1800489D0[0], v20, BidObjectID);
        }
        else
        {
          v19 = v41;
        }
        (*(void (__fastcall **)(CXMLReader *))(*(_QWORD *)v19 + 8LL))(v19);
        v21 = ((unsigned __int64)this - 4520) & -(__int64)(this != (CPersistDSO *)4544);
        *((_QWORD *)v19 + 67) = v21;
        (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v21 + 8LL))(v21);
        RowsetFromStream = (*(__int64 (__fastcall **)(CXMLReader *, struct IStream *))(*(_QWORD *)v19 + 152LL))(
                             v19,
                             v42);
        if ( RowsetFromStream >= 0 )
          RowsetFromStream = (**(__int64 (__fastcall ***)(CXMLReader *, const struct _GUID *, struct IUnknown **))v19)(
                               v19,
                               a2,
                               a4);
        (*(void (__fastcall **)(CXMLReader *))(*(_QWORD *)v19 + 16LL))(v19);
        if ( RowsetFromStream < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_1800489C8[0] )
            bidTraceW(off_1800481E0[0], 422912, off_1800489C8[0], (unsigned int)RowsetFromStream, 413);
          ThrowHR(RowsetFromStream);
        }
      }
      else
      {
        v22 = ATL::CComObject<CXMLReader>::CreateInstance(&v41);
        v23 = v22;
        if ( v22 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_1800489C0[0] )
            bidTraceW(off_1800481E0[0], 432128, off_1800489C0[0], (unsigned int)v22, 422);
          ThrowHR(v23);
        }
        if ( (bidGblFlags & 2) != 0 && off_1800489B8[0] )
        {
          v24 = CBidGenericBase::GetBidObjectID((CPersistDSO *)((char *)this + 64));
          v25 = v41;
          v26 = CBidGenericBase::GetBidObjectID((CXMLReader *)((char *)v41 + 496));
          bidTraceW(off_1800481E0[0], 435200, off_1800489B8[0], v26, v24);
        }
        else
        {
          v25 = v41;
        }
        (*(void (__fastcall **)(CXMLReader *))(*(_QWORD *)v25 + 8LL))(v25);
        RowsetFromStream = CXMLReader::CreateRowsetFromStream(
                             v25,
                             v42,
                             (struct IDBProperties *)(((unsigned __int64)this - 4520)
                                                    & -(__int64)(this != (CPersistDSO *)4544)),
                             a2,
                             (void **)a4);
        (*(void (__fastcall **)(CXMLReader *))(*(_QWORD *)v25 + 16LL))(v25);
        if ( RowsetFromStream < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_1800489B0[0] )
            bidTraceW(off_1800481E0[0], 442368, off_1800489B0[0], (unsigned int)RowsetFromStream, 432);
          ThrowHR(RowsetFromStream);
        }
      }
      CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v42);
      goto LABEL_76;
    }
    PropertyValueLong = CDSOProps::GetPropertyValueLong((CPersistDSO *)((char *)this + 80), v10);
    PropertyValueLongLong = CDSOProps::GetPropertyValueLongLong((CPersistDSO *)((char *)this + 80), v28);
    CPersistDSO::PopulateRowset(v30, a3, PropertyValueLongLong);
    v42 = 0;
    if ( PropertyValueLong == 1 )
    {
      v31 = ATL::CComObject<CPersistStreamInit>::CreateInstance(&v42);
      v32 = v31;
      if ( v31 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_1800489A8[0] )
          bidTraceW(off_1800481E0[0], 463872, off_1800489A8[0], (unsigned int)v31, 453);
        ThrowHR(v32);
      }
      v33 = v42;
      ((void (__fastcall *)(struct IStream *))v42->lpVtbl->AddRef)(v42);
      if ( CPersistStreamInit::Init((CPersistStreamInit *)v33, a3, (CPersistDSO *)((char *)this + 80)) < 0 )
        goto LABEL_59;
    }
    else
    {
      v34 = ATL::CComObject<CADTGPersistStreamInit>::CreateInstance(&v42);
      v35 = v34;
      if ( v34 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_1800489A0[0] )
          bidTraceW(off_1800481E0[0], 480256, off_1800489A0[0], (unsigned int)v34, 469);
        ThrowHR(v35);
      }
      if ( (bidGblFlags & 2) != 0 && off_180048998[0] )
      {
        v36 = CBidGenericBase::GetBidObjectID((CPersistDSO *)((char *)this + 64));
        v33 = v42;
        v37 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)&v42[3]);
        bidTraceW(off_1800481E0[0], 483328, off_180048998[0], v37, v36);
      }
      else
      {
        v33 = v42;
      }
      ((void (__fastcall *)(struct IStream *))v33->lpVtbl->AddRef)(v33);
      v33[6].lpVtbl = (struct IStreamVtbl *)PropertyValueLongLong;
      if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IStream *))a3->lpVtbl->QueryInterface)(
             a3,
             &IID_IRowset,
             &v33[7]) < 0 )
        goto LABEL_59;
    }
    RowsetFromStream = ((__int64 (__fastcall *)(struct IStream *, const struct _GUID *, struct IUnknown **))v33->lpVtbl->QueryInterface)(
                         v33,
                         a2,
                         v43);
LABEL_59:
    ((void (__fastcall *)(struct IStream *))v33->lpVtbl->Release)(v33);
  }
  catch ( long v40 )
  {
    LODWORD(v42) = v40;
    RowsetFromStream = v40;
  }
  catch ( ... )
  {
    return 2147500037LL;
  }
LABEL_76:
  v38 = RowsetFromStream;
  return Exit(v38, 0);
}

```

## disassembly

```asm
0x1800146d0  mov     [rsp+arg_8], rbx
0x1800146d5  mov     [rsp+arg_10], rsi
0x1800146da  mov     [rsp+arg_18], r9
0x1800146df  push    rdi
0x1800146e0  push    r12
0x1800146e2  push    r13
0x1800146e4  push    r14
0x1800146e6  push    r15
0x1800146e8  sub     rsp, 40h
0x1800146ec  mov     r14, r9
0x1800146ef  mov     r12, r8
0x1800146f2  mov     r15, rdx
0x1800146f5  mov     rsi, rcx
0x1800146f8  mov     rax, [rdx]
0x1800146fb  sub     rax, qword ptr cs:IID_IRowset.Data1
0x180014702  jnz     short loc_18001470F
0x180014704  mov     rax, [rdx+8]
0x180014708  sub     rax, qword ptr cs:IID_IRowset.Data4
0x18001470f  xor     r13d, r13d
0x180014712  mov     edi, r13d
0x180014715  test    rax, rax
0x180014718  setz    dil
0x18001471c  xor     edx, edx; perrinfo
0x18001471e  xor     ecx, ecx; dwReserved
0x180014720  call    cs:__imp_SetErrorInfo
0x180014726  movups  xmm0, xmmword ptr cs:?IID_IRDSService@@3U_GUID@@B.Data1; _GUID const IID_IRDSService ...
0x18001472d  movdqu  xmmword ptr [rsi-1148h], xmm0
0x180014735  mov     [rsi-134h], r13d
0x18001473c  test    edi, edi
0x18001473e  jnz     short loc_18001477C
0x180014740  mov     rax, [r15]
0x180014743  sub     rax, qword ptr cs:IID_IPersistStream.Data1
0x18001474a  jnz     short loc_180014757
0x18001474c  mov     rax, [r15+8]
0x180014750  sub     rax, qword ptr cs:IID_IPersistStream.Data4
0x180014757  test    rax, rax
0x18001475a  jz      short loc_18001477C
0x18001475c  mov     rax, [r15]
0x18001475f  sub     rax, qword ptr cs:IID_IPersistStreamInit.Data1
0x180014766  jnz     short loc_180014773
0x180014768  mov     rax, [r15+8]
0x18001476c  sub     rax, qword ptr cs:IID_IPersistStreamInit.Data4
0x180014773  test    rax, rax
0x180014776  jnz     loc_180014C9F
0x18001477c  test    r14, r14
0x18001477f  jz      loc_180014C9F
0x180014785  mov     ebx, r13d
0x180014788  test    r12, r12
0x18001478b  jz      loc_180014C9F
0x180014791  test    edi, edi
0x180014793  jz      loc_180014ABA
0x180014799  mov     [rsp+68h+arg_0], r13
0x18001479e  mov     rax, [r12]
0x1800147a2  lea     r8, [rsp+68h+arg_0]
0x1800147a7  lea     rdx, IID_IStream
0x1800147ae  mov     rcx, r12
0x1800147b1  mov     rax, [rax]
0x1800147b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147b9  mov     ebx, eax
0x1800147bb  test    eax, eax
0x1800147bd  jns     short loc_1800147FE
0x1800147bf  test    byte ptr cs:_bidGblFlags, 2
0x1800147c6  jz      short loc_1800147F7
0x1800147c8  mov     rcx, cs:off_1800489E0; "<CPersistDSO::InvokeService|ADO|ERR>  H"...
0x1800147cf  test    rcx, rcx
0x1800147d2  jz      short loc_1800147F7
0x1800147d4  mov     dword ptr [rsp+68h+var_48], 186h
0x1800147dc  mov     r9d, eax
0x1800147df  mov     r8, cs:off_1800489E0; "<CPersistDSO::InvokeService|ADO|ERR>  H"...
0x1800147e6  mov     edx, 61800h
0x1800147eb  mov     rcx, cs:off_1800481E0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800147f2  call    _bidTraceW
0x1800147f7  mov     ecx, ebx; int
0x1800147f9  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800147fe  lea     rcx, [rsp+68h+arg_0]; struct IStream **
0x180014803  call    ?IsADTGStream@@YA_NPEAPEAUIStream@@@Z; IsADTGStream(IStream * *)
0x180014808  mov     [rsp+68h+var_30], r13
0x18001480d  lea     rcx, [rsp+68h+var_30]
0x180014812  test    al, al
0x180014814  jz      loc_18001497A
0x18001481a  call    ?CreateInstance@?$CComObject@VCADTGRowset@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CADTGRowset>::CreateInstance(ATL::CComObject<CADTGRowset> * *)
0x18001481f  mov     ebx, eax
0x180014821  test    eax, eax
0x180014823  jns     short loc_180014864
0x180014825  test    byte ptr cs:_bidGblFlags, 2
0x18001482c  jz      short loc_18001485D
0x18001482e  mov     rcx, cs:off_1800489D8; "<CPersistDSO::InvokeService|ADO|ERR>  H"...
0x180014835  test    rcx, rcx
0x180014838  jz      short loc_18001485D
0x18001483a  mov     dword ptr [rsp+68h+var_48], 18Dh
0x180014842  mov     r9d, eax
0x180014845  mov     r8, cs:off_1800489D8; "<CPersistDSO::InvokeService|ADO|ERR>  H"...
0x18001484c  mov     edx, 63400h
0x180014851  mov     rcx, cs:off_1800481E0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180014858  call    _bidTraceW
0x18001485d  mov     ecx, ebx; int
0x18001485f  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180014864  test    byte ptr cs:_bidGblFlags, 2
0x18001486b  jz      short loc_1800148B3
0x18001486d  mov     rax, cs:off_1800489D0; "<CPersistDSO::InvokeService|ADO|PERSIST"...
0x180014874  test    rax, rax
0x180014877  jz      short loc_1800148B3
0x180014879  lea     rcx, [rsi+40h]; this
0x18001487d  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180014882  mov     ebx, eax
0x180014884  mov     rdi, [rsp+68h+var_30]
0x180014889  lea     rcx, [rdi+70h]; this
0x18001488d  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180014892  mov     r8, cs:off_1800489D0; "<CPersistDSO::InvokeService|ADO|PERSIST"...
0x180014899  mov     rcx, cs:off_1800481E0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800148a0  mov     dword ptr [rsp+68h+var_48], ebx
0x1800148a4  mov     r9d, eax
0x1800148a7  mov     edx, 64000h
0x1800148ac  call    _bidTraceW
0x1800148b1  jmp     short loc_1800148B8
0x1800148b3  mov     rdi, [rsp+68h+var_30]
0x1800148b8  mov     rax, [rdi]
0x1800148bb  mov     rcx, rdi
0x1800148be  mov     rax, [rax+8]
0x1800148c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148c7  lea     rax, [rsi-11C0h]
0x1800148ce  lea     rdx, [rsi-11A8h]
0x1800148d5  neg     rax
0x1800148d8  sbb     rcx, rcx
0x1800148db  and     rcx, rdx
0x1800148de  mov     [rdi+218h], rcx
0x1800148e5  mov     rax, [rcx]
0x1800148e8  mov     rax, [rax+8]
0x1800148ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148f1  mov     rax, [rdi]
0x1800148f4  mov     rdx, [rsp+68h+arg_0]
0x1800148f9  mov     rcx, rdi
0x1800148fc  mov     rax, [rax+98h]
0x180014903  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014908  mov     ebx, eax
0x18001490a  test    eax, eax
0x18001490c  js      short loc_180014924
0x18001490e  mov     rax, [rdi]
0x180014911  mov     r8, r14
0x180014914  mov     rdx, r15
0x180014917  mov     rcx, rdi
0x18001491a  mov     rax, [rax]
0x18001491d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014922  mov     ebx, eax
0x180014924  mov     rax, [rdi]
0x180014927  mov     rcx, rdi
0x18001492a  mov     rax, [rax+10h]
0x18001492e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014933  test    ebx, ebx
0x180014935  jns     loc_180014AAB
0x18001493b  test    byte ptr cs:_bidGblFlags, 2
0x180014942  jz      short loc_180014973
0x180014944  mov     rax, cs:off_1800489C8; "<CPersistDSO::InvokeService|ADO|ERR>  H"...
0x18001494b  test    rax, rax
0x18001494e  jz      short loc_180014973
0x180014950  mov     dword ptr [rsp+68h+var_48], 19Dh
0x180014958  mov     r9d, ebx
0x18001495b  mov     r8, cs:off_1800489C8; "<CPersistDSO::InvokeService|ADO|ERR>  H"...
0x180014962  mov     edx, 67400h
0x180014967  mov     rcx, cs:off_1800481E0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18001496e  call    _bidTraceW
0x180014973  mov     ecx, ebx; int
0x180014975  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18001497a  call    ?CreateInstance@?$CComObject@VCXMLReader@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CXMLReader>::CreateInstance(ATL::CComObject<CXMLReader> * *)
0x18001497f  mov     ebx, eax
0x180014981  test    eax, eax
0x180014983  jns     short loc_1800149C4
0x180014985  test    byte ptr cs:_bidGblFlags, 2
0x18001498c  jz      short loc_1800149BD
0x18001498e  mov     rcx, cs:off_1800489C0; "<CPersistDSO::InvokeService|ADO|ERR>  H"...
0x180014995  test    rcx, rcx
0x180014998  jz      short loc_1800149BD
0x18001499a  mov     dword ptr [rsp+68h+var_48], 1A6h
0x1800149a2  mov     r9d, eax
0x1800149a5  mov     r8, cs:off_1800489C0; "<CPersistDSO::InvokeService|ADO|ERR>  H"...
0x1800149ac  mov     edx, 69800h
0x1800149b1  mov     rcx, cs:off_1800481E0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800149b8  call    _bidTraceW
0x1800149bd  mov     ecx, ebx; int
0x1800149bf  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800149c4  test    byte ptr cs:_bidGblFlags, 2
0x1800149cb  jz      short loc_180014A16
0x1800149cd  mov     rax, cs:off_1800489B8; "<CPersistDSO::InvokeService|ADO|PERSIST"...
0x1800149d4  test    rax, rax
0x1800149d7  jz      short loc_180014A16
0x1800149d9  lea     rcx, [rsi+40h]; this
0x1800149dd  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800149e2  mov     ebx, eax
0x1800149e4  mov     rdi, [rsp+68h+var_30]
0x1800149e9  lea     rcx, [rdi+1F0h]; this
0x1800149f0  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800149f5  mov     r8, cs:off_1800489B8; "<CPersistDSO::InvokeService|ADO|PERSIST"...
0x1800149fc  mov     rcx, cs:off_1800481E0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180014a03  mov     dword ptr [rsp+68h+var_48], ebx
0x180014a07  mov     r9d, eax
0x180014a0a  mov     edx, 6A400h
0x180014a0f  call    _bidTraceW
0x180014a14  jmp     short loc_180014A1B
0x180014a16  mov     rdi, [rsp+68h+var_30]
0x180014a1b  mov     rax, [rdi]
0x180014a1e  mov     rcx, rdi
0x180014a21  mov     rax, [rax+8]
0x180014a25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a2a  lea     rax, [rsi-11C0h]
0x180014a31  lea     rcx, [rsi-11A8h]
0x180014a38  neg     rax
0x180014a3b  sbb     r8, r8
0x180014a3e  and     r8, rcx; struct IDBProperties *
0x180014a41  mov     [rsp+68h+var_48], r14; void **
0x180014a46  mov     r9, r15; struct _GUID *
0x180014a49  mov     rdx, [rsp+68h+arg_0]; struct IStream *
0x180014a4e  mov     rcx, rdi; this
0x180014a51  call    ?CreateRowsetFromStream@CXMLReader@@QEAAJPEAUIStream@@PEAUIDBProperties@@AEBU_GUID@@PEAPEAX@Z; CXMLReader::CreateRowsetFromStream(IStream *,IDBProperties *,_GUID const &,void * *)
0x180014a56  mov     ebx, eax
0x180014a58  mov     rax, [rdi]
0x180014a5b  mov     rcx, rdi
0x180014a5e  mov     rax, [rax+10h]
0x180014a62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a67  test    ebx, ebx
0x180014a69  jns     short loc_180014AAB
0x180014a6b  test    byte ptr cs:_bidGblFlags, 2
0x180014a72  jz      short loc_180014AA3
0x180014a74  mov     rax, cs:off_1800489B0; "<CPersistDSO::InvokeService|ADO|ERR>  H"...
0x180014a7b  test    rax, rax
0x180014a7e  jz      short loc_180014AA3
0x180014a80  mov     dword ptr [rsp+68h+var_48], 1B0h
0x180014a88  mov     r9d, ebx
0x180014a8b  mov     r8, cs:off_1800489B0; "<CPersistDSO::InvokeService|ADO|ERR>  H"...
0x180014a92  mov     edx, 6C000h
0x180014a97  mov     rcx, cs:off_1800481E0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180014a9e  call    _bidTraceW
0x180014aa3  mov     ecx, ebx; int
0x180014aa5  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180014aab  lea     rcx, [rsp+68h+arg_0]
0x180014ab0  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180014ab5  jmp     loc_180014C8E
0x180014aba  lea     r14, [rsi+50h]
0x180014abe  mov     rcx, r14; this
0x180014ac1  call    ?GetPropertyValueLong@CDSOProps@@QEAAJK@Z; CDSOProps::GetPropertyValueLong(ulong)
0x180014ac6  mov     edi, eax
0x180014ac8  mov     rcx, r14; this
0x180014acb  call    ?GetPropertyValueLongLong@CDSOProps@@QEAA_JK@Z; CDSOProps::GetPropertyValueLongLong(ulong)
0x180014ad0  mov     r13, rax
0x180014ad3  mov     r8, rax; unsigned __int64
0x180014ad6  mov     rdx, r12; struct IUnknown *
0x180014ad9  call    ?PopulateRowset@CPersistDSO@@AEAAXPEAUIUnknown@@_K@Z; CPersistDSO::PopulateRowset(IUnknown *,unsigned __int64)
0x180014ade  mov     [rsp+68h+arg_0], 0
0x180014ae7  lea     rcx, [rsp+68h+arg_0]
0x180014aec  cmp     edi, 1
0x180014aef  jnz     loc_180014B94
0x180014af5  call    ?CreateInstance@?$CComObject@VCPersistStreamInit@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CPersistStreamInit>::CreateInstance(ATL::CComObject<CPersistStreamInit> * *)
0x180014afa  mov     edi, eax
0x180014afc  test    eax, eax
0x180014afe  jns     short loc_180014B3F
0x180014b00  test    byte ptr cs:_bidGblFlags, 2
0x180014b07  jz      short loc_180014B38
0x180014b09  mov     rcx, cs:off_1800489A8; "<CPersistDSO::InvokeService|ADO|ERR>  H"...
0x180014b10  test    rcx, rcx
0x180014b13  jz      short loc_180014B38
0x180014b15  mov     dword ptr [rsp+68h+var_48], 1C5h
0x180014b1d  mov     r9d, eax
0x180014b20  mov     r8, cs:off_1800489A8; "<CPersistDSO::InvokeService|ADO|ERR>  H"...
0x180014b27  mov     edx, 71400h
0x180014b2c  mov     rcx, cs:off_1800481E0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180014b33  call    _bidTraceW
0x180014b38  mov     ecx, edi; int
0x180014b3a  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180014b3f  mov     rdi, [rsp+68h+arg_0]
0x180014b44  mov     rax, [rdi]
0x180014b47  mov     rcx, rdi
0x180014b4a  mov     rax, [rax+8]
0x180014b4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b53  mov     r8, r14; struct CDSOProps *
0x180014b56  mov     rdx, r12; struct IUnknown *
0x180014b59  mov     rcx, rdi; this
0x180014b5c  call    ?Init@CPersistStreamInit@@QEAAJPEAUIUnknown@@AEAVCDSOProps@@@Z; CPersistStreamInit::Init(IUnknown *,CDSOProps &)
0x180014b61  test    eax, eax
0x180014b63  js      short loc_180014B80
0x180014b65  mov     rax, [rdi]
0x180014b68  mov     r8, [rsp+68h+arg_18]
0x180014b70  mov     rdx, r15
0x180014b73  mov     rcx, rdi
0x180014b76  mov     rax, [rax]
0x180014b79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b7e  mov     ebx, eax
0x180014b80  mov     rax, [rdi]
0x180014b83  mov     rcx, rdi
0x180014b86  mov     rax, [rax+10h]
0x180014b8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b8f  jmp     loc_180014C8E
0x180014b94  call    ?CreateInstance@?$CComObject@VCADTGPersistStreamInit@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CADTGPersistStreamInit>::CreateInstance(ATL::CComObject<CADTGPersistStreamInit> * *)
0x180014b99  mov     edi, eax
0x180014b9b  test    eax, eax
0x180014b9d  jns     short loc_180014BDE
0x180014b9f  test    byte ptr cs:_bidGblFlags, 2
0x180014ba6  jz      short loc_180014BD7
0x180014ba8  mov     rcx, cs:off_1800489A0; "<CPersistDSO::InvokeService|ADO|ERR>  H"...
0x180014baf  test    rcx, rcx
0x180014bb2  jz      short loc_180014BD7
0x180014bb4  mov     dword ptr [rsp+68h+var_48], 1D5h
  ... truncated ...
```
