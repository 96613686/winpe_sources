# RDFItem::InitializeFromXMLNode(IXMLDOMNode *)

- ea: `0x18000f9a0`
- end: `0x18000fa82`
- name: `?InitializeFromXMLNode@RDFItem@@UEAAJPEAUIXMLDOMNode@@@Z`
- size: `226`
- prototype: `__int64 __fastcall(RDFItem *__hidden this, struct IXMLDOMNode *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x18000f9a0`
- `0x1800171c4`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall RDFItem::InitializeFromXMLNode(RDFItem *this, struct IXMLDOMNode *a2)
{
  __int64 result; // rax
  unsigned int v5; // ebx
  int v6; // [rsp+30h] [rbp+8h] BYREF

  *((_DWORD *)this + 2) = 0;
  v6 = 0;
  result = ((__int64 (__fastcall *)(struct IXMLDOMNode *, int *))a2->lpVtbl->get_nodeType)(a2, &v6);
  v5 = result;
  if ( (int)result < 0 && g_doStackCaptures )
  {
    DoStackCapture(result);
    return v5;
  }
  if ( (int)result >= 0 )
  {
    if ( (_DWORD)result )
    {
      if ( g_doStackCaptures )
        DoStackCapture(-2147467259);
      return 2147500037LL;
    }
    else
    {
      if ( v6 == 1 )
      {
LABEL_6:
        *((_QWORD *)this + 2) = a2;
        ((void (__fastcall *)(struct IXMLDOMNode *))a2->lpVtbl->AddRef)(a2);
        return 0;
      }
      if ( v6 == 2 )
      {
        *((_DWORD *)this + 2) |= 0x10u;
        goto LABEL_6;
      }
      if ( g_doStackCaptures )
        DoStackCapture(-2003292271);
      return 2291675025LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000f9a0  mov     [rsp+arg_8], rbx
0x18000f9a5  mov     [rsp+arg_10], rsi
0x18000f9aa  push    rdi
0x18000f9ab  sub     rsp, 20h
0x18000f9af  xor     eax, eax
0x18000f9b1  mov     rdi, rdx
0x18000f9b4  mov     [rcx+8], eax
0x18000f9b7  mov     rsi, rcx
0x18000f9ba  mov     [rsp+28h+arg_0], eax
0x18000f9be  mov     rcx, rdi
0x18000f9c1  mov     rax, [rdx]
0x18000f9c4  lea     rdx, [rsp+28h+arg_0]
0x18000f9c9  mov     rax, [rax+50h]
0x18000f9cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f9d2  mov     ecx, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18000f9d8  mov     ebx, eax
0x18000f9da  test    eax, eax
0x18000f9dc  jns     short loc_18000F9E2
0x18000f9de  test    ecx, ecx
0x18000f9e0  jnz     short loc_18000FA21
0x18000f9e2  test    ebx, ebx
0x18000f9e4  js      short loc_18000FA06
0x18000f9e6  jnz     short loc_18000FA3A
0x18000f9e8  mov     eax, [rsp+28h+arg_0]
0x18000f9ec  cmp     eax, 1
0x18000f9ef  jnz     short loc_18000FA16
0x18000f9f1  mov     [rsi+10h], rdi
0x18000f9f5  mov     rcx, rdi
0x18000f9f8  mov     rax, [rdi]
0x18000f9fb  mov     rax, [rax+8]
0x18000f9ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa04  mov     eax, ebx
0x18000fa06  mov     rbx, [rsp+28h+arg_8]
0x18000fa0b  mov     rsi, [rsp+28h+arg_10]
0x18000fa10  add     rsp, 20h
0x18000fa14  pop     rdi
0x18000fa15  retn
0x18000fa16  cmp     eax, 2
0x18000fa19  jnz     short loc_18000FA5F
0x18000fa1b  or      dword ptr [rsi+8], 10h
0x18000fa1f  jmp     short loc_18000F9F1
0x18000fa21  mov     ecx, ebx; int
0x18000fa23  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000fa28  mov     eax, ebx
0x18000fa2a  mov     rbx, [rsp+28h+arg_8]
0x18000fa2f  mov     rsi, [rsp+28h+arg_10]
0x18000fa34  add     rsp, 20h
0x18000fa38  pop     rdi
0x18000fa39  retn
0x18000fa3a  test    ecx, ecx
0x18000fa3c  jnz     short loc_18000FA53
0x18000fa3e  mov     eax, 80004005h
0x18000fa43  mov     rbx, [rsp+28h+arg_8]
0x18000fa48  mov     rsi, [rsp+28h+arg_10]
0x18000fa4d  add     rsp, 20h
0x18000fa51  pop     rdi
0x18000fa52  retn
0x18000fa53  mov     ecx, 80004005h; int
0x18000fa58  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000fa5d  jmp     short loc_18000FA3E
0x18000fa5f  test    ecx, ecx
0x18000fa61  jz      short loc_18000FA6D
0x18000fa63  mov     ecx, 88982F91h; int
0x18000fa68  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000fa6d  mov     rbx, [rsp+28h+arg_8]
0x18000fa72  mov     eax, 88982F91h
0x18000fa77  mov     rsi, [rsp+28h+arg_10]
0x18000fa7c  add     rsp, 20h
0x18000fa80  pop     rdi
0x18000fa81  retn
```
