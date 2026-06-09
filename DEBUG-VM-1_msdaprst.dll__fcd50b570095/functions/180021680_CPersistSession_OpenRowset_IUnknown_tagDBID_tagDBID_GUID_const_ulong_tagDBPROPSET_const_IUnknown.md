# CPersistSession::OpenRowset(IUnknown *,tagDBID *,tagDBID *,_GUID const &,ulong,tagDBPROPSET * const,IUnknown * *)

- ea: `0x180021680`
- end: `0x180022102`
- name: `?OpenRowset@CPersistSession@@UEAAJPEAUIUnknown@@PEAUtagDBID@@1AEBU_GUID@@KQEAUtagDBPROPSET@@PEAPEAU2@@Z`
- size: `2690`
- prototype: `__int64 __fastcall(CPersistSession *__hidden this, struct IUnknown *, struct tagDBID *, struct tagDBID *, const struct _GUID *, unsigned int, struct tagDBPROPSET *const, struct IUnknown **)`
- caller_count: `0`
- callee_count: `19`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180001d94`
- `0x18000266c`
- `0x1800145e0`
- `0x180015370`
- `0x1800158f8`
- `0x180015f14`
- `0x180015fb4`
- `0x180018914`
- `0x18001a6c8`
- `0x180020b24`
- `0x180020e74`
- `0x180021060`
- `0x180021680`
- `0x180022108`
- `0x180022814`
- `0x180022d40`
- `0x18002cd54`
- `0x18002d574`
- `0x180030010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800218c9`
- `msvcrt!_wcsnicmp` at `0x1800218e4`
- `msvcrt!_wcsnicmp` at `0x1800218ff`
- `msvcrt!_wcsnicmp` at `0x180021a5d`
- `msvcrt!_wcsnicmp` at `0x180021aab`
- `msvcrt!_wcsnicmp` at `0x180021ad3`
- `msvcrt!_wcsnicmp` at `0x1800218c9`
- `msvcrt!_wcsnicmp` at `0x1800218e4`
- `msvcrt!_wcsnicmp` at `0x1800218ff`
- `msvcrt!_wcsnicmp` at `0x180021a5d`
- `msvcrt!_wcsnicmp` at `0x180021aab`
- `msvcrt!_wcsnicmp` at `0x180021ad3`
- `msvcrt!_wfsopen` at `0x180021af2`
- `msvcrt!_wfsopen` at `0x180021af2`
- `msvcrt!_get_osfhandle` at `0x180021b0f`
- `msvcrt!_get_osfhandle` at `0x180021b0f`
- `msvcrt!_fileno` at `0x180021b07`
- `msvcrt!_fileno` at `0x180021b07`
- `msvcrt!fclose` at `0x180021b32`
- `msvcrt!fclose` at `0x180021b32`
- `KERNEL32!GetFileType` at `0x180021b1e`
- `KERNEL32!GetFileType` at `0x180021b1e`
- `KERNEL32!GetCurrentThreadId` at `0x1800216c9`
- `KERNEL32!GetCurrentThreadId` at `0x1800216c9`
- `KERNEL32!LeaveCriticalSection` at `0x180021748`
- `KERNEL32!LeaveCriticalSection` at `0x1800217e3`
- `KERNEL32!LeaveCriticalSection` at `0x18002184a`
- `KERNEL32!LeaveCriticalSection` at `0x1800218ae`
- `KERNEL32!LeaveCriticalSection` at `0x18002208c`
- `KERNEL32!LeaveCriticalSection` at `0x1800220e4`
- `KERNEL32!LeaveCriticalSection` at `0x180021748`
- `KERNEL32!LeaveCriticalSection` at `0x1800217e3`
- `KERNEL32!LeaveCriticalSection` at `0x18002184a`
- `KERNEL32!LeaveCriticalSection` at `0x1800218ae`
- `KERNEL32!LeaveCriticalSection` at `0x18002208c`
- `KERNEL32!LeaveCriticalSection` at `0x1800220e4`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180021c19`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180022000`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180021c19`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180022000`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180021703`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180021703`
- `MSDART!UMSEnterCSWraper` at `0x1800216b1`
- `MSDART!UMSEnterCSWraper` at `0x1800216b1`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall CPersistSession::OpenRowset(
        CPersistSession *this,
        struct IUnknown *a2,
        struct tagDBID *a3,
        struct tagDBID *a4,
        struct _GUID *a5,
        unsigned int a6,
        struct tagDBPROPSET *const a7,
        struct IUnknown **a8)
{
  char *v11; // r15
  _DWORD *v12; // rbx
  DWORD *v13; // rsi
  _DWORD *v14; // rdi
  int v15; // ecx
  unsigned int v16; // r14d
  bool v17; // zf
  __int64 v18; // rcx
  LPOLESTR pwszName; // rcx
  CStreamWrapper *v21; // rax
  _QWORD *v22; // rdx
  HINSTANCE ResourceInstance; // rax
  CPersistSession *v24; // rcx
  int v25; // r12d
  int v26; // eax
  const wchar_t *v27; // rcx
  FILE *v28; // rax
  FILE *v29; // r14
  int v30; // eax
  void *osfhandle; // rax
  int Instance; // eax
  int v33; // r14d
  CFileStream *v34; // r12
  const unsigned __int16 *v35; // r8
  int v36; // r14d
  unsigned int v37; // edx
  CPersistSession *v38; // rcx
  CStreamWrapper *v39; // r12
  HINSTANCE v40; // rdx
  unsigned int v41; // r9d
  CStreamWrapper *v42; // rax
  int v43; // eax
  int v44; // r13d
  int v45; // eax
  int v46; // r13d
  int v47; // eax
  int v48; // r12d
  int v49; // eax
  int v50; // r12d
  int v51; // eax
  int v52; // r12d
  int v53; // eax
  int v54; // r12d
  int v55; // eax
  int v56; // r12d
  __int64 v57; // [rsp+30h] [rbp-B8h] BYREF
  __int64 (__fastcall ***v58)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-B0h] BYREF
  struct IUnknown *v59; // [rsp+40h] [rbp-A8h] BYREF
  _QWORD v60[2]; // [rsp+48h] [rbp-A0h] BYREF
  struct IUnknown *v61[4]; // [rsp+58h] [rbp-90h] BYREF
  char v62[8]; // [rsp+78h] [rbp-70h] BYREF
  IErrorInfo *pperrinfo; // [rsp+80h] [rbp-68h] BYREF
  int v64; // [rsp+88h] [rbp-60h]
  __int64 v65; // [rsp+90h] [rbp-58h]
  _QWORD *v66; // [rsp+A0h] [rbp-48h]
  char *v67; // [rsp+A8h] [rbp-40h]
  CStreamWrapper *v70; // [rsp+108h] [rbp+20h] BYREF

  v11 = (char *)this + 48;
  v61[3] = (struct IUnknown *)((char *)this + 48);
  UMSEnterCSWraper((char *)this + 48);
  v12 = v11 + 12;
  v61[2] = (struct IUnknown *)(v11 + 12);
  v13 = (DWORD *)(v11 + 8);
  if ( !*((_DWORD *)v11 + 3) )
    *v13 = GetCurrentThreadId();
  v60[1] = v11 + 8;
  ++*v12;
  v14 = v11 + 16;
  v61[1] = (struct IUnknown *)(v11 + 16);
  ++*((_DWORD *)v11 + 4);
  v67 = v11;
  v70 = (CStreamWrapper *)*((_QWORD *)this + 565);
  SetErrorInfo(0, 0);
  *((GUID *)this + 6) = IID_IOpenRowset;
  *((_DWORD *)this + 1053) = 0;
  if ( a4 )
  {
    v15 = -2147217867;
    goto LABEL_5;
  }
  if ( !a3 )
  {
    v15 = -2147024809;
    goto LABEL_5;
  }
  if ( a2 )
  {
    v15 = -2147217886;
LABEL_5:
    v16 = Exit(v15, 0);
    --*v14;
    v17 = (*v12)-- == 1;
    if ( v17 )
      *v13 = -1;
    goto LABEL_7;
  }
  v59 = 0;
  v61[0] = 0;
  v60[0] = 0;
  v58 = 0;
  v57 = 0;
  if ( a3->eKind != 2 )
  {
    v16 = Exit(-2147217865, 0);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v57);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v58);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(v60);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v59);
    --*v14;
    v17 = (*v12)-- == 1;
    if ( v17 )
      *v13 = -1;
    goto LABEL_7;
  }
  pwszName = a3->uName.pwszName;
  if ( !pwszName )
  {
    v16 = Exit(-2147217865, 0);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v57);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v58);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(v60);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v59);
    --*v14;
    v17 = (*v12)-- == 1;
    if ( v17 )
      *v13 = -1;
    goto LABEL_7;
  }
  if ( !*pwszName )
  {
    v16 = Exit(-2147217865, 0);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v57);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v58);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(v60);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v59);
    --*v14;
    v17 = (*v12)-- == 1;
    if ( v17 )
      *v13 = -1;
    goto LABEL_7;
  }
  if ( !_wcsnicmp(pwszName, L"http://", 7u)
    || !_wcsnicmp(a3->uName.pwszName, L"https://", 8u)
    || !_wcsnicmp(a3->uName.pwszName, L"ftp://", 6u) )
  {
    LODWORD(a4) = 1;
  }
  v21 = *(CStreamWrapper **)v70;
  v70 = v21;
  v22 = *(_QWORD **)v21;
  v66 = *(_QWORD **)v21;
  if ( (_DWORD)a4 == 1 )
  {
    ResourceInstance = GetResourceInstance(g_hInstancePersistMain);
    v25 = 0;
    if ( !((unsigned int (__fastcall *)(CStreamWrapper *, LPOLESTR, HINSTANCE, __int64, int))v66[6])(
            v70,
            a3->uName.pwszName,
            ResourceInstance,
            2001,
            2002) )
    {
      CError::PostError((CPersistSession *)((char *)this + 80), -2147467259, 0x7D0u);
      if ( (bidGblFlags & 2) != 0 && off_180048C70[0] )
        bidTraceW(off_1800481F8[0], 122880, off_180048C70[0], 2147500037LL, 120);
      ThrowHR(-2147467259);
    }
    LODWORD(v70) = 0;
  }
  else
  {
    if ( !((unsigned int (__fastcall *)(CStreamWrapper *))v22[9])(v21) )
    {
      CError::PostError((CPersistSession *)((char *)this + 80), -2147467259, 0x7D0u);
      if ( (bidGblFlags & 2) != 0 && off_180048C68[0] )
        bidTraceW(off_1800481F8[0], 133120, off_180048C68[0], 2147500037LL, 130);
      ThrowHR(-2147467259);
    }
    LODWORD(v70) = 0;
    v25 = 0;
    if ( _wcsnicmp(a3->uName.pwszName, L"file://", 7u) )
      goto LABEL_46;
  }
  if ( !(unsigned int)CPersistSession::GetURLMonDLL(v24) )
  {
    if ( (unsigned int)((__int64 (__fastcall *)(_QWORD, LPOLESTR, _QWORD))CPersistSession::m_pIsValidURL)(
                         0,
                         a3->uName.pwszName,
                         0) )
    {
      LODWORD(v70) = 0;
    }
    else
    {
      LODWORD(v70) = 1;
      if ( _wcsnicmp(a3->uName.pwszName, L"file://", 7u) )
        goto LABEL_53;
    }
  }
LABEL_46:
  v26 = _wcsnicmp(a3->uName.pwszName, L"file://", 7u);
  v27 = a3->uName.pwszName;
  if ( !v26 )
    v27 += 7;
  v28 = _wfsopen(v27, L"r", 64);
  v29 = v28;
  if ( v28 )
  {
    v30 = _fileno(v28);
    osfhandle = (void *)_get_osfhandle(v30);
    if ( osfhandle != (void *)-1LL && GetFileType(osfhandle) == 1 )
      v25 = 1;
    fclose(v29);
    if ( v25 )
    {
LABEL_53:
      Instance = ATL::CComObject<CFileStream>::CreateInstance(v61);
      v33 = Instance;
      if ( Instance < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180048C60[0] )
          bidTraceW(off_1800481F8[0], 188416, off_180048C60[0], (unsigned int)Instance, 184);
        ThrowHR(v33);
      }
      v34 = (CFileStream *)v61[0];
      ((void (__fastcall *)(struct IUnknown *))v61[0]->lpVtbl->AddRef)(v61[0]);
      v36 = CFileStream::Open(v34, a3->uName.pwszName, v35);
      if ( v36 >= 0 )
        ATL::AtlComPtrAssign(&v59, (struct IUnknown *)v34);
      (*(void (__fastcall **)(CFileStream *))(*(_QWORD *)v34 + 16LL))(v34);
      v39 = 0;
      if ( v36 < 0 )
      {
        if ( v36 == -2147024864 || !(_DWORD)v70 )
          goto LABEL_67;
        v36 = CPersistSession::OpenStreamFromURL(v38, a3->uName.pwszName, (struct IStream **)&v59);
        if ( v36 < 0 )
        {
          GetErrorInfo(0, &pperrinfo);
          v64 = 0;
          v65 = 0;
          if ( !pperrinfo )
            CPersistErrorCache::AddHMODULEError((CPersistErrorCache *)v62, v40, v36, v41);
          CPersistErrorCache::~CPersistErrorCache((CPersistErrorCache *)v62);
LABEL_67:
          if ( (bidGblFlags & 2) != 0 && off_180048C58[0] )
            bidTraceW(off_1800481F8[0], 207872, off_180048C58[0], (unsigned int)v36, 203);
          ThrowHR(v36);
        }
      }
      v42 = (CStreamWrapper *)MMMAlloc(0x30u, v37);
      v70 = v42;
      if ( v42 )
        v39 = CStreamWrapper::CStreamWrapper(v42, 1);
      v70 = v39;
      if ( !v39 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180048C50[0] )
          bidTraceW(off_1800481F8[0], 216064, off_180048C50[0], 2147942414LL, 211);
        ThrowHR(-2147024882);
      }
      v43 = CStreamWrapper::SetStream(v39, v59);
      v44 = v43;
      if ( v43 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180048C48[0] )
          bidTraceW(off_1800481F8[0], 219136, off_180048C48[0], (unsigned int)v43, 214);
        ThrowHR(v44);
      }
      v45 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *))this + 9))(
              *((_QWORD *)this + 9),
              &IID_IRDSService,
              v60);
      v46 = v45;
      if ( v45 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180048C40[0] )
          bidTraceW(off_1800481F8[0], 222208, off_180048C40[0], (unsigned int)v45, 217);
        ThrowHR(v46);
      }
      v47 = (*(__int64 (__fastcall **)(_QWORD, GUID *, CStreamWrapper *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v60[0] + 32LL))(
              v60[0],
              &IID_IRowset,
              v39,
              &v58);
      v48 = v47;
      if ( v47 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180048C38[0] )
          bidTraceW(off_1800481F8[0], 223232, off_180048C38[0], (unsigned int)v47, 218);
        ThrowHR(v48);
      }
      v49 = (**v58)(v58, &IID_IRowsetConnection, &v57);
      v50 = v49;
      if ( v49 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180048C30[0] )
          bidTraceW(off_1800481F8[0], 224256, off_180048C30[0], (unsigned int)v49, 219);
        ThrowHR(v50);
      }
      v51 = (*(__int64 (__fastcall **)(__int64, CPersistSession *))(*(_QWORD *)v57 + 24LL))(v57, this);
      v52 = v51;
      if ( v51 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180048C28[0] )
          bidTraceW(off_1800481F8[0], 226304, off_180048C28[0], (unsigned int)v51, 221);
        ThrowHR(v52);
      }
      v53 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v57 + 56LL))(v57, 0);
      v54 = v53;
      if ( v53 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180048C20[0] )
          bidTraceW(off_1800481F8[0], 227328, off_180048C20[0], (unsigned int)v53, 222);
        ThrowHR(v54);
      }
      v55 = (**v58)(v58, a5, (__int64 *)a8);
      v56 = v55;
      if ( v55 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180048C18[0] )
          bidTraceW(off_1800481F8[0], 228352, off_180048C18[0], (unsigned int)v55, 223);
        ThrowHR(v56);
      }
      CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v70);
      CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v57);
      CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v58);
      CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(v60);
      CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v59);
      v15 = v36;
      goto LABEL_5;
    }
  }
  GetErrorInfo(0, &pperrinfo);
  v64 = 0;
  v65 = 0;
  CPersistErrorCache::AddInternalError((CPersistErrorCache *)v62, -2147287038, a3->uName.pwszName, 0x82u);
  v16 = Exit(-2147287038, 0);
  CPersistErrorCache::~CPersistErrorCache((CPersistErrorCache *)v62);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v57);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v58);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(v60);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v59);
  --*v14;
  v17 = (*v12)-- == 1;
  if ( v17 )
    *v13 = -1;
LABEL_7:
  v18 = *(_QWORD *)v11;
  --*(_DWORD *)(v18 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v18 + 8));
  return v16;
}

```

## disassembly

```asm
0x180021680  mov     [rsp+arg_8], rdx
0x180021685  mov     [rsp+arg_0], rcx
0x18002168a  push    rbx
0x18002168b  push    rsi
0x18002168c  push    rdi
0x18002168d  push    r12
0x18002168f  push    r13
0x180021691  push    r14
0x180021693  push    r15
0x180021695  sub     rsp, 0B0h
0x18002169c  mov     r12, r9
0x18002169f  mov     r13, r8
0x1800216a2  mov     r14, rcx
0x1800216a5  lea     r15, [rcx+30h]
0x1800216a9  mov     [rsp+0E8h+var_78], r15
0x1800216ae  mov     rcx, r15
0x1800216b1  call    cs:__imp_UMSEnterCSWraper
0x1800216b7  lea     rbx, [r15+0Ch]
0x1800216bb  mov     [rsp+0E8h+var_80], rbx
0x1800216c0  lea     rsi, [r15+8]
0x1800216c4  cmp     dword ptr [rbx], 0
0x1800216c7  jnz     short loc_1800216D1
0x1800216c9  call    cs:__imp_GetCurrentThreadId
0x1800216cf  mov     [rsi], eax
0x1800216d1  mov     [rsp+0E8h+var_98], rsi
0x1800216d6  mov     eax, 1
0x1800216db  add     [rbx], eax
0x1800216dd  lea     rdi, [r15+10h]
0x1800216e1  mov     [rsp+0E8h+var_88], rdi
0x1800216e6  add     [rdi], eax
0x1800216e8  mov     [rsp+0E8h+var_40], r15
0x1800216f0  mov     rax, [r14+11A8h]
0x1800216f7  mov     [rsp+0E8h+arg_18], rax
0x1800216ff  xor     edx, edx; perrinfo
0x180021701  xor     ecx, ecx; dwReserved
0x180021703  call    cs:__imp_SetErrorInfo
0x180021709  movups  xmm0, xmmword ptr cs:IID_IOpenRowset.Data1
0x180021710  movdqu  xmmword ptr [r14+60h], xmm0
0x180021716  xor     ecx, ecx
0x180021718  mov     [r14+1074h], ecx
0x18002171f  test    r12, r12
0x180021722  jz      short loc_180021756
0x180021724  mov     ecx, 80040E35h; int
0x180021729  xor     edx, edx; unsigned int
0x18002172b  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180021730  mov     r14d, eax
0x180021733  or      edx, 0FFFFFFFFh
0x180021736  add     [rdi], edx
0x180021738  add     [rbx], edx
0x18002173a  jnz     short loc_18002173E
0x18002173c  mov     [rsi], edx
0x18002173e  mov     rcx, [r15]
0x180021741  dec     dword ptr [rcx+30h]
0x180021744  add     rcx, 8; lpCriticalSection
0x180021748  call    cs:__imp_LeaveCriticalSection
0x18002174e  mov     eax, r14d
0x180021751  jmp     loc_1800220EF
0x180021756  test    r13, r13
0x180021759  jnz     short loc_180021762
0x18002175b  mov     ecx, 80070057h
0x180021760  jmp     short loc_180021729
0x180021762  cmp     [rsp+0E8h+arg_8], r12
0x18002176a  jz      short loc_180021773
0x18002176c  mov     ecx, 80040E22h
0x180021771  jmp     short loc_180021729
0x180021773  mov     [rsp+0E8h+var_A8], r12
0x180021778  mov     [rsp+0E8h+var_90], r12
0x18002177d  mov     [rsp+0E8h+var_A0], r12
0x180021782  mov     [rsp+0E8h+var_B0], r12
0x180021787  mov     [rsp+0E8h+var_B8], r12
0x18002178c  cmp     dword ptr [r13+10h], 2
0x180021791  jz      short loc_1800217F1
0x180021793  xor     edx, edx; unsigned int
0x180021795  mov     ecx, 80040E37h; int
0x18002179a  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x18002179f  mov     r14d, eax
0x1800217a2  lea     rcx, [rsp+0E8h+var_B8]
0x1800217a7  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x1800217ac  nop
0x1800217ad  lea     rcx, [rsp+0E8h+var_B0]
0x1800217b2  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x1800217b7  nop
0x1800217b8  lea     rcx, [rsp+0E8h+var_A0]
0x1800217bd  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x1800217c2  nop
0x1800217c3  lea     rcx, [rsp+0E8h+var_A8]
0x1800217c8  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x1800217cd  nop
0x1800217ce  or      edx, 0FFFFFFFFh
0x1800217d1  add     [rdi], edx
0x1800217d3  add     [rbx], edx
0x1800217d5  jnz     short loc_1800217D9
0x1800217d7  mov     [rsi], edx
0x1800217d9  mov     rcx, [r15]
0x1800217dc  dec     dword ptr [rcx+30h]
0x1800217df  add     rcx, 8; lpCriticalSection
0x1800217e3  call    cs:__imp_LeaveCriticalSection
0x1800217e9  mov     eax, r14d
0x1800217ec  jmp     loc_1800220EF
0x1800217f1  mov     rcx, [r13+18h]; String1
0x1800217f5  test    rcx, rcx
0x1800217f8  jnz     short loc_180021858
0x1800217fa  xor     edx, edx; unsigned int
0x1800217fc  mov     ecx, 80040E37h; int
0x180021801  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180021806  mov     r14d, eax
0x180021809  lea     rcx, [rsp+0E8h+var_B8]
0x18002180e  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180021813  nop
0x180021814  lea     rcx, [rsp+0E8h+var_B0]
0x180021819  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x18002181e  nop
0x18002181f  lea     rcx, [rsp+0E8h+var_A0]
0x180021824  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180021829  nop
0x18002182a  lea     rcx, [rsp+0E8h+var_A8]
0x18002182f  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180021834  nop
0x180021835  or      edx, 0FFFFFFFFh
0x180021838  add     [rdi], edx
0x18002183a  add     [rbx], edx
0x18002183c  jnz     short loc_180021840
0x18002183e  mov     [rsi], edx
0x180021840  mov     rcx, [r15]
0x180021843  dec     dword ptr [rcx+30h]
0x180021846  add     rcx, 8; lpCriticalSection
0x18002184a  call    cs:__imp_LeaveCriticalSection
0x180021850  mov     eax, r14d
0x180021853  jmp     loc_1800220EF
0x180021858  cmp     [rcx], r12w
0x18002185c  jnz     short loc_1800218BC
0x18002185e  xor     edx, edx; unsigned int
0x180021860  mov     ecx, 80040E37h; int
0x180021865  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x18002186a  mov     r14d, eax
0x18002186d  lea     rcx, [rsp+0E8h+var_B8]
0x180021872  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180021877  nop
0x180021878  lea     rcx, [rsp+0E8h+var_B0]
0x18002187d  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180021882  nop
0x180021883  lea     rcx, [rsp+0E8h+var_A0]
0x180021888  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x18002188d  nop
0x18002188e  lea     rcx, [rsp+0E8h+var_A8]
0x180021893  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180021898  nop
0x180021899  or      edx, 0FFFFFFFFh
0x18002189c  add     [rdi], edx
0x18002189e  add     [rbx], edx
0x1800218a0  jnz     short loc_1800218A4
0x1800218a2  mov     [rsi], edx
0x1800218a4  mov     rcx, [r15]
0x1800218a7  dec     dword ptr [rcx+30h]
0x1800218aa  add     rcx, 8; lpCriticalSection
0x1800218ae  call    cs:__imp_LeaveCriticalSection
0x1800218b4  mov     eax, r14d
0x1800218b7  jmp     loc_1800220EF
0x1800218bc  mov     r8d, 7; MaxCount
0x1800218c2  lea     rdx, aHttp; "http://"
0x1800218c9  call    cs:__imp__wcsnicmp
0x1800218cf  test    eax, eax
0x1800218d1  jz      short loc_180021909
0x1800218d3  mov     r8d, 8; MaxCount
0x1800218d9  lea     rdx, aHttps; "https://"
0x1800218e0  mov     rcx, [r13+18h]; String1
0x1800218e4  call    cs:__imp__wcsnicmp
0x1800218ea  test    eax, eax
0x1800218ec  jz      short loc_180021909
0x1800218ee  mov     r8d, 6; MaxCount
0x1800218f4  lea     rdx, aFtp; "ftp://"
0x1800218fb  mov     rcx, [r13+18h]; String1
0x1800218ff  call    cs:__imp__wcsnicmp
0x180021905  test    eax, eax
0x180021907  jnz     short loc_18002190F
0x180021909  mov     r12d, 1
0x18002190f  mov     rax, [rsp+0E8h+arg_18]
0x180021917  mov     rax, [rax]
0x18002191a  mov     [rsp+0E8h+arg_18], rax
0x180021922  mov     rdx, [rax]
0x180021925  mov     [rsp+0E8h+var_48], rdx
0x18002192d  cmp     r12d, 1
0x180021931  jnz     loc_1800219DA
0x180021937  mov     rcx, cs:?g_hInstancePersistMain@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x18002193e  call    ?GetResourceInstance@@YAPEAUHINSTANCE__@@PEAU1@@Z; GetResourceInstance(HINSTANCE__ *)
0x180021943  mov     [rsp+0E8h+var_C8], 7D2h
0x18002194b  mov     r9d, 7D1h
0x180021951  mov     r8, rax
0x180021954  mov     rdx, [r13+18h]
0x180021958  mov     rcx, [rsp+0E8h+arg_18]
0x180021960  mov     rax, [rsp+0E8h+var_48]
0x180021968  mov     rax, [rax+30h]
0x18002196c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021971  xor     r12d, r12d
0x180021974  test    eax, eax
0x180021976  jnz     short loc_1800219CD
0x180021978  mov     ebx, 80004005h
0x18002197d  mov     r8d, 7D0h; unsigned int
0x180021983  mov     edx, ebx; int
0x180021985  lea     rcx, [r14+50h]; this
0x180021989  call    ?PostError@CError@@QEAAXJK@Z; CError::PostError(long,ulong)
0x18002198e  test    byte ptr cs:_bidGblFlags, 2
0x180021995  jz      short loc_1800219C6
0x180021997  mov     rax, cs:off_180048C70; "<CPersistSession::OpenRowset|ADO|ERR>  "...
0x18002199e  test    rax, rax
0x1800219a1  jz      short loc_1800219C6
0x1800219a3  mov     [rsp+0E8h+var_C8], 78h ; 'x'
0x1800219ab  mov     r9d, ebx
0x1800219ae  mov     r8, cs:off_180048C70; "<CPersistSession::OpenRowset|ADO|ERR>  "...
0x1800219b5  mov     edx, 1E000h
0x1800219ba  mov     rcx, cs:off_1800481F8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800219c1  call    _bidTraceW
0x1800219c6  mov     ecx, ebx; int
0x1800219c8  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800219cd  mov     dword ptr [rsp+0E8h+arg_18], r12d
0x1800219d5  jmp     loc_180021A6F
0x1800219da  mov     rcx, rax
0x1800219dd  mov     rax, [rdx+48h]
0x1800219e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800219e6  xor     ecx, ecx; this
0x1800219e8  test    eax, eax
0x1800219ea  jnz     short loc_180021A41
0x1800219ec  mov     ebx, 80004005h
0x1800219f1  mov     r8d, 7D0h; unsigned int
0x1800219f7  mov     edx, ebx; int
0x1800219f9  lea     rcx, [r14+50h]; this
0x1800219fd  call    ?PostError@CError@@QEAAXJK@Z; CError::PostError(long,ulong)
0x180021a02  test    byte ptr cs:_bidGblFlags, 2
0x180021a09  jz      short loc_180021A3A
0x180021a0b  mov     rax, cs:off_180048C68; "<CPersistSession::OpenRowset|ADO|ERR>  "...
0x180021a12  test    rax, rax
0x180021a15  jz      short loc_180021A3A
0x180021a17  mov     [rsp+0E8h+var_C8], 82h
0x180021a1f  mov     r9d, ebx
0x180021a22  mov     r8, cs:off_180048C68; "<CPersistSession::OpenRowset|ADO|ERR>  "...
0x180021a29  mov     edx, 20800h
0x180021a2e  mov     rcx, cs:off_1800481F8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180021a35  call    _bidTraceW
0x180021a3a  mov     ecx, ebx; int
0x180021a3c  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180021a41  mov     dword ptr [rsp+0E8h+arg_18], ecx
0x180021a48  test    r12d, r12d
0x180021a4b  jnz     short loc_180021A6C
0x180021a4d  lea     r8d, [r12+7]; MaxCount
0x180021a52  lea     rdx, aFile; "file://"
0x180021a59  mov     rcx, [r13+18h]; String1
0x180021a5d  call    cs:__imp__wcsnicmp
0x180021a63  xor     r12d, r12d
0x180021a66  test    eax, eax
0x180021a68  jnz     short loc_180021AC2
0x180021a6a  jmp     short loc_180021A6F
0x180021a6c  xor     r12d, r12d
0x180021a6f  call    ?GetURLMonDLL@CPersistSession@@AEAAJXZ; CPersistSession::GetURLMonDLL(void)
0x180021a74  test    eax, eax
0x180021a76  jnz     short loc_180021AC2
0x180021a78  xor     r8d, r8d
0x180021a7b  mov     rdx, [r13+18h]
0x180021a7f  xor     ecx, ecx
0x180021a81  mov     rax, cs:?m_pIsValidURL@CPersistSession@@0P6AJPEAUIBindCtx@@PEBGK@ZEA; long (*CPersistSession::m_pIsValidURL)(IBindCtx *,ushort const *,ulong)
0x180021a88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a8d  test    eax, eax
0x180021a8f  jnz     short loc_180021ABA
0x180021a91  mov     dword ptr [rsp+0E8h+arg_18], 1
0x180021a9c  lea     r8d, [rax+7]; MaxCount
0x180021aa0  lea     rdx, aFile; "file://"
0x180021aa7  mov     rcx, [r13+18h]; String1
0x180021aab  call    cs:__imp__wcsnicmp
0x180021ab1  test    eax, eax
0x180021ab3  jz      short loc_180021AC2
0x180021ab5  jmp     loc_180021B41
0x180021aba  mov     dword ptr [rsp+0E8h+arg_18], r12d
0x180021ac2  mov     r8d, 7; MaxCount
0x180021ac8  lea     rdx, aFile; "file://"
0x180021acf  mov     rcx, [r13+18h]; String1
0x180021ad3  call    cs:__imp__wcsnicmp
0x180021ad9  mov     rcx, [r13+18h]
0x180021add  mov     r8d, 40h ; '@'; ShFlag
0x180021ae3  lea     rdx, aR; "r"
0x180021aea  test    eax, eax
0x180021aec  jnz     short loc_180021AF2
0x180021aee  add     rcx, 0Eh; FileName
0x180021af2  call    cs:__imp__wfsopen
0x180021af8  mov     r14, rax
0x180021afb  test    rax, rax
0x180021afe  jz      loc_180021FF6
0x180021b04  mov     rcx, rax; Stream
0x180021b07  call    cs:__imp__fileno
0x180021b0d  mov     ecx, eax; FileHandle
0x180021b0f  call    cs:__imp__get_osfhandle
0x180021b15  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180021b19  jz      short loc_180021B2F
0x180021b1b  mov     rcx, rax; hFile
0x180021b1e  call    cs:__imp_GetFileType
0x180021b24  mov     ecx, 1
0x180021b29  cmp     eax, ecx
0x180021b2b  cmovz   r12d, ecx
0x180021b2f  mov     rcx, r14; Stream
0x180021b32  call    cs:__imp_fclose
0x180021b38  test    r12d, r12d
0x180021b3b  jz      loc_180021FF3
  ... truncated ...
```
