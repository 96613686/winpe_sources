# GetUnusedPrinterActionCenterNotificationToastContent(void)

- ea: `0x180012918`
- end: `0x180012a50`
- name: `?GetUnusedPrinterActionCenterNotificationToastContent@@YA?AUXmlDocument@Dom@Xml@Data@Windows@winrt@@XZ`
- size: `312`
- prototype: `volatile signed __int32 *__fastcall(volatile signed __int32 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180011a10`

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
- `0x180012918`

## string_xrefs

- `0x18001299f`: ` <toast activationType="protocol" launch="ms-settings:printers">     <visual>         <binding template="ToastGeneric">             <text hint-maxLines="2">%s</text>         </binding>     </visual>     <actions>         <action activationType="protocol" arguments="ms-settings:printers" content="%s"/>     </actions> </toast> `
- `0x1800129c2`: `printscan\print\shared\printercleanuptask\lib\printercleanuputil.cpp`

## pseudocode

```c
volatile signed __int32 *__fastcall GetUnusedPrinterActionCenterNotificationToastContent(volatile signed __int32 *a1)
{
  int v2; // ebx
  __int64 v3; // rax
  int v4; // eax
  volatile signed __int32 *v6[2]; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v7[4]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v8[40]; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 v9[1024]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+8A8h] [rbp+7A8h]

  v6[1] = a1;
  memset_0(v9, 0, sizeof(v9));
  GetResourceString((__int64)v7, 0x64u);
  v2 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  GetResourceString((__int64)v8, 0x67u);
  v3 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  v4 = StringCchPrintfW(
         v9,
         0x400u,
         L" <toast activationType=\"protocol\" launch=\"ms-settings:printers\">     <visual>         <binding template=\"T"
          "oastGeneric\">             <text hint-maxLines=\"2\">%s</text>         </binding>     </visual>     <actions> "
          "        <action activationType=\"protocol\" arguments=\"ms-settings:printers\" content=\"%s\"/>     </actions> </toast> ",
         v3);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x60,
      (int)"printscan\\print\\shared\\printercleanuptask\\lib\\printercleanuputil.cpp",
      (const char *)(unsigned int)v4,
      v2);
  std::wstring::_Tidy_deallocate((__int64)v8);
  std::wstring::_Tidy_deallocate((__int64)v7);
  winrt::Windows::Data::Xml::Dom::XmlDocument::XmlDocument((struct IUnknown *)a1);
  v7[0] = *(_QWORD *)winrt::hstring::hstring((winrt::hstring *)v6, v9);
  winrt::impl::consume_Windows_Data_Xml_Dom_IXmlDocumentIO<winrt::Windows::Data::Xml::Dom::XmlDocument>::LoadXml(a1, v7);
  winrt::handle_type<winrt::impl::hstring_traits>::close(v6);
  return a1;
}

```

## disassembly

```asm
0x180012918  mov     [rsp-8+arg_8], rbx
0x18001291d  mov     [rsp-8+arg_10], rdi
0x180012922  push    rbp
0x180012923  lea     rbp, [rsp-7A0h]
0x18001292b  sub     rsp, 8A0h
0x180012932  mov     rax, cs:__security_cookie
0x180012939  xor     rax, rsp
0x18001293c  mov     [rbp+7A0h+var_10], rax
0x180012943  mov     rdi, rcx
0x180012946  mov     [rsp+8A0h+var_860], rcx
0x18001294b  mov     [rsp+8A0h+var_870], 0
0x180012953  xor     edx, edx; Val
0x180012955  mov     r8d, 800h; Size
0x18001295b  lea     rcx, [rbp+7A0h+var_810]; void *
0x18001295f  call    memset_0
0x180012964  mov     edx, 64h ; 'd'
0x180012969  lea     rcx, [rsp+8A0h+var_858]
0x18001296e  call    ?GetResourceString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; GetResourceString(uint)
0x180012973  nop
0x180012974  mov     rcx, rax
0x180012977  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001297c  mov     rbx, rax
0x18001297f  mov     edx, 67h ; 'g'
0x180012984  lea     rcx, [rsp+8A0h+var_838]
0x180012989  call    ?GetResourceString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; GetResourceString(uint)
0x18001298e  nop
0x18001298f  mov     rcx, rax
0x180012992  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180012997  mov     qword ptr [rsp+8A0h+var_880], rbx; int
0x18001299c  mov     r9, rax
0x18001299f  lea     r8, aToastActivatio; " <toast activationType=\"protocol\" lau"...
0x1800129a6  mov     edx, 400h; unsigned __int64
0x1800129ab  lea     rcx, [rbp+7A0h+var_810]; unsigned __int16 *
0x1800129af  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800129b4  mov     rcx, [rbp+7A8h]; this
0x1800129bb  test    eax, eax
0x1800129bd  jns     short loc_1800129D4
0x1800129bf  mov     r9d, eax; char *
0x1800129c2  lea     r8, aPrintscanPrint_1; "printscan\\print\\shared\\printercleanu"...
0x1800129c9  mov     edx, 60h ; '`'; void *
0x1800129ce  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800129d4  lea     rcx, [rsp+8A0h+var_838]
0x1800129d9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800129de  nop
0x1800129df  lea     rcx, [rsp+8A0h+var_858]
0x1800129e4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800129e9  mov     rcx, rdi; this
0x1800129ec  call    ??0XmlDocument@Dom@Xml@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Xml::Dom::XmlDocument::XmlDocument(void)
0x1800129f1  mov     [rsp+8A0h+var_870], 1
0x1800129f9  lea     rdx, [rbp+7A0h+var_810]; unsigned __int16 *
0x1800129fd  lea     rcx, [rsp+8A0h+var_868]; this
0x180012a02  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x180012a07  nop
0x180012a08  mov     rcx, [rax]
0x180012a0b  mov     [rsp+8A0h+var_858], rcx
0x180012a10  lea     rdx, [rsp+8A0h+var_858]
0x180012a15  mov     rcx, rdi
0x180012a18  call    ?LoadXml@?$consume_Windows_Data_Xml_Dom_IXmlDocumentIO@UXmlDocument@Dom@Xml@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Xml_Dom_IXmlDocumentIO<winrt::Windows::Data::Xml::Dom::XmlDocument>::LoadXml(winrt::param::hstring const &)
0x180012a1d  nop
0x180012a1e  lea     rcx, [rsp+8A0h+var_868]
0x180012a23  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180012a28  mov     rax, rdi
0x180012a2b  mov     rcx, [rbp+7A0h+var_10]
0x180012a32  xor     rcx, rsp; StackCookie
0x180012a35  call    __security_check_cookie
0x180012a3a  lea     r11, [rsp+8A0h+var_s0]
0x180012a42  mov     rbx, [r11+18h]
0x180012a46  mov     rdi, [r11+20h]
0x180012a4a  mov     rsp, r11
0x180012a4d  pop     rbp
0x180012a4e  retn
```
