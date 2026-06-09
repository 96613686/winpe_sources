# XcAddChildElementEnum(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,_XC_STRING_VALUE_MAPPING const *,ulong,IXMLDOMNode * *)

- ea: `0x180012310`
- end: `0x1800123cc`
- name: `?XcAddChildElementEnum@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEBU_XC_STRING_VALUE_MAPPING@@KPEAPEAU2@@Z`
- size: `188`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *, struct IXMLDOMNode *, OLECHAR *psz, OLECHAR *, unsigned int, const struct _XC_STRING_VALUE_MAPPING *, unsigned int)`
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800092fc`
- `0x180009c84`
- `0x18000a298`
- `0x18000b060`
- `0x18000ec80`
- `0x18000fc08`
- `0x1800103ac`

## callees

- `0x180011f90`
- `0x180012310`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180012374`
- `OLEAUT32!__imp_SysAllocString` at `0x180012374`
- `OLEAUT32!__imp_SysFreeString` at `0x18001236b`
- `OLEAUT32!__imp_SysFreeString` at `0x180012384`
- `OLEAUT32!__imp_SysFreeString` at `0x1800123b5`
- `OLEAUT32!__imp_SysFreeString` at `0x18001236b`
- `OLEAUT32!__imp_SysFreeString` at `0x180012384`
- `OLEAUT32!__imp_SysFreeString` at `0x1800123b5`

## pseudocode

```c
__int64 __fastcall XcAddChildElementEnum(
        struct IXMLDOMDocument2 *a1,
        struct IXMLDOMNode *a2,
        OLECHAR *psz,
        OLECHAR *a4,
        unsigned int a5,
        const struct _XC_STRING_VALUE_MAPPING *a6,
        unsigned int a7)
{
  OLECHAR *v7; // rbx
  unsigned int v8; // eax
  unsigned int v13; // edi
  const OLECHAR *v14; // rbx

  v7 = 0;
  v8 = 0;
  v13 = 1206;
  if ( a7 )
  {
    while ( *((_DWORD *)a6 + 4 * v8 + 2) != a5 )
    {
      if ( ++v8 >= a7 )
        goto LABEL_8;
    }
    v14 = (const OLECHAR *)*((_QWORD *)a6 + 2 * v8);
    SysFreeString(0);
    v7 = SysAllocString(v14);
    if ( v7 )
    {
      SysFreeString(0);
      v13 = XcAddChildElement(a1, a2, psz, a4, v7, 0);
    }
    else
    {
      v7 = 0;
      v13 = 14;
    }
  }
LABEL_8:
  SysFreeString(v7);
  return v13;
}

```

## disassembly

```asm
0x180012310  push    rbx
0x180012312  push    rbp
0x180012313  push    rsi
0x180012314  push    rdi
0x180012315  push    r12
0x180012317  push    r14
0x180012319  push    r15
0x18001231b  sub     rsp, 30h
0x18001231f  mov     r11d, [rsp+68h+arg_30]
0x180012327  xor     ebx, ebx
0x180012329  mov     r10, [rsp+68h+arg_28]
0x180012331  xor     eax, eax
0x180012333  mov     rbp, r9
0x180012336  mov     r14, r8
0x180012339  mov     r15, rdx
0x18001233c  mov     r12, rcx
0x18001233f  mov     edi, 4B6h
0x180012344  test    r11d, r11d
0x180012347  jz      short loc_1800123B2
0x180012349  mov     esi, [rsp+68h+arg_20]
0x180012350  mov     ecx, eax
0x180012352  add     rcx, rcx
0x180012355  cmp     [r10+rcx*8+8], esi
0x18001235a  jz      short loc_180012365
0x18001235c  inc     eax
0x18001235e  cmp     eax, r11d
0x180012361  jb      short loc_180012350
0x180012363  jmp     short loc_1800123B2
0x180012365  mov     rbx, [r10+rcx*8]
0x180012369  xor     ecx, ecx; bstrString
0x18001236b  call    cs:__imp_SysFreeString
0x180012371  mov     rcx, rbx; psz
0x180012374  call    cs:__imp_SysAllocString
0x18001237a  mov     rbx, rax
0x18001237d  test    rax, rax
0x180012380  jz      short loc_1800123AD
0x180012382  xor     ecx, ecx; bstrString
0x180012384  call    cs:__imp_SysFreeString
0x18001238a  mov     r9, rbp; OLECHAR *
0x18001238d  mov     [rsp+68h+var_40], 0; struct IXMLDOMNode **
0x180012396  mov     r8, r14; psz
0x180012399  mov     [rsp+68h+var_48], rbx; OLECHAR *
0x18001239e  mov     rdx, r15; struct IXMLDOMNode *
0x1800123a1  mov     rcx, r12; struct IXMLDOMDocument2 *
0x1800123a4  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x1800123a9  mov     edi, eax
0x1800123ab  jmp     short loc_1800123B2
0x1800123ad  xor     ebx, ebx
0x1800123af  lea     edi, [rbx+0Eh]
0x1800123b2  mov     rcx, rbx; bstrString
0x1800123b5  call    cs:__imp_SysFreeString
0x1800123bb  mov     eax, edi
0x1800123bd  add     rsp, 30h
0x1800123c1  pop     r15
0x1800123c3  pop     r14
0x1800123c5  pop     r12
0x1800123c7  pop     rdi
0x1800123c8  pop     rsi
0x1800123c9  pop     rbp
0x1800123ca  pop     rbx
0x1800123cb  retn
```
