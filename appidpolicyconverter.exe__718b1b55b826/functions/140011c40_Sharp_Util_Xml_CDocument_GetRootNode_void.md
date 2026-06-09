# Sharp::Util::Xml::CDocument::GetRootNode(void)

- ea: `0x140011c40`
- end: `0x140011d60`
- name: `?GetRootNode@CDocument@Xml@Util@Sharp@@QEBA?AVCNode@234@XZ`
- size: `288`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000a9ac`

## callees

- `0x140001d1c`
- `0x1400070e4`
- `0x140007428`
- `0x140011888`
- `0x1400119d4`
- `0x140011a6c`
- `0x140011c40`
- `0x140011fa0`
- `0x140013b10`
- `0x140016010`

## pseudocode

```c
_QWORD *__fastcall Sharp::Util::Xml::CDocument::GetRootNode(__int64 a1, _QWORD *a2)
{
  int v4; // eax
  int v5; // edi
  __int64 *v6; // rax
  __int64 v8; // [rsp+28h] [rbp-31h] BYREF
  __int64 v9[4]; // [rsp+30h] [rbp-29h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+50h] [rbp-9h] BYREF

  v9[1] = (__int64)a2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_e137bfdab7b23ac569be7b05e5d5c80a_Traceguids);
  v8 = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(a1 + 8) + 360LL))(*(_QWORD *)(a1 + 8), &v8);
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        28,
        WPP_e137bfdab7b23ac569be7b05e5d5c80a_Traceguids,
        (unsigned int)v4);
    xml_exception::xml_exception((xml_exception *)pExceptionObject, v5);
    throw (xml_exception *)pExceptionObject;
  }
  v9[2] = (__int64)v9;
  v6 = ATL::CComPtr<IXMLDOMNodeList>::CComPtr<IXMLDOMNodeList>(v9, &v8);
  Sharp::Util::Xml::CNode::CNode(a2, (struct IUnknown **)v6);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v8);
  return a2;
}

```

## disassembly

```asm
0x140011c40  mov     [rsp-8+arg_10], rbx
0x140011c45  push    rbp
0x140011c46  push    rsi
0x140011c47  push    rdi
0x140011c48  lea     rbp, [rsp-47h]
0x140011c4d  sub     rsp, 0A0h
0x140011c54  mov     rax, cs:__security_cookie
0x140011c5b  xor     rax, rsp
0x140011c5e  mov     [rbp+57h+var_20], rax
0x140011c62  mov     rbx, rdx
0x140011c65  mov     rdi, rcx
0x140011c68  mov     [rbp+57h+var_78], rdx
0x140011c6c  mov     [rbp+57h+var_90], 0
0x140011c73  lea     rsi, WPP_GLOBAL_Control
0x140011c7a  mov     rcx, cs:WPP_GLOBAL_Control
0x140011c81  cmp     rcx, rsi
0x140011c84  jz      short loc_140011CA1
0x140011c86  test    byte ptr [rcx+1Ch], 8
0x140011c8a  jz      short loc_140011CA1
0x140011c8c  mov     edx, 1Bh
0x140011c91  lea     r8, WPP_e137bfdab7b23ac569be7b05e5d5c80a_Traceguids
0x140011c98  mov     rcx, [rcx+10h]
0x140011c9c  call    WPP_SF_
0x140011ca1  mov     [rbp+57h+var_88], 0
0x140011ca9  mov     rcx, [rdi+8]
0x140011cad  mov     rax, [rcx]
0x140011cb0  lea     rdx, [rbp+57h+var_88]
0x140011cb4  mov     rax, [rax+168h]
0x140011cbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011cc0  mov     edi, eax
0x140011cc2  test    eax, eax
0x140011cc4  jns     short loc_140011D0C
0x140011cc6  mov     rcx, cs:WPP_GLOBAL_Control
0x140011ccd  cmp     rcx, rsi
0x140011cd0  jz      short loc_140011CF0
0x140011cd2  test    byte ptr [rcx+1Ch], 1
0x140011cd6  jz      short loc_140011CF0
0x140011cd8  mov     edx, 1Ch
0x140011cdd  mov     r9d, eax
0x140011ce0  lea     r8, WPP_e137bfdab7b23ac569be7b05e5d5c80a_Traceguids
0x140011ce7  mov     rcx, [rcx+10h]
0x140011ceb  call    WPP_SF_d
0x140011cf0  mov     edx, edi; int
0x140011cf2  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140011cf6  call    ??0xml_exception@@QEAA@J@Z; xml_exception::xml_exception(long)
0x140011cfb  lea     rdx, _TI3?AVxml_exception@@; pThrowInfo
0x140011d02  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140011d06  call    _CxxThrowException_0
0x140011d0c  lea     rax, [rbp+57h+var_80]
0x140011d10  mov     [rbp+57h+var_70], rax
0x140011d14  lea     rdx, [rbp+57h+var_88]
0x140011d18  lea     rcx, [rbp+57h+var_80]
0x140011d1c  call    ??0?$CComPtr@UIXMLDOMNodeList@@@ATL@@QEAA@AEBV01@@Z; ATL::CComPtr<IXMLDOMNodeList>::CComPtr<IXMLDOMNodeList>(ATL::CComPtr<IXMLDOMNodeList> const &)
0x140011d21  nop
0x140011d22  mov     rdx, rax
0x140011d25  mov     rcx, rbx
0x140011d28  call    ??0CNode@Xml@Util@Sharp@@QEAA@V?$CComPtr@UIXMLDOMNode@@@ATL@@@Z; Sharp::Util::Xml::CNode::CNode(ATL::CComPtr<IXMLDOMNode>)
0x140011d2d  mov     [rbp+57h+var_90], 1
0x140011d34  lea     rcx, [rbp+57h+var_88]
0x140011d38  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x140011d3d  mov     rax, rbx
0x140011d40  mov     rcx, [rbp+57h+var_20]
0x140011d44  xor     rcx, rsp; StackCookie
0x140011d47  call    __security_check_cookie
0x140011d4c  mov     rbx, [rsp+0B0h+arg_10]
0x140011d54  add     rsp, 0A0h
0x140011d5b  pop     rdi
0x140011d5c  pop     rsi
0x140011d5d  pop     rbp
0x140011d5e  retn
```
