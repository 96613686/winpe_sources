# XcGetNodeXmlIndented(IXMLDOMNode *,ushort * *)

- ea: `0x180012fe0`
- end: `0x1800130d9`
- name: `?XcGetNodeXmlIndented@@YAKPEAUIXMLDOMNode@@PEAPEAG@Z`
- size: `249`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000dea0`

## callees

- `0x1800030fc`
- `0x1800125a4`
- `0x180012808`
- `0x180012e8c`
- `0x180012fe0`
- `0x180014010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800130c1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800130c1`

## pseudocode

```c
__int64 __fastcall XcGetNodeXmlIndented(struct IXMLDOMNode *a1, unsigned __int16 **a2)
{
  unsigned int NodeXml; // edi
  int v5; // eax
  struct IXMLDOMDocument2 *v6; // rbx
  int v7; // eax
  BSTR bstrString[3]; // [rsp+20h] [rbp-18h] BYREF
  __int16 v10; // [rsp+50h] [rbp+18h] BYREF
  struct IXMLDOMDocument2 *v11; // [rsp+58h] [rbp+20h] BYREF

  bstrString[0] = 0;
  v11 = 0;
  v10 = 0;
  NodeXml = XcCreateXmlDoc(0, 0, &v11);
  if ( !NodeXml )
  {
    v5 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))a1->lpVtbl->get_xml)(a1, bstrString);
    NodeXml = v5;
    if ( v5 >= 0 )
      goto LABEL_6;
    if ( (v5 & 0x1FFF0000) == 0x70000 )
      NodeXml = (unsigned __int16)v5;
    if ( !NodeXml )
    {
LABEL_6:
      v6 = v11;
      v7 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, BSTR, __int16 *))v11->lpVtbl->loadXML)(
             v11,
             bstrString[0],
             &v10);
      NodeXml = v7;
      if ( v7 >= 0 )
        goto LABEL_16;
      if ( (v7 & 0x1FFF0000) == 0x70000 )
        NodeXml = (unsigned __int16)v7;
      if ( !NodeXml )
      {
LABEL_16:
        if ( v10 == -1 || (NodeXml = XcGetLoadError(v6)) == 0 )
          NodeXml = XcGetNodeXml((struct IXMLDOMNode *)v6, a2);
      }
    }
  }
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&v11);
  SysFreeString(bstrString[0]);
  return NodeXml;
}

```

## disassembly

```asm
0x180012fe0  mov     r11, rsp
0x180012fe3  mov     [r11+8], rbx
0x180012fe7  mov     [r11+10h], rsi
0x180012feb  push    rdi
0x180012fec  sub     rsp, 30h
0x180012ff0  mov     rsi, rdx
0x180012ff3  mov     rbx, rcx
0x180012ff6  mov     qword ptr [r11-18h], 0
0x180012ffe  mov     qword ptr [r11+20h], 0
0x180013006  xor     eax, eax
0x180013008  mov     [rsp+38h+arg_10], ax
0x18001300d  lea     r8, [r11+20h]; struct IXMLDOMDocument2 **
0x180013011  xor     edx, edx; struct IXMLDOMSchemaCollection *
0x180013013  xor     ecx, ecx; psz
0x180013015  call    ?XcCreateXmlDoc@@YAKPEBGPEAUIXMLDOMSchemaCollection@@PEAPEAUIXMLDOMDocument2@@@Z; XcCreateXmlDoc(ushort const *,IXMLDOMSchemaCollection *,IXMLDOMDocument2 * *)
0x18001301a  mov     edi, eax
0x18001301c  test    eax, eax
0x18001301e  jnz     loc_1800130B1
0x180013024  mov     rax, [rbx]
0x180013027  lea     rdx, [rsp+38h+bstrString]
0x18001302c  mov     rcx, rbx
0x18001302f  mov     rax, [rax+110h]
0x180013036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001303b  mov     edi, eax
0x18001303d  test    eax, eax
0x18001303f  jns     short loc_180013054
0x180013041  and     eax, 1FFF0000h
0x180013046  cmp     eax, 70000h
0x18001304b  jnz     short loc_180013050
0x18001304d  movzx   edi, di
0x180013050  test    edi, edi
0x180013052  jnz     short loc_1800130B1
0x180013054  mov     rbx, [rsp+38h+arg_18]
0x180013059  mov     rax, [rbx]
0x18001305c  lea     r8, [rsp+38h+arg_10]
0x180013061  mov     rdx, [rsp+38h+bstrString]
0x180013066  mov     rcx, rbx
0x180013069  mov     rax, [rax+208h]
0x180013070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013075  mov     edi, eax
0x180013077  test    eax, eax
0x180013079  jns     short loc_18001308E
0x18001307b  and     eax, 1FFF0000h
0x180013080  cmp     eax, 70000h
0x180013085  jnz     short loc_18001308A
0x180013087  movzx   edi, di
0x18001308a  test    edi, edi
0x18001308c  jnz     short loc_1800130B1
0x18001308e  cmp     [rsp+38h+arg_10], 0FFFFh
0x180013094  jz      short loc_1800130A4
0x180013096  mov     rcx, rbx; struct IXMLDOMDocument2 *
0x180013099  call    ?XcGetLoadError@@YAKPEAUIXMLDOMDocument2@@@Z; XcGetLoadError(IXMLDOMDocument2 *)
0x18001309e  mov     edi, eax
0x1800130a0  test    eax, eax
0x1800130a2  jnz     short loc_1800130B1
0x1800130a4  mov     rdx, rsi; unsigned __int16 **
0x1800130a7  mov     rcx, rbx; struct IXMLDOMNode *
0x1800130aa  call    ?XcGetNodeXml@@YAKPEAUIXMLDOMNode@@PEAPEAG@Z; XcGetNodeXml(IXMLDOMNode *,ushort * *)
0x1800130af  mov     edi, eax
0x1800130b1  lea     rcx, [rsp+38h+arg_18]
0x1800130b6  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x1800130bb  nop
0x1800130bc  mov     rcx, [rsp+38h+bstrString]; bstrString
0x1800130c1  call    cs:__imp_SysFreeString
0x1800130c7  mov     eax, edi
0x1800130c9  mov     rbx, [rsp+38h+arg_0]
0x1800130ce  mov     rsi, [rsp+38h+arg_8]
0x1800130d3  add     rsp, 30h
0x1800130d7  pop     rdi
0x1800130d8  retn
```
