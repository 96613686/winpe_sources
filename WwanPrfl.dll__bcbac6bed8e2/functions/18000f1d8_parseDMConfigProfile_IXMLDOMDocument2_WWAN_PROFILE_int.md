# _parseDMConfigProfile(IXMLDOMDocument2 *,WWAN_PROFILE *,int)

- ea: `0x18000f1d8`
- end: `0x18000f266`
- name: `?_parseDMConfigProfile@@YAKPEAUIXMLDOMDocument2@@PEAUWWAN_PROFILE@@H@Z`
- size: `142`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, struct WWAN_PROFILE *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000e2f0`
- `0x18000e3f0`

## callees

- `0x18000f1d8`
- `0x18000f26c`
- `0x1800131e4`
- `0x180014010`

## string_xrefs

- `0x18000f1fa`: `MBNProfileV4:ModemDMConfigProfile`

## pseudocode

```c
__int64 __fastcall _parseDMConfigProfile(struct IXMLDOMNode *a1, struct WWAN_PROFILE *a2, int a3)
{
  unsigned int SingleNode; // ebx
  struct IXMLDOMNode *v7; // [rsp+48h] [rbp+20h] BYREF

  v7 = 0;
  SingleNode = XcGetSingleNode(a1, L"MBNProfileV4:ModemDMConfigProfile", &v7);
  if ( SingleNode )
  {
    if ( v7 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v7->lpVtbl->Release)(v7);
  }
  else
  {
    SingleNode = parseDMConfigRootNodeExt(v7, (unsigned __int16 *)a2, a3, 2u);
    if ( v7 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v7->lpVtbl->Release)(v7);
  }
  return SingleNode;
}

```

## disassembly

```asm
0x18000f1d8  mov     rax, rsp
0x18000f1db  mov     [rax+8], rbx
0x18000f1df  mov     [rax+10h], rsi
0x18000f1e3  push    rdi
0x18000f1e4  sub     rsp, 20h
0x18000f1e8  mov     edi, r8d
0x18000f1eb  mov     rsi, rdx
0x18000f1ee  mov     qword ptr [rax+20h], 0
0x18000f1f6  lea     r8, [rax+20h]; struct IXMLDOMNode **
0x18000f1fa  lea     rdx, aMbnprofilev4Mo; "MBNProfileV4:ModemDMConfigProfile"
0x18000f201  call    ?XcGetSingleNode@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; XcGetSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18000f206  mov     ebx, eax
0x18000f208  test    eax, eax
0x18000f20a  jz      short loc_18000F225
0x18000f20c  mov     rcx, [rsp+28h+arg_18]
0x18000f211  test    rcx, rcx
0x18000f214  jz      short loc_18000F223
0x18000f216  mov     rax, [rcx]
0x18000f219  mov     rax, [rax+10h]
0x18000f21d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f222  nop
0x18000f223  jmp     short loc_18000F254
0x18000f225  mov     r9d, 2; unsigned int
0x18000f22b  mov     r8d, edi; int
0x18000f22e  mov     rdx, rsi; unsigned __int16 *
0x18000f231  mov     rcx, [rsp+28h+arg_18]; struct IXMLDOMNode *
0x18000f236  call    _parseDMConfigRootNodeExt
0x18000f23b  mov     ebx, eax
0x18000f23d  mov     rcx, [rsp+28h+arg_18]
0x18000f242  test    rcx, rcx
0x18000f245  jz      short loc_18000F254
0x18000f247  mov     rdx, [rcx]
0x18000f24a  mov     rax, [rdx+10h]
0x18000f24e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f253  nop
0x18000f254  mov     eax, ebx
0x18000f256  mov     rbx, [rsp+28h+arg_0]
0x18000f25b  mov     rsi, [rsp+28h+arg_8]
0x18000f260  add     rsp, 20h
0x18000f264  pop     rdi
0x18000f265  retn
```
