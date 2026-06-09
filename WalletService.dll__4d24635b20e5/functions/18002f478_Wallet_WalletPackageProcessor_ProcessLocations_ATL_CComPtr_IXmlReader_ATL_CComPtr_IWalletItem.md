# Wallet::WalletPackageProcessor::ProcessLocations(ATL::CComPtr<IXmlReader>,ATL::CComPtr<IWalletItem> &)

- ea: `0x18002f478`
- end: `0x18002f865`
- name: `?ProcessLocations@WalletPackageProcessor@Wallet@@AEAAJV?$CComPtr@UIXmlReader@@@ATL@@AEAV?$CComPtr@UIWalletItem@@@4@@Z`
- size: `1005`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800306b0`

## callees

- `0x180003ae4`
- `0x180003b40`
- `0x1800043b8`
- `0x180014328`
- `0x18001e754`
- `0x18002d048`
- `0x18002e4d4`
- `0x18002f478`
- `0x18003912c`
- `0x180045010`

## import_xrefs

- `msvcrt!_wtof` at `0x18002f687`
- `msvcrt!_wtof` at `0x18002f6f7`
- `msvcrt!_wtof` at `0x18002f75e`
- `msvcrt!_wtof` at `0x18002f687`
- `msvcrt!_wtof` at `0x18002f6f7`
- `msvcrt!_wtof` at `0x18002f75e`
- `msvcrt!_wcsicmp` at `0x18002f54c`
- `msvcrt!_wcsicmp` at `0x18002f5bc`
- `msvcrt!_wcsicmp` at `0x18002f62d`
- `msvcrt!_wcsicmp` at `0x18002f66f`
- `msvcrt!_wcsicmp` at `0x18002f6df`
- `msvcrt!_wcsicmp` at `0x18002f74c`
- `msvcrt!_wcsicmp` at `0x18002f7e4`
- `msvcrt!_wcsicmp` at `0x18002f54c`
- `msvcrt!_wcsicmp` at `0x18002f5bc`
- `msvcrt!_wcsicmp` at `0x18002f62d`
- `msvcrt!_wcsicmp` at `0x18002f66f`
- `msvcrt!_wcsicmp` at `0x18002f6df`
- `msvcrt!_wcsicmp` at `0x18002f74c`
- `msvcrt!_wcsicmp` at `0x18002f7e4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002f7aa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002f7aa`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Wallet::WalletPackageProcessor::ProcessLocations(__int64 *a1, __int64 *a2, _QWORD *a3)
{
  int WalletLocationManager; // esi
  BOOL v6; // r12d
  BOOL v7; // r15d
  int v8; // eax
  __int64 v9; // r8
  _QWORD *v10; // rcx
  wchar_t *v11; // rbx
  bool v12; // sf
  double v13; // xmm0_8
  int v14; // ebx
  int v15; // eax
  double v16; // xmm0_8
  int v17; // eax
  double v18; // xmm0_8
  int v19; // eax
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, _QWORD, __int64 *); // rbx
  __int64 *v22; // rax
  wchar_t *String2; // [rsp+20h] [rbp-50h] BYREF
  struct IUnknown *v25; // [rsp+28h] [rbp-48h] BYREF
  wchar_t *String; // [rsp+30h] [rbp-40h] BYREF
  __int64 v27; // [rsp+38h] [rbp-38h] BYREF
  PROPVARIANT v28[2]; // [rsp+40h] [rbp-30h] BYREF
  PROPVARIANT pvar[2]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v30; // [rsp+60h] [rbp-10h]
  int v32; // [rsp+C8h] [rbp+58h] BYREF

  v32 = 0;
  String2 = 0;
  String = 0;
  v25 = 0;
  v27 = 0;
  WalletLocationManager = Wallet::Utils::GetWalletLocationManager(&v27);
  if ( WalletLocationManager >= 0 )
  {
    WalletLocationManager = 0;
LABEL_3:
    v6 = 0;
    v7 = 0;
    while ( 1 )
    {
      while ( 1 )
      {
        do
        {
          while ( 1 )
          {
            while ( 1 )
            {
              if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)*a2 + 200LL))(*a2) )
                goto LABEL_50;
              v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)*a2 + 48LL))(*a2, &v32);
              if ( v8 < 0 )
                goto LABEL_49;
              if ( v32 != 1 )
                break;
              v8 = (*(__int64 (__fastcall **)(__int64, wchar_t **, _QWORD))(*(_QWORD *)*a2 + 112LL))(*a2, &String2, 0);
              if ( v8 >= 0 )
              {
                if ( _wcsicmp(L"Location", String2) )
                  continue;
                v20 = v27;
                v21 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v27 + 32LL);
                v22 = ce::pointerTo<IWalletNotification>((__int64 *)&v25);
                v8 = v21(v20, *a3, v22);
                if ( v8 >= 0 )
                  continue;
              }
              goto LABEL_49;
            }
            if ( v32 == 3 )
              break;
            if ( v32 == 15 )
            {
              v8 = (*(__int64 (__fastcall **)(__int64, wchar_t **, _QWORD))(*(_QWORD *)*a2 + 112LL))(*a2, &String2, 0);
              if ( v8 < 0 )
                goto LABEL_49;
              if ( !_wcsicmp(L"Location", String2) )
              {
                if ( !v7 || !v6 )
                {
LABEL_45:
                  WalletLocationManager = -2143682476;
                  goto LABEL_50;
                }
                v10 = (_QWORD *)a1[10];
                if ( v10 == (_QWORD *)a1[11] )
                {
                  if ( !utl::vector<ATL::CComPtr<IWalletItemListener>,utl::allocator<ATL::CComPtr<IWalletItemListener>>>::_PushBackOne2<ATL::CComPtr<IWalletItemListener>>(
                          a1 + 9,
                          &v25,
                          v9) )
                  {
                    WalletLocationManager = -2147024882;
                    goto LABEL_50;
                  }
                }
                else
                {
                  ATL::CComPtrBase<IWalletBackgroundAgentListener>::CComPtrBase<IWalletBackgroundAgentListener>(
                    v10,
                    (__int64)v25);
                  a1[10] += 8;
                }
                if ( v25 )
                  ATL::AtlComPtrAssign(&v25, 0);
                goto LABEL_3;
              }
              if ( !_wcsicmp(L"RelevantLocations", String2) )
                goto LABEL_50;
            }
          }
        }
        while ( !String2 );
        if ( !v25 )
          goto LABEL_45;
        v8 = (*(__int64 (__fastcall **)(__int64, wchar_t **, _QWORD))(*(_QWORD *)*a2 + 128LL))(*a2, &String, 0);
        if ( v8 < 0
          || (v8 = (*(__int64 (__fastcall **)(__int64, wchar_t **, _QWORD))(*(_QWORD *)*a2 + 112LL))(*a2, &String2, 0),
              v8 < 0) )
        {
LABEL_49:
          WalletLocationManager = v8;
          goto LABEL_50;
        }
        if ( _wcsicmp(L"DisplayMessage", String2) )
          break;
        v11 = String;
        ATL::CComPtrBase<IWalletBackgroundAgentListener>::CComPtrBase<IWalletBackgroundAgentListener>(v28, (__int64)v25);
        v12 = (int)Wallet::WalletPackageProcessor::HandleStringProperty(a1, v28, 40005, v11) < 0;
LABEL_44:
        if ( v12 )
          goto LABEL_45;
      }
      if ( !_wcsicmp(L"Latitude", String2) )
        break;
      if ( !_wcsicmp(L"Longitude", String2) )
      {
        v6 = String != 0;
        v16 = _wtof(String);
        *(_OWORD *)pvar = 0;
        v30 = 0;
        if ( v25 )
        {
          LOWORD(pvar[0]) = 5;
          pvar[1] = *(PROPVARIANT *)&v16;
          v17 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, PROPVARIANT *))v25->lpVtbl[2].AddRef)(
                  v25,
                  40002,
                  pvar);
          v14 = 0;
          if ( v17 < 0 )
            v14 = v17;
        }
        else
        {
          v14 = -2147467261;
        }
        goto LABEL_43;
      }
      if ( !_wcsicmp(L"Altitude", String2) )
      {
        v18 = _wtof(String);
        *(_OWORD *)pvar = 0;
        v30 = 0;
        if ( v25 )
        {
          LOWORD(pvar[0]) = 5;
          pvar[1] = *(PROPVARIANT *)&v18;
          v19 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, PROPVARIANT *))v25->lpVtbl[2].AddRef)(
                  v25,
                  40003,
                  pvar);
          v14 = 0;
          if ( v19 < 0 )
            v14 = v19;
        }
        else
        {
          v14 = -2147467261;
        }
        goto LABEL_43;
      }
    }
    v7 = String != 0;
    v13 = _wtof(String);
    *(_OWORD *)pvar = 0;
    v30 = 0;
    if ( v25 )
    {
      LOWORD(pvar[0]) = 5;
      pvar[1] = *(PROPVARIANT *)&v13;
      v15 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, PROPVARIANT *))v25->lpVtbl[2].AddRef)(v25, 40001, pvar);
      v14 = 0;
      if ( v15 < 0 )
        v14 = v15;
    }
    else
    {
      v14 = -2147467261;
    }
LABEL_43:
    PropVariantClear(pvar);
    v12 = v14 < 0;
    goto LABEL_44;
  }
LABEL_50:
  ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(&v27);
  ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>((__int64 *)&v25);
  ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(a2);
  return (unsigned int)WalletLocationManager;
}

```

## disassembly

```asm
0x18002f478  mov     [rsp-38h+arg_0], rbx
0x18002f47d  mov     [rsp-38h+arg_10], r8
0x18002f482  mov     [rsp-38h+arg_8], rdx
0x18002f487  push    rbp
0x18002f488  push    rsi
0x18002f489  push    rdi
0x18002f48a  push    r12
0x18002f48c  push    r13
0x18002f48e  push    r14
0x18002f490  push    r15
0x18002f492  mov     rbp, rsp
0x18002f495  sub     rsp, 70h
0x18002f499  mov     r14, rdx
0x18002f49c  mov     r13, rcx
0x18002f49f  xor     edi, edi
0x18002f4a1  mov     [rbp+arg_18], edi
0x18002f4a4  mov     [rbp+String2], rdi
0x18002f4a8  mov     [rbp+String], rdi
0x18002f4ac  mov     [rbp+var_48], rdi
0x18002f4b0  mov     [rbp+var_38], rdi
0x18002f4b4  lea     rcx, [rbp+var_38]
0x18002f4b8  call    ?GetWalletLocationManager@Utils@Wallet@@YAJAEAV?$CComPtr@UIWalletLocationManager@@@ATL@@@Z; Wallet::Utils::GetWalletLocationManager(ATL::CComPtr<IWalletLocationManager> &)
0x18002f4bd  mov     esi, eax
0x18002f4bf  test    eax, eax
0x18002f4c1  js      loc_18002F827
0x18002f4c7  mov     esi, edi
0x18002f4c9  mov     r12d, edi
0x18002f4cc  mov     r15d, edi
0x18002f4cf  mov     ebx, 5
0x18002f4d4  mov     rcx, [r14]
0x18002f4d7  mov     rax, [rcx]
0x18002f4da  mov     rax, [rax+0C8h]
0x18002f4e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f4e6  test    eax, eax
0x18002f4e8  jnz     loc_18002F827
0x18002f4ee  mov     rcx, [r14]
0x18002f4f1  mov     rax, [rcx]
0x18002f4f4  lea     rdx, [rbp+arg_18]
0x18002f4f8  mov     rax, [rax+30h]
0x18002f4fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f501  test    eax, eax
0x18002f503  js      loc_18002F825
0x18002f509  mov     ecx, [rbp+arg_18]
0x18002f50c  sub     ecx, 1
0x18002f50f  jz      loc_18002F7BF
0x18002f515  sub     ecx, 2
0x18002f518  jz      loc_18002F5CF
0x18002f51e  cmp     ecx, 0Ch
0x18002f521  jnz     short loc_18002F4D4
0x18002f523  mov     rcx, [r14]
0x18002f526  mov     rax, [rcx]
0x18002f529  xor     r8d, r8d
0x18002f52c  lea     rdx, [rbp+String2]
0x18002f530  mov     rax, [rax+70h]
0x18002f534  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f539  test    eax, eax
0x18002f53b  js      loc_18002F825
0x18002f541  mov     rdx, [rbp+String2]; String2
0x18002f545  lea     rcx, aLocation_0; "Location"
0x18002f54c  call    cs:__imp__wcsicmp
0x18002f552  test    eax, eax
0x18002f554  jnz     short loc_18002F5B1
0x18002f556  test    r15d, r15d
0x18002f559  jz      loc_18002F7B8
0x18002f55f  test    r12d, r12d
0x18002f562  jz      loc_18002F7B8
0x18002f568  mov     rcx, [r13+50h]
0x18002f56c  cmp     rcx, [r13+58h]
0x18002f570  jz      short loc_18002F582
0x18002f572  mov     rdx, [rbp+var_48]
0x18002f576  call    ??0?$CComPtrBase@UIWalletBackgroundAgentListener@@@ATL@@IEAA@PEAUIWalletBackgroundAgentListener@@@Z; ATL::CComPtrBase<IWalletBackgroundAgentListener>::CComPtrBase<IWalletBackgroundAgentListener>(IWalletBackgroundAgentListener *)
0x18002f57b  add     qword ptr [r13+50h], 8
0x18002f580  jmp     short loc_18002F597
0x18002f582  lea     rdx, [rbp+var_48]
0x18002f586  lea     rcx, [r13+48h]
0x18002f58a  call    ??$_PushBackOne2@V?$CComPtr@UIWalletItemListener@@@ATL@@@?$vector@V?$CComPtr@UIWalletItemListener@@@ATL@@V?$allocator@V?$CComPtr@UIWalletItemListener@@@ATL@@@utl@@@utl@@AEAA_N$$QEAV?$CComPtr@UIWalletItemListener@@@ATL@@@Z; utl::vector<ATL::CComPtr<IWalletItemListener>,utl::allocator<ATL::CComPtr<IWalletItemListener>>>::_PushBackOne2<ATL::CComPtr<IWalletItemListener>>(ATL::CComPtr<IWalletItemListener> &&)
0x18002f58f  test    al, al
0x18002f591  jz      loc_18002F85D
0x18002f597  cmp     [rbp+var_48], rdi
0x18002f59b  jz      loc_18002F4C9
0x18002f5a1  xor     edx, edx; struct IUnknown *
0x18002f5a3  lea     rcx, [rbp+var_48]; struct IUnknown **
0x18002f5a7  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18002f5ac  jmp     loc_18002F4C9
0x18002f5b1  mov     rdx, [rbp+String2]; String2
0x18002f5b5  lea     rcx, aRelevantlocati; "RelevantLocations"
0x18002f5bc  call    cs:__imp__wcsicmp
0x18002f5c2  test    eax, eax
0x18002f5c4  jnz     loc_18002F4D4
0x18002f5ca  jmp     loc_18002F827
0x18002f5cf  cmp     [rbp+String2], rdi
0x18002f5d3  jz      loc_18002F4D4
0x18002f5d9  cmp     [rbp+var_48], rdi
0x18002f5dd  jz      loc_18002F7B8
0x18002f5e3  mov     rcx, [r14]
0x18002f5e6  mov     rax, [rcx]
0x18002f5e9  xor     r8d, r8d
0x18002f5ec  lea     rdx, [rbp+String]
0x18002f5f0  mov     rax, [rax+80h]
0x18002f5f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f5fc  test    eax, eax
0x18002f5fe  js      loc_18002F825
0x18002f604  mov     rcx, [r14]
0x18002f607  mov     rax, [rcx]
0x18002f60a  xor     r8d, r8d
0x18002f60d  lea     rdx, [rbp+String2]
0x18002f611  mov     rax, [rax+70h]
0x18002f615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f61a  test    eax, eax
0x18002f61c  js      loc_18002F825
0x18002f622  mov     rdx, [rbp+String2]; String2
0x18002f626  lea     rcx, aDisplaymessage; "DisplayMessage"
0x18002f62d  call    cs:__imp__wcsicmp
0x18002f633  test    eax, eax
0x18002f635  jnz     short loc_18002F664
0x18002f637  mov     rbx, [rbp+String]
0x18002f63b  mov     rdx, [rbp+var_48]
0x18002f63f  lea     rcx, [rbp+var_30]
0x18002f643  call    ??0?$CComPtrBase@UIWalletBackgroundAgentListener@@@ATL@@IEAA@PEAUIWalletBackgroundAgentListener@@@Z; ATL::CComPtrBase<IWalletBackgroundAgentListener>::CComPtrBase<IWalletBackgroundAgentListener>(IWalletBackgroundAgentListener *)
0x18002f648  mov     r9, rbx
0x18002f64b  mov     r8d, 9C45h
0x18002f651  lea     rdx, [rbp+var_30]
0x18002f655  mov     rcx, r13
0x18002f658  call    ?HandleStringProperty@WalletPackageProcessor@Wallet@@AEAAJV?$CComPtr@UIWalletItem@@@ATL@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@PEBG@Z; Wallet::WalletPackageProcessor::HandleStringProperty(ATL::CComPtr<IWalletItem>,__MIDL___MIDL_itf_wallettypes_0000_0000_0010,ushort const *)
0x18002f65d  test    eax, eax
0x18002f65f  jmp     loc_18002F7B2
0x18002f664  mov     rdx, [rbp+String2]; String2
0x18002f668  lea     rcx, aLatitude_0; "Latitude"
0x18002f66f  call    cs:__imp__wcsicmp
0x18002f675  test    eax, eax
0x18002f677  jnz     short loc_18002F6D4
0x18002f679  mov     r15d, edi
0x18002f67c  mov     rcx, [rbp+String]; String
0x18002f680  test    rcx, rcx
0x18002f683  setnz   r15b
0x18002f687  call    cs:__imp__wtof
0x18002f68d  mov     rcx, [rbp+var_48]
0x18002f691  xorps   xmm1, xmm1
0x18002f694  xor     eax, eax
0x18002f696  movups  xmmword ptr [rbp+pvar], xmm1
0x18002f69a  mov     [rbp+var_10], rax
0x18002f69e  test    rcx, rcx
0x18002f6a1  jnz     short loc_18002F6AA
0x18002f6a3  mov     ebx, 80004003h
0x18002f6a8  jmp     short loc_18002F6CF
0x18002f6aa  mov     word ptr [rbp+pvar], bx
0x18002f6ae  movsd   [rbp+pvar+8], xmm0
0x18002f6b3  mov     rax, [rcx]
0x18002f6b6  lea     r8, [rbp+pvar]
0x18002f6ba  mov     edx, 9C41h
0x18002f6bf  mov     rax, [rax+38h]
0x18002f6c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f6c8  mov     ebx, edi
0x18002f6ca  test    eax, eax
0x18002f6cc  cmovs   ebx, eax
0x18002f6cf  jmp     loc_18002F7A6
0x18002f6d4  mov     rdx, [rbp+String2]; String2
0x18002f6d8  lea     rcx, aLongitude_0; "Longitude"
0x18002f6df  call    cs:__imp__wcsicmp
0x18002f6e5  test    eax, eax
0x18002f6e7  jnz     short loc_18002F741
0x18002f6e9  mov     r12d, edi
0x18002f6ec  mov     rcx, [rbp+String]; String
0x18002f6f0  test    rcx, rcx
0x18002f6f3  setnz   r12b
0x18002f6f7  call    cs:__imp__wtof
0x18002f6fd  mov     rcx, [rbp+var_48]
0x18002f701  xorps   xmm1, xmm1
0x18002f704  xor     eax, eax
0x18002f706  movups  xmmword ptr [rbp+pvar], xmm1
0x18002f70a  mov     [rbp+var_10], rax
0x18002f70e  test    rcx, rcx
0x18002f711  jnz     short loc_18002F71A
0x18002f713  mov     ebx, 80004003h
0x18002f718  jmp     short loc_18002F73F
0x18002f71a  mov     word ptr [rbp+pvar], bx
0x18002f71e  movsd   [rbp+pvar+8], xmm0
0x18002f723  mov     rax, [rcx]
0x18002f726  lea     r8, [rbp+pvar]
0x18002f72a  mov     edx, 9C42h
0x18002f72f  mov     rax, [rax+38h]
0x18002f733  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f738  mov     ebx, edi
0x18002f73a  test    eax, eax
0x18002f73c  cmovs   ebx, eax
0x18002f73f  jmp     short loc_18002F7A6
0x18002f741  mov     rdx, [rbp+String2]; String2
0x18002f745  lea     rcx, aAltitude_0; "Altitude"
0x18002f74c  call    cs:__imp__wcsicmp
0x18002f752  test    eax, eax
0x18002f754  jnz     loc_18002F4D4
0x18002f75a  mov     rcx, [rbp+String]; String
0x18002f75e  call    cs:__imp__wtof
0x18002f764  mov     rcx, [rbp+var_48]
0x18002f768  xorps   xmm1, xmm1
0x18002f76b  xor     eax, eax
0x18002f76d  movups  xmmword ptr [rbp+pvar], xmm1
0x18002f771  mov     [rbp+var_10], rax
0x18002f775  test    rcx, rcx
0x18002f778  jnz     short loc_18002F781
0x18002f77a  mov     ebx, 80004003h
0x18002f77f  jmp     short loc_18002F7A6
0x18002f781  mov     word ptr [rbp+pvar], bx
0x18002f785  movsd   [rbp+pvar+8], xmm0
0x18002f78a  mov     rax, [rcx]
0x18002f78d  lea     r8, [rbp+pvar]
0x18002f791  mov     edx, 9C43h
0x18002f796  mov     rax, [rax+38h]
0x18002f79a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f79f  mov     ebx, edi
0x18002f7a1  test    eax, eax
0x18002f7a3  cmovs   ebx, eax
0x18002f7a6  lea     rcx, [rbp+pvar]; pvar
0x18002f7aa  call    cs:__imp_PropVariantClear
0x18002f7b0  test    ebx, ebx
0x18002f7b2  jns     loc_18002F4CF
0x18002f7b8  mov     esi, 803A0054h
0x18002f7bd  jmp     short loc_18002F827
0x18002f7bf  mov     rcx, [r14]
0x18002f7c2  mov     rax, [rcx]
0x18002f7c5  xor     r8d, r8d
0x18002f7c8  lea     rdx, [rbp+String2]
0x18002f7cc  mov     rax, [rax+70h]
0x18002f7d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f7d5  test    eax, eax
0x18002f7d7  js      short loc_18002F825
0x18002f7d9  mov     rdx, [rbp+String2]; String2
0x18002f7dd  lea     rcx, aLocation_0; "Location"
0x18002f7e4  call    cs:__imp__wcsicmp
0x18002f7ea  test    eax, eax
0x18002f7ec  jnz     loc_18002F4D4
0x18002f7f2  mov     rdi, [rbp+var_38]
0x18002f7f6  mov     rax, [rdi]
0x18002f7f9  mov     rbx, [rax+20h]
0x18002f7fd  lea     rcx, [rbp+var_48]
0x18002f801  call    ??$pointerTo@UIWalletNotification@@@ce@@YAPEAPEAUIWalletNotification@@AEAV?$CComPtr@UIWalletNotification@@@ATL@@@Z; ce::pointerTo<IWalletNotification>(ATL::CComPtr<IWalletNotification> &)
0x18002f806  mov     r8, rax
0x18002f809  mov     rax, [rbp+arg_10]
0x18002f80d  mov     rdx, [rax]
0x18002f810  mov     rcx, rdi
0x18002f813  mov     rax, rbx
0x18002f816  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f81b  xor     edi, edi
0x18002f81d  test    eax, eax
0x18002f81f  jns     loc_18002F4CF
0x18002f825  mov     esi, eax
0x18002f827  lea     rcx, [rbp+var_38]
0x18002f82b  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x18002f830  nop
0x18002f831  lea     rcx, [rbp+var_48]
0x18002f835  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x18002f83a  nop
0x18002f83b  mov     rcx, r14
0x18002f83e  call    ??1?$CComPtrBase@UIWalletWebServiceManager@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(void)
0x18002f843  mov     eax, esi
0x18002f845  mov     rbx, [rsp+70h+arg_0]
0x18002f84d  add     rsp, 70h
0x18002f851  pop     r15
0x18002f853  pop     r14
0x18002f855  pop     r13
0x18002f857  pop     r12
0x18002f859  pop     rdi
0x18002f85a  pop     rsi
0x18002f85b  pop     rbp
0x18002f85c  retn
0x18002f85d  mov     esi, 8007000Eh
0x18002f862  jmp     short loc_18002F827
```
