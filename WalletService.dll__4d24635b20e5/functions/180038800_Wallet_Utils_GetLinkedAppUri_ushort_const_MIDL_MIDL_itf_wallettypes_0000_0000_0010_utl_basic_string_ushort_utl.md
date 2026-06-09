# Wallet::Utils::GetLinkedAppUri(ushort const *,__MIDL___MIDL_itf_wallettypes_0000_0000_0010,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)

- ea: `0x180038800`
- end: `0x180038a3a`
- name: `?GetLinkedAppUri@Utils@Wallet@@YAJPEBGW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `570`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x180027bd0`

## callees

- `0x180003ae4`
- `0x1800043b8`
- `0x18000d8d8`
- `0x180013f78`
- `0x180036c58`
- `0x180037310`
- `0x180037674`
- `0x180037fe4`
- `0x180038800`
- `0x1800390b4`
- `0x18003968c`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180038943`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180038943`

## pseudocode

```c
__int64 __fastcall Wallet::Utils::GetLinkedAppUri(__int64 a1, __int64 a2, _QWORD *a3)
{
  unsigned __int64 *v4; // r8
  Wallet::Utils *v5; // r9
  int AppTaskUriAndDefaultParams; // ebx
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64, __int64); // rbx
  __int64 v12; // rax
  struct IWalletItem *v13; // rdx
  PROPVARIANT v14; // rsi
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, PROPVARIANT, __int64); // rbx
  __int64 v19; // rax
  int TString; // eax
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v27; // [rsp+20h] [rbp-49h] BYREF
  PROPVARIANT pvar[2]; // [rsp+28h] [rbp-41h] BYREF
  __int64 v29; // [rsp+38h] [rbp-31h]
  _QWORD v30[4]; // [rsp+40h] [rbp-29h] BYREF
  _QWORD v31[4]; // [rsp+60h] [rbp-9h] BYREF
  _QWORD v32[8]; // [rsp+80h] [rbp+17h] BYREF
  __int64 v33; // [rsp+D0h] [rbp+67h] BYREF
  Wallet::Utils *v34; // [rsp+E8h] [rbp+7Fh] BYREF

  v33 = 0;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v32);
  v34 = 0;
  v27 = 0;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v31);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v30);
  if ( v5 )
  {
    AppTaskUriAndDefaultParams = Wallet::Utils::ConvertStringToItemId(v5, (const unsigned __int16 *)&v33, v4);
    if ( AppTaskUriAndDefaultParams >= 0 )
    {
      AppTaskUriAndDefaultParams = ((__int64 (__fastcall *)(__int64 *, __int64, __int64, __int64))Wallet::Utils::GetWalletItemManager)(
                                     &v27,
                                     v7,
                                     v8,
                                     v9);
      if ( AppTaskUriAndDefaultParams >= 0 )
      {
        v10 = v27;
        v11 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v27 + 64LL);
        v12 = ce::pointerTo<IWalletNotification>(&v34);
        AppTaskUriAndDefaultParams = v11(v10, v33, v12);
        if ( AppTaskUriAndDefaultParams >= 0 )
        {
          if ( (unsigned int)Wallet::Utils::IsItemTransactionEntry(v34, v13) )
          {
            v14 = 0;
            v33 = 0;
            *(_OWORD *)pvar = 0;
            v29 = 0;
            if ( v34 )
            {
              AppTaskUriAndDefaultParams = (*(__int64 (__fastcall **)(Wallet::Utils *, __int64, PROPVARIANT *))(*(_QWORD *)v34 + 48LL))(
                                             v34,
                                             30000,
                                             pvar);
              if ( AppTaskUriAndDefaultParams >= 0 )
              {
                if ( LOWORD(pvar[0]) == 21 )
                {
                  AppTaskUriAndDefaultParams = 0;
                  v14 = pvar[1];
                }
                else
                {
                  AppTaskUriAndDefaultParams = -2147418113;
                }
              }
            }
            else
            {
              AppTaskUriAndDefaultParams = -2147467261;
            }
            PropVariantClear(pvar);
            if ( AppTaskUriAndDefaultParams < 0
              || (v17 = v27,
                  v18 = *(__int64 (__fastcall **)(__int64, PROPVARIANT, __int64))(*(_QWORD *)v27 + 64LL),
                  v19 = ce::pointerTo<IWalletNotification>(&v33),
                  AppTaskUriAndDefaultParams = v18(v17, v14, v19),
                  AppTaskUriAndDefaultParams < 0)
              || (AppTaskUriAndDefaultParams = Wallet::Utils::GetAppTaskUriAndDefaultParams(&v33, v31, v30),
                  AppTaskUriAndDefaultParams < 0) )
            {
              ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(&v33, v15, v16);
              goto LABEL_27;
            }
            ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(&v33, v15, v16);
          }
          else
          {
            AppTaskUriAndDefaultParams = Wallet::Utils::GetAppTaskUriAndDefaultParams(&v34, v31, v30);
            if ( AppTaskUriAndDefaultParams < 0 )
              goto LABEL_27;
          }
          TString = Wallet::Utils::GetTStringProperty<IWalletItem,enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>(
                      v34,
                      3002,
                      v32);
          AppTaskUriAndDefaultParams = 0;
          if ( TString != -2143682560 )
            AppTaskUriAndDefaultParams = TString;
          if ( AppTaskUriAndDefaultParams >= 0 )
          {
            v21 = Wallet::Utils::ConstructApplicationLaunchUri(v31[0], v30[0], v32[0], a3);
            if ( v21 >= 0 )
            {
              if ( !((__int64)(a3[1] - *a3) >> 1) )
                AppTaskUriAndDefaultParams = -2147418113;
            }
            else
            {
              AppTaskUriAndDefaultParams = v21;
            }
          }
        }
      }
    }
  }
  else
  {
    AppTaskUriAndDefaultParams = -2147467261;
  }
LABEL_27:
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v30);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v31);
  ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(&v27, v22, v23);
  ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(&v34, v24, v25);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v32);
  return (unsigned int)AppTaskUriAndDefaultParams;
}

```

## disassembly

```asm
0x180038800  mov     [rsp-8+arg_8], rbx
0x180038805  push    rbp
0x180038806  push    rsi
0x180038807  push    rdi
0x180038808  push    r12
0x18003880a  push    r14
0x18003880c  lea     rbp, [rsp-37h]
0x180038811  sub     rsp, 0A0h
0x180038818  mov     r14, r8
0x18003881b  mov     r9, rcx
0x18003881e  mov     [rbp+57h+arg_0], 0
0x180038826  lea     rcx, [rbp+57h+var_40]
0x18003882a  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18003882f  nop
0x180038830  mov     [rbp+57h+arg_18], 0
0x180038838  mov     [rbp+57h+var_A0], 0
0x180038840  lea     rcx, [rbp+57h+var_60]
0x180038844  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180038849  nop
0x18003884a  lea     rcx, [rbp+57h+var_80]
0x18003884e  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180038853  nop
0x180038854  test    r9, r9
0x180038857  jnz     short loc_180038863
0x180038859  mov     ebx, 80004003h
0x18003885e  jmp     loc_1800389F0
0x180038863  lea     rdx, [rbp+57h+arg_0]; unsigned __int16 *
0x180038867  mov     rcx, r9; this
0x18003886a  call    ?ConvertStringToItemId@Utils@Wallet@@YAJPEBGAEA_K@Z; Wallet::Utils::ConvertStringToItemId(ushort const *,unsigned __int64 &)
0x18003886f  mov     ebx, eax
0x180038871  test    eax, eax
0x180038873  js      loc_1800389F0
0x180038879  lea     rcx, [rbp+57h+var_A0]
0x18003887d  call    ?GetWalletItemManager@Utils@Wallet@@YAJAEAV?$CComPtr@UIWalletItemManager@@@ATL@@@Z; Wallet::Utils::GetWalletItemManager(ATL::CComPtr<IWalletItemManager> &)
0x180038882  mov     ebx, eax
0x180038884  test    eax, eax
0x180038886  js      loc_1800389F0
0x18003888c  mov     rdi, [rbp+57h+var_A0]
0x180038890  mov     rax, [rdi]
0x180038893  mov     rbx, [rax+40h]
0x180038897  lea     rcx, [rbp+57h+arg_18]
0x18003889b  call    ??$pointerTo@UIWalletNotification@@@ce@@YAPEAPEAUIWalletNotification@@AEAV?$CComPtr@UIWalletNotification@@@ATL@@@Z; ce::pointerTo<IWalletNotification>(ATL::CComPtr<IWalletNotification> &)
0x1800388a0  mov     r8, rax
0x1800388a3  mov     rdx, [rbp+57h+arg_0]
0x1800388a7  mov     rcx, rdi
0x1800388aa  mov     rax, rbx
0x1800388ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800388b2  mov     ebx, eax
0x1800388b4  test    eax, eax
0x1800388b6  js      loc_1800389F0
0x1800388bc  mov     rcx, [rbp+57h+arg_18]; this
0x1800388c0  call    ?IsItemTransactionEntry@Utils@Wallet@@YAHPEAUIWalletItem@@@Z; Wallet::Utils::IsItemTransactionEntry(IWalletItem *)
0x1800388c5  mov     r12d, 8000FFFFh
0x1800388cb  test    eax, eax
0x1800388cd  jnz     short loc_1800388EF
0x1800388cf  lea     r8, [rbp+57h+var_80]
0x1800388d3  lea     rdx, [rbp+57h+var_60]
0x1800388d7  lea     rcx, [rbp+57h+arg_18]
0x1800388db  call    ?GetAppTaskUriAndDefaultParams@Utils@Wallet@@YAJAEAV?$CComPtr@UIWalletItem@@@ATL@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@1@Z; Wallet::Utils::GetAppTaskUriAndDefaultParams(ATL::CComPtr<IWalletItem> &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x1800388e0  mov     ebx, eax
0x1800388e2  test    eax, eax
0x1800388e4  jns     loc_1800389A6
0x1800388ea  jmp     loc_1800389F0
0x1800388ef  xor     esi, esi
0x1800388f1  mov     [rbp+57h+arg_0], rsi
0x1800388f5  mov     rcx, [rbp+57h+arg_18]
0x1800388f9  xorps   xmm0, xmm0
0x1800388fc  xor     eax, eax
0x1800388fe  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180038902  mov     [rbp+57h+var_88], rax
0x180038906  test    rcx, rcx
0x180038909  jnz     short loc_180038912
0x18003890b  mov     ebx, 80004003h
0x180038910  jmp     short loc_18003893F
0x180038912  mov     rax, [rcx]
0x180038915  lea     r8, [rbp+57h+pvar]
0x180038919  mov     edx, 7530h
0x18003891e  mov     rax, [rax+30h]
0x180038922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038927  mov     ebx, eax
0x180038929  test    eax, eax
0x18003892b  js      short loc_18003893F
0x18003892d  cmp     word ptr [rbp+57h+pvar], 15h
0x180038932  jz      short loc_180038939
0x180038934  mov     ebx, r12d
0x180038937  jmp     short loc_18003893F
0x180038939  xor     ebx, ebx
0x18003893b  mov     rsi, [rbp+57h+pvar+8]
0x18003893f  lea     rcx, [rbp+57h+pvar]; pvar
0x180038943  call    cs:__imp_PropVariantClear
0x180038949  test    ebx, ebx
0x18003894b  jns     short loc_18003895B
0x18003894d  lea     rcx, [rbp+57h+arg_0]
0x180038951  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x180038956  jmp     loc_1800389F0
0x18003895b  mov     rdi, [rbp+57h+var_A0]
0x18003895f  mov     rax, [rdi]
0x180038962  mov     rbx, [rax+40h]
0x180038966  lea     rcx, [rbp+57h+arg_0]
0x18003896a  call    ??$pointerTo@UIWalletNotification@@@ce@@YAPEAPEAUIWalletNotification@@AEAV?$CComPtr@UIWalletNotification@@@ATL@@@Z; ce::pointerTo<IWalletNotification>(ATL::CComPtr<IWalletNotification> &)
0x18003896f  mov     r8, rax
0x180038972  mov     rdx, rsi
0x180038975  mov     rcx, rdi
0x180038978  mov     rax, rbx
0x18003897b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038980  mov     ebx, eax
0x180038982  test    eax, eax
0x180038984  js      short loc_18003894D
0x180038986  lea     r8, [rbp+57h+var_80]
0x18003898a  lea     rdx, [rbp+57h+var_60]
0x18003898e  lea     rcx, [rbp+57h+arg_0]
0x180038992  call    ?GetAppTaskUriAndDefaultParams@Utils@Wallet@@YAJAEAV?$CComPtr@UIWalletItem@@@ATL@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@1@Z; Wallet::Utils::GetAppTaskUriAndDefaultParams(ATL::CComPtr<IWalletItem> &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x180038997  mov     ebx, eax
0x180038999  lea     rcx, [rbp+57h+arg_0]
0x18003899d  test    eax, eax
0x18003899f  js      short loc_180038951
0x1800389a1  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x1800389a6  lea     r8, [rbp+57h+var_40]
0x1800389aa  mov     edx, 0BBAh
0x1800389af  mov     rcx, [rbp+57h+arg_18]
0x1800389b3  call    ??$GetTStringProperty@UIWalletItem@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@Utils@Wallet@@YAJPEAUIWalletItem@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Wallet::Utils::GetTStringProperty<IWalletItem,__MIDL___MIDL_itf_wallettypes_0000_0000_0010>(IWalletItem *,__MIDL___MIDL_itf_wallettypes_0000_0000_0010,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x1800389b8  xor     ebx, ebx
0x1800389ba  cmp     eax, 803A0000h
0x1800389bf  cmovnz  ebx, eax
0x1800389c2  test    ebx, ebx
0x1800389c4  js      short loc_1800389F0
0x1800389c6  mov     r9, r14
0x1800389c9  mov     r8, [rbp+57h+var_40]
0x1800389cd  mov     rdx, [rbp+57h+var_80]
0x1800389d1  mov     rcx, [rbp+57h+var_60]
0x1800389d5  call    ?ConstructApplicationLaunchUri@Utils@Wallet@@YAJPEBG00AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Wallet::Utils::ConstructApplicationLaunchUri(ushort const *,ushort const *,ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x1800389da  test    eax, eax
0x1800389dc  jns     short loc_1800389E2
0x1800389de  mov     ebx, eax
0x1800389e0  jmp     short loc_1800389F0
0x1800389e2  mov     rax, [r14+8]
0x1800389e6  sub     rax, [r14]
0x1800389e9  sar     rax, 1
0x1800389ec  cmovz   ebx, r12d
0x1800389f0  lea     rcx, [rbp+57h+var_80]
0x1800389f4  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800389f9  nop
0x1800389fa  lea     rcx, [rbp+57h+var_60]
0x1800389fe  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180038a03  nop
0x180038a04  lea     rcx, [rbp+57h+var_A0]
0x180038a08  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x180038a0d  nop
0x180038a0e  lea     rcx, [rbp+57h+arg_18]
0x180038a12  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x180038a17  nop
0x180038a18  lea     rcx, [rbp+57h+var_40]
0x180038a1c  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180038a21  mov     eax, ebx
0x180038a23  mov     rbx, [rsp+0C0h+arg_8]
0x180038a2b  add     rsp, 0A0h
0x180038a32  pop     r14
0x180038a34  pop     r12
0x180038a36  pop     rdi
0x180038a37  pop     rsi
0x180038a38  pop     rbp
0x180038a39  retn
```
