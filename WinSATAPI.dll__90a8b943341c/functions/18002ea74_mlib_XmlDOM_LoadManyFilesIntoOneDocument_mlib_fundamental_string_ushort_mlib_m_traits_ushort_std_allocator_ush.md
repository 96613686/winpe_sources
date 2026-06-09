# mlib::XmlDOM::LoadManyFilesIntoOneDocument(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>,std::allocator<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>>> const &,IXMLDOMNode * *)

- ea: `0x18002ea74`
- end: `0x18002ecc2`
- name: `?LoadManyFilesIntoOneDocument@XmlDOM@mlib@@SA_NAEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@AEBV?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@PEAPEAUIXMLDOMNode@@@Z`
- size: `590`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001f530`

## callees

- `0x180006494`
- `0x18000cf90`
- `0x18000e490`
- `0x18000e68c`
- `0x18002e660`
- `0x18002ea74`
- `0x180033010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18002eab6`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ec8a`
- `OLEAUT32!__imp_SysFreeString` at `0x18002eab6`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ec8a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002eb4f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002eb4f`

## string_xrefs

- `0x18002eb21`: `base\winsat\mlib\mxmldom.cpp`
- `0x18002eb87`: `base\winsat\mlib\mxmldom.cpp`
- `0x18002ec73`: `base\winsat\mlib\mxmldom.cpp`
- `0x18002eb62`: `cannot create an IXMLDOMDocument2 document`
- `0x18002ebba`: `cannot create a root XML document element`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall mlib::XmlDOM::LoadManyFilesIntoOneDocument(__int64 a1, __int64 a2, _QWORD *a3)
{
  char v6; // di
  OLECHAR *v7; // rcx
  OLECHAR *v9; // rbx
  HRESULT v10; // r8d
  int v11; // eax
  int v12; // eax
  int v13; // eax
  BSTR bstrString[2]; // [rsp+40h] [rbp-10h] BYREF
  LPVOID ppv; // [rsp+90h] [rbp+40h] BYREF
  __int64 v16; // [rsp+98h] [rbp+48h] BYREF

  bstrString[1] = (BSTR)-2LL;
  v6 = 0;
  ppv = 0;
  v16 = 0;
  bstrString[0] = 0;
  *a3 = 0;
  if ( !mlib::XmlDOM::Init() )
    goto LABEL_2;
  ATL::CComBSTR::operator=(bstrString, *(_QWORD *)(*(_QWORD *)a1 + 24LL));
  v9 = bstrString[0];
  if ( !bstrString[0] )
  {
    mlib::XmlDOM::ReportCOMError_w(
      (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
      510,
      -2147024882,
      0,
      (__int64)&unk_180050618,
      0,
      (__int64)L"cannot allocate memory for a string");
LABEL_2:
    v7 = 0;
LABEL_3:
    SysFreeString(v7);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
    return 0;
  }
  v10 = CoCreateInstance(&mlib::XmlDOM::clsIDDocument, 0, 1u, &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60, &ppv);
  if ( v10 < 0 )
  {
    mlib::XmlDOM::ReportCOMError_w(
      (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
      532,
      v10,
      0,
      (__int64)&unk_180050618,
      0,
      (__int64)L"cannot create an IXMLDOMDocument2 document");
LABEL_8:
    v7 = v9;
    goto LABEL_3;
  }
  v11 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, __int64 *))(*(_QWORD *)ppv + 376LL))(ppv, v9, &v16);
  if ( v11 < 0 )
  {
    mlib::XmlDOM::ReportCOMError_w(
      (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
      543,
      v11,
      (_DWORD)ppv,
      (__int64)&GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
      0,
      (__int64)L"cannot create a root XML document element");
    goto LABEL_8;
  }
  v12 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 368LL))(ppv, v16);
  if ( v12 < 0 )
  {
    mlib::XmlDOM::ReportCOMError_w(
      (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
      554,
      v12,
      (_DWORD)ppv,
      (__int64)&GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
      0,
      (__int64)L"cannot set the new element as the DOM document root");
    goto LABEL_8;
  }
  if ( !(unsigned __int8)mlib::XmlDOM::AppendFilesToElementNode(a2, v16) )
    goto LABEL_8;
  v13 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, _QWORD *))ppv)(ppv, &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60, a3);
  if ( v13 >= 0 )
  {
    v6 = 1;
  }
  else
  {
    mlib::XmlDOM::ReportCOMError_w(
      (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
      571,
      v13,
      (_DWORD)ppv,
      (__int64)&GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
      0,
      (__int64)L"cannot get root DOM node");
    *a3 = 0;
  }
  SysFreeString(v9);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  return v6;
}

```

## disassembly

```asm
0x18002ea74  mov     rax, rsp
0x18002ea77  push    rbp
0x18002ea78  push    rsi
0x18002ea79  push    rdi
0x18002ea7a  push    r14
0x18002ea7c  push    r15
0x18002ea7e  mov     rbp, rsp
0x18002ea81  sub     rsp, 50h
0x18002ea85  mov     [rbp+var_8], 0FFFFFFFFFFFFFFFEh
0x18002ea8d  mov     [rax+8], rbx
0x18002ea91  mov     rsi, r8
0x18002ea94  mov     r14, rdx
0x18002ea97  mov     rbx, rcx
0x18002ea9a  xor     edi, edi
0x18002ea9c  mov     [rbp+arg_10], rdi
0x18002eaa0  mov     [rbp+arg_18], rdi
0x18002eaa4  mov     [rbp+bstrString], rdi
0x18002eaa8  mov     [r8], rdi
0x18002eaab  call    ?Init@XmlDOM@mlib@@CA_NXZ; mlib::XmlDOM::Init(void)
0x18002eab0  test    al, al
0x18002eab2  jnz     short loc_18002EADD
0x18002eab4  xor     ecx, ecx; bstrString
0x18002eab6  call    cs:__imp_SysFreeString
0x18002eabd  nop     dword ptr [rax+rax+00h]
0x18002eac2  nop
0x18002eac3  lea     rcx, [rbp+arg_18]
0x18002eac7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002eacc  nop
0x18002eacd  lea     rcx, [rbp+arg_10]
0x18002ead1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002ead6  xor     al, al
0x18002ead8  jmp     loc_18002ECAD
0x18002eadd  mov     rax, [rbx]
0x18002eae0  mov     rdx, [rax+18h]
0x18002eae4  lea     rcx, [rbp+bstrString]
0x18002eae8  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18002eaed  mov     rbx, [rbp+bstrString]
0x18002eaf1  test    rbx, rbx
0x18002eaf4  jnz     short loc_18002EB2F
0x18002eaf6  lea     rax, aCannotAllocate_0; "cannot allocate memory for a string"
0x18002eafd  mov     [rsp+50h+var_20], rax
0x18002eb02  mov     [rsp+50h+var_28], rdi
0x18002eb07  lea     rax, unk_180050618
0x18002eb0e  mov     [rsp+50h+ppv], rax
0x18002eb13  xor     r9d, r9d
0x18002eb16  mov     edx, 1FEh
0x18002eb1b  mov     r8d, 8007000Eh
0x18002eb21  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x18002eb28  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x18002eb2d  jmp     short loc_18002EAB4
0x18002eb2f  lea     rax, [rbp+arg_10]
0x18002eb33  mov     [rsp+50h+ppv], rax; ppv
0x18002eb38  lea     r15, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60
0x18002eb3f  mov     r9, r15; riid
0x18002eb42  xor     edx, edx; pUnkOuter
0x18002eb44  lea     r8d, [rdx+1]; dwClsContext
0x18002eb48  lea     rcx, ?clsIDDocument@XmlDOM@mlib@@0U_GUID@@A; rclsid
0x18002eb4f  call    cs:__imp_CoCreateInstance
0x18002eb56  nop     dword ptr [rax+rax+00h]
0x18002eb5b  mov     r8d, eax
0x18002eb5e  test    eax, eax
0x18002eb60  jns     short loc_18002EB9C
0x18002eb62  lea     rax, aCannotCreateAn; "cannot create an IXMLDOMDocument2 docum"...
0x18002eb69  mov     [rsp+50h+var_20], rax
0x18002eb6e  mov     [rsp+50h+var_28], rdi
0x18002eb73  lea     rax, unk_180050618
0x18002eb7a  mov     [rsp+50h+ppv], rax
0x18002eb7f  xor     r9d, r9d
0x18002eb82  mov     edx, 214h
0x18002eb87  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x18002eb8e  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x18002eb93  nop
0x18002eb94  mov     rcx, rbx
0x18002eb97  jmp     loc_18002EAB6
0x18002eb9c  mov     rcx, [rbp+arg_10]
0x18002eba0  mov     rax, [rcx]
0x18002eba3  lea     r8, [rbp+arg_18]
0x18002eba7  mov     rdx, rbx
0x18002ebaa  mov     rax, [rax+178h]
0x18002ebb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ebb6  test    eax, eax
0x18002ebb8  jns     short loc_18002EBDE
0x18002ebba  lea     rcx, aCannotCreateAR; "cannot create a root XML document eleme"...
0x18002ebc1  mov     [rsp+50h+var_20], rcx
0x18002ebc6  mov     [rsp+50h+var_28], rdi
0x18002ebcb  mov     [rsp+50h+ppv], r15
0x18002ebd0  mov     r9, [rbp+arg_10]
0x18002ebd4  mov     r8d, eax
0x18002ebd7  mov     edx, 21Fh
0x18002ebdc  jmp     short loc_18002EB87
0x18002ebde  mov     rcx, [rbp+arg_10]
0x18002ebe2  mov     rax, [rcx]
0x18002ebe5  mov     rdx, [rbp+arg_18]
0x18002ebe9  mov     rax, [rax+170h]
0x18002ebf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ebf5  test    eax, eax
0x18002ebf7  jns     short loc_18002EC20
0x18002ebf9  lea     rcx, aCannotSetTheNe; "cannot set the new element as the DOM d"...
0x18002ec00  mov     [rsp+50h+var_20], rcx
0x18002ec05  mov     [rsp+50h+var_28], rdi
0x18002ec0a  mov     [rsp+50h+ppv], r15
0x18002ec0f  mov     r9, [rbp+arg_10]
0x18002ec13  mov     r8d, eax
0x18002ec16  mov     edx, 22Ah
0x18002ec1b  jmp     loc_18002EB87
0x18002ec20  mov     rdx, [rbp+arg_18]
0x18002ec24  mov     rcx, r14
0x18002ec27  call    ?AppendFilesToElementNode@XmlDOM@mlib@@SA_NAEBV?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@PEAUIXMLDOMNode@@@Z; mlib::XmlDOM::AppendFilesToElementNode(std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>> const &,IXMLDOMNode *)
0x18002ec2c  test    al, al
0x18002ec2e  jz      loc_18002EB94
0x18002ec34  mov     rcx, [rbp+arg_10]
0x18002ec38  mov     rax, [rcx]
0x18002ec3b  mov     r8, rsi
0x18002ec3e  lea     rdx, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60
0x18002ec45  mov     rax, [rax]
0x18002ec48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec4d  test    eax, eax
0x18002ec4f  jns     short loc_18002EC84
0x18002ec51  lea     rcx, aCannotGetRootD; "cannot get root DOM node"
0x18002ec58  mov     [rsp+50h+var_20], rcx
0x18002ec5d  mov     [rsp+50h+var_28], rdi
0x18002ec62  mov     [rsp+50h+ppv], r15
0x18002ec67  mov     r9, [rbp+arg_10]
0x18002ec6b  mov     r8d, eax
0x18002ec6e  mov     edx, 23Bh
0x18002ec73  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x18002ec7a  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x18002ec7f  mov     [rsi], rdi
0x18002ec82  jmp     short loc_18002EC87
0x18002ec84  mov     dil, 1
0x18002ec87  mov     rcx, rbx; bstrString
0x18002ec8a  call    cs:__imp_SysFreeString
0x18002ec91  nop     dword ptr [rax+rax+00h]
0x18002ec96  nop
0x18002ec97  lea     rcx, [rbp+arg_18]
0x18002ec9b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002eca0  nop
0x18002eca1  lea     rcx, [rbp+arg_10]
0x18002eca5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002ecaa  mov     al, dil
0x18002ecad  mov     rbx, [rsp+50h+arg_0]
0x18002ecb5  add     rsp, 50h
0x18002ecb9  pop     r15
0x18002ecbb  pop     r14
0x18002ecbd  pop     rdi
0x18002ecbe  pop     rsi
0x18002ecbf  pop     rbp
0x18002ecc0  retn
```
