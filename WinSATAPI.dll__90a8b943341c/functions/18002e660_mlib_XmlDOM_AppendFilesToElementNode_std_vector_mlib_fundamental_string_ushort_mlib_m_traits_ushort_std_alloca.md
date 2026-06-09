# mlib::XmlDOM::AppendFilesToElementNode(std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>,std::allocator<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>>> const &,IXMLDOMNode *)

- ea: `0x18002e660`
- end: `0x18002e770`
- name: `?AppendFilesToElementNode@XmlDOM@mlib@@SA_NAEBV?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@PEAUIXMLDOMNode@@@Z`
- size: `272`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002ea74`

## callees

- `0x180006494`
- `0x18000e490`
- `0x18002e660`
- `0x18002e99c`
- `0x180033010`

## string_xrefs

- `0x18002e6fa`: `base\winsat\mlib\mxmldom.cpp`
- `0x18002e742`: `base\winsat\mlib\mxmldom.cpp`
- `0x18002e714`: `cannot load XML data from file '%s'`
- `0x18002e6d4`: `cannot append data to a XML node`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall mlib::XmlDOM::AppendFilesToElementNode(__int64 *a1, __int64 a2)
{
  __int64 i; // rbx
  int v5; // r8d
  __int64 v7; // [rsp+60h] [rbp+8h] BYREF

  for ( i = *a1; i != a1[1]; i += 8 )
  {
    v7 = 0;
    if ( (int)mlib::XmlDOM::LoadDocumentFromFile(i, &v7) < 0 )
    {
      mlib::XmlDOM::ReportCOMError_w(
        (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
        457,
        -2147467259,
        v7,
        (__int64)&GUID_2933bf80_7b36_11d2_b20e_00c04f983e60,
        0,
        (__int64)L"cannot load XML data from file '%s'",
        *(_QWORD *)(*(_QWORD *)i + 24LL),
        -2);
      goto LABEL_8;
    }
    v5 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)a2 + 168LL))(a2, v7, 0);
    if ( v5 < 0 )
    {
      mlib::XmlDOM::ReportCOMError_w(
        (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
        466,
        v5,
        a2,
        (__int64)&GUID_2933bf80_7b36_11d2_b20e_00c04f983e60,
        0,
        (__int64)L"cannot append data to a XML node");
LABEL_8:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v7);
      return 0;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v7);
  }
  return 1;
}

```

## disassembly

```asm
0x18002e660  push    rdi
0x18002e662  sub     rsp, 50h
0x18002e666  mov     [rsp+58h+var_18], 0FFFFFFFFFFFFFFFEh
0x18002e66f  mov     [rsp+58h+arg_8], rbx
0x18002e674  mov     [rsp+58h+arg_10], rsi
0x18002e679  mov     rsi, rdx
0x18002e67c  mov     rdi, rcx
0x18002e67f  mov     rbx, [rcx]
0x18002e682  cmp     rbx, [rdi+8]
0x18002e686  jz      loc_18002E75D
0x18002e68c  and     [rsp+58h+arg_0], 0
0x18002e692  lea     rdx, [rsp+58h+arg_0]
0x18002e697  mov     rcx, rbx
0x18002e69a  call    ?LoadDocumentFromFile@XmlDOM@mlib@@SAJAEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEAPEAUIXMLDOMNode@@PEAV32@_N@Z; mlib::XmlDOM::LoadDocumentFromFile(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,IXMLDOMNode * *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,bool)
0x18002e69f  test    eax, eax
0x18002e6a1  js      short loc_18002E708
0x18002e6a3  mov     rax, [rsi]
0x18002e6a6  xor     r8d, r8d
0x18002e6a9  mov     rdx, [rsp+58h+arg_0]
0x18002e6ae  mov     rcx, rsi
0x18002e6b1  mov     rax, [rax+0A8h]
0x18002e6b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e6bd  mov     r8d, eax
0x18002e6c0  test    eax, eax
0x18002e6c2  js      short loc_18002E6D4
0x18002e6c4  lea     rcx, [rsp+58h+arg_0]
0x18002e6c9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002e6ce  add     rbx, 8
0x18002e6d2  jmp     short loc_18002E682
0x18002e6d4  lea     rax, aCannotAppendDa; "cannot append data to a XML node"
0x18002e6db  mov     [rsp+58h+var_28], rax
0x18002e6e0  and     [rsp+58h+var_30], 0
0x18002e6e6  lea     rax, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60
0x18002e6ed  mov     [rsp+58h+var_38], rax
0x18002e6f2  mov     r9, rsi
0x18002e6f5  mov     edx, 1D2h
0x18002e6fa  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x18002e701  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x18002e706  jmp     short loc_18002E74F
0x18002e708  mov     rax, [rbx]
0x18002e70b  mov     rcx, [rax+18h]
0x18002e70f  mov     [rsp+58h+var_20], rcx
0x18002e714  lea     rax, aCannotLoadXmlD; "cannot load XML data from file '%s'"
0x18002e71b  mov     [rsp+58h+var_28], rax
0x18002e720  and     [rsp+58h+var_30], 0
0x18002e726  lea     rax, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60
0x18002e72d  mov     [rsp+58h+var_38], rax
0x18002e732  mov     r9, [rsp+58h+arg_0]
0x18002e737  mov     edx, 1C9h
0x18002e73c  mov     r8d, 80004005h
0x18002e742  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x18002e749  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x18002e74e  nop
0x18002e74f  lea     rcx, [rsp+58h+arg_0]
0x18002e754  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002e759  xor     al, al
0x18002e75b  jmp     short loc_18002E75F
0x18002e75d  mov     al, 1
0x18002e75f  mov     rbx, [rsp+58h+arg_8]
0x18002e764  mov     rsi, [rsp+58h+arg_10]
0x18002e769  add     rsp, 50h
0x18002e76d  pop     rdi
0x18002e76e  retn
```
