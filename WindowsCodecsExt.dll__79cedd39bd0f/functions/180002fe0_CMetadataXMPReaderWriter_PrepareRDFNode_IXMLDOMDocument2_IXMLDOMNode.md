# CMetadataXMPReaderWriter::PrepareRDFNode(IXMLDOMDocument2 *,IXMLDOMNode * *)

- ea: `0x180002fe0`
- end: `0x180003343`
- name: `?PrepareRDFNode@CMetadataXMPReaderWriter@@MEAAJPEAUIXMLDOMDocument2@@PEAPEAUIXMLDOMNode@@@Z`
- size: `867`
- prototype: `__int64 __fastcall(CMetadataXMPReaderWriter *__hidden this, struct IXMLDOMDocument2 *, struct IXMLDOMNode **)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180002fe0`
- `0x180004500`
- `0x1800171c4`
- `0x180033010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180003040`
- `OLEAUT32!__imp_SysAllocString` at `0x180003054`
- `OLEAUT32!__imp_SysAllocString` at `0x180003143`
- `OLEAUT32!__imp_SysAllocString` at `0x180003157`
- `OLEAUT32!__imp_SysAllocString` at `0x180003213`
- `OLEAUT32!__imp_SysAllocString` at `0x180003227`
- `OLEAUT32!__imp_SysAllocString` at `0x180003040`
- `OLEAUT32!__imp_SysAllocString` at `0x180003054`
- `OLEAUT32!__imp_SysAllocString` at `0x180003143`
- `OLEAUT32!__imp_SysAllocString` at `0x180003157`
- `OLEAUT32!__imp_SysAllocString` at `0x180003213`
- `OLEAUT32!__imp_SysAllocString` at `0x180003227`

## pseudocode

```c
__int64 __fastcall CMetadataXMPReaderWriter::PrepareRDFNode(
        CMetadataXMPReaderWriter *this,
        struct IXMLDOMDocument2 *a2,
        struct IXMLDOMNode **a3)
{
  unsigned __int16 *v5; // rax
  int v6; // ebx
  int v7; // ecx
  int v8; // eax
  int v9; // eax
  int v10; // ecx
  bool v11; // zf
  unsigned __int16 *v12; // rbx
  unsigned __int16 *v13; // rax
  struct IXMLDOMDocument2Vtbl *lpVtbl; // rcx
  __int128 v15; // xmm6
  unsigned __int16 *v16; // rbx
  unsigned __int16 *v17; // rax
  struct IXMLDOMDocument2Vtbl *v18; // rcx
  unsigned __int16 *v20; // [rsp+38h] [rbp-29h] BYREF
  __int64 v21; // [rsp+40h] [rbp-21h] BYREF
  __int64 v22; // [rsp+48h] [rbp-19h] BYREF
  __int128 v23; // [rsp+58h] [rbp-9h] BYREF
  __int64 v24; // [rsp+68h] [rbp+7h]
  __int64 v25; // [rsp+D8h] [rbp+77h] BYREF
  unsigned __int16 *v26; // [rsp+E0h] [rbp+7Fh] BYREF

  v25 = 0;
  v23 = 0;
  v21 = 0;
  LOWORD(v23) = 18;
  WORD4(v23) = 1;
  v22 = 0;
  *a3 = 0;
  v20 = SysAllocString(L"xpacket");
  v5 = SysAllocString(aBegin);
  v26 = v5;
  if ( !v20 || !v5 )
    goto LABEL_2;
  v8 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, unsigned __int16 *, unsigned __int16 *, __int64 *))a2->lpVtbl->createProcessingInstruction)(
         a2,
         v20,
         v5,
         &v22);
  v6 = v8;
  if ( v8 < 0 )
  {
LABEL_9:
    if ( !g_doStackCaptures )
      goto LABEL_6;
    v7 = v8;
    goto LABEL_5;
  }
  if ( v8 )
    goto LABEL_12;
  FreeBSTR(&v26);
  FreeBSTR(&v20);
  v9 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, __int64, __int64 *))a2->lpVtbl->appendChild)(a2, v22, &v25);
  v6 = v9;
  if ( v9 < 0 )
    goto LABEL_14;
  if ( v9 )
  {
LABEL_17:
    v11 = g_doStackCaptures == 0;
    goto LABEL_36;
  }
  if ( v25 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    v25 = 0;
  }
  v20 = SysAllocString(L"x:xmpmeta");
  v12 = v20;
  v13 = SysAllocString(L"adobe:ns:meta/");
  v26 = v13;
  if ( !v12 || !v13 )
    goto LABEL_2;
  lpVtbl = a2->lpVtbl;
  v15 = v23;
  v24 = 0;
  v8 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, __int128 *, unsigned __int16 *, unsigned __int16 *, __int64 *))lpVtbl->createNode)(
         a2,
         &v23,
         v12,
         v13,
         &v25);
  v6 = v8;
  if ( v8 < 0 )
    goto LABEL_9;
  if ( v8 )
    goto LABEL_12;
  FreeBSTR(&v26);
  FreeBSTR(&v20);
  v9 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, __int64, __int64 *))a2->lpVtbl->appendChild)(a2, v25, &v21);
  v6 = v9;
  if ( v9 < 0 )
  {
LABEL_14:
    if ( !g_doStackCaptures )
      goto LABEL_39;
    v10 = v9;
    goto LABEL_38;
  }
  if ( v9 )
    goto LABEL_17;
  if ( v25 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    v25 = 0;
  }
  v20 = SysAllocString(L"rdf:RDF");
  v16 = v20;
  v17 = SysAllocString(L"http://www.w3.org/1999/02/22-rdf-syntax-ns#");
  v26 = v17;
  if ( !v16 || !v17 )
  {
LABEL_2:
    v6 = -2147024882;
LABEL_3:
    if ( !g_doStackCaptures )
    {
LABEL_6:
      FreeBSTR(&v26);
      FreeBSTR(&v20);
      goto LABEL_39;
    }
    v7 = v6;
LABEL_5:
    DoStackCapture(v7);
    goto LABEL_6;
  }
  v18 = a2->lpVtbl;
  v23 = v15;
  v24 = 0;
  v8 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, __int128 *, unsigned __int16 *, unsigned __int16 *, __int64 *))v18->createNode)(
         a2,
         &v23,
         v16,
         v17,
         &v25);
  v6 = v8;
  if ( v8 < 0 )
    goto LABEL_9;
  if ( v8 )
  {
LABEL_12:
    v6 = -2147467259;
    goto LABEL_3;
  }
  FreeBSTR(&v26);
  FreeBSTR(&v20);
  v6 = (*(__int64 (__fastcall **)(__int64, __int64, struct IXMLDOMNode **))(*(_QWORD *)v21 + 168LL))(v21, v25, a3);
  if ( v6 >= 0 || !g_doStackCaptures )
  {
    if ( v6 < 1 )
      goto LABEL_39;
    v11 = g_doStackCaptures == 0;
LABEL_36:
    v6 = -2147467259;
    if ( v11 )
      goto LABEL_39;
  }
  v10 = v6;
LABEL_38:
  DoStackCapture(v10);
LABEL_39:
  if ( v25 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    v25 = 0;
  }
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
  }
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180002fe0  mov     rax, rsp
0x180002fe3  mov     [rax+8], rbx
0x180002fe7  mov     [rax+10h], rsi
0x180002feb  push    rbp
0x180002fec  push    rdi
0x180002fed  push    r12
0x180002fef  push    r14
0x180002ff1  push    r15
0x180002ff3  lea     rbp, [rax-5Fh]
0x180002ff7  sub     rsp, 90h
0x180002ffe  xor     r14d, r14d
0x180003001  movaps  xmmword ptr [rax-38h], xmm6
0x180003005  movaps  xmmword ptr [rax-48h], xmm7
0x180003009  lea     rcx, aXpacket; "xpacket"
0x180003010  xorps   xmm0, xmm0
0x180003013  mov     [rbp+57h+arg_10], r14
0x180003017  movups  [rbp+57h+var_60], xmm0
0x18000301b  lea     eax, [r14+12h]
0x18000301f  mov     [rbp+57h+var_78], r14
0x180003023  lea     r15d, [r14+1]
0x180003027  mov     word ptr [rbp+57h+var_60], ax
0x18000302b  mov     word ptr [rbp+57h+var_60+8], r15w
0x180003030  mov     rsi, r8
0x180003033  mov     rdi, rdx
0x180003036  mov     [rbp+57h+var_70], r14
0x18000303a  xor     r12d, r12d
0x18000303d  mov     [r8], r14
0x180003040  call    cs:__imp_SysAllocString
0x180003046  lea     rcx, aBegin; "begin='"
0x18000304d  mov     [rbp+57h+var_80], rax
0x180003051  mov     rbx, rax
0x180003054  call    cs:__imp_SysAllocString
0x18000305a  mov     [rbp+57h+arg_18], rax
0x18000305e  test    rbx, rbx
0x180003061  jnz     short loc_18000308F
0x180003063  mov     ebx, 8007000Eh
0x180003068  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x18000306f  jz      short loc_180003078
0x180003071  mov     ecx, ebx; int
0x180003073  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180003078  lea     rcx, [rbp+57h+arg_18]; unsigned __int16 **
0x18000307c  call    ?FreeBSTR@@YAXAEAPEAG@Z; FreeBSTR(ushort * &)
0x180003081  lea     rcx, [rbp+57h+var_80]; unsigned __int16 **
0x180003085  call    ?FreeBSTR@@YAXAEAPEAG@Z; FreeBSTR(ushort * &)
0x18000308a  jmp     loc_1800032D4
0x18000308f  test    rax, rax
0x180003092  jz      short loc_180003063
0x180003094  mov     rcx, [rdi]
0x180003097  lea     r9, [rbp+57h+var_70]
0x18000309b  mov     r8, rax
0x18000309e  mov     rdx, rbx
0x1800030a1  mov     r10, [rcx+1A0h]
0x1800030a8  mov     rcx, rdi
0x1800030ab  mov     rax, r10
0x1800030ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030b3  mov     ebx, eax
0x1800030b5  test    eax, eax
0x1800030b7  jns     short loc_1800030C6
0x1800030b9  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x1800030c0  jz      short loc_180003078
0x1800030c2  mov     ecx, eax
0x1800030c4  jmp     short loc_180003073
0x1800030c6  jz      short loc_1800030CF
0x1800030c8  mov     ebx, 80004005h
0x1800030cd  jmp     short loc_180003068
0x1800030cf  lea     rcx, [rbp+57h+arg_18]; unsigned __int16 **
0x1800030d3  call    ?FreeBSTR@@YAXAEAPEAG@Z; FreeBSTR(ushort * &)
0x1800030d8  lea     rcx, [rbp+57h+var_80]; unsigned __int16 **
0x1800030dc  call    ?FreeBSTR@@YAXAEAPEAG@Z; FreeBSTR(ushort * &)
0x1800030e1  mov     rax, [rdi]
0x1800030e4  lea     r8, [rbp+57h+arg_10]
0x1800030e8  mov     rdx, [rbp+57h+var_70]
0x1800030ec  mov     rcx, rdi
0x1800030ef  mov     rax, [rax+0A8h]
0x1800030f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030fb  mov     ebx, eax
0x1800030fd  test    eax, eax
0x1800030ff  jns     short loc_180003115
0x180003101  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x180003108  jz      loc_1800032D4
0x18000310e  mov     ecx, eax
0x180003110  jmp     loc_1800032CF
0x180003115  jz      short loc_180003123
0x180003117  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x18000311e  jmp     loc_1800032C6
0x180003123  mov     rcx, [rbp+57h+arg_10]
0x180003127  test    rcx, rcx
0x18000312a  jz      short loc_18000313C
0x18000312c  mov     rax, [rcx]
0x18000312f  mov     rax, [rax+10h]
0x180003133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003138  mov     [rbp+57h+arg_10], r14
0x18000313c  lea     rcx, aXXmpmeta; "x:xmpmeta"
0x180003143  call    cs:__imp_SysAllocString
0x180003149  lea     rcx, aAdobeNsMeta; "adobe:ns:meta/"
0x180003150  mov     [rbp+57h+var_80], rax
0x180003154  mov     rbx, rax
0x180003157  call    cs:__imp_SysAllocString
0x18000315d  mov     [rbp+57h+arg_18], rax
0x180003161  test    rbx, rbx
0x180003164  jz      loc_180003063
0x18000316a  test    rax, rax
0x18000316d  jz      loc_180003063
0x180003173  mov     rcx, [rdi]
0x180003176  lea     rdx, [rbp+57h+var_60]
0x18000317a  movups  xmm6, [rbp+57h+var_60]
0x18000317e  mov     r9, rax
0x180003181  mov     [rbp+57h+var_50], r12
0x180003185  mov     r8, rbx
0x180003188  mov     r10, [rcx+1C0h]
0x18000318f  lea     rcx, [rbp+57h+arg_10]
0x180003193  mov     [rsp+0B0h+var_90], rcx
0x180003198  mov     rax, r10
0x18000319b  mov     rcx, rdi
0x18000319e  movaps  [rbp+57h+var_60], xmm6
0x1800031a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031a7  mov     ebx, eax
0x1800031a9  test    eax, eax
0x1800031ab  js      loc_1800030B9
0x1800031b1  jnz     loc_1800030C8
0x1800031b7  lea     rcx, [rbp+57h+arg_18]; unsigned __int16 **
0x1800031bb  call    ?FreeBSTR@@YAXAEAPEAG@Z; FreeBSTR(ushort * &)
0x1800031c0  lea     rcx, [rbp+57h+var_80]; unsigned __int16 **
0x1800031c4  call    ?FreeBSTR@@YAXAEAPEAG@Z; FreeBSTR(ushort * &)
0x1800031c9  mov     rax, [rdi]
0x1800031cc  lea     r8, [rbp+57h+var_78]
0x1800031d0  mov     rdx, [rbp+57h+arg_10]
0x1800031d4  mov     rcx, rdi
0x1800031d7  mov     rax, [rax+0A8h]
0x1800031de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031e3  mov     ebx, eax
0x1800031e5  test    eax, eax
0x1800031e7  js      loc_180003101
0x1800031ed  jnz     loc_180003117
0x1800031f3  mov     rcx, [rbp+57h+arg_10]
0x1800031f7  test    rcx, rcx
0x1800031fa  jz      short loc_18000320C
0x1800031fc  mov     rax, [rcx]
0x1800031ff  mov     rax, [rax+10h]
0x180003203  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003208  mov     [rbp+57h+arg_10], r14
0x18000320c  lea     rcx, aRdfRdf; "rdf:RDF"
0x180003213  call    cs:__imp_SysAllocString
0x180003219  lea     rcx, aHttpWwwW3Org19; "http://www.w3.org/1999/02/22-rdf-syntax"...
0x180003220  mov     [rbp+57h+var_80], rax
0x180003224  mov     rbx, rax
0x180003227  call    cs:__imp_SysAllocString
0x18000322d  mov     [rbp+57h+arg_18], rax
0x180003231  test    rbx, rbx
0x180003234  jz      loc_180003063
0x18000323a  test    rax, rax
0x18000323d  jz      loc_180003063
0x180003243  mov     rcx, [rdi]
0x180003246  lea     rdx, [rbp+57h+var_60]
0x18000324a  mov     r9, rax
0x18000324d  movaps  [rbp+57h+var_60], xmm6
0x180003251  mov     r8, rbx
0x180003254  mov     [rbp+57h+var_50], r12
0x180003258  mov     r10, [rcx+1C0h]
0x18000325f  lea     rcx, [rbp+57h+arg_10]
0x180003263  mov     [rsp+0B0h+var_90], rcx
0x180003268  mov     rax, r10
0x18000326b  mov     rcx, rdi
0x18000326e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003273  mov     ebx, eax
0x180003275  test    eax, eax
0x180003277  js      loc_1800030B9
0x18000327d  jnz     loc_1800030C8
0x180003283  lea     rcx, [rbp+57h+arg_18]; unsigned __int16 **
0x180003287  call    ?FreeBSTR@@YAXAEAPEAG@Z; FreeBSTR(ushort * &)
0x18000328c  lea     rcx, [rbp+57h+var_80]; unsigned __int16 **
0x180003290  call    ?FreeBSTR@@YAXAEAPEAG@Z; FreeBSTR(ushort * &)
0x180003295  mov     rcx, [rbp+57h+var_78]
0x180003299  mov     r8, rsi
0x18000329c  mov     rdx, [rbp+57h+arg_10]
0x1800032a0  mov     rax, [rcx]
0x1800032a3  mov     rax, [rax+0A8h]
0x1800032aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032af  mov     ebx, eax
0x1800032b1  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1800032b7  test    ebx, ebx
0x1800032b9  jns     short loc_1800032BF
0x1800032bb  test    eax, eax
0x1800032bd  jnz     short loc_1800032CD
0x1800032bf  cmp     ebx, r15d
0x1800032c2  jl      short loc_1800032D4
0x1800032c4  test    eax, eax
0x1800032c6  mov     ebx, 80004005h
0x1800032cb  jz      short loc_1800032D4
0x1800032cd  mov     ecx, ebx; int
0x1800032cf  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800032d4  mov     rcx, [rbp+57h+arg_10]
0x1800032d8  test    rcx, rcx
0x1800032db  jz      short loc_1800032ED
0x1800032dd  mov     rax, [rcx]
0x1800032e0  mov     rax, [rax+10h]
0x1800032e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032e9  mov     [rbp+57h+arg_10], r14
0x1800032ed  mov     rcx, [rbp+57h+var_78]
0x1800032f1  test    rcx, rcx
0x1800032f4  jz      short loc_180003306
0x1800032f6  mov     rax, [rcx]
0x1800032f9  mov     rax, [rax+10h]
0x1800032fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003302  mov     [rbp+57h+var_78], r14
0x180003306  mov     rcx, [rbp+57h+var_70]
0x18000330a  test    rcx, rcx
0x18000330d  jz      short loc_18000331B
0x18000330f  mov     rdx, [rcx]
0x180003312  mov     rax, [rdx+10h]
0x180003316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000331b  movaps  xmm7, [rsp+0B0h+var_48+8]
0x180003320  lea     r11, [rsp+0B0h+var_20]
0x180003328  mov     rsi, [r11+38h]
0x18000332c  mov     eax, ebx
0x18000332e  mov     rbx, [r11+30h]
0x180003332  movaps  xmm6, xmmword ptr [r11-10h]
0x180003337  mov     rsp, r11
0x18000333a  pop     r15
0x18000333c  pop     r14
0x18000333e  pop     r12
0x180003340  pop     rdi
0x180003341  pop     rbp
0x180003342  retn
```
