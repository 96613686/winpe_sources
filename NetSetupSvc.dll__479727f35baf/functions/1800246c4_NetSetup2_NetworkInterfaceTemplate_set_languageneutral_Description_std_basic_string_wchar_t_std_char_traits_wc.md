# NetSetup2::NetworkInterfaceTemplate::set_languageneutral_Description(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x1800246c4`
- end: `0x18002474f`
- name: `?set_languageneutral_Description@NetworkInterfaceTemplate@NetSetup2@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `139`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180021650`

## callees

- `0x1800027c0`
- `0x18000d954`
- `0x18000d974`
- `0x18001d294`
- `0x18002b328`
- `0x18002d560`

## pseudocode

```c
void __fastcall NetSetup2::NetworkInterfaceTemplate::set_languageneutral_Description(__int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // r10
  __int64 v4; // r9
  _BYTE v5[20]; // [rsp+20h] [rbp-48h] BYREF
  int v6; // [rsp+34h] [rbp-34h]
  _BYTE v7[24]; // [rsp+38h] [rbp-30h] BYREF

  NetSetup2::Property::Property(
    (NetSetup2::Property *)v5,
    (const struct _NETSETUPPROPKEY *)NETSETUPPKEY_Driver_Description);
  v6 = 25;
  std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  v2 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  std::vector<unsigned char>::assign<unsigned char const *,0>(v7, v4, v2 + 2 * (*(_QWORD *)(v3 + 16) + 1LL));
  NetSetup2::ObjectCreationTemplate::SetProperty(a1, v5);
  std::vector<unsigned char>::_Tidy((__int64)v7);
}

```

## disassembly

```asm
0x1800246c4  push    rbx
0x1800246c6  sub     rsp, 60h
0x1800246ca  mov     rax, cs:__security_cookie
0x1800246d1  xor     rax, rsp
0x1800246d4  mov     [rsp+68h+var_18], rax
0x1800246d9  mov     r10, rdx
0x1800246dc  mov     rbx, rcx
0x1800246df  lea     rdx, NETSETUPPKEY_Driver_Description; struct _NETSETUPPROPKEY *
0x1800246e6  lea     rcx, [rsp+68h+var_48]; this
0x1800246eb  call    ??0Property@NetSetup2@@QEAA@AEBU_NETSETUPPROPKEY@@@Z; NetSetup2::Property::Property(_NETSETUPPROPKEY const &)
0x1800246f0  nop
0x1800246f1  mov     [rsp+68h+var_34], 19h
0x1800246f9  mov     rcx, r10
0x1800246fc  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180024701  mov     r9, rax
0x180024704  mov     rcx, r10
0x180024707  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002470c  mov     rdx, [r10+10h]
0x180024710  inc     rdx
0x180024713  lea     r8, [rax+rdx*2]
0x180024717  mov     rdx, r9
0x18002471a  lea     rcx, [rsp+68h+var_30]
0x18002471f  call    ??$assign@PEBE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAAXPEBE0@Z; std::vector<uchar>::assign<uchar const *,0>(uchar const *,uchar const *)
0x180024724  lea     rdx, [rsp+68h+var_48]
0x180024729  mov     rcx, rbx
0x18002472c  call    ?SetProperty@ObjectCreationTemplate@NetSetup2@@QEAAX$$QEAVProperty@2@@Z; NetSetup2::ObjectCreationTemplate::SetProperty(NetSetup2::Property &&)
0x180024731  nop
0x180024732  lea     rcx, [rsp+68h+var_30]
0x180024737  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18002473c  mov     rcx, [rsp+68h+var_18]
0x180024741  xor     rcx, rsp; StackCookie
0x180024744  call    __security_check_cookie
0x180024749  add     rsp, 60h
0x18002474d  pop     rbx
0x18002474e  retn
```
