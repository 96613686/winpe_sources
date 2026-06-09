# MatchNodeByUriAndName(IXMLDOMNode *,ushort const *,ushort const *,int *)

- ea: `0x18000e07c`
- end: `0x18000e216`
- name: `?MatchNodeByUriAndName@@YAJPEAUIXMLDOMNode@@PEBG1PEAH@Z`
- size: `410`
- prototype: `int(struct IXMLDOMNode *, const unsigned __int16 *, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d550`

## callees

- `0x18000e07c`
- `0x18000e21c`
- `0x1800171c4`
- `0x180033010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000e0d0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e0e3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e0d0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e0e3`
- `OLEAUT32!__imp_SysStringLen` at `0x18000e185`
- `OLEAUT32!__imp_SysStringLen` at `0x18000e185`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e1a3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e1a3`

## pseudocode

```c
__int64 __fastcall MatchNodeByUriAndName(struct IXMLDOMNode *a1, wchar_t *a2, const unsigned __int16 *a3, int *a4)
{
  struct IXMLDOMNodeVtbl *lpVtbl; // rax
  int v5; // edi
  int v10; // eax
  unsigned int v11; // ebx
  int v13; // ecx
  const unsigned __int16 *v14; // rax
  __int64 v15; // rcx
  __int64 cchCount2; // r15
  UINT v17; // eax
  BSTR bstrString; // [rsp+30h] [rbp-18h] BYREF
  BSTR String1[2]; // [rsp+38h] [rbp-10h] BYREF
  int v20; // [rsp+90h] [rbp+48h] BYREF

  lpVtbl = a1->lpVtbl;
  v5 = 0;
  bstrString = 0;
  String1[0] = 0;
  v20 = 0;
  v10 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, int *))lpVtbl->get_nodeType)(a1, &v20);
  v11 = v10;
  if ( v10 < 0 )
    goto LABEL_2;
  if ( v10 )
  {
    v11 = -2147467259;
  }
  else
  {
    if ( v20 == 8 )
    {
      v5 = 1;
      goto LABEL_24;
    }
    if ( !a3 )
      goto LABEL_20;
    v14 = a3;
    v15 = 0x7FFFFFFF;
    do
    {
      if ( !*v14 )
        break;
      ++v14;
      --v15;
    }
    while ( v15 );
    v11 = v15 == 0 ? 0x80070057 : 0;
    cchCount2 = (0x7FFFFFFF - v15) & -(__int64)(v15 != 0);
    if ( v15 )
    {
      v10 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))a1->lpVtbl->get_baseName)(a1, &bstrString);
      v11 = v10;
      if ( v10 < 0 )
        goto LABEL_2;
      if ( v10 || (v17 = SysStringLen(bstrString), CompareStringW(0x400u, 0, bstrString, v17, a3, cchCount2) != 2) )
      {
LABEL_24:
        *a4 = v5;
        v11 = 0;
        goto LABEL_3;
      }
LABEL_20:
      v5 = 1;
      if ( a2 )
      {
        v10 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))a1->lpVtbl->get_namespaceURI)(a1, String1);
        v5 = 0;
        v11 = v10;
        if ( v10 >= 0 )
        {
          if ( !v10 )
            v5 = XMPSchemaURIsMatch(String1[0], a2);
          goto LABEL_24;
        }
LABEL_2:
        if ( !g_doStackCaptures )
          goto LABEL_3;
        v13 = v10;
        goto LABEL_9;
      }
      goto LABEL_24;
    }
  }
  if ( g_doStackCaptures )
  {
    v13 = v11;
LABEL_9:
    DoStackCapture(v13);
  }
LABEL_3:
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( String1[0] )
    SysFreeString(String1[0]);
  return v11;
}

```

## disassembly

```asm
0x18000e07c  push    rbp
0x18000e07e  push    rbx
0x18000e07f  push    rsi
0x18000e080  push    rdi
0x18000e081  push    r12
0x18000e083  push    r13
0x18000e085  push    r14
0x18000e087  push    r15
0x18000e089  mov     rbp, rsp
0x18000e08c  sub     rsp, 48h
0x18000e090  mov     rax, [rcx]
0x18000e093  xor     edi, edi
0x18000e095  mov     r12, rdx
0x18000e098  mov     [rbp+bstrString], rdi
0x18000e09c  lea     rdx, [rbp+arg_0]
0x18000e0a0  mov     [rbp+String1], rdi
0x18000e0a4  mov     r13, r9
0x18000e0a7  mov     [rbp+arg_0], edi
0x18000e0aa  mov     rax, [rax+50h]
0x18000e0ae  mov     r14, r8
0x18000e0b1  mov     rsi, rcx
0x18000e0b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0b9  mov     ebx, eax
0x18000e0bb  test    eax, eax
0x18000e0bd  jns     short loc_18000E105
0x18000e0bf  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x18000e0c5  jnz     short loc_18000E0FC
0x18000e0c7  mov     rcx, [rbp+bstrString]; bstrString
0x18000e0cb  test    rcx, rcx
0x18000e0ce  jz      short loc_18000E0DA
0x18000e0d0  call    cs:__imp_SysFreeString
0x18000e0d6  mov     [rbp+bstrString], rdi
0x18000e0da  mov     rcx, [rbp+String1]; bstrString
0x18000e0de  test    rcx, rcx
0x18000e0e1  jz      short loc_18000E0E9
0x18000e0e3  call    cs:__imp_SysFreeString
0x18000e0e9  mov     eax, ebx
0x18000e0eb  add     rsp, 48h
0x18000e0ef  pop     r15
0x18000e0f1  pop     r14
0x18000e0f3  pop     r13
0x18000e0f5  pop     r12
0x18000e0f7  pop     rdi
0x18000e0f8  pop     rsi
0x18000e0f9  pop     rbx
0x18000e0fa  pop     rbp
0x18000e0fb  retn
0x18000e0fc  mov     ecx, eax; int
0x18000e0fe  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000e103  jmp     short loc_18000E0C7
0x18000e105  jnz     loc_18000E1F7
0x18000e10b  cmp     [rbp+arg_0], 8
0x18000e10f  jz      loc_18000E20F
0x18000e115  test    r14, r14
0x18000e118  jz      loc_18000E1AE
0x18000e11e  mov     edx, 7FFFFFFFh
0x18000e123  mov     rax, r14
0x18000e126  mov     ecx, edx
0x18000e128  cmp     [rax], di
0x18000e12b  jz      short loc_18000E137
0x18000e12d  add     rax, 2
0x18000e131  sub     rcx, 1
0x18000e135  jnz     short loc_18000E128
0x18000e137  mov     rax, rcx
0x18000e13a  neg     rax
0x18000e13d  mov     rax, rcx
0x18000e140  sbb     ebx, ebx
0x18000e142  sub     rdx, rcx
0x18000e145  not     ebx
0x18000e147  and     ebx, 80070057h
0x18000e14d  neg     rax
0x18000e150  sbb     r15, r15
0x18000e153  and     r15, rdx
0x18000e156  test    rcx, rcx
0x18000e159  jz      loc_18000E1FC
0x18000e15f  mov     rax, [rsi]
0x18000e162  lea     rdx, [rbp+bstrString]
0x18000e166  mov     rcx, rsi
0x18000e169  mov     rax, [rax+148h]
0x18000e170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e175  mov     ebx, eax
0x18000e177  test    eax, eax
0x18000e179  js      loc_18000E0BF
0x18000e17f  jnz     short loc_18000E1EA
0x18000e181  mov     rcx, [rbp+bstrString]; pbstr
0x18000e185  call    cs:__imp_SysStringLen
0x18000e18b  mov     r8, [rbp+bstrString]; lpString1
0x18000e18f  xor     edx, edx; dwCmpFlags
0x18000e191  mov     r9d, eax; cchCount1
0x18000e194  mov     [rsp+48h+cchCount2], r15d; cchCount2
0x18000e199  mov     ecx, 400h; Locale
0x18000e19e  mov     [rsp+48h+lpString2], r14; lpString2
0x18000e1a3  call    cs:__imp_CompareStringW
0x18000e1a9  cmp     eax, 2
0x18000e1ac  jnz     short loc_18000E1EA
0x18000e1ae  mov     edi, 1
0x18000e1b3  test    r12, r12
0x18000e1b6  jz      short loc_18000E1EA
0x18000e1b8  mov     rax, [rsi]
0x18000e1bb  lea     rdx, [rbp+String1]
0x18000e1bf  mov     rcx, rsi
0x18000e1c2  mov     rax, [rax+138h]
0x18000e1c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1ce  xor     edi, edi
0x18000e1d0  mov     ebx, eax
0x18000e1d2  test    eax, eax
0x18000e1d4  js      loc_18000E0BF
0x18000e1da  jnz     short loc_18000E1EA
0x18000e1dc  mov     rcx, [rbp+String1]; String1
0x18000e1e0  mov     rdx, r12; String2
0x18000e1e3  call    ?XMPSchemaURIsMatch@@YAHPEBG0@Z; XMPSchemaURIsMatch(ushort const *,ushort const *)
0x18000e1e8  mov     edi, eax
0x18000e1ea  mov     [r13+0], edi
0x18000e1ee  xor     edi, edi
0x18000e1f0  mov     ebx, edi
0x18000e1f2  jmp     loc_18000E0C7
0x18000e1f7  mov     ebx, 80004005h
0x18000e1fc  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x18000e202  jz      loc_18000E0C7
0x18000e208  mov     ecx, ebx
0x18000e20a  jmp     loc_18000E0FE
0x18000e20f  mov     edi, 1
0x18000e214  jmp     short loc_18000E1EA
```
