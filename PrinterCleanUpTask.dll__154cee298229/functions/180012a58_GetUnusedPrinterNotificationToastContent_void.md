# GetUnusedPrinterNotificationToastContent(void)

- ea: `0x180012a58`
- end: `0x180012be8`
- name: `?GetUnusedPrinterNotificationToastContent@@YA?AUXmlDocument@Dom@Xml@Data@Windows@winrt@@XZ`
- size: `400`
- prototype: `volatile signed __int32 *__fastcall(volatile signed __int32 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180012f8c`

## callees

- `0x180002020`
- `0x180002b78`
- `0x1800051e0`
- `0x18000670c`
- `0x180007118`
- `0x180009c84`
- `0x18000a300`
- `0x18000cab8`
- `0x18000da60`
- `0x18000f0d0`
- `0x18000f26c`
- `0x180012a58`

## string_xrefs

- `0x180012b20`: ` <toast activationType="protocol" launch="ms-settings:printers">     <visual>         <binding template="ToastGeneric">             <text hint-maxLines="2">%s</text>         </binding>     </visual>     <actions>         <action activationType="protocol" arguments="ms-settings:printers" content="%s"/>         <action activationType="system" arguments="snooze" content="%s" />         <action activationType="system" arguments="dismiss" content="%s"/>     </actions> </toast> `
- `0x180012b43`: `printscan\print\shared\printercleanuptask\lib\printercleanuputil.cpp`

## pseudocode

```c
volatile signed __int32 *__fastcall GetUnusedPrinterNotificationToastContent(volatile signed __int32 *a1)
{
  int v2; // ebx
  __int64 v3; // rax
  int v4; // eax
  volatile signed __int32 *v6[2]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v7[4]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v8[32]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v9[32]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v10[40]; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 v11[1024]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+908h] [rbp+808h]

  v6[1] = a1;
  memset_0(v11, 0, sizeof(v11));
  GetResourceString((__int64)v7, 0x66u);
  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  GetResourceString((__int64)v10, 0x65u);
  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  GetResourceString((__int64)v9, 0x64u);
  v2 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  GetResourceString((__int64)v8, 0x67u);
  v3 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  v4 = StringCchPrintfW(
         v11,
         0x400u,
         L" <toast activationType=\"protocol\" launch=\"ms-settings:printers\">     <visual>         <binding template=\"T"
          "oastGeneric\">             <text hint-maxLines=\"2\">%s</text>         </binding>     </visual>     <actions> "
          "        <action activationType=\"protocol\" arguments=\"ms-settings:printers\" content=\"%s\"/>         <actio"
          "n activationType=\"system\" arguments=\"snooze\" content=\"%s\" />         <action activationType=\"system\" a"
          "rguments=\"dismiss\" content=\"%s\"/>     </actions> </toast> ",
         v3);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x52,
      (int)"printscan\\print\\shared\\printercleanuptask\\lib\\printercleanuputil.cpp",
      (const char *)(unsigned int)v4,
      v2);
  std::wstring::_Tidy_deallocate((__int64)v8);
  std::wstring::_Tidy_deallocate((__int64)v9);
  std::wstring::_Tidy_deallocate((__int64)v10);
  std::wstring::_Tidy_deallocate((__int64)v7);
  winrt::Windows::Data::Xml::Dom::XmlDocument::XmlDocument((struct IUnknown *)a1);
  v7[0] = *(_QWORD *)winrt::hstring::hstring((winrt::hstring *)v6, v11);
  winrt::impl::consume_Windows_Data_Xml_Dom_IXmlDocumentIO<winrt::Windows::Data::Xml::Dom::XmlDocument>::LoadXml(a1, v7);
  winrt::handle_type<winrt::impl::hstring_traits>::close(v6);
  return a1;
}

```

## disassembly

```asm
0x180012a58  mov     [rsp-8+arg_8], rbx
0x180012a5d  mov     [rsp-8+arg_10], rsi
0x180012a62  push    rbp
0x180012a63  push    rdi
0x180012a64  push    r14
0x180012a66  lea     rbp, [rsp-7F0h]
0x180012a6e  sub     rsp, 8F0h
0x180012a75  mov     rax, cs:__security_cookie
0x180012a7c  xor     rax, rsp
0x180012a7f  mov     [rbp+800h+var_20], rax
0x180012a86  mov     r14, rcx
0x180012a89  mov     [rsp+900h+var_8B0], rcx
0x180012a8e  mov     [rsp+900h+var_8C0], 0
0x180012a96  xor     edx, edx; Val
0x180012a98  mov     r8d, 800h; Size
0x180012a9e  lea     rcx, [rbp+800h+var_820]; void *
0x180012aa2  call    memset_0
0x180012aa7  mov     edx, 66h ; 'f'
0x180012aac  lea     rcx, [rsp+900h+var_8A8]
0x180012ab1  call    ?GetResourceString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; GetResourceString(uint)
0x180012ab6  nop
0x180012ab7  mov     rcx, rax
0x180012aba  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180012abf  mov     rsi, rax
0x180012ac2  mov     edx, 65h ; 'e'
0x180012ac7  lea     rcx, [rbp+800h+var_848]
0x180012acb  call    ?GetResourceString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; GetResourceString(uint)
0x180012ad0  nop
0x180012ad1  mov     rcx, rax
0x180012ad4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180012ad9  mov     rdi, rax
0x180012adc  mov     edx, 64h ; 'd'
0x180012ae1  lea     rcx, [rbp+800h+var_868]
0x180012ae5  call    ?GetResourceString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; GetResourceString(uint)
0x180012aea  nop
0x180012aeb  mov     rcx, rax
0x180012aee  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180012af3  mov     rbx, rax
0x180012af6  mov     edx, 67h ; 'g'
0x180012afb  lea     rcx, [rsp+900h+var_888]
0x180012b00  call    ?GetResourceString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; GetResourceString(uint)
0x180012b05  nop
0x180012b06  mov     rcx, rax
0x180012b09  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180012b0e  mov     [rsp+900h+var_8D0], rsi
0x180012b13  mov     [rsp+900h+var_8D8], rdi
0x180012b18  mov     qword ptr [rsp+900h+var_8E0], rbx; int
0x180012b1d  mov     r9, rax
0x180012b20  lea     r8, aToastActivatio_0; " <toast activationType=\"protocol\" lau"...
0x180012b27  mov     edx, 400h; unsigned __int64
0x180012b2c  lea     rcx, [rbp+800h+var_820]; unsigned __int16 *
0x180012b30  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012b35  mov     rcx, [rbp+808h]; this
0x180012b3c  test    eax, eax
0x180012b3e  jns     short loc_180012B55
0x180012b40  mov     r9d, eax; char *
0x180012b43  lea     r8, aPrintscanPrint_1; "printscan\\print\\shared\\printercleanu"...
0x180012b4a  mov     edx, 52h ; 'R'; void *
0x180012b4f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180012b55  lea     rcx, [rsp+900h+var_888]
0x180012b5a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180012b5f  nop
0x180012b60  lea     rcx, [rbp+800h+var_868]
0x180012b64  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180012b69  nop
0x180012b6a  lea     rcx, [rbp+800h+var_848]
0x180012b6e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180012b73  nop
0x180012b74  lea     rcx, [rsp+900h+var_8A8]
0x180012b79  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180012b7e  mov     rcx, r14; this
0x180012b81  call    ??0XmlDocument@Dom@Xml@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Xml::Dom::XmlDocument::XmlDocument(void)
0x180012b86  mov     [rsp+900h+var_8C0], 1
0x180012b8e  lea     rdx, [rbp+800h+var_820]; unsigned __int16 *
0x180012b92  lea     rcx, [rsp+900h+var_8B8]; this
0x180012b97  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x180012b9c  nop
0x180012b9d  mov     rcx, [rax]
0x180012ba0  mov     [rsp+900h+var_8A8], rcx
0x180012ba5  lea     rdx, [rsp+900h+var_8A8]
0x180012baa  mov     rcx, r14
0x180012bad  call    ?LoadXml@?$consume_Windows_Data_Xml_Dom_IXmlDocumentIO@UXmlDocument@Dom@Xml@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Xml_Dom_IXmlDocumentIO<winrt::Windows::Data::Xml::Dom::XmlDocument>::LoadXml(winrt::param::hstring const &)
0x180012bb2  nop
0x180012bb3  lea     rcx, [rsp+900h+var_8B8]
0x180012bb8  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180012bbd  mov     rax, r14
0x180012bc0  mov     rcx, [rbp+800h+var_20]
0x180012bc7  xor     rcx, rsp; StackCookie
0x180012bca  call    __security_check_cookie
0x180012bcf  lea     r11, [rsp+900h+var_10]
0x180012bd7  mov     rbx, [r11+28h]
0x180012bdb  mov     rsi, [r11+30h]
0x180012bdf  mov     rsp, r11
0x180012be2  pop     r14
0x180012be4  pop     rdi
0x180012be5  pop     rbp
0x180012be6  retn
```
