# XcGetSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)

- ea: `0x1800131e4`
- end: `0x180013277`
- name: `?XcGetSingleNode@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z`
- size: `147`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, const unsigned __int16 *, struct IXMLDOMNode **)`
- caller_count: `7`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b4b0`
- `0x18000bbd8`
- `0x18000c4a0`
- `0x18000cf80`
- `0x18000f1d8`
- `0x180011164`
- `0x180012db0`

## callees

- `0x1800030fc`
- `0x1800130e0`
- `0x1800131e4`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall XcGetSingleNode(struct IXMLDOMNode *a1, const unsigned __int16 *a2, struct IXMLDOMNode **a3)
{
  unsigned int Nodes; // ebx
  int v5; // eax
  struct IXMLDOMNodeList *v7[3]; // [rsp+20h] [rbp-18h] BYREF
  int v8; // [rsp+58h] [rbp+20h] BYREF

  v7[0] = 0;
  v8 = 0;
  Nodes = XcGetNodes(a1, a2, v7, &v8);
  if ( !Nodes )
  {
    if ( v8 > 0 )
    {
      if ( v8 <= 1 )
      {
        v5 = ((__int64 (__fastcall *)(struct IXMLDOMNodeList *, _QWORD, struct IXMLDOMNode **))v7[0]->lpVtbl->get_item)(
               v7[0],
               0,
               a3);
        Nodes = v5;
        if ( v5 < 0 )
        {
          if ( (v5 & 0x1FFF0000) == 0x70000 )
            Nodes = (unsigned __int16)v5;
        }
        else
        {
          Nodes = 0;
        }
      }
      else
      {
        Nodes = 1206;
      }
    }
    else
    {
      Nodes = 1168;
    }
  }
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)v7);
  return Nodes;
}

```

## disassembly

```asm
0x1800131e4  mov     rax, rsp
0x1800131e7  mov     [rax+8], rbx
0x1800131eb  push    rdi
0x1800131ec  sub     rsp, 30h
0x1800131f0  mov     rdi, r8
0x1800131f3  mov     qword ptr [rax-18h], 0
0x1800131fb  mov     dword ptr [rax+20h], 0
0x180013202  lea     r9, [rax+20h]; int *
0x180013206  lea     r8, [rax-18h]; struct IXMLDOMNodeList **
0x18001320a  call    ?XcGetNodes@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAUIXMLDOMNodeList@@PEAJ@Z; XcGetNodes(IXMLDOMNode *,ushort const *,IXMLDOMNodeList * *,long *)
0x18001320f  mov     ebx, eax
0x180013211  test    eax, eax
0x180013213  jnz     short loc_18001325F
0x180013215  mov     eax, [rsp+38h+arg_18]
0x180013219  test    eax, eax
0x18001321b  jg      short loc_180013224
0x18001321d  mov     ebx, 490h
0x180013222  jmp     short loc_18001325F
0x180013224  cmp     eax, 1
0x180013227  jle     short loc_180013230
0x180013229  mov     ebx, 4B6h
0x18001322e  jmp     short loc_18001325F
0x180013230  mov     rcx, [rsp+38h+var_18]
0x180013235  mov     rax, [rcx]
0x180013238  mov     r8, rdi
0x18001323b  xor     edx, edx
0x18001323d  mov     rax, [rax+38h]
0x180013241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013246  mov     ebx, eax
0x180013248  test    eax, eax
0x18001324a  js      short loc_180013250
0x18001324c  xor     ebx, ebx
0x18001324e  jmp     short loc_18001325F
0x180013250  and     eax, 1FFF0000h
0x180013255  cmp     eax, 70000h
0x18001325a  jnz     short loc_18001325F
0x18001325c  movzx   ebx, bx
0x18001325f  lea     rcx, [rsp+38h+var_18]
0x180013264  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180013269  nop
0x18001326a  mov     eax, ebx
0x18001326c  mov     rbx, [rsp+38h+arg_0]
0x180013271  add     rsp, 30h
0x180013275  pop     rdi
0x180013276  retn
```
