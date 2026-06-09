# Sharp::Util::Xml::CNode::HasAttribute(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x140012e1c`
- end: `0x140012f17`
- name: `?HasAttribute@CNode@Xml@Util@Sharp@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `251`
- prototype: `char __fastcall(__int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140010d90`

## callees

- `0x1400070e4`
- `0x140007de4`
- `0x140011a6c`
- `0x140012e1c`
- `0x140016010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140012ecb`
- `OLEAUT32!__imp_SysFreeString` at `0x140012ecb`

## pseudocode

```c
char __fastcall Sharp::Util::Xml::CNode::HasAttribute(__int64 a1, const unsigned __int16 *a2)
{
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, _QWORD, __int64 *); // rsi
  ATL::CComBSTR *v6; // rax
  int v7; // ebx
  __int64 v9; // [rsp+40h] [rbp+20h] BYREF
  __int64 v10; // [rsp+50h] [rbp+30h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp+38h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids);
  v9 = 0;
  if ( (*(int (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(a1 + 8) + 136LL))(*(_QWORD *)(a1 + 8), &v9) >= 0 && v9 )
  {
    v10 = 0;
    v4 = v9;
    v5 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v9 + 56LL);
    if ( *((_QWORD *)a2 + 3) >= 8u )
      a2 = *(const unsigned __int16 **)a2;
    v6 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, a2);
    v7 = v5(v4, *(_QWORD *)v6, &v10);
    SysFreeString(bstrString);
    if ( v7 >= 0 && v10 )
    {
      ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v10);
      ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v9);
      return 1;
    }
    ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v10);
  }
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v9);
  return 0;
}

```

## disassembly

```asm
0x140012e1c  mov     [rsp-18h+arg_8], rbx
0x140012e21  push    rbp
0x140012e22  push    rsi
0x140012e23  push    rdi
0x140012e24  mov     rbp, rsp
0x140012e27  sub     rsp, 20h
0x140012e2b  mov     rbx, rdx
0x140012e2e  mov     rdi, rcx
0x140012e31  lea     rax, WPP_GLOBAL_Control
0x140012e38  mov     rcx, cs:WPP_GLOBAL_Control
0x140012e3f  cmp     rcx, rax
0x140012e42  jz      short loc_140012E5F
0x140012e44  test    byte ptr [rcx+1Ch], 8
0x140012e48  jz      short loc_140012E5F
0x140012e4a  mov     edx, 29h ; ')'
0x140012e4f  lea     r8, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids
0x140012e56  mov     rcx, [rcx+10h]
0x140012e5a  call    WPP_SF_
0x140012e5f  mov     [rbp+arg_0], 0
0x140012e67  mov     rcx, [rdi+8]
0x140012e6b  mov     rax, [rcx]
0x140012e6e  lea     rdx, [rbp+arg_0]
0x140012e72  mov     rax, [rax+88h]
0x140012e79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012e7e  test    eax, eax
0x140012e80  js      short loc_140012EFF
0x140012e82  cmp     [rbp+arg_0], 0
0x140012e87  jz      short loc_140012EFF
0x140012e89  mov     [rbp+arg_10], 0
0x140012e91  mov     rdi, [rbp+arg_0]
0x140012e95  mov     rax, [rdi]
0x140012e98  mov     rsi, [rax+38h]
0x140012e9c  cmp     qword ptr [rbx+18h], 8
0x140012ea1  jb      short loc_140012EA6
0x140012ea3  mov     rbx, [rbx]
0x140012ea6  mov     rdx, rbx; unsigned __int16 *
0x140012ea9  lea     rcx, [rbp+bstrString]; this
0x140012ead  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x140012eb2  nop
0x140012eb3  lea     r8, [rbp+arg_10]
0x140012eb7  mov     rdx, [rax]
0x140012eba  mov     rcx, rdi
0x140012ebd  mov     rax, rsi
0x140012ec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012ec5  mov     ebx, eax
0x140012ec7  mov     rcx, [rbp+bstrString]; bstrString
0x140012ecb  call    cs:__imp_SysFreeString
0x140012ed1  test    ebx, ebx
0x140012ed3  js      short loc_140012EF3
0x140012ed5  cmp     [rbp+arg_10], 0
0x140012eda  jz      short loc_140012EF3
0x140012edc  lea     rcx, [rbp+arg_10]
0x140012ee0  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x140012ee5  nop
0x140012ee6  lea     rcx, [rbp+arg_0]
0x140012eea  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x140012eef  mov     al, 1
0x140012ef1  jmp     short loc_140012F0A
0x140012ef3  lea     rcx, [rbp+arg_10]
0x140012ef7  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x140012efc  nop
0x140012efd  jmp     short $+2
0x140012eff  lea     rcx, [rbp+arg_0]
0x140012f03  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x140012f08  xor     al, al
0x140012f0a  mov     rbx, [rsp+20h+arg_8]
0x140012f0f  add     rsp, 20h
0x140012f13  pop     rdi
0x140012f14  pop     rsi
0x140012f15  pop     rbp
0x140012f16  retn
```
