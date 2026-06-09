# CInkPicture::FinalConstruct(void)

- ea: `0x1800e7fdc`
- end: `0x1800e8302`
- name: `?FinalConstruct@CInkPicture@@QEAAJXZ`
- size: `806`
- prototype: `__int64 __fastcall(CInkPicture *__hidden this)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004f728`
- `0x180050d40`

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
- `0x1800e7fdc`
- `0x1800eee84`
- `0x1800f12e8`
- `0x1800f26f4`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800e80cc`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800e80cc`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800e802a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800e80fb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800e802a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800e80fb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1800e8117`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1800e8117`
- `USER32!RegisterWindowMessageW` at `0x1800e8045`
- `USER32!RegisterWindowMessageW` at `0x1800e8067`
- `USER32!RegisterWindowMessageW` at `0x1800e808e`
- `USER32!RegisterWindowMessageW` at `0x1800e8045`
- `USER32!RegisterWindowMessageW` at `0x1800e8067`
- `USER32!RegisterWindowMessageW` at `0x1800e808e`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800e800c`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800e800c`

## pseudocode

```c
__int64 __fastcall CInkPicture::FinalConstruct(LPUNKNOWN *this)
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
  FreeThreadedMarshaler = CoCreateFreeThreadedMarshaler(v2, this + 60);
  if ( FreeThreadedMarshaler >= 0 )
  {
    if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(this + 62), 0x8001FA0u) )
    {
      v4 = RegisterWindowMessageW(L"FA233FB8-B9DB-4368-BF19-12D81DA1D0E9");
      *((_DWORD *)this + 223) = v4;
      if ( v4 || (FreeThreadedMarshaler = SpHrFromLastWin32Error(), FreeThreadedMarshaler >= 0) )
      {
        *((_DWORD *)this + 225) = RegisterWindowMessageW(L"6328EA9E-8BFD-4bba-8155-A7542E171BAD");
        if ( *((_DWORD *)this + 223) || (FreeThreadedMarshaler = SpHrFromLastWin32Error(), FreeThreadedMarshaler >= 0) )
        {
          v5 = RegisterWindowMessageW(L"9A8AB2F0-2C1E-4c1a-9F20-80FC782F8A49");
          *((_DWORD *)this + 224) = v5;
          if ( v5 || (FreeThreadedMarshaler = SpHrFromLastWin32Error(), FreeThreadedMarshaler >= 0) )
          {
            FreeThreadedMarshaler = CInvalidateMgr::Init(
                                      (CInvalidateMgr *)(this + 113),
                                      (__int64)this,
                                      *((_DWORD *)this + 225));
            if ( FreeThreadedMarshaler >= 0 )
              this[83] = (LPUNKNOWN)CreateMutexW(0, 0, 0);
          }
        }
      }
    }
    else
    {
      FreeThreadedMarshaler = -2147024882;
    }
  }
  if ( !this[83] )
    goto LABEL_35;
  if ( FreeThreadedMarshaler >= 0 )
  {
    if ( !InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(this + 48), 0x8001FA0u) )
      goto LABEL_39;
    *((_DWORD *)this + 119) = 1;
    if ( !QueryPerformanceFrequency((LARGE_INTEGER *)this + 90) )
      goto LABEL_39;
    FreeThreadedMarshaler = InternalCustomModuleGetClassObject(v6, &CLSID_TpcPlatformManager, &IID_IClassFactory, &v15);
    if ( FreeThreadedMarshaler >= 0 )
    {
      FreeThreadedMarshaler = (*(__int64 (__fastcall **)(void *, _QWORD, GUID *, char *))(*(_QWORD *)v15 + 24LL))(
                                v15,
                                0,
                                &IID_IInkManager,
                                (char *)this + 744);
      if ( FreeThreadedMarshaler >= 0 )
      {
        FreeThreadedMarshaler = ((__int64 (__fastcall *)(LPUNKNOWN))this[93]->lpVtbl[1].QueryInterface)(this[93]);
        if ( FreeThreadedMarshaler >= 0 )
        {
          v16 = 0;
          FreeThreadedMarshaler = ATL::CComObject<CDrawingAttributes>::CreateInstance(&v16);
          if ( FreeThreadedMarshaler >= 0 )
          {
            v7 = v16 ? (struct IUnknown *)&v16[2] : 0LL;
            ATL::AtlComPtrAssign(this + 74, v7);
            v16 = 0;
            FreeThreadedMarshaler = ATL::CComObject<CInkRenderer>::CreateInstance(&v16);
            if ( FreeThreadedMarshaler >= 0 )
            {
              v8 = v16;
              v9 = v16 ? (struct IUnknown *)&v16[2] : 0LL;
              ATL::AtlComPtrAssign(this + 75, v9);
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
                  FreeThreadedMarshaler = CInkPicture::_ReplaceInk((CInkPicture *)this, v16, v11);
                  ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v16);
                  if ( FreeThreadedMarshaler >= 0 )
                  {
                    FreeThreadedMarshaler = CInkPicture::_CreateCursorsCollection((CInkPicture *)this);
                    if ( FreeThreadedMarshaler >= 0 )
                    {
                      *((_DWORD *)this + 173) = 3;
                      v12 = (IUnknown *)WinMalloc(0x60u);
                      this[87] = v12;
                      if ( !v12 )
                      {
LABEL_35:
                        FreeThreadedMarshaler = -2147024882;
                        goto LABEL_40;
                      }
                      for ( i = 0; i < 3; ++i )
                        *(_GUID *)&this[87][4 * (int)i].lpVtbl = *off_180161340[i];
                      if ( !(unsigned int)CInkPicture::_LoadCursors((CInkPicture *)this) )
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
0x1800e7fdc  mov     [rsp-18h+arg_10], rbx
0x1800e7fe1  push    rbp
0x1800e7fe2  push    rsi
0x1800e7fe3  push    rdi
0x1800e7fe4  mov     rbp, rsp
0x1800e7fe7  sub     rsp, 30h
0x1800e7feb  mov     rdi, rcx
0x1800e7fee  mov     [rbp+arg_0], 0
0x1800e7ff6  mov     rax, [rcx]
0x1800e7ff9  mov     rax, [rax+60h]
0x1800e7ffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e8002  lea     rdx, [rdi+1E0h]; ppunkMarshal
0x1800e8009  mov     rcx, rax; punkOuter
0x1800e800c  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x1800e8012  mov     ebx, eax
0x1800e8014  mov     esi, 8001FA0h
0x1800e8019  test    eax, eax
0x1800e801b  js      loc_1800E80D9
0x1800e8021  lea     rcx, [rdi+1F0h]; lpCriticalSection
0x1800e8028  mov     edx, esi; dwSpinCount
0x1800e802a  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800e8030  test    eax, eax
0x1800e8032  jnz     short loc_1800E803E
0x1800e8034  mov     ebx, 8007000Eh
0x1800e8039  jmp     loc_1800E80D9
0x1800e803e  lea     rcx, aFa233fb8B9db43; "FA233FB8-B9DB-4368-BF19-12D81DA1D0E9"
0x1800e8045  call    cs:__imp_RegisterWindowMessageW
0x1800e804b  mov     [rdi+37Ch], eax
0x1800e8051  test    eax, eax
0x1800e8053  jnz     short loc_1800E8060
0x1800e8055  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x1800e805a  mov     ebx, eax
0x1800e805c  test    eax, eax
0x1800e805e  js      short loc_1800E80D9
0x1800e8060  lea     rcx, a6328ea9e8bfd4b; "6328EA9E-8BFD-4bba-8155-A7542E171BAD"
0x1800e8067  call    cs:__imp_RegisterWindowMessageW
0x1800e806d  mov     [rdi+384h], eax
0x1800e8073  cmp     dword ptr [rdi+37Ch], 0
0x1800e807a  jnz     short loc_1800E8087
0x1800e807c  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x1800e8081  mov     ebx, eax
0x1800e8083  test    eax, eax
0x1800e8085  js      short loc_1800E80D9
0x1800e8087  lea     rcx, a9a8ab2f02c1e4c; "9A8AB2F0-2C1E-4c1a-9F20-80FC782F8A49"
0x1800e808e  call    cs:__imp_RegisterWindowMessageW
0x1800e8094  mov     [rdi+380h], eax
0x1800e809a  test    eax, eax
0x1800e809c  jnz     short loc_1800E80A9
0x1800e809e  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x1800e80a3  mov     ebx, eax
0x1800e80a5  test    eax, eax
0x1800e80a7  js      short loc_1800E80D9
0x1800e80a9  lea     rcx, [rdi+388h]; this
0x1800e80b0  mov     r8d, [rdi+384h]; unsigned int
0x1800e80b7  mov     rdx, rdi; __int64
0x1800e80ba  call    ?Init@CInvalidateMgr@@QEAAJ_JI@Z; CInvalidateMgr::Init(__int64,uint)
0x1800e80bf  mov     ebx, eax
0x1800e80c1  test    eax, eax
0x1800e80c3  js      short loc_1800E80D9
0x1800e80c5  xor     r8d, r8d; lpName
0x1800e80c8  xor     edx, edx; bInitialOwner
0x1800e80ca  xor     ecx, ecx; lpMutexAttributes
0x1800e80cc  call    cs:__imp_CreateMutexW
0x1800e80d2  mov     [rdi+298h], rax
0x1800e80d9  cmp     qword ptr [rdi+298h], 0
0x1800e80e1  jz      loc_1800E82A5
0x1800e80e7  test    ebx, ebx
0x1800e80e9  js      loc_1800E82EA
0x1800e80ef  lea     rbx, [rdi+180h]
0x1800e80f6  mov     edx, esi; dwSpinCount
0x1800e80f8  mov     rcx, rbx; lpCriticalSection
0x1800e80fb  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800e8101  test    eax, eax
0x1800e8103  jz      loc_1800E82E5
0x1800e8109  mov     dword ptr [rbx+5Ch], 1
0x1800e8110  lea     rcx, [rdi+2D0h]; lpFrequency
0x1800e8117  call    cs:__imp_QueryPerformanceFrequency
0x1800e811d  test    eax, eax
0x1800e811f  jz      loc_1800E82E5
0x1800e8125  lea     r9, [rbp+arg_0]; void **
0x1800e8129  lea     r8, IID_IClassFactory; struct _GUID *
0x1800e8130  lea     rdx, CLSID_TpcPlatformManager; struct _GUID *
0x1800e8137  call    ?InternalCustomModuleGetClassObject@@YAJPEAU_ATL_MODULE@ATL@@AEBU_GUID@@1PEAPEAX@Z; InternalCustomModuleGetClassObject(ATL::_ATL_MODULE *,_GUID const &,_GUID const &,void * *)
0x1800e813c  mov     ebx, eax
0x1800e813e  test    eax, eax
0x1800e8140  js      loc_1800E82EA
0x1800e8146  mov     rcx, [rbp+arg_0]
0x1800e814a  lea     rsi, [rdi+2E8h]
0x1800e8151  mov     rax, [rcx]
0x1800e8154  mov     r9, rsi
0x1800e8157  lea     r8, IID_IInkManager
0x1800e815e  xor     edx, edx
0x1800e8160  mov     rax, [rax+18h]
0x1800e8164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e8169  mov     ebx, eax
0x1800e816b  test    eax, eax
0x1800e816d  js      loc_1800E82EA
0x1800e8173  mov     rcx, [rsi]
0x1800e8176  mov     rax, [rcx]
0x1800e8179  mov     rax, [rax+18h]
0x1800e817d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e8182  mov     ebx, eax
0x1800e8184  test    eax, eax
0x1800e8186  js      loc_1800E82EA
0x1800e818c  mov     [rbp+arg_8], 0
0x1800e8194  lea     rcx, [rbp+arg_8]
0x1800e8198  call    ?CreateInstance@?$CComObject@VCDrawingAttributes@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CDrawingAttributes>::CreateInstance(ATL::CComObject<CDrawingAttributes> * *)
0x1800e819d  mov     ebx, eax
0x1800e819f  test    eax, eax
0x1800e81a1  js      loc_1800E82EA
0x1800e81a7  mov     rax, [rbp+arg_8]
0x1800e81ab  test    rax, rax
0x1800e81ae  jz      short loc_1800E81B6
0x1800e81b0  lea     rdx, [rax+10h]
0x1800e81b4  jmp     short loc_1800E81B8
0x1800e81b6  xor     edx, edx; struct IUnknown *
0x1800e81b8  lea     rcx, [rdi+250h]; struct IUnknown **
0x1800e81bf  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800e81c4  mov     [rbp+arg_8], 0
0x1800e81cc  lea     rcx, [rbp+arg_8]
0x1800e81d0  call    ?CreateInstance@?$CComObject@VCInkRenderer@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CInkRenderer>::CreateInstance(ATL::CComObject<CInkRenderer> * *)
0x1800e81d5  mov     ebx, eax
0x1800e81d7  test    eax, eax
0x1800e81d9  js      loc_1800E82EA
0x1800e81df  mov     rbx, [rbp+arg_8]
0x1800e81e3  test    rbx, rbx
0x1800e81e6  jz      short loc_1800E81EE
0x1800e81e8  lea     rdx, [rbx+10h]
0x1800e81ec  jmp     short loc_1800E81F0
0x1800e81ee  xor     edx, edx; struct IUnknown *
0x1800e81f0  lea     rcx, [rdi+258h]; struct IUnknown **
0x1800e81f7  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800e81fc  lea     rcx, [rbx+8]
0x1800e8200  mov     r9, [rcx]
0x1800e8203  mov     rax, rdi
0x1800e8206  lea     r8, [rdi+8]
0x1800e820a  neg     rax
0x1800e820d  sbb     rdx, rdx
0x1800e8210  and     rdx, r8
0x1800e8213  mov     rax, [r9+48h]
0x1800e8217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e821c  mov     ebx, eax
0x1800e821e  test    eax, eax
0x1800e8220  js      loc_1800E82EA
0x1800e8226  mov     [rbp+arg_8], 0
0x1800e822e  lea     rcx, [rbp+arg_8]
0x1800e8232  call    ?CreateInstance@?$CComObject@VCInkObjectDisp@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CInkObjectDisp>::CreateInstance(ATL::CComObject<CInkObjectDisp> * *)
0x1800e8237  mov     ebx, eax
0x1800e8239  test    eax, eax
0x1800e823b  js      loc_1800E82EA
0x1800e8241  mov     rax, [rbp+arg_8]
0x1800e8245  test    rax, rax
0x1800e8248  jz      short loc_1800E8250
0x1800e824a  lea     rdx, [rax+8]
0x1800e824e  jmp     short loc_1800E8252
0x1800e8250  xor     edx, edx
0x1800e8252  lea     rcx, [rbp+arg_8]
0x1800e8256  call    ??0?$CComPtr@UIUnknown@@@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComPtr<IUnknown>::CComPtr<IUnknown>(IUnknown *)
0x1800e825b  nop
0x1800e825c  mov     rdx, [rbp+arg_8]; struct IInkDisp *
0x1800e8260  mov     rcx, rdi; this
0x1800e8263  call    ?_ReplaceInk@CInkPicture@@AEAAJPEAUIInkDisp@@PEAPEAU2@@Z; CInkPicture::_ReplaceInk(IInkDisp *,IInkDisp * *)
0x1800e8268  mov     ebx, eax
0x1800e826a  lea     rcx, [rbp+arg_8]; void *
0x1800e826e  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
0x1800e8273  test    ebx, ebx
0x1800e8275  js      short loc_1800E82EA
0x1800e8277  mov     rcx, rdi; this
0x1800e827a  call    ?_CreateCursorsCollection@CInkPicture@@AEAAJXZ; CInkPicture::_CreateCursorsCollection(void)
0x1800e827f  mov     ebx, eax
0x1800e8281  test    eax, eax
0x1800e8283  js      short loc_1800E82EA
0x1800e8285  mov     dword ptr [rdi+2B4h], 3
0x1800e828f  mov     ecx, 60h ; '`'; unsigned __int64
0x1800e8294  call    ?WinMalloc@@YAPEAX_K@Z; WinMalloc(unsigned __int64)
0x1800e8299  mov     [rdi+2B8h], rax
0x1800e82a0  test    rax, rax
0x1800e82a3  jnz     short loc_1800E82AC
0x1800e82a5  mov     ebx, 8007000Eh
0x1800e82aa  jmp     short loc_1800E82EA
0x1800e82ac  xor     r8d, r8d
0x1800e82af  movsxd  rdx, r8d
0x1800e82b2  lea     rcx, off_180161340
0x1800e82b9  mov     rcx, [rcx+rdx*8]
0x1800e82bd  shl     rdx, 5
0x1800e82c1  mov     rax, [rdi+2B8h]
0x1800e82c8  movups  xmm0, xmmword ptr [rcx]
0x1800e82cb  movdqu  xmmword ptr [rdx+rax], xmm0
0x1800e82d0  inc     r8d
0x1800e82d3  cmp     r8d, 3
0x1800e82d7  jb      short loc_1800E82AF
0x1800e82d9  mov     rcx, rdi; this
0x1800e82dc  call    ?_LoadCursors@CInkPicture@@AEAAHXZ; CInkPicture::_LoadCursors(void)
0x1800e82e1  test    eax, eax
0x1800e82e3  jnz     short loc_1800E82EA
0x1800e82e5  mov     ebx, 80004005h
0x1800e82ea  lea     rcx, [rbp+arg_0]; void *
0x1800e82ee  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
0x1800e82f3  mov     eax, ebx
0x1800e82f5  mov     rbx, [rsp+30h+arg_10]
0x1800e82fa  add     rsp, 30h
0x1800e82fe  pop     rdi
0x1800e82ff  pop     rsi
0x1800e8300  pop     rbp
0x1800e8301  retn
```
