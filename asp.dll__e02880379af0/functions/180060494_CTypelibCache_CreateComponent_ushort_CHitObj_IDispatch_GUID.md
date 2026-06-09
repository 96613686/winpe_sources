# CTypelibCache::CreateComponent(ushort *,CHitObj *,IDispatch * *,_GUID *)

- ea: `0x180060494`
- end: `0x180060868`
- name: `?CreateComponent@CTypelibCache@@QEAAJPEAGPEAVCHitObj@@PEAPEAUIDispatch@@PEAU_GUID@@@Z`
- size: `980`
- prototype: `int(CTypelibCache *__hidden this, unsigned __int16 *, struct CHitObj *, struct IDispatch **, struct _GUID *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180057330`

## callees

- `0x180006698`
- `0x180006ed4`
- `0x180007228`
- `0x180037344`
- `0x180037d44`
- `0x180038ae8`
- `0x180038f00`
- `0x180045a60`
- `0x1800462c0`
- `0x180060494`
- `0x180060a14`
- `0x180060e24`
- `0x180064010`

## import_xrefs

- `ole32!CLSIDFromProgID` at `0x180060613`
- `ole32!CLSIDFromProgID` at `0x180060613`
- `KERNEL32!LeaveCriticalSection` at `0x18006054b`
- `KERNEL32!LeaveCriticalSection` at `0x1800605df`
- `KERNEL32!LeaveCriticalSection` at `0x180060815`
- `KERNEL32!LeaveCriticalSection` at `0x18006054b`
- `KERNEL32!LeaveCriticalSection` at `0x1800605df`
- `KERNEL32!LeaveCriticalSection` at `0x180060815`
- `KERNEL32!EnterCriticalSection` at `0x1800604fb`
- `KERNEL32!EnterCriticalSection` at `0x1800605bc`
- `KERNEL32!EnterCriticalSection` at `0x1800607cf`
- `KERNEL32!EnterCriticalSection` at `0x1800604fb`
- `KERNEL32!EnterCriticalSection` at `0x1800605bc`
- `KERNEL32!EnterCriticalSection` at `0x1800607cf`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180060664`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180060664`

## pseudocode

```c
HRESULT __fastcall CTypelibCache::CreateComponent(
        CTypelibCache *this,
        unsigned __int16 *a2,
        CPageComponentManager **a3,
        struct IDispatch **a4,
        struct _GUID *lpclsid)
{
  unsigned int v5; // r12d
  int v9; // r14d
  struct CLinkElem *Elem; // rax
  int v11; // ebx
  unsigned int v12; // edx
  CComponentObject *v13; // rbx
  struct CComponentObject *v14; // rdx
  struct CLinkElem *v15; // rbx
  HRESULT result; // eax
  unsigned int v17; // edx
  CComponentObject *v18; // r14
  char *v19; // rax
  char *v20; // rbx
  int v21; // r12d
  int v22; // ecx
  _DWORD *v23; // rdx
  struct IDispatch *v24; // rcx
  CGlobalInterfaceAPI *v25; // rcx
  BOOL v26; // edi
  int v27; // r8d
  unsigned int v28; // [rsp+30h] [rbp-30h]
  unsigned int v29[2]; // [rsp+38h] [rbp-28h] BYREF
  CComponentObject *v30; // [rsp+40h] [rbp-20h] BYREF
  struct IUnknown *v31; // [rsp+48h] [rbp-18h] BYREF
  __int64 v32; // [rsp+50h] [rbp-10h] BYREF

  v5 = 0;
  v30 = 0;
  *(_QWORD *)v29 = 0;
  *lpclsid = GUID_NULL;
  *a4 = 0;
  if ( !a2 || !*a2 )
    return -2147467259;
  v28 = CbWStr(a2);
  v9 = 0;
  EnterCriticalSection(&stru_18007D278);
  Elem = CHashTable::FindElem((CHashTable *)&qword_18007D078, a2, v28);
  if ( Elem )
  {
    *lpclsid = *(struct _GUID *)((char *)Elem + 56);
    if ( (*((_BYTE *)Elem + 40) & 2) != 0 )
    {
      v9 = 1;
      v29[0] = *((_DWORD *)Elem + 19);
      v29[1] = *((_DWORD *)Elem + 20);
    }
    v5 = *((_DWORD *)Elem + 18);
    v11 = 1;
  }
  else
  {
    v11 = 0;
  }
  LeaveCriticalSection(&stru_18007D278);
  if ( v11 )
  {
    if ( CPageComponentManager::AddScopedUnnamedInstantiated(
           a3[11],
           v12,
           lpclsid,
           v5,
           (struct COnPageInfo *)((unsigned __int64)v29 & -(__int64)(v9 != 0)),
           &v30) >= 0 )
    {
      v13 = v30;
      if ( (int)CComponentObject::GetAddRefdIDispatch(v30, a4) >= 0 )
      {
        if ( !(unsigned int)CComponentObject::FEarlyReleaseAllowed(v13) )
          return 0;
        v14 = v13;
LABEL_38:
        CPageComponentManager::RemoveComponent(a3[11], v14);
        return 0;
      }
    }
    EnterCriticalSection(&stru_18007D278);
    v15 = CHashTable::DeleteElem((CHashTable *)&qword_18007D078, a2, v28);
    LeaveCriticalSection(&stru_18007D278);
    if ( v15 )
      (**(void (__fastcall ***)(struct CLinkElem *, __int64))v15)(v15, 1);
    *lpclsid = GUID_NULL;
  }
  result = CLSIDFromProgID(a2, lpclsid);
  if ( result >= 0 )
  {
    result = CPageComponentManager::AddScopedUnnamedInstantiated(a3[11], v17, lpclsid, 0, 0, &v30);
    if ( result >= 0 )
    {
      v18 = v30;
      result = CComponentObject::GetAddRefdIDispatch(v30, a4);
      if ( result >= 0 )
      {
        v19 = (char *)ALLOC_CACHE_HANDLER::Alloc(CTypelibCacheEntry::sm_pach);
        v20 = v19;
        if ( !v19 )
          return 0;
        *((_DWORD *)v19 + 10) &= 0xFFFFFFF8;
        *((_QWORD *)v19 + 1) = 0;
        *((_DWORD *)v19 + 4) = 0;
        *((_WORD *)v19 + 10) = 0;
        *((_QWORD *)v19 + 3) = 0;
        *((_QWORD *)v19 + 4) = 0;
        *((_QWORD *)v19 + 6) = 0;
        *(_QWORD *)v19 = &CTypelibCacheEntry::`vftable';
        *((_DWORD *)v19 + 18) = 0;
        v21 = -1;
        *((_DWORD *)v19 + 19) = -1;
        *(GUID *)(v19 + 56) = GUID_NULL;
        *((_DWORD *)v19 + 20) = -1;
        *((_DWORD *)v19 + 21) = -1;
        CTypelibCacheEntry::StoreProgID((CTypelibCacheEntry *)v19, a2, v28);
        CLinkElem::Init((CLinkElem *)v20, *((void **)v20 + 6), v28);
        *((_DWORD *)v20 + 10) |= 1u;
        v22 = *((_DWORD *)v20 + 10);
        *(struct _GUID *)(v20 + 56) = *lpclsid;
        *((_DWORD *)v20 + 18) = (*((_DWORD *)v18 + 10) >> 8) & 0xF;
        if ( (*((_DWORD *)v18 + 10) & 0x2000) != 0 )
          v23 = (_DWORD *)((char *)v18 + 92);
        else
          v23 = 0;
        if ( v23 )
        {
          *((_DWORD *)v20 + 10) = v22 | 2;
          *((_DWORD *)v20 + 19) = *v23;
          v21 = v23[1];
        }
        else
        {
          *((_DWORD *)v20 + 19) = -1;
          *((_DWORD *)v20 + 10) = v22 & 0xFFFFFFFD;
        }
        *((_DWORD *)v20 + 20) = v21;
        *((_DWORD *)v20 + 21) = -1;
        v24 = *a4;
        v32 = 0;
        if ( ((int (__fastcall *)(struct IDispatch *, _QWORD, _QWORD, __int64 *))v24->lpVtbl->GetTypeInfo)(
               v24,
               0,
               0,
               &v32) >= 0 )
        {
          v31 = 0;
          LODWORD(v30) = 0;
          if ( (*(int (__fastcall **)(__int64, struct IUnknown **, CComponentObject **))(*(_QWORD *)v32 + 144LL))(
                 v32,
                 &v31,
                 &v30) >= 0 )
          {
            v29[0] = 0;
            if ( (int)CGlobalInterfaceAPI::Register(v25, v31, &IID_ITypeLib, v29) >= 0 )
              *((_DWORD *)v20 + 21) = v29[0];
            ((void (__fastcall *)(struct IUnknown *))v31->lpVtbl->Release)(v31);
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
        }
        v26 = 0;
        EnterCriticalSection(&stru_18007D278);
        if ( !CHashTable::FindElem((CHashTable *)&qword_18007D078, a2, v28) )
          v26 = CHashTable::AddElem((CHashTable *)&qword_18007D078, (struct CLinkElem *)v20, v27) != 0;
        LeaveCriticalSection(&stru_18007D278);
        if ( !v26 )
          (**(void (__fastcall ***)(char *, __int64))v20)(v20, 1);
        if ( !(unsigned int)CComponentObject::FEarlyReleaseAllowed(v18) )
          return 0;
        v14 = v18;
        goto LABEL_38;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180060494  mov     [rsp-38h+arg_0], rbx
0x180060499  push    rbp
0x18006049a  push    rsi
0x18006049b  push    rdi
0x18006049c  push    r12
0x18006049e  push    r13
0x1800604a0  push    r14
0x1800604a2  push    r15
0x1800604a4  mov     rbp, rsp
0x1800604a7  sub     rsp, 60h
0x1800604ab  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800604b2  mov     rdi, [rbp+lpclsid]
0x1800604b6  xor     r12d, r12d
0x1800604b9  mov     [rbp+var_20], r12
0x1800604bd  mov     r13, r9
0x1800604c0  mov     qword ptr [rbp+var_28], r12
0x1800604c4  mov     r15, r8
0x1800604c7  mov     rsi, rdx
0x1800604ca  movdqu  xmmword ptr [rdi], xmm0
0x1800604ce  mov     [r9], r12
0x1800604d1  test    rdx, rdx
0x1800604d4  jz      loc_18006084B
0x1800604da  cmp     [rdx], r12w
0x1800604de  jz      loc_18006084B
0x1800604e4  mov     rcx, rdx; unsigned __int16 *
0x1800604e7  call    ?CbWStr@@YAKPEAG@Z; CbWStr(ushort *)
0x1800604ec  lea     rcx, stru_18007D278; lpCriticalSection
0x1800604f3  mov     [rbp+var_30], eax
0x1800604f6  mov     ebx, eax
0x1800604f8  mov     r14d, r12d
0x1800604fb  call    cs:__imp_EnterCriticalSection
0x180060501  mov     r8d, ebx; int
0x180060504  lea     rcx, qword_18007D078; this
0x18006050b  mov     rdx, rsi; void *
0x18006050e  call    ?FindElem@CHashTable@@QEAAPEAUCLinkElem@@PEBXH@Z; CHashTable::FindElem(void const *,int)
0x180060513  lea     edx, [r12+1]
0x180060518  test    rax, rax
0x18006051b  jz      short loc_180060542
0x18006051d  movups  xmm0, xmmword ptr [rax+38h]
0x180060521  movdqu  xmmword ptr [rdi], xmm0
0x180060525  test    byte ptr [rax+28h], 2
0x180060529  jz      short loc_18006053A
0x18006052b  mov     ecx, [rax+4Ch]
0x18006052e  mov     r14d, edx
0x180060531  mov     [rbp+var_28], ecx
0x180060534  mov     ecx, [rax+50h]
0x180060537  mov     [rbp+var_28+4], ecx
0x18006053a  mov     r12d, [rax+48h]
0x18006053e  mov     ebx, edx
0x180060540  jmp     short loc_180060544
0x180060542  xor     ebx, ebx
0x180060544  lea     rcx, stru_18007D278; lpCriticalSection
0x18006054b  call    cs:__imp_LeaveCriticalSection
0x180060551  test    ebx, ebx
0x180060553  jz      loc_18006060A
0x180060559  lea     rcx, [rbp+var_28]
0x18006055d  neg     r14d
0x180060560  mov     r9d, r12d; unsigned int
0x180060563  mov     r8, rdi; struct _GUID *
0x180060566  sbb     rax, rax
0x180060569  and     rax, rcx
0x18006056c  lea     rcx, [rbp+var_20]
0x180060570  mov     [rsp+60h+var_38], rcx; struct CComponentObject **
0x180060575  mov     rcx, [r15+58h]; this
0x180060579  mov     [rsp+60h+var_40], rax; struct COnPageInfo *
0x18006057e  call    ?AddScopedUnnamedInstantiated@CPageComponentManager@@QEAAJKAEBU_GUID@@KPEAUCOnPageInfo@@PEAPEAVCComponentObject@@@Z; CPageComponentManager::AddScopedUnnamedInstantiated(ulong,_GUID const &,ulong,COnPageInfo *,CComponentObject * *)
0x180060583  xor     r12d, r12d
0x180060586  test    eax, eax
0x180060588  js      short loc_1800605B5
0x18006058a  mov     rbx, [rbp+var_20]
0x18006058e  mov     rdx, r13; struct IDispatch **
0x180060591  mov     rcx, rbx; this
0x180060594  call    ?GetAddRefdIDispatch@CComponentObject@@QEAAJPEAPEAUIDispatch@@@Z; CComponentObject::GetAddRefdIDispatch(IDispatch * *)
0x180060599  test    eax, eax
0x18006059b  js      short loc_1800605B5
0x18006059d  mov     rcx, rbx; this
0x1800605a0  call    ?FEarlyReleaseAllowed@CComponentObject@@QEBAHXZ; CComponentObject::FEarlyReleaseAllowed(void)
0x1800605a5  test    eax, eax
0x1800605a7  jz      loc_180060847
0x1800605ad  mov     rdx, rbx
0x1800605b0  jmp     loc_18006083E
0x1800605b5  lea     rcx, stru_18007D278; lpCriticalSection
0x1800605bc  call    cs:__imp_EnterCriticalSection
0x1800605c2  mov     r8d, [rbp+var_30]; int
0x1800605c6  lea     rcx, qword_18007D078; this
0x1800605cd  mov     rdx, rsi; void *
0x1800605d0  call    ?DeleteElem@CHashTable@@QEAAPEAUCLinkElem@@PEBXH@Z; CHashTable::DeleteElem(void const *,int)
0x1800605d5  lea     rcx, stru_18007D278; lpCriticalSection
0x1800605dc  mov     rbx, rax
0x1800605df  call    cs:__imp_LeaveCriticalSection
0x1800605e5  test    rbx, rbx
0x1800605e8  jz      short loc_1800605FD
0x1800605ea  mov     rcx, [rbx]
0x1800605ed  mov     edx, 1
0x1800605f2  mov     rax, [rcx]
0x1800605f5  mov     rcx, rbx
0x1800605f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800605fd  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180060604  movdqu  xmmword ptr [rdi], xmm0
0x180060608  jmp     short loc_18006060D
0x18006060a  xor     r12d, r12d
0x18006060d  mov     rdx, rdi; lpclsid
0x180060610  mov     rcx, rsi; lpszProgID
0x180060613  call    cs:__imp_CLSIDFromProgID
0x180060619  test    eax, eax
0x18006061b  js      loc_180060850
0x180060621  mov     rcx, [r15+58h]; this
0x180060625  lea     rax, [rbp+var_20]
0x180060629  mov     [rsp+60h+var_38], rax; struct CComponentObject **
0x18006062e  xor     r9d, r9d; unsigned int
0x180060631  mov     r8, rdi; struct _GUID *
0x180060634  mov     [rsp+60h+var_40], r12; struct COnPageInfo *
0x180060639  call    ?AddScopedUnnamedInstantiated@CPageComponentManager@@QEAAJKAEBU_GUID@@KPEAUCOnPageInfo@@PEAPEAVCComponentObject@@@Z; CPageComponentManager::AddScopedUnnamedInstantiated(ulong,_GUID const &,ulong,COnPageInfo *,CComponentObject * *)
0x18006063e  test    eax, eax
0x180060640  js      loc_180060850
0x180060646  mov     r14, [rbp+var_20]
0x18006064a  mov     rdx, r13; struct IDispatch **
0x18006064d  mov     rcx, r14; this
0x180060650  call    ?GetAddRefdIDispatch@CComponentObject@@QEAAJPEAPEAUIDispatch@@@Z; CComponentObject::GetAddRefdIDispatch(IDispatch * *)
0x180060655  test    eax, eax
0x180060657  js      loc_180060850
0x18006065d  mov     rcx, cs:?sm_pach@CTypelibCacheEntry@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CTypelibCacheEntry::sm_pach
0x180060664  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x18006066a  mov     rbx, rax
0x18006066d  test    rax, rax
0x180060670  jz      loc_180060847
0x180060676  and     dword ptr [rbx+28h], 0FFFFFFF8h
0x18006067a  mov     rdx, rsi; unsigned __int16 *
0x18006067d  mov     r8d, [rbp+var_30]; unsigned int
0x180060681  mov     rcx, rbx; this
0x180060684  mov     [rax+8], r12
0x180060688  mov     [rax+10h], r12d
0x18006068c  mov     [rax+14h], r12w
0x180060691  mov     [rax+18h], r12
0x180060695  mov     [rax+20h], r12
0x180060699  lea     rax, ??_7CTypelibCacheEntry@@6B@; const CTypelibCacheEntry::`vftable'
0x1800606a0  mov     [rbx+30h], r12
0x1800606a4  mov     [rbx], rax
0x1800606a7  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800606ae  mov     [rbx+48h], r12d
0x1800606b2  or      r12d, 0FFFFFFFFh
0x1800606b6  mov     [rbx+4Ch], r12d
0x1800606ba  movdqu  xmmword ptr [rbx+38h], xmm0
0x1800606bf  mov     [rbx+50h], r12d
0x1800606c3  mov     dword ptr [rbx+54h], 0FFFFFFFFh
0x1800606ca  call    ?StoreProgID@CTypelibCacheEntry@@AEAAJPEAGK@Z; CTypelibCacheEntry::StoreProgID(ushort *,ulong)
0x1800606cf  mov     rdx, [rbx+30h]; void *
0x1800606d3  mov     rcx, rbx; this
0x1800606d6  mov     r8d, [rbp+var_30]; int
0x1800606da  call    ?Init@CLinkElem@@QEAAJPEAXH@Z; CLinkElem::Init(void *,int)
0x1800606df  or      dword ptr [rbx+28h], 1
0x1800606e3  movups  xmm0, xmmword ptr [rdi]
0x1800606e6  mov     ecx, [rbx+28h]
0x1800606e9  movdqu  xmmword ptr [rbx+38h], xmm0
0x1800606ee  mov     eax, [r14+28h]
0x1800606f2  shr     eax, 8
0x1800606f5  and     eax, 0Fh
0x1800606f8  mov     [rbx+48h], eax
0x1800606fb  test    dword ptr [r14+28h], 2000h
0x180060703  jz      short loc_18006070B
0x180060705  lea     rdx, [r14+5Ch]
0x180060709  jmp     short loc_18006070D
0x18006070b  xor     edx, edx
0x18006070d  test    rdx, rdx
0x180060710  jz      short loc_180060723
0x180060712  or      ecx, 2
0x180060715  mov     [rbx+28h], ecx
0x180060718  mov     eax, [rdx]
0x18006071a  mov     [rbx+4Ch], eax
0x18006071d  mov     r12d, [rdx+4]
0x180060721  jmp     short loc_18006072D
0x180060723  and     ecx, 0FFFFFFFDh
0x180060726  mov     [rbx+4Ch], r12d
0x18006072a  mov     [rbx+28h], ecx
0x18006072d  mov     [rbx+50h], r12d
0x180060731  lea     r9, [rbp+var_10]
0x180060735  mov     dword ptr [rbx+54h], 0FFFFFFFFh
0x18006073c  xor     r12d, r12d
0x18006073f  mov     rcx, [r13+0]
0x180060743  xor     r8d, r8d
0x180060746  mov     [rbp+var_10], r12
0x18006074a  xor     edx, edx
0x18006074c  mov     rax, [rcx]
0x18006074f  mov     rax, [rax+20h]
0x180060753  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060758  test    eax, eax
0x18006075a  js      short loc_1800607C5
0x18006075c  mov     rcx, [rbp+var_10]
0x180060760  lea     r8, [rbp+var_20]
0x180060764  mov     [rbp+var_18], r12
0x180060768  lea     rdx, [rbp+var_18]
0x18006076c  mov     dword ptr [rbp+var_20], r12d
0x180060770  mov     rax, [rcx]
0x180060773  mov     rax, [rax+90h]
0x18006077a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006077f  test    eax, eax
0x180060781  js      short loc_1800607B5
0x180060783  mov     rdx, [rbp+var_18]; struct IUnknown *
0x180060787  lea     r9, [rbp+var_28]; unsigned int *
0x18006078b  lea     r8, IID_ITypeLib; struct _GUID *
0x180060792  mov     [rbp+var_28], r12d
0x180060796  call    ?Register@CGlobalInterfaceAPI@@QEAAJPEAUIUnknown@@AEBU_GUID@@PEAK@Z; CGlobalInterfaceAPI::Register(IUnknown *,_GUID const &,ulong *)
0x18006079b  test    eax, eax
0x18006079d  js      short loc_1800607A5
0x18006079f  mov     eax, [rbp+var_28]
0x1800607a2  mov     [rbx+54h], eax
0x1800607a5  mov     rcx, [rbp+var_18]
0x1800607a9  mov     rax, [rcx]
0x1800607ac  mov     rax, [rax+10h]
0x1800607b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800607b5  mov     rcx, [rbp+var_10]
0x1800607b9  mov     rax, [rcx]
0x1800607bc  mov     rax, [rax+10h]
0x1800607c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800607c5  lea     rcx, stru_18007D278; lpCriticalSection
0x1800607cc  mov     edi, r12d
0x1800607cf  call    cs:__imp_EnterCriticalSection
0x1800607d5  mov     r8d, [rbp+var_30]; int
0x1800607d9  lea     rcx, qword_18007D078; this
0x1800607e0  mov     rdx, rsi; void *
0x1800607e3  call    ?FindElem@CHashTable@@QEAAPEAUCLinkElem@@PEBXH@Z; CHashTable::FindElem(void const *,int)
0x1800607e8  test    rax, rax
0x1800607eb  jnz     short loc_180060809
0x1800607ed  mov     rdx, rbx; struct CLinkElem *
0x1800607f0  lea     rcx, qword_18007D078; this
0x1800607f7  call    ?AddElem@CHashTable@@QEAAPEAUCLinkElem@@PEAU2@H@Z; CHashTable::AddElem(CLinkElem *,int)
0x1800607fc  test    rax, rax
0x1800607ff  mov     esi, 1
0x180060804  cmovnz  edi, esi
0x180060807  jmp     short loc_18006080E
0x180060809  mov     esi, 1
0x18006080e  lea     rcx, stru_18007D278; lpCriticalSection
0x180060815  call    cs:__imp_LeaveCriticalSection
0x18006081b  test    edi, edi
0x18006081d  jnz     short loc_18006082F
0x18006081f  mov     rax, [rbx]
0x180060822  mov     edx, esi
0x180060824  mov     rcx, rbx
0x180060827  mov     rax, [rax]
0x18006082a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006082f  mov     rcx, r14; this
0x180060832  call    ?FEarlyReleaseAllowed@CComponentObject@@QEBAHXZ; CComponentObject::FEarlyReleaseAllowed(void)
0x180060837  test    eax, eax
0x180060839  jz      short loc_180060847
0x18006083b  mov     rdx, r14; struct CComponentObject *
0x18006083e  mov     rcx, [r15+58h]; this
0x180060842  call    ?RemoveComponent@CPageComponentManager@@QEAAJPEAVCComponentObject@@@Z; CPageComponentManager::RemoveComponent(CComponentObject *)
0x180060847  xor     eax, eax
0x180060849  jmp     short loc_180060850
0x18006084b  mov     eax, 80004005h
0x180060850  mov     rbx, [rsp+60h+arg_0]
0x180060858  add     rsp, 60h
0x18006085c  pop     r15
0x18006085e  pop     r14
0x180060860  pop     r13
0x180060862  pop     r12
0x180060864  pop     rdi
0x180060865  pop     rsi
0x180060866  pop     rbp
0x180060867  retn
```
