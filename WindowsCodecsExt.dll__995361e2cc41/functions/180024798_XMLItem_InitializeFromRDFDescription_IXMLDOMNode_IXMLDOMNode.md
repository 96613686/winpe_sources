# XMLItem::InitializeFromRDFDescription(IXMLDOMNode *,IXMLDOMNode *)

- ea: `0x180024798`
- end: `0x180024861`
- name: `?InitializeFromRDFDescription@XMLItem@@QEAAJPEAUIXMLDOMNode@@0@Z`
- size: `201`
- prototype: `__int64 __fastcall(XMLItem *__hidden this, struct IXMLDOMNode *, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800162c0`

## callees

- `0x1800171c4`
- `0x180024798`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall XMLItem::InitializeFromRDFDescription(XMLItem *this, struct IXMLDOMNode *a2, struct IXMLDOMNode *a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // ecx
  bool v9; // zf
  __int64 v10; // rcx

  v6 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, char *))a3->lpVtbl->get_prefix)(a3, (char *)this + 40);
  v7 = v6;
  if ( v6 >= 0 )
  {
    if ( v6 )
    {
      v9 = g_doStackCaptures == 0;
    }
    else
    {
      v7 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, char *))a3->lpVtbl->get_namespaceURI)(a3, (char *)this + 32);
      if ( (v7 & 0x80000000) != 0 )
      {
        if ( !g_doStackCaptures )
          return v7;
        goto LABEL_12;
      }
      if ( !v7 )
      {
        v10 = *((_QWORD *)this + 3);
        if ( v10 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        *((_QWORD *)this + 3) = a2;
        if ( a2 )
          ((void (__fastcall *)(struct IXMLDOMNode *))a2->lpVtbl->AddRef)(a2);
        *((_DWORD *)this + 2) = 1;
        return v7;
      }
      v9 = g_doStackCaptures == 0;
    }
    v7 = -2147467259;
    if ( v9 )
      return v7;
LABEL_12:
    v8 = v7;
    goto LABEL_13;
  }
  if ( g_doStackCaptures )
  {
    v8 = v6;
LABEL_13:
    DoStackCapture(v8);
  }
  return v7;
}

```

## disassembly

```asm
0x180024798  push    rbx
0x18002479a  push    rsi
0x18002479b  push    rdi
0x18002479c  push    r14
0x18002479e  sub     rsp, 28h
0x1800247a2  mov     rax, [r8]
0x1800247a5  mov     rsi, rdx
0x1800247a8  mov     rdi, rcx
0x1800247ab  lea     rdx, [rcx+28h]
0x1800247af  mov     rcx, r8
0x1800247b2  mov     r14, r8
0x1800247b5  mov     rax, [rax+140h]
0x1800247bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800247c1  mov     ebx, eax
0x1800247c3  test    eax, eax
0x1800247c5  jns     short loc_1800247D8
0x1800247c7  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800247ce  jz      loc_180024855
0x1800247d4  mov     ecx, eax
0x1800247d6  jmp     short loc_18002481A
0x1800247d8  jz      short loc_1800247E3
0x1800247da  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800247e1  jmp     short loc_180024811
0x1800247e3  mov     rax, [r14]
0x1800247e6  lea     rdx, [rdi+20h]
0x1800247ea  mov     rcx, r14
0x1800247ed  mov     rax, [rax+138h]
0x1800247f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800247f9  mov     ebx, eax
0x1800247fb  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180024801  test    ebx, ebx
0x180024803  jns     short loc_18002480D
0x180024805  test    eax, eax
0x180024807  jnz     short loc_180024818
0x180024809  test    ebx, ebx
0x18002480b  js      short loc_180024855
0x18002480d  jz      short loc_180024821
0x18002480f  test    eax, eax
0x180024811  mov     ebx, 80004005h
0x180024816  jz      short loc_180024855
0x180024818  mov     ecx, ebx; int
0x18002481a  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18002481f  jmp     short loc_180024855
0x180024821  mov     rcx, [rdi+18h]
0x180024825  test    rcx, rcx
0x180024828  jz      short loc_180024836
0x18002482a  mov     rax, [rcx]
0x18002482d  mov     rax, [rax+10h]
0x180024831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024836  mov     [rdi+18h], rsi
0x18002483a  test    rsi, rsi
0x18002483d  jz      short loc_18002484E
0x18002483f  mov     rcx, [rsi]
0x180024842  mov     rax, [rcx+8]
0x180024846  mov     rcx, rsi
0x180024849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002484e  mov     dword ptr [rdi+8], 1
0x180024855  mov     eax, ebx
0x180024857  add     rsp, 28h
0x18002485b  pop     r14
0x18002485d  pop     rdi
0x18002485e  pop     rsi
0x18002485f  pop     rbx
0x180024860  retn
```
