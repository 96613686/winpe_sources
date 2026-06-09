# Wallet::WalletPackageProcessor::ProcessProperties(ATL::CComPtr<IXmlReader>,ATL::CComPtr<IWalletItem> &)

- ea: `0x18002f86c`
- end: `0x1800300af`
- name: `?ProcessProperties@WalletPackageProcessor@Wallet@@AEAAJV?$CComPtr@UIXmlReader@@@ATL@@AEAV?$CComPtr@UIWalletItem@@@4@@Z`
- size: `2115`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800306b0`

## callees

- `0x180003ae4`
- `0x1800043b8`
- `0x180013f78`
- `0x180013fe4`
- `0x18001400c`
- `0x180014328`
- `0x18001c81c`
- `0x18001d000`
- `0x18002ce08`
- `0x18002d048`
- `0x18002df5c`
- `0x18002f86c`
- `0x180032cf0`
- `0x180032f74`
- `0x1800376c0`
- `0x180039cec`
- `0x180039e60`
- `0x180043052`
- `0x180043090`
- `0x180045010`

## import_xrefs

- `msvcrt!_wtol` at `0x18002fef5`
- `msvcrt!_wtol` at `0x18002fef5`
- `msvcrt!_wcsicmp` at `0x18002f9fa`
- `msvcrt!_wcsicmp` at `0x18002fd3c`
- `msvcrt!_wcsicmp` at `0x18002fd56`
- `msvcrt!_wcsicmp` at `0x18002fd6c`
- `msvcrt!_wcsicmp` at `0x18002fd82`
- `msvcrt!_wcsicmp` at `0x18002fd98`
- `msvcrt!_wcsicmp` at `0x18002fdae`
- `msvcrt!_wcsicmp` at `0x18002fe1e`
- `msvcrt!_wcsicmp` at `0x18002fe54`
- `msvcrt!_wcsicmp` at `0x18002fe70`
- `msvcrt!_wcsicmp` at `0x18002fe8c`
- `msvcrt!_wcsicmp` at `0x18002fea8`
- `msvcrt!_wcsicmp` at `0x18002fec7`
- `msvcrt!_wcsicmp` at `0x18002fee6`
- `msvcrt!_wcsicmp` at `0x18002ff0f`
- `msvcrt!_wcsicmp` at `0x18002ff29`
- `msvcrt!_wcsicmp` at `0x18002ff69`
- `msvcrt!_wcsicmp` at `0x18002ff85`
- `msvcrt!_wcsicmp` at `0x18002ffa1`
- `msvcrt!_wcsicmp` at `0x18002ffbd`
- `msvcrt!_wcsicmp` at `0x18002ffd9`
- `msvcrt!_wcsicmp` at `0x18002fffc`
- `msvcrt!_wcsicmp` at `0x18002f9fa`
- `msvcrt!_wcsicmp` at `0x18002fd3c`
- `msvcrt!_wcsicmp` at `0x18002fd56`
- `msvcrt!_wcsicmp` at `0x18002fd6c`
- `msvcrt!_wcsicmp` at `0x18002fd82`
- `msvcrt!_wcsicmp` at `0x18002fd98`
- `msvcrt!_wcsicmp` at `0x18002fdae`
- `msvcrt!_wcsicmp` at `0x18002fe1e`
- `msvcrt!_wcsicmp` at `0x18002fe54`
- `msvcrt!_wcsicmp` at `0x18002fe70`
- `msvcrt!_wcsicmp` at `0x18002fe8c`
- `msvcrt!_wcsicmp` at `0x18002fea8`
- `msvcrt!_wcsicmp` at `0x18002fec7`
- `msvcrt!_wcsicmp` at `0x18002fee6`
- `msvcrt!_wcsicmp` at `0x18002ff0f`
- `msvcrt!_wcsicmp` at `0x18002ff29`
- `msvcrt!_wcsicmp` at `0x18002ff69`
- `msvcrt!_wcsicmp` at `0x18002ff85`
- `msvcrt!_wcsicmp` at `0x18002ffa1`
- `msvcrt!_wcsicmp` at `0x18002ffbd`
- `msvcrt!_wcsicmp` at `0x18002ffd9`
- `msvcrt!_wcsicmp` at `0x18002fffc`

## string_xrefs

- `0x18002ff08`: `AutoDetectLinks`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall Wallet::WalletPackageProcessor::ProcessProperties(__int64 a1, __int64 *a2, __int64 *a3)
{
  __int64 *v3; // rdi
  int v5; // esi
  unsigned int v6; // r15d
  unsigned int v7; // r14d
  unsigned int v8; // r13d
  BOOL v9; // ebx
  int v10; // eax
  __int64 v11; // r8
  unsigned __int16 *v12; // r9
  int LocalizedValue; // eax
  unsigned __int16 *v14; // rdx
  __int64 v15; // rdi
  int (__fastcall *v16)(__int64, unsigned __int16 *, __int64 *); // rbx
  __int64 *v17; // rax
  void **p_lpValue; // rcx
  unsigned int v20; // [rsp+20h] [rbp-E0h]
  wchar_t *String2; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t *String; // [rsp+40h] [rbp-C0h] BYREF
  int v24; // [rsp+48h] [rbp-B8h] BYREF
  void *v25[2]; // [rsp+50h] [rbp-B0h] BYREF
  _WORD v26[8]; // [rsp+60h] [rbp-A0h] BYREF
  void *v27[2]; // [rsp+70h] [rbp-90h] BYREF
  _WORD v28[8]; // [rsp+80h] [rbp-80h] BYREF
  LPCWSTR lpValue; // [rsp+90h] [rbp-70h] BYREF
  LPCWSTR v30; // [rsp+98h] [rbp-68h]
  _WORD v31[8]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v32; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 *v33; // [rsp+B8h] [rbp-48h]
  _WORD v34[8]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v35; // [rsp+D0h] [rbp-30h]
  __int64 *v36; // [rsp+D8h] [rbp-28h]
  wchar_t *v37; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 *v38; // [rsp+E8h] [rbp-18h]
  _WORD v39[8]; // [rsp+F0h] [rbp-10h] BYREF
  Wallet::ServerUtils *v40; // [rsp+100h] [rbp+0h] BYREF
  Wallet::ServerUtils *v41; // [rsp+108h] [rbp+8h]
  _WORD v42[8]; // [rsp+110h] [rbp+10h] BYREF
  wchar_t *v43; // [rsp+120h] [rbp+20h] BYREF
  wchar_t *v44; // [rsp+128h] [rbp+28h]
  _WORD v45[8]; // [rsp+130h] [rbp+30h] BYREF
  _WORD *v46; // [rsp+140h] [rbp+40h] BYREF
  _WORD *v47; // [rsp+148h] [rbp+48h]
  _WORD v48[8]; // [rsp+150h] [rbp+50h] BYREF
  __int64 *v49; // [rsp+160h] [rbp+60h]
  OLECHAR sz[40]; // [rsp+170h] [rbp+70h] BYREF
  WCHAR TimeStr[520]; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned __int16 v52[520]; // [rsp+5D0h] [rbp+4D0h] BYREF

  v3 = a3;
  v36 = a3;
  v35 = a1;
  v49 = a2;
  v24 = 0;
  String2 = 0;
  String = 0;
  v32 = v34;
  v33 = v34;
  v34[0] = 0;
  v46 = v48;
  v47 = v48;
  v48[0] = 0;
  lpValue = v31;
  v30 = v31;
  v31[0] = 0;
  v43 = v45;
  v44 = v45;
  v45[0] = 0;
  v40 = (Wallet::ServerUtils *)v42;
  v41 = (Wallet::ServerUtils *)v42;
  v42[0] = 0;
  v37 = v39;
  v38 = v39;
  v39[0] = 0;
  memset_0(sz, 0, sizeof(sz));
  ATL::CComPtrBase<IWalletBackgroundAgentListener>::CComPtrBase<IWalletBackgroundAgentListener>(&v22, *v3);
  v5 = Wallet::Utils::RemoveCustomProperties(&v22);
  if ( v5 < 0 )
    goto LABEL_99;
  v5 = 0;
  v6 = 0;
  v7 = -1;
  v8 = -1;
  while ( 2 )
  {
    v9 = 1;
    while ( 1 )
    {
      do
      {
        while ( 1 )
        {
          while ( 1 )
          {
            if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)*a2 + 200LL))(*a2) )
              goto LABEL_99;
            v10 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)*a2 + 48LL))(*a2, &v24);
            if ( v10 < 0 )
              goto LABEL_98;
            if ( v24 != 1 )
              break;
            v10 = (*(__int64 (__fastcall **)(__int64, wchar_t **, _QWORD))(*(_QWORD *)*a2 + 112LL))(*a2, &String2, 0);
            if ( v10 < 0 )
              goto LABEL_98;
            if ( !_wcsicmp(String2, L"Header") )
            {
              v6 = 1;
              goto LABEL_92;
            }
            if ( !_wcsicmp(String2, L"Primary") )
            {
              v6 = 2;
              goto LABEL_92;
            }
            if ( !_wcsicmp(String2, L"Secondary") )
            {
              v6 = 4;
              goto LABEL_92;
            }
            if ( !_wcsicmp(String2, L"Center") )
            {
              v6 = 8;
              goto LABEL_92;
            }
            if ( _wcsicmp(String2, L"Footer") )
            {
              if ( !_wcsicmp(String2, L"Property") )
                ++v7;
            }
            else
            {
              v6 = 16;
LABEL_92:
              v7 = -1;
            }
          }
          if ( v24 != 3 )
            break;
          if ( String2 )
          {
            v10 = (*(__int64 (__fastcall **)(__int64, wchar_t **, _QWORD))(*(_QWORD *)*a2 + 128LL))(*a2, &String, 0);
            if ( v10 < 0
              || (v10 = (*(__int64 (__fastcall **)(__int64, wchar_t **, _QWORD))(*(_QWORD *)*a2 + 112LL))(
                          *a2,
                          &String2,
                          0),
                  v10 < 0) )
            {
LABEL_98:
              v5 = v10;
              goto LABEL_99;
            }
            if ( _wcsicmp(L"Key", String2) )
            {
              if ( !_wcsicmp(L"Name", String2) )
              {
                p_lpValue = (void **)&v46;
                goto LABEL_65;
              }
              if ( !_wcsicmp(L"Value", String2) )
              {
                p_lpValue = (void **)&lpValue;
                goto LABEL_65;
              }
              if ( !_wcsicmp(L"NumberFormat", String2) )
              {
                p_lpValue = (void **)&v43;
                goto LABEL_65;
              }
              if ( !_wcsicmp(L"CurrencyCode", String2) )
              {
                p_lpValue = (void **)&v40;
                goto LABEL_65;
              }
              if ( !_wcsicmp(L"DateTimeFormat", String2) )
              {
                p_lpValue = (void **)&v37;
                goto LABEL_65;
              }
              if ( _wcsicmp(L"SummaryViewPosition", String2) )
              {
                if ( !_wcsicmp(L"AutoDetectLinks", String2) )
                  v9 = _wcsicmp(String, L"true") == 0;
              }
              else
              {
                v8 = _wtol(String);
              }
            }
            else
            {
              p_lpValue = (void **)&v32;
LABEL_65:
              if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                       (__int64)p_lpValue,
                                       (__int64)String) )
                goto LABEL_66;
            }
          }
        }
      }
      while ( v24 != 15 );
      v10 = (*(__int64 (__fastcall **)(__int64, wchar_t **, _QWORD))(*(_QWORD *)*a2 + 112LL))(*a2, &String2, 0);
      if ( v10 < 0 )
        goto LABEL_98;
      if ( !_wcsicmp(L"Property", String2) )
        break;
      if ( !_wcsicmp(L"DisplayProperties", String2) )
        goto LABEL_99;
      if ( !_wcsicmp(String2, L"Header")
        || !_wcsicmp(String2, L"Primary")
        || !_wcsicmp(String2, L"Secondary")
        || !_wcsicmp(String2, L"Center")
        || !_wcsicmp(String2, L"Footer") )
      {
        v6 = 0;
      }
    }
    if ( v43 != v44 && (v40 != v41 || v37 != v38)
      || v40 != v41 && (v43 != v44 || v37 != v38)
      || v37 != v38 && (v43 != v44 || v40 != v41) )
    {
      goto LABEL_95;
    }
    if ( v43 == v44 )
    {
      if ( v40 == v41 )
      {
        if ( v37 == v38 )
          goto LABEL_36;
        if ( (int)FormatDateTime(v37, lpValue, TimeStr, (unsigned int)v43) < 0 )
          goto LABEL_95;
        v11 = -1;
        do
          ++v11;
        while ( TimeStr[v11] );
      }
      else
      {
        if ( (int)Wallet::ServerUtils::GetCurrencySymbol(v40, v52, v38, (unsigned int)v43) < 0
          || (int)Wallet::ServerUtils::FormatCurrency(lpValue, v52, TimeStr, v12, v20) < 0 )
        {
          goto LABEL_95;
        }
        v11 = -1;
        do
          ++v11;
        while ( TimeStr[v11] );
      }
LABEL_35:
      if ( !utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
              &lpValue,
              TimeStr,
              v11) )
      {
LABEL_66:
        v5 = -2147024882;
        goto LABEL_99;
      }
LABEL_36:
      v22 = 0;
      v27[0] = v28;
      v27[1] = v28;
      v28[0] = 0;
      v25[0] = v26;
      v25[1] = v26;
      v26[0] = 0;
      LocalizedValue = Wallet::WalletPackageProcessor::GetLocalizedValue(v35, lpValue, v27);
      if ( LocalizedValue < 0 )
        goto LABEL_96;
      LocalizedValue = Wallet::WalletPackageProcessor::GetLocalizedValue(v35, v46, v25);
      if ( LocalizedValue < 0 )
        goto LABEL_96;
      v14 = v32;
      if ( v32 == v33 )
      {
        LocalizedValue = Wallet::Utils::CreateGuid(sz, v32);
        if ( LocalizedValue < 0 )
          goto LABEL_96;
        LocalizedValue = tlx::assign_sprintf<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
                           &v32,
                           L"Key%s",
                           sz);
        if ( LocalizedValue < 0 )
          goto LABEL_96;
        v14 = v32;
      }
      if ( v9 )
        v20 = 2;
      else
        v20 = 8;
      if ( (int)Wallet::Utils::SetItemCustomProperty(*v3, v14, v25[0], v27[0]) < 0 )
        goto LABEL_50;
      v15 = *v3;
      v16 = *(int (__fastcall **)(__int64, unsigned __int16 *, __int64 *))(*(_QWORD *)v15 + 88LL);
      v17 = ce::pointerTo<IWalletNotification>(&v22);
      if ( v16(v15, v32, v17) < 0 )
      {
        v3 = v36;
        goto LABEL_52;
      }
      LocalizedValue = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v22 + 80LL))(
                         v22,
                         0,
                         v6,
                         v7);
      if ( LocalizedValue >= 0 )
      {
        LocalizedValue = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v22 + 80LL))(
                           v22,
                           1,
                           v8 != -1 ? 0x20 : 0,
                           v8);
        if ( LocalizedValue >= 0 )
        {
          v3 = v36;
          if ( (*(int (__fastcall **)(__int64, unsigned __int16 *, __int64))(*(_QWORD *)*v36 + 96LL))(*v36, v32, v22) < 0 )
          {
LABEL_50:
            v5 = -2143682461;
LABEL_97:
            utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v25);
            utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v27);
            ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(&v22);
            goto LABEL_99;
          }
LABEL_52:
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v25);
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v27);
          ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(&v22);
          v33 = v32;
          *v32 = 0;
          v47 = v46;
          *v46 = 0;
          v30 = lpValue;
          *lpValue = 0;
          v44 = v43;
          *v43 = 0;
          v41 = v40;
          *(_WORD *)v40 = 0;
          v38 = v37;
          *v37 = 0;
          v8 = -1;
          continue;
        }
      }
LABEL_96:
      v5 = LocalizedValue;
      goto LABEL_97;
    }
    break;
  }
  if ( (int)FormatNumber(v43, (wchar_t *)lpValue, TimeStr, (unsigned int)v43) >= 0 )
  {
    v11 = -1;
    do
      ++v11;
    while ( TimeStr[v11] );
    goto LABEL_35;
  }
LABEL_95:
  v5 = -2143682461;
LABEL_99:
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((void **)&v37);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((void **)&v40);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((void **)&v43);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((void **)&lpValue);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((void **)&v46);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((void **)&v32);
  ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(a2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002f86c  mov     [rsp-8+arg_18], rbx
0x18002f871  push    rbp
0x18002f872  push    rsi
0x18002f873  push    rdi
0x18002f874  push    r12
0x18002f876  push    r13
0x18002f878  push    r14
0x18002f87a  push    r15
0x18002f87c  lea     rbp, [rsp-8F0h]
0x18002f884  sub     rsp, 9F0h
0x18002f88b  mov     rax, cs:__security_cookie
0x18002f892  xor     rax, rsp
0x18002f895  mov     [rbp+920h+var_40], rax
0x18002f89c  mov     rdi, r8
0x18002f89f  mov     [rbp+920h+var_948], r8
0x18002f8a3  mov     r12, rdx
0x18002f8a6  mov     [rbp+920h+var_950], rcx
0x18002f8aa  mov     [rbp+920h+var_8C0], rdx
0x18002f8ae  xor     ebx, ebx
0x18002f8b0  mov     [rsp+0A20h+var_9D8], ebx
0x18002f8b4  mov     [rsp+0A20h+String2], rbx
0x18002f8b9  mov     [rsp+0A20h+String], rbx
0x18002f8be  lea     rax, [rbp+920h+var_960]
0x18002f8c2  mov     [rbp+920h+var_970], rax
0x18002f8c6  lea     rax, [rbp+920h+var_960]
0x18002f8ca  mov     [rbp+920h+var_968], rax
0x18002f8ce  mov     [rbp+920h+var_960], bx
0x18002f8d2  lea     rax, [rbp+920h+var_8D0]
0x18002f8d6  mov     [rbp+920h+var_8E0], rax
0x18002f8da  lea     rax, [rbp+920h+var_8D0]
0x18002f8de  mov     [rbp+920h+var_8D8], rax
0x18002f8e2  mov     [rbp+920h+var_8D0], bx
0x18002f8e6  lea     rax, [rbp+920h+var_980]
0x18002f8ea  mov     [rbp+920h+lpValue], rax
0x18002f8ee  lea     rax, [rbp+920h+var_980]
0x18002f8f2  mov     [rbp+920h+var_988], rax
0x18002f8f6  mov     [rbp+920h+var_980], bx
0x18002f8fa  lea     rax, [rbp+920h+var_8F0]
0x18002f8fe  mov     [rbp+920h+var_900], rax
0x18002f902  lea     rax, [rbp+920h+var_8F0]
0x18002f906  mov     [rbp+920h+var_8F8], rax
0x18002f90a  mov     [rbp+920h+var_8F0], bx
0x18002f90e  lea     rax, [rbp+920h+var_910]
0x18002f912  mov     [rbp+920h+var_920], rax
0x18002f916  lea     rax, [rbp+920h+var_910]
0x18002f91a  mov     [rbp+920h+var_918], rax
0x18002f91e  mov     [rbp+920h+var_910], bx
0x18002f922  lea     rax, [rbp+920h+var_930]
0x18002f926  mov     [rbp+920h+var_940], rax
0x18002f92a  lea     rax, [rbp+920h+var_930]
0x18002f92e  mov     [rbp+920h+var_938], rax
0x18002f932  mov     [rbp+920h+var_930], bx
0x18002f936  xor     edx, edx; Val
0x18002f938  lea     r8d, [rbx+50h]; Size
0x18002f93c  lea     rcx, [rbp+920h+sz]; void *
0x18002f940  call    memset_0
0x18002f945  mov     rdx, [rdi]
0x18002f948  lea     rcx, [rsp+0A20h+var_9E8]
0x18002f94d  call    ??0?$CComPtrBase@UIWalletBackgroundAgentListener@@@ATL@@IEAA@PEAUIWalletBackgroundAgentListener@@@Z; ATL::CComPtrBase<IWalletBackgroundAgentListener>::CComPtrBase<IWalletBackgroundAgentListener>(IWalletBackgroundAgentListener *)
0x18002f952  lea     rcx, [rsp+0A20h+var_9E8]
0x18002f957  call    ?RemoveCustomProperties@Utils@Wallet@@YAJV?$CComPtr@UIWalletItem@@@ATL@@@Z; Wallet::Utils::RemoveCustomProperties(ATL::CComPtr<IWalletItem>)
0x18002f95c  mov     esi, eax
0x18002f95e  test    eax, eax
0x18002f960  js      loc_18003003F
0x18002f966  mov     esi, ebx
0x18002f968  mov     r15d, ebx
0x18002f96b  or      eax, 0FFFFFFFFh
0x18002f96e  mov     r14d, eax
0x18002f971  mov     r13d, eax
0x18002f974  mov     ebx, 1
0x18002f979  mov     rcx, [r12]
0x18002f97d  mov     rax, [rcx]
0x18002f980  mov     rax, [rax+0C8h]
0x18002f987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f98c  test    eax, eax
0x18002f98e  jnz     loc_18003003F
0x18002f994  mov     rcx, [r12]
0x18002f998  mov     rax, [rcx]
0x18002f99b  lea     rdx, [rsp+0A20h+var_9D8]
0x18002f9a0  mov     rax, [rax+30h]
0x18002f9a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f9a9  xor     edx, edx
0x18002f9ab  test    eax, eax
0x18002f9ad  js      loc_18003003D
0x18002f9b3  mov     ecx, [rsp+0A20h+var_9D8]
0x18002f9b7  sub     ecx, 1
0x18002f9ba  jz      loc_18002FF3D
0x18002f9c0  sub     ecx, 2
0x18002f9c3  jz      loc_18002FDC4
0x18002f9c9  cmp     ecx, 0Ch
0x18002f9cc  jnz     short loc_18002F979
0x18002f9ce  mov     rcx, [r12]
0x18002f9d2  mov     rax, [rcx]
0x18002f9d5  xor     r8d, r8d
0x18002f9d8  lea     rdx, [rsp+0A20h+String2]
0x18002f9dd  mov     rax, [rax+70h]
0x18002f9e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f9e6  test    eax, eax
0x18002f9e8  js      loc_18003003D
0x18002f9ee  mov     rdx, [rsp+0A20h+String2]; String2
0x18002f9f3  lea     rcx, aProperty; "Property"
0x18002f9fa  call    cs:__imp__wcsicmp
0x18002fa00  test    eax, eax
0x18002fa02  jnz     loc_18002FD30
0x18002fa08  mov     rdx, [rbp+920h+var_918]
0x18002fa0c  mov     rcx, [rbp+920h+var_920]; this
0x18002fa10  mov     r8, [rbp+920h+var_938]; unsigned __int16 *
0x18002fa14  mov     rax, [rbp+920h+var_940]
0x18002fa18  mov     r9, [rbp+920h+var_900]; unsigned int
0x18002fa1c  mov     r10, [rbp+920h+var_8F8]
0x18002fa20  cmp     r9, r10
0x18002fa23  jz      short loc_18002FA37
0x18002fa25  cmp     rcx, rdx
0x18002fa28  jnz     loc_180030012
0x18002fa2e  cmp     rax, r8
0x18002fa31  jnz     loc_180030012
0x18002fa37  cmp     rcx, rdx
0x18002fa3a  jz      short loc_18002FA4E
0x18002fa3c  cmp     r9, r10
0x18002fa3f  jnz     loc_180030012
0x18002fa45  cmp     rax, r8
0x18002fa48  jnz     loc_180030012
0x18002fa4e  cmp     rax, r8
0x18002fa51  jz      short loc_18002FA65
0x18002fa53  cmp     r9, r10
0x18002fa56  jnz     loc_180030012
0x18002fa5c  cmp     rcx, rdx
0x18002fa5f  jnz     loc_180030012
0x18002fa65  cmp     r9, r10
0x18002fa68  jz      short loc_18002FAA1
0x18002fa6a  lea     r8, [rbp+920h+TimeStr]; unsigned __int16 *
0x18002fa71  mov     rdx, [rbp+920h+lpValue]; String
0x18002fa75  mov     rcx, r9; String2
0x18002fa78  call    ?FormatNumber@@YAJPEBG0PEAGI@Z; FormatNumber(ushort const *,ushort const *,ushort *,uint)
0x18002fa7d  xor     ecx, ecx
0x18002fa7f  test    eax, eax
0x18002fa81  js      loc_180030012
0x18002fa87  lea     rax, [rbp+920h+TimeStr]
0x18002fa8e  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002fa92  inc     r8
0x18002fa95  cmp     [rax+r8*2], cx
0x18002fa9a  jnz     short loc_18002FA92
0x18002fa9c  jmp     loc_18002FB29
0x18002faa1  cmp     rcx, rdx
0x18002faa4  jz      short loc_18002FAF2
0x18002faa6  lea     rdx, [rbp+920h+var_450]; unsigned __int16 *
0x18002faad  call    ?GetCurrencySymbol@ServerUtils@Wallet@@YAJPEBGPEAGK@Z; Wallet::ServerUtils::GetCurrencySymbol(ushort const *,ushort *,ulong)
0x18002fab2  test    eax, eax
0x18002fab4  js      loc_180030012
0x18002faba  lea     r8, [rbp+920h+TimeStr]; unsigned __int16 *
0x18002fac1  lea     rdx, [rbp+920h+var_450]; unsigned __int16 *
0x18002fac8  mov     rcx, [rbp+920h+lpValue]; lpValue
0x18002facc  call    ?FormatCurrency@ServerUtils@Wallet@@YAJPEBG0PEAGK@Z; Wallet::ServerUtils::FormatCurrency(ushort const *,ushort const *,ushort *,ulong)
0x18002fad1  xor     ecx, ecx
0x18002fad3  test    eax, eax
0x18002fad5  js      loc_180030012
0x18002fadb  lea     rax, [rbp+920h+TimeStr]
0x18002fae2  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002fae6  inc     r8
0x18002fae9  cmp     [rax+r8*2], cx
0x18002faee  jnz     short loc_18002FAE6
0x18002faf0  jmp     short loc_18002FB29
0x18002faf2  cmp     rax, r8
0x18002faf5  jz      short loc_18002FB41
0x18002faf7  lea     r8, [rbp+920h+TimeStr]; lpTimeStr
0x18002fafe  mov     rdx, [rbp+920h+lpValue]; unsigned __int16 *
0x18002fb02  mov     rcx, rax; String2
0x18002fb05  call    ?FormatDateTime@@YAJPEBG0PEAGI@Z; FormatDateTime(ushort const *,ushort const *,ushort *,uint)
0x18002fb0a  xor     ecx, ecx
0x18002fb0c  test    eax, eax
0x18002fb0e  js      loc_180030012
0x18002fb14  lea     rax, [rbp+920h+TimeStr]
0x18002fb1b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002fb1f  inc     r8
0x18002fb22  cmp     [rax+r8*2], cx
0x18002fb27  jnz     short loc_18002FB1F
0x18002fb29  lea     rdx, [rbp+920h+TimeStr]
0x18002fb30  lea     rcx, [rbp+920h+lpValue]
0x18002fb34  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18002fb39  test    al, al
0x18002fb3b  jz      loc_18002FE3E
0x18002fb41  mov     [rsp+0A20h+var_9E8], 0
0x18002fb4a  lea     rax, [rbp+920h+var_9A0]
0x18002fb4e  mov     [rsp+0A20h+var_9B0], rax
0x18002fb53  lea     rax, [rbp+920h+var_9A0]
0x18002fb57  mov     [rsp+0A20h+var_9A8], rax
0x18002fb5c  xor     eax, eax
0x18002fb5e  mov     [rbp+920h+var_9A0], ax
0x18002fb62  lea     rax, [rsp+0A20h+var_9C0]
0x18002fb67  mov     [rsp+0A20h+var_9D0], rax
0x18002fb6c  lea     rax, [rsp+0A20h+var_9C0]
0x18002fb71  mov     [rsp+0A20h+var_9C8], rax
0x18002fb76  xor     eax, eax
0x18002fb78  mov     [rsp+0A20h+var_9C0], ax
0x18002fb7d  lea     r8, [rsp+0A20h+var_9B0]
0x18002fb82  mov     rdx, [rbp+920h+lpValue]
0x18002fb86  mov     rcx, [rbp+920h+var_950]
0x18002fb8a  call    ?GetLocalizedValue@WalletPackageProcessor@Wallet@@AEAAJPEBGAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Wallet::WalletPackageProcessor::GetLocalizedValue(ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x18002fb8f  test    eax, eax
0x18002fb91  js      loc_180030019
0x18002fb97  lea     r8, [rsp+0A20h+var_9D0]
0x18002fb9c  mov     rdx, [rbp+920h+var_8E0]
0x18002fba0  mov     rcx, [rbp+920h+var_950]
0x18002fba4  call    ?GetLocalizedValue@WalletPackageProcessor@Wallet@@AEAAJPEBGAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Wallet::WalletPackageProcessor::GetLocalizedValue(ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x18002fba9  test    eax, eax
0x18002fbab  js      loc_180030019
0x18002fbb1  mov     rdx, [rbp+920h+var_970]; unsigned __int16 *
0x18002fbb5  cmp     rdx, [rbp+920h+var_968]
0x18002fbb9  jnz     short loc_18002FBEC
0x18002fbbb  lea     rcx, [rbp+920h+sz]; lpsz
0x18002fbbf  call    ?CreateGuid@Utils@Wallet@@YAJPEAGI@Z; Wallet::Utils::CreateGuid(ushort *,uint)
0x18002fbc4  test    eax, eax
0x18002fbc6  js      loc_180030019
0x18002fbcc  lea     r8, [rbp+920h+sz]
0x18002fbd0  lea     rdx, aKeyS; "Key%s"
0x18002fbd7  lea     rcx, [rbp+920h+var_970]
0x18002fbdb  call    ??$assign_sprintf@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGZZ; tlx::assign_sprintf<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *,...)
0x18002fbe0  test    eax, eax
0x18002fbe2  js      loc_180030019
0x18002fbe8  mov     rdx, [rbp+920h+var_970]
0x18002fbec  mov     r9, [rsp+0A20h+var_9B0]
0x18002fbf1  mov     r8, [rsp+0A20h+var_9D0]
0x18002fbf6  mov     rcx, [rdi]
0x18002fbf9  test    ebx, ebx
0x18002fbfb  jz      short loc_18002FC07
0x18002fbfd  mov     [rsp+0A20h+var_A00], 2
0x18002fc05  jmp     short loc_18002FC0F
0x18002fc07  mov     [rsp+0A20h+var_A00], 8
0x18002fc0f  call    ?SetItemCustomProperty@Utils@Wallet@@YAJPEAUIWalletItem@@PEBG11W4__MIDL___MIDL_itf_iwalletcustomproperty_0000_0000_0001@@@Z; Wallet::Utils::SetItemCustomProperty(IWalletItem *,ushort const *,ushort const *,ushort const *,__MIDL___MIDL_itf_iwalletcustomproperty_0000_0000_0001)
0x18002fc14  test    eax, eax
0x18002fc16  js      loc_18002FCB7
0x18002fc1c  mov     rdi, [rdi]
0x18002fc1f  mov     rax, [rdi]
0x18002fc22  mov     rbx, [rax+58h]
0x18002fc26  lea     rcx, [rsp+0A20h+var_9E8]
0x18002fc2b  call    ??$pointerTo@UIWalletNotification@@@ce@@YAPEAPEAUIWalletNotification@@AEAV?$CComPtr@UIWalletNotification@@@ATL@@@Z; ce::pointerTo<IWalletNotification>(ATL::CComPtr<IWalletNotification> &)
0x18002fc30  mov     r8, rax
0x18002fc33  mov     rdx, [rbp+920h+var_970]
0x18002fc37  mov     rcx, rdi
0x18002fc3a  mov     rax, rbx
0x18002fc3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fc42  xor     ebx, ebx
0x18002fc44  test    eax, eax
0x18002fc46  js      short loc_18002FCC1
0x18002fc48  mov     rcx, [rsp+0A20h+var_9E8]
0x18002fc4d  mov     rax, [rcx]
0x18002fc50  mov     r9d, r14d
0x18002fc53  mov     r8d, r15d
0x18002fc56  xor     edx, edx
0x18002fc58  mov     rax, [rax+50h]
0x18002fc5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fc61  test    eax, eax
0x18002fc63  js      loc_180030019
0x18002fc69  mov     rcx, [rsp+0A20h+var_9E8]
0x18002fc6e  mov     r10, [rcx]
0x18002fc71  or      eax, 0FFFFFFFFh
0x18002fc74  sub     eax, r13d
0x18002fc77  neg     eax
0x18002fc79  sbb     r8d, r8d
0x18002fc7c  and     r8d, 20h
0x18002fc80  mov     r9d, r13d
0x18002fc83  lea     edx, [rbx+1]
0x18002fc86  mov     rax, [r10+50h]
0x18002fc8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fc8f  test    eax, eax
0x18002fc91  js      loc_180030019
0x18002fc97  mov     rdi, [rbp+920h+var_948]
0x18002fc9b  mov     rcx, [rdi]
0x18002fc9e  mov     rax, [rcx]
0x18002fca1  mov     r8, [rsp+0A20h+var_9E8]
0x18002fca6  mov     rdx, [rbp+920h+var_970]
0x18002fcaa  mov     rax, [rax+60h]
0x18002fcae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fcb3  test    eax, eax
0x18002fcb5  jns     short loc_18002FCC5
0x18002fcb7  mov     esi, 803A0063h
0x18002fcbc  jmp     loc_18003001B
0x18002fcc1  mov     rdi, [rbp+920h+var_948]
0x18002fcc5  lea     rcx, [rsp+0A20h+var_9D0]
0x18002fcca  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18002fccf  nop
0x18002fcd0  lea     rcx, [rsp+0A20h+var_9B0]
0x18002fcd5  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18002fcda  nop
0x18002fcdb  lea     rcx, [rsp+0A20h+var_9E8]
0x18002fce0  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x18002fce5  mov     rcx, [rbp+920h+var_970]
0x18002fce9  mov     [rbp+920h+var_968], rcx
0x18002fced  mov     [rcx], bx
0x18002fcf0  mov     rcx, [rbp+920h+var_8E0]
0x18002fcf4  mov     [rbp+920h+var_8D8], rcx
0x18002fcf8  mov     [rcx], bx
0x18002fcfb  mov     rcx, [rbp+920h+lpValue]
0x18002fcff  mov     [rbp+920h+var_988], rcx
0x18002fd03  mov     [rcx], bx
0x18002fd06  mov     rcx, [rbp+920h+var_900]
0x18002fd0a  mov     [rbp+920h+var_8F8], rcx
0x18002fd0e  mov     [rcx], bx
0x18002fd11  mov     rcx, [rbp+920h+var_920]
0x18002fd15  mov     [rbp+920h+var_918], rcx
  ... truncated ...
```
