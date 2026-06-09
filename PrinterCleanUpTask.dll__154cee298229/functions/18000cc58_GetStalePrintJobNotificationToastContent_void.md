# GetStalePrintJobNotificationToastContent(void)

- ea: `0x18000cc58`
- end: `0x18000ce04`
- name: `?GetStalePrintJobNotificationToastContent@@YA?AUXmlDocument@Dom@Xml@Data@Windows@winrt@@XZ`
- size: `428`
- prototype: `volatile signed __int32 *__fastcall(volatile signed __int32 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x18000d424`

## callees

- `0x180002020`
- `0x180002b78`
- `0x1800051e0`
- `0x18000670c`
- `0x180007118`
- `0x180009c84`
- `0x18000a300`
- `0x18000cab8`
- `0x18000cc58`
- `0x18000da60`
- `0x18000f0d0`
- `0x18000f26c`

## string_xrefs

- `0x18000cd3a`: ` <toast>     <visual>         <binding template="ToastGeneric">             <text>%s</text>             <text>%s</text>             <group>                 <subgroup id="DocumentNames" hint-weight="3">                     <text hint-style="baseSubtle">%s</text>                 </subgroup>                 <subgroup id="SubmissionDates" hint-weight="1">                     <text hint-style="baseSubtle" />                 </subgroup>             </group>         </binding>     </visual>     <action`
- `0x18000cd5d`: `printscan\print\shared\printercleanuptask\lib\printjobcleanuputil.cpp`

## pseudocode

```c
volatile signed __int32 *__fastcall GetStalePrintJobNotificationToastContent(volatile signed __int32 *a1)
{
  int v2; // ebx
  __int64 v3; // rax
  int v4; // eax
  volatile signed __int32 *v6[2]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v7[4]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v8[32]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v9[32]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v10[32]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v11[40]; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int16 v12[1024]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+948h] [rbp+848h]

  v6[1] = a1;
  memset_0(v12, 0, sizeof(v12));
  GetResourceString((__int64)v7, 0x65u);
  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  GetResourceString((__int64)v11, 0x69u);
  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  GetResourceString((__int64)v10, 0xC8u);
  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  GetResourceString((__int64)v9, 0xC9u);
  v2 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  GetResourceString((__int64)v8, 0xCAu);
  v3 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  v4 = StringCchPrintfW(
         v12,
         0x400u,
         L" <toast>     <visual>         <binding template=\"ToastGeneric\">             <text>%s</text>             <text"
          ">%s</text>             <group>                 <subgroup id=\"DocumentNames\" hint-weight=\"3\">              "
          "       <text hint-style=\"baseSubtle\">%s</text>                 </subgroup>                 <subgroup id=\"Su"
          "bmissionDates\" hint-weight=\"1\">                     <text hint-style=\"baseSubtle\" />                 </su"
          "bgroup>             </group>         </binding>     </visual>     <actions>         <action activationType=\"b"
          "ackground\" arguments=\"PrintJobCleanupTask/delete\" content=\"%s\" />         <action activationType=\"system"
          "\" arguments=\"dismiss\" content=\"%s\" />     </actions> </toast> ",
         v3);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x41,
      (int)"printscan\\print\\shared\\printercleanuptask\\lib\\printjobcleanuputil.cpp",
      (const char *)(unsigned int)v4,
      v2);
  std::wstring::_Tidy_deallocate((__int64)v8);
  std::wstring::_Tidy_deallocate((__int64)v9);
  std::wstring::_Tidy_deallocate((__int64)v10);
  std::wstring::_Tidy_deallocate((__int64)v11);
  std::wstring::_Tidy_deallocate((__int64)v7);
  winrt::Windows::Data::Xml::Dom::XmlDocument::XmlDocument((struct IUnknown *)a1);
  v7[0] = *(_QWORD *)winrt::hstring::hstring((winrt::hstring *)v6, v12);
  winrt::impl::consume_Windows_Data_Xml_Dom_IXmlDocumentIO<winrt::Windows::Data::Xml::Dom::XmlDocument>::LoadXml(a1, v7);
  winrt::handle_type<winrt::impl::hstring_traits>::close(v6);
  return a1;
}

```

## disassembly

```asm
0x18000cc58  push    rbp
0x18000cc5a  push    rbx
0x18000cc5b  push    rsi
0x18000cc5c  push    rdi
0x18000cc5d  push    r14
0x18000cc5f  push    r15
0x18000cc61  lea     rbp, [rsp-818h]
0x18000cc69  sub     rsp, 918h
0x18000cc70  mov     rax, cs:__security_cookie
0x18000cc77  xor     rax, rsp
0x18000cc7a  mov     [rbp+840h+var_40], rax
0x18000cc81  mov     r15, rcx
0x18000cc84  mov     [rsp+940h+var_8F0], rcx
0x18000cc89  mov     [rsp+940h+var_900], 0
0x18000cc91  xor     edx, edx; Val
0x18000cc93  mov     r8d, 800h; Size
0x18000cc99  lea     rcx, [rbp+840h+var_840]; void *
0x18000cc9d  call    memset_0
0x18000cca2  mov     edx, 65h ; 'e'
0x18000cca7  lea     rcx, [rsp+940h+var_8E8]
0x18000ccac  call    ?GetResourceString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; GetResourceString(uint)
0x18000ccb1  nop
0x18000ccb2  mov     rcx, rax
0x18000ccb5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000ccba  mov     r14, rax
0x18000ccbd  mov     edx, 69h ; 'i'
0x18000ccc2  lea     rcx, [rbp+840h+var_868]
0x18000ccc6  call    ?GetResourceString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; GetResourceString(uint)
0x18000cccb  nop
0x18000cccc  mov     rcx, rax
0x18000cccf  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000ccd4  mov     rsi, rax
0x18000ccd7  mov     edx, 0C8h
0x18000ccdc  lea     rcx, [rbp+840h+var_888]
0x18000cce0  call    ?GetResourceString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; GetResourceString(uint)
0x18000cce5  nop
0x18000cce6  mov     rcx, rax
0x18000cce9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000ccee  mov     rdi, rax
0x18000ccf1  mov     edx, 0C9h
0x18000ccf6  lea     rcx, [rbp+840h+var_8A8]
0x18000ccfa  call    ?GetResourceString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; GetResourceString(uint)
0x18000ccff  nop
0x18000cd00  mov     rcx, rax
0x18000cd03  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000cd08  mov     rbx, rax
0x18000cd0b  mov     edx, 0CAh
0x18000cd10  lea     rcx, [rsp+940h+var_8C8]
0x18000cd15  call    ?GetResourceString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; GetResourceString(uint)
0x18000cd1a  nop
0x18000cd1b  mov     rcx, rax
0x18000cd1e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000cd23  mov     [rsp+940h+var_908], r14
0x18000cd28  mov     [rsp+940h+var_910], rsi
0x18000cd2d  mov     [rsp+940h+var_918], rdi
0x18000cd32  mov     qword ptr [rsp+940h+var_920], rbx; int
0x18000cd37  mov     r9, rax
0x18000cd3a  lea     r8, aToastVisualBin; " <toast>     <visual>         <binding "...
0x18000cd41  mov     edx, 400h; unsigned __int64
0x18000cd46  lea     rcx, [rbp+840h+var_840]; unsigned __int16 *
0x18000cd4a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000cd4f  mov     rcx, [rbp+848h]; this
0x18000cd56  test    eax, eax
0x18000cd58  jns     short loc_18000CD6F
0x18000cd5a  mov     r9d, eax; char *
0x18000cd5d  lea     r8, aPrintscanPrint_4; "printscan\\print\\shared\\printercleanu"...
0x18000cd64  mov     edx, 41h ; 'A'; void *
0x18000cd69  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000cd6f  lea     rcx, [rsp+940h+var_8C8]
0x18000cd74  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000cd79  nop
0x18000cd7a  lea     rcx, [rbp+840h+var_8A8]
0x18000cd7e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000cd83  nop
0x18000cd84  lea     rcx, [rbp+840h+var_888]
0x18000cd88  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000cd8d  nop
0x18000cd8e  lea     rcx, [rbp+840h+var_868]
0x18000cd92  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000cd97  nop
0x18000cd98  lea     rcx, [rsp+940h+var_8E8]
0x18000cd9d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000cda2  mov     rcx, r15; this
0x18000cda5  call    ??0XmlDocument@Dom@Xml@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Xml::Dom::XmlDocument::XmlDocument(void)
0x18000cdaa  mov     [rsp+940h+var_900], 1
0x18000cdb2  lea     rdx, [rbp+840h+var_840]; unsigned __int16 *
0x18000cdb6  lea     rcx, [rsp+940h+var_8F8]; this
0x18000cdbb  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x18000cdc0  nop
0x18000cdc1  mov     rcx, [rax]
0x18000cdc4  mov     [rsp+940h+var_8E8], rcx
0x18000cdc9  lea     rdx, [rsp+940h+var_8E8]
0x18000cdce  mov     rcx, r15
0x18000cdd1  call    ?LoadXml@?$consume_Windows_Data_Xml_Dom_IXmlDocumentIO@UXmlDocument@Dom@Xml@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Xml_Dom_IXmlDocumentIO<winrt::Windows::Data::Xml::Dom::XmlDocument>::LoadXml(winrt::param::hstring const &)
0x18000cdd6  nop
0x18000cdd7  lea     rcx, [rsp+940h+var_8F8]
0x18000cddc  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18000cde1  mov     rax, r15
0x18000cde4  mov     rcx, [rbp+840h+var_40]
0x18000cdeb  xor     rcx, rsp; StackCookie
0x18000cdee  call    __security_check_cookie
0x18000cdf3  add     rsp, 918h
0x18000cdfa  pop     r15
0x18000cdfc  pop     r14
0x18000cdfe  pop     rdi
0x18000cdff  pop     rsi
0x18000ce00  pop     rbx
0x18000ce01  pop     rbp
0x18000ce02  retn
```
