# SdpXmlGetChildNodes(IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *,ulong *)

- ea: `0x180024f14`
- end: `0x180025017`
- name: `?SdpXmlGetChildNodes@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@PEAK@Z`
- size: `259`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *, struct IXMLDOMNode *, struct IXMLDOMNodeList **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800209e0`

## callees

- `0x180024ce8`
- `0x180024f14`
- `0x18002527c`
- `0x180027010`

## string_xrefs

- `0x180024f56`: `SdpXmlGetChildNodes`

## pseudocode

```c
__int64 __fastcall SdpXmlGetChildNodes(
        struct IXMLDOMDocument2 *a1,
        struct IXMLDOMNode *a2,
        struct IXMLDOMNodeList **a3,
        unsigned int *a4)
{
  __int64 v6; // r9
  int NumChildNodes; // eax
  unsigned int v8; // ebx
  int v10; // [rsp+20h] [rbp-18h]
  unsigned int v11; // [rsp+40h] [rbp+8h] BYREF
  int v12; // [rsp+44h] [rbp+Ch]
  struct IXMLDOMNodeList *v13; // [rsp+50h] [rbp+18h] BYREF

  v12 = HIDWORD(a1);
  v13 = 0;
  v11 = 0;
  if ( !a3 )
  {
    v6 = 371;
LABEL_3:
    NumChildNodes = -2147024809;
    v8 = -2147024809;
LABEL_4:
    v10 = NumChildNodes;
LABEL_5:
    SdpDebugPrint(1u, "SDIAG: %ws:%d - hr = 0x%08X\n", L"SdpXmlGetChildNodes", v6, v10);
    goto LABEL_15;
  }
  if ( !a4 )
  {
    v6 = 372;
    goto LABEL_3;
  }
  if ( !a2 )
  {
    v8 = -2147467261;
    v6 = 385;
    v10 = -2147467261;
    goto LABEL_5;
  }
  NumChildNodes = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMNodeList **))a2->lpVtbl->get_childNodes)(
                    a2,
                    &v13);
  v8 = NumChildNodes;
  if ( NumChildNodes < 0 )
  {
    v6 = 387;
    goto LABEL_4;
  }
  NumChildNodes = SdpXmlGetNumChildNodes(v13, &v11);
  v8 = NumChildNodes;
  if ( NumChildNodes < 0 )
  {
    v6 = 391;
    goto LABEL_4;
  }
  *a3 = v13;
  *a4 = v11;
  ((void (__fastcall *)(_QWORD))(*a3)->lpVtbl->AddRef)(*a3);
LABEL_15:
  if ( v13 )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v13->lpVtbl->Release)(v13);
  return v8;
}

```

## disassembly

```asm
0x180024f14  mov     rax, rsp
0x180024f17  mov     [rax+10h], rbx
0x180024f1b  mov     [rax+20h], rsi
0x180024f1f  mov     [rax+8], rcx
0x180024f23  push    rdi
0x180024f24  sub     rsp, 30h
0x180024f28  mov     qword ptr [rax+18h], 0
0x180024f30  mov     rdi, r9
0x180024f33  mov     dword ptr [rax+8], 0
0x180024f3a  mov     rsi, r8
0x180024f3d  mov     r10, rdx
0x180024f40  test    r8, r8
0x180024f43  jnz     short loc_180024F70
0x180024f45  mov     r9d, 173h
0x180024f4b  mov     eax, 80070057h
0x180024f50  mov     ebx, eax
0x180024f52  mov     [rsp+38h+var_18], eax
0x180024f56  lea     r8, aSdpxmlgetchild; "SdpXmlGetChildNodes"
0x180024f5d  mov     ecx, 1; Level
0x180024f62  lea     rdx, aSdiagWsDHr0x08; "SDIAG: %ws:%d - hr = 0x%08X\n"
0x180024f69  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x180024f6e  jmp     short loc_180024FEF
0x180024f70  test    rdi, rdi
0x180024f73  jnz     short loc_180024F7D
0x180024f75  mov     r9d, 174h
0x180024f7b  jmp     short loc_180024F4B
0x180024f7d  test    r10, r10
0x180024f80  jnz     short loc_180024F93
0x180024f82  mov     ebx, 80004003h
0x180024f87  mov     r9d, 181h
0x180024f8d  mov     [rsp+38h+var_18], ebx
0x180024f91  jmp     short loc_180024F56
0x180024f93  mov     rax, [rdx]
0x180024f96  mov     rcx, r10
0x180024f99  lea     rdx, [rsp+38h+arg_10]
0x180024f9e  mov     rax, [rax+60h]
0x180024fa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024fa7  mov     ebx, eax
0x180024fa9  test    eax, eax
0x180024fab  jns     short loc_180024FB5
0x180024fad  mov     r9d, 183h
0x180024fb3  jmp     short loc_180024F52
0x180024fb5  mov     rcx, [rsp+38h+arg_10]; struct IXMLDOMNodeList *
0x180024fba  lea     rdx, [rsp+38h+arg_0]; unsigned int *
0x180024fbf  call    ?SdpXmlGetNumChildNodes@@YAJPEAUIXMLDOMNodeList@@PEAK@Z; SdpXmlGetNumChildNodes(IXMLDOMNodeList *,ulong *)
0x180024fc4  mov     ebx, eax
0x180024fc6  test    eax, eax
0x180024fc8  jns     short loc_180024FD2
0x180024fca  mov     r9d, 187h
0x180024fd0  jmp     short loc_180024F52
0x180024fd2  mov     rax, [rsp+38h+arg_10]
0x180024fd7  mov     [rsi], rax
0x180024fda  mov     eax, [rsp+38h+arg_0]
0x180024fde  mov     [rdi], eax
0x180024fe0  mov     rcx, [rsi]
0x180024fe3  mov     rax, [rcx]
0x180024fe6  mov     rax, [rax+8]
0x180024fea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024fef  mov     rcx, [rsp+38h+arg_10]
0x180024ff4  test    rcx, rcx
0x180024ff7  jz      short loc_180025005
0x180024ff9  mov     rax, [rcx]
0x180024ffc  mov     rax, [rax+10h]
0x180025000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025005  mov     rsi, [rsp+38h+arg_18]
0x18002500a  mov     eax, ebx
0x18002500c  mov     rbx, [rsp+38h+arg_8]
0x180025011  add     rsp, 30h
0x180025015  pop     rdi
0x180025016  retn
```
