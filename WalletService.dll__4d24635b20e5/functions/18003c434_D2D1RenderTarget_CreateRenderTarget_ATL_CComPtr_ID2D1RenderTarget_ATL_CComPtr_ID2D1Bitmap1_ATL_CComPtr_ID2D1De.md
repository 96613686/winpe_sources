# D2D1RenderTarget::CreateRenderTarget(ATL::CComPtr<ID2D1RenderTarget> &,ATL::CComPtr<ID2D1Bitmap1> &,ATL::CComPtr<ID2D1DeviceContext> &)

- ea: `0x18003c434`
- end: `0x18003c744`
- name: `?CreateRenderTarget@D2D1RenderTarget@@AEAAJAEAV?$CComPtr@UID2D1RenderTarget@@@ATL@@AEAV?$CComPtr@UID2D1Bitmap1@@@3@AEAV?$CComPtr@UID2D1DeviceContext@@@3@@Z`
- size: `784`
- prototype: `__int64 __fastcall(__int64, struct IUnknown **, struct IUnknown **, struct IUnknown **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003ca80`

## callees

- `0x180003ae4`
- `0x180003b40`
- `0x18002d048`
- `0x18003c434`
- `0x180043090`
- `0x180045010`

## import_xrefs

- `d2d1!__imp_D2D1CreateFactory` at `0x18003c585`
- `d2d1!__imp_D2D1CreateFactory` at `0x18003c585`
- `d3d11!D3D11CreateDevice` at `0x18003c53f`
- `d3d11!D3D11CreateDevice` at `0x18003c53f`

## pseudocode

```c
__int64 __fastcall D2D1RenderTarget::CreateRenderTarget(
        __int64 a1,
        struct IUnknown **a2,
        struct IUnknown **a3,
        struct IUnknown **a4)
{
  int v7; // xmm0_4
  _DWORD *v8; // rcx
  HRESULT v9; // ebx
  struct IUnknown *v11; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v12; // [rsp+58h] [rbp-A8h] BYREF
  struct IUnknown *v13; // [rsp+60h] [rbp-A0h] BYREF
  ID3D11Device *ppDevice; // [rsp+68h] [rbp-98h] BYREF
  void *ppIFactory; // [rsp+70h] [rbp-90h] BYREF
  D3D_FEATURE_LEVEL pFeatureLevel; // [rsp+78h] [rbp-88h] BYREF
  __int64 v17; // [rsp+80h] [rbp-80h] BYREF
  __int64 (__fastcall ***v18)(_QWORD, GUID *, __int64 *); // [rsp+88h] [rbp-78h] BYREF
  struct IUnknown *v19; // [rsp+90h] [rbp-70h] BYREF
  __int64 v20[2]; // [rsp+98h] [rbp-68h] BYREF
  ID3D11DeviceContext *ppImmediateContext; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v22; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v23[3]; // [rsp+B8h] [rbp-48h] BYREF
  int v24; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v25; // [rsp+ECh] [rbp-14h]
  int v26; // [rsp+F4h] [rbp-Ch]
  int v27; // [rsp+F8h] [rbp-8h]
  __int64 v28; // [rsp+FCh] [rbp-4h]

  ppIFactory = 0;
  v20[0] = 0;
  v19 = 0;
  v11 = 0;
  ppDevice = 0;
  v13 = 0;
  v12 = 0;
  v18 = 0;
  ppImmediateContext = 0;
  v17 = 0;
  v22 = 0;
  pFeatureLevel = 0;
  v7 = *(_DWORD *)(a1 + 96);
  v20[1] = 0x100000000LL;
  v24 = 0;
  v25 = 0x100000000LL;
  v26 = v7;
  v27 = v7;
  v28 = 0;
  memset(v23, 0, 44);
  v8 = *(_DWORD **)(a1 + 88);
  LODWORD(v23[0]) = v8[2] - *v8;
  DWORD1(v23[0]) = v8[3] - v8[1];
  *((_QWORD *)&v23[0] + 1) = 0x100000001LL;
  v23[1] = 0x100000057uLL;
  *(_QWORD *)&v23[2] = 40;
  DWORD2(v23[2]) = 0;
  v9 = D3D11CreateDevice(
         0,
         D3D_DRIVER_TYPE_HARDWARE,
         0,
         0x21u,
         0,
         0,
         7u,
         &ppDevice,
         &pFeatureLevel,
         &ppImmediateContext);
  if ( v9 >= 0 )
  {
    v9 = ((__int64 (__fastcall *)(ID3D11Device *, GUID *, __int64 *))ppDevice->lpVtbl->QueryInterface)(
           ppDevice,
           &GUID_54ec77fa_1377_44e6_8c32_88fd5f44c84c,
           &v17);
    if ( v9 >= 0 )
    {
      v9 = D2D1CreateFactory(
             D2D1_FACTORY_TYPE_SINGLE_THREADED,
             &GUID_bb12d362_daee_4b9a_aa1d_14ba401cfa1f,
             0,
             &ppIFactory);
      if ( v9 >= 0 )
      {
        v9 = (*(__int64 (__fastcall **)(void *, __int64, __int64 *))(*(_QWORD *)ppIFactory + 136LL))(
               ppIFactory,
               v17,
               v20);
        if ( v9 >= 0 )
        {
          v9 = ((__int64 (__fastcall *)(ID3D11Device *, _OWORD *, _QWORD, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))ppDevice->lpVtbl->CreateTexture2D)(
                 ppDevice,
                 v23,
                 0,
                 &v18);
          if ( v9 >= 0 )
          {
            v9 = (**v18)(v18, &GUID_cafcb56c_6ac3_4889_bf47_9e23bbd260ec, &v12);
            if ( v9 >= 0 )
            {
              v9 = (*(__int64 (__fastcall **)(void *, __int64, int *, struct IUnknown **))(*(_QWORD *)ppIFactory + 120LL))(
                     ppIFactory,
                     v12,
                     &v24,
                     &v19);
              if ( v9 >= 0 )
              {
                v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IUnknown **))(*(_QWORD *)v20[0] + 32LL))(
                       v20[0],
                       0,
                       &v11);
                if ( v9 >= 0 )
                {
                  v9 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, _QWORD, struct IUnknown **))v11->lpVtbl[20].Release)(
                         v11,
                         v12,
                         0,
                         &v13);
                  if ( v9 >= 0 )
                    ((void (__fastcall *)(struct IUnknown *, struct IUnknown *))v11->lpVtbl[24].Release)(v11, v13);
                }
              }
            }
          }
        }
      }
    }
  }
  if ( *a2 != v19 )
    ATL::AtlComPtrAssign(a2, v19);
  if ( *a3 != v13 )
    ATL::AtlComPtrAssign(a3, v13);
  if ( *a4 != v11 )
    ATL::AtlComPtrAssign(a4, v11);
  ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(&v22);
  ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(&v17);
  ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>((__int64 *)&ppImmediateContext);
  ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>((__int64 *)&v18);
  ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(&v12);
  ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>((__int64 *)&v13);
  ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>((__int64 *)&ppDevice);
  ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>((__int64 *)&v11);
  ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>((__int64 *)&v19);
  ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(v20);
  ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>((__int64 *)&ppIFactory);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18003c434  push    rbp
0x18003c436  push    rbx
0x18003c437  push    rsi
0x18003c438  push    rdi
0x18003c439  push    r14
0x18003c43b  push    r15
0x18003c43d  lea     rbp, [rsp-18h]
0x18003c442  sub     rsp, 118h
0x18003c449  mov     rax, cs:__security_cookie
0x18003c450  xor     rax, rsp
0x18003c453  mov     [rbp+40h+var_38], rax
0x18003c457  mov     rdi, r9
0x18003c45a  mov     rsi, r8
0x18003c45d  mov     r14, rdx
0x18003c460  xor     r15d, r15d
0x18003c463  mov     [rsp+140h+ppIFactory], r15
0x18003c468  mov     [rbp+40h+var_A8], r15
0x18003c46c  mov     [rbp+40h+var_B0], r15
0x18003c470  mov     [rsp+140h+var_F0], r15
0x18003c475  mov     [rsp+140h+var_D8], r15
0x18003c47a  mov     [rsp+140h+var_E0], r15
0x18003c47f  mov     [rsp+140h+var_E8], r15
0x18003c484  mov     [rbp+40h+var_B8], r15
0x18003c488  mov     [rbp+40h+var_98], r15
0x18003c48c  mov     [rbp+40h+var_C0], r15
0x18003c490  mov     [rbp+40h+var_90], r15
0x18003c494  mov     [rsp+140h+var_C8], r15d
0x18003c499  movss   xmm0, dword ptr [rcx+60h]
0x18003c49e  mov     dword ptr [rbp+40h+var_A0], r15d
0x18003c4a2  lea     edx, [r15+1]; DriverType
0x18003c4a6  mov     dword ptr [rbp+40h+var_A0+4], edx
0x18003c4a9  mov     [rbp+40h+var_58], r15d
0x18003c4ad  mov     rax, [rbp+40h+var_A0]
0x18003c4b1  mov     [rbp+40h+var_54], rax
0x18003c4b5  movss   [rbp+40h+var_4C], xmm0
0x18003c4ba  movss   [rbp+40h+var_48], xmm0
0x18003c4bf  mov     [rbp+40h+var_44], r15
0x18003c4c3  xorps   xmm0, xmm0
0x18003c4c6  movups  [rbp+40h+var_88], xmm0
0x18003c4ca  movups  [rbp+40h+var_78], xmm0
0x18003c4ce  movups  [rbp+40h+var_78+0Ch], xmm0
0x18003c4d2  mov     rcx, [rcx+58h]
0x18003c4d6  mov     eax, [rcx+8]
0x18003c4d9  sub     eax, [rcx]
0x18003c4db  mov     dword ptr [rbp+40h+var_88], eax
0x18003c4de  mov     eax, [rcx+0Ch]
0x18003c4e1  sub     eax, [rcx+4]
0x18003c4e4  mov     dword ptr [rbp+40h+var_88+4], eax
0x18003c4e7  mov     dword ptr [rbp+40h+var_88+8], edx
0x18003c4ea  mov     dword ptr [rbp+40h+var_88+0Ch], edx
0x18003c4ed  mov     dword ptr [rbp+40h+var_78], 57h ; 'W'
0x18003c4f4  mov     [rbp+40h+var_68], 28h ; '('
0x18003c4fc  mov     qword ptr [rbp+40h+var_78+8], r15
0x18003c500  mov     dword ptr [rbp+40h+var_78+4], edx
0x18003c503  mov     [rbp+40h+var_60], r15d
0x18003c507  lea     rax, [rbp+40h+var_98]
0x18003c50b  mov     [rsp+140h+ppImmediateContext], rax; ppImmediateContext
0x18003c510  lea     rax, [rsp+140h+var_C8]
0x18003c515  mov     [rsp+140h+pFeatureLevel], rax; pFeatureLevel
0x18003c51a  lea     rax, [rsp+140h+var_D8]
0x18003c51f  mov     [rsp+140h+ppDevice], rax; ppDevice
0x18003c524  mov     [rsp+140h+SDKVersion], 7; SDKVersion
0x18003c52c  mov     [rsp+140h+FeatureLevels], r15d; FeatureLevels
0x18003c531  mov     [rsp+140h+pFeatureLevels], r15; pFeatureLevels
0x18003c536  lea     r9d, [r15+21h]; Flags
0x18003c53a  xor     r8d, r8d; Software
0x18003c53d  xor     ecx, ecx; pAdapter
0x18003c53f  call    cs:__imp_D3D11CreateDevice
0x18003c545  mov     ebx, eax
0x18003c547  test    eax, eax
0x18003c549  js      loc_18003C687
0x18003c54f  mov     rcx, [rsp+140h+var_D8]
0x18003c554  mov     rax, [rcx]
0x18003c557  lea     r8, [rbp+40h+var_C0]
0x18003c55b  lea     rdx, _GUID_54ec77fa_1377_44e6_8c32_88fd5f44c84c
0x18003c562  mov     rax, [rax]
0x18003c565  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c56a  mov     ebx, eax
0x18003c56c  test    eax, eax
0x18003c56e  js      loc_18003C687
0x18003c574  lea     r9, [rsp+140h+ppIFactory]; ppIFactory
0x18003c579  xor     r8d, r8d; pFactoryOptions
0x18003c57c  lea     rdx, _GUID_bb12d362_daee_4b9a_aa1d_14ba401cfa1f; riid
0x18003c583  xor     ecx, ecx; factoryType
0x18003c585  call    cs:__imp_D2D1CreateFactory
0x18003c58b  mov     ebx, eax
0x18003c58d  test    eax, eax
0x18003c58f  js      loc_18003C687
0x18003c595  mov     rcx, [rsp+140h+ppIFactory]
0x18003c59a  mov     rax, [rcx]
0x18003c59d  lea     r8, [rbp+40h+var_A8]
0x18003c5a1  mov     rdx, [rbp+40h+var_C0]
0x18003c5a5  mov     rax, [rax+88h]
0x18003c5ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c5b1  mov     ebx, eax
0x18003c5b3  test    eax, eax
0x18003c5b5  js      loc_18003C687
0x18003c5bb  mov     rcx, [rsp+140h+var_D8]
0x18003c5c0  mov     rax, [rcx]
0x18003c5c3  lea     r9, [rbp+40h+var_B8]
0x18003c5c7  xor     r8d, r8d
0x18003c5ca  lea     rdx, [rbp+40h+var_88]
0x18003c5ce  mov     rax, [rax+28h]
0x18003c5d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c5d7  mov     ebx, eax
0x18003c5d9  test    eax, eax
0x18003c5db  js      loc_18003C687
0x18003c5e1  mov     rcx, [rbp+40h+var_B8]
0x18003c5e5  mov     rax, [rcx]
0x18003c5e8  lea     r8, [rsp+140h+var_E8]
0x18003c5ed  lea     rdx, _GUID_cafcb56c_6ac3_4889_bf47_9e23bbd260ec
0x18003c5f4  mov     rax, [rax]
0x18003c5f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c5fc  mov     ebx, eax
0x18003c5fe  test    eax, eax
0x18003c600  js      loc_18003C687
0x18003c606  mov     rcx, [rsp+140h+ppIFactory]
0x18003c60b  mov     rax, [rcx]
0x18003c60e  lea     r9, [rbp+40h+var_B0]
0x18003c612  lea     r8, [rbp+40h+var_58]
0x18003c616  mov     rdx, [rsp+140h+var_E8]
0x18003c61b  mov     rax, [rax+78h]
0x18003c61f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c624  mov     ebx, eax
0x18003c626  test    eax, eax
0x18003c628  js      short loc_18003C687
0x18003c62a  mov     rcx, [rbp+40h+var_A8]
0x18003c62e  mov     rax, [rcx]
0x18003c631  lea     r8, [rsp+140h+var_F0]
0x18003c636  xor     edx, edx
0x18003c638  mov     rax, [rax+20h]
0x18003c63c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c641  mov     ebx, eax
0x18003c643  test    eax, eax
0x18003c645  js      short loc_18003C687
0x18003c647  mov     rcx, [rsp+140h+var_F0]
0x18003c64c  mov     rax, [rcx]
0x18003c64f  lea     r9, [rsp+140h+var_E0]
0x18003c654  xor     r8d, r8d
0x18003c657  mov     rdx, [rsp+140h+var_E8]
0x18003c65c  mov     rax, [rax+1F0h]
0x18003c663  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c668  mov     ebx, eax
0x18003c66a  test    eax, eax
0x18003c66c  js      short loc_18003C687
0x18003c66e  mov     rcx, [rsp+140h+var_F0]
0x18003c673  mov     rax, [rcx]
0x18003c676  mov     rdx, [rsp+140h+var_E0]
0x18003c67b  mov     rax, [rax+250h]
0x18003c682  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c687  mov     rdx, [rbp+40h+var_B0]; struct IUnknown *
0x18003c68b  cmp     [r14], rdx
0x18003c68e  jz      short loc_18003C698
0x18003c690  mov     rcx, r14; struct IUnknown **
0x18003c693  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18003c698  mov     rdx, [rsp+140h+var_E0]; struct IUnknown *
0x18003c69d  cmp     [rsi], rdx
0x18003c6a0  jz      short loc_18003C6AA
0x18003c6a2  mov     rcx, rsi; struct IUnknown **
0x18003c6a5  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18003c6aa  mov     rdx, [rsp+140h+var_F0]; struct IUnknown *
0x18003c6af  cmp     [rdi], rdx
0x18003c6b2  jz      short loc_18003C6BC
0x18003c6b4  mov     rcx, rdi; struct IUnknown **
0x18003c6b7  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18003c6bc  lea     rcx, [rbp+40h+var_90]
0x18003c6c0  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x18003c6c5  lea     rcx, [rbp+40h+var_C0]
0x18003c6c9  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x18003c6ce  lea     rcx, [rbp+40h+var_98]
0x18003c6d2  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x18003c6d7  lea     rcx, [rbp+40h+var_B8]
0x18003c6db  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x18003c6e0  lea     rcx, [rsp+140h+var_E8]
0x18003c6e5  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x18003c6ea  nop
0x18003c6eb  lea     rcx, [rsp+140h+var_E0]
0x18003c6f0  call    ??1?$CComPtrBase@UIWalletWebServiceManager@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(void)
0x18003c6f5  nop
0x18003c6f6  lea     rcx, [rsp+140h+var_D8]
0x18003c6fb  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x18003c700  lea     rcx, [rsp+140h+var_F0]
0x18003c705  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x18003c70a  lea     rcx, [rbp+40h+var_B0]
0x18003c70e  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x18003c713  lea     rcx, [rbp+40h+var_A8]
0x18003c717  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x18003c71c  lea     rcx, [rsp+140h+ppIFactory]
0x18003c721  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x18003c726  mov     eax, ebx
0x18003c728  mov     rcx, [rbp+40h+var_38]
0x18003c72c  xor     rcx, rsp; StackCookie
0x18003c72f  call    __security_check_cookie
0x18003c734  add     rsp, 118h
0x18003c73b  pop     r15
0x18003c73d  pop     r14
0x18003c73f  pop     rdi
0x18003c740  pop     rsi
0x18003c741  pop     rbx
0x18003c742  pop     rbp
0x18003c743  retn
```
