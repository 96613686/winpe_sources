# mlib::XmlDOM::SelectSingleNode(IXMLDOMNode *,ushort const *,ushort const *,IXMLDOMNode * &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x140055bf0`
- end: `0x140055d72`
- name: `?SelectSingleNode@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@PEBG1AEAPEAU3@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z`
- size: `386`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14001e350`
- `0x14001fc70`
- `0x1400563ec`

## callees

- `0x14000712c`
- `0x140053e14`
- `0x1400557f4`
- `0x140055bf0`
- `0x14011a010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140055c8c`
- `OLEAUT32!__imp_SysFreeString` at `0x140055c95`
- `OLEAUT32!__imp_SysFreeString` at `0x140055d0b`
- `OLEAUT32!__imp_SysFreeString` at `0x140055d14`
- `OLEAUT32!__imp_SysFreeString` at `0x140055d23`
- `OLEAUT32!__imp_SysFreeString` at `0x140055d2d`
- `OLEAUT32!__imp_SysFreeString` at `0x140055d36`
- `OLEAUT32!__imp_SysFreeString` at `0x140055d45`
- `OLEAUT32!__imp_SysFreeString` at `0x140055c8c`
- `OLEAUT32!__imp_SysFreeString` at `0x140055c95`
- `OLEAUT32!__imp_SysFreeString` at `0x140055d0b`
- `OLEAUT32!__imp_SysFreeString` at `0x140055d14`
- `OLEAUT32!__imp_SysFreeString` at `0x140055d23`
- `OLEAUT32!__imp_SysFreeString` at `0x140055d2d`
- `OLEAUT32!__imp_SysFreeString` at `0x140055d36`
- `OLEAUT32!__imp_SysFreeString` at `0x140055d45`

## string_xrefs

- `0x140055c7c`: `base\winsat\mlib\mxmldom.cpp`
- `0x140055cfb`: `base\winsat\mlib\mxmldom.cpp`
- `0x140055ccb`: `cannot select a XML node for from an XPATH expression`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall mlib::XmlDOM::SelectSingleNode(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4, __int64 a5)
{
  unsigned int v7; // edi
  OLECHAR *v8; // rcx
  int v9; // eax
  _BYTE v11[40]; // [rsp+40h] [rbp-28h] BYREF
  BSTR bstrString; // [rsp+80h] [rbp+18h] BYREF
  __int64 v13; // [rsp+88h] [rbp+20h] BYREF

  memset(v11, 0, 24);
  v13 = 0;
  bstrString = 0;
  *a4 = 0;
  ATL::CComBSTR::operator=(&bstrString, a2);
  if ( bstrString )
  {
    v9 = (*(__int64 (__fastcall **)(__int64, BSTR, _QWORD *))(*(_QWORD *)a1 + 296LL))(a1, bstrString, a4);
    if ( v9 >= 0 )
    {
      SysFreeString(0);
      SysFreeString(0);
      SysFreeString(bstrString);
      v7 = 0;
      goto LABEL_7;
    }
    *a4 = 0;
    v7 = mlib::XmlDOM::ReportCOMError_w(
           (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
           1049,
           v9,
           a1,
           (__int64)&GUID_2933bf80_7b36_11d2_b20e_00c04f983e60,
           a5,
           (__int64)L"cannot select a XML node for from an XPATH expression");
    SysFreeString(0);
    SysFreeString(0);
    v8 = bstrString;
  }
  else
  {
    v7 = mlib::XmlDOM::ReportCOMError_w(
           (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
           997,
           -2147024882,
           0,
           (__int64)qword_1401C3B08,
           a5,
           (__int64)L"cannot allocate memory for a string");
    SysFreeString(0);
    SysFreeString(0);
    v8 = 0;
  }
  SysFreeString(v8);
LABEL_7:
  ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v13);
  ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(v11);
  return v7;
}

```

## disassembly

```asm
0x140055bf0  mov     rax, rsp
0x140055bf3  mov     [rax+8], rsi
0x140055bf7  mov     [rax+18h], r8
0x140055bfb  push    rdi
0x140055bfc  sub     rsp, 60h
0x140055c00  mov     rdi, r9
0x140055c03  mov     rsi, rcx
0x140055c06  mov     qword ptr [rax-28h], 0
0x140055c0e  mov     qword ptr [rax+20h], 0
0x140055c16  mov     qword ptr [rax+18h], 0
0x140055c1e  mov     qword ptr [rax-20h], 0
0x140055c26  mov     qword ptr [rax-18h], 0
0x140055c2e  mov     qword ptr [r9], 0
0x140055c35  lea     rcx, [rax+18h]
0x140055c39  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x140055c3e  cmp     [rsp+68h+bstrString], 0
0x140055c47  jnz     short loc_140055CA3
0x140055c49  lea     rax, aCannotAllocate_0; "cannot allocate memory for a string"
0x140055c50  mov     [rsp+68h+var_38], rax
0x140055c55  mov     rax, [rsp+68h+arg_20]
0x140055c5d  mov     [rsp+68h+var_40], rax
0x140055c62  lea     rax, qword_1401C3B08
0x140055c69  mov     [rsp+68h+var_48], rax
0x140055c6e  xor     r9d, r9d
0x140055c71  mov     edx, 3E5h
0x140055c76  mov     r8d, 8007000Eh
0x140055c7c  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x140055c83  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x140055c88  mov     edi, eax
0x140055c8a  xor     ecx, ecx; bstrString
0x140055c8c  call    cs:__imp_SysFreeString
0x140055c92  nop
0x140055c93  xor     ecx, ecx; bstrString
0x140055c95  call    cs:__imp_SysFreeString
0x140055c9b  nop
0x140055c9c  xor     ecx, ecx
0x140055c9e  jmp     loc_140055D23
0x140055ca3  mov     rax, [rsi]
0x140055ca6  mov     r8, rdi
0x140055ca9  mov     rdx, [rsp+68h+bstrString]
0x140055cb1  mov     rcx, rsi
0x140055cb4  mov     rax, [rax+128h]
0x140055cbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140055cc0  test    eax, eax
0x140055cc2  jns     short loc_140055D2B
0x140055cc4  mov     qword ptr [rdi], 0
0x140055ccb  lea     rcx, aCannotSelectAX; "cannot select a XML node for from an XP"...
0x140055cd2  mov     [rsp+68h+var_38], rcx
0x140055cd7  mov     rcx, [rsp+68h+arg_20]
0x140055cdf  mov     [rsp+68h+var_40], rcx
0x140055ce4  lea     rcx, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60
0x140055ceb  mov     [rsp+68h+var_48], rcx
0x140055cf0  mov     r9, rsi
0x140055cf3  mov     r8d, eax
0x140055cf6  mov     edx, 419h
0x140055cfb  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x140055d02  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x140055d07  mov     edi, eax
0x140055d09  xor     ecx, ecx; bstrString
0x140055d0b  call    cs:__imp_SysFreeString
0x140055d11  nop
0x140055d12  xor     ecx, ecx; bstrString
0x140055d14  call    cs:__imp_SysFreeString
0x140055d1a  nop
0x140055d1b  mov     rcx, [rsp+68h+bstrString]; bstrString
0x140055d23  call    cs:__imp_SysFreeString
0x140055d29  jmp     short loc_140055D4D
0x140055d2b  xor     ecx, ecx; bstrString
0x140055d2d  call    cs:__imp_SysFreeString
0x140055d33  nop
0x140055d34  xor     ecx, ecx; bstrString
0x140055d36  call    cs:__imp_SysFreeString
0x140055d3c  nop
0x140055d3d  mov     rcx, [rsp+68h+bstrString]; bstrString
0x140055d45  call    cs:__imp_SysFreeString
0x140055d4b  xor     edi, edi
0x140055d4d  lea     rcx, [rsp+68h+arg_18]
0x140055d55  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140055d5a  nop
0x140055d5b  lea     rcx, [rsp+68h+var_28]
0x140055d60  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140055d65  mov     eax, edi
0x140055d67  mov     rsi, [rsp+68h+arg_0]
0x140055d6c  add     rsp, 60h
0x140055d70  pop     rdi
0x140055d71  retn
```
