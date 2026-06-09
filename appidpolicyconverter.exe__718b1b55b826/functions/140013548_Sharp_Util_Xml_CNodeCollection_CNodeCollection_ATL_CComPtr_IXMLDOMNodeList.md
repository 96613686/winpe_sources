# Sharp::Util::Xml::CNodeCollection::CNodeCollection(ATL::CComPtr<IXMLDOMNodeList>)

- ea: `0x140013548`
- end: `0x140013776`
- name: `??0CNodeCollection@Xml@Util@Sharp@@QEAA@V?$CComPtr@UIXMLDOMNodeList@@@ATL@@@Z`
- size: `558`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140012950`

## callees

- `0x140001d1c`
- `0x1400070e4`
- `0x140007428`
- `0x140011888`
- `0x140011974`
- `0x1400119d4`
- `0x140011a6c`
- `0x140011fa0`
- `0x140012138`
- `0x140013524`
- `0x140013548`
- `0x1400137d8`
- `0x140013b10`
- `0x140016010`

## pseudocode

```c
_QWORD *__fastcall Sharp::Util::Xml::CNodeCollection::CNodeCollection(_QWORD *a1, _QWORD *a2)
{
  _QWORD *v4; // rcx
  __int64 v5; // r9
  int v6; // eax
  int v7; // esi
  unsigned int i; // r14d
  int v9; // eax
  int v10; // esi
  __int64 *v11; // rax
  Sharp::Util::Xml::CNode *v12; // rax
  int v14; // [rsp+20h] [rbp-79h] BYREF
  __int64 v15; // [rsp+28h] [rbp-71h] BYREF
  __int64 v16; // [rsp+30h] [rbp-69h] BYREF
  _QWORD v17[6]; // [rsp+38h] [rbp-61h] BYREF
  _BYTE v18[24]; // [rsp+68h] [rbp-31h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+80h] [rbp-19h] BYREF

  v17[2] = a1;
  v17[3] = a2;
  *a1 = &Sharp::Util::Xml::CNodeCollection::`vftable';
  std::list<Sharp::Util::Xml::CNode>::list<Sharp::Util::Xml::CNode>(a1 + 1);
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_aa5cb3998772301bcbc4f4136f5a9bc8_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  v5 = *a2;
  if ( !*a2 )
  {
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 )
      WPP_SF_(v4[2], 12, WPP_aa5cb3998772301bcbc4f4136f5a9bc8_Traceguids);
    xml_exception::xml_exception((xml_exception *)pExceptionObject, -2147024809);
    throw (xml_exception *)pExceptionObject;
  }
  v14 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v5 + 64LL))(v5, &v14);
  v7 = v6;
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        WPP_aa5cb3998772301bcbc4f4136f5a9bc8_Traceguids,
        (unsigned int)v6);
    xml_exception::xml_exception((xml_exception *)pExceptionObject, v7);
    throw (xml_exception *)pExceptionObject;
  }
  for ( i = 0; (int)i < v14; ++i )
  {
    v15 = 0;
    v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(*(_QWORD *)*a2 + 56LL))(*a2, i, &v15);
    v10 = v9;
    if ( v9 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          WPP_aa5cb3998772301bcbc4f4136f5a9bc8_Traceguids,
          (unsigned int)v9);
      xml_exception::xml_exception((xml_exception *)pExceptionObject, v10);
      throw (xml_exception *)pExceptionObject;
    }
    v17[4] = &v16;
    v11 = ATL::CComPtr<IXMLDOMNodeList>::CComPtr<IXMLDOMNodeList>(&v16, &v15);
    Sharp::Util::Xml::CNode::CNode(v17, (struct IUnknown **)v11);
    v17[5] = v18;
    v12 = Sharp::Util::Xml::CNode::CNode((Sharp::Util::Xml::CNode *)v18, (const struct Sharp::Util::Xml::CNode *)v17);
    Sharp::Util::Xml::CNodeCollection::Add(a1, v12);
    Sharp::Util::Xml::CNode::~CNode((Sharp::Util::Xml::CNode *)v17);
    ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v15);
  }
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(a2);
  return a1;
}

```

## disassembly

```asm
0x140013548  mov     [rsp-8+arg_10], rbx
0x14001354d  push    rbp
0x14001354e  push    rsi
0x14001354f  push    rdi
0x140013550  push    r14
0x140013552  push    r15
0x140013554  lea     rbp, [rsp-37h]
0x140013559  sub     rsp, 0D0h
0x140013560  mov     rax, cs:__security_cookie
0x140013567  xor     rax, rsp
0x14001356a  mov     [rbp+57h+var_30], rax
0x14001356e  mov     rdi, rdx
0x140013571  mov     rbx, rcx
0x140013574  mov     [rbp+57h+var_A8], rcx
0x140013578  mov     [rbp+57h+var_A0], rdx
0x14001357c  lea     rax, ??_7CNodeCollection@Xml@Util@Sharp@@6B@; const Sharp::Util::Xml::CNodeCollection::`vftable'
0x140013583  mov     [rcx], rax
0x140013586  add     rcx, 8
0x14001358a  call    ??0?$list@VCNode@Xml@Util@Sharp@@V?$allocator@VCNode@Xml@Util@Sharp@@@std@@@std@@QEAA@XZ; std::list<Sharp::Util::Xml::CNode>::list<Sharp::Util::Xml::CNode>(void)
0x14001358f  nop
0x140013590  lea     r15, WPP_GLOBAL_Control
0x140013597  mov     rcx, cs:WPP_GLOBAL_Control
0x14001359e  cmp     rcx, r15
0x1400135a1  jz      short loc_1400135C5
0x1400135a3  test    byte ptr [rcx+1Ch], 8
0x1400135a7  jz      short loc_1400135C5
0x1400135a9  mov     edx, 0Bh
0x1400135ae  lea     r8, WPP_aa5cb3998772301bcbc4f4136f5a9bc8_Traceguids
0x1400135b5  mov     rcx, [rcx+10h]
0x1400135b9  call    WPP_SF_
0x1400135be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400135c5  mov     r9, [rdi]
0x1400135c8  test    r9, r9
0x1400135cb  jnz     short loc_14001360B
0x1400135cd  cmp     rcx, r15
0x1400135d0  jz      short loc_1400135EC
0x1400135d2  test    byte ptr [rcx+1Ch], 1
0x1400135d6  jz      short loc_1400135EC
0x1400135d8  lea     edx, [r9+0Ch]
0x1400135dc  lea     r8, WPP_aa5cb3998772301bcbc4f4136f5a9bc8_Traceguids
0x1400135e3  mov     rcx, [rcx+10h]
0x1400135e7  call    WPP_SF_
0x1400135ec  mov     edx, 80070057h; int
0x1400135f1  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1400135f5  call    ??0xml_exception@@QEAA@J@Z; xml_exception::xml_exception(long)
0x1400135fa  lea     rdx, _TI3?AVxml_exception@@; pThrowInfo
0x140013601  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140013605  call    _CxxThrowException_0
0x14001360b  mov     [rbp+57h+var_D0], 0
0x140013612  mov     rax, [r9]
0x140013615  lea     rdx, [rbp+57h+var_D0]
0x140013619  mov     rcx, r9
0x14001361c  mov     rax, [rax+40h]
0x140013620  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013625  mov     esi, eax
0x140013627  test    eax, eax
0x140013629  jns     short loc_140013671
0x14001362b  mov     rcx, cs:WPP_GLOBAL_Control
0x140013632  cmp     rcx, r15
0x140013635  jz      short loc_140013655
0x140013637  test    byte ptr [rcx+1Ch], 1
0x14001363b  jz      short loc_140013655
0x14001363d  mov     edx, 0Dh
0x140013642  mov     r9d, eax
0x140013645  lea     r8, WPP_aa5cb3998772301bcbc4f4136f5a9bc8_Traceguids
0x14001364c  mov     rcx, [rcx+10h]
0x140013650  call    WPP_SF_d
0x140013655  mov     edx, esi; int
0x140013657  lea     rcx, [rbp+57h+pExceptionObject]; this
0x14001365b  call    ??0xml_exception@@QEAA@J@Z; xml_exception::xml_exception(long)
0x140013660  lea     rdx, _TI3?AVxml_exception@@; pThrowInfo
0x140013667  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14001366b  call    _CxxThrowException_0
0x140013671  xor     r14d, r14d
0x140013674  cmp     r14d, [rbp+57h+var_D0]
0x140013678  jge     loc_140013748
0x14001367e  mov     [rbp+57h+var_C8], 0
0x140013686  mov     rcx, [rdi]
0x140013689  mov     rax, [rcx]
0x14001368c  lea     r8, [rbp+57h+var_C8]
0x140013690  mov     edx, r14d
0x140013693  mov     rax, [rax+38h]
0x140013697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001369c  mov     esi, eax
0x14001369e  test    eax, eax
0x1400136a0  js      short loc_140013702
0x1400136a2  lea     rax, [rbp+57h+var_C0]
0x1400136a6  mov     [rbp+57h+var_98], rax
0x1400136aa  lea     rdx, [rbp+57h+var_C8]
0x1400136ae  lea     rcx, [rbp+57h+var_C0]
0x1400136b2  call    ??0?$CComPtr@UIXMLDOMNodeList@@@ATL@@QEAA@AEBV01@@Z; ATL::CComPtr<IXMLDOMNodeList>::CComPtr<IXMLDOMNodeList>(ATL::CComPtr<IXMLDOMNodeList> const &)
0x1400136b7  nop
0x1400136b8  mov     rdx, rax
0x1400136bb  lea     rcx, [rbp+57h+var_B8]
0x1400136bf  call    ??0CNode@Xml@Util@Sharp@@QEAA@V?$CComPtr@UIXMLDOMNode@@@ATL@@@Z; Sharp::Util::Xml::CNode::CNode(ATL::CComPtr<IXMLDOMNode>)
0x1400136c4  nop
0x1400136c5  lea     rax, [rbp+57h+var_88]
0x1400136c9  mov     [rbp+57h+var_90], rax
0x1400136cd  lea     rdx, [rbp+57h+var_B8]; struct Sharp::Util::Xml::CNode *
0x1400136d1  lea     rcx, [rbp+57h+var_88]; this
0x1400136d5  call    ??0CNode@Xml@Util@Sharp@@QEAA@AEBV0123@@Z; Sharp::Util::Xml::CNode::CNode(Sharp::Util::Xml::CNode const &)
0x1400136da  nop
0x1400136db  mov     rdx, rax
0x1400136de  mov     rcx, rbx
0x1400136e1  call    ?Add@CNodeCollection@Xml@Util@Sharp@@QEAAXVCNode@234@@Z; Sharp::Util::Xml::CNodeCollection::Add(Sharp::Util::Xml::CNode)
0x1400136e6  nop
0x1400136e7  lea     rcx, [rbp+57h+var_B8]; this
0x1400136eb  call    ??1CNode@Xml@Util@Sharp@@UEAA@XZ; Sharp::Util::Xml::CNode::~CNode(void)
0x1400136f0  nop
0x1400136f1  lea     rcx, [rbp+57h+var_C8]
0x1400136f5  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x1400136fa  inc     r14d
0x1400136fd  jmp     loc_140013674
0x140013702  mov     rcx, cs:WPP_GLOBAL_Control
0x140013709  cmp     rcx, r15
0x14001370c  jz      short loc_14001372C
0x14001370e  test    byte ptr [rcx+1Ch], 1
0x140013712  jz      short loc_14001372C
0x140013714  mov     edx, 0Eh
0x140013719  mov     r9d, esi
0x14001371c  lea     r8, WPP_aa5cb3998772301bcbc4f4136f5a9bc8_Traceguids
0x140013723  mov     rcx, [rcx+10h]
0x140013727  call    WPP_SF_d
0x14001372c  mov     edx, esi; int
0x14001372e  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140013732  call    ??0xml_exception@@QEAA@J@Z; xml_exception::xml_exception(long)
0x140013737  lea     rdx, _TI3?AVxml_exception@@; pThrowInfo
0x14001373e  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140013742  call    _CxxThrowException_0
0x140013748  mov     rcx, rdi
0x14001374b  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x140013750  mov     rax, rbx
0x140013753  mov     rcx, [rbp+57h+var_30]
0x140013757  xor     rcx, rsp; StackCookie
0x14001375a  call    __security_check_cookie
0x14001375f  mov     rbx, [rsp+0F0h+arg_10]
0x140013767  add     rsp, 0D0h
0x14001376e  pop     r15
0x140013770  pop     r14
0x140013772  pop     rdi
0x140013773  pop     rsi
0x140013774  pop     rbp
0x140013775  retn
```
