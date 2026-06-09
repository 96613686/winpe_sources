# CMetadataRDFReaderWriter::CheckParseType(IXMLDOMNode *,ushort const *,int *)

- ea: `0x180004340`
- end: `0x1800044f6`
- name: `?CheckParseType@CMetadataRDFReaderWriter@@MEAAJPEAUIXMLDOMNode@@PEBGPEAH@Z`
- size: `438`
- prototype: `__int64 __fastcall(CMetadataRDFReaderWriter *__hidden this, struct IXMLDOMNode *, const unsigned __int16 *, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180004340`
- `0x180004500`
- `0x1800171c4`
- `0x180033010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000441d`
- `OLEAUT32!__imp_SysAllocString` at `0x180004431`
- `OLEAUT32!__imp_SysAllocString` at `0x18000441d`
- `OLEAUT32!__imp_SysAllocString` at `0x180004431`
- `OLEAUT32!__imp_SysFreeString` at `0x1800043fb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800043fb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800044c0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800044c0`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::CheckParseType(
        CMetadataRDFReaderWriter *this,
        struct IXMLDOMNode *a2,
        const unsigned __int16 *a3,
        int *a4)
{
  struct IXMLDOMNodeVtbl *lpVtbl; // rax
  int v6; // eax
  int v7; // ebx
  int v8; // ecx
  unsigned __int16 *v10; // rbx
  unsigned __int16 *v11; // rax
  __int64 v12; // [rsp+30h] [rbp-20h] BYREF
  __int64 v13; // [rsp+38h] [rbp-18h] BYREF
  BSTR bstrString[2]; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int16 *v15; // [rsp+78h] [rbp+28h] BYREF
  unsigned __int16 *v16; // [rsp+88h] [rbp+38h] BYREF

  *a4 = 0;
  lpVtbl = a2->lpVtbl;
  v12 = 0;
  v13 = 0;
  bstrString[0] = 0;
  v6 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64 *, const unsigned __int16 *))lpVtbl->get_attributes)(
         a2,
         &v13,
         a3);
  v7 = v6;
  if ( v6 < 0 )
    goto LABEL_2;
  if ( v6 )
  {
    v7 = -2147467259;
    if ( g_doStackCaptures )
    {
      v8 = -2147467259;
LABEL_4:
      DoStackCapture(v8);
    }
  }
  else
  {
    v16 = SysAllocString(L"parseType");
    v10 = v16;
    v11 = SysAllocString(L"http://www.w3.org/1999/02/22-rdf-syntax-ns#");
    v15 = v11;
    if ( !v10 || !v11 )
    {
      v7 = -2147024882;
LABEL_7:
      if ( g_doStackCaptures )
        DoStackCapture(v7);
      FreeBSTR(&v15);
      FreeBSTR(&v16);
      goto LABEL_10;
    }
    v7 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, unsigned __int16 *, __int64 *))(*(_QWORD *)v13 + 96LL))(
           v13,
           v10,
           v11,
           &v12);
    if ( v7 < 0 )
      goto LABEL_7;
    FreeBSTR(&v15);
    FreeBSTR(&v16);
    if ( !v7 && v12 )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v12 + 208LL))(v12, bstrString);
      v7 = v6;
      if ( v6 < 0 )
      {
LABEL_2:
        if ( !g_doStackCaptures )
          goto LABEL_10;
        v8 = v6;
        goto LABEL_4;
      }
      if ( !v6 && !lstrcmpW(bstrString[0], L"Resource") )
        *a4 = 1;
    }
    v7 = 0;
  }
LABEL_10:
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v12 = 0;
  }
  if ( v13 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    v13 = 0;
  }
  if ( bstrString[0] )
    SysFreeString(bstrString[0]);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180004340  mov     [rsp-18h+arg_0], rbx
0x180004345  push    rbp
0x180004346  push    rsi
0x180004347  push    rdi
0x180004348  mov     rbp, rsp
0x18000434b  sub     rsp, 50h
0x18000434f  xor     esi, esi
0x180004351  mov     rcx, rdx
0x180004354  mov     [r9], esi
0x180004357  mov     rdi, r9
0x18000435a  mov     rax, [rdx]
0x18000435d  lea     rdx, [rbp+var_18]
0x180004361  mov     [rbp+var_20], rsi
0x180004365  mov     [rbp+var_18], rsi
0x180004369  mov     [rbp+bstrString], rsi
0x18000436d  mov     rax, [rax+88h]
0x180004374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004379  mov     ebx, eax
0x18000437b  test    eax, eax
0x18000437d  jns     loc_180004410
0x180004383  cmp     cs:?g_doStackCaptures@@3HA, esi; int g_doStackCaptures
0x180004389  jz      short loc_1800043C0
0x18000438b  mov     ecx, eax; int
0x18000438d  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180004392  jmp     short loc_1800043C0
0x180004394  test    rax, rax
0x180004397  jnz     loc_180004449
0x18000439d  mov     ebx, 8007000Eh
0x1800043a2  cmp     cs:?g_doStackCaptures@@3HA, esi; int g_doStackCaptures
0x1800043a8  jnz     loc_1800044D2
0x1800043ae  lea     rcx, [rbp+arg_8]; unsigned __int16 **
0x1800043b2  call    ?FreeBSTR@@YAXAEAPEAG@Z; FreeBSTR(ushort * &)
0x1800043b7  lea     rcx, [rbp+arg_18]; unsigned __int16 **
0x1800043bb  call    ?FreeBSTR@@YAXAEAPEAG@Z; FreeBSTR(ushort * &)
0x1800043c0  mov     rcx, [rbp+var_20]
0x1800043c4  test    rcx, rcx
0x1800043c7  jz      short loc_1800043D9
0x1800043c9  mov     rax, [rcx]
0x1800043cc  mov     rax, [rax+10h]
0x1800043d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043d5  mov     [rbp+var_20], rsi
0x1800043d9  mov     rcx, [rbp+var_18]
0x1800043dd  test    rcx, rcx
0x1800043e0  jz      short loc_1800043F2
0x1800043e2  mov     rax, [rcx]
0x1800043e5  mov     rax, [rax+10h]
0x1800043e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043ee  mov     [rbp+var_18], rsi
0x1800043f2  mov     rcx, [rbp+bstrString]; bstrString
0x1800043f6  test    rcx, rcx
0x1800043f9  jz      short loc_180004401
0x1800043fb  call    cs:__imp_SysFreeString
0x180004401  mov     eax, ebx
0x180004403  mov     rbx, [rsp+50h+arg_0]
0x180004408  add     rsp, 50h
0x18000440c  pop     rdi
0x18000440d  pop     rsi
0x18000440e  pop     rbp
0x18000440f  retn
0x180004410  jnz     loc_1800044DE
0x180004416  lea     rcx, aParsetype; "parseType"
0x18000441d  call    cs:__imp_SysAllocString
0x180004423  lea     rcx, aHttpWwwW3Org19; "http://www.w3.org/1999/02/22-rdf-syntax"...
0x18000442a  mov     [rbp+arg_18], rax
0x18000442e  mov     rbx, rax
0x180004431  call    cs:__imp_SysAllocString
0x180004437  mov     [rbp+arg_8], rax
0x18000443b  test    rbx, rbx
0x18000443e  jz      loc_18000439D
0x180004444  jmp     loc_180004394
0x180004449  mov     rcx, [rbp+var_18]
0x18000444d  lea     r9, [rbp+var_20]
0x180004451  mov     r8, rax
0x180004454  mov     rdx, [rcx]
0x180004457  mov     r10, [rdx+60h]
0x18000445b  mov     rdx, rbx
0x18000445e  mov     rax, r10
0x180004461  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004466  mov     ebx, eax
0x180004468  test    eax, eax
0x18000446a  js      loc_1800043A2
0x180004470  lea     rcx, [rbp+arg_8]; unsigned __int16 **
0x180004474  call    ?FreeBSTR@@YAXAEAPEAG@Z; FreeBSTR(ushort * &)
0x180004479  lea     rcx, [rbp+arg_18]; unsigned __int16 **
0x18000447d  call    ?FreeBSTR@@YAXAEAPEAG@Z; FreeBSTR(ushort * &)
0x180004482  test    ebx, ebx
0x180004484  jz      short loc_18000448D
0x180004486  mov     ebx, esi
0x180004488  jmp     loc_1800043C0
0x18000448d  mov     rcx, [rbp+var_20]
0x180004491  test    rcx, rcx
0x180004494  jz      short loc_180004486
0x180004496  mov     rax, [rcx]
0x180004499  lea     rdx, [rbp+bstrString]
0x18000449d  mov     rax, [rax+0D0h]
0x1800044a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044a9  mov     ebx, eax
0x1800044ab  test    eax, eax
0x1800044ad  js      loc_180004383
0x1800044b3  jnz     short loc_180004486
0x1800044b5  mov     rcx, [rbp+bstrString]; lpString1
0x1800044b9  lea     rdx, aResource; "Resource"
0x1800044c0  call    cs:__imp_lstrcmpW
0x1800044c6  test    eax, eax
0x1800044c8  jnz     short loc_180004486
0x1800044ca  mov     dword ptr [rdi], 1
0x1800044d0  jmp     short loc_180004486
0x1800044d2  mov     ecx, ebx; int
0x1800044d4  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800044d9  jmp     loc_1800043AE
0x1800044de  cmp     cs:?g_doStackCaptures@@3HA, esi; int g_doStackCaptures
0x1800044e4  mov     ebx, 80004005h
0x1800044e9  jz      loc_1800043C0
0x1800044ef  mov     ecx, ebx
0x1800044f1  jmp     loc_18000438D
```
