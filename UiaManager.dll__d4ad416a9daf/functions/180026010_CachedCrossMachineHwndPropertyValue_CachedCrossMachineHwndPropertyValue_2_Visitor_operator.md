# _CachedCrossMachineHwndPropertyValue::CachedCrossMachineHwndPropertyValue_::_2_::Visitor::operator()

- ea: `0x180026010`
- end: `0x180026082`
- name: `_CachedCrossMachineHwndPropertyValue::CachedCrossMachineHwndPropertyValue_::_2_::Visitor::operator()`
- size: `114`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18007a128`

## callees

- `0x180026010`
- `0x1800260bc`
- `0x180031540`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180026025`
- `OLEAUT32!__imp_VariantInit` at `0x180026025`
- `OLEAUT32!__imp_VariantClear` at `0x18002606e`
- `OLEAUT32!__imp_VariantClear` at `0x18002606e`
- `OLEAUT32!__imp_VariantCopy` at `0x180026034`
- `OLEAUT32!__imp_VariantCopy` at `0x180026034`

## string_xrefs

- `0x180026046`: `onecore\windows\accessibletech\uiamanager\dll\hwndinfocache.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CachedCrossMachineHwndPropertyValue::CachedCrossMachineHwndPropertyValue_::_2_::Visitor::operator()(
        __int64 a1,
        __int64 a2,
        const VARIANTARG *a3)
{
  HRESULT v5; // eax
  __int64 v6; // rdx
  int v8; // [rsp+20h] [rbp-28h]
  VARIANTARG pvarg; // [rsp+28h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  VariantInit(&pvarg);
  v5 = VariantCopy(&pvarg, a3);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x14,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\hwndinfocache.cpp",
      (const char *)(unsigned int)v5,
      v8);
  std::_Variant_storage_<0,long,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)>>::_Variant_storage_<0,long,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)>>(
    a2,
    v6,
    &pvarg);
  *(_BYTE *)(a2 + 24) = 1;
  VariantClear(&pvarg);
  return a2;
}

```

## disassembly

```asm
0x180026010  mov     [rsp+arg_0], rbx
0x180026015  push    rdi
0x180026016  sub     rsp, 40h
0x18002601a  mov     rbx, r8
0x18002601d  mov     rdi, rdx
0x180026020  lea     rcx, [rsp+48h+pvarg]; pvarg
0x180026025  call    cs:__imp_VariantInit
0x18002602b  nop
0x18002602c  mov     rdx, rbx; pvargSrc
0x18002602f  lea     rcx, [rsp+48h+pvarg]; pvargDest
0x180026034  call    cs:__imp_VariantCopy
0x18002603a  mov     rcx, [rsp+48h]; this
0x18002603f  test    eax, eax
0x180026041  jns     short loc_180026058
0x180026043  mov     r9d, eax; char *
0x180026046  lea     r8, aOnecoreWindows_33; "onecore\\windows\\accessibletech\\uiama"...
0x18002604d  mov     edx, 14h; void *
0x180026052  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180026058  lea     r8, [rsp+48h+pvarg]
0x18002605d  mov     rcx, rdi
0x180026060  call    ??$?0$00V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@$0A@@?$_Variant_storage_@$0A@JV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@QEAA@U?$integral_constant@_K$00@1@$$QEAV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@Z; std::_Variant_storage_<0,long,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)>>::_Variant_storage_<0,long,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)>>(std::integral_constant<unsigned __int64,1>,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)> &&)
0x180026065  mov     byte ptr [rdi+18h], 1
0x180026069  lea     rcx, [rsp+48h+pvarg]; pvarg
0x18002606e  call    cs:__imp_VariantClear
0x180026074  mov     rax, rdi
0x180026077  mov     rbx, [rsp+48h+arg_0]
0x18002607c  add     rsp, 40h
0x180026080  pop     rdi
0x180026081  retn
```
