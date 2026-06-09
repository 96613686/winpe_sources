# XcGetItem(IXMLDOMNodeList *,long,IXMLDOMNode * *)

- ea: `0x1800127d0`
- end: `0x180012800`
- name: `?XcGetItem@@YAKPEAUIXMLDOMNodeList@@JPEAPEAUIXMLDOMNode@@@Z`
- size: `48`
- prototype: `__int64 __fastcall(struct IXMLDOMNodeList *, __int64, struct IXMLDOMNode **)`
- caller_count: `8`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000b880`
- `0x18000c050`
- `0x18000c280`
- `0x18000f510`
- `0x180010820`
- `0x180010a24`
- `0x1800114a0`
- `0x180011974`

## callees

- `0x1800127d0`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall XcGetItem(struct IXMLDOMNodeList *a1, __int64 a2, struct IXMLDOMNode **a3)
{
  int v3; // eax
  unsigned int v4; // ecx

  v3 = ((__int64 (__fastcall *)(struct IXMLDOMNodeList *, __int64, struct IXMLDOMNode **))a1->lpVtbl->get_item)(
         a1,
         a2,
         a3);
  v4 = v3;
  if ( v3 < 0 )
  {
    if ( (v3 & 0x1FFF0000) == 0x70000 )
      return (unsigned __int16)v3;
  }
  else
  {
    return 0;
  }
  return v4;
}

```

## disassembly

```asm
0x1800127d0  sub     rsp, 28h
0x1800127d4  mov     rax, [rcx]
0x1800127d7  mov     rax, [rax+38h]
0x1800127db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127e0  mov     ecx, eax
0x1800127e2  test    eax, eax
0x1800127e4  js      short loc_1800127EA
0x1800127e6  xor     ecx, ecx
0x1800127e8  jmp     short loc_1800127F9
0x1800127ea  and     eax, 1FFF0000h
0x1800127ef  cmp     eax, 70000h
0x1800127f4  jnz     short loc_1800127F9
0x1800127f6  movzx   ecx, cx
0x1800127f9  mov     eax, ecx
0x1800127fb  add     rsp, 28h
0x1800127ff  retn
```
