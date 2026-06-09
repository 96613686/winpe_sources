# CInkCollector::FinalConstruct(void)

- ea: `0x1800ab48c`
- end: `0x1800ab7a8`
- name: `?FinalConstruct@CInkCollector@@QEAAJXZ`
- size: `796`
- prototype: `__int64 __fastcall(CInkCollector *__hidden this)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004e9d0`
- `0x180050954`

## callees

- `0x180001c20`
- `0x1800063c4`
- `0x180010350`
- `0x18001a410`
- `0x1800217b0`
- `0x180047c94`
- `0x1800aa1a4`
- `0x1800aa22c`
- `0x1800ab48c`
- `0x1800af1cc`
- `0x1800b0630`
- `0x1800b2824`
- `0x1800c9f58`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800ab57c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800ab57c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800ab4da`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800ab5ab`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800ab4da`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800ab5ab`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1800ab5c7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1800ab5c7`
- `USER32!RegisterWindowMessageW` at `0x1800ab4f5`
- `USER32!RegisterWindowMessageW` at `0x1800ab517`
- `USER32!RegisterWindowMessageW` at `0x1800ab53e`
- `USER32!RegisterWindowMessageW` at `0x1800ab4f5`
- `USER32!RegisterWindowMessageW` at `0x1800ab517`
- `USER32!RegisterWindowMessageW` at `0x1800ab53e`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800ab4bc`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800ab4bc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CInkCollector::FinalConstruct(LPUNKNOWN *this)
{
  IUnknown *v2; // rax
  HRESULT FreeThreadedMarshaler; // ebx
  UINT v4; // eax
  UINT v5; // eax
  struct ATL::_ATL_MODULE *v6; // rcx
  struct IUnknown *v7; // rdx
  struct IInkDisp *v8; // rbx
  struct IUnknown *v9; // rdx
  struct IInkDisp *v10; // rdx
  struct IInkDisp **v11; // r8
  IUnknown *v12; // rax
  unsigned int i; // r8d
  void *v15; // [rsp+50h] [rbp+20h] BYREF
  struct IInkDisp *v16; // [rsp+58h] [rbp+28h] BYREF

  v15 = 0;
  v2 = (IUnknown *)((__int64 (__fastcall *)(LPUNKNOWN *))(*this)[12].lpVtbl)(this);
  FreeThreadedMarshaler = CoCreateFreeThreadedMarshaler(v2, this + 32);
  if ( FreeThreadedMarshaler >= 0 )
  {
    if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(this + 34), 0x8001FA0u) )
    {
      v4 = RegisterWindowMessageW(L"FA233FB8-B9DB-4368-BF19-12D81DA1D0E9");
      *((_DWORD *)this + 163) = v4;
      if ( v4 || (FreeThreadedMarshaler = SpHrFromLastWin32Error(), FreeThreadedMarshaler >= 0) )
      {
        *((_DWORD *)this + 165) = RegisterWindowMessageW(L"6328EA9E-8BFD-4bba-8155-A7542E171BAD");
        if ( *((_DWORD *)this + 163) || (FreeThreadedMarshaler = SpHrFromLastWin32Error(), FreeThreadedMarshaler >= 0) )
        {
          v5 = RegisterWindowMessageW(L"9A8AB2F0-2C1E-4c1a-9F20-80FC782F8A49");
          *((_DWORD *)this + 164) = v5;
          if ( v5 || (FreeThreadedMarshaler = SpHrFromLastWin32Error(), FreeThreadedMarshaler >= 0) )
          {
            FreeThreadedMarshaler = CInvalidateMgr::Init(
                                      (CInvalidateMgr *)(this + 83),
                                      (__int64)this,
                                      *((_DWORD *)this + 165));
            if ( FreeThreadedMarshaler >= 0 )
              this[55] = (LPUNKNOWN)CreateMutexW(0, 0, 0);
          }
        }
      }
    }
    else
    {
      FreeThreadedMarshaler = -2147024882;
    }
  }
  if ( !this[55] )
    goto LABEL_35;
  if ( FreeThreadedMarshaler >= 0 )
  {
    if ( !InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)this + 4, 0x8001FA0u)
      || (*((_DWORD *)this + 63) = 1, !QueryPerformanceFrequency((LARGE_INTEGER *)this + 62)) )
    {
      FreeThreadedMarshaler = -2147467259;
      goto LABEL_40;
    }
    FreeThreadedMarshaler = InternalCustomModuleGetClassObject(v6, &CLSID_TpcPlatformManager, &IID_IClassFactory, &v15);
    if ( FreeThreadedMarshaler >= 0 )
    {
      FreeThreadedMarshaler = (*(__int64 (__fastcall **)(void *, _QWORD, GUID *, char *))(*(_QWORD *)v15 + 24LL))(
                                v15,
                                0,
                                &IID_IInkManager,
                                (char *)this + 520);
      if ( FreeThreadedMarshaler >= 0 )
      {
        FreeThreadedMarshaler = ((__int64 (__fastcall *)(LPUNKNOWN))this[65]->lpVtbl[1].QueryInterface)(this[65]);
        if ( FreeThreadedMarshaler >= 0 )
        {
          v16 = 0;
          FreeThreadedMarshaler = ATL::CComObject<CDrawingAttributes>::CreateInstance(&v16);
          if ( FreeThreadedMarshaler >= 0 )
          {
            v7 = v16 ? (struct IUnknown *)&v16[2] : 0LL;
            ATL::AtlComPtrAssign(this + 46, v7);
            v16 = 0;
            FreeThreadedMarshaler = ATL::CComObject<CInkRenderer>::CreateInstance(&v16);
            if ( FreeThreadedMarshaler >= 0 )
            {
              v8 = v16;
              v9 = v16 ? (struct IUnknown *)&v16[2] : 0LL;
              ATL::AtlComPtrAssign(this + 47, v9);
              FreeThreadedMarshaler = ((__int64 (__fastcall *)(struct IInkDisp *, _QWORD))v8[1].lpVtbl->get_Dirty)(
                                        &v8[1],
                                        (unsigned __int64)(this + 1)
                                      & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64));
              if ( FreeThreadedMarshaler >= 0 )
              {
                v16 = 0;
                FreeThreadedMarshaler = ATL::CComObject<CInkObjectDisp>::CreateInstance(&v16);
                if ( FreeThreadedMarshaler >= 0 )
                {
                  v10 = v16 ? &v16[1] : 0LL;
                  ATL::CComPtr<IUnknown>::CComPtr<IUnknown>(&v16, v10);
                  FreeThreadedMarshaler = CInkCollector::_ReplaceInk((CInkCollector *)this, v16, v11);
                  ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v16);
                  if ( FreeThreadedMarshaler >= 0 )
                  {
                    FreeThreadedMarshaler = CInkCollector::_CreateCursorsCollection((CInkCollector *)this);
                    if ( FreeThreadedMarshaler >= 0 )
                    {
                      *((_DWORD *)this + 117) = 3;
                      v12 = (IUnknown *)WinMalloc(0x60u);
                      this[59] = v12;
                      if ( !v12 )
                      {
LABEL_35:
                        FreeThreadedMarshaler = -2147024882;
                        goto LABEL_40;
                      }
                      for ( i = 0; i < 3; ++i )
                        *(_GUID *)&this[59][4 * (int)i].lpVtbl = *off_180161150[i];
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_40:
  ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v15);
  return (unsigned int)FreeThreadedMarshaler;
}

```

## disassembly

```asm
0x1800ab48c  mov     [rsp-18h+arg_10], rbx
0x1800ab491  push    rbp
0x1800ab492  push    rsi
0x1800ab493  push    rdi
0x1800ab494  mov     rbp, rsp
0x1800ab497  sub     rsp, 30h
0x1800ab49b  mov     rdi, rcx
0x1800ab49e  mov     [rbp+arg_0], 0
0x1800ab4a6  mov     rax, [rcx]
0x1800ab4a9  mov     rax, [rax+60h]
0x1800ab4ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab4b2  lea     rdx, [rdi+100h]; ppunkMarshal
0x1800ab4b9  mov     rcx, rax; punkOuter
0x1800ab4bc  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x1800ab4c2  mov     ebx, eax
0x1800ab4c4  mov     esi, 8001FA0h
0x1800ab4c9  test    eax, eax
0x1800ab4cb  js      loc_1800AB589
0x1800ab4d1  lea     rcx, [rdi+110h]; lpCriticalSection
0x1800ab4d8  mov     edx, esi; dwSpinCount
0x1800ab4da  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800ab4e0  test    eax, eax
0x1800ab4e2  jnz     short loc_1800AB4EE
0x1800ab4e4  mov     ebx, 8007000Eh
0x1800ab4e9  jmp     loc_1800AB589
0x1800ab4ee  lea     rcx, aFa233fb8B9db43; "FA233FB8-B9DB-4368-BF19-12D81DA1D0E9"
0x1800ab4f5  call    cs:__imp_RegisterWindowMessageW
0x1800ab4fb  mov     [rdi+28Ch], eax
0x1800ab501  test    eax, eax
0x1800ab503  jnz     short loc_1800AB510
0x1800ab505  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x1800ab50a  mov     ebx, eax
0x1800ab50c  test    eax, eax
0x1800ab50e  js      short loc_1800AB589
0x1800ab510  lea     rcx, a6328ea9e8bfd4b; "6328EA9E-8BFD-4bba-8155-A7542E171BAD"
0x1800ab517  call    cs:__imp_RegisterWindowMessageW
0x1800ab51d  mov     [rdi+294h], eax
0x1800ab523  cmp     dword ptr [rdi+28Ch], 0
0x1800ab52a  jnz     short loc_1800AB537
0x1800ab52c  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x1800ab531  mov     ebx, eax
0x1800ab533  test    eax, eax
0x1800ab535  js      short loc_1800AB589
0x1800ab537  lea     rcx, a9a8ab2f02c1e4c; "9A8AB2F0-2C1E-4c1a-9F20-80FC782F8A49"
0x1800ab53e  call    cs:__imp_RegisterWindowMessageW
0x1800ab544  mov     [rdi+290h], eax
0x1800ab54a  test    eax, eax
0x1800ab54c  jnz     short loc_1800AB559
0x1800ab54e  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x1800ab553  mov     ebx, eax
0x1800ab555  test    eax, eax
0x1800ab557  js      short loc_1800AB589
0x1800ab559  lea     rcx, [rdi+298h]; this
0x1800ab560  mov     r8d, [rdi+294h]; unsigned int
0x1800ab567  mov     rdx, rdi; __int64
0x1800ab56a  call    ?Init@CInvalidateMgr@@QEAAJ_JI@Z; CInvalidateMgr::Init(__int64,uint)
0x1800ab56f  mov     ebx, eax
0x1800ab571  test    eax, eax
0x1800ab573  js      short loc_1800AB589
0x1800ab575  xor     r8d, r8d; lpName
0x1800ab578  xor     edx, edx; bInitialOwner
0x1800ab57a  xor     ecx, ecx; lpMutexAttributes
0x1800ab57c  call    cs:__imp_CreateMutexW
0x1800ab582  mov     [rdi+1B8h], rax
0x1800ab589  cmp     qword ptr [rdi+1B8h], 0
0x1800ab591  jz      loc_1800AB755
0x1800ab597  test    ebx, ebx
0x1800ab599  js      loc_1800AB790
0x1800ab59f  lea     rbx, [rdi+0A0h]
0x1800ab5a6  mov     edx, esi; dwSpinCount
0x1800ab5a8  mov     rcx, rbx; lpCriticalSection
0x1800ab5ab  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800ab5b1  test    eax, eax
0x1800ab5b3  jz      loc_1800AB78B
0x1800ab5b9  mov     dword ptr [rbx+5Ch], 1
0x1800ab5c0  lea     rcx, [rdi+1F0h]; lpFrequency
0x1800ab5c7  call    cs:__imp_QueryPerformanceFrequency
0x1800ab5cd  test    eax, eax
0x1800ab5cf  jz      loc_1800AB78B
0x1800ab5d5  lea     r9, [rbp+arg_0]; void **
0x1800ab5d9  lea     r8, IID_IClassFactory; struct _GUID *
0x1800ab5e0  lea     rdx, CLSID_TpcPlatformManager; struct _GUID *
0x1800ab5e7  call    ?InternalCustomModuleGetClassObject@@YAJPEAU_ATL_MODULE@ATL@@AEBU_GUID@@1PEAPEAX@Z; InternalCustomModuleGetClassObject(ATL::_ATL_MODULE *,_GUID const &,_GUID const &,void * *)
0x1800ab5ec  mov     ebx, eax
0x1800ab5ee  test    eax, eax
0x1800ab5f0  js      loc_1800AB790
0x1800ab5f6  mov     rcx, [rbp+arg_0]
0x1800ab5fa  lea     rsi, [rdi+208h]
0x1800ab601  mov     rax, [rcx]
0x1800ab604  mov     r9, rsi
0x1800ab607  lea     r8, IID_IInkManager
0x1800ab60e  xor     edx, edx
0x1800ab610  mov     rax, [rax+18h]
0x1800ab614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab619  mov     ebx, eax
0x1800ab61b  test    eax, eax
0x1800ab61d  js      loc_1800AB790
0x1800ab623  mov     rcx, [rsi]
0x1800ab626  mov     rax, [rcx]
0x1800ab629  mov     rax, [rax+18h]
0x1800ab62d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab632  mov     ebx, eax
0x1800ab634  test    eax, eax
0x1800ab636  js      loc_1800AB790
0x1800ab63c  mov     [rbp+arg_8], 0
0x1800ab644  lea     rcx, [rbp+arg_8]
0x1800ab648  call    ?CreateInstance@?$CComObject@VCDrawingAttributes@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CDrawingAttributes>::CreateInstance(ATL::CComObject<CDrawingAttributes> * *)
0x1800ab64d  mov     ebx, eax
0x1800ab64f  test    eax, eax
0x1800ab651  js      loc_1800AB790
0x1800ab657  mov     rax, [rbp+arg_8]
0x1800ab65b  test    rax, rax
0x1800ab65e  jz      short loc_1800AB666
0x1800ab660  lea     rdx, [rax+10h]
0x1800ab664  jmp     short loc_1800AB668
0x1800ab666  xor     edx, edx; struct IUnknown *
0x1800ab668  lea     rcx, [rdi+170h]; struct IUnknown **
0x1800ab66f  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800ab674  mov     [rbp+arg_8], 0
0x1800ab67c  lea     rcx, [rbp+arg_8]
0x1800ab680  call    ?CreateInstance@?$CComObject@VCInkRenderer@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CInkRenderer>::CreateInstance(ATL::CComObject<CInkRenderer> * *)
0x1800ab685  mov     ebx, eax
0x1800ab687  test    eax, eax
0x1800ab689  js      loc_1800AB790
0x1800ab68f  mov     rbx, [rbp+arg_8]
0x1800ab693  test    rbx, rbx
0x1800ab696  jz      short loc_1800AB69E
0x1800ab698  lea     rdx, [rbx+10h]
0x1800ab69c  jmp     short loc_1800AB6A0
0x1800ab69e  xor     edx, edx; struct IUnknown *
0x1800ab6a0  lea     rcx, [rdi+178h]; struct IUnknown **
0x1800ab6a7  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800ab6ac  lea     rcx, [rbx+8]
0x1800ab6b0  mov     r9, [rcx]
0x1800ab6b3  mov     rax, rdi
0x1800ab6b6  lea     r8, [rdi+8]
0x1800ab6ba  neg     rax
0x1800ab6bd  sbb     rdx, rdx
0x1800ab6c0  and     rdx, r8
0x1800ab6c3  mov     rax, [r9+48h]
0x1800ab6c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab6cc  mov     ebx, eax
0x1800ab6ce  test    eax, eax
0x1800ab6d0  js      loc_1800AB790
0x1800ab6d6  mov     [rbp+arg_8], 0
0x1800ab6de  lea     rcx, [rbp+arg_8]
0x1800ab6e2  call    ?CreateInstance@?$CComObject@VCInkObjectDisp@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CInkObjectDisp>::CreateInstance(ATL::CComObject<CInkObjectDisp> * *)
0x1800ab6e7  mov     ebx, eax
0x1800ab6e9  test    eax, eax
0x1800ab6eb  js      loc_1800AB790
0x1800ab6f1  mov     rax, [rbp+arg_8]
0x1800ab6f5  test    rax, rax
0x1800ab6f8  jz      short loc_1800AB700
0x1800ab6fa  lea     rdx, [rax+8]
0x1800ab6fe  jmp     short loc_1800AB702
0x1800ab700  xor     edx, edx
0x1800ab702  lea     rcx, [rbp+arg_8]
0x1800ab706  call    ??0?$CComPtr@UIUnknown@@@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComPtr<IUnknown>::CComPtr<IUnknown>(IUnknown *)
0x1800ab70b  nop
0x1800ab70c  mov     rdx, [rbp+arg_8]; struct IInkDisp *
0x1800ab710  mov     rcx, rdi; this
0x1800ab713  call    ?_ReplaceInk@CInkCollector@@AEAAJPEAUIInkDisp@@PEAPEAU2@@Z; CInkCollector::_ReplaceInk(IInkDisp *,IInkDisp * *)
0x1800ab718  mov     ebx, eax
0x1800ab71a  lea     rcx, [rbp+arg_8]; void *
0x1800ab71e  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
0x1800ab723  test    ebx, ebx
0x1800ab725  js      short loc_1800AB790
0x1800ab727  mov     rcx, rdi; this
0x1800ab72a  call    ?_CreateCursorsCollection@CInkCollector@@AEAAJXZ; CInkCollector::_CreateCursorsCollection(void)
0x1800ab72f  mov     ebx, eax
0x1800ab731  test    eax, eax
0x1800ab733  js      short loc_1800AB790
0x1800ab735  mov     dword ptr [rdi+1D4h], 3
0x1800ab73f  mov     ecx, 60h ; '`'; unsigned __int64
0x1800ab744  call    ?WinMalloc@@YAPEAX_K@Z; WinMalloc(unsigned __int64)
0x1800ab749  mov     [rdi+1D8h], rax
0x1800ab750  test    rax, rax
0x1800ab753  jnz     short loc_1800AB75C
0x1800ab755  mov     ebx, 8007000Eh
0x1800ab75a  jmp     short loc_1800AB790
0x1800ab75c  xor     r8d, r8d
0x1800ab75f  movsxd  rdx, r8d
0x1800ab762  lea     rcx, off_180161150
0x1800ab769  mov     rcx, [rcx+rdx*8]
0x1800ab76d  shl     rdx, 5
0x1800ab771  mov     rax, [rdi+1D8h]
0x1800ab778  movups  xmm0, xmmword ptr [rcx]
0x1800ab77b  movdqu  xmmword ptr [rdx+rax], xmm0
0x1800ab780  inc     r8d
0x1800ab783  cmp     r8d, 3
0x1800ab787  jb      short loc_1800AB75F
0x1800ab789  jmp     short loc_1800AB790
0x1800ab78b  mov     ebx, 80004005h
0x1800ab790  lea     rcx, [rbp+arg_0]; void *
0x1800ab794  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
0x1800ab799  mov     eax, ebx
0x1800ab79b  mov     rbx, [rsp+30h+arg_10]
0x1800ab7a0  add     rsp, 30h
0x1800ab7a4  pop     rdi
0x1800ab7a5  pop     rsi
0x1800ab7a6  pop     rbp
0x1800ab7a7  retn
```
