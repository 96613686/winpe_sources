# CMetadataRDFReaderWriter::PrepareRDFNode(IXMLDOMDocument2 *,IXMLDOMNode * *)

- ea: `0x180023910`
- end: `0x180023a92`
- name: `?PrepareRDFNode@CMetadataRDFReaderWriter@@MEAAJPEAUIXMLDOMDocument2@@PEAPEAUIXMLDOMNode@@@Z`
- size: `386`
- prototype: `__int64 __fastcall(CMetadataRDFReaderWriter *__hidden this, struct IXMLDOMDocument2 *, struct IXMLDOMNode **)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180004500`
- `0x1800171c4`
- `0x180023910`
- `0x180033010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180023963`
- `OLEAUT32!__imp_SysAllocString` at `0x180023977`
- `OLEAUT32!__imp_SysAllocString` at `0x180023963`
- `OLEAUT32!__imp_SysAllocString` at `0x180023977`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::PrepareRDFNode(
        CMetadataRDFReaderWriter *this,
        struct IXMLDOMDocument2 *a2,
        struct IXMLDOMNode **a3)
{
  const OLECHAR *v5; // rax
  unsigned __int16 *v6; // rax
  unsigned int v7; // ebx
  int v8; // ecx
  struct IXMLDOMDocument2Vtbl *lpVtbl; // rcx
  int v10; // eax
  unsigned __int16 *v12; // [rsp+30h] [rbp-30h] BYREF
  __int128 v13; // [rsp+40h] [rbp-20h] BYREF
  __int64 v14; // [rsp+50h] [rbp-10h]
  __int64 v15; // [rsp+90h] [rbp+30h] BYREF
  __int64 v16; // [rsp+A0h] [rbp+40h] BYREF
  unsigned __int16 *v17; // [rsp+A8h] [rbp+48h] BYREF

  v13 = 0;
  *a3 = 0;
  v15 = 0;
  v16 = 0;
  LOWORD(v13) = 18;
  WORD4(v13) = 1;
  v5 = (const OLECHAR *)(*(__int64 (__fastcall **)(CMetadataRDFReaderWriter *))(*(_QWORD *)this + 312LL))(this);
  v12 = SysAllocString(v5);
  v6 = SysAllocString(L"http://www.w3.org/1999/02/22-rdf-syntax-ns#");
  v17 = v6;
  if ( !v12 || !v6 )
  {
    v7 = -2147024882;
LABEL_3:
    if ( !g_doStackCaptures )
      goto LABEL_15;
    v8 = v7;
    goto LABEL_14;
  }
  lpVtbl = a2->lpVtbl;
  v14 = 0;
  v10 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, __int128 *, unsigned __int16 *, unsigned __int16 *, __int64 *))lpVtbl->createNode)(
          a2,
          &v13,
          v12,
          v6,
          &v15);
  v7 = v10;
  if ( v10 >= 0 )
  {
    if ( v10 )
    {
LABEL_8:
      v7 = -2147467259;
      goto LABEL_3;
    }
    v10 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, __int64, __int64 *))a2->lpVtbl->appendChild)(
            a2,
            v15,
            &v16);
    v7 = v10;
    if ( v10 >= 0 )
    {
      if ( v10 )
        goto LABEL_8;
      v10 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IXMLDOMNode **))v16)(v16, &IID_IXMLDOMElement, a3);
      v7 = v10;
      if ( v10 >= 0 )
        goto LABEL_15;
    }
  }
  if ( !g_doStackCaptures )
    goto LABEL_15;
  v8 = v10;
LABEL_14:
  DoStackCapture(v8);
LABEL_15:
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    v15 = 0;
  }
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v16 = 0;
  }
  FreeBSTR(&v17);
  FreeBSTR(&v12);
  return v7;
}

```

## disassembly

```asm
0x180023910  mov     [rsp-28h+arg_8], rbx
0x180023915  push    rbp
0x180023916  push    rsi
0x180023917  push    rdi
0x180023918  push    r14
0x18002391a  push    r15
0x18002391c  mov     rbp, rsp
0x18002391f  sub     rsp, 60h
0x180023923  xor     r14d, r14d
0x180023926  xorps   xmm0, xmm0
0x180023929  movups  [rbp+var_20], xmm0
0x18002392d  mov     [r8], r14
0x180023930  mov     rsi, r8
0x180023933  mov     rdi, rdx
0x180023936  mov     [rbp+arg_0], r14
0x18002393a  lea     eax, [r14+12h]
0x18002393e  mov     [rbp+arg_10], r14
0x180023942  mov     word ptr [rbp+var_20], ax
0x180023946  xor     r15d, r15d
0x180023949  lea     eax, [r14+1]
0x18002394d  mov     word ptr [rbp+var_20+8], ax
0x180023951  mov     rax, [rcx]
0x180023954  mov     rax, [rax+138h]
0x18002395b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023960  mov     rcx, rax; psz
0x180023963  call    cs:__imp_SysAllocString
0x180023969  lea     rcx, aHttpWwwW3Org19; "http://www.w3.org/1999/02/22-rdf-syntax"...
0x180023970  mov     [rbp+var_30], rax
0x180023974  mov     rbx, rax
0x180023977  call    cs:__imp_SysAllocString
0x18002397d  mov     [rbp+arg_18], rax
0x180023981  test    rbx, rbx
0x180023984  jnz     short loc_18002399F
0x180023986  mov     ebx, 8007000Eh
0x18002398b  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x180023992  jz      loc_180023A38
0x180023998  mov     ecx, ebx
0x18002399a  jmp     loc_180023A33
0x18002399f  test    rax, rax
0x1800239a2  jz      short loc_180023986
0x1800239a4  mov     rcx, [rdi]
0x1800239a7  lea     rdx, [rbp+var_20]
0x1800239ab  movups  xmm0, [rbp+var_20]
0x1800239af  mov     r9, rax
0x1800239b2  mov     [rbp+var_10], r15
0x1800239b6  mov     r8, rbx
0x1800239b9  mov     r10, [rcx+1C0h]
0x1800239c0  lea     rcx, [rbp+arg_0]
0x1800239c4  mov     [rsp+60h+var_40], rcx
0x1800239c9  mov     rax, r10
0x1800239cc  mov     rcx, rdi
0x1800239cf  movaps  [rbp+var_20], xmm0
0x1800239d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800239d8  mov     ebx, eax
0x1800239da  test    eax, eax
0x1800239dc  js      short loc_180023A28
0x1800239de  jz      short loc_1800239E7
0x1800239e0  mov     ebx, 80004005h
0x1800239e5  jmp     short loc_18002398B
0x1800239e7  mov     rax, [rdi]
0x1800239ea  lea     r8, [rbp+arg_10]
0x1800239ee  mov     rdx, [rbp+arg_0]
0x1800239f2  mov     rcx, rdi
0x1800239f5  mov     rax, [rax+0A8h]
0x1800239fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a01  mov     ebx, eax
0x180023a03  test    eax, eax
0x180023a05  js      short loc_180023A28
0x180023a07  jnz     short loc_1800239E0
0x180023a09  mov     rcx, [rbp+arg_10]
0x180023a0d  lea     rdx, IID_IXMLDOMElement
0x180023a14  mov     r8, rsi
0x180023a17  mov     rax, [rcx]
0x180023a1a  mov     rax, [rax]
0x180023a1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a22  mov     ebx, eax
0x180023a24  test    eax, eax
0x180023a26  jns     short loc_180023A38
0x180023a28  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x180023a2f  jz      short loc_180023A38
0x180023a31  mov     ecx, eax; int
0x180023a33  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180023a38  mov     rcx, [rbp+arg_0]
0x180023a3c  test    rcx, rcx
0x180023a3f  jz      short loc_180023A51
0x180023a41  mov     rax, [rcx]
0x180023a44  mov     rax, [rax+10h]
0x180023a48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a4d  mov     [rbp+arg_0], r14
0x180023a51  mov     rcx, [rbp+arg_10]
0x180023a55  test    rcx, rcx
0x180023a58  jz      short loc_180023A6A
0x180023a5a  mov     rdx, [rcx]
0x180023a5d  mov     rax, [rdx+10h]
0x180023a61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a66  mov     [rbp+arg_10], r14
0x180023a6a  lea     rcx, [rbp+arg_18]; unsigned __int16 **
0x180023a6e  call    ?FreeBSTR@@YAXAEAPEAG@Z; FreeBSTR(ushort * &)
0x180023a73  lea     rcx, [rbp+var_30]; unsigned __int16 **
0x180023a77  call    ?FreeBSTR@@YAXAEAPEAG@Z; FreeBSTR(ushort * &)
0x180023a7c  mov     eax, ebx
0x180023a7e  mov     rbx, [rsp+60h+arg_8]
0x180023a86  add     rsp, 60h
0x180023a8a  pop     r15
0x180023a8c  pop     r14
0x180023a8e  pop     rdi
0x180023a8f  pop     rsi
0x180023a90  pop     rbp
0x180023a91  retn
```
