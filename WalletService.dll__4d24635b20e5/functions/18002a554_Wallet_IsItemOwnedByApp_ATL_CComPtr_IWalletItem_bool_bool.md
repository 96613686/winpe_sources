# Wallet::IsItemOwnedByApp(ATL::CComPtr<IWalletItem> &,bool &,bool &)

- ea: `0x18002a554`
- end: `0x18002a654`
- name: `?IsItemOwnedByApp@Wallet@@YAJAEAV?$CComPtr@UIWalletItem@@@ATL@@AEA_N1@Z`
- size: `256`
- prototype: `__int64 __fastcall(__int64, _BYTE *)`
- caller_count: `11`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180029890`
- `0x180029fd0`
- `0x18002a370`
- `0x18002a47c`
- `0x18002a65c`
- `0x18002b590`
- `0x18002b8a0`
- `0x18002bab0`
- `0x18002bdc0`
- `0x18002bef0`
- `0x18002c9f0`

## callees

- `0x180003ae4`
- `0x18000d8d8`
- `0x180013f78`
- `0x18001cdf8`
- `0x180029ebc`
- `0x18002a554`
- `0x180036c58`
- `0x180039628`
- `0x18003991c`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002a603`
- `msvcrt!_wcsicmp` at `0x18002a615`
- `msvcrt!_wcsicmp` at `0x18002a603`
- `msvcrt!_wcsicmp` at `0x18002a615`

## pseudocode

```c
__int64 __fastcall Wallet::IsItemOwnedByApp(__int64 a1, _BYTE *a2)
{
  Wallet::Utils *v4; // r8
  bool *v5; // rdx
  int IsSystemApp; // ebx
  int RealWalletItem; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  wchar_t *String1[4]; // [rsp+20h] [rbp-29h] BYREF
  wchar_t *v12[4]; // [rsp+40h] [rbp-9h] BYREF
  wchar_t *String2[8]; // [rsp+60h] [rbp+17h] BYREF
  __int64 v14; // [rsp+B8h] [rbp+6Fh] BYREF

  LOBYTE(v14) = 0;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(String1);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(String2);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v12);
  *a2 = 0;
  *(_BYTE *)v4 = 0;
  IsSystemApp = Wallet::Utils::IsSystemApp(v4, v5);
  if ( IsSystemApp >= 0 )
  {
    IsSystemApp = Wallet::Utils::IsItemLinkedToApp(a1, &v14);
    if ( IsSystemApp >= 0 )
    {
      IsSystemApp = 0;
      if ( (_BYTE)v14 )
      {
        v14 = 0;
        RealWalletItem = Wallet::GetRealWalletItem(a1, &v14);
        if ( RealWalletItem < 0
          || (RealWalletItem = Wallet::ServerUtils::GetCallerId(String2, v12), RealWalletItem < 0)
          || (RealWalletItem = Wallet::Utils::GetTStringProperty<IWalletItem,enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>(
                                 v14,
                                 3000,
                                 String1),
              RealWalletItem < 0) )
        {
          IsSystemApp = RealWalletItem;
        }
        else if ( !_wcsicmp(String1[0], String2[0]) || !_wcsicmp(String1[0], v12[0]) )
        {
          *a2 = 1;
        }
        ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(&v14, v8, v9);
      }
    }
  }
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v12);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(String2);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(String1);
  return (unsigned int)IsSystemApp;
}

```

## disassembly

```asm
0x18002a554  push    rbp
0x18002a556  push    rbx
0x18002a557  push    rsi
0x18002a558  push    rdi
0x18002a559  lea     rbp, [rsp-3Fh]
0x18002a55e  sub     rsp, 88h
0x18002a565  mov     rdi, rcx
0x18002a568  mov     byte ptr [rbp+57h+arg_8], 0
0x18002a56c  lea     rcx, [rbp+57h+String1]
0x18002a570  mov     rsi, rdx
0x18002a573  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18002a578  lea     rcx, [rbp+57h+String2]
0x18002a57c  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18002a581  lea     rcx, [rbp+57h+var_60]
0x18002a585  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18002a58a  mov     rcx, r8; this
0x18002a58d  mov     byte ptr [rsi], 0
0x18002a590  mov     byte ptr [r8], 0
0x18002a594  call    ?IsSystemApp@Utils@Wallet@@YAJAEA_N@Z; Wallet::Utils::IsSystemApp(bool &)
0x18002a599  mov     ebx, eax
0x18002a59b  test    eax, eax
0x18002a59d  js      loc_18002A62B
0x18002a5a3  lea     rdx, [rbp+57h+arg_8]
0x18002a5a7  mov     rcx, rdi
0x18002a5aa  call    ?IsItemLinkedToApp@Utils@Wallet@@YAJAEAV?$CComPtr@UIWalletItem@@@ATL@@AEA_N@Z; Wallet::Utils::IsItemLinkedToApp(ATL::CComPtr<IWalletItem> &,bool &)
0x18002a5af  mov     ebx, eax
0x18002a5b1  test    eax, eax
0x18002a5b3  js      short loc_18002A62B
0x18002a5b5  xor     ebx, ebx
0x18002a5b7  cmp     byte ptr [rbp+57h+arg_8], bl
0x18002a5ba  jz      short loc_18002A62B
0x18002a5bc  lea     rdx, [rbp+57h+arg_8]
0x18002a5c0  mov     [rbp+57h+arg_8], rbx
0x18002a5c4  mov     rcx, rdi
0x18002a5c7  call    ?GetRealWalletItem@Wallet@@YAJAEAV?$CComPtr@UIWalletItem@@@ATL@@0@Z; Wallet::GetRealWalletItem(ATL::CComPtr<IWalletItem> &,ATL::CComPtr<IWalletItem> &)
0x18002a5cc  test    eax, eax
0x18002a5ce  jns     short loc_18002A5D4
0x18002a5d0  mov     ebx, eax
0x18002a5d2  jmp     short loc_18002A622
0x18002a5d4  lea     rdx, [rbp+57h+var_60]
0x18002a5d8  lea     rcx, [rbp+57h+String2]
0x18002a5dc  call    ?GetCallerId@ServerUtils@Wallet@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@0@Z; Wallet::ServerUtils::GetCallerId(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x18002a5e1  test    eax, eax
0x18002a5e3  js      short loc_18002A5D0
0x18002a5e5  mov     rcx, [rbp+57h+arg_8]
0x18002a5e9  lea     r8, [rbp+57h+String1]
0x18002a5ed  mov     edx, 0BB8h
0x18002a5f2  call    ??$GetTStringProperty@UIWalletItem@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@Utils@Wallet@@YAJPEAUIWalletItem@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Wallet::Utils::GetTStringProperty<IWalletItem,__MIDL___MIDL_itf_wallettypes_0000_0000_0010>(IWalletItem *,__MIDL___MIDL_itf_wallettypes_0000_0000_0010,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x18002a5f7  test    eax, eax
0x18002a5f9  js      short loc_18002A5D0
0x18002a5fb  mov     rdx, [rbp+57h+String2]; String2
0x18002a5ff  mov     rcx, [rbp+57h+String1]; String1
0x18002a603  call    cs:__imp__wcsicmp
0x18002a609  test    eax, eax
0x18002a60b  jz      short loc_18002A61F
0x18002a60d  mov     rdx, [rbp+57h+var_60]; String2
0x18002a611  mov     rcx, [rbp+57h+String1]; String1
0x18002a615  call    cs:__imp__wcsicmp
0x18002a61b  test    eax, eax
0x18002a61d  jnz     short loc_18002A622
0x18002a61f  mov     byte ptr [rsi], 1
0x18002a622  lea     rcx, [rbp+57h+arg_8]
0x18002a626  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x18002a62b  lea     rcx, [rbp+57h+var_60]
0x18002a62f  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18002a634  lea     rcx, [rbp+57h+String2]
0x18002a638  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18002a63d  lea     rcx, [rbp+57h+String1]
0x18002a641  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18002a646  mov     eax, ebx
0x18002a648  add     rsp, 88h
0x18002a64f  pop     rdi
0x18002a650  pop     rsi
0x18002a651  pop     rbx
0x18002a652  pop     rbp
0x18002a653  retn
```
