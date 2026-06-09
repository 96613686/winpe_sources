# XcAddChildElementDWORD(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,IXMLDOMNode * *)

- ea: `0x180012260`
- end: `0x180012307`
- name: `?XcAddChildElementDWORD@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEAPEAU2@@Z`
- size: `167`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *, struct IXMLDOMNode *, OLECHAR *psz, OLECHAR *, LONG)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000a298`
- `0x18000f854`
- `0x18000fc08`
- `0x18001027c`

## callees

- `0x180011f90`
- `0x180012260`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18001227c`
- `OLEAUT32!__imp_VariantInit` at `0x18001227c`
- `OLEAUT32!__imp_VariantClear` at `0x1800122f4`
- `OLEAUT32!__imp_VariantClear` at `0x1800122f4`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800122aa`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800122aa`

## pseudocode

```c
__int64 __fastcall XcAddChildElementDWORD(
        struct IXMLDOMDocument2 *a1,
        struct IXMLDOMNode *a2,
        OLECHAR *psz,
        OLECHAR *a4,
        LONG a5)
{
  HRESULT v9; // eax
  unsigned int v10; // ebx
  VARIANTARG pvarg; // [rsp+30h] [rbp-48h] BYREF

  VariantInit(&pvarg);
  pvarg.vt = 19;
  pvarg.lVal = a5;
  v9 = VariantChangeType(&pvarg, &pvarg, 0, 8u);
  v10 = v9;
  if ( v9 >= 0 )
    goto LABEL_5;
  if ( (v9 & 0x1FFF0000) == 0x70000 )
    v10 = (unsigned __int16)v9;
  if ( !v10 )
LABEL_5:
    v10 = XcAddChildElement(a1, a2, psz, a4, pvarg.bstrVal, 0);
  VariantClear(&pvarg);
  return v10;
}

```

## disassembly

```asm
0x180012260  push    rbx
0x180012262  push    rbp
0x180012263  push    rsi
0x180012264  push    rdi
0x180012265  push    r14
0x180012267  sub     rsp, 50h
0x18001226b  mov     r14, rcx
0x18001226e  mov     rdi, r9
0x180012271  lea     rcx, [rsp+78h+pvarg]; pvarg
0x180012276  mov     rsi, r8
0x180012279  mov     rbp, rdx
0x18001227c  call    cs:__imp_VariantInit
0x180012282  mov     eax, 13h
0x180012287  lea     rdx, [rsp+78h+pvarg]; pvarSrc
0x18001228c  mov     word ptr [rsp+78h+pvarg], ax
0x180012291  lea     rcx, [rsp+78h+pvarg]; pvargDest
0x180012296  mov     eax, [rsp+78h+arg_20]
0x18001229d  mov     r9d, 8; vt
0x1800122a3  xor     r8d, r8d; wFlags
0x1800122a6  mov     dword ptr [rsp+78h+pvarg+8], eax
0x1800122aa  call    cs:__imp_VariantChangeType
0x1800122b0  mov     ebx, eax
0x1800122b2  test    eax, eax
0x1800122b4  jns     short loc_1800122C9
0x1800122b6  and     eax, 1FFF0000h
0x1800122bb  cmp     eax, 70000h
0x1800122c0  jnz     short loc_1800122C5
0x1800122c2  movzx   ebx, bx
0x1800122c5  test    ebx, ebx
0x1800122c7  jnz     short loc_1800122EF
0x1800122c9  mov     rax, qword ptr [rsp+78h+pvarg+8]
0x1800122ce  mov     r9, rdi; OLECHAR *
0x1800122d1  mov     [rsp+78h+var_50], 0; struct IXMLDOMNode **
0x1800122da  mov     r8, rsi; psz
0x1800122dd  mov     rdx, rbp; struct IXMLDOMNode *
0x1800122e0  mov     [rsp+78h+var_58], rax; OLECHAR *
0x1800122e5  mov     rcx, r14; struct IXMLDOMDocument2 *
0x1800122e8  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x1800122ed  mov     ebx, eax
0x1800122ef  lea     rcx, [rsp+78h+pvarg]; pvarg
0x1800122f4  call    cs:__imp_VariantClear
0x1800122fa  mov     eax, ebx
0x1800122fc  add     rsp, 50h
0x180012300  pop     r14
0x180012302  pop     rdi
0x180012303  pop     rsi
0x180012304  pop     rbp
0x180012305  pop     rbx
0x180012306  retn
```
