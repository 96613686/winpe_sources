# AppHostQueryProcessor::Query(IAppHostAdminManager *,ushort *,IAppHostNodeIterator * *)

- ea: `0x180008190`
- end: `0x180008421`
- name: `?Query@AppHostQueryProcessor@@UEAAJPEAUIAppHostAdminManager@@PEAGPEAPEAUIAppHostNodeIterator@@@Z`
- size: `657`
- prototype: `__int64 __fastcall(LPVOID *this, struct IAppHostAdminManager *, unsigned __int16 *, struct IAppHostNodeIterator **)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180001194`
- `0x1800021a4`
- `0x180002310`
- `0x180003a1c`
- `0x180004c04`
- `0x180007680`
- `0x180007f94`
- `0x180008190`
- `0x18000dac8`
- `0x180014010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800081e7`
- `ole32!CoCreateInstance` at `0x1800081e7`

## pseudocode

```c
__int64 __fastcall AppHostQueryProcessor::Query(
        LPVOID *this,
        struct IAppHostAdminManager *a2,
        unsigned __int16 *a3,
        struct IAppHostNodeIterator **a4)
{
  __int64 *v9; // rdi
  HRESULT Instance; // ebx
  __int64 v11; // rbx
  int ConfigNameTablePair; // edi
  struct AppHostConfigPathNavigator *v13; // rax
  struct AppHostConfigPathNavigator *v14; // rsi
  _DWORD *v15; // rbx
  __int64 v16; // rdi
  struct AppHostConfigPathNavigator *v17; // [rsp+30h] [rbp-38h] BYREF
  struct AppHostConfigPathNavigator *v18; // [rsp+38h] [rbp-30h] BYREF
  __int64 v19; // [rsp+40h] [rbp-28h] BYREF
  __int64 v20; // [rsp+48h] [rbp-20h] BYREF
  _DWORD *v21; // [rsp+50h] [rbp-18h]
  struct ConfigNameTablePair *v22; // [rsp+B8h] [rbp+50h] BYREF

  if ( !a2 )
    return 2147942487LL;
  v20 = 0;
  v9 = (__int64 *)(this + 3);
  if ( this[3]
    || (Instance = CoCreateInstance(
                     &CLSID_XPathQueryStringCompiler,
                     0,
                     1u,
                     &GUID_5fd1dce3_10f9_4d4e_b18a_90851d05690c,
                     this + 3),
        Instance >= 0) )
  {
    v11 = *v9;
    v20 = v11;
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
    v22 = 0;
    ConfigNameTablePair = AppHostQueryProcessor::GetConfigNameTablePair((AppHostQueryProcessor *)this, &v22);
    if ( ConfigNameTablePair < 0 )
      goto LABEL_8;
    v17 = 0;
    v13 = (struct AppHostConfigPathNavigator *)operator new(0x38u);
    v14 = v13;
    v18 = v13;
    if ( v13 )
    {
      *(_QWORD *)v13 = &InvasivePtrObject::`vftable';
      *((_DWORD *)v13 + 2) = 1;
      *(_QWORD *)v13 = &ConfigSystemContext::`vftable';
      *((_QWORD *)v13 + 2) = a2;
      ((void (__fastcall *)(struct IAppHostAdminManager *))a2->lpVtbl->AddRef)(a2);
      v21 = (_DWORD *)((char *)v14 + 24);
      StringTable::StringTable((struct AppHostConfigPathNavigator *)((char *)v14 + 24));
      AvailableSectionsTable::Initialize((struct AppHostConfigPathNavigator *)((char *)v14 + 24), a2);
    }
    else
    {
      v14 = 0;
    }
    InvasivePtr<ConfigLocationsTree>::Reset(&v17);
    v17 = v14;
    if ( v14 )
    {
      v18 = 0;
      ConfigNameTablePair = AppHostConfigPathNavigator::CreateInstance(v22, v14, &v18);
      if ( ConfigNameTablePair < 0 )
      {
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v18);
        InvasivePtr<ConfigLocationsTree>::Reset(&v17);
LABEL_8:
        InvasivePtr<ConfigLocationsTree>::Reset(&v22);
        Instance = ConfigNameTablePair;
        goto LABEL_25;
      }
      v19 = 0;
      Instance = (*(__int64 (__fastcall **)(__int64, unsigned __int64, unsigned __int16 *, struct AppHostConfigPathNavigator *, __int64 *))(*(_QWORD *)v11 + 32LL))(
                   v11,
                   (unsigned __int64)(this + 1) & -(__int64)(this != 0),
                   a3,
                   v18,
                   &v19);
      if ( Instance < 0 )
      {
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v18);
        InvasivePtr<ConfigLocationsTree>::Reset(&v17);
        InvasivePtr<ConfigLocationsTree>::Reset(&v22);
        goto LABEL_25;
      }
      v15 = operator new(0x18u);
      v21 = v15;
      if ( v15 )
      {
        v16 = v19;
        ModuleRefCounter::AddRef();
        *(_QWORD *)v15 = &AppHostNodeIterator::`vftable';
        v15[2] = 1;
        *((_QWORD *)v15 + 2) = v16;
        if ( v16 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
        *a4 = (struct IAppHostNodeIterator *)v15;
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v18);
        InvasivePtr<ConfigLocationsTree>::Reset(&v17);
        InvasivePtr<ConfigLocationsTree>::Reset(&v22);
        Instance = 0;
        goto LABEL_25;
      }
      *a4 = 0;
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v18);
    }
    InvasivePtr<ConfigLocationsTree>::Reset(&v17);
    InvasivePtr<ConfigLocationsTree>::Reset(&v22);
    Instance = -2147024882;
  }
LABEL_25:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v20);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180008190  push    rbp
0x180008192  push    rbx
0x180008193  push    rsi
0x180008194  push    rdi
0x180008195  push    r12
0x180008197  push    r13
0x180008199  push    r14
0x18000819b  push    r15
0x18000819d  mov     rbp, rsp
0x1800081a0  sub     rsp, 68h
0x1800081a4  mov     r15, r9
0x1800081a7  mov     r13, r8
0x1800081aa  mov     r12, rdx
0x1800081ad  mov     r14, rcx
0x1800081b0  xor     esi, esi
0x1800081b2  test    rdx, rdx
0x1800081b5  jnz     short loc_1800081C1
0x1800081b7  mov     eax, 80070057h
0x1800081bc  jmp     loc_180008410
0x1800081c1  mov     [rbp+var_20], rsi
0x1800081c5  lea     rdi, [rcx+18h]
0x1800081c9  cmp     [rdi], rsi
0x1800081cc  jnz     short loc_1800081F7
0x1800081ce  mov     [rsp+68h+ppv], rdi; ppv
0x1800081d3  lea     r9, _GUID_5fd1dce3_10f9_4d4e_b18a_90851d05690c; riid
0x1800081da  xor     edx, edx; pUnkOuter
0x1800081dc  lea     r8d, [rdx+1]; dwClsContext
0x1800081e0  lea     rcx, CLSID_XPathQueryStringCompiler; rclsid
0x1800081e7  call    cs:__imp_CoCreateInstance
0x1800081ed  mov     ebx, eax
0x1800081ef  test    eax, eax
0x1800081f1  js      loc_180008405
0x1800081f7  mov     rbx, [rdi]
0x1800081fa  mov     [rbp+var_20], rbx
0x1800081fe  test    rbx, rbx
0x180008201  jz      short loc_180008213
0x180008203  mov     rax, [rbx]
0x180008206  mov     rcx, rbx
0x180008209  mov     rax, [rax+8]
0x18000820d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008212  nop
0x180008213  mov     [rbp+arg_8], rsi
0x180008217  lea     rdx, [rbp+arg_8]; struct ConfigNameTablePair **
0x18000821b  mov     rcx, r14; this
0x18000821e  call    ?GetConfigNameTablePair@AppHostQueryProcessor@@AEAAJPEAPEAVConfigNameTablePair@@@Z; AppHostQueryProcessor::GetConfigNameTablePair(ConfigNameTablePair * *)
0x180008223  mov     edi, eax
0x180008225  test    eax, eax
0x180008227  jns     short loc_180008239
0x180008229  lea     rcx, [rbp+arg_8]
0x18000822d  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x180008232  mov     ebx, edi
0x180008234  jmp     loc_180008405
0x180008239  mov     [rbp+var_38], rsi
0x18000823d  mov     ecx, 38h ; '8'; Size
0x180008242  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008247  mov     rsi, rax
0x18000824a  mov     [rbp+var_30], rax
0x18000824e  test    rax, rax
0x180008251  jz      short loc_1800082A2
0x180008253  lea     rax, ??_7InvasivePtrObject@@6B@; const InvasivePtrObject::`vftable'
0x18000825a  mov     [rsi], rax
0x18000825d  mov     dword ptr [rsi+8], 1
0x180008264  lea     rax, ??_7ConfigSystemContext@@6B@; const ConfigSystemContext::`vftable'
0x18000826b  mov     [rsi], rax
0x18000826e  mov     [rsi+10h], r12
0x180008272  mov     rax, [r12]
0x180008276  mov     rcx, r12
0x180008279  mov     rax, [rax+8]
0x18000827d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008282  nop
0x180008283  lea     rdi, [rsi+18h]
0x180008287  mov     [rbp+var_18], rdi
0x18000828b  mov     rcx, rdi; this
0x18000828e  call    ??0StringTable@@QEAA@XZ; StringTable::StringTable(void)
0x180008293  nop
0x180008294  mov     rdx, r12; struct IAppHostAdminManager *
0x180008297  mov     rcx, rdi; this
0x18000829a  call    ?Initialize@AvailableSectionsTable@@AEAAXPEAUIAppHostAdminManager@@@Z; AvailableSectionsTable::Initialize(IAppHostAdminManager *)
0x18000829f  nop
0x1800082a0  jmp     short loc_1800082A4
0x1800082a2  xor     esi, esi
0x1800082a4  lea     rcx, [rbp+var_38]
0x1800082a8  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x1800082ad  mov     [rbp+var_38], rsi
0x1800082b1  test    rsi, rsi
0x1800082b4  jz      loc_1800083ED
0x1800082ba  mov     [rbp+var_30], 0
0x1800082c2  lea     r8, [rbp+var_30]; struct AppHostConfigPathNavigator **
0x1800082c6  mov     rdx, rsi; struct ConfigSystemContext *
0x1800082c9  mov     rcx, [rbp+arg_8]; struct ConfigNameTablePair *
0x1800082cd  call    ?CreateInstance@AppHostConfigPathNavigator@@SAJPEAVConfigNameTablePair@@PEAVConfigSystemContext@@PEAPEAV1@@Z; AppHostConfigPathNavigator::CreateInstance(ConfigNameTablePair *,ConfigSystemContext *,AppHostConfigPathNavigator * *)
0x1800082d2  mov     edi, eax
0x1800082d4  test    eax, eax
0x1800082d6  jns     short loc_1800082F0
0x1800082d8  lea     rcx, [rbp+var_30]
0x1800082dc  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800082e1  nop
0x1800082e2  lea     rcx, [rbp+var_38]
0x1800082e6  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x1800082eb  jmp     loc_180008229
0x1800082f0  mov     [rbp+var_28], 0
0x1800082f8  mov     rcx, [rbx]
0x1800082fb  lea     rax, [r14+8]
0x1800082ff  neg     r14
0x180008302  sbb     rdx, rdx
0x180008305  and     rdx, rax
0x180008308  mov     rax, [rcx+20h]
0x18000830c  lea     rcx, [rbp+var_28]
0x180008310  mov     [rsp+68h+ppv], rcx
0x180008315  mov     r9, [rbp+var_30]
0x180008319  mov     r8, r13
0x18000831c  mov     rcx, rbx
0x18000831f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008324  mov     ebx, eax
0x180008326  test    eax, eax
0x180008328  jns     short loc_180008356
0x18000832a  lea     rcx, [rbp+var_28]
0x18000832e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180008333  nop
0x180008334  lea     rcx, [rbp+var_30]
0x180008338  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000833d  nop
0x18000833e  lea     rcx, [rbp+var_38]
0x180008342  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x180008347  nop
0x180008348  lea     rcx, [rbp+arg_8]
0x18000834c  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x180008351  jmp     loc_180008405
0x180008356  mov     ecx, 18h; Size
0x18000835b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008360  mov     rbx, rax
0x180008363  mov     [rbp+var_18], rax
0x180008367  test    rax, rax
0x18000836a  jz      short loc_1800083D2
0x18000836c  mov     rdi, [rbp+var_28]
0x180008370  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x180008375  lea     rax, ??_7AppHostNodeIterator@@6B@; const AppHostNodeIterator::`vftable'
0x18000837c  mov     [rbx], rax
0x18000837f  mov     dword ptr [rbx+8], 1
0x180008386  mov     [rbx+10h], rdi
0x18000838a  test    rdi, rdi
0x18000838d  jz      short loc_18000839F
0x18000838f  mov     rax, [rdi]
0x180008392  mov     rcx, rdi
0x180008395  mov     rax, [rax+8]
0x180008399  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000839e  nop
0x18000839f  mov     [r15], rbx
0x1800083a2  test    rbx, rbx
0x1800083a5  jz      short loc_1800083D9
0x1800083a7  lea     rcx, [rbp+var_28]
0x1800083ab  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800083b0  nop
0x1800083b1  lea     rcx, [rbp+var_30]
0x1800083b5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800083ba  nop
0x1800083bb  lea     rcx, [rbp+var_38]
0x1800083bf  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x1800083c4  nop
0x1800083c5  lea     rcx, [rbp+arg_8]
0x1800083c9  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x1800083ce  xor     ebx, ebx
0x1800083d0  jmp     short loc_180008405
0x1800083d2  mov     qword ptr [r15], 0
0x1800083d9  lea     rcx, [rbp+var_28]
0x1800083dd  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800083e2  nop
0x1800083e3  lea     rcx, [rbp+var_30]
0x1800083e7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800083ec  nop
0x1800083ed  lea     rcx, [rbp+var_38]
0x1800083f1  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x1800083f6  nop
0x1800083f7  lea     rcx, [rbp+arg_8]
0x1800083fb  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x180008400  mov     ebx, 8007000Eh
0x180008405  lea     rcx, [rbp+var_20]
0x180008409  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000840e  mov     eax, ebx
0x180008410  add     rsp, 68h
0x180008414  pop     r15
0x180008416  pop     r14
0x180008418  pop     r13
0x18000841a  pop     r12
0x18000841c  pop     rdi
0x18000841d  pop     rsi
0x18000841e  pop     rbx
0x18000841f  pop     rbp
0x180008420  retn
```
