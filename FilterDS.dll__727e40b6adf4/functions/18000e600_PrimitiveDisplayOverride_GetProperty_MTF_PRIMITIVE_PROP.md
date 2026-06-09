# PrimitiveDisplayOverride::GetProperty(_MTF_PRIMITIVE_PROP *)

- ea: `0x18000e600`
- end: `0x18000e6c0`
- name: `?GetProperty@PrimitiveDisplayOverride@@UEAAJPEAU_MTF_PRIMITIVE_PROP@@@Z`
- size: `192`
- prototype: `__int64 __fastcall(PrimitiveDisplayOverride *__hidden this, struct _MTF_PRIMITIVE_PROP *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000cd18`
- `0x18000e600`
- `0x18000edb8`
- `0x180024010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000e65d`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e65d`

## string_xrefs

- `0x18000e6ad`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PrimitiveDisplayOverride::GetProperty(
        PrimitiveDisplayOverride *this,
        struct _MTF_PRIMITIVE_PROP *a2)
{
  int v4; // edi
  __int64 v5; // rcx
  int v6; // eax
  const char *v7; // r9
  BSTR v8; // rax
  __int64 result; // rax
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v4 = *(_DWORD *)a2;
  *(_DWORD *)a2 &= ~2u;
  v5 = *((_QWORD *)this + 3);
  try
  {
    v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 24LL))(v5);
    if ( v6 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x87,
        (int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\lib\\primitiveoverride.cpp",
        (const char *)(unsigned int)v6,
        (int)&PrimitiveOverrideBase::ScopedDropPropertyBits::`vftable');
    if ( (v4 & 2) != 0 )
    {
      v8 = SysAllocString(*((const OLECHAR **)this + 4));
      if ( !v8 )
        wil::details::in1diag3::_Throw_NullAlloc(
          retaddr,
          (void *)0x15F3,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v7);
      *((_QWORD *)a2 + 2) = v8;
    }
    *(_DWORD *)a2 = v4;
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x93,
                           (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\lib\\primitiveoverride.cpp",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x18000e600  mov     r11, rsp
0x18000e603  mov     [r11+18h], rbx
0x18000e607  mov     [r11+20h], rsi
0x18000e60b  push    rdi
0x18000e60c  sub     rsp, 40h
0x18000e610  mov     rbx, rdx
0x18000e613  mov     rsi, rcx
0x18000e616  mov     [rsp+48h+arg_0], 0
0x18000e61e  lea     rax, ??_7ScopedDropPropertyBits@PrimitiveOverrideBase@@6B@; const PrimitiveOverrideBase::ScopedDropPropertyBits::`vftable'
0x18000e625  mov     [r11-28h], rax
0x18000e629  mov     [r11-20h], rdx
0x18000e62d  mov     edi, [rdx]
0x18000e62f  mov     [rsp+48h+var_18], edi
0x18000e633  mov     eax, edi
0x18000e635  and     eax, 0FFFFFFFDh
0x18000e638  mov     [rdx], eax
0x18000e63a  mov     rcx, [rcx+18h]
0x18000e63e  mov     rax, [rcx]
0x18000e641  mov     rax, [rax+18h]
0x18000e645  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e64a  mov     rcx, [rsp+48h]; this
0x18000e64f  test    eax, eax
0x18000e651  js      short loc_18000E698
0x18000e653  test    dil, 2
0x18000e657  jz      short loc_18000E67E
0x18000e659  mov     rcx, [rsi+20h]; psz
0x18000e65d  call    cs:__imp_SysAllocString
0x18000e663  mov     [rsp+48h+arg_8], rax
0x18000e668  mov     [rsp+48h+arg_0], 1
0x18000e670  mov     rcx, [rsp+48h]; this
0x18000e675  test    rax, rax
0x18000e678  jz      short loc_18000E6AD
0x18000e67a  mov     [rbx+10h], rax
0x18000e67e  mov     [rbx], edi
0x18000e680  xor     eax, eax
0x18000e682  jmp     short loc_18000E688
0x18000e684  mov     eax, [rsp+48h+arg_0]
0x18000e688  mov     rbx, [rsp+48h+arg_10]
0x18000e68d  mov     rsi, [rsp+48h+arg_18]
0x18000e692  add     rsp, 40h
0x18000e696  pop     rdi
0x18000e697  retn
0x18000e698  mov     r9d, eax; char *
0x18000e69b  lea     r8, aMincoreTextinp_2; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x18000e6a2  mov     edx, 87h; void *
0x18000e6a7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000e6ad  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e6b4  mov     edx, 15F3h; void *
0x18000e6b9  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
