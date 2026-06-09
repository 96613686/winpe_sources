# Dynamo::StateEntry::SetValue(tagVARIANT const &)

- ea: `0x140048d90`
- end: `0x140048e7a`
- name: `?SetValue@StateEntry@Dynamo@@UEAAXAEBUtagVARIANT@@@Z`
- size: `234`
- prototype: `void(Dynamo::StateEntry *__hidden this, const struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x14000a6e4`
- `0x140048d90`

## import_xrefs

- `DMCmnUtils!OmaDmRegistrySetBinary` at `0x140048e16`
- `DMCmnUtils!OmaDmRegistrySetBinary` at `0x140048e16`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x140048db1`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x140048db1`
- `OLEAUT32!__imp_VariantInit` at `0x140048dc9`
- `OLEAUT32!__imp_VariantInit` at `0x140048dc9`
- `OLEAUT32!__imp_VariantClear` at `0x140048e2a`
- `OLEAUT32!__imp_VariantClear` at `0x140048e2a`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x140048de6`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x140048de6`
- `OLEAUT32!__imp_SysStringByteLen` at `0x140048dfa`
- `OLEAUT32!__imp_SysStringByteLen` at `0x140048dfa`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Dynamo::StateEntry::SetValue(HKEY *this, const struct tagVARIANT *a2)
{
  int v4; // eax
  HRESULT v5; // eax
  UINT v6; // eax
  int v7; // eax
  int vt; // [rsp+20h] [rbp-38h]
  int vta; // [rsp+20h] [rbp-38h]
  int vtb; // [rsp+20h] [rbp-38h]
  VARIANTARG pvarg; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v4 = OmaDmRegistrySetDWORD(this[1], 0, L"VarType", a2->vt);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x32,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\stateentry.cpp",
      (const char *)(unsigned int)v4,
      vt);
  VariantInit(&pvarg);
  v5 = VariantChangeTypeEx(&pvarg, a2, 0x7Fu, 0, 8u);
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x35,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\stateentry.cpp",
      (const char *)(unsigned int)v5,
      vta);
  v6 = SysStringByteLen(pvarg.bstrVal);
  v7 = OmaDmRegistrySetBinary(this[1], 0, L"Data", pvarg.bstrVal, v6);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3A,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\stateentry.cpp",
      (const char *)(unsigned int)v7,
      vtb);
  VariantClear(&pvarg);
}

```

## disassembly

```asm
0x140048d90  mov     [rsp+arg_0], rbx
0x140048d95  push    rdi
0x140048d96  sub     rsp, 50h
0x140048d9a  mov     rbx, rdx
0x140048d9d  mov     rdi, rcx
0x140048da0  movzx   r9d, word ptr [rdx]
0x140048da4  lea     r8, aVartype; "VarType"
0x140048dab  xor     edx, edx
0x140048dad  mov     rcx, [rcx+8]
0x140048db1  call    cs:__imp_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x140048db7  mov     rcx, [rsp+58h]; this
0x140048dbc  test    eax, eax
0x140048dbe  js      loc_140048E50
0x140048dc4  lea     rcx, [rsp+58h+pvarg]; pvarg
0x140048dc9  call    cs:__imp_VariantInit
0x140048dcf  nop
0x140048dd0  xor     r9d, r9d; wFlags
0x140048dd3  mov     [rsp+58h+vt], 8; int
0x140048dda  lea     r8d, [r9+7Fh]; lcid
0x140048dde  mov     rdx, rbx; pvarSrc
0x140048de1  lea     rcx, [rsp+58h+pvarg]; pvargDest
0x140048de6  call    cs:__imp_VariantChangeTypeEx
0x140048dec  mov     rcx, [rsp+58h]; this
0x140048df1  test    eax, eax
0x140048df3  js      short loc_140048E65
0x140048df5  mov     rcx, qword ptr [rsp+58h+pvarg+8]; bstr
0x140048dfa  call    cs:__imp_SysStringByteLen
0x140048e00  mov     dword ptr [rsp+58h+vt], eax; int
0x140048e04  mov     r9, qword ptr [rsp+58h+pvarg+8]
0x140048e09  lea     r8, aData; "Data"
0x140048e10  xor     edx, edx
0x140048e12  mov     rcx, [rdi+8]
0x140048e16  call    cs:__imp_?OmaDmRegistrySetBinary@@YAJPEAUHKEY__@@PEBG1PEAXK@Z; OmaDmRegistrySetBinary(HKEY__ *,ushort const *,ushort const *,void *,ulong)
0x140048e1c  mov     rcx, [rsp+58h]; this
0x140048e21  test    eax, eax
0x140048e23  js      short loc_140048E3B
0x140048e25  lea     rcx, [rsp+58h+pvarg]; pvarg
0x140048e2a  call    cs:__imp_VariantClear
0x140048e30  mov     rbx, [rsp+58h+arg_0]
0x140048e35  add     rsp, 50h
0x140048e39  pop     rdi
0x140048e3a  retn
0x140048e3b  mov     r9d, eax; char *
0x140048e3e  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140048e45  mov     edx, 3Ah ; ':'; void *
0x140048e4a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140048e50  mov     r9d, eax; char *
0x140048e53  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140048e5a  mov     edx, 32h ; '2'; void *
0x140048e5f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140048e65  mov     r9d, eax; char *
0x140048e68  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140048e6f  mov     edx, 35h ; '5'; void *
0x140048e74  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
