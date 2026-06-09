# SdpXmlGetNumChildNodes(IXMLDOMNodeList *,ulong *)

- ea: `0x18002527c`
- end: `0x180025348`
- name: `?SdpXmlGetNumChildNodes@@YAJPEAUIXMLDOMNodeList@@PEAK@Z`
- size: `204`
- prototype: `__int64 __fastcall(struct IXMLDOMNodeList *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180024f14`

## callees

- `0x180024ce8`
- `0x18002527c`
- `0x180025500`
- `0x180027010`

## string_xrefs

- `0x1800252ad`: `SdpXmlGetNumChildNodes`

## pseudocode

```c
__int64 __fastcall SdpXmlGetNumChildNodes(struct IXMLDOMNodeList *a1, unsigned int *a2)
{
  struct IXMLDOMNodeList *v3; // rdi
  __int64 v4; // r9
  unsigned int v5; // esi
  unsigned int v6; // ebp
  struct IXMLDOMNode *v8; // [rsp+50h] [rbp+8h] BYREF

  v8 = 0;
  v3 = a1;
  if ( !a1 )
  {
    v4 = 438;
LABEL_3:
    v5 = -2147024809;
    SdpDebugPrint(1u, "SDIAG: %ws:%d - hr = 0x%08X\n", L"SdpXmlGetNumChildNodes", v4, -2147024809);
    return v5;
  }
  if ( !a2 )
  {
    v4 = 439;
    goto LABEL_3;
  }
  v6 = 0;
  v5 = 0;
  while ( 1 )
  {
    SdpXmlNextNode(a1, &v8);
    if ( !v8 )
      break;
    ((void (__fastcall *)(struct IXMLDOMNode *))v8->lpVtbl->Release)(v8);
    ++v6;
    v8 = 0;
    a1 = v3;
  }
  ((void (__fastcall *)(struct IXMLDOMNodeList *))v3->lpVtbl->reset)(v3);
  *a2 = v6;
  return v5;
}

```

## disassembly

```asm
0x18002527c  mov     [rsp+arg_8], rbx
0x180025281  mov     [rsp+arg_10], rbp
0x180025286  push    rsi
0x180025287  push    rdi
0x180025288  push    r14
0x18002528a  sub     rsp, 30h
0x18002528e  mov     [rsp+48h+arg_0], 0
0x180025297  mov     r14, rdx
0x18002529a  mov     rdi, rcx
0x18002529d  test    rcx, rcx
0x1800252a0  jnz     short loc_1800252CD
0x1800252a2  mov     r9d, 1B6h
0x1800252a8  mov     eax, 80070057h
0x1800252ad  lea     r8, aSdpxmlgetnumch; "SdpXmlGetNumChildNodes"
0x1800252b4  lea     rdx, aSdiagWsDHr0x08; "SDIAG: %ws:%d - hr = 0x%08X\n"
0x1800252bb  mov     [rsp+48h+var_28], eax
0x1800252bf  mov     ecx, 1; Level
0x1800252c4  mov     esi, eax
0x1800252c6  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1800252cb  jmp     short loc_180025333
0x1800252cd  test    r14, r14
0x1800252d0  jnz     short loc_1800252DA
0x1800252d2  mov     r9d, 1B7h
0x1800252d8  jmp     short loc_1800252A8
0x1800252da  xor     ebp, ebp
0x1800252dc  xor     esi, esi
0x1800252de  jmp     short loc_1800252F9
0x1800252e0  mov     rax, [rbx]
0x1800252e3  mov     rcx, rbx
0x1800252e6  mov     rax, [rax+10h]
0x1800252ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800252ef  inc     ebp
0x1800252f1  mov     [rsp+48h+arg_0], rsi
0x1800252f6  mov     rcx, rdi; struct IXMLDOMNodeList *
0x1800252f9  lea     rdx, [rsp+48h+arg_0]; struct IXMLDOMNode **
0x1800252fe  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x180025303  mov     rbx, [rsp+48h+arg_0]
0x180025308  test    rbx, rbx
0x18002530b  jnz     short loc_1800252E0
0x18002530d  mov     rax, [rdi]
0x180025310  mov     rcx, rdi
0x180025313  mov     rax, [rax+50h]
0x180025317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002531c  mov     [r14], ebp
0x18002531f  test    rbx, rbx
0x180025322  jz      short loc_180025333
0x180025324  mov     rcx, [rbx]
0x180025327  mov     rax, [rcx+10h]
0x18002532b  mov     rcx, rbx
0x18002532e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025333  mov     rbx, [rsp+48h+arg_8]
0x180025338  mov     eax, esi
0x18002533a  mov     rbp, [rsp+48h+arg_10]
0x18002533f  add     rsp, 30h
0x180025343  pop     r14
0x180025345  pop     rdi
0x180025346  pop     rsi
0x180025347  retn
```
