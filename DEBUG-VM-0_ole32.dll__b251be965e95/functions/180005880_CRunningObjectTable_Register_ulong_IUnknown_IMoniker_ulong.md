# CRunningObjectTable::Register(ulong,IUnknown *,IMoniker *,ulong *)

- ea: `0x180005880`
- end: `0x180005e33`
- name: `?Register@CRunningObjectTable@@UEAAJKPEAUIUnknown@@PEAUIMoniker@@PEAK@Z`
- size: `1459`
- prototype: `HRESULT __fastcall(CRunningObjectTable *this, unsigned int grfFlags, IUnknown *punkObject, IMoniker *pmkObjectName, unsigned int *pdwRegister)`
- caller_count: `0`
- callee_count: `16`
- tags: `reparse_path, service_task, broker_com_uri`

## callees

- `0x180005880`
- `0x180005e40`
- `0x180006f8c`
- `0x180008544`
- `0x18000895c`
- `0x180009de0`
- `0x180009e1c`
- `0x18000a4a8`
- `0x18000ac30`
- `0x1800293b8`
- `0x180052390`
- `0x180059088`
- `0x180073600`
- `0x180073648`
- `0x18007386c`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005b38`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005b95`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005dbb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005dd4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005b38`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005b95`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005dbb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005dd4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005a0b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005a0b`
- `api-ms-win-core-com-l1-1-0!CoGetCurrentProcess` at `0x180005ceb`
- `api-ms-win-core-com-l1-1-0!CoGetCurrentProcess` at `0x180005ceb`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1800059c7`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1800059c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005c3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005c48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005c3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005c48`
- `api-ms-win-core-com-private-l1-1-0!InternalIrotRegister` at `0x180005d17`
- `api-ms-win-core-com-private-l1-1-0!InternalIrotRegister` at `0x180005d17`
- `api-ms-win-core-com-private-l1-1-0!InternalCoRegisterDisconnectCallback` at `0x180005cd3`
- `api-ms-win-core-com-private-l1-1-0!InternalCoRegisterDisconnectCallback` at `0x180005cd3`
- `api-ms-win-core-com-private-l1-1-0!InternalCoUnregisterDisconnectCallback` at `0x180005ae2`
- `api-ms-win-core-com-private-l1-1-0!InternalCoUnregisterDisconnectCallback` at `0x180005ae2`

## string_xrefs

- `0x180005e1d`: `Register object in ROT %p completed with status %08x`

## pseudocode

```c
__int64 __fastcall CRunningObjectTable::Register(
        CRunningObjectTable *this,
        unsigned int grfFlags,
        IUnknown *punkObject,
        IMoniker *pmkObjectName,
        unsigned int *pdwRegister)
{
  tagInterfaceData *v5; // rdi
  tagMInterfacePointer *v6; // rsi
  tagMInterfacePointer *pMInterfacePointer; // r12
  int v10; // r14d
  unsigned int v11; // edx
  const char *v12; // r9
  struct IUnknownVtbl *lpVtbl; // rax
  HRESULT function; // ebx
  HRESULT v15; // eax
  unsigned int cbBufferSize; // ecx
  _DWORD *v17; // rax
  _DWORD *v18; // rbx
  const char *v19; // r9
  CRunningObjectTable *v20; // r13
  CROTItem **MyBegin; // rdx
  CROTItem **MyEnd; // rcx
  unsigned __int64 v23; // rax
  unsigned __int64 v24; // rcx
  signed __int64 v25; // rax
  unsigned int v27; // r13d
  DWORD CurrentProcess; // eax
  const char *v29; // rcx
  TraceLevel v30; // r9d
  tagInterfaceData *pifdMoniker; // [rsp+48h] [rbp-B8h] BYREF
  CRunningObjectTable *file; // [rsp+50h] [rbp-B0h]
  CWriteInterfaceDataMarshalingStream objectStream; // [rsp+58h] [rbp-A8h] BYREF
  DWORD mshlflags; // [rsp+88h] [rbp-78h]
  CReadInterfaceDataFromInternalSourceMarshalingStream monikerStream; // [rsp+90h] [rbp-70h] BYREF
  IProxyManager *pProxyManager; // [rsp+C0h] [rbp-40h] BYREF
  void *pvNotifyCookie; // [rsp+C8h] [rbp-38h] BYREF
  _FILETIME filetime; // [rsp+D0h] [rbp-30h] BYREF
  IUnknown *v40; // [rsp+D8h] [rbp-28h]
  unsigned int *v41; // [rsp+E0h] [rbp-20h]
  CTmpMkEqBuf tmeb; // [rsp+F0h] [rbp-10h] BYREF

  v5 = 0;
  file = this;
  v6 = 0;
  v40 = punkObject;
  v41 = pdwRegister;
  pifdMoniker = 0;
  pMInterfacePointer = 0;
  v10 = -1;
  CheckInitDde(1);
  if ( (grfFlags & 0xFFFFFFFC) != 0 || !IsValidInterface(punkObject) || !IsValidInterface(pmkObjectName) || !pdwRegister )
  {
    function = -2147024809;
    goto LABEL_19;
  }
  lpVtbl = punkObject->lpVtbl;
  pProxyManager = 0;
  if ( !((unsigned int (__fastcall *)(IUnknown *, GUID *, IProxyManager **))lpVtbl->QueryInterface)(
          punkObject,
          &IID_IProxyManager,
          &pProxyManager) )
  {
    ((void (__fastcall *)(IProxyManager *))pProxyManager->lpVtbl->Release)(pProxyManager);
    function = -2147024809;
    goto LABEL_36;
  }
  *pdwRegister = 0;
  filetime = 0;
  function = GetMonikerCompareBuffer(pmkObjectName, &tmeb, &filetime, &pifdMoniker);
  if ( function >= 0 )
  {
    objectStream.CAbstractMarshalingStream = 0;
    CAbstractMarshalingStream::CAbstractMarshalingStream(&objectStream);
    *(_QWORD *)&objectStream._lOffset = 0;
    objectStream._fFree = 1;
    objectStream.lpVtbl = (struct IStreamVtbl *)CReadInterfaceDataFromInternalSourceMarshalingStream::`vftable';
    objectStream._cbBufferSize = 0;
    objectStream._pMInterfacePointer = 0;
    mshlflags = ((grfFlags & 1) == 0) + 1;
    v15 = CoMarshalInterface(&objectStream, &IID_IUnknown, punkObject, 1u, 0, mshlflags);
    v6 = (tagMInterfacePointer *)pifdMoniker;
    function = v15;
    if ( !v15 )
    {
      cbBufferSize = objectStream._cbBufferSize;
      if ( objectStream._cbDataSize )
        cbBufferSize = objectStream._cbDataSize;
      objectStream._pMInterfacePointer->ulCntData = cbBufferSize;
      pMInterfacePointer = objectStream._pMInterfacePointer;
      objectStream._pMInterfacePointer = 0;
      objectStream._fFree = 0;
      v17 = HeapAlloc(g_hHeap, 0, 0x28u);
      v18 = v17;
      if ( !v17 )
      {
        function = -2147024882;
        objectStream.lpVtbl = (struct IStreamVtbl *)CBaseMInterfacePointerMarshalingStream::`vftable';
        if ( objectStream._fFree )
          HeapFree(g_hHeap, 0, objectStream._pMInterfacePointer);
        objectStream.lpVtbl = (struct IStreamVtbl *)CAbstractStream::`vftable';
        goto LABEL_19;
      }
      v17[1] = 0;
      v17[6] = GetCurrentApartmentId();
      *((_QWORD *)v18 + 4) = 0;
      *((_QWORD *)v18 + 1) = -1;
      v5 = (tagInterfaceData *)v18;
      pifdMoniker = (tagInterfaceData *)v18;
      COleStaticMutexSem::Request(&g_RotSem, "Unknown File", 0, v19);
      v20 = file;
      ++file->_wSigRotItem;
      *(_WORD *)v18 = v20->_wSigRotItem;
      MyBegin = v20->_rotList._MyBegin;
      MyEnd = v20->_rotList._MyEnd;
      if ( MyBegin != MyEnd )
      {
        v23 = 0;
        v24 = MyEnd - MyBegin;
        while ( v23 < v24 )
        {
          if ( !MyBegin[v23] )
          {
            MyBegin[v23] = (CROTItem *)v18;
            v10 = v23;
            if ( (_DWORD)v23 == -1 )
              break;
            goto LABEL_39;
          }
          ++v23;
        }
      }
      if ( !utl::vector<CROTItem *,utl::allocator<CROTItem *>>::_PushBackOne<CROTItem * const &>(
              (utl::vector<unsigned __int64,utl::allocator<unsigned __int64> > *)&v20->_rotList,
              (const unsigned __int64 *)&pifdMoniker) )
      {
        function = -2147024882;
        COleStaticMutexSem::Release(&g_RotSem);
        CBaseMInterfacePointerMarshalingStream::~CBaseMInterfacePointerMarshalingStream(&objectStream);
        v5 = pifdMoniker;
        goto LABEL_19;
      }
      v5 = pifdMoniker;
      v10 = v20->_rotList._MyEnd - v20->_rotList._MyBegin - 1;
LABEL_39:
      v27 = v10 | (v20->_wSigRotItem << 16);
      COleStaticMutexSem::Release(&g_RotSem);
      pvNotifyCookie = 0;
      function = InternalCoRegisterDisconnectCallback(v40, mshlflags, &file->IDisconnectSink, v27, &pvNotifyCookie);
      if ( function < 0 )
      {
        CBaseMInterfacePointerMarshalingStream::~CBaseMInterfacePointerMarshalingStream(&objectStream);
LABEL_19:
        if ( v5 )
        {
          v25 = _InterlockedCompareExchange64((volatile signed __int64 *)&v5->abData[28], 0, *(_QWORD *)&v5->abData[28]);
          if ( v25 )
            InternalCoUnregisterDisconnectCallback(v25);
        }
        if ( pMInterfacePointer )
        {
          monikerStream.CAbstractMarshalingStream = 0;
          CAbstractMarshalingStream::CAbstractMarshalingStream(&monikerStream);
          monikerStream.lpVtbl = (struct IStreamVtbl *)CBaseMInterfacePointerMarshalingStream::`vftable';
          *(_QWORD *)&monikerStream._lOffset = 0;
          monikerStream._pMInterfacePointer = pMInterfacePointer;
          monikerStream._fFree = 0;
          monikerStream._cbBufferSize = pMInterfacePointer->ulCntData;
          monikerStream.lpVtbl = (struct IStreamVtbl *)CReadInterfaceDataFromInternalSourceMarshalingStream::`vftable';
          ReleaseMarshalingData(&monikerStream);
          HeapFree(g_hHeap, 0, pMInterfacePointer);
          CBaseMInterfacePointerMarshalingStream::~CBaseMInterfacePointerMarshalingStream(&monikerStream);
        }
        goto LABEL_24;
      }
      *(_QWORD *)&v5->abData[28] = pvNotifyCookie;
      CurrentProcess = CoGetCurrentProcess();
      function = InternalIrotRegister(
                   &tmeb,
                   pMInterfacePointer,
                   v6,
                   &filetime,
                   CurrentProcess,
                   grfFlags & 2,
                   &v5->abData[4]);
      if ( function < 0 )
        *(_QWORD *)&v5->abData[4] = -1;
      else
        *v41 = v27;
    }
    objectStream.lpVtbl = (struct IStreamVtbl *)CBaseMInterfacePointerMarshalingStream::`vftable';
    if ( objectStream._fFree )
      HeapFree(g_hHeap, 0, objectStream._pMInterfacePointer);
    objectStream.lpVtbl = (struct IStreamVtbl *)CAbstractStream::`vftable';
    if ( function >= 0 )
    {
      CoTaskMemFree(v6);
      CoTaskMemFree(pMInterfacePointer);
      goto LABEL_36;
    }
    goto LABEL_19;
  }
  v6 = (tagMInterfacePointer *)pifdMoniker;
LABEL_24:
  if ( v6 )
  {
    monikerStream.CAbstractMarshalingStream = 0;
    CAbstractMarshalingStream::CAbstractMarshalingStream(&monikerStream);
    monikerStream.lpVtbl = (struct IStreamVtbl *)CBaseMInterfacePointerMarshalingStream::`vftable';
    *(_QWORD *)&monikerStream._lOffset = 0;
    monikerStream._pMInterfacePointer = v6;
    monikerStream._fFree = 0;
    monikerStream._cbBufferSize = v6->ulCntData;
    monikerStream.lpVtbl = (struct IStreamVtbl *)CReadInterfaceDataFromInternalSourceMarshalingStream::`vftable';
    ReleaseMarshalingData(&monikerStream);
    HeapFree(g_hHeap, 0, v6);
    CBaseMInterfacePointerMarshalingStream::~CBaseMInterfacePointerMarshalingStream(&monikerStream);
  }
  if ( v5 )
  {
    if ( v10 != -1 )
    {
      COleStaticMutexSem::Request(&g_RotSem, "Unknown File", 0, v12);
      file->_rotList._MyBegin[v10] = 0;
      COleStaticMutexSem::Release(&g_RotSem);
    }
    CROTItem::`scalar deleting destructor'((CROTItem *)v5, v11);
  }
LABEL_36:
  if ( gfEnableTracing && IsWppLevelEnabled(INFO) )
    ComTraceMessageT<CFilteredRunningObjectTable *,long>(
      v29,
      "CRunningObjectTable::Register",
      785,
      v30,
      L"Register object in ROT %p completed with status %08x",
      file,
      function);
  return (unsigned int)function;
}

```

## disassembly

```asm
0x180005880  mov     [rsp-8+arg_8], rbx
0x180005885  push    rbp
0x180005886  push    rsi
0x180005887  push    rdi
0x180005888  push    r12
0x18000588a  push    r13
0x18000588c  push    r14
0x18000588e  push    r15
0x180005890  lea     rbp, [rsp-810h]
0x180005898  sub     rsp, 910h
0x18000589f  mov     rax, cs:__security_cookie
0x1800058a6  xor     rax, rsp
0x1800058a9  mov     [rbp+840h+var_40], rax
0x1800058b0  mov     r13, [rbp+840h+arg_20]
0x1800058b7  xor     edi, edi
0x1800058b9  mov     [rsp+940h+file], this
0x1800058be  xor     esi, esi
0x1800058c0  mov     rbx, pmkObjectName
0x1800058c3  mov     [rbp+840h+var_868], punkObject
0x1800058c7  mov     r15, punkObject
0x1800058ca  mov     [rsp+940h+var_900], grfFlags
0x1800058ce  lea     ecx, [rdi+1]; fRegisteringServerObject
0x1800058d1  mov     [rbp+840h+var_860], r13
0x1800058d5  mov     [rsp+940h+pifdMoniker], rsi
0x1800058da  xor     r12d, r12d
0x1800058dd  or      r14d, 0FFFFFFFFh
0x1800058e1  call    CheckInitDde
0x1800058e6  test    [rsp+940h+var_900], 0FFFFFFFCh
0x1800058ee  jnz     loc_180005BF4
0x1800058f4  mov     this, r15; pv
0x1800058f7  call    IsValidInterface
0x1800058fc  test    eax, eax
0x1800058fe  jz      loc_180005BF4
0x180005904  mov     this, rbx; pv
0x180005907  call    IsValidInterface
0x18000590c  test    eax, eax
0x18000590e  jz      loc_180005BF4
0x180005914  test    r13, r13
0x180005917  jz      loc_180005BF4
0x18000591d  mov     rax, [r15]
0x180005920  lea     punkObject, [rbp+840h+pProxyManager]
0x180005924  lea     rdx, IID_IProxyManager
0x18000592b  mov     [rbp+840h+pProxyManager], rsi
0x18000592f  mov     this, r15
0x180005932  mov     rax, [rax]
0x180005935  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000593a  test    eax, eax
0x18000593c  jz      loc_180005D33
0x180005942  mov     [r13+0], esi
0x180005946  lea     pmkObjectName, [rsp+940h+pifdMoniker]; ppifdMoniker
0x18000594b  xor     r13d, r13d
0x18000594e  lea     punkObject, [rbp+840h+filetime]; pfiletime
0x180005952  lea     rdx, [rbp+840h+tmeb]; ptmpmkeqbuf
0x180005956  mov     qword ptr [rbp+840h+filetime.dwLowDateTime], r13
0x18000595a  mov     this, rbx; pmk
0x18000595d  call    ?GetMonikerCompareBuffer@@YAJPEAUIMoniker@@PEAVCTmpMkEqBuf@@PEAU_FILETIME@@PEAPEAUtagInterfaceData@@@Z; GetMonikerCompareBuffer(IMoniker *,CTmpMkEqBuf *,_FILETIME *,tagInterfaceData * *)
0x180005962  mov     ebx, eax
0x180005964  test    eax, eax
0x180005966  js      loc_180005DDF
0x18000596c  xorps   xmm0, xmm0
0x18000596f  lea     this, [rsp+940h+objectStream]; this
0x180005974  movups  xmmword ptr [rsp+940h+objectStream.lpVtbl], xmm0
0x180005979  call    ??0CAbstractMarshalingStream@@QEAA@XZ; CAbstractMarshalingStream::CAbstractMarshalingStream(void)
0x18000597e  lea     ecx, [rdi+1]
0x180005981  mov     qword ptr [rsp+940h+objectStream._lOffset], r13
0x180005986  lea     rax, ??_7CReadInterfaceDataFromInternalSourceMarshalingStream@@6B@; const CReadInterfaceDataFromInternalSourceMarshalingStream::`vftable'
0x18000598d  mov     [rbp+840h+objectStream._fFree], ecx
0x180005990  mov     [rsp+940h+objectStream.lpVtbl], rax
0x180005995  lea     rdx, IID_IUnknown; riid
0x18000599c  mov     eax, [rsp+940h+var_900]
0x1800059a0  mov     r9d, ecx; dwDestContext
0x1800059a3  not     eax
0x1800059a5  mov     [rsp+940h+objectStream._cbBufferSize], r13d
0x1800059aa  and     eax, ecx
0x1800059ac  mov     [rsp+940h+objectStream._pMInterfacePointer], r13
0x1800059b1  inc     eax
0x1800059b3  lea     this, [rsp+940h+objectStream]; pStm
0x1800059b8  mov     [rsp+940h+mshlflags], eax; mshlflags
0x1800059bc  mov     punkObject, r15; pUnk
0x1800059bf  mov     [rsp+940h+pvDestContext], r13; pvDestContext
0x1800059c4  mov     [rbp+840h+var_8B8], eax
0x1800059c7  call    cs:__imp_CoMarshalInterface
0x1800059cd  mov     rsi, [rsp+940h+pifdMoniker]
0x1800059d2  mov     ebx, eax
0x1800059d4  test    eax, eax
0x1800059d6  jnz     loc_180005C12
0x1800059dc  mov     eax, [rsp+940h+objectStream._cbDataSize]
0x1800059e0  lea     r8d, [rdi+28h]; dwBytes
0x1800059e4  mov     ecx, [rsp+940h+objectStream._cbBufferSize]
0x1800059e8  test    eax, eax
0x1800059ea  cmovnz  ecx, eax
0x1800059ed  mov     rax, [rsp+940h+objectStream._pMInterfacePointer]
0x1800059f2  xor     grfFlags, grfFlags; dwFlags
0x1800059f4  mov     [rax], ecx
0x1800059f6  mov     r12, [rsp+940h+objectStream._pMInterfacePointer]
0x1800059fb  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x180005a02  mov     [rsp+940h+objectStream._pMInterfacePointer], r13
0x180005a07  mov     [rbp+840h+objectStream._fFree], r13d
0x180005a0b  call    cs:__imp_HeapAlloc
0x180005a11  mov     rbx, rax
0x180005a14  test    rax, rax
0x180005a17  jz      loc_180005AA1
0x180005a1d  mov     [rax+4], r13d
0x180005a21  call    ?GetCurrentApartmentId@@YAKXZ; GetCurrentApartmentId(void)
0x180005a26  xor     r8d, r8d; dwLine
0x180005a29  mov     [rbx+18h], eax
0x180005a2c  lea     rdx, pszFile; "Unknown File"
0x180005a33  mov     [rbx+20h], r13
0x180005a37  lea     this, ?g_RotSem@@3VCOleStaticMutexSem@@A; this
0x180005a3e  mov     qword ptr [rbx+8], 0FFFFFFFFFFFFFFFFh
0x180005a46  mov     rdi, rbx
0x180005a49  mov     [rsp+940h+pifdMoniker], rbx
0x180005a4e  call    ?Request@COleStaticMutexSem@@QEAAXPEBDK0@Z; COleStaticMutexSem::Request(char const *,ulong,char const *)
0x180005a53  mov     r13, [rsp+940h+file]
0x180005a58  mov     r8d, 1
0x180005a5e  add     [r13+38h], r8w
0x180005a63  lea     r15, [r13+10h]
0x180005a67  movzx   eax, word ptr [r13+38h]
0x180005a6c  mov     [rbx], ax
0x180005a6f  mov     rdx, [r15]
0x180005a72  mov     this, [r15+8]
0x180005a76  cmp     rdx, this
0x180005a79  jz      loc_180005D50
0x180005a7f  xor     eax, eax
0x180005a81  sub     this, rdx
0x180005a84  sar     this, 3
0x180005a88  cmp     rax, this
0x180005a8b  jnb     loc_180005D50
0x180005a91  cmp     qword ptr [rdx+rax*8], 0
0x180005a96  jz      loc_180005C87
0x180005a9c  add     rax, punkObject
0x180005a9f  jmp     short loc_180005A88
0x180005aa1  lea     r15, ??_7CBaseMInterfacePointerMarshalingStream@@6B@; const CBaseMInterfacePointerMarshalingStream::`vftable'
0x180005aa8  mov     ebx, 8007000Eh
0x180005aad  mov     [rsp+940h+objectStream.lpVtbl], r15
0x180005ab2  cmp     [rbp+840h+objectStream._fFree], r13d
0x180005ab6  jnz     loc_180005DC6
0x180005abc  lea     rax, ??_7CAbstractStream@@6B@; const CAbstractStream::`vftable'
0x180005ac3  mov     [rsp+940h+objectStream.lpVtbl], rax
0x180005ac8  test    rdi, rdi
0x180005acb  jz      short loc_180005AE8
0x180005acd  mov     rax, [rdi+20h]
0x180005ad1  mov     this, r13
0x180005ad4  lock cmpxchg [rdi+20h], this
0x180005ada  test    rax, rax
0x180005add  jz      short loc_180005AE8
0x180005adf  mov     this, rax
0x180005ae2  call    cs:__imp_InternalCoUnregisterDisconnectCallback
0x180005ae8  test    r12, r12
0x180005aeb  jz      short loc_180005B47
0x180005aed  xorps   xmm0, xmm0
0x180005af0  lea     this, [rbp+840h+monikerStream]; this
0x180005af4  movups  xmmword ptr [rbp+840h+monikerStream.lpVtbl], xmm0
0x180005af8  call    ??0CAbstractMarshalingStream@@QEAA@XZ; CAbstractMarshalingStream::CAbstractMarshalingStream(void)
0x180005afd  mov     [rbp+840h+monikerStream.lpVtbl], r15
0x180005b01  lea     this, [rbp+840h+monikerStream]; pStream
0x180005b05  mov     qword ptr [rbp+840h+monikerStream._lOffset], 0
0x180005b0d  mov     [rbp+840h+monikerStream._pMInterfacePointer], r12
0x180005b11  mov     [rbp+840h+monikerStream._fFree], r13d
0x180005b15  mov     eax, [r12]
0x180005b19  mov     [rbp+840h+monikerStream._cbBufferSize], eax
0x180005b1c  lea     rax, ??_7CReadInterfaceDataFromInternalSourceMarshalingStream@@6B@; const CReadInterfaceDataFromInternalSourceMarshalingStream::`vftable'
0x180005b23  mov     [rbp+840h+monikerStream.lpVtbl], rax
0x180005b27  call    ?ReleaseMarshalingData@@YAXPEAUIStream@@@Z; ReleaseMarshalingData(IStream *)
0x180005b2c  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x180005b33  mov     punkObject, r12; lpMem
0x180005b36  xor     grfFlags, grfFlags; dwFlags
0x180005b38  call    cs:__imp_HeapFree
0x180005b3e  lea     this, [rbp+840h+monikerStream]; this
0x180005b42  call    ??1CBaseMInterfacePointerMarshalingStream@@MEAA@XZ; CBaseMInterfacePointerMarshalingStream::~CBaseMInterfacePointerMarshalingStream(void)
0x180005b47  test    rsi, rsi
0x180005b4a  jz      short loc_180005BA4
0x180005b4c  xorps   xmm0, xmm0
0x180005b4f  lea     this, [rbp+840h+monikerStream]; this
0x180005b53  movups  xmmword ptr [rbp+840h+monikerStream.lpVtbl], xmm0
0x180005b57  call    ??0CAbstractMarshalingStream@@QEAA@XZ; CAbstractMarshalingStream::CAbstractMarshalingStream(void)
0x180005b5c  mov     [rbp+840h+monikerStream.lpVtbl], r15
0x180005b60  lea     this, [rbp+840h+monikerStream]; pStream
0x180005b64  mov     qword ptr [rbp+840h+monikerStream._lOffset], 0
0x180005b6c  mov     [rbp+840h+monikerStream._pMInterfacePointer], rsi
0x180005b70  mov     [rbp+840h+monikerStream._fFree], r13d
0x180005b74  mov     eax, [rsi]
0x180005b76  mov     [rbp+840h+monikerStream._cbBufferSize], eax
0x180005b79  lea     rax, ??_7CReadInterfaceDataFromInternalSourceMarshalingStream@@6B@; const CReadInterfaceDataFromInternalSourceMarshalingStream::`vftable'
0x180005b80  mov     [rbp+840h+monikerStream.lpVtbl], rax
0x180005b84  call    ?ReleaseMarshalingData@@YAXPEAUIStream@@@Z; ReleaseMarshalingData(IStream *)
0x180005b89  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x180005b90  mov     punkObject, rsi; lpMem
0x180005b93  xor     grfFlags, grfFlags; dwFlags
0x180005b95  call    cs:__imp_HeapFree
0x180005b9b  lea     this, [rbp+840h+monikerStream]; this
0x180005b9f  call    ??1CBaseMInterfacePointerMarshalingStream@@MEAA@XZ; CBaseMInterfacePointerMarshalingStream::~CBaseMInterfacePointerMarshalingStream(void)
0x180005ba4  test    rdi, rdi
0x180005ba7  jz      loc_180005C4E
0x180005bad  cmp     r14d, 0FFFFFFFFh
0x180005bb1  jz      short loc_180005BE5
0x180005bb3  xor     r8d, r8d; dwLine
0x180005bb6  lea     rdx, pszFile; "Unknown File"
0x180005bbd  lea     this, ?g_RotSem@@3VCOleStaticMutexSem@@A; this
0x180005bc4  call    ?Request@COleStaticMutexSem@@QEAAXPEBDK0@Z; COleStaticMutexSem::Request(char const *,ulong,char const *)
0x180005bc9  mov     rax, [rsp+940h+file]
0x180005bce  lea     this, ?g_RotSem@@3VCOleStaticMutexSem@@A; this
0x180005bd5  mov     grfFlags, r14d
0x180005bd8  mov     rax, [rax+10h]
0x180005bdc  mov     [rax+rdx*8], r13
0x180005be0  call    ?Release@COleStaticMutexSem@@QEAAXXZ; COleStaticMutexSem::Release(void)
0x180005be5  test    rdi, rdi
0x180005be8  jz      short loc_180005C4E
0x180005bea  mov     this, rdi; this
0x180005bed  call    ??_GCROTItem@@QEAAPEAXI@Z; CROTItem::`scalar deleting destructor'(uint)
0x180005bf2  jmp     short loc_180005C4E
0x180005bf4  mov     ebx, 80070057h
0x180005bf9  xor     r13d, r13d
0x180005bfc  lea     r15, ??_7CBaseMInterfacePointerMarshalingStream@@6B@; const CBaseMInterfacePointerMarshalingStream::`vftable'
0x180005c03  jmp     loc_180005AC8
0x180005c08  mov     qword ptr [r15], 0FFFFFFFFFFFFFFFFh
0x180005c0f  xor     r13d, r13d
0x180005c12  lea     r15, ??_7CBaseMInterfacePointerMarshalingStream@@6B@; const CBaseMInterfacePointerMarshalingStream::`vftable'
0x180005c19  mov     [rsp+940h+objectStream.lpVtbl], r15
0x180005c1e  cmp     [rbp+840h+objectStream._fFree], r13d
0x180005c22  jnz     loc_180005DAD
0x180005c28  lea     rax, ??_7CAbstractStream@@6B@; const CAbstractStream::`vftable'
0x180005c2f  mov     [rsp+940h+objectStream.lpVtbl], rax
0x180005c34  test    ebx, ebx
0x180005c36  js      loc_180005AC8
0x180005c3c  mov     this, rsi; pv
0x180005c3f  call    cs:__imp_CoTaskMemFree
0x180005c45  mov     this, r12; pv
0x180005c48  call    cs:__imp_CoTaskMemFree
0x180005c4e  cmp     cs:?gfEnableTracing@@3HA, r13d; int gfEnableTracing
0x180005c55  jnz     loc_180005DF0
0x180005c5b  mov     eax, ebx
0x180005c5d  mov     this, [rbp+840h+var_40]
0x180005c64  xor     this, rsp; StackCookie
0x180005c67  call    __security_check_cookie
0x180005c6c  mov     rbx, [rsp+940h+arg_8]
0x180005c74  add     rsp, 910h
0x180005c7b  pop     r15
0x180005c7d  pop     r14
0x180005c7f  pop     r13
0x180005c81  pop     r12
0x180005c83  pop     rdi
0x180005c84  pop     rsi
0x180005c85  pop     rbp
0x180005c86  retn
0x180005c87  mov     [rdx+rax*8], rbx
0x180005c8b  mov     r14d, eax
0x180005c8e  cmp     eax, 0FFFFFFFFh
0x180005c91  jz      loc_180005D50
0x180005c97  movzx   r13d, word ptr [r13+38h]
0x180005c9c  lea     this, ?g_RotSem@@3VCOleStaticMutexSem@@A; this
0x180005ca3  shl     r13d, 10h
0x180005ca7  or      r13d, r14d
0x180005caa  call    ?Release@COleStaticMutexSem@@QEAAXXZ; COleStaticMutexSem::Release(void)
0x180005caf  mov     punkObject, [rsp+940h+file]
0x180005cb4  lea     rax, [rbp+840h+pvNotifyCookie]
0x180005cb8  mov     grfFlags, [rbp+840h+var_8B8]
0x180005cbb  add     punkObject, 8
0x180005cbf  mov     this, [rbp+840h+var_868]
0x180005cc3  mov     r9d, r13d
0x180005cc6  mov     [rbp+840h+pvNotifyCookie], 0
0x180005cce  mov     [rsp+940h+pvDestContext], rax
0x180005cd3  call    cs:__imp_InternalCoRegisterDisconnectCallback
0x180005cd9  mov     ebx, eax
0x180005cdb  test    eax, eax
0x180005cdd  js      loc_180005D9E
0x180005ce3  mov     rax, [rbp+840h+pvNotifyCookie]
0x180005ce7  mov     [rdi+20h], rax
0x180005ceb  call    cs:__imp_CoGetCurrentProcess
0x180005cf1  mov     ecx, [rsp+940h+var_900]
0x180005cf5  lea     r15, [rdi+8]
0x180005cf9  and     ecx, 2
0x180005cfc  mov     qword ptr [rsp+940h+function], r15
0x180005d01  mov     [rsp+940h+mshlflags], ecx
0x180005d05  lea     pmkObjectName, [rbp+840h+filetime]
0x180005d09  lea     this, [rbp+840h+tmeb]
0x180005d0d  mov     dword ptr [rsp+940h+pvDestContext], eax
0x180005d11  mov     punkObject, rsi
0x180005d14  mov     rdx, r12
0x180005d17  call    cs:__imp_InternalIrotRegister
0x180005d1d  mov     ebx, eax
0x180005d1f  test    eax, eax
0x180005d21  js      loc_180005C08
0x180005d27  mov     rax, [rbp+840h+var_860]
0x180005d2b  mov     [rax], r13d
0x180005d2e  jmp     loc_180005C0F
0x180005d33  mov     this, [rbp+840h+pProxyManager]
0x180005d37  mov     rax, [this]
0x180005d3a  mov     rax, [rax+10h]
0x180005d3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d43  xor     r13d, r13d
0x180005d46  mov     ebx, 80070057h
0x180005d4b  jmp     loc_180005C4E
0x180005d50  lea     rdx, [rsp+940h+pifdMoniker]; _Val
0x180005d55  mov     this, r15; this
0x180005d58  call    ??$_PushBackOne@AEBQEAVCROTItem@@@?$vector@PEAVCROTItem@@V?$allocator@PEAVCROTItem@@@utl@@@utl@@AEAA_NAEBQEAVCROTItem@@@Z; utl::vector<CROTItem *,utl::allocator<CROTItem *>>::_PushBackOne<CROTItem * const &>(CROTItem * const &)
0x180005d5d  test    al, al
0x180005d5f  jnz     short loc_180005D86
0x180005d61  lea     this, ?g_RotSem@@3VCOleStaticMutexSem@@A; this
0x180005d68  mov     ebx, 8007000Eh
  ... truncated ...
```
