# Wallet::WalletDatabaseESE::SetCustomItemProperty(unsigned __int64,ushort const *,tagPROPVARIANT const *)

- ea: `0x180011fd0`
- end: `0x180012484`
- name: `?SetCustomItemProperty@WalletDatabaseESE@Wallet@@UEAAJ_KPEBGPEBUtagPROPVARIANT@@@Z`
- size: `1204`
- prototype: `__int64 __fastcall(Wallet::WalletDatabaseESE *__hidden this, unsigned __int64, const unsigned __int16 *, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180003ae4`
- `0x180003b40`
- `0x1800043b8`
- `0x18000fe14`
- `0x180011fd0`
- `0x18001265c`
- `0x180013a90`
- `0x18003983c`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001242c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012436`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012440`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001244a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012454`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001245e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012468`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001242c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012436`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012440`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001244a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012454`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001245e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012468`

## pseudocode

```c
__int64 __fastcall Wallet::WalletDatabaseESE::SetCustomItemProperty(
        Wallet::WalletDatabaseESE *this,
        unsigned __int64 a2,
        unsigned __int16 *a3,
        struct tagPROPVARIANT *a4)
{
  const struct tagPROPVARIANT *v8; // rdx
  int v9; // ebx
  char *v10; // rsi
  bool v11; // zf
  struct IUnknown *v12; // rbx
  struct IUnknown *punkVal; // rdx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  __int64 *v15; // rax
  const struct tagPROPVARIANT *v16; // rdx
  int v17; // ebx
  unsigned int v19; // [rsp+60h] [rbp-A0h] BYREF
  struct IUnknown *v20; // [rsp+68h] [rbp-98h] BYREF
  __int64 v21; // [rsp+70h] [rbp-90h] BYREF
  LONG v22; // [rsp+78h] [rbp-88h] BYREF
  LONG v23; // [rsp+7Ch] [rbp-84h] BYREF
  struct tagPROPVARIANT v24; // [rsp+80h] [rbp-80h] BYREF
  struct tagPROPVARIANT pvar; // [rsp+98h] [rbp-68h] BYREF
  struct tagPROPVARIANT v26; // [rsp+B0h] [rbp-50h] BYREF
  struct tagPROPVARIANT v27; // [rsp+C8h] [rbp-38h] BYREF
  struct tagPROPVARIANT v28; // [rsp+E0h] [rbp-20h] BYREF
  struct tagPROPVARIANT v29; // [rsp+F8h] [rbp-8h] BYREF
  struct tagPROPVARIANT v30[4]; // [rsp+110h] [rbp+10h] BYREF

  v22 = 0;
  memset(v30, 0, 24);
  v23 = 0;
  memset(&v29, 0, sizeof(v29));
  v21 = 0;
  memset(&v28, 0, sizeof(v28));
  v20 = 0;
  memset(&v27, 0, sizeof(v27));
  memset(&v26, 0, sizeof(v26));
  memset(&v24, 0, sizeof(v24));
  memset(&pvar, 0, sizeof(pvar));
  v9 = StringCbLengthW(a3, a2, (unsigned __int64 *)&v20);
  if ( v9 >= 0 )
  {
    v10 = (char *)&v20->lpVtbl + 2;
    if ( !(unsigned int)Wallet::Utils::IsPropVariantEmpty((Wallet::Utils *)a4, v8) )
    {
      v11 = a4->vt == 13;
      v12 = 0;
      v20 = 0;
      v19 = 0;
      if ( !v11 )
      {
        v9 = -2147024809;
LABEL_5:
        ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>((__int64 *)&v20);
        goto LABEL_27;
      }
      punkVal = a4->punkVal;
      if ( punkVal )
      {
        ATL::AtlComPtrAssign(&v20, punkVal);
        v12 = v20;
      }
      QueryInterface = v12->lpVtbl->QueryInterface;
      v15 = ce::pointerTo<IWalletNotification>(&v21);
      v9 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))QueryInterface)(
             v12,
             &GUID_21f1a452_9759_48a5_8d9b_bbd859ef89ee,
             v15);
      if ( v9 < 0 )
        goto LABEL_5;
      v9 = (*(__int64 (__fastcall **)(__int64, struct tagPROPVARIANT *))(*(_QWORD *)v21 + 24LL))(v21, v30);
      if ( v9 < 0 )
        goto LABEL_5;
      v9 = (*(__int64 (__fastcall **)(__int64, struct tagPROPVARIANT *))(*(_QWORD *)v21 + 40LL))(v21, &v29);
      if ( v9 < 0 )
        goto LABEL_5;
      v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v21 + 56LL))(v21, &v19);
      if ( v9 < 0 )
        goto LABEL_5;
      v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, ULONG *, LONG *))(*(_QWORD *)v21 + 72LL))(
             v21,
             0,
             &v27.ulVal,
             &v22);
      if ( v9 < 0 )
        goto LABEL_5;
      v26.lVal = v22;
      v27.vt = 22;
      v26.vt = 22;
      v9 = (*(__int64 (__fastcall **)(__int64, __int64, ULONG *, LONG *))(*(_QWORD *)v21 + 72LL))(
             v21,
             1,
             &v24.ulVal,
             &v23);
      if ( v9 < 0 )
        goto LABEL_5;
      if ( v24.lVal )
      {
        v24.vt = 22;
        pvar.vt = 22;
      }
      else
      {
        v24.vt = 0;
        pvar.vt = 0;
      }
      pvar.lVal = v23;
      v28.vt = 18;
      v28.iVal = v19;
      ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>((__int64 *)&v20);
    }
    v17 = Wallet::WalletDatabaseESE::_SetProperty(this, a2, a3, (unsigned __int64)v10, 3u, 2u, v29.vt, 0, &v29, 1, 0);
    if ( v17 >= 0 && !(unsigned int)Wallet::Utils::IsPropVariantEmpty((Wallet::Utils *)&v29, v16) )
    {
      v17 = Wallet::WalletDatabaseESE::_SetProperty(this, a2, a3, (unsigned __int64)v10, 3u, 3u, v28.vt, 2u, &v28, 0, 0);
      if ( v17 >= 0 )
      {
        v17 = Wallet::WalletDatabaseESE::_SetProperty(
                this,
                a2,
                a3,
                (unsigned __int64)v10,
                3u,
                4u,
                v30[0].vt,
                0x1000u,
                v30,
                0,
                0);
        if ( v17 >= 0 )
        {
          v19 = 1;
          v17 = Wallet::WalletDatabaseESE::_SetProperty(
                  this,
                  a2,
                  a3,
                  (unsigned __int64)v10,
                  3u,
                  5u,
                  v27.vt,
                  0x1000u,
                  &v27,
                  0,
                  &v19);
          if ( v17 >= 0 )
          {
            v17 = Wallet::WalletDatabaseESE::_SetProperty(
                    this,
                    a2,
                    a3,
                    (unsigned __int64)v10,
                    3u,
                    6u,
                    v26.vt,
                    4u,
                    &v26,
                    0,
                    &v19);
            if ( v17 >= 0 )
            {
              v19 = 2;
              v17 = Wallet::WalletDatabaseESE::_SetProperty(
                      this,
                      a2,
                      a3,
                      (unsigned __int64)v10,
                      3u,
                      5u,
                      v24.vt,
                      0x1000u,
                      &v24,
                      0,
                      &v19);
              if ( v17 >= 0 )
                v17 = Wallet::WalletDatabaseESE::_SetProperty(
                        this,
                        a2,
                        a3,
                        (unsigned __int64)v10,
                        3u,
                        6u,
                        pvar.vt,
                        4u,
                        &pvar,
                        0,
                        &v19);
            }
          }
        }
      }
    }
    v9 = Wallet::WalletDatabaseESE::JetErrToHR(v17);
  }
LABEL_27:
  ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(&v21);
  PropVariantClear((PROPVARIANT *)&pvar);
  PropVariantClear((PROPVARIANT *)&v24);
  PropVariantClear((PROPVARIANT *)&v26);
  PropVariantClear((PROPVARIANT *)&v27);
  PropVariantClear((PROPVARIANT *)&v28);
  PropVariantClear((PROPVARIANT *)&v29);
  PropVariantClear((PROPVARIANT *)v30);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180011fd0  push    rbp
0x180011fd2  push    rbx
0x180011fd3  push    rsi
0x180011fd4  push    rdi
0x180011fd5  push    r12
0x180011fd7  push    r13
0x180011fd9  push    r14
0x180011fdb  push    r15
0x180011fdd  lea     rbp, [rsp-38h]
0x180011fe2  sub     rsp, 138h
0x180011fe9  xor     eax, eax
0x180011feb  xorps   xmm0, xmm0
0x180011fee  xor     r13d, r13d
0x180011ff1  mov     [rbp+70h+var_50], rax
0x180011ff5  xorps   xmm1, xmm1
0x180011ff8  mov     [rbp+70h+var_68], rax
0x180011ffc  mov     r14, r8
0x180011fff  mov     [rbp+70h+var_80], rax
0x180012003  mov     r12, rcx
0x180012006  mov     [rbp+70h+var_98], rax
0x18001200a  mov     rcx, r14; unsigned __int16 *
0x18001200d  mov     [rbp+70h+var_B0], rax
0x180012011  lea     r8, [rsp+170h+var_108]; unsigned __int64 *
0x180012016  mov     [rbp+70h+var_E0], rax
0x18001201a  mov     rdi, r9
0x18001201d  mov     [rbp+70h+var_C8], rax
0x180012021  mov     r15, rdx
0x180012024  mov     [rsp+170h+var_F8], r13d
0x180012029  movups  xmmword ptr [rbp+70h+var_60], xmm0
0x18001202d  mov     [rsp+170h+var_F4], r13d
0x180012032  movups  xmmword ptr [rbp+70h+var_78], xmm1
0x180012036  mov     [rsp+170h+var_100], r13
0x18001203b  movups  xmmword ptr [rbp+70h+var_90], xmm0
0x18001203f  mov     [rsp+170h+var_108], r13
0x180012044  movups  xmmword ptr [rbp+70h+var_A8], xmm1
0x180012048  movups  xmmword ptr [rbp+70h+var_C0], xmm0
0x18001204c  movups  xmmword ptr [rbp+70h+var_F0], xmm1
0x180012050  movups  xmmword ptr [rbp+70h+pvar], xmm0
0x180012054  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180012059  mov     ebx, eax
0x18001205b  test    eax, eax
0x18001205d  js      loc_18001241E
0x180012063  mov     rsi, [rsp+170h+var_108]
0x180012068  mov     rcx, rdi; this
0x18001206b  add     rsi, 2
0x18001206f  call    ?IsPropVariantEmpty@Utils@Wallet@@YAHPEBUtagPROPVARIANT@@@Z; Wallet::Utils::IsPropVariantEmpty(tagPROPVARIANT const *)
0x180012074  test    eax, eax
0x180012076  jnz     loc_1800121DE
0x18001207c  cmp     word ptr [rdi], 0Dh
0x180012080  mov     ebx, r13d
0x180012083  mov     [rsp+170h+var_108], rbx
0x180012088  mov     [rsp+170h+var_110], r13d
0x18001208d  jz      short loc_1800120A3
0x18001208f  mov     ebx, 80070057h
0x180012094  lea     rcx, [rsp+170h+var_108]
0x180012099  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x18001209e  jmp     loc_18001241E
0x1800120a3  mov     rdx, [rdi+8]; struct IUnknown *
0x1800120a7  test    rdx, rdx
0x1800120aa  jz      short loc_1800120BB
0x1800120ac  lea     rcx, [rsp+170h+var_108]; struct IUnknown **
0x1800120b1  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800120b6  mov     rbx, [rsp+170h+var_108]
0x1800120bb  mov     rax, [rbx]
0x1800120be  lea     rcx, [rsp+170h+var_100]
0x1800120c3  mov     rdi, [rax]
0x1800120c6  call    ??$pointerTo@UIWalletNotification@@@ce@@YAPEAPEAUIWalletNotification@@AEAV?$CComPtr@UIWalletNotification@@@ATL@@@Z; ce::pointerTo<IWalletNotification>(ATL::CComPtr<IWalletNotification> &)
0x1800120cb  mov     r8, rax
0x1800120ce  lea     rdx, _GUID_21f1a452_9759_48a5_8d9b_bbd859ef89ee
0x1800120d5  mov     rax, rdi
0x1800120d8  mov     rcx, rbx
0x1800120db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120e0  mov     ebx, eax
0x1800120e2  test    eax, eax
0x1800120e4  js      short loc_180012094
0x1800120e6  mov     rcx, [rsp+170h+var_100]
0x1800120eb  lea     rdx, [rbp+70h+var_60]
0x1800120ef  mov     rax, [rcx]
0x1800120f2  mov     rax, [rax+18h]
0x1800120f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120fb  mov     ebx, eax
0x1800120fd  test    eax, eax
0x1800120ff  js      short loc_180012094
0x180012101  mov     rcx, [rsp+170h+var_100]
0x180012106  lea     rdx, [rbp+70h+var_78]
0x18001210a  mov     rax, [rcx]
0x18001210d  mov     rax, [rax+28h]
0x180012111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012116  mov     ebx, eax
0x180012118  test    eax, eax
0x18001211a  js      loc_180012094
0x180012120  mov     rcx, [rsp+170h+var_100]
0x180012125  lea     rdx, [rsp+170h+var_110]
0x18001212a  mov     rax, [rcx]
0x18001212d  mov     rax, [rax+38h]
0x180012131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012136  mov     ebx, eax
0x180012138  test    eax, eax
0x18001213a  js      loc_180012094
0x180012140  mov     rcx, [rsp+170h+var_100]
0x180012145  lea     r9, [rsp+170h+var_F8]
0x18001214a  lea     r8, [rbp+70h+var_A8+8]
0x18001214e  xor     edx, edx
0x180012150  mov     rax, [rcx]
0x180012153  mov     rax, [rax+48h]
0x180012157  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001215c  mov     ebx, eax
0x18001215e  test    eax, eax
0x180012160  js      loc_180012094
0x180012166  mov     eax, [rsp+170h+var_F8]
0x18001216a  lea     r9, [rsp+170h+var_F4]
0x18001216f  mov     rcx, [rsp+170h+var_100]
0x180012174  lea     r8, [rbp+70h+var_F0+8]
0x180012178  mov     edi, 16h
0x18001217d  mov     dword ptr [rbp+70h+var_C0+8], eax
0x180012180  mov     word ptr [rbp+70h+var_A8], di
0x180012184  mov     word ptr [rbp+70h+var_C0], di
0x180012188  mov     rax, [rcx]
0x18001218b  lea     edx, [rdi-15h]
0x18001218e  mov     rax, [rax+48h]
0x180012192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012197  mov     ebx, eax
0x180012199  test    eax, eax
0x18001219b  js      loc_180012094
0x1800121a1  cmp     dword ptr [rbp+70h+var_F0+8], r13d
0x1800121a5  jnz     short loc_1800121B3
0x1800121a7  mov     word ptr [rbp+70h+var_F0], r13w
0x1800121ac  mov     word ptr [rbp+70h+pvar], r13w
0x1800121b1  jmp     short loc_1800121BB
0x1800121b3  mov     word ptr [rbp+70h+var_F0], di
0x1800121b7  mov     word ptr [rbp+70h+pvar], di
0x1800121bb  mov     eax, [rsp+170h+var_F4]
0x1800121bf  lea     rcx, [rsp+170h+var_108]
0x1800121c4  mov     dword ptr [rbp+70h+pvar+8], eax
0x1800121c7  mov     eax, 12h
0x1800121cc  mov     word ptr [rbp+70h+var_90], ax
0x1800121d0  movzx   eax, word ptr [rsp+170h+var_110]
0x1800121d5  mov     word ptr [rbp+70h+var_90+8], ax
0x1800121d9  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x1800121de  mov     [rsp+170h+var_120], r13; unsigned int *
0x1800121e3  lea     rax, [rbp+70h+var_78]
0x1800121e7  mov     [rsp+170h+var_128], 1; int
0x1800121ef  mov     edi, 3
0x1800121f4  mov     [rsp+170h+var_130], rax; struct tagPROPVARIANT *
0x1800121f9  mov     r9, rsi; unsigned __int64
0x1800121fc  movzx   eax, word ptr [rbp+70h+var_78]
0x180012200  mov     r8, r14; void *
0x180012203  mov     [rsp+170h+var_138], r13d; unsigned int
0x180012208  mov     rdx, r15; unsigned __int64
0x18001220b  mov     [rsp+170h+var_140], ax; unsigned __int16
0x180012210  mov     rcx, r12; this
0x180012213  mov     [rsp+170h+var_148], 2; unsigned int
0x18001221b  mov     [rsp+170h+var_150], edi; unsigned int
0x18001221f  call    ?_SetProperty@WalletDatabaseESE@Wallet@@AEAAJ_KPEAX0KKGKPEBUtagPROPVARIANT@@HPEAK@Z; Wallet::WalletDatabaseESE::_SetProperty(unsigned __int64,void *,unsigned __int64,ulong,ulong,ushort,ulong,tagPROPVARIANT const *,int,ulong *)
0x180012224  mov     ebx, eax
0x180012226  test    eax, eax
0x180012228  js      loc_180012415
0x18001222e  lea     rcx, [rbp+70h+var_78]; this
0x180012232  call    ?IsPropVariantEmpty@Utils@Wallet@@YAHPEBUtagPROPVARIANT@@@Z; Wallet::Utils::IsPropVariantEmpty(tagPROPVARIANT const *)
0x180012237  test    eax, eax
0x180012239  jnz     loc_180012415
0x18001223f  mov     [rsp+170h+var_120], r13; unsigned int *
0x180012244  lea     rax, [rbp+70h+var_90]
0x180012248  mov     [rsp+170h+var_128], r13d; int
0x18001224d  mov     r9, rsi; unsigned __int64
0x180012250  mov     [rsp+170h+var_130], rax; struct tagPROPVARIANT *
0x180012255  mov     r8, r14; void *
0x180012258  movzx   eax, word ptr [rbp+70h+var_90]
0x18001225c  mov     rdx, r15; unsigned __int64
0x18001225f  mov     [rsp+170h+var_138], 2; unsigned int
0x180012267  mov     rcx, r12; this
0x18001226a  mov     [rsp+170h+var_140], ax; unsigned __int16
0x18001226f  mov     [rsp+170h+var_148], edi; unsigned int
0x180012273  mov     [rsp+170h+var_150], edi; unsigned int
0x180012277  call    ?_SetProperty@WalletDatabaseESE@Wallet@@AEAAJ_KPEAX0KKGKPEBUtagPROPVARIANT@@HPEAK@Z; Wallet::WalletDatabaseESE::_SetProperty(unsigned __int64,void *,unsigned __int64,ulong,ulong,ushort,ulong,tagPROPVARIANT const *,int,ulong *)
0x18001227c  mov     ebx, eax
0x18001227e  test    eax, eax
0x180012280  js      loc_180012415
0x180012286  mov     [rsp+170h+var_120], r13; unsigned int *
0x18001228b  lea     rax, [rbp+70h+var_60]
0x18001228f  mov     [rsp+170h+var_128], r13d; int
0x180012294  mov     r9, rsi; unsigned __int64
0x180012297  mov     [rsp+170h+var_130], rax; struct tagPROPVARIANT *
0x18001229c  mov     r8, r14; void *
0x18001229f  movzx   eax, word ptr [rbp+70h+var_60]
0x1800122a3  mov     rdx, r15; unsigned __int64
0x1800122a6  mov     [rsp+170h+var_138], 1000h; unsigned int
0x1800122ae  mov     rcx, r12; this
0x1800122b1  mov     [rsp+170h+var_140], ax; unsigned __int16
0x1800122b6  mov     [rsp+170h+var_148], 4; unsigned int
0x1800122be  mov     [rsp+170h+var_150], edi; unsigned int
0x1800122c2  call    ?_SetProperty@WalletDatabaseESE@Wallet@@AEAAJ_KPEAX0KKGKPEBUtagPROPVARIANT@@HPEAK@Z; Wallet::WalletDatabaseESE::_SetProperty(unsigned __int64,void *,unsigned __int64,ulong,ulong,ushort,ulong,tagPROPVARIANT const *,int,ulong *)
0x1800122c7  mov     ebx, eax
0x1800122c9  test    eax, eax
0x1800122cb  js      loc_180012415
0x1800122d1  lea     rax, [rsp+170h+var_110]
0x1800122d6  mov     [rsp+170h+var_110], 1
0x1800122de  mov     [rsp+170h+var_120], rax; unsigned int *
0x1800122e3  mov     r9, rsi; unsigned __int64
0x1800122e6  mov     [rsp+170h+var_128], r13d; int
0x1800122eb  lea     rax, [rbp+70h+var_A8]
0x1800122ef  mov     [rsp+170h+var_130], rax; struct tagPROPVARIANT *
0x1800122f4  mov     r8, r14; void *
0x1800122f7  movzx   eax, word ptr [rbp+70h+var_A8]
0x1800122fb  mov     rdx, r15; unsigned __int64
0x1800122fe  mov     [rsp+170h+var_138], 1000h; unsigned int
0x180012306  mov     rcx, r12; this
0x180012309  mov     [rsp+170h+var_140], ax; unsigned __int16
0x18001230e  mov     [rsp+170h+var_148], 5; unsigned int
0x180012316  mov     [rsp+170h+var_150], edi; unsigned int
0x18001231a  call    ?_SetProperty@WalletDatabaseESE@Wallet@@AEAAJ_KPEAX0KKGKPEBUtagPROPVARIANT@@HPEAK@Z; Wallet::WalletDatabaseESE::_SetProperty(unsigned __int64,void *,unsigned __int64,ulong,ulong,ushort,ulong,tagPROPVARIANT const *,int,ulong *)
0x18001231f  mov     ebx, eax
0x180012321  test    eax, eax
0x180012323  js      loc_180012415
0x180012329  lea     rax, [rsp+170h+var_110]
0x18001232e  mov     r9, rsi; unsigned __int64
0x180012331  mov     [rsp+170h+var_120], rax; unsigned int *
0x180012336  mov     r8, r14; void *
0x180012339  mov     [rsp+170h+var_128], r13d; int
0x18001233e  lea     rax, [rbp+70h+var_C0]
0x180012342  mov     [rsp+170h+var_130], rax; struct tagPROPVARIANT *
0x180012347  mov     rdx, r15; unsigned __int64
0x18001234a  movzx   eax, word ptr [rbp+70h+var_C0]
0x18001234e  mov     rcx, r12; this
0x180012351  mov     [rsp+170h+var_138], 4; unsigned int
0x180012359  mov     [rsp+170h+var_140], ax; unsigned __int16
0x18001235e  mov     [rsp+170h+var_148], 6; unsigned int
0x180012366  mov     [rsp+170h+var_150], edi; unsigned int
0x18001236a  call    ?_SetProperty@WalletDatabaseESE@Wallet@@AEAAJ_KPEAX0KKGKPEBUtagPROPVARIANT@@HPEAK@Z; Wallet::WalletDatabaseESE::_SetProperty(unsigned __int64,void *,unsigned __int64,ulong,ulong,ushort,ulong,tagPROPVARIANT const *,int,ulong *)
0x18001236f  mov     ebx, eax
0x180012371  test    eax, eax
0x180012373  js      loc_180012415
0x180012379  lea     rax, [rsp+170h+var_110]
0x18001237e  mov     [rsp+170h+var_110], 2
0x180012386  mov     [rsp+170h+var_120], rax; unsigned int *
0x18001238b  mov     r9, rsi; unsigned __int64
0x18001238e  mov     [rsp+170h+var_128], r13d; int
0x180012393  lea     rax, [rbp+70h+var_F0]
0x180012397  mov     [rsp+170h+var_130], rax; struct tagPROPVARIANT *
0x18001239c  mov     r8, r14; void *
0x18001239f  movzx   eax, word ptr [rbp+70h+var_F0]
0x1800123a3  mov     rdx, r15; unsigned __int64
0x1800123a6  mov     [rsp+170h+var_138], 1000h; unsigned int
0x1800123ae  mov     rcx, r12; this
0x1800123b1  mov     [rsp+170h+var_140], ax; unsigned __int16
0x1800123b6  mov     [rsp+170h+var_148], 5; unsigned int
0x1800123be  mov     [rsp+170h+var_150], edi; unsigned int
0x1800123c2  call    ?_SetProperty@WalletDatabaseESE@Wallet@@AEAAJ_KPEAX0KKGKPEBUtagPROPVARIANT@@HPEAK@Z; Wallet::WalletDatabaseESE::_SetProperty(unsigned __int64,void *,unsigned __int64,ulong,ulong,ushort,ulong,tagPROPVARIANT const *,int,ulong *)
0x1800123c7  mov     ebx, eax
0x1800123c9  test    eax, eax
0x1800123cb  js      short loc_180012415
0x1800123cd  lea     rax, [rsp+170h+var_110]
0x1800123d2  mov     r9, rsi; unsigned __int64
0x1800123d5  mov     [rsp+170h+var_120], rax; unsigned int *
0x1800123da  mov     r8, r14; void *
0x1800123dd  mov     [rsp+170h+var_128], r13d; int
0x1800123e2  lea     rax, [rbp+70h+pvar]
0x1800123e6  mov     [rsp+170h+var_130], rax; struct tagPROPVARIANT *
0x1800123eb  mov     rdx, r15; unsigned __int64
0x1800123ee  movzx   eax, word ptr [rbp+70h+pvar]
0x1800123f2  mov     rcx, r12; this
0x1800123f5  mov     [rsp+170h+var_138], 4; unsigned int
0x1800123fd  mov     [rsp+170h+var_140], ax; unsigned __int16
0x180012402  mov     [rsp+170h+var_148], 6; unsigned int
0x18001240a  mov     [rsp+170h+var_150], edi; unsigned int
0x18001240e  call    ?_SetProperty@WalletDatabaseESE@Wallet@@AEAAJ_KPEAX0KKGKPEBUtagPROPVARIANT@@HPEAK@Z; Wallet::WalletDatabaseESE::_SetProperty(unsigned __int64,void *,unsigned __int64,ulong,ulong,ushort,ulong,tagPROPVARIANT const *,int,ulong *)
0x180012413  mov     ebx, eax
0x180012415  mov     ecx, ebx; int
0x180012417  call    ?JetErrToHR@WalletDatabaseESE@Wallet@@CAJJ@Z; Wallet::WalletDatabaseESE::JetErrToHR(long)
0x18001241c  mov     ebx, eax
0x18001241e  lea     rcx, [rsp+170h+var_100]
0x180012423  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x180012428  lea     rcx, [rbp+70h+pvar]; pvar
0x18001242c  call    cs:__imp_PropVariantClear
0x180012432  lea     rcx, [rbp+70h+var_F0]; pvar
0x180012436  call    cs:__imp_PropVariantClear
0x18001243c  lea     rcx, [rbp+70h+var_C0]; pvar
0x180012440  call    cs:__imp_PropVariantClear
0x180012446  lea     rcx, [rbp+70h+var_A8]; pvar
0x18001244a  call    cs:__imp_PropVariantClear
0x180012450  lea     rcx, [rbp+70h+var_90]; pvar
0x180012454  call    cs:__imp_PropVariantClear
0x18001245a  lea     rcx, [rbp+70h+var_78]; pvar
0x18001245e  call    cs:__imp_PropVariantClear
0x180012464  lea     rcx, [rbp+70h+var_60]; pvar
0x180012468  call    cs:__imp_PropVariantClear
0x18001246e  mov     eax, ebx
0x180012470  add     rsp, 138h
0x180012477  pop     r15
0x180012479  pop     r14
0x18001247b  pop     r13
0x18001247d  pop     r12
0x18001247f  pop     rdi
0x180012480  pop     rsi
0x180012481  pop     rbx
0x180012482  pop     rbp
0x180012483  retn
```
