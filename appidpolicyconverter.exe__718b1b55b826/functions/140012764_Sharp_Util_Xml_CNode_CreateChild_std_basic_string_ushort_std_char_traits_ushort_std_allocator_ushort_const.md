# Sharp::Util::Xml::CNode::CreateChild(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x140012764`
- end: `0x140012949`
- name: `?CreateChild@CNode@Xml@Util@Sharp@@QEAA?AV1234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `485`
- prototype: `OLECHAR *__fastcall(Sharp::Util::Xml::CNode *this, OLECHAR *, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000ac40`
- `0x14000cdf0`
- `0x14000e4f0`

## callees

- `0x140001d1c`
- `0x1400070e4`
- `0x140007428`
- `0x140007de4`
- `0x140011888`
- `0x1400119d4`
- `0x140011a6c`
- `0x140011fa0`
- `0x1400121d8`
- `0x140012764`
- `0x140013b10`
- `0x140016010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140012844`
- `OLEAUT32!__imp_SysFreeString` at `0x140012844`

## pseudocode

```c
OLECHAR *__fastcall Sharp::Util::Xml::CNode::CreateChild(
        Sharp::Util::Xml::CNode *this,
        OLECHAR *a2,
        unsigned __int16 *a3)
{
  int v6; // eax
  int v7; // edi
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, _QWORD, __int64 *); // r15
  ATL::CComBSTR *v10; // rax
  int v11; // ebx
  __int64 *v12; // rax
  __int64 v14; // [rsp+20h] [rbp-59h] BYREF
  __int64 v15; // [rsp+28h] [rbp-51h] BYREF
  int v16; // [rsp+30h] [rbp-49h]
  BSTR bstrString[3]; // [rsp+38h] [rbp-41h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+50h] [rbp-29h] BYREF

  bstrString[1] = a2;
  v16 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids);
  v15 = 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 1) + 184LL))(*((_QWORD *)this + 1), &v15);
  v7 = v6;
  if ( v6 < 0 || !v15 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        29,
        WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids,
        (unsigned int)v6);
    xml_exception::xml_exception((xml_exception *)pExceptionObject, v7);
    throw (xml_exception *)pExceptionObject;
  }
  v14 = 0;
  v8 = v15;
  v9 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v15 + 376LL);
  if ( *((_QWORD *)a3 + 3) >= 8u )
    a3 = *(unsigned __int16 **)a3;
  v10 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)bstrString, a3);
  v11 = v9(v8, *(_QWORD *)v10, &v14);
  SysFreeString(bstrString[0]);
  if ( v11 < 0 || !v14 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        30,
        WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids,
        (unsigned int)v11);
    xml_exception::xml_exception((xml_exception *)pExceptionObject, v11);
    throw (xml_exception *)pExceptionObject;
  }
  bstrString[2] = (BSTR)bstrString;
  v12 = ATL::CComPtr<IXMLDOMNodeList>::CComPtr<IXMLDOMNodeList>((__int64 *)bstrString, &v14);
  Sharp::Util::Xml::CNode::CNode(a2, (struct IUnknown **)v12);
  v16 = 1;
  Sharp::Util::Xml::CNode::AppendChild(this, (const struct Sharp::Util::Xml::CNode *)a2);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v14);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v15);
  return a2;
}

```

## disassembly

```asm
0x140012764  push    rbp
0x140012766  push    rbx
0x140012767  push    rsi
0x140012768  push    rdi
0x140012769  push    r13
0x14001276b  push    r14
0x14001276d  push    r15
0x14001276f  lea     rbp, [rsp-27h]
0x140012774  sub     rsp, 0A0h
0x14001277b  mov     rax, cs:__security_cookie
0x140012782  xor     rax, rsp
0x140012785  mov     [rbp+57h+var_40], rax
0x140012789  mov     rbx, r8
0x14001278c  mov     rsi, rdx
0x14001278f  mov     r14, rcx
0x140012792  mov     [rbp+57h+var_90], rdx
0x140012796  mov     [rbp+57h+var_A0], 0
0x14001279d  lea     r13, WPP_GLOBAL_Control
0x1400127a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400127ab  cmp     rcx, r13
0x1400127ae  jz      short loc_1400127CB
0x1400127b0  test    byte ptr [rcx+1Ch], 8
0x1400127b4  jz      short loc_1400127CB
0x1400127b6  mov     edx, 1Ch
0x1400127bb  lea     r8, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids
0x1400127c2  mov     rcx, [rcx+10h]
0x1400127c6  call    WPP_SF_
0x1400127cb  mov     [rbp+57h+var_A8], 0
0x1400127d3  mov     rcx, [r14+8]
0x1400127d7  mov     rax, [rcx]
0x1400127da  lea     rdx, [rbp+57h+var_A8]
0x1400127de  mov     rax, [rax+0B8h]
0x1400127e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400127ea  mov     edi, eax
0x1400127ec  test    eax, eax
0x1400127ee  js      loc_140012903
0x1400127f4  cmp     [rbp+57h+var_A8], 0
0x1400127f9  jz      loc_140012903
0x1400127ff  mov     [rbp+57h+var_B0], 0
0x140012807  mov     rdi, [rbp+57h+var_A8]
0x14001280b  mov     rax, [rdi]
0x14001280e  mov     r15, [rax+178h]
0x140012815  cmp     qword ptr [rbx+18h], 8
0x14001281a  jb      short loc_14001281F
0x14001281c  mov     rbx, [rbx]
0x14001281f  mov     rdx, rbx; unsigned __int16 *
0x140012822  lea     rcx, [rbp+57h+bstrString]; this
0x140012826  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x14001282b  nop
0x14001282c  lea     r8, [rbp+57h+var_B0]
0x140012830  mov     rdx, [rax]
0x140012833  mov     rcx, rdi
0x140012836  mov     rax, r15
0x140012839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001283e  mov     ebx, eax
0x140012840  mov     rcx, [rbp+57h+bstrString]; bstrString
0x140012844  call    cs:__imp_SysFreeString
0x14001284a  test    ebx, ebx
0x14001284c  js      short loc_1400128BD
0x14001284e  cmp     [rbp+57h+var_B0], 0
0x140012853  jz      short loc_1400128BD
0x140012855  lea     rax, [rbp+57h+bstrString]
0x140012859  mov     [rbp+57h+var_88], rax
0x14001285d  lea     rdx, [rbp+57h+var_B0]
0x140012861  lea     rcx, [rbp+57h+bstrString]
0x140012865  call    ??0?$CComPtr@UIXMLDOMNodeList@@@ATL@@QEAA@AEBV01@@Z; ATL::CComPtr<IXMLDOMNodeList>::CComPtr<IXMLDOMNodeList>(ATL::CComPtr<IXMLDOMNodeList> const &)
0x14001286a  nop
0x14001286b  mov     rdx, rax
0x14001286e  mov     rcx, rsi
0x140012871  call    ??0CNode@Xml@Util@Sharp@@QEAA@V?$CComPtr@UIXMLDOMNode@@@ATL@@@Z; Sharp::Util::Xml::CNode::CNode(ATL::CComPtr<IXMLDOMNode>)
0x140012876  mov     [rbp+57h+var_A0], 1
0x14001287d  mov     rdx, rsi; struct Sharp::Util::Xml::CNode *
0x140012880  mov     rcx, r14; this
0x140012883  call    ?AppendChild@CNode@Xml@Util@Sharp@@QEAAXAEBV1234@@Z; Sharp::Util::Xml::CNode::AppendChild(Sharp::Util::Xml::CNode const &)
0x140012888  nop
0x140012889  lea     rcx, [rbp+57h+var_B0]
0x14001288d  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x140012892  nop
0x140012893  lea     rcx, [rbp+57h+var_A8]
0x140012897  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x14001289c  mov     rax, rsi
0x14001289f  mov     rcx, [rbp+57h+var_40]
0x1400128a3  xor     rcx, rsp; StackCookie
0x1400128a6  call    __security_check_cookie
0x1400128ab  add     rsp, 0A0h
0x1400128b2  pop     r15
0x1400128b4  pop     r14
0x1400128b6  pop     r13
0x1400128b8  pop     rdi
0x1400128b9  pop     rsi
0x1400128ba  pop     rbx
0x1400128bb  pop     rbp
0x1400128bc  retn
0x1400128bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400128c4  cmp     rcx, r13
0x1400128c7  jz      short loc_1400128E7
0x1400128c9  test    byte ptr [rcx+1Ch], 1
0x1400128cd  jz      short loc_1400128E7
0x1400128cf  mov     edx, 1Eh
0x1400128d4  mov     r9d, ebx
0x1400128d7  lea     r8, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids
0x1400128de  mov     rcx, [rcx+10h]
0x1400128e2  call    WPP_SF_d
0x1400128e7  mov     edx, ebx; int
0x1400128e9  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1400128ed  call    ??0xml_exception@@QEAA@J@Z; xml_exception::xml_exception(long)
0x1400128f2  lea     rdx, _TI3?AVxml_exception@@; pThrowInfo
0x1400128f9  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1400128fd  call    _CxxThrowException_0
0x140012903  mov     rcx, cs:WPP_GLOBAL_Control
0x14001290a  cmp     rcx, r13
0x14001290d  jz      short loc_14001292D
0x14001290f  test    byte ptr [rcx+1Ch], 1
0x140012913  jz      short loc_14001292D
0x140012915  mov     edx, 1Dh
0x14001291a  mov     r9d, edi
0x14001291d  lea     r8, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids
0x140012924  mov     rcx, [rcx+10h]
0x140012928  call    WPP_SF_d
0x14001292d  mov     edx, edi; int
0x14001292f  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140012933  call    ??0xml_exception@@QEAA@J@Z; xml_exception::xml_exception(long)
0x140012938  lea     rdx, _TI3?AVxml_exception@@; pThrowInfo
0x14001293f  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140012943  call    _CxxThrowException_0
```
