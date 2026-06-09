# Sharp::Util::Xml::CNode::GetChilds(void)

- ea: `0x140012950`
- end: `0x140012a6d`
- name: `?GetChilds@CNode@Xml@Util@Sharp@@QEBA?AVCNodeCollection@234@XZ`
- size: `285`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140012b94`
- `0x140012c90`
- `0x140012f20`

## callees

- `0x140001d1c`
- `0x1400070e4`
- `0x140007428`
- `0x140011888`
- `0x1400119d4`
- `0x140011a6c`
- `0x140012950`
- `0x140013548`
- `0x140013b10`
- `0x140016010`

## pseudocode

```c
_QWORD *__fastcall Sharp::Util::Xml::CNode::GetChilds(__int64 a1, _QWORD *a2)
{
  int v4; // eax
  int v5; // edi
  __int64 *v6; // rax
  __int64 v8; // [rsp+28h] [rbp-31h] BYREF
  __int64 v9[4]; // [rsp+30h] [rbp-29h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+50h] [rbp-9h] BYREF

  v9[1] = (__int64)a2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids);
  v8 = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(a1 + 8) + 96LL))(*(_QWORD *)(a1 + 8), &v8);
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids,
        (unsigned int)v4);
    xml_exception::xml_exception((xml_exception *)pExceptionObject, v5);
    throw (xml_exception *)pExceptionObject;
  }
  v9[2] = (__int64)v9;
  v6 = ATL::CComPtr<IXMLDOMNodeList>::CComPtr<IXMLDOMNodeList>(v9, &v8);
  Sharp::Util::Xml::CNodeCollection::CNodeCollection(a2, v6);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v8);
  return a2;
}

```

## disassembly

```asm
0x140012950  mov     [rsp-8+arg_10], rbx
0x140012955  push    rbp
0x140012956  push    rsi
0x140012957  push    rdi
0x140012958  lea     rbp, [rsp-47h]
0x14001295d  sub     rsp, 0A0h
0x140012964  mov     rax, cs:__security_cookie
0x14001296b  xor     rax, rsp
0x14001296e  mov     [rbp+57h+var_20], rax
0x140012972  mov     rbx, rdx
0x140012975  mov     rdi, rcx
0x140012978  mov     [rbp+57h+var_78], rdx
0x14001297c  mov     [rbp+57h+var_90], 0
0x140012983  lea     rsi, WPP_GLOBAL_Control
0x14001298a  mov     rcx, cs:WPP_GLOBAL_Control
0x140012991  cmp     rcx, rsi
0x140012994  jz      short loc_1400129B1
0x140012996  test    byte ptr [rcx+1Ch], 8
0x14001299a  jz      short loc_1400129B1
0x14001299c  mov     edx, 11h
0x1400129a1  lea     r8, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids
0x1400129a8  mov     rcx, [rcx+10h]
0x1400129ac  call    WPP_SF_
0x1400129b1  mov     [rbp+57h+var_88], 0
0x1400129b9  mov     rcx, [rdi+8]
0x1400129bd  mov     rax, [rcx]
0x1400129c0  lea     rdx, [rbp+57h+var_88]
0x1400129c4  mov     rax, [rax+60h]
0x1400129c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400129cd  mov     edi, eax
0x1400129cf  test    eax, eax
0x1400129d1  jns     short loc_140012A19
0x1400129d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400129da  cmp     rcx, rsi
0x1400129dd  jz      short loc_1400129FD
0x1400129df  test    byte ptr [rcx+1Ch], 1
0x1400129e3  jz      short loc_1400129FD
0x1400129e5  mov     edx, 12h
0x1400129ea  mov     r9d, eax
0x1400129ed  lea     r8, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids
0x1400129f4  mov     rcx, [rcx+10h]
0x1400129f8  call    WPP_SF_d
0x1400129fd  mov     edx, edi; int
0x1400129ff  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140012a03  call    ??0xml_exception@@QEAA@J@Z; xml_exception::xml_exception(long)
0x140012a08  lea     rdx, _TI3?AVxml_exception@@; pThrowInfo
0x140012a0f  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140012a13  call    _CxxThrowException_0
0x140012a19  lea     rax, [rbp+57h+var_80]
0x140012a1d  mov     [rbp+57h+var_70], rax
0x140012a21  lea     rdx, [rbp+57h+var_88]
0x140012a25  lea     rcx, [rbp+57h+var_80]
0x140012a29  call    ??0?$CComPtr@UIXMLDOMNodeList@@@ATL@@QEAA@AEBV01@@Z; ATL::CComPtr<IXMLDOMNodeList>::CComPtr<IXMLDOMNodeList>(ATL::CComPtr<IXMLDOMNodeList> const &)
0x140012a2e  nop
0x140012a2f  mov     rdx, rax
0x140012a32  mov     rcx, rbx
0x140012a35  call    ??0CNodeCollection@Xml@Util@Sharp@@QEAA@V?$CComPtr@UIXMLDOMNodeList@@@ATL@@@Z; Sharp::Util::Xml::CNodeCollection::CNodeCollection(ATL::CComPtr<IXMLDOMNodeList>)
0x140012a3a  mov     [rbp+57h+var_90], 1
0x140012a41  lea     rcx, [rbp+57h+var_88]
0x140012a45  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x140012a4a  mov     rax, rbx
0x140012a4d  mov     rcx, [rbp+57h+var_20]
0x140012a51  xor     rcx, rsp; StackCookie
0x140012a54  call    __security_check_cookie
0x140012a59  mov     rbx, [rsp+0B0h+arg_10]
0x140012a61  add     rsp, 0A0h
0x140012a68  pop     rdi
0x140012a69  pop     rsi
0x140012a6a  pop     rbp
0x140012a6b  retn
```
