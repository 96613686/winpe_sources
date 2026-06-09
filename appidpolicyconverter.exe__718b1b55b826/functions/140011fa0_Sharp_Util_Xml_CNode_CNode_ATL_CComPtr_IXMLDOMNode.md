# Sharp::Util::Xml::CNode::CNode(ATL::CComPtr<IXMLDOMNode>)

- ea: `0x140011fa0`
- end: `0x1400120a5`
- name: `??0CNode@Xml@Util@Sharp@@QEAA@V?$CComPtr@UIXMLDOMNode@@@ATL@@@Z`
- size: `261`
- prototype: `_QWORD *__fastcall(_QWORD *, struct IUnknown **)`
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140011c40`
- `0x140012764`
- `0x140012b94`
- `0x140013548`

## callees

- `0x140001d1c`
- `0x1400070e4`
- `0x1400119d4`
- `0x140011a6c`
- `0x140011be8`
- `0x140011fa0`
- `0x140013b10`

## pseudocode

```c
_QWORD *__fastcall Sharp::Util::Xml::CNode::CNode(_QWORD *a1, struct IUnknown **a2)
{
  struct IUnknown **v4; // rbx
  _QWORD *v5; // rcx
  struct IUnknown *v6; // rdx
  _BYTE pExceptionObject[64]; // [rsp+40h] [rbp-68h] BYREF

  *a1 = &Sharp::Util::Xml::CNode::`vftable';
  v4 = (struct IUnknown **)(a1 + 1);
  a1[1] = 0;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids);
    v5 = WPP_GLOBAL_Control;
  }
  v6 = *a2;
  if ( !*a2 )
  {
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 )
      WPP_SF_(v5[2], 11, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids);
    xml_exception::xml_exception((xml_exception *)pExceptionObject, -2147024809);
    throw (xml_exception *)pExceptionObject;
  }
  if ( *v4 != v6 )
    ATL::AtlComPtrAssign(v4, v6);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(a2);
  return a1;
}

```

## disassembly

```asm
0x140011fa0  mov     [rsp+arg_10], rbx
0x140011fa5  push    rbp
0x140011fa6  push    rsi
0x140011fa7  push    rdi
0x140011fa8  sub     rsp, 90h
0x140011faf  mov     rax, cs:__security_cookie
0x140011fb6  xor     rax, rsp
0x140011fb9  mov     [rsp+0A8h+var_28], rax
0x140011fc1  mov     rdi, rdx
0x140011fc4  mov     rsi, rcx
0x140011fc7  mov     [rsp+0A8h+var_88], rcx
0x140011fcc  mov     [rsp+0A8h+var_80], rdx
0x140011fd1  lea     rax, ??_7CNode@Xml@Util@Sharp@@6B@; const Sharp::Util::Xml::CNode::`vftable'
0x140011fd8  mov     [rcx], rax
0x140011fdb  lea     rbx, [rcx+8]
0x140011fdf  mov     [rsp+0A8h+var_78], rbx
0x140011fe4  mov     qword ptr [rbx], 0
0x140011feb  lea     rbp, WPP_GLOBAL_Control
0x140011ff2  mov     rcx, cs:WPP_GLOBAL_Control
0x140011ff9  cmp     rcx, rbp
0x140011ffc  jz      short loc_140012020
0x140011ffe  test    byte ptr [rcx+1Ch], 8
0x140012002  jz      short loc_140012020
0x140012004  mov     edx, 0Ah
0x140012009  lea     r8, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids
0x140012010  mov     rcx, [rcx+10h]
0x140012014  call    WPP_SF_
0x140012019  mov     rcx, cs:WPP_GLOBAL_Control
0x140012020  mov     rdx, [rdi]; struct IUnknown *
0x140012023  test    rdx, rdx
0x140012026  jnz     short loc_140012069
0x140012028  cmp     rcx, rbp
0x14001202b  jz      short loc_140012048
0x14001202d  test    byte ptr [rcx+1Ch], 1
0x140012031  jz      short loc_140012048
0x140012033  mov     edx, 0Bh
0x140012038  lea     r8, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids
0x14001203f  mov     rcx, [rcx+10h]
0x140012043  call    WPP_SF_
0x140012048  mov     edx, 80070057h; int
0x14001204d  lea     rcx, [rsp+0A8h+pExceptionObject]; this
0x140012052  call    ??0xml_exception@@QEAA@J@Z; xml_exception::xml_exception(long)
0x140012057  lea     rdx, _TI3?AVxml_exception@@; pThrowInfo
0x14001205e  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x140012063  call    _CxxThrowException_0
0x140012069  cmp     [rbx], rdx
0x14001206c  jz      short loc_140012077
0x14001206e  mov     rcx, rbx; struct IUnknown **
0x140012071  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x140012076  nop
0x140012077  mov     rcx, rdi
0x14001207a  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x14001207f  mov     rax, rsi
0x140012082  mov     rcx, [rsp+0A8h+var_28]
0x14001208a  xor     rcx, rsp; StackCookie
0x14001208d  call    __security_check_cookie
0x140012092  mov     rbx, [rsp+0A8h+arg_10]
0x14001209a  add     rsp, 90h
0x1400120a1  pop     rdi
0x1400120a2  pop     rsi
0x1400120a3  pop     rbp
0x1400120a4  retn
```
