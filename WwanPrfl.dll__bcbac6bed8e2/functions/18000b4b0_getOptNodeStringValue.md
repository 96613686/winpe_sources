# _getOptNodeStringValue

- ea: `0x18000b4b0`
- end: `0x18000b599`
- name: `_getOptNodeStringValue`
- size: `233`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, const unsigned __int16 *, unsigned __int16 *, unsigned __int64, _DWORD *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000b670`
- `0x18000c4a0`
- `0x18000cf80`

## callees

- `0x18000b4b0`
- `0x180012bc8`
- `0x1800131e4`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall getOptNodeStringValue(
        struct IXMLDOMNode *a1,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int64 a4,
        _DWORD *a5)
{
  _DWORD *v7; // rbx
  unsigned int SingleNode; // edi
  struct IXMLDOMNode *v10; // [rsp+80h] [rbp+18h] BYREF

  *a3 = 0;
  v10 = 0;
  v7 = a5;
  if ( a5 )
    *a5 = 0;
  SingleNode = XcGetSingleNode(a1, a2, &v10);
  if ( SingleNode )
  {
    if ( SingleNode != 1168 )
    {
      if ( v10 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v10->lpVtbl->Release)(v10);
      return SingleNode;
    }
  }
  else
  {
    SingleNode = XcGetNodeStringValue(v10, L".", a3, a4, 0, 0, 0);
    if ( SingleNode )
    {
      if ( v10 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v10->lpVtbl->Release)(v10);
      return SingleNode;
    }
    if ( v7 )
      *v7 = 1;
  }
  if ( v10 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v10->lpVtbl->Release)(v10);
  return 0;
}

```

## disassembly

```asm
0x18000b4b0  mov     r11, rsp
0x18000b4b3  push    rbx
0x18000b4b4  push    rbp
0x18000b4b5  push    rsi
0x18000b4b6  push    rdi
0x18000b4b7  sub     rsp, 48h
0x18000b4bb  mov     rbp, r9
0x18000b4be  mov     rsi, r8
0x18000b4c1  xor     eax, eax
0x18000b4c3  mov     [r8], ax
0x18000b4c7  mov     [r11+18h], rax
0x18000b4cb  mov     rbx, [rsp+68h+arg_20]
0x18000b4d3  test    rbx, rbx
0x18000b4d6  jz      short loc_18000B4DA
0x18000b4d8  mov     [rbx], eax
0x18000b4da  lea     r8, [rsp+68h+arg_10]; struct IXMLDOMNode **
0x18000b4e2  call    ?XcGetSingleNode@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; XcGetSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18000b4e7  mov     edi, eax
0x18000b4e9  test    eax, eax
0x18000b4eb  jnz     loc_18000B575
0x18000b4f1  mov     [rsp+68h+var_38], 0; int *
0x18000b4fa  mov     [rsp+68h+var_40], 0; unsigned __int16 *
0x18000b503  mov     [rsp+68h+var_48], eax; int
0x18000b507  mov     r9, rbp; unsigned __int64
0x18000b50a  mov     r8, rsi; unsigned __int16 *
0x18000b50d  lea     rdx, asc_18001646C; "."
0x18000b514  mov     rcx, [rsp+68h+arg_10]; struct IXMLDOMNode *
0x18000b51c  call    ?XcGetNodeStringValue@@YAKPEAUIXMLDOMNode@@PEBGPEAG_KH1PEAH@Z; XcGetNodeStringValue(IXMLDOMNode *,ushort const *,ushort *,unsigned __int64,int,ushort const *,int *)
0x18000b521  mov     edi, eax
0x18000b523  test    eax, eax
0x18000b525  jz      short loc_18000B545
0x18000b527  mov     rcx, [rsp+68h+arg_10]
0x18000b52f  test    rcx, rcx
0x18000b532  jz      short loc_18000B541
0x18000b534  mov     rdx, [rcx]
0x18000b537  mov     rax, [rdx+10h]
0x18000b53b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b540  nop
0x18000b541  mov     eax, edi
0x18000b543  jmp     short loc_18000B56C
0x18000b545  test    rbx, rbx
0x18000b548  jz      short loc_18000B550
0x18000b54a  mov     dword ptr [rbx], 1
0x18000b550  mov     rcx, [rsp+68h+arg_10]
0x18000b558  test    rcx, rcx
0x18000b55b  jz      short loc_18000B56A
0x18000b55d  mov     rax, [rcx]
0x18000b560  mov     rax, [rax+10h]
0x18000b564  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b569  nop
0x18000b56a  xor     eax, eax
0x18000b56c  add     rsp, 48h
0x18000b570  pop     rdi
0x18000b571  pop     rsi
0x18000b572  pop     rbp
0x18000b573  pop     rbx
0x18000b574  retn
0x18000b575  cmp     edi, 490h
0x18000b57b  jz      short loc_18000B550
0x18000b57d  mov     rcx, [rsp+68h+arg_10]
0x18000b585  test    rcx, rcx
0x18000b588  jz      short loc_18000B597
0x18000b58a  mov     rax, [rcx]
0x18000b58d  mov     rax, [rax+10h]
0x18000b591  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b596  nop
0x18000b597  jmp     short loc_18000B541
```
