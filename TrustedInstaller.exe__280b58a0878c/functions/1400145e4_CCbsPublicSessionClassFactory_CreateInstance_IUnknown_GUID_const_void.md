# CCbsPublicSessionClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1400145e4`
- end: `0x1400148e0`
- name: `?CreateInstance@CCbsPublicSessionClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `764`
- prototype: `__int64 __fastcall(CCbsPublicSessionClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1400145d0`

## callees

- `0x140002070`
- `0x140006344`
- `0x14000695c`
- `0x140007630`
- `0x14000e210`
- `0x1400145e4`
- `0x140014f04`
- `0x140015738`
- `0x140017658`
- `0x14002b010`

## string_xrefs

- `0x1400147b0`: `Failed to create session.`
- `0x14001487a`: `Failed to create session.`
- `0x1400148ae`: `Unexpected COM service request`

## pseudocode

```c
__int64 __fastcall CCbsPublicSessionClassFactory::CreateInstance(
        CCbsPublicSessionClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v8; // esi
  bool v9; // zf
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 (__fastcall **v17)(_QWORD, _QWORD, _QWORD); // rax
  struct ICbsSession **InitPointer; // rax
  int Session; // eax
  __int64 v20; // rax
  __int64 v21; // rax
  CCbsTiSxSStore *v22; // rax
  CCbsTiSxSStore *v23; // rax
  char *v24; // rdx
  _QWORD *v25; // rbx
  _QWORD *v27; // [rsp+20h] [rbp-20h] BYREF
  _QWORD v28[3]; // [rsp+28h] [rbp-18h] BYREF

  MonitoredCritSecLocker::MonitoredCritSecLocker((MonitoredCritSecLocker *)v28, (struct MonitoredCritSec *)&vTiLock, 1);
  v28[0] = &TiCoreLocker::`vftable';
  if ( vbShuttingdown )
  {
    v8 = -2147023781;
    goto LABEL_53;
  }
  if ( !a4 )
  {
    v8 = -2147024809;
    CBSWdsLogLight(0x4000000, 2147942487LL, 1, "Invalid ppvObject passed in.", v27, v28[0]);
    goto LABEL_53;
  }
  *a4 = 0;
  if ( a2 )
  {
    v8 = -2147221232;
    CBSWdsLogLight(0x4000000, 2147746064LL, 1, "Aggregation not supported.", v27, v28[0]);
    goto LABEL_53;
  }
  if ( *((_DWORD *)this - 30) )
  {
    if ( *((_DWORD *)this - 30) == 2 )
    {
      v20 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
      v9 = *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IUnknown.Data1;
      v27 = 0;
      if ( v9 )
        v20 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IUnknown.Data4;
      if ( v20 )
      {
        v21 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_ISxsStore.Data1;
        if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_ISxsStore.Data1 )
          v21 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_ISxsStore.Data4;
        if ( v21 )
        {
          v8 = -2147467262;
          CBSWdsLogLight(0x4000000, 2147500034LL, 1, "Unsupported interface.", v27, v28[0]);
          goto LABEL_53;
        }
      }
      v22 = (CCbsTiSxSStore *)operator new(0x60u);
      if ( v22
        && (v23 = CCbsTiSxSStore::CCbsTiSxSStore(v22, (CCbsPublicSessionClassFactory *)((char *)this - 144))) != 0 )
      {
        v24 = (char *)v23 + *(int *)(*((_QWORD *)v23 + 1) + 4LL) + 8;
      }
      else
      {
        v24 = 0;
      }
      Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::TakeOwnership(&v27, v24);
      v25 = v27;
      if ( !v27 )
      {
        v8 = -2147024882;
        CBSWdsLogLight(0x4000000, 2147942414LL, 1, "Failed to create session.", 0, v28[0]);
        goto LABEL_53;
      }
      v8 = (*(__int64 (__fastcall **)(_QWORD *, const struct _GUID *, void **))*v27)(v27, a3, a4);
      v17 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v25;
      goto LABEL_32;
    }
    v8 = -2146498560;
    CBSWdsLogLight(0x4000000, 2148468736LL, 1, "Unexpected COM service request", v27, v28[0]);
  }
  else
  {
    v10 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_ICbsServicingProcessor.Data1;
    v9 = *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_ICbsServicingProcessor.Data1;
    v27 = 0;
    if ( v9 )
      v10 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_ICbsServicingProcessor.Data4;
    if ( !v10 )
      goto LABEL_33;
    v11 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
      v11 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IUnknown.Data4;
    if ( !v11 )
      goto LABEL_33;
    v12 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_ICbsSession.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_ICbsSession.Data1 )
      v12 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_ICbsSession.Data4;
    if ( !v12 )
      goto LABEL_33;
    v13 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_ICbsSession7.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_ICbsSession7.Data1 )
      v13 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_ICbsSession7.Data4;
    if ( !v13 )
      goto LABEL_33;
    v14 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_ICbsSession8.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_ICbsSession8.Data1 )
      v14 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_ICbsSession8.Data4;
    if ( !v14 )
      goto LABEL_33;
    v15 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_ICbsSession9.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_ICbsSession9.Data1 )
      v15 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_ICbsSession9.Data4;
    if ( !v15 )
      goto LABEL_33;
    v16 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_ICbsSession10.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_ICbsSession10.Data1 )
      v16 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_ICbsSession10.Data4;
    if ( v16 )
    {
      v8 = -2147467262;
      CBSWdsLogLight(0x4000000, 2147500034LL, 1, "Unsupported interface.", v27, v28[0]);
    }
    else
    {
LABEL_33:
      InitPointer = (struct ICbsSession **)Windows::AutoComPtr<IClassFactory>::GetInitPointer(&v27);
      Session = CCbsPublicSessionClassFactory::CreateSession(
                  (CCbsPublicSessionClassFactory *)((char *)this - 144),
                  (CCbsPublicSessionClassFactory *)((char *)this - 144),
                  InitPointer);
      v8 = Session;
      if ( Session >= 0 )
        v8 = (*(__int64 (__fastcall **)(_QWORD *, const struct _GUID *, void **))*v27)(v27, a3, a4);
      else
        CBSWdsLogLight(0x4000000, (unsigned int)Session, 1, "Failed to create session.", v27, v28[0]);
    }
    if ( v27 )
    {
      v17 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v27;
LABEL_32:
      ((void (*)(void))v17[2])();
    }
  }
LABEL_53:
  MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v28);
  return v8;
}

```

## disassembly

```asm
0x1400145e4  mov     [rsp-28h+arg_8], rbx
0x1400145e9  push    rbp
0x1400145ea  push    rsi
0x1400145eb  push    rdi
0x1400145ec  push    r12
0x1400145ee  push    r14
0x1400145f0  mov     rbp, rsp
0x1400145f3  sub     rsp, 40h
0x1400145f7  mov     rdi, r8
0x1400145fa  mov     rbx, rdx
0x1400145fd  mov     rsi, rcx
0x140014600  lea     rdx, vTiLock; struct MonitoredCritSec *
0x140014607  mov     r12d, 1
0x14001460d  lea     rcx, [rbp+var_18]; this
0x140014611  mov     r8b, r12b; bool
0x140014614  mov     r14, r9
0x140014617  call    ??0MonitoredCritSecLocker@@QEAA@AEAUMonitoredCritSec@@_N@Z; MonitoredCritSecLocker::MonitoredCritSecLocker(MonitoredCritSec &,bool)
0x14001461c  cmp     cs:?vbShuttingdown@@3HA, 0; int vbShuttingdown
0x140014623  lea     rax, ??_7TiCoreLocker@@6B@; const TiCoreLocker::`vftable'
0x14001462a  mov     [rbp+var_18], rax
0x14001462e  jz      short loc_14001463A
0x140014630  mov     esi, 8007045Bh
0x140014635  jmp     loc_1400148C4
0x14001463a  test    r14, r14
0x14001463d  jnz     short loc_140014650
0x14001463f  mov     esi, 80070057h
0x140014644  lea     r9, aInvalidPpvobje; "Invalid ppvObject passed in."
0x14001464b  jmp     loc_1400148B5
0x140014650  mov     qword ptr [r14], 0
0x140014657  test    rbx, rbx
0x14001465a  jz      short loc_14001466D
0x14001465c  mov     esi, 80040110h
0x140014661  lea     r9, aAggregationNot; "Aggregation not supported."
0x140014668  jmp     loc_1400148B5
0x14001466d  lea     rbx, [rsi-90h]
0x140014674  cmp     dword ptr [rbx+18h], 0
0x140014678  jnz     loc_1400147D4
0x14001467e  mov     rax, [rdi]
0x140014681  sub     rax, qword ptr cs:IID_ICbsServicingProcessor.Data1
0x140014688  mov     [rbp+var_20], 0
0x140014690  jnz     short loc_14001469D
0x140014692  mov     rax, [rdi+8]
0x140014696  sub     rax, qword ptr cs:IID_ICbsServicingProcessor.Data4
0x14001469d  test    rax, rax
0x1400146a0  jz      loc_140014793
0x1400146a6  mov     rax, [rdi]
0x1400146a9  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x1400146b0  jnz     short loc_1400146BD
0x1400146b2  mov     rax, [rdi+8]
0x1400146b6  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x1400146bd  test    rax, rax
0x1400146c0  jz      loc_140014793
0x1400146c6  mov     rax, [rdi]
0x1400146c9  sub     rax, qword ptr cs:IID_ICbsSession.Data1
0x1400146d0  jnz     short loc_1400146DD
0x1400146d2  mov     rax, [rdi+8]
0x1400146d6  sub     rax, qword ptr cs:IID_ICbsSession.Data4
0x1400146dd  test    rax, rax
0x1400146e0  jz      loc_140014793
0x1400146e6  mov     rax, [rdi]
0x1400146e9  sub     rax, qword ptr cs:IID_ICbsSession7.Data1
0x1400146f0  jnz     short loc_1400146FD
0x1400146f2  mov     rax, [rdi+8]
0x1400146f6  sub     rax, qword ptr cs:IID_ICbsSession7.Data4
0x1400146fd  test    rax, rax
0x140014700  jz      loc_140014793
0x140014706  mov     rax, [rdi]
0x140014709  sub     rax, qword ptr cs:IID_ICbsSession8.Data1
0x140014710  jnz     short loc_14001471D
0x140014712  mov     rax, [rdi+8]
0x140014716  sub     rax, qword ptr cs:IID_ICbsSession8.Data4
0x14001471d  test    rax, rax
0x140014720  jz      short loc_140014793
0x140014722  mov     rax, [rdi]
0x140014725  sub     rax, qword ptr cs:IID_ICbsSession9.Data1
0x14001472c  jnz     short loc_140014739
0x14001472e  mov     rax, [rdi+8]
0x140014732  sub     rax, qword ptr cs:IID_ICbsSession9.Data4
0x140014739  test    rax, rax
0x14001473c  jz      short loc_140014793
0x14001473e  mov     rax, [rdi]
0x140014741  sub     rax, qword ptr cs:IID_ICbsSession10.Data1
0x140014748  jnz     short loc_140014755
0x14001474a  mov     rax, [rdi+8]
0x14001474e  sub     rax, qword ptr cs:IID_ICbsSession10.Data4
0x140014755  test    rax, rax
0x140014758  jz      short loc_140014793
0x14001475a  mov     edx, 80004002h
0x14001475f  lea     r9, aUnsupportedInt; "Unsupported interface."
0x140014766  mov     esi, edx
0x140014768  mov     r8d, r12d
0x14001476b  mov     ecx, 4000000h
0x140014770  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140014775  mov     rcx, [rbp+var_20]
0x140014779  test    rcx, rcx
0x14001477c  jz      loc_1400148C4
0x140014782  mov     rax, [rcx]
0x140014785  mov     rax, [rax+10h]
0x140014789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001478e  jmp     loc_1400148C4
0x140014793  lea     rcx, [rbp+var_20]
0x140014797  call    ?GetInitPointer@?$AutoComPtr@UIClassFactory@@@Windows@@QEAAPEAPEAUIClassFactory@@XZ; Windows::AutoComPtr<IClassFactory>::GetInitPointer(void)
0x14001479c  mov     r8, rax; struct ICbsSession **
0x14001479f  mov     rdx, rbx; struct CCbsPublicSessionClassFactory *
0x1400147a2  mov     rcx, rbx; this
0x1400147a5  call    ?CreateSession@CCbsPublicSessionClassFactory@@QEAAJPEAV1@PEAPEAUICbsSession@@@Z; CCbsPublicSessionClassFactory::CreateSession(CCbsPublicSessionClassFactory *,ICbsSession * *)
0x1400147aa  mov     esi, eax
0x1400147ac  test    eax, eax
0x1400147ae  jns     short loc_1400147BB
0x1400147b0  lea     r9, aFailedToCreate; "Failed to create session."
0x1400147b7  mov     edx, eax
0x1400147b9  jmp     short loc_140014768
0x1400147bb  mov     rcx, [rbp+var_20]
0x1400147bf  mov     r8, r14
0x1400147c2  mov     rdx, rdi
0x1400147c5  mov     rax, [rcx]
0x1400147c8  mov     rax, [rax]
0x1400147cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400147d0  mov     esi, eax
0x1400147d2  jmp     short loc_140014775
0x1400147d4  cmp     dword ptr [rbx+18h], 2
0x1400147d8  jnz     loc_1400148A9
0x1400147de  mov     rax, [rdi]
0x1400147e1  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x1400147e8  mov     [rbp+var_20], 0
0x1400147f0  jnz     short loc_1400147FD
0x1400147f2  mov     rax, [rdi+8]
0x1400147f6  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x1400147fd  test    rax, rax
0x140014800  jz      short loc_140014831
0x140014802  mov     rax, [rdi]
0x140014805  sub     rax, qword ptr cs:IID_ISxsStore.Data1
0x14001480c  jnz     short loc_140014819
0x14001480e  mov     rax, [rdi+8]
0x140014812  sub     rax, qword ptr cs:IID_ISxsStore.Data4
0x140014819  test    rax, rax
0x14001481c  jz      short loc_140014831
0x14001481e  mov     edx, 80004002h
0x140014823  lea     r9, aUnsupportedInt; "Unsupported interface."
0x14001482a  mov     esi, edx
0x14001482c  jmp     loc_1400148B7
0x140014831  mov     ecx, 60h ; '`'; Size
0x140014836  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001483b  test    rax, rax
0x14001483e  jz      short loc_140014861
0x140014840  mov     rdx, rbx; struct CCbsPublicSessionClassFactory *
0x140014843  mov     rcx, rax; this
0x140014846  call    ??0CCbsTiSxSStore@@QEAA@PEAVCCbsPublicSessionClassFactory@@@Z; CCbsTiSxSStore::CCbsTiSxSStore(CCbsPublicSessionClassFactory *)
0x14001484b  test    rax, rax
0x14001484e  jz      short loc_140014861
0x140014850  mov     rcx, [rax+8]
0x140014854  movsxd  rdx, dword ptr [rcx+4]
0x140014858  add     rdx, 8
0x14001485c  add     rdx, rax
0x14001485f  jmp     short loc_140014863
0x140014861  xor     edx, edx
0x140014863  lea     rcx, [rbp+var_20]
0x140014867  call    ?TakeOwnership@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXPEA_W@Z; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::TakeOwnership(wchar_t *)
0x14001486c  mov     rbx, [rbp+var_20]
0x140014870  test    rbx, rbx
0x140014873  jnz     short loc_140014883
0x140014875  mov     esi, 8007000Eh
0x14001487a  lea     r9, aFailedToCreate; "Failed to create session."
0x140014881  jmp     short loc_1400148B5
0x140014883  mov     rax, [rbx]
0x140014886  mov     r8, r14
0x140014889  mov     rdx, rdi
0x14001488c  mov     rcx, rbx
0x14001488f  mov     rax, [rax]
0x140014892  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014897  mov     esi, eax
0x140014899  test    rbx, rbx
0x14001489c  jz      short loc_1400148C4
0x14001489e  mov     rax, [rbx]
0x1400148a1  mov     rcx, rbx
0x1400148a4  jmp     loc_140014785
0x1400148a9  mov     esi, 800F0800h
0x1400148ae  lea     r9, aUnexpectedComS; "Unexpected COM service request"
0x1400148b5  mov     edx, esi
0x1400148b7  mov     r8d, r12d
0x1400148ba  mov     ecx, 4000000h
0x1400148bf  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400148c4  lea     rcx, [rbp+var_18]; this
0x1400148c8  call    ??1MonitoredCritSecLocker@@UEAA@XZ; MonitoredCritSecLocker::~MonitoredCritSecLocker(void)
0x1400148cd  mov     rbx, [rsp+40h+arg_8]
0x1400148d2  mov     eax, esi
0x1400148d4  add     rsp, 40h
0x1400148d8  pop     r14
0x1400148da  pop     r12
0x1400148dc  pop     rdi
0x1400148dd  pop     rsi
0x1400148de  pop     rbp
0x1400148df  retn
```
