# CPersistErrorCache::AddError(long,ulong,IErrorInfo *)

- ea: `0x1800153fc`
- end: `0x1800158f2`
- name: `?AddError@CPersistErrorCache@@AEAAXJKPEAUIErrorInfo@@@Z`
- size: `1270`
- prototype: `void(CPersistErrorCache *__hidden this, int, unsigned int, struct IErrorInfo *)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800158f8`
- `0x180015b78`

## callees

- `0x180001d94`
- `0x18000266c`
- `0x1800027c0`
- `0x180015324`
- `0x1800153fc`
- `0x180016b30`
- `0x18001a6c8`
- `0x18002cd54`
- `0x18002e060`
- `0x180030010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800154a0`
- `ole32!CoCreateInstance` at `0x1800155d4`
- `ole32!CoCreateInstance` at `0x1800154a0`
- `ole32!CoCreateInstance` at `0x1800155d4`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CPersistErrorCache::AddError(
        CPersistErrorCache *this,
        unsigned int a2,
        unsigned int a3,
        struct IErrorInfo *a4)
{
  _QWORD *v7; // r14
  void (__fastcall ***v8)(_QWORD, GUID *, LPVOID *); // rcx
  HRESULT v9; // eax
  int v10; // ebx
  int v11; // eax
  int v12; // ebx
  HRESULT v13; // eax
  int v14; // ebx
  int v15; // eax
  int v16; // ebx
  unsigned int i; // r14d
  int v18; // ebx
  int v19; // ebx
  CPersistErrorInfo *v20; // rbx
  unsigned int v21; // edx
  CPersistErrorInfo *v22; // rax
  CPersistErrorInfo *v23; // rsi
  __int64 v24; // rcx
  int v25; // ebx
  LPVOID v26; // [rsp+40h] [rbp-49h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-41h] BYREF
  unsigned int v28; // [rsp+50h] [rbp-39h] BYREF
  CPersistErrorInfo *v29; // [rsp+58h] [rbp-31h] BYREF
  CPersistErrorInfo *v30; // [rsp+60h] [rbp-29h] BYREF
  __int64 v31; // [rsp+68h] [rbp-21h] BYREF
  _OWORD v32[3]; // [rsp+70h] [rbp-19h] BYREF

  memset(v32, 0, 44);
  v28 = 1;
  v26 = 0;
  ppv = 0;
  if ( a4 )
  {
    v7 = (_QWORD *)((char *)this + 8);
    v8 = (void (__fastcall ***)(_QWORD, GUID *, LPVOID *))*((_QWORD *)this + 1);
    if ( v8 )
    {
      (**v8)(v8, &IID_IErrorRecords, &ppv);
    }
    else
    {
      if ( ((__int64 (__fastcall *)(struct IErrorInfo *, GUID *, LPVOID *))a4->lpVtbl->QueryInterface)(
             a4,
             &IID_IErrorRecords,
             &ppv) >= 0 )
      {
        *v7 = a4;
        ((void (__fastcall *)(struct IErrorInfo *))a4->lpVtbl->AddRef)(a4);
        goto LABEL_15;
      }
      v9 = CoCreateInstance(&CLSID_EXTENDEDERRORINFO, 0, 1u, &IID_IErrorRecords, &ppv);
      v10 = v9;
      if ( v9 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( off_180048A50[0] )
            bidTraceW(off_1800481E8[0], 455680, off_180048A50[0], (unsigned int)v9, 445);
        }
        ThrowHR(v10);
      }
      v11 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, _QWORD *))ppv)(ppv, &IID_IErrorInfo, v7);
      v12 = v11;
      if ( v11 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180048A48[0] )
          bidTraceW(off_1800481E8[0], 459776, off_180048A48[0], (unsigned int)v11, 449);
        ThrowHR(v12);
      }
    }
    if ( ((__int64 (__fastcall *)(struct IErrorInfo *, GUID *, LPVOID *))a4->lpVtbl->QueryInterface)(
           a4,
           &IID_IErrorRecords,
           &v26) < 0 )
    {
      v13 = CoCreateInstance(&CLSID_EXTENDEDERRORINFO, 0, 1u, &IID_IErrorRecords, &v26);
      v14 = v13;
      if ( v13 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180048A40[0] )
          bidTraceW(off_1800481E8[0], 484352, off_180048A40[0], (unsigned int)v13, 473);
        ThrowHR(v14);
      }
      *(GUID *)((char *)v32 + 8) = CLSID_MSPersist;
      *(_QWORD *)&v32[0] = __PAIR64__(a3, a2);
      memset((char *)&v32[1] + 8, 0, 20);
      v15 = (*(__int64 (__fastcall **)(LPVOID, _OWORD *, _QWORD, _QWORD, struct IErrorInfo *, _DWORD))(*(_QWORD *)v26 + 24LL))(
              v26,
              v32,
              0,
              0,
              a4,
              0);
      v16 = v15;
      if ( v15 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180048A38[0] )
          bidTraceW(off_1800481E8[0], 495616, off_180048A38[0], (unsigned int)v15, 484);
        ThrowHR(v16);
      }
    }
    (*(void (__fastcall **)(LPVOID, unsigned int *))(*(_QWORD *)v26 + 64LL))(v26, &v28);
    for ( i = 0; i < v28; ++i )
    {
      v31 = 0;
      v29 = 0;
      v30 = 0;
      v18 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _OWORD *))(*(_QWORD *)v26 + 32LL))(v26, i, v32);
      if ( v18 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180048A30[0] )
          bidTraceW(off_1800481E8[0], 507904, off_180048A30[0], (unsigned int)v18, 496);
        ThrowHR(v18);
      }
      v19 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, CPersistErrorInfo **))(*(_QWORD *)v26 + 40LL))(
              v26,
              i,
              &IID_IUnknown,
              &v29);
      if ( v19 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180048A28[0] )
          bidTraceW(off_1800481E8[0], 509952, off_180048A28[0], (unsigned int)v19, 498);
        ThrowHR(v19);
      }
      v20 = v29;
      if ( v29 )
      {
        if ( (**(int (__fastcall ***)(CPersistErrorInfo *, GUID *, __int64 *))v29)(v29, &IID_IErrorInfo, &v31) >= 0 )
        {
          v20 = v29;
        }
        else
        {
          v22 = (CPersistErrorInfo *)MMMAlloc(0x48u, v21);
          v30 = v22;
          if ( v22 )
            v20 = CPersistErrorInfo::CPersistErrorInfo(v22);
          else
            v20 = 0;
          v30 = v20;
          OnNullThrowOOM(v20);
          CPersistErrorInfo::SetErrorInfo(v20, a4);
          v23 = v29;
          v24 = *((_QWORD *)v20 + 2);
          if ( v24 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
          *((_QWORD *)v20 + 2) = v23;
          if ( v23 )
            (*(void (__fastcall **)(CPersistErrorInfo *))(*(_QWORD *)v23 + 8LL))(v23);
        }
      }
      v25 = (*(__int64 (__fastcall **)(LPVOID, _OWORD *, _QWORD, _QWORD, CPersistErrorInfo *, _DWORD))(*(_QWORD *)ppv + 24LL))(
              ppv,
              v32,
              v20 == 0 ? 0x10000000 : 0,
              0,
              v20,
              0);
      if ( v25 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180048A20[0] )
          bidTraceW(off_1800481E8[0], 525312, off_180048A20[0], (unsigned int)v25, 513);
        ThrowHR(v25);
      }
      CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v30);
      CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v29);
      CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v31);
    }
  }
LABEL_15:
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&ppv);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v26);
}

```

## disassembly

```asm
0x1800153fc  push    rbp
0x1800153fe  push    rbx
0x1800153ff  push    rsi
0x180015400  push    rdi
0x180015401  push    r12
0x180015403  push    r14
0x180015405  push    r15
0x180015407  lea     rbp, [rsp-27h]
0x18001540c  sub     rsp, 0B0h
0x180015413  mov     rax, cs:__security_cookie
0x18001541a  xor     rax, rsp
0x18001541d  mov     [rbp+57h+var_40], rax
0x180015421  mov     rdi, r9
0x180015424  mov     r12d, r8d
0x180015427  mov     r15d, edx
0x18001542a  xorps   xmm0, xmm0
0x18001542d  xor     eax, eax
0x18001542f  movups  [rbp+57h+var_70], xmm0
0x180015433  movups  [rbp+57h+var_60], xmm0
0x180015437  movups  [rbp+57h+var_60+0Ch], xmm0
0x18001543b  mov     [rbp+57h+var_90], 1
0x180015442  mov     [rbp+57h+var_A0], rax
0x180015446  mov     [rbp+57h+var_98], rax
0x18001544a  test    r9, r9
0x18001544d  jz      loc_180015562
0x180015453  lea     r14, [rcx+8]
0x180015457  mov     rcx, [r14]
0x18001545a  lea     r8, [rbp+57h+var_98]
0x18001545e  lea     rsi, IID_IErrorRecords
0x180015465  mov     rdx, rsi
0x180015468  test    rcx, rcx
0x18001546b  jnz     loc_180015593
0x180015471  mov     rax, [r9]
0x180015474  mov     rcx, r9
0x180015477  mov     rax, [rax]
0x18001547a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001547f  test    eax, eax
0x180015481  jns     loc_18001554F
0x180015487  lea     rax, [rbp+57h+var_98]
0x18001548b  mov     [rsp+0E0h+ppv], rax; ppv
0x180015490  mov     r9, rsi; riid
0x180015493  xor     edx, edx; pUnkOuter
0x180015495  lea     r8d, [rdx+1]; dwClsContext
0x180015499  lea     rcx, CLSID_EXTENDEDERRORINFO; rclsid
0x1800154a0  call    cs:__imp_CoCreateInstance
0x1800154a6  mov     ebx, eax
0x1800154a8  test    eax, eax
0x1800154aa  jns     short loc_1800154EC
0x1800154ac  test    byte ptr cs:_bidGblFlags, 2
0x1800154b3  jz      short loc_1800154E4
0x1800154b5  mov     rcx, cs:off_180048A50; "<CPersistErrorCache::AddError|ADO|ERR> "...
0x1800154bc  test    rcx, rcx
0x1800154bf  jz      short loc_1800154E4
0x1800154c1  mov     dword ptr [rsp+0E0h+ppv], 1BDh
0x1800154c9  mov     r9d, eax
0x1800154cc  mov     r8, cs:off_180048A50; "<CPersistErrorCache::AddError|ADO|ERR> "...
0x1800154d3  mov     edx, 6F400h
0x1800154d8  mov     rcx, cs:off_1800481E8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800154df  call    _bidTraceW
0x1800154e4  mov     ecx, ebx; int
0x1800154e6  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800154ec  mov     rcx, [rbp+57h+var_98]
0x1800154f0  mov     rax, [rcx]
0x1800154f3  mov     r8, r14
0x1800154f6  lea     rdx, IID_IErrorInfo
0x1800154fd  mov     rax, [rax]
0x180015500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015505  mov     ebx, eax
0x180015507  test    eax, eax
0x180015509  jns     loc_18001559E
0x18001550f  test    byte ptr cs:_bidGblFlags, 2
0x180015516  jz      short loc_180015547
0x180015518  mov     rcx, cs:off_180048A48; "<CPersistErrorCache::AddError|ADO|ERR> "...
0x18001551f  test    rcx, rcx
0x180015522  jz      short loc_180015547
0x180015524  mov     dword ptr [rsp+0E0h+ppv], 1C1h
0x18001552c  mov     r9d, eax
0x18001552f  mov     r8, cs:off_180048A48; "<CPersistErrorCache::AddError|ADO|ERR> "...
0x180015536  mov     edx, 70400h
0x18001553b  mov     rcx, cs:off_1800481E8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180015542  call    _bidTraceW
0x180015547  mov     ecx, ebx; int
0x180015549  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18001554f  mov     [r14], rdi
0x180015552  mov     rax, [rdi]
0x180015555  mov     rcx, rdi
0x180015558  mov     rax, [rax+8]
0x18001555c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015561  nop
0x180015562  lea     rcx, [rbp+57h+var_98]
0x180015566  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x18001556b  nop
0x18001556c  lea     rcx, [rbp+57h+var_A0]
0x180015570  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180015575  mov     rcx, [rbp+57h+var_40]
0x180015579  xor     rcx, rsp; StackCookie
0x18001557c  call    __security_check_cookie
0x180015581  add     rsp, 0B0h
0x180015588  pop     r15
0x18001558a  pop     r14
0x18001558c  pop     r12
0x18001558e  pop     rdi
0x18001558f  pop     rsi
0x180015590  pop     rbx
0x180015591  pop     rbp
0x180015592  retn
0x180015593  mov     rax, [rcx]
0x180015596  mov     rax, [rax]
0x180015599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001559e  mov     rax, [rdi]
0x1800155a1  lea     r8, [rbp+57h+var_A0]
0x1800155a5  mov     rdx, rsi
0x1800155a8  mov     rcx, rdi
0x1800155ab  mov     rax, [rax]
0x1800155ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155b3  test    eax, eax
0x1800155b5  jns     loc_1800156B4
0x1800155bb  lea     rax, [rbp+57h+var_A0]
0x1800155bf  mov     [rsp+0E0h+ppv], rax; ppv
0x1800155c4  mov     r9, rsi; riid
0x1800155c7  xor     edx, edx; pUnkOuter
0x1800155c9  lea     r8d, [rdx+1]; dwClsContext
0x1800155cd  lea     rcx, CLSID_EXTENDEDERRORINFO; rclsid
0x1800155d4  call    cs:__imp_CoCreateInstance
0x1800155da  mov     ebx, eax
0x1800155dc  test    eax, eax
0x1800155de  jns     short loc_180015620
0x1800155e0  test    byte ptr cs:_bidGblFlags, 2
0x1800155e7  jz      short loc_180015618
0x1800155e9  mov     rcx, cs:off_180048A40; "<CPersistErrorCache::AddError|ADO|ERR> "...
0x1800155f0  test    rcx, rcx
0x1800155f3  jz      short loc_180015618
0x1800155f5  mov     dword ptr [rsp+0E0h+ppv], 1D9h
0x1800155fd  mov     r9d, eax
0x180015600  mov     r8, cs:off_180048A40; "<CPersistErrorCache::AddError|ADO|ERR> "...
0x180015607  mov     edx, 76400h
0x18001560c  mov     rcx, cs:off_1800481E8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180015613  call    _bidTraceW
0x180015618  mov     ecx, ebx; int
0x18001561a  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180015620  movups  xmm0, xmmword ptr cs:?CLSID_MSPersist@@3U_GUID@@B.Data1; _GUID const CLSID_MSPersist ...
0x180015627  movdqu  [rbp+57h+var_70+8], xmm0
0x18001562c  mov     [rbp+57h+var_48], 0
0x180015633  mov     dword ptr [rbp+57h+var_70+4], r12d
0x180015637  mov     dword ptr [rbp+57h+var_70], r15d
0x18001563b  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180015642  movdqu  [rbp+57h+var_60+8], xmm0
0x180015647  mov     rcx, [rbp+57h+var_A0]
0x18001564b  mov     rax, [rcx]
0x18001564e  mov     [rsp+0E0h+var_B8], 0
0x180015656  mov     [rsp+0E0h+ppv], rdi
0x18001565b  xor     r9d, r9d
0x18001565e  xor     r8d, r8d
0x180015661  lea     rdx, [rbp+57h+var_70]
0x180015665  mov     rax, [rax+18h]
0x180015669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001566e  mov     ebx, eax
0x180015670  test    eax, eax
0x180015672  jns     short loc_1800156B4
0x180015674  test    byte ptr cs:_bidGblFlags, 2
0x18001567b  jz      short loc_1800156AC
0x18001567d  mov     rcx, cs:off_180048A38; "<CPersistErrorCache::AddError|ADO|ERR> "...
0x180015684  test    rcx, rcx
0x180015687  jz      short loc_1800156AC
0x180015689  mov     dword ptr [rsp+0E0h+ppv], 1E4h
0x180015691  mov     r9d, eax
0x180015694  mov     r8, cs:off_180048A38; "<CPersistErrorCache::AddError|ADO|ERR> "...
0x18001569b  mov     edx, 79000h
0x1800156a0  mov     rcx, cs:off_1800481E8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800156a7  call    _bidTraceW
0x1800156ac  mov     ecx, ebx; int
0x1800156ae  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800156b4  mov     rcx, [rbp+57h+var_A0]
0x1800156b8  mov     rax, [rcx]
0x1800156bb  lea     rdx, [rbp+57h+var_90]
0x1800156bf  mov     rax, [rax+40h]
0x1800156c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156c8  xor     r14d, r14d
0x1800156cb  cmp     r14d, [rbp+57h+var_90]
0x1800156cf  jnb     loc_180015562
0x1800156d5  mov     [rbp+57h+var_78], 0
0x1800156dd  mov     [rbp+57h+var_88], 0
0x1800156e5  mov     [rbp+57h+var_80], 0
0x1800156ed  mov     rcx, [rbp+57h+var_A0]
0x1800156f1  mov     rax, [rcx]
0x1800156f4  lea     r8, [rbp+57h+var_70]
0x1800156f8  mov     edx, r14d
0x1800156fb  mov     rax, [rax+20h]
0x1800156ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015704  mov     ebx, eax
0x180015706  test    eax, eax
0x180015708  js      loc_1800158B2
0x18001570e  mov     rcx, [rbp+57h+var_A0]
0x180015712  mov     rax, [rcx]
0x180015715  lea     r9, [rbp+57h+var_88]
0x180015719  lea     r8, IID_IUnknown
0x180015720  mov     edx, r14d
0x180015723  mov     rax, [rax+28h]
0x180015727  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001572c  mov     ebx, eax
0x18001572e  test    eax, eax
0x180015730  js      loc_180015872
0x180015736  mov     rbx, [rbp+57h+var_88]
0x18001573a  test    rbx, rbx
0x18001573d  jz      loc_1800157D0
0x180015743  mov     rax, [rbx]
0x180015746  lea     r8, [rbp+57h+var_78]
0x18001574a  lea     rdx, IID_IErrorInfo
0x180015751  mov     rcx, rbx
0x180015754  mov     rax, [rax]
0x180015757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001575c  test    eax, eax
0x18001575e  jns     short loc_1800157CC
0x180015760  mov     ecx, 48h ; 'H'; unsigned int
0x180015765  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18001576a  mov     [rbp+57h+var_80], rax
0x18001576e  test    rax, rax
0x180015771  jz      short loc_180015780
0x180015773  mov     rcx, rax; this
0x180015776  call    ??0CPersistErrorInfo@@QEAA@XZ; CPersistErrorInfo::CPersistErrorInfo(void)
0x18001577b  mov     rbx, rax
0x18001577e  jmp     short loc_180015782
0x180015780  xor     ebx, ebx
0x180015782  mov     [rbp+57h+var_80], rbx
0x180015786  mov     rcx, rbx; void *
0x180015789  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x18001578e  mov     rdx, rdi; struct IErrorInfo *
0x180015791  mov     rcx, rbx; this
0x180015794  call    ?SetErrorInfo@CPersistErrorInfo@@QEAAXPEAUIErrorInfo@@@Z; CPersistErrorInfo::SetErrorInfo(IErrorInfo *)
0x180015799  mov     rsi, [rbp+57h+var_88]
0x18001579d  mov     rcx, [rbx+10h]
0x1800157a1  test    rcx, rcx
0x1800157a4  jz      short loc_1800157B2
0x1800157a6  mov     rax, [rcx]
0x1800157a9  mov     rax, [rax+10h]
0x1800157ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157b2  mov     [rbx+10h], rsi
0x1800157b6  test    rsi, rsi
0x1800157b9  jz      short loc_1800157D0
0x1800157bb  mov     rax, [rsi]
0x1800157be  mov     rcx, rsi
0x1800157c1  mov     rax, [rax+8]
0x1800157c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157ca  jmp     short loc_1800157D0
0x1800157cc  mov     rbx, [rbp+57h+var_88]
0x1800157d0  mov     rcx, [rbp+57h+var_98]
0x1800157d4  mov     rdx, [rcx]
0x1800157d7  mov     rax, rbx
0x1800157da  neg     rax
0x1800157dd  sbb     r8d, r8d
0x1800157e0  not     r8d
0x1800157e3  and     r8d, 10000000h
0x1800157ea  mov     rax, [rdx+18h]
0x1800157ee  mov     [rsp+0E0h+var_B8], 0
0x1800157f6  mov     [rsp+0E0h+ppv], rbx
0x1800157fb  xor     r9d, r9d
0x1800157fe  lea     rdx, [rbp+57h+var_70]
0x180015802  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015807  mov     ebx, eax
0x180015809  test    eax, eax
0x18001580b  js      short loc_180015832
0x18001580d  lea     rcx, [rbp+57h+var_80]
0x180015811  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180015816  nop
0x180015817  lea     rcx, [rbp+57h+var_88]
0x18001581b  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180015820  nop
0x180015821  lea     rcx, [rbp+57h+var_78]
0x180015825  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x18001582a  inc     r14d
0x18001582d  jmp     loc_1800156CB
0x180015832  test    byte ptr cs:_bidGblFlags, 2
0x180015839  jz      short loc_18001586A
0x18001583b  mov     rax, cs:off_180048A20; "<CPersistErrorCache::AddError|ADO|ERR> "...
0x180015842  test    rax, rax
0x180015845  jz      short loc_18001586A
0x180015847  mov     dword ptr [rsp+0E0h+ppv], 201h
0x18001584f  mov     r9d, ebx
0x180015852  mov     r8, cs:off_180048A20; "<CPersistErrorCache::AddError|ADO|ERR> "...
0x180015859  mov     edx, 80400h
0x18001585e  mov     rcx, cs:off_1800481E8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180015865  call    _bidTraceW
0x18001586a  mov     ecx, ebx; int
0x18001586c  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180015872  test    byte ptr cs:_bidGblFlags, 2
0x180015879  jz      short loc_1800158AA
0x18001587b  mov     rax, cs:off_180048A28; "<CPersistErrorCache::AddError|ADO|ERR> "...
0x180015882  test    rax, rax
0x180015885  jz      short loc_1800158AA
0x180015887  mov     dword ptr [rsp+0E0h+ppv], 1F2h
0x18001588f  mov     r9d, ebx
0x180015892  mov     r8, cs:off_180048A28; "<CPersistErrorCache::AddError|ADO|ERR> "...
0x180015899  mov     edx, 7C800h
0x18001589e  mov     rcx, cs:off_1800481E8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800158a5  call    _bidTraceW
0x1800158aa  mov     ecx, ebx; int
0x1800158ac  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800158b2  test    byte ptr cs:_bidGblFlags, 2
0x1800158b9  jz      short loc_1800158EA
0x1800158bb  mov     rax, cs:off_180048A30; "<CPersistErrorCache::AddError|ADO|ERR> "...
  ... truncated ...
```
