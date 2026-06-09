# CInkOverlay::FinalConstruct(void)

- ea: `0x1800d9dac`
- end: `0x1800da0d2`
- name: `?FinalConstruct@CInkOverlay@@QEAAJXZ`
- size: `806`
- prototype: `__int64 __fastcall(CInkOverlay *__hidden this)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004eb70`
- `0x180050c20`

## callees

- `0x180001c20`
- `0x1800063c4`
- `0x180010350`
- `0x18001a410`
- `0x1800217b0`
- `0x180047c94`
- `0x1800aa1a4`
- `0x1800aa22c`
- `0x1800af1cc`
- `0x1800c9f58`
- `0x1800d9dac`
- `0x1800def7c`
- `0x1800e0d58`
- `0x1800e20b0`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800d9e9c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800d9e9c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800d9dfa`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800d9ecb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800d9dfa`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800d9ecb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1800d9ee7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1800d9ee7`
- `USER32!RegisterWindowMessageW` at `0x1800d9e15`
- `USER32!RegisterWindowMessageW` at `0x1800d9e37`
- `USER32!RegisterWindowMessageW` at `0x1800d9e5e`
- `USER32!RegisterWindowMessageW` at `0x1800d9e15`
- `USER32!RegisterWindowMessageW` at `0x1800d9e37`
- `USER32!RegisterWindowMessageW` at `0x1800d9e5e`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800d9ddc`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800d9ddc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CInkOverlay::FinalConstruct(LPUNKNOWN *this)
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
      *((_DWORD *)this + 167) = v4;
      if ( v4 || (FreeThreadedMarshaler = SpHrFromLastWin32Error(), FreeThreadedMarshaler >= 0) )
      {
        *((_DWORD *)this + 169) = RegisterWindowMessageW(L"6328EA9E-8BFD-4bba-8155-A7542E171BAD");
        if ( *((_DWORD *)this + 167) || (FreeThreadedMarshaler = SpHrFromLastWin32Error(), FreeThreadedMarshaler >= 0) )
        {
          v5 = RegisterWindowMessageW(L"9A8AB2F0-2C1E-4c1a-9F20-80FC782F8A49");
          *((_DWORD *)this + 168) = v5;
          if ( v5 || (FreeThreadedMarshaler = SpHrFromLastWin32Error(), FreeThreadedMarshaler >= 0) )
          {
            FreeThreadedMarshaler = CInvalidateMgr::Init(
                                      (CInvalidateMgr *)(this + 85),
                                      (__int64)this,
                                      *((_DWORD *)this + 169));
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
    if ( !InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)this + 4, 0x8001FA0u) )
      goto LABEL_39;
    *((_DWORD *)this + 63) = 1;
    if ( !QueryPerformanceFrequency((LARGE_INTEGER *)this + 62) )
      goto LABEL_39;
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
                  FreeThreadedMarshaler = CInkOverlay::_ReplaceInk((CInkOverlay *)this, v16, v11);
                  ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v16);
                  if ( FreeThreadedMarshaler >= 0 )
                  {
                    FreeThreadedMarshaler = CInkOverlay::_CreateCursorsCollection((CInkOverlay *)this);
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
                        *(_GUID *)&this[59][4 * (int)i].lpVtbl = *off_180161320[i];
                      if ( !(unsigned int)CInkOverlay::_LoadCursors((CInkOverlay *)this) )
LABEL_39:
                        FreeThreadedMarshaler = -2147467259;
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
0x1800d9dac  mov     [rsp-18h+arg_10], rbx
0x1800d9db1  push    rbp
0x1800d9db2  push    rsi
0x1800d9db3  push    rdi
0x1800d9db4  mov     rbp, rsp
0x1800d9db7  sub     rsp, 30h
0x1800d9dbb  mov     rdi, rcx
0x1800d9dbe  mov     [rbp+arg_0], 0
0x1800d9dc6  mov     rax, [rcx]
0x1800d9dc9  mov     rax, [rax+60h]
0x1800d9dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9dd2  lea     rdx, [rdi+100h]; ppunkMarshal
0x1800d9dd9  mov     rcx, rax; punkOuter
0x1800d9ddc  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x1800d9de2  mov     ebx, eax
0x1800d9de4  mov     esi, 8001FA0h
0x1800d9de9  test    eax, eax
0x1800d9deb  js      loc_1800D9EA9
0x1800d9df1  lea     rcx, [rdi+110h]; lpCriticalSection
0x1800d9df8  mov     edx, esi; dwSpinCount
0x1800d9dfa  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800d9e00  test    eax, eax
0x1800d9e02  jnz     short loc_1800D9E0E
0x1800d9e04  mov     ebx, 8007000Eh
0x1800d9e09  jmp     loc_1800D9EA9
0x1800d9e0e  lea     rcx, aFa233fb8B9db43; "FA233FB8-B9DB-4368-BF19-12D81DA1D0E9"
0x1800d9e15  call    cs:__imp_RegisterWindowMessageW
0x1800d9e1b  mov     [rdi+29Ch], eax
0x1800d9e21  test    eax, eax
0x1800d9e23  jnz     short loc_1800D9E30
0x1800d9e25  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x1800d9e2a  mov     ebx, eax
0x1800d9e2c  test    eax, eax
0x1800d9e2e  js      short loc_1800D9EA9
0x1800d9e30  lea     rcx, a6328ea9e8bfd4b; "6328EA9E-8BFD-4bba-8155-A7542E171BAD"
0x1800d9e37  call    cs:__imp_RegisterWindowMessageW
0x1800d9e3d  mov     [rdi+2A4h], eax
0x1800d9e43  cmp     dword ptr [rdi+29Ch], 0
0x1800d9e4a  jnz     short loc_1800D9E57
0x1800d9e4c  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x1800d9e51  mov     ebx, eax
0x1800d9e53  test    eax, eax
0x1800d9e55  js      short loc_1800D9EA9
0x1800d9e57  lea     rcx, a9a8ab2f02c1e4c; "9A8AB2F0-2C1E-4c1a-9F20-80FC782F8A49"
0x1800d9e5e  call    cs:__imp_RegisterWindowMessageW
0x1800d9e64  mov     [rdi+2A0h], eax
0x1800d9e6a  test    eax, eax
0x1800d9e6c  jnz     short loc_1800D9E79
0x1800d9e6e  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x1800d9e73  mov     ebx, eax
0x1800d9e75  test    eax, eax
0x1800d9e77  js      short loc_1800D9EA9
0x1800d9e79  lea     rcx, [rdi+2A8h]; this
0x1800d9e80  mov     r8d, [rdi+2A4h]; unsigned int
0x1800d9e87  mov     rdx, rdi; __int64
0x1800d9e8a  call    ?Init@CInvalidateMgr@@QEAAJ_JI@Z; CInvalidateMgr::Init(__int64,uint)
0x1800d9e8f  mov     ebx, eax
0x1800d9e91  test    eax, eax
0x1800d9e93  js      short loc_1800D9EA9
0x1800d9e95  xor     r8d, r8d; lpName
0x1800d9e98  xor     edx, edx; bInitialOwner
0x1800d9e9a  xor     ecx, ecx; lpMutexAttributes
0x1800d9e9c  call    cs:__imp_CreateMutexW
0x1800d9ea2  mov     [rdi+1B8h], rax
0x1800d9ea9  cmp     qword ptr [rdi+1B8h], 0
0x1800d9eb1  jz      loc_1800DA075
0x1800d9eb7  test    ebx, ebx
0x1800d9eb9  js      loc_1800DA0BA
0x1800d9ebf  lea     rbx, [rdi+0A0h]
0x1800d9ec6  mov     edx, esi; dwSpinCount
0x1800d9ec8  mov     rcx, rbx; lpCriticalSection
0x1800d9ecb  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800d9ed1  test    eax, eax
0x1800d9ed3  jz      loc_1800DA0B5
0x1800d9ed9  mov     dword ptr [rbx+5Ch], 1
0x1800d9ee0  lea     rcx, [rdi+1F0h]; lpFrequency
0x1800d9ee7  call    cs:__imp_QueryPerformanceFrequency
0x1800d9eed  test    eax, eax
0x1800d9eef  jz      loc_1800DA0B5
0x1800d9ef5  lea     r9, [rbp+arg_0]; void **
0x1800d9ef9  lea     r8, IID_IClassFactory; struct _GUID *
0x1800d9f00  lea     rdx, CLSID_TpcPlatformManager; struct _GUID *
0x1800d9f07  call    ?InternalCustomModuleGetClassObject@@YAJPEAU_ATL_MODULE@ATL@@AEBU_GUID@@1PEAPEAX@Z; InternalCustomModuleGetClassObject(ATL::_ATL_MODULE *,_GUID const &,_GUID const &,void * *)
0x1800d9f0c  mov     ebx, eax
0x1800d9f0e  test    eax, eax
0x1800d9f10  js      loc_1800DA0BA
0x1800d9f16  mov     rcx, [rbp+arg_0]
0x1800d9f1a  lea     rsi, [rdi+208h]
0x1800d9f21  mov     rax, [rcx]
0x1800d9f24  mov     r9, rsi
0x1800d9f27  lea     r8, IID_IInkManager
0x1800d9f2e  xor     edx, edx
0x1800d9f30  mov     rax, [rax+18h]
0x1800d9f34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9f39  mov     ebx, eax
0x1800d9f3b  test    eax, eax
0x1800d9f3d  js      loc_1800DA0BA
0x1800d9f43  mov     rcx, [rsi]
0x1800d9f46  mov     rax, [rcx]
0x1800d9f49  mov     rax, [rax+18h]
0x1800d9f4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9f52  mov     ebx, eax
0x1800d9f54  test    eax, eax
0x1800d9f56  js      loc_1800DA0BA
0x1800d9f5c  mov     [rbp+arg_8], 0
0x1800d9f64  lea     rcx, [rbp+arg_8]
0x1800d9f68  call    ?CreateInstance@?$CComObject@VCDrawingAttributes@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CDrawingAttributes>::CreateInstance(ATL::CComObject<CDrawingAttributes> * *)
0x1800d9f6d  mov     ebx, eax
0x1800d9f6f  test    eax, eax
0x1800d9f71  js      loc_1800DA0BA
0x1800d9f77  mov     rax, [rbp+arg_8]
0x1800d9f7b  test    rax, rax
0x1800d9f7e  jz      short loc_1800D9F86
0x1800d9f80  lea     rdx, [rax+10h]
0x1800d9f84  jmp     short loc_1800D9F88
0x1800d9f86  xor     edx, edx; struct IUnknown *
0x1800d9f88  lea     rcx, [rdi+170h]; struct IUnknown **
0x1800d9f8f  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800d9f94  mov     [rbp+arg_8], 0
0x1800d9f9c  lea     rcx, [rbp+arg_8]
0x1800d9fa0  call    ?CreateInstance@?$CComObject@VCInkRenderer@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CInkRenderer>::CreateInstance(ATL::CComObject<CInkRenderer> * *)
0x1800d9fa5  mov     ebx, eax
0x1800d9fa7  test    eax, eax
0x1800d9fa9  js      loc_1800DA0BA
0x1800d9faf  mov     rbx, [rbp+arg_8]
0x1800d9fb3  test    rbx, rbx
0x1800d9fb6  jz      short loc_1800D9FBE
0x1800d9fb8  lea     rdx, [rbx+10h]
0x1800d9fbc  jmp     short loc_1800D9FC0
0x1800d9fbe  xor     edx, edx; struct IUnknown *
0x1800d9fc0  lea     rcx, [rdi+178h]; struct IUnknown **
0x1800d9fc7  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800d9fcc  lea     rcx, [rbx+8]
0x1800d9fd0  mov     r9, [rcx]
0x1800d9fd3  mov     rax, rdi
0x1800d9fd6  lea     r8, [rdi+8]
0x1800d9fda  neg     rax
0x1800d9fdd  sbb     rdx, rdx
0x1800d9fe0  and     rdx, r8
0x1800d9fe3  mov     rax, [r9+48h]
0x1800d9fe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9fec  mov     ebx, eax
0x1800d9fee  test    eax, eax
0x1800d9ff0  js      loc_1800DA0BA
0x1800d9ff6  mov     [rbp+arg_8], 0
0x1800d9ffe  lea     rcx, [rbp+arg_8]
0x1800da002  call    ?CreateInstance@?$CComObject@VCInkObjectDisp@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CInkObjectDisp>::CreateInstance(ATL::CComObject<CInkObjectDisp> * *)
0x1800da007  mov     ebx, eax
0x1800da009  test    eax, eax
0x1800da00b  js      loc_1800DA0BA
0x1800da011  mov     rax, [rbp+arg_8]
0x1800da015  test    rax, rax
0x1800da018  jz      short loc_1800DA020
0x1800da01a  lea     rdx, [rax+8]
0x1800da01e  jmp     short loc_1800DA022
0x1800da020  xor     edx, edx
0x1800da022  lea     rcx, [rbp+arg_8]
0x1800da026  call    ??0?$CComPtr@UIUnknown@@@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComPtr<IUnknown>::CComPtr<IUnknown>(IUnknown *)
0x1800da02b  nop
0x1800da02c  mov     rdx, [rbp+arg_8]; struct IInkDisp *
0x1800da030  mov     rcx, rdi; this
0x1800da033  call    ?_ReplaceInk@CInkOverlay@@AEAAJPEAUIInkDisp@@PEAPEAU2@@Z; CInkOverlay::_ReplaceInk(IInkDisp *,IInkDisp * *)
0x1800da038  mov     ebx, eax
0x1800da03a  lea     rcx, [rbp+arg_8]; void *
0x1800da03e  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
0x1800da043  test    ebx, ebx
0x1800da045  js      short loc_1800DA0BA
0x1800da047  mov     rcx, rdi; this
0x1800da04a  call    ?_CreateCursorsCollection@CInkOverlay@@AEAAJXZ; CInkOverlay::_CreateCursorsCollection(void)
0x1800da04f  mov     ebx, eax
0x1800da051  test    eax, eax
0x1800da053  js      short loc_1800DA0BA
0x1800da055  mov     dword ptr [rdi+1D4h], 3
0x1800da05f  mov     ecx, 60h ; '`'; unsigned __int64
0x1800da064  call    ?WinMalloc@@YAPEAX_K@Z; WinMalloc(unsigned __int64)
0x1800da069  mov     [rdi+1D8h], rax
0x1800da070  test    rax, rax
0x1800da073  jnz     short loc_1800DA07C
0x1800da075  mov     ebx, 8007000Eh
0x1800da07a  jmp     short loc_1800DA0BA
0x1800da07c  xor     r8d, r8d
0x1800da07f  movsxd  rdx, r8d
0x1800da082  lea     rcx, off_180161320
0x1800da089  mov     rcx, [rcx+rdx*8]
0x1800da08d  shl     rdx, 5
0x1800da091  mov     rax, [rdi+1D8h]
0x1800da098  movups  xmm0, xmmword ptr [rcx]
0x1800da09b  movdqu  xmmword ptr [rdx+rax], xmm0
0x1800da0a0  inc     r8d
0x1800da0a3  cmp     r8d, 3
0x1800da0a7  jb      short loc_1800DA07F
0x1800da0a9  mov     rcx, rdi; this
0x1800da0ac  call    ?_LoadCursors@CInkOverlay@@AEAAHXZ; CInkOverlay::_LoadCursors(void)
0x1800da0b1  test    eax, eax
0x1800da0b3  jnz     short loc_1800DA0BA
0x1800da0b5  mov     ebx, 80004005h
0x1800da0ba  lea     rcx, [rbp+arg_0]; void *
0x1800da0be  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
0x1800da0c3  mov     eax, ebx
0x1800da0c5  mov     rbx, [rsp+30h+arg_10]
0x1800da0ca  add     rsp, 30h
0x1800da0ce  pop     rdi
0x1800da0cf  pop     rsi
0x1800da0d0  pop     rbp
0x1800da0d1  retn
```
