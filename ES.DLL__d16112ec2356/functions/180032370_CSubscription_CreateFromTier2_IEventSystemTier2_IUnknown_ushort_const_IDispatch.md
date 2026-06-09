# CSubscription::CreateFromTier2(IEventSystemTier2 *,IUnknown *,ushort const * *,IDispatch * *)

- ea: `0x180032370`
- end: `0x180032941`
- name: `?CreateFromTier2@CSubscription@@SAJPEAUIEventSystemTier2@@PEAUIUnknown@@PEAPEBGPEAPEAUIDispatch@@@Z`
- size: `1489`
- prototype: `__int64 __fastcall(struct IEventSystemTier2 *, struct IUnknown *, const unsigned __int16 **, struct IDispatch **)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180008938`
- `0x180012654`
- `0x180015850`
- `0x180015efc`
- `0x180022778`
- `0x180032370`
- `0x18003f080`
- `0x180046010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180032638`
- `OLEAUT32!__imp_VariantInit` at `0x180032717`
- `OLEAUT32!__imp_VariantInit` at `0x180032638`
- `OLEAUT32!__imp_VariantInit` at `0x180032717`
- `OLEAUT32!__imp_VariantClear` at `0x180032683`
- `OLEAUT32!__imp_VariantClear` at `0x180032696`
- `OLEAUT32!__imp_VariantClear` at `0x180032762`
- `OLEAUT32!__imp_VariantClear` at `0x18003277e`
- `OLEAUT32!__imp_VariantClear` at `0x180032683`
- `OLEAUT32!__imp_VariantClear` at `0x180032696`
- `OLEAUT32!__imp_VariantClear` at `0x180032762`
- `OLEAUT32!__imp_VariantClear` at `0x18003277e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003278e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003279c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800327aa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800327b8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003278e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003279c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800327aa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800327b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800323a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800323a0`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180032459`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180032459`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003285e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003285e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180032896`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180032896`
- `PROPSYS!PropVariantToVariant` at `0x180032653`
- `PROPSYS!PropVariantToVariant` at `0x180032732`
- `PROPSYS!PropVariantToVariant` at `0x180032653`
- `PROPSYS!PropVariantToVariant` at `0x180032732`

## string_xrefs

- `0x1800325f9`: `com\complus\src\events\tier1\subscription.cpp`
- `0x1800326da`: `com\complus\src\events\tier1\subscription.cpp`
- `0x18003290f`: `com\complus\src\events\tier1\subscription.cpp`

## pseudocode

```c
__int64 __fastcall CSubscription::CreateFromTier2(
        struct IEventSystemTier2 *a1,
        struct IUnknown *a2,
        const unsigned __int16 **a3,
        struct IDispatch **a4)
{
  const unsigned __int16 **v5; // r12
  struct IEventSystemTier2 *v7; // r15
  CSubscription *v8; // rax
  CSubscription *v9; // r14
  HRESULT Instance; // ebx
  unsigned int v12; // r9d
  __int64 i; // r12
  int v14; // esi
  __int64 v15; // rsi
  __int64 v16; // r15
  __int64 v17; // rsi
  int v18; // eax
  struct IUnknown *v19; // [rsp+58h] [rbp-120h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-118h] BYREF
  IUnknown *pProxy; // [rsp+80h] [rbp-F8h] BYREF
  HRESULT v22; // [rsp+88h] [rbp-F0h]
  struct tagBLOB v23; // [rsp+90h] [rbp-E8h] BYREF
  CSubscription *v24; // [rsp+A0h] [rbp-D8h]
  PROPVARIANT pvar[2]; // [rsp+A8h] [rbp-D0h] BYREF
  __int64 v26; // [rsp+B8h] [rbp-C0h]
  PROPVARIANT v27[2]; // [rsp+C0h] [rbp-B8h] BYREF
  __int64 v28; // [rsp+D0h] [rbp-A8h]
  PROPVARIANT v29[2]; // [rsp+D8h] [rbp-A0h] BYREF
  __int64 v30; // [rsp+E8h] [rbp-90h]
  PROPVARIANT v31[2]; // [rsp+F0h] [rbp-88h] BYREF
  __int64 v32; // [rsp+100h] [rbp-78h]
  struct tagPROPVARIANT v33; // [rsp+110h] [rbp-68h] BYREF
  struct tagPROPVARIANT v34; // [rsp+130h] [rbp-48h] BYREF

  v5 = a3;
  v7 = a1;
  v8 = (CSubscription *)CoTaskMemAlloc(0x388u);
  if ( v8 )
    v9 = CSubscription::CSubscription(v8);
  else
    v9 = 0;
  v24 = v9;
  if ( !v9 )
    return 2147942414LL;
  Instance = (**(__int64 (__fastcall ***)(CSubscription *, GUID *, struct IDispatch **))v9)(
               v9,
               &IID_IEventSubscription2,
               a4);
  if ( Instance >= 0 )
  {
    pProxy = 0;
    Instance = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, IUnknown **))a2->lpVtbl->QueryInterface)(
                 a2,
                 &IID_IEventSubscriptionTier2,
                 &pProxy);
    if ( Instance >= 0 )
    {
      CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, 0, 0, 3u, 0, 0x40u);
      *(_OWORD *)pvar = 0;
      v26 = 0;
      *(_OWORD *)v29 = 0;
      v30 = 0;
      *(_OWORD *)v27 = 0;
      v28 = 0;
      *(_OWORD *)v31 = 0;
      v32 = 0;
      v19 = 0;
      *(_QWORD *)&v23.cbSize = 0;
      v23.pBlobData = 0;
      Instance = ((__int64 (__fastcall *)(IUnknown *, struct IEventSystemTier2 *, char *, PROPVARIANT *, PROPVARIANT *, PROPVARIANT *, PROPVARIANT *, struct tagBLOB *))pProxy->lpVtbl[1].AddRef)(
                   pProxy,
                   v7,
                   (char *)v9 + 40,
                   pvar,
                   v29,
                   v27,
                   v31,
                   &v23);
      ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
      if ( Instance < 0 )
      {
        v14 = Instance;
      }
      else
      {
        pvarg = *(VARIANTARG *)((char *)v9 + 448);
        v33 = *(struct tagPROPVARIANT *)((char *)v9 + 424);
        v34 = *(struct tagPROPVARIANT *)((char *)v9 + 40);
        Instance = ConcatenateECID_PARTID_APPID(
                     &v34,
                     &v33,
                     (struct tagPROPVARIANT *)&pvarg,
                     v12,
                     (unsigned __int16 *)v9 + 334);
        if ( Instance >= 0 && LOWORD(pvar[0]) == 4127 )
        {
          if ( LOWORD(v29[0]) != 4108 )
            InternalAssert(
              L"com\\complus\\src\\events\\tier1\\subscription.cpp",
              0xB8u,
              0x10u,
              L"pubProps.vt == (VT_VECTOR | VT_VARIANT)");
          for ( i = 0; ; i = (unsigned int)(i + 1) )
          {
            v14 = Instance;
            if ( (unsigned int)i >= LODWORD(pvar[1]) )
              break;
            v15 = *(_QWORD *)(v26 + 8 * i);
            memset(&pvarg, 0, sizeof(pvarg));
            VariantInit(&pvarg);
            Instance = PropVariantToVariant((const PROPVARIANT *)(v30 + 24 * i), &pvarg);
            if ( Instance < 0 )
            {
              VariantClear(&pvarg);
              v14 = Instance;
              break;
            }
            (*(void (__fastcall **)(__int64, VARIANTARG *, __int64))(*((_QWORD *)v9 + 61) + 88LL))(
              (__int64)v9 + 488,
              &pvarg,
              v15);
            VariantClear(&pvarg);
          }
          v5 = a3;
        }
        else
        {
          v14 = Instance;
        }
        if ( v14 >= 0 && LOWORD(v27[0]) == 4127 )
        {
          if ( LOWORD(v31[0]) != 4108 )
            InternalAssert(
              L"com\\complus\\src\\events\\tier1\\subscription.cpp",
              0xCDu,
              0x10u,
              L"subProps.vt == (VT_VECTOR | VT_VARIANT)");
          v16 = 0;
          while ( (unsigned int)v16 < LODWORD(v27[1]) )
          {
            v17 = *(_QWORD *)(v28 + 8 * v16);
            memset(&pvarg, 0, sizeof(pvarg));
            VariantInit(&pvarg);
            Instance = PropVariantToVariant((const PROPVARIANT *)(v32 + 24 * v16), &pvarg);
            if ( Instance < 0 )
            {
              VariantClear(&pvarg);
              v14 = Instance;
              break;
            }
            (*(void (__fastcall **)(__int64, VARIANTARG *, __int64))(*((_QWORD *)v9 + 72) + 88LL))(
              (__int64)v9 + 576,
              &pvarg,
              v17);
            VariantClear(&pvarg);
            v16 = (unsigned int)(v16 + 1);
            v14 = Instance;
          }
        }
        PropVariantClear(pvar);
        PropVariantClear(v29);
        PropVariantClear(v27);
        PropVariantClear(v31);
        v7 = a1;
        if ( v14 < 0 )
          goto LABEL_41;
        if ( v5 )
          *v5 = (const unsigned __int16 *)((char *)v9 + 668);
      }
      if ( v14 >= 0 && v23.pBlobData )
      {
        v18 = UnmarshalIUnknownFromBlob(&v23, &v19);
        Instance = v18;
        if ( v18 == -2147023174 || v18 == -2147417848 || (unsigned int)(v18 + 2147023170) <= 1 )
        {
          (*(void (__fastcall **)(struct IEventSystemTier2 *, const wchar_t *))(*(_QWORD *)v7 + 96LL))(v7, L"ALL");
          Instance = 0;
          v19 = 0;
        }
        else if ( v18 < 0 )
        {
          v19 = 0;
        }
      }
LABEL_41:
      if ( v23.pBlobData )
        CoTaskMemFree(v23.pBlobData);
      if ( v19 )
      {
        if ( !*((_QWORD *)v9 + 59) )
          Instance = CoCreateInstance(
                       &CLSID_StdGlobalInterfaceTable,
                       0,
                       0x17u,
                       &IID_IGlobalInterfaceTable,
                       (LPVOID *)v9 + 59);
        if ( Instance >= 0 )
          Instance = (*(__int64 (__fastcall **)(_QWORD, struct IUnknown *, GUID *, __int64))(**((_QWORD **)v9 + 59)
                                                                                           + 24LL))(
                       *((_QWORD *)v9 + 59),
                       v19,
                       &IID_IUnknown,
                       (__int64)v9 + 480);
        v22 = Instance;
        ((void (__fastcall *)(struct IUnknown *))v19->lpVtbl->Release)(v19);
        if ( Instance < 0 )
          InternalError_HR(L"com\\complus\\src\\events\\tier1\\subscription.cpp", 0x131u, 0x11u, Instance);
      }
    }
  }
  *((_DWORD *)v9 + 166) = 0;
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180032370  mov     [rsp+arg_8], rbx
0x180032375  mov     [rsp+arg_10], r8
0x18003237a  mov     [rsp+arg_0], rcx
0x18003237f  push    rsi
0x180032380  push    r12
0x180032382  push    r13
0x180032384  push    r14
0x180032386  push    r15
0x180032388  sub     rsp, 150h
0x18003238f  mov     rbx, r9
0x180032392  mov     r12, r8
0x180032395  mov     rsi, rdx
0x180032398  mov     r15, rcx
0x18003239b  mov     ecx, 388h; cb
0x1800323a0  call    cs:__imp_CoTaskMemAlloc
0x1800323a6  test    rax, rax
0x1800323a9  jz      short loc_1800323B8
0x1800323ab  mov     rcx, rax; this
0x1800323ae  call    ??0CSubscription@@AEAA@XZ; CSubscription::CSubscription(void)
0x1800323b3  mov     r14, rax
0x1800323b6  jmp     short loc_1800323BB
0x1800323b8  xor     r14d, r14d
0x1800323bb  mov     [rsp+178h+var_D8], r14
0x1800323c3  test    r14, r14
0x1800323c6  jnz     short loc_1800323D2
0x1800323c8  mov     eax, 8007000Eh
0x1800323cd  jmp     loc_180032928
0x1800323d2  mov     rax, [r14]
0x1800323d5  mov     r8, rbx
0x1800323d8  lea     rdx, IID_IEventSubscription2
0x1800323df  mov     rcx, r14
0x1800323e2  mov     rax, [rax]
0x1800323e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800323ea  mov     ebx, eax
0x1800323ec  test    eax, eax
0x1800323ee  js      loc_18003291B
0x1800323f4  mov     [rsp+178h+pProxy], 0
0x180032400  mov     rax, [rsi]
0x180032403  lea     r8, [rsp+178h+pProxy]
0x18003240b  lea     rdx, IID_IEventSubscriptionTier2
0x180032412  mov     rcx, rsi
0x180032415  mov     rax, [rax]
0x180032418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003241d  mov     ebx, eax
0x18003241f  test    eax, eax
0x180032421  js      loc_18003291B
0x180032427  mov     [rsp+178h+dwCapabilities], 40h ; '@'; dwCapabilities
0x18003242f  mov     [rsp+178h+pAuthInfo], 0; pAuthInfo
0x180032438  mov     [rsp+178h+dwImpLevel], 3; dwImpLevel
0x180032440  mov     [rsp+178h+dwAuthnLevel], 0; dwAuthnLevel
0x180032448  xor     r9d, r9d; pServerPrincName
0x18003244b  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18003244e  mov     r8d, edx; dwAuthzSvc
0x180032451  mov     rcx, [rsp+178h+pProxy]; pProxy
0x180032459  call    cs:__imp_CoSetProxyBlanket
0x18003245f  xorps   xmm0, xmm0
0x180032462  xor     eax, eax
0x180032464  movups  xmmword ptr [rsp+178h+pvar], xmm0
0x18003246c  mov     [rsp+178h+var_C0], rax
0x180032474  xorps   xmm1, xmm1
0x180032477  movups  xmmword ptr [rsp+178h+var_A0], xmm1
0x18003247f  mov     [rsp+178h+var_90], rax
0x180032487  movups  xmmword ptr [rsp+178h+var_B8], xmm0
0x18003248f  mov     [rsp+178h+var_A8], rax
0x180032497  movups  xmmword ptr [rsp+178h+var_88], xmm1
0x18003249f  mov     [rsp+178h+var_78], rax
0x1800324a7  mov     [rsp+178h+var_120], rax
0x1800324ac  mov     qword ptr [rsp+178h+var_E8.cbSize], rax
0x1800324b4  mov     [rsp+178h+var_E8.pBlobData], rax
0x1800324bc  mov     rcx, [rsp+178h+pProxy]
0x1800324c4  mov     rax, [rcx]
0x1800324c7  lea     rdx, [rsp+178h+var_E8]
0x1800324cf  mov     qword ptr [rsp+178h+dwCapabilities], rdx
0x1800324d4  lea     rdx, [rsp+178h+var_88]
0x1800324dc  mov     [rsp+178h+pAuthInfo], rdx
0x1800324e1  lea     rdx, [rsp+178h+var_B8]
0x1800324e9  mov     qword ptr [rsp+178h+dwImpLevel], rdx
0x1800324ee  lea     rdx, [rsp+178h+var_A0]
0x1800324f6  mov     qword ptr [rsp+178h+dwAuthnLevel], rdx
0x1800324fb  lea     r9, [rsp+178h+pvar]
0x180032503  lea     r8, [r14+28h]
0x180032507  mov     rdx, r15
0x18003250a  mov     rax, [rax+20h]
0x18003250e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032513  mov     ebx, eax
0x180032515  mov     [rsp+178h+var_128], eax
0x180032519  mov     rcx, [rsp+178h+pProxy]
0x180032521  mov     rax, [rcx]
0x180032524  mov     rax, [rax+10h]
0x180032528  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003252d  test    ebx, ebx
0x18003252f  js      loc_1800327E0
0x180032535  movups  xmm0, xmmword ptr [r14+1C0h]
0x18003253d  movaps  xmmword ptr [rsp+178h+pvarg], xmm0
0x180032542  movsd   xmm1, qword ptr [r14+1D0h]
0x18003254b  movsd   qword ptr [rsp+178h+pvarg+10h], xmm1
0x180032551  movups  xmm0, xmmword ptr [r14+1A8h]
0x180032559  movaps  xmmword ptr [rsp+178h+var_68], xmm0
0x180032561  movsd   xmm1, qword ptr [r14+1B8h]
0x18003256a  movsd   qword ptr [rsp+178h+var_68+10h], xmm1
0x180032573  movups  xmm0, xmmword ptr [r14+28h]
0x180032578  movaps  xmmword ptr [rsp+178h+var_48], xmm0
0x180032580  movsd   xmm1, qword ptr [r14+38h]
0x180032586  movsd   qword ptr [rsp+178h+var_48+10h], xmm1
0x18003258f  lea     rax, [r14+29Ch]
0x180032596  mov     qword ptr [rsp+178h+dwAuthnLevel], rax; unsigned __int16 *
0x18003259b  lea     r8, [rsp+178h+pvarg]; struct tagPROPVARIANT *
0x1800325a0  lea     rdx, [rsp+178h+var_68]; struct tagPROPVARIANT *
0x1800325a8  lea     rcx, [rsp+178h+var_48]; struct tagPROPVARIANT *
0x1800325b0  call    ?ConcatenateECID_PARTID_APPID@@YAJUtagPROPVARIANT@@00KPEAG@Z; ConcatenateECID_PARTID_APPID(tagPROPVARIANT,tagPROPVARIANT,tagPROPVARIANT,ulong,ushort *)
0x1800325b5  mov     ebx, eax
0x1800325b7  mov     [rsp+178h+var_128], eax
0x1800325bb  mov     r13d, 101Fh
0x1800325c1  lea     r15d, [r13-13h]
0x1800325c5  test    eax, eax
0x1800325c7  js      loc_180032772
0x1800325cd  cmp     word ptr [rsp+178h+pvar], r13w
0x1800325d6  jnz     loc_180032772
0x1800325dc  cmp     word ptr [rsp+178h+var_A0], r15w
0x1800325e5  jz      short loc_180032605
0x1800325e7  mov     r8d, 10h; unsigned __int16
0x1800325ed  lea     r9, aPubpropsVtVtVe; "pubProps.vt == (VT_VECTOR | VT_VARIANT)"
0x1800325f4  mov     edx, 0B8h; unsigned int
0x1800325f9  lea     rcx, aComComplusSrcE_15; "com\\complus\\src\\events\\tier1\\subsc"...
0x180032600  call    ?InternalAssert@@YA_NPEBGKG0@Z; InternalAssert(ushort const *,ulong,ushort,ushort const *)
0x180032605  xor     r12d, r12d
0x180032608  mov     esi, ebx
0x18003260a  cmp     r12d, dword ptr [rsp+178h+pvar+8]
0x180032612  jnb     loc_18003269E
0x180032618  mov     rax, [rsp+178h+var_C0]
0x180032620  mov     rsi, [rax+r12*8]
0x180032624  xorps   xmm0, xmm0
0x180032627  xor     eax, eax
0x180032629  movups  xmmword ptr [rsp+178h+pvarg], xmm0
0x18003262e  mov     qword ptr [rsp+178h+pvarg+10h], rax
0x180032633  lea     rcx, [rsp+178h+pvarg]; pvarg
0x180032638  call    cs:__imp_VariantInit
0x18003263e  lea     rcx, [r12+r12*2]
0x180032642  mov     rax, [rsp+178h+var_90]
0x18003264a  lea     rcx, [rax+rcx*8]; pPropVar
0x18003264e  lea     rdx, [rsp+178h+pvarg]; pVar
0x180032653  call    cs:__imp_PropVariantToVariant
0x180032659  mov     ebx, eax
0x18003265b  mov     [rsp+178h+var_128], eax
0x18003265f  test    eax, eax
0x180032661  js      short loc_180032691
0x180032663  lea     rcx, [r14+1E8h]
0x18003266a  mov     rax, [rcx]
0x18003266d  mov     r8, rsi
0x180032670  lea     rdx, [rsp+178h+pvarg]
0x180032675  mov     rax, [rax+58h]
0x180032679  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003267e  lea     rcx, [rsp+178h+pvarg]; pvarg
0x180032683  call    cs:__imp_VariantClear
0x180032689  inc     r12d
0x18003268c  jmp     loc_180032608
0x180032691  lea     rcx, [rsp+178h+pvarg]; pvarg
0x180032696  call    cs:__imp_VariantClear
0x18003269c  mov     esi, ebx
0x18003269e  mov     r12, [rsp+178h+arg_10]
0x1800326a6  test    esi, esi
0x1800326a8  js      loc_180032786
0x1800326ae  cmp     word ptr [rsp+178h+var_B8], r13w
0x1800326b7  jnz     loc_180032786
0x1800326bd  cmp     word ptr [rsp+178h+var_88], r15w
0x1800326c6  jz      short loc_1800326E6
0x1800326c8  mov     r8d, 10h; unsigned __int16
0x1800326ce  lea     r9, aSubpropsVtVtVe; "subProps.vt == (VT_VECTOR | VT_VARIANT)"
0x1800326d5  mov     edx, 0CDh; unsigned int
0x1800326da  lea     rcx, aComComplusSrcE_15; "com\\complus\\src\\events\\tier1\\subsc"...
0x1800326e1  call    ?InternalAssert@@YA_NPEBGKG0@Z; InternalAssert(ushort const *,ulong,ushort,ushort const *)
0x1800326e6  xor     r15d, r15d
0x1800326e9  cmp     r15d, dword ptr [rsp+178h+var_B8+8]
0x1800326f1  jnb     loc_180032786
0x1800326f7  mov     rax, [rsp+178h+var_A8]
0x1800326ff  mov     rsi, [rax+r15*8]
0x180032703  xorps   xmm0, xmm0
0x180032706  xor     eax, eax
0x180032708  movups  xmmword ptr [rsp+178h+pvarg], xmm0
0x18003270d  mov     qword ptr [rsp+178h+pvarg+10h], rax
0x180032712  lea     rcx, [rsp+178h+pvarg]; pvarg
0x180032717  call    cs:__imp_VariantInit
0x18003271d  lea     rcx, [r15+r15*2]
0x180032721  mov     rax, [rsp+178h+var_78]
0x180032729  lea     rcx, [rax+rcx*8]; pPropVar
0x18003272d  lea     rdx, [rsp+178h+pvarg]; pVar
0x180032732  call    cs:__imp_PropVariantToVariant
0x180032738  mov     ebx, eax
0x18003273a  mov     [rsp+178h+var_128], eax
0x18003273e  test    eax, eax
0x180032740  js      short loc_180032779
0x180032742  lea     rcx, [r14+240h]
0x180032749  mov     rax, [rcx]
0x18003274c  mov     r8, rsi
0x18003274f  lea     rdx, [rsp+178h+pvarg]
0x180032754  mov     rax, [rax+58h]
0x180032758  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003275d  lea     rcx, [rsp+178h+pvarg]; pvarg
0x180032762  call    cs:__imp_VariantClear
0x180032768  inc     r15d
0x18003276b  mov     esi, ebx
0x18003276d  jmp     loc_1800326E9
0x180032772  mov     esi, ebx
0x180032774  jmp     loc_1800326A6
0x180032779  lea     rcx, [rsp+178h+pvarg]; pvarg
0x18003277e  call    cs:__imp_VariantClear
0x180032784  mov     esi, ebx
0x180032786  lea     rcx, [rsp+178h+pvar]; pvar
0x18003278e  call    cs:__imp_PropVariantClear
0x180032794  lea     rcx, [rsp+178h+var_A0]; pvar
0x18003279c  call    cs:__imp_PropVariantClear
0x1800327a2  lea     rcx, [rsp+178h+var_B8]; pvar
0x1800327aa  call    cs:__imp_PropVariantClear
0x1800327b0  lea     rcx, [rsp+178h+var_88]; pvar
0x1800327b8  call    cs:__imp_PropVariantClear
0x1800327be  mov     r15, [rsp+178h+arg_0]
0x1800327c6  test    esi, esi
0x1800327c8  js      loc_180032851
0x1800327ce  test    r12, r12
0x1800327d1  jz      short loc_1800327E2
0x1800327d3  lea     rax, [r14+29Ch]
0x1800327da  mov     [r12], rax
0x1800327de  jmp     short loc_1800327E2
0x1800327e0  mov     esi, ebx
0x1800327e2  test    esi, esi
0x1800327e4  js      short loc_180032851
0x1800327e6  cmp     [rsp+178h+var_E8.pBlobData], 0
0x1800327ef  jz      short loc_180032851
0x1800327f1  lea     rdx, [rsp+178h+var_120]; struct IUnknown **
0x1800327f6  lea     rcx, [rsp+178h+var_E8]; struct tagBLOB *
0x1800327fe  call    ?UnmarshalIUnknownFromBlob@@YAJAEBUtagBLOB@@AEAPEAUIUnknown@@@Z; UnmarshalIUnknownFromBlob(tagBLOB const &,IUnknown * &)
0x180032803  mov     ebx, eax
0x180032805  mov     [rsp+178h+var_128], eax
0x180032809  cmp     eax, 800706BAh
0x18003280e  jz      short loc_180032830
0x180032810  cmp     eax, 80010108h
0x180032815  jz      short loc_180032830
0x180032817  add     eax, 7FF8F942h
0x18003281c  cmp     eax, 1
0x18003281f  jbe     short loc_180032830
0x180032821  test    ebx, ebx
0x180032823  jns     short loc_180032851
0x180032825  mov     [rsp+178h+var_120], 0
0x18003282e  jmp     short loc_180032851
0x180032830  mov     rax, [r15]
0x180032833  lea     rdx, aAll; "ALL"
0x18003283a  mov     rcx, r15
0x18003283d  mov     rax, [rax+60h]
0x180032841  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032846  xor     ebx, ebx
0x180032848  mov     [rsp+178h+var_128], ebx
0x18003284c  mov     [rsp+178h+var_120], rbx
0x180032851  mov     rcx, [rsp+178h+var_E8.pBlobData]; pv
0x180032859  test    rcx, rcx
0x18003285c  jz      short loc_180032864
0x18003285e  call    cs:__imp_CoTaskMemFree
0x180032864  cmp     [rsp+178h+var_120], 0
0x18003286a  jz      loc_18003291B
0x180032870  lea     rsi, [r14+1D8h]
0x180032877  cmp     qword ptr [rsi], 0
0x18003287b  jnz     short loc_1800328A2
0x18003287d  mov     qword ptr [rsp+178h+dwAuthnLevel], rsi; ppv
0x180032882  lea     r9, IID_IGlobalInterfaceTable; riid
0x180032889  xor     edx, edx; pUnkOuter
0x18003288b  lea     r8d, [rdx+17h]; dwClsContext
0x18003288f  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180032896  call    cs:__imp_CoCreateInstance
0x18003289c  mov     ebx, eax
0x18003289e  mov     [rsp+178h+var_128], eax
0x1800328a2  test    ebx, ebx
0x1800328a4  js      short loc_1800328CE
0x1800328a6  mov     rcx, [rsi]
0x1800328a9  mov     rax, [rcx]
0x1800328ac  lea     r9, [r14+1E0h]
0x1800328b3  lea     r8, IID_IUnknown
0x1800328ba  mov     rdx, [rsp+178h+var_120]
0x1800328bf  mov     rax, [rax+18h]
0x1800328c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800328c8  mov     ebx, eax
0x1800328ca  mov     [rsp+178h+var_128], eax
0x1800328ce  mov     esi, ebx
0x1800328d0  mov     [rsp+178h+var_F0], ebx
0x1800328d7  mov     rcx, [rsp+178h+var_120]
0x1800328dc  mov     rax, [rcx]
0x1800328df  mov     rax, [rax+10h]
0x1800328e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800328e8  jmp     short loc_1800328FD
0x1800328ea  mov     r14, [rsp+178h+var_D8]
0x1800328f2  mov     ebx, [rsp+178h+var_128]
0x1800328f6  mov     esi, [rsp+178h+var_F0]
0x1800328fd  test    esi, esi
0x1800328ff  jns     short loc_18003291B
0x180032901  mov     r8d, 11h; unsigned __int16
0x180032907  mov     r9d, esi; int
0x18003290a  mov     edx, 131h; unsigned int
0x18003290f  lea     rcx, aComComplusSrcE_15; "com\\complus\\src\\events\\tier1\\subsc"...
0x180032916  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x18003291b  mov     dword ptr [r14+298h], 0
0x180032926  mov     eax, ebx
0x180032928  mov     rbx, [rsp+178h+arg_8]
  ... truncated ...
```
