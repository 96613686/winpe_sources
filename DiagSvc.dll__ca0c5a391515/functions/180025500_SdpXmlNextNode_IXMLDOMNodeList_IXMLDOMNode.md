# SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)

- ea: `0x180025500`
- end: `0x180025621`
- name: `?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z`
- size: `289`
- prototype: `__int64 __fastcall(struct IXMLDOMNodeList *, struct IXMLDOMNode **)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800209e0`
- `0x180021270`
- `0x18002527c`

## callees

- `0x180024ce8`
- `0x180025500`
- `0x180027010`

## string_xrefs

- `0x1800255dd`: `SdpXmlNextNode`

## pseudocode

```c
__int64 __fastcall SdpXmlNextNode(struct IXMLDOMNodeList *a1, struct IXMLDOMNode **a2)
{
  struct IXMLDOMNode *v4; // rcx
  int v5; // eax
  __int64 v6; // r9
  unsigned int v7; // ebx
  struct IXMLDOMNode *v8; // rcx
  int v10; // [rsp+50h] [rbp+20h] BYREF
  struct IXMLDOMNode *v11; // [rsp+60h] [rbp+30h] BYREF

  v4 = 0;
  v11 = 0;
  v10 = 1;
  if ( a1 )
  {
    if ( a2 )
    {
      while ( 1 )
      {
        if ( v4 )
        {
          ((void (__fastcall *)(struct IXMLDOMNode *))v4->lpVtbl->Release)(v4);
          v11 = 0;
        }
        v5 = ((__int64 (__fastcall *)(struct IXMLDOMNodeList *, struct IXMLDOMNode **))a1->lpVtbl->nextNode)(a1, &v11);
        v7 = v5;
        if ( v5 < 0 )
          break;
        v8 = v11;
        if ( v5 == 1 || !v11 )
        {
          v7 = -2147467259;
          goto LABEL_18;
        }
        v5 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, int *))v11->lpVtbl->get_nodeType)(v11, &v10);
        v7 = v5;
        if ( v5 < 0 )
        {
          v6 = 645;
          goto LABEL_16;
        }
        v4 = v11;
        if ( v10 == 1 )
        {
          *a2 = v11;
          ((void (__fastcall *)(struct IXMLDOMNode *))v4->lpVtbl->AddRef)(v4);
          goto LABEL_17;
        }
      }
      v6 = 637;
    }
    else
    {
      v5 = -2147024809;
      v6 = 631;
      v7 = -2147024809;
    }
  }
  else
  {
    v5 = -2147024809;
    v6 = 630;
    v7 = -2147024809;
  }
LABEL_16:
  SdpDebugPrint(1u, "SDIAG: %ws:%d - hr = 0x%08X\n", L"SdpXmlNextNode", v6, v5);
LABEL_17:
  v8 = v11;
LABEL_18:
  if ( v8 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v8->lpVtbl->Release)(v8);
  return v7;
}

```

## disassembly

```asm
0x180025500  mov     [rsp-18h+arg_8], rbx
0x180025505  mov     [rsp-18h+arg_18], rsi
0x18002550a  push    rbp
0x18002550b  push    rdi
0x18002550c  push    r14
0x18002550e  mov     rbp, rsp
0x180025511  sub     rsp, 30h
0x180025515  mov     rdi, rcx
0x180025518  mov     rsi, rdx
0x18002551b  xor     ecx, ecx
0x18002551d  mov     [rbp+arg_10], rcx
0x180025521  lea     r14d, [rcx+1]
0x180025525  mov     [rbp+arg_0], r14d
0x180025529  test    rdi, rdi
0x18002552c  jnz     short loc_180025540
0x18002552e  mov     eax, 80070057h
0x180025533  mov     r9d, 276h
0x180025539  mov     ebx, eax
0x18002553b  jmp     loc_1800255DD
0x180025540  test    rsi, rsi
0x180025543  jnz     short loc_180025557
0x180025545  mov     eax, 80070057h
0x18002554a  mov     r9d, 277h
0x180025550  mov     ebx, eax
0x180025552  jmp     loc_1800255DD
0x180025557  test    rcx, rcx
0x18002555a  jz      short loc_180025570
0x18002555c  mov     rax, [rcx]
0x18002555f  mov     rax, [rax+10h]
0x180025563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025568  mov     [rbp+arg_10], 0
0x180025570  mov     rax, [rdi]
0x180025573  lea     rdx, [rbp+arg_10]
0x180025577  mov     rcx, rdi
0x18002557a  mov     rax, [rax+48h]
0x18002557e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025583  mov     ebx, eax
0x180025585  test    eax, eax
0x180025587  js      short loc_1800255D7
0x180025589  mov     rcx, [rbp+arg_10]
0x18002558d  cmp     eax, r14d
0x180025590  jz      short loc_1800255D0
0x180025592  test    rcx, rcx
0x180025595  jz      short loc_1800255D0
0x180025597  mov     rax, [rcx]
0x18002559a  lea     rdx, [rbp+arg_0]
0x18002559e  mov     rax, [rax+50h]
0x1800255a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800255a7  mov     ebx, eax
0x1800255a9  test    eax, eax
0x1800255ab  js      short loc_1800255C8
0x1800255ad  mov     rcx, [rbp+arg_10]
0x1800255b1  cmp     [rbp+arg_0], r14d
0x1800255b5  jnz     short loc_180025557
0x1800255b7  mov     [rsi], rcx
0x1800255ba  mov     rax, [rcx]
0x1800255bd  mov     rax, [rax+8]
0x1800255c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800255c6  jmp     short loc_1800255F7
0x1800255c8  mov     r9d, 285h
0x1800255ce  jmp     short loc_1800255DD
0x1800255d0  mov     ebx, 80004005h
0x1800255d5  jmp     short loc_1800255FB
0x1800255d7  mov     r9d, 27Dh
0x1800255dd  lea     r8, aSdpxmlnextnode; "SdpXmlNextNode"
0x1800255e4  mov     [rsp+30h+var_10], eax
0x1800255e8  lea     rdx, aSdiagWsDHr0x08; "SDIAG: %ws:%d - hr = 0x%08X\n"
0x1800255ef  mov     ecx, r14d; Level
0x1800255f2  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1800255f7  mov     rcx, [rbp+arg_10]
0x1800255fb  test    rcx, rcx
0x1800255fe  jz      short loc_18002560C
0x180025600  mov     rax, [rcx]
0x180025603  mov     rax, [rax+10h]
0x180025607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002560c  mov     rsi, [rsp+30h+arg_18]
0x180025611  mov     eax, ebx
0x180025613  mov     rbx, [rsp+30h+arg_8]
0x180025618  add     rsp, 30h
0x18002561c  pop     r14
0x18002561e  pop     rdi
0x18002561f  pop     rbp
0x180025620  retn
```
