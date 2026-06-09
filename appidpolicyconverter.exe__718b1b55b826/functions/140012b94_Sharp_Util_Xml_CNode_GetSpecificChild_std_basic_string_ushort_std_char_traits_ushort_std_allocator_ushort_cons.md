# Sharp::Util::Xml::CNode::GetSpecificChild(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x140012b94`
- end: `0x140012c8a`
- name: `?GetSpecificChild@CNode@Xml@Util@Sharp@@QEBA?AV1234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `246`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x14000a560`
- `0x14000cba0`

## callees

- `0x140001d1c`
- `0x1400070e4`
- `0x1400119d4`
- `0x140011e84`
- `0x140011fa0`
- `0x140012950`
- `0x140012b94`
- `0x14001377c`
- `0x140013918`
- `0x140013b10`

## pseudocode

```c
_QWORD *__fastcall Sharp::Util::Xml::CNode::GetSpecificChild(__int64 a1, _QWORD *a2, __int64 a3)
{
  _QWORD *First; // rax
  struct IUnknown **v7; // rax
  _BYTE v9[8]; // [rsp+28h] [rbp-A0h] BYREF
  _QWORD *v10; // [rsp+30h] [rbp-98h]
  _BYTE *v11; // [rsp+38h] [rbp-90h]
  _QWORD v12[4]; // [rsp+40h] [rbp-88h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+60h] [rbp-68h] BYREF

  v10 = a2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids);
  Sharp::Util::Xml::CNode::GetChilds(a1, v12);
  First = Sharp::Util::Xml::CNodeCollection::FindFirst((__int64)v12, a3);
  if ( !First )
  {
    xml_exception::xml_exception((xml_exception *)pExceptionObject, -2147024809);
    throw (xml_exception *)pExceptionObject;
  }
  v11 = v9;
  v7 = (struct IUnknown **)Sharp::Util::Xml::CNode::ToDom(First, v9);
  Sharp::Util::Xml::CNode::CNode(a2, v7);
  Sharp::Util::Xml::CNodeCollection::~CNodeCollection((Sharp::Util::Xml::CNodeCollection *)v12);
  return a2;
}

```

## disassembly

```asm
0x140012b94  push    rbx
0x140012b96  push    rsi
0x140012b97  push    rdi
0x140012b98  sub     rsp, 0B0h
0x140012b9f  mov     rax, cs:__security_cookie
0x140012ba6  xor     rax, rsp
0x140012ba9  mov     [rsp+0C8h+var_28], rax
0x140012bb1  mov     rsi, r8
0x140012bb4  mov     rbx, rdx
0x140012bb7  mov     rdi, rcx
0x140012bba  mov     [rsp+0C8h+var_98], rdx
0x140012bbf  mov     [rsp+0C8h+var_A8], 0
0x140012bc7  lea     rax, WPP_GLOBAL_Control
0x140012bce  mov     rcx, cs:WPP_GLOBAL_Control
0x140012bd5  cmp     rcx, rax
0x140012bd8  jz      short loc_140012BF5
0x140012bda  test    byte ptr [rcx+1Ch], 8
0x140012bde  jz      short loc_140012BF5
0x140012be0  mov     edx, 17h
0x140012be5  lea     r8, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids
0x140012bec  mov     rcx, [rcx+10h]
0x140012bf0  call    WPP_SF_
0x140012bf5  lea     rdx, [rsp+0C8h+var_88]
0x140012bfa  mov     rcx, rdi
0x140012bfd  call    ?GetChilds@CNode@Xml@Util@Sharp@@QEBA?AVCNodeCollection@234@XZ; Sharp::Util::Xml::CNode::GetChilds(void)
0x140012c02  nop
0x140012c03  mov     rdx, rsi
0x140012c06  lea     rcx, [rsp+0C8h+var_88]
0x140012c0b  call    ?FindFirst@CNodeCollection@Xml@Util@Sharp@@QEBAPEBVCNode@234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Sharp::Util::Xml::CNodeCollection::FindFirst(std::wstring const &)
0x140012c10  test    rax, rax
0x140012c13  jnz     short loc_140012C36
0x140012c15  mov     edx, 80070057h; int
0x140012c1a  lea     rcx, [rsp+0C8h+pExceptionObject]; this
0x140012c1f  call    ??0xml_exception@@QEAA@J@Z; xml_exception::xml_exception(long)
0x140012c24  lea     rdx, _TI3?AVxml_exception@@; pThrowInfo
0x140012c2b  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x140012c30  call    _CxxThrowException_0
0x140012c36  lea     rcx, [rsp+0C8h+var_A0]
0x140012c3b  mov     [rsp+0C8h+var_90], rcx
0x140012c40  lea     rdx, [rsp+0C8h+var_A0]
0x140012c45  mov     rcx, rax
0x140012c48  call    ?ToDom@CNode@Xml@Util@Sharp@@QEBA?AV?$CComPtr@UIXMLDOMNode@@@ATL@@XZ; Sharp::Util::Xml::CNode::ToDom(void)
0x140012c4d  nop
0x140012c4e  mov     rdx, rax
0x140012c51  mov     rcx, rbx
0x140012c54  call    ??0CNode@Xml@Util@Sharp@@QEAA@V?$CComPtr@UIXMLDOMNode@@@ATL@@@Z; Sharp::Util::Xml::CNode::CNode(ATL::CComPtr<IXMLDOMNode>)
0x140012c59  mov     [rsp+0C8h+var_A8], 1
0x140012c61  lea     rcx, [rsp+0C8h+var_88]; this
0x140012c66  call    ??1CNodeCollection@Xml@Util@Sharp@@UEAA@XZ; Sharp::Util::Xml::CNodeCollection::~CNodeCollection(void)
0x140012c6b  mov     rax, rbx
0x140012c6e  mov     rcx, [rsp+0C8h+var_28]
0x140012c76  xor     rcx, rsp; StackCookie
0x140012c79  call    __security_check_cookie
0x140012c7e  add     rsp, 0B0h
0x140012c85  pop     rdi
0x140012c86  pop     rsi
0x140012c87  pop     rbx
0x140012c88  retn
```
