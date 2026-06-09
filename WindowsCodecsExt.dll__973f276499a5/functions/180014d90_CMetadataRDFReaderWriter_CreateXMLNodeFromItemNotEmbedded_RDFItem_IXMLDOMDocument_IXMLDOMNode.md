# CMetadataRDFReaderWriter::CreateXMLNodeFromItemNotEmbedded(RDFItem *,IXMLDOMDocument *,IXMLDOMNode * *)

- ea: `0x180014d90`
- end: `0x180014e62`
- name: `?CreateXMLNodeFromItemNotEmbedded@CMetadataRDFReaderWriter@@MEAAJPEAVRDFItem@@PEAUIXMLDOMDocument@@PEAPEAUIXMLDOMNode@@@Z`
- size: `210`
- prototype: `int(CMetadataRDFReaderWriter *__hidden this, struct RDFItem *, struct IXMLDOMDocument *, struct IXMLDOMNode **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180004500`
- `0x180014d90`
- `0x1800153b8`
- `0x1800171c4`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::CreateXMLNodeFromItemNotEmbedded(
        CMetadataRDFReaderWriter *this,
        struct RDFItem *a2,
        struct IXMLDOMDocument *a3,
        struct IXMLDOMNode **a4)
{
  int ValueAsBSTR; // eax
  int v7; // ebx
  int v8; // ecx
  struct IXMLDOMNode *v10; // [rsp+20h] [rbp-18h] BYREF
  unsigned __int16 *v11[2]; // [rsp+28h] [rbp-10h] BYREF

  v11[0] = 0;
  v10 = 0;
  ValueAsBSTR = Item::GetValueAsBSTR(a2, v11, 1);
  v7 = ValueAsBSTR;
  if ( ValueAsBSTR < 0 )
  {
    if ( !g_doStackCaptures )
      goto LABEL_11;
    v8 = ValueAsBSTR;
    goto LABEL_10;
  }
  v7 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, unsigned __int16 *, struct IXMLDOMNode **))a3->lpVtbl->createTextNode)(
         a3,
         v11[0],
         &v10);
  if ( v7 < 0 )
  {
    if ( !g_doStackCaptures )
      goto LABEL_11;
LABEL_9:
    v8 = v7;
LABEL_10:
    DoStackCapture(v8);
    goto LABEL_11;
  }
  if ( !v7 )
  {
    *a4 = v10;
    goto LABEL_13;
  }
  v7 = -2147467259;
  if ( g_doStackCaptures )
    goto LABEL_9;
LABEL_11:
  if ( v10 )
  {
    ((void (__fastcall *)(struct IXMLDOMNode *))v10->lpVtbl->Release)(v10);
LABEL_13:
    v10 = 0;
  }
  FreeBSTR(v11);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180014d90  mov     rax, rsp
0x180014d93  mov     [rax+8], rbx
0x180014d97  mov     [rax+10h], rsi
0x180014d9b  push    rdi
0x180014d9c  sub     rsp, 30h
0x180014da0  mov     rsi, r8
0x180014da3  mov     qword ptr [rax-10h], 0
0x180014dab  mov     rcx, rdx; this
0x180014dae  mov     qword ptr [rax-18h], 0
0x180014db6  mov     r8d, 1; int
0x180014dbc  lea     rdx, [rax-10h]; unsigned __int16 **
0x180014dc0  mov     rdi, r9
0x180014dc3  call    ?GetValueAsBSTR@Item@@QEAAJPEAPEAGH@Z; Item::GetValueAsBSTR(ushort * *,int)
0x180014dc8  mov     ebx, eax
0x180014dca  test    eax, eax
0x180014dcc  jns     short loc_180014DDB
0x180014dce  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180014dd5  jz      short loc_180014E1D
0x180014dd7  mov     ecx, eax
0x180014dd9  jmp     short loc_180014E18
0x180014ddb  mov     rax, [rsi]
0x180014dde  lea     r8, [rsp+38h+var_18]
0x180014de3  mov     rdx, [rsp+38h+var_10]
0x180014de8  mov     rcx, rsi
0x180014deb  mov     rax, [rax+188h]
0x180014df2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014df7  mov     ebx, eax
0x180014df9  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180014dff  test    ebx, ebx
0x180014e01  jns     short loc_180014E0B
0x180014e03  test    eax, eax
0x180014e05  jnz     short loc_180014E16
0x180014e07  test    ebx, ebx
0x180014e09  js      short loc_180014E1D
0x180014e0b  jz      short loc_180014E58
0x180014e0d  mov     ebx, 80004005h
0x180014e12  test    eax, eax
0x180014e14  jz      short loc_180014E1D
0x180014e16  mov     ecx, ebx; int
0x180014e18  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180014e1d  mov     rcx, [rsp+38h+var_18]
0x180014e22  test    rcx, rcx
0x180014e25  jz      short loc_180014E3C
0x180014e27  mov     rdx, [rcx]
0x180014e2a  mov     rax, [rdx+10h]
0x180014e2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e33  mov     [rsp+38h+var_18], 0
0x180014e3c  lea     rcx, [rsp+38h+var_10]; unsigned __int16 **
0x180014e41  call    ?FreeBSTR@@YAXAEAPEAG@Z; FreeBSTR(ushort * &)
0x180014e46  mov     rsi, [rsp+38h+arg_8]
0x180014e4b  mov     eax, ebx
0x180014e4d  mov     rbx, [rsp+38h+arg_0]
0x180014e52  add     rsp, 30h
0x180014e56  pop     rdi
0x180014e57  retn
0x180014e58  mov     rax, [rsp+38h+var_18]
0x180014e5d  mov     [rdi], rax
0x180014e60  jmp     short loc_180014E33
```
