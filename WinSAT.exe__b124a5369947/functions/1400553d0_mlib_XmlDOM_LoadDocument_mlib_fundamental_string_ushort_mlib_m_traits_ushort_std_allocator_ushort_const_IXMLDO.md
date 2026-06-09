# mlib::XmlDOM::LoadDocument(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,IXMLDOMNode * *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,bool)

- ea: `0x1400553d0`
- end: `0x1400555a4`
- name: `?LoadDocument@XmlDOM@mlib@@SAJAEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEAPEAUIXMLDOMNode@@PEAV32@_N@Z`
- size: `468`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140012f64`

## callees

- `0x14000712c`
- `0x140053e14`
- `0x140055054`
- `0x1400553d0`
- `0x1400557f4`
- `0x14011a010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1400554fe`
- `OLEAUT32!__imp_SysFreeString` at `0x14005557c`
- `OLEAUT32!__imp_SysFreeString` at `0x1400554fe`
- `OLEAUT32!__imp_SysFreeString` at `0x14005557c`
- `ole32!CoCreateInstance` at `0x140055437`
- `ole32!CoCreateInstance` at `0x140055437`

## string_xrefs

- `0x14005549b`: `base\winsat\mlib\mxmldom.cpp`
- `0x1400554ed`: `base\winsat\mlib\mxmldom.cpp`
- `0x140055441`: `cannot create an IXMLDOMDocument2 document`
- `0x1400554d3`: `cannot load XML data from a string`
- `0x140055565`: `cannot get the IXMLDOMNode interface for an XML document`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall mlib::XmlDOM::LoadDocument(__int64 a1, _QWORD *a2, __int64 a3)
{
  unsigned int v6; // edi
  HRESULT v7; // eax
  unsigned int v8; // eax
  OLECHAR *v9; // rbx
  OLECHAR *v10; // rcx
  int v11; // eax
  int v12; // r8d
  int v13; // edx
  unsigned int v14; // eax
  int v15; // eax
  int v16; // eax
  BSTR bstrString[2]; // [rsp+40h] [rbp-10h] BYREF
  LPVOID ppv; // [rsp+88h] [rbp+38h] BYREF
  __int16 v20; // [rsp+98h] [rbp+48h] BYREF

  ppv = 0;
  v20 = 0;
  bstrString[0] = 0;
  *a2 = 0;
  if ( mlib::XmlDOM::Init() )
  {
    v7 = CoCreateInstance(&mlib::XmlDOM::clsIDDocument, 0, 1u, &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60, &ppv);
    if ( v7 < 0 )
    {
      v8 = mlib::XmlDOM::ReportCOMError_w(
             (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
             304,
             v7,
             0,
             (__int64)qword_1401C3B08,
             a3,
             (__int64)L"cannot create an IXMLDOMDocument2 document");
LABEL_7:
      v6 = v8;
      goto LABEL_8;
    }
    ATL::CComBSTR::operator=(bstrString, *(_QWORD *)(*(_QWORD *)a1 + 24LL));
    v9 = bstrString[0];
    if ( !bstrString[0] )
    {
      v8 = mlib::XmlDOM::ReportCOMError_w(
             (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
             310,
             -2147024882,
             0,
             (__int64)qword_1401C3B08,
             a3,
             (__int64)L"cannot allocate memory for a string");
      goto LABEL_7;
    }
    v11 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int16 *))(*(_QWORD *)ppv + 520LL))(ppv, bstrString[0], &v20);
    if ( v11 >= 0 )
    {
      if ( v20 )
      {
        v15 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 576LL))(ppv, 0xFFFFFFFFLL);
        if ( v15 >= 0 )
        {
          v16 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, _QWORD *))ppv)(
                  ppv,
                  &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60,
                  a2);
          if ( v16 >= 0 )
          {
            SysFreeString(v9);
            v6 = 0;
            goto LABEL_21;
          }
          *a2 = 0;
          v14 = mlib::XmlDOM::ReportCOMError_w(
                  (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
                  340,
                  v16,
                  (_DWORD)ppv,
                  (__int64)&GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
                  a3,
                  (__int64)L"cannot get the IXMLDOMNode interface for an XML document");
        }
        else
        {
          v14 = mlib::XmlDOM::ReportCOMError_w(
                  (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
                  332,
                  v15,
                  (_DWORD)ppv,
                  (__int64)&GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
                  a3,
                  (__int64)L"cannot set the 'preserve white space' flag");
        }
        goto LABEL_12;
      }
      v13 = 321;
      v12 = -2147467259;
    }
    else
    {
      v12 = v11;
      v13 = 316;
    }
    v14 = mlib::XmlDOM::ReportCOMError_w(
            (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
            v13,
            v12,
            (_DWORD)ppv,
            (__int64)&GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
            a3,
            (__int64)L"cannot load XML data from a string");
LABEL_12:
    v6 = v14;
    v10 = v9;
    goto LABEL_13;
  }
  v6 = -2147467259;
LABEL_8:
  v10 = 0;
LABEL_13:
  SysFreeString(v10);
LABEL_21:
  ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&ppv);
  return v6;
}

```

## disassembly

```asm
0x1400553d0  mov     [rsp-28h+arg_0], rbx
0x1400553d5  mov     byte ptr [rsp-28h+arg_18], r9b
0x1400553da  push    rbp
0x1400553db  push    rsi
0x1400553dc  push    rdi
0x1400553dd  push    r14
0x1400553df  push    r15
0x1400553e1  mov     rbp, rsp
0x1400553e4  sub     rsp, 50h
0x1400553e8  mov     rdi, r8
0x1400553eb  mov     rsi, rdx
0x1400553ee  mov     rbx, rcx
0x1400553f1  xor     r14d, r14d
0x1400553f4  mov     [rbp+arg_8], r14
0x1400553f8  mov     [rbp+arg_18], r14w
0x1400553fd  mov     [rbp+bstrString], r14
0x140055401  mov     [rdx], r14
0x140055404  call    ?Init@XmlDOM@mlib@@CA_NXZ; mlib::XmlDOM::Init(void)
0x140055409  test    al, al
0x14005540b  jnz     short loc_140055417
0x14005540d  mov     edi, 80004005h
0x140055412  jmp     loc_1400554A9
0x140055417  lea     rax, [rbp+arg_8]
0x14005541b  mov     [rsp+50h+ppv], rax; ppv
0x140055420  lea     r15, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60
0x140055427  mov     r9, r15; riid
0x14005542a  xor     edx, edx; pUnkOuter
0x14005542c  lea     r8d, [rdx+1]; dwClsContext
0x140055430  lea     rcx, ?clsIDDocument@XmlDOM@mlib@@0U_GUID@@A; rclsid
0x140055437  call    cs:__imp_CoCreateInstance
0x14005543d  test    eax, eax
0x14005543f  jns     short loc_140055457
0x140055441  lea     rcx, aCannotCreateAn; "cannot create an IXMLDOMDocument2 docum"...
0x140055448  mov     [rsp+50h+var_20], rcx
0x14005544d  mov     r8d, eax
0x140055450  mov     edx, 130h
0x140055455  jmp     short loc_140055487
0x140055457  mov     rdx, [rbx]
0x14005545a  mov     rdx, [rdx+18h]
0x14005545e  lea     rcx, [rbp+bstrString]
0x140055462  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x140055467  mov     rbx, [rbp+bstrString]
0x14005546b  test    rbx, rbx
0x14005546e  jnz     short loc_1400554AD
0x140055470  lea     rax, aCannotAllocate_0; "cannot allocate memory for a string"
0x140055477  mov     [rsp+50h+var_20], rax
0x14005547c  mov     edx, 136h
0x140055481  mov     r8d, 8007000Eh
0x140055487  mov     [rsp+50h+var_28], rdi
0x14005548c  lea     rcx, qword_1401C3B08
0x140055493  mov     [rsp+50h+ppv], rcx
0x140055498  xor     r9d, r9d
0x14005549b  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x1400554a2  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x1400554a7  mov     edi, eax
0x1400554a9  xor     ecx, ecx
0x1400554ab  jmp     short loc_1400554FE
0x1400554ad  mov     rcx, [rbp+arg_8]
0x1400554b1  mov     rax, [rcx]
0x1400554b4  lea     r8, [rbp+arg_18]
0x1400554b8  mov     rdx, rbx
0x1400554bb  mov     rax, [rax+208h]
0x1400554c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400554c7  test    eax, eax
0x1400554c9  jns     short loc_140055506
0x1400554cb  mov     r8d, eax
0x1400554ce  mov     edx, 13Ch
0x1400554d3  lea     rcx, aCannotLoadXmlD; "cannot load XML data from a string"
0x1400554da  mov     [rsp+50h+var_20], rcx
0x1400554df  mov     [rsp+50h+var_28], rdi
0x1400554e4  mov     r9, [rbp+arg_8]
0x1400554e8  mov     [rsp+50h+ppv], r15
0x1400554ed  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x1400554f4  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x1400554f9  mov     edi, eax
0x1400554fb  mov     rcx, rbx; bstrString
0x1400554fe  call    cs:__imp_SysFreeString
0x140055504  jmp     short loc_140055585
0x140055506  cmp     [rbp+arg_18], r14w
0x14005550b  jnz     short loc_14005551A
0x14005550d  mov     edx, 141h
0x140055512  mov     r8d, 80004005h
0x140055518  jmp     short loc_1400554D3
0x14005551a  mov     rcx, [rbp+arg_8]
0x14005551e  mov     rax, [rcx]
0x140055521  or      edx, 0FFFFFFFFh
0x140055524  mov     rax, [rax+240h]
0x14005552b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140055530  test    eax, eax
0x140055532  jns     short loc_140055545
0x140055534  lea     rcx, aCannotSetThePr; "cannot set the 'preserve white space' f"...
0x14005553b  mov     r8d, eax
0x14005553e  mov     edx, 14Ch
0x140055543  jmp     short loc_1400554DA
0x140055545  mov     rcx, [rbp+arg_8]
0x140055549  mov     rax, [rcx]
0x14005554c  mov     r8, rsi
0x14005554f  lea     rdx, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60
0x140055556  mov     rax, [rax]
0x140055559  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005555e  test    eax, eax
0x140055560  jns     short loc_140055579
0x140055562  mov     [rsi], r14
0x140055565  lea     rcx, aCannotGetTheIx; "cannot get the IXMLDOMNode interface fo"...
0x14005556c  mov     r8d, eax
0x14005556f  mov     edx, 154h
0x140055574  jmp     loc_1400554DA
0x140055579  mov     rcx, rbx; bstrString
0x14005557c  call    cs:__imp_SysFreeString
0x140055582  mov     edi, r14d
0x140055585  lea     rcx, [rbp+arg_8]
0x140055589  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x14005558e  mov     eax, edi
0x140055590  mov     rbx, [rsp+50h+arg_0]
0x140055598  add     rsp, 50h
0x14005559c  pop     r15
0x14005559e  pop     r14
0x1400555a0  pop     rdi
0x1400555a1  pop     rsi
0x1400555a2  pop     rbp
0x1400555a3  retn
```
