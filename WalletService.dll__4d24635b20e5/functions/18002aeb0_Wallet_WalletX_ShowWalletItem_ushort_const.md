# Wallet::WalletX::ShowWalletItem(ushort const *)

- ea: `0x18002aeb0`
- end: `0x18002b021`
- name: `?ShowWalletItem@WalletX@Wallet@@UEAAJPEBG@Z`
- size: `369`
- prototype: `__int64 __fastcall(Wallet::WalletX *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180003ae4`
- `0x1800043b8`
- `0x18000ac74`
- `0x18000acac`
- `0x18000d8d8`
- `0x180013f78`
- `0x18002aeb0`
- `0x1800375ec`
- `0x180043090`
- `0x180043150`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-url-l1-1-0!UrlEscapeW` at `0x18002af8a`
- `api-ms-win-core-url-l1-1-0!UrlEscapeW` at `0x18002af8a`
- `ext-ms-onecore-shellchromeapi-l1-1-0!Shell_LaunchSessionByUriEx` at `0x18002afbe`
- `ext-ms-onecore-shellchromeapi-l1-1-0!Shell_LaunchSessionByUriEx` at `0x18002afbe`

## pseudocode

```c
__int64 __fastcall Wallet::WalletX::ShowWalletItem(Wallet::WalletX *this, const unsigned __int16 *a2)
{
  __int64 (__fastcall *v4)(Wallet::WalletX *, const unsigned __int16 *, __int64); // rbx
  __int64 v5; // rax
  HRESULT v6; // ebx
  int v7; // eax
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 pcchEscaped; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v13; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v14; // [rsp+30h] [rbp-D0h] BYREF
  PCWSTR pszUrl[5]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 v16[2088]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR pszEscaped[2088]; // [rsp+10B0h] [rbp+FB0h] BYREF

  LODWORD(pcchEscaped) = 2084;
  v13 = 0;
  v14 = 0;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(pszUrl);
  if ( a2 && *a2 )
  {
    v4 = *(__int64 (__fastcall **)(Wallet::WalletX *, const unsigned __int16 *, __int64))(*(_QWORD *)this + 40LL);
    v5 = ce::pointerTo<IWalletNotification>(&v13);
    v6 = v4(this, a2, v5);
    if ( v6 < 0 )
      goto LABEL_10;
    v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v13 + 24LL))(v13, &v14);
    if ( v6 < 0 )
      goto LABEL_10;
    Wallet::Utils::ConvertItemIdToString(&v14, pszUrl);
    v6 = UrlEscapeW(pszUrl[0], pszEscaped, (DWORD *)&pcchEscaped, 0x42000u);
    if ( v6 < 0 )
      goto LABEL_10;
    v7 = StringCchPrintfW(v16, 0x824u, L"ms-wallet:ShowItem?Id=%s", pszEscaped, pcchEscaped);
  }
  else
  {
    v7 = StringCchCopyW(v16, 0x824u, L"ms-wallet:");
  }
  v6 = v7;
  if ( v7 >= 0 )
  {
    v8 = Shell_LaunchSessionByUriEx(v16);
    v6 = 0;
    if ( v8 < 0 )
      v6 = v8;
  }
LABEL_10:
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(pszUrl);
  ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(&v13, v9, v10);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002aeb0  mov     [rsp-8+arg_10], rbx
0x18002aeb5  mov     [rsp-8+arg_18], rsi
0x18002aeba  push    rbp
0x18002aebb  push    rdi
0x18002aebc  push    r14
0x18002aebe  lea     rbp, [rsp-2010h]
0x18002aec6  mov     eax, 2110h
0x18002aecb  call    _alloca_probe
0x18002aed0  sub     rsp, rax
0x18002aed3  mov     rax, cs:__security_cookie
0x18002aeda  xor     rax, rsp
0x18002aedd  mov     [rbp+2020h+var_20], rax
0x18002aee4  xor     r14d, r14d
0x18002aee7  mov     dword ptr [rsp+2120h+pcchEscaped], 824h
0x18002aeef  mov     rsi, rcx
0x18002aef2  mov     [rsp+2120h+var_20F8], r14
0x18002aef7  lea     rcx, [rsp+2120h+pszUrl]
0x18002aefc  mov     [rsp+2120h+var_20F0], r14
0x18002af01  mov     rdi, rdx
0x18002af04  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18002af09  test    rdi, rdi
0x18002af0c  jz      loc_18002B009
0x18002af12  cmp     [rdi], r14w
0x18002af16  jz      loc_18002B009
0x18002af1c  mov     rax, [rsi]
0x18002af1f  lea     rcx, [rsp+2120h+var_20F8]
0x18002af24  mov     rbx, [rax+28h]
0x18002af28  call    ??$pointerTo@UIWalletNotification@@@ce@@YAPEAPEAUIWalletNotification@@AEAV?$CComPtr@UIWalletNotification@@@ATL@@@Z; ce::pointerTo<IWalletNotification>(ATL::CComPtr<IWalletNotification> &)
0x18002af2d  mov     r8, rax
0x18002af30  mov     rdx, rdi
0x18002af33  mov     rax, rbx
0x18002af36  mov     rcx, rsi
0x18002af39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002af3e  mov     ebx, eax
0x18002af40  test    eax, eax
0x18002af42  js      loc_18002AFCC
0x18002af48  mov     rcx, [rsp+2120h+var_20F8]
0x18002af4d  lea     rdx, [rsp+2120h+var_20F0]
0x18002af52  mov     rax, [rcx]
0x18002af55  mov     rax, [rax+18h]
0x18002af59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002af5e  mov     ebx, eax
0x18002af60  test    eax, eax
0x18002af62  js      short loc_18002AFCC
0x18002af64  lea     rdx, [rsp+2120h+pszUrl]
0x18002af69  lea     rcx, [rsp+2120h+var_20F0]
0x18002af6e  call    ?ConvertItemIdToString@Utils@Wallet@@YAJAEB_KAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Wallet::Utils::ConvertItemIdToString(unsigned __int64 const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x18002af73  mov     rcx, [rsp+2120h+pszUrl]; pszUrl
0x18002af78  lea     r8, [rsp+2120h+pcchEscaped]; pcchEscaped
0x18002af7d  mov     r9d, 42000h; dwFlags
0x18002af83  lea     rdx, [rbp+2020h+pszEscaped]; pszEscaped
0x18002af8a  call    cs:__imp_UrlEscapeW
0x18002af90  mov     ebx, eax
0x18002af92  test    eax, eax
0x18002af94  js      short loc_18002AFCC
0x18002af96  lea     r9, [rbp+2020h+pszEscaped]
0x18002af9d  mov     edx, 824h; unsigned __int64
0x18002afa2  lea     r8, aMsWalletShowit; "ms-wallet:ShowItem?Id=%s"
0x18002afa9  lea     rcx, [rsp+2120h+var_20C0]; unsigned __int16 *
0x18002afae  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002afb3  mov     ebx, eax
0x18002afb5  test    eax, eax
0x18002afb7  js      short loc_18002AFCC
0x18002afb9  lea     rcx, [rsp+2120h+var_20C0]
0x18002afbe  call    cs:__imp_Shell_LaunchSessionByUriEx
0x18002afc4  test    eax, eax
0x18002afc6  mov     ebx, r14d
0x18002afc9  cmovs   ebx, eax
0x18002afcc  lea     rcx, [rsp+2120h+pszUrl]
0x18002afd1  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18002afd6  lea     rcx, [rsp+2120h+var_20F8]
0x18002afdb  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x18002afe0  mov     eax, ebx
0x18002afe2  mov     rcx, [rbp+2020h+var_20]
0x18002afe9  xor     rcx, rsp; StackCookie
0x18002afec  call    __security_check_cookie
0x18002aff1  lea     r11, [rsp+2120h+var_10]
0x18002aff9  mov     rbx, [r11+30h]
0x18002affd  mov     rsi, [r11+38h]
0x18002b001  mov     rsp, r11
0x18002b004  pop     r14
0x18002b006  pop     rdi
0x18002b007  pop     rbp
0x18002b008  retn
0x18002b009  lea     r8, aMsWallet; "ms-wallet:"
0x18002b010  mov     edx, 824h; unsigned __int64
0x18002b015  lea     rcx, [rsp+2120h+var_20C0]; unsigned __int16 *
0x18002b01a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002b01f  jmp     short loc_18002AFB3
```
