# CMetadataXMPReaderWriter::CheckXMPMetadataName(IXMLDOMNode *)

- ea: `0x1800144bc`
- end: `0x180014558`
- name: `?CheckXMPMetadataName@CMetadataXMPReaderWriter@@IEAAHPEAUIXMLDOMNode@@@Z`
- size: `156`
- prototype: `_BOOL8 __fastcall(OLECHAR *this, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d550`

## callees

- `0x1800144bc`
- `0x1800171c4`
- `0x180033010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180014545`
- `OLEAUT32!__imp_SysFreeString` at `0x180014545`
- `OLEAUT32!__imp_SysStringLen` at `0x180014501`
- `OLEAUT32!__imp_SysStringLen` at `0x180014501`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001452f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001452f`

## pseudocode

```c
_BOOL8 __fastcall CMetadataXMPReaderWriter::CheckXMPMetadataName(OLECHAR *this, struct IXMLDOMNode *a2)
{
  struct IXMLDOMNodeVtbl *lpVtbl; // rax
  BOOL v3; // ebx
  int v4; // eax
  UINT v5; // eax
  BSTR pbstr; // [rsp+40h] [rbp+8h] BYREF

  pbstr = this;
  lpVtbl = a2->lpVtbl;
  v3 = 0;
  pbstr = 0;
  v4 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))lpVtbl->get_nodeName)(a2, &pbstr);
  if ( v4 >= 0 )
  {
    if ( !v4 )
    {
      v5 = SysStringLen(pbstr);
      v3 = CompareStringW(0x400u, 1u, pbstr, v5, L"xmp:xmpmeta", 11) == 2;
    }
  }
  else if ( g_doStackCaptures )
  {
    DoStackCapture(v4);
  }
  if ( pbstr )
    SysFreeString(pbstr);
  return v3;
}

```

## disassembly

```asm
0x1800144bc  mov     r11, rsp
0x1800144bf  mov     [r11+10h], rbx
0x1800144c3  mov     [r11+8], rcx
0x1800144c7  push    rdi
0x1800144c8  sub     rsp, 30h
0x1800144cc  mov     rax, [rdx]
0x1800144cf  mov     rcx, rdx
0x1800144d2  xor     ebx, ebx
0x1800144d4  lea     rdx, [r11+8]
0x1800144d8  mov     [r11+8], rbx
0x1800144dc  mov     rax, [rax+38h]
0x1800144e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144e5  test    eax, eax
0x1800144e7  jns     short loc_1800144FA
0x1800144e9  cmp     cs:?g_doStackCaptures@@3HA, ebx; int g_doStackCaptures
0x1800144ef  jz      short loc_18001453B
0x1800144f1  mov     ecx, eax; int
0x1800144f3  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800144f8  jmp     short loc_18001453B
0x1800144fa  jnz     short loc_18001453B
0x1800144fc  mov     rcx, [rsp+38h+pbstr]; pbstr
0x180014501  call    cs:__imp_SysStringLen
0x180014507  mov     r8, [rsp+38h+pbstr]; lpString1
0x18001450c  lea     rcx, aXmpXmpmeta; "xmp:xmpmeta"
0x180014513  mov     [rsp+38h+cchCount2], 0Bh; cchCount2
0x18001451b  mov     edi, 1
0x180014520  mov     [rsp+38h+lpString2], rcx; lpString2
0x180014525  mov     r9d, eax; cchCount1
0x180014528  mov     ecx, 400h; Locale
0x18001452d  mov     edx, edi; dwCmpFlags
0x18001452f  call    cs:__imp_CompareStringW
0x180014535  cmp     eax, 2
0x180014538  cmovz   ebx, edi
0x18001453b  mov     rcx, [rsp+38h+pbstr]; bstrString
0x180014540  test    rcx, rcx
0x180014543  jz      short loc_18001454B
0x180014545  call    cs:__imp_SysFreeString
0x18001454b  mov     eax, ebx
0x18001454d  mov     rbx, [rsp+38h+arg_8]
0x180014552  add     rsp, 30h
0x180014556  pop     rdi
0x180014557  retn
```
