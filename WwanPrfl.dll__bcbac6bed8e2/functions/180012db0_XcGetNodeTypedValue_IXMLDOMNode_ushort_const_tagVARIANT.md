# XcGetNodeTypedValue(IXMLDOMNode *,ushort const *,tagVARIANT *)

- ea: `0x180012db0`
- end: `0x180012e85`
- name: `?XcGetNodeTypedValue@@YAKPEAUIXMLDOMNode@@PEBGPEAUtagVARIANT@@@Z`
- size: `213`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, const unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001288c`
- `0x180012968`
- `0x180012a4c`
- `0x180012bc8`

## callees

- `0x1800030fc`
- `0x180012db0`
- `0x1800131e4`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall XcGetNodeTypedValue(struct IXMLDOMNode *a1, const unsigned __int16 *a2, struct tagVARIANT *a3)
{
  unsigned int SingleNode; // ebx
  struct IXMLDOMNode *v6; // rcx
  int v7; // eax
  struct IXMLDOMNode *v9; // [rsp+38h] [rbp+10h] BYREF

  v9 = 0;
  if ( a2 )
  {
    SingleNode = XcGetSingleNode(a1, a2, &v9);
    if ( SingleNode )
      goto LABEL_16;
    v6 = v9;
  }
  else
  {
    SingleNode = 0;
    v6 = v9;
    if ( v9 != a1 )
    {
      if ( a1 )
      {
        ((void (__fastcall *)(struct IXMLDOMNode *))a1->lpVtbl->AddRef)(a1);
        v6 = v9;
      }
      if ( v6 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v6->lpVtbl->Release)(v6);
      v6 = a1;
      v9 = a1;
    }
  }
  v7 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct tagVARIANT *))v6->lpVtbl->get_nodeTypedValue)(v6, a3);
  if ( v7 < 0 )
  {
    SingleNode = (unsigned __int16)v7;
    if ( (v7 & 0x1FFF0000) != 0x70000 )
      SingleNode = v7;
  }
  else if ( a3->vt != 8 || !a3->llVal )
  {
    SingleNode = 1168;
  }
LABEL_16:
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&v9);
  return SingleNode;
}

```

## disassembly

```asm
0x180012db0  mov     rax, rsp
0x180012db3  mov     [rax+8], rbx
0x180012db7  mov     [rax+18h], rsi
0x180012dbb  push    rdi
0x180012dbc  sub     rsp, 20h
0x180012dc0  mov     rsi, r8
0x180012dc3  mov     rdi, rcx
0x180012dc6  mov     qword ptr [rax+10h], 0
0x180012dce  test    rdx, rdx
0x180012dd1  jz      short loc_180012DED
0x180012dd3  lea     r8, [rax+10h]; struct IXMLDOMNode **
0x180012dd7  call    ?XcGetSingleNode@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; XcGetSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x180012ddc  mov     ebx, eax
0x180012dde  test    eax, eax
0x180012de0  jnz     loc_180012E68
0x180012de6  mov     rcx, [rsp+28h+arg_8]
0x180012deb  jmp     short loc_180012E2B
0x180012ded  xor     ebx, ebx
0x180012def  mov     rcx, [rsp+28h+arg_8]
0x180012df4  cmp     rcx, rdi
0x180012df7  jz      short loc_180012E2B
0x180012df9  test    rdi, rdi
0x180012dfc  jz      short loc_180012E12
0x180012dfe  mov     rax, [rdi]
0x180012e01  mov     rcx, rdi
0x180012e04  mov     rax, [rax+8]
0x180012e08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e0d  mov     rcx, [rsp+28h+arg_8]
0x180012e12  test    rcx, rcx
0x180012e15  jz      short loc_180012E23
0x180012e17  mov     rax, [rcx]
0x180012e1a  mov     rax, [rax+10h]
0x180012e1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e23  mov     rcx, rdi
0x180012e26  mov     [rsp+28h+arg_8], rcx
0x180012e2b  mov     rax, [rcx]
0x180012e2e  mov     rdx, rsi
0x180012e31  mov     rax, [rax+0F0h]
0x180012e38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e3d  mov     ecx, eax
0x180012e3f  test    eax, eax
0x180012e41  js      short loc_180012E57
0x180012e43  cmp     word ptr [rsi], 8
0x180012e47  jnz     short loc_180012E50
0x180012e49  cmp     qword ptr [rsi+8], 0
0x180012e4e  jnz     short loc_180012E68
0x180012e50  mov     ebx, 490h
0x180012e55  jmp     short loc_180012E68
0x180012e57  and     eax, 1FFF0000h
0x180012e5c  cmp     eax, 70000h
0x180012e61  movzx   ebx, cx
0x180012e64  jz      short loc_180012E68
0x180012e66  mov     ebx, ecx
0x180012e68  lea     rcx, [rsp+28h+arg_8]
0x180012e6d  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180012e72  nop
0x180012e73  mov     eax, ebx
0x180012e75  mov     rbx, [rsp+28h+arg_0]
0x180012e7a  mov     rsi, [rsp+28h+arg_10]
0x180012e7f  add     rsp, 20h
0x180012e83  pop     rdi
0x180012e84  retn
```
