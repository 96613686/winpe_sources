# PrimitiveDisplayOverride::SetProperty(_MTF_PRIMITIVE_PROP *)

- ea: `0x18000ec10`
- end: `0x18000ed24`
- name: `?SetProperty@PrimitiveDisplayOverride@@UEAAJPEAU_MTF_PRIMITIVE_PROP@@@Z`
- size: `276`
- prototype: `__int64 __fastcall(PrimitiveDisplayOverride *__hidden this, struct _MTF_PRIMITIVE_PROP *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000cd18`
- `0x18000ec10`
- `0x18000edb8`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ecac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ecac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ecbf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ecbf`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ec73`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ec73`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ecb7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ecd9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ecb7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ecd9`

## string_xrefs

- `0x18000ed11`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PrimitiveDisplayOverride::SetProperty(PrimitiveDisplayOverride *this, const OLECHAR **a2)
{
  int v4; // r12d
  __int64 v5; // rcx
  int v6; // eax
  const char *v7; // r9
  OLECHAR *v8; // rbx
  OLECHAR **v9; // r14
  OLECHAR *v10; // r15
  DWORD LastError; // edi
  OLECHAR *v12; // rax
  __int64 result; // rax
  _QWORD v14[3]; // [rsp+20h] [rbp-58h] BYREF
  int v15; // [rsp+38h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v14[1] = &PrimitiveOverrideBase::ScopedDropPropertyBits::`vftable';
  v14[2] = a2;
  v4 = *(_DWORD *)a2;
  v15 = v4;
  *(_DWORD *)a2 = v4 & 0xFFFFFFFD;
  v5 = *((_QWORD *)this + 3);
  try
  {
    v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 32LL))(v5);
    if ( v6 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x99,
        (int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\lib\\primitiveoverride.cpp",
        (const char *)(unsigned int)v6,
        v14[0]);
    if ( (v4 & 2) != 0 )
    {
      v8 = SysAllocString(a2[2]);
      v14[0] = v8;
      if ( !v8 )
        wil::details::in1diag3::_Throw_NullAlloc(
          retaddr,
          (void *)0x15F3,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v7);
      v9 = (OLECHAR **)((char *)this + 32);
      if ( v9 == v14 )
      {
        v12 = v8;
      }
      else
      {
        v10 = *v9;
        if ( *v9 )
        {
          LastError = GetLastError();
          SysFreeString(v10);
          SetLastError(LastError);
        }
        *v9 = v8;
        v8 = 0;
        v12 = 0;
      }
      if ( v12 )
        SysFreeString(v8);
    }
    *(_DWORD *)a2 = v4;
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xA3,
                           (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\lib\\primitiveoverride.cpp",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x18000ec10  mov     r11, rsp
0x18000ec13  push    rbx
0x18000ec14  push    rsi
0x18000ec15  push    rdi
0x18000ec16  push    r12
0x18000ec18  push    r14
0x18000ec1a  push    r15
0x18000ec1c  sub     rsp, 48h
0x18000ec20  mov     rsi, rdx
0x18000ec23  mov     r14, rcx
0x18000ec26  mov     dword ptr [r11+8], 0
0x18000ec2e  lea     rax, ??_7ScopedDropPropertyBits@PrimitiveOverrideBase@@6B@; const PrimitiveOverrideBase::ScopedDropPropertyBits::`vftable'
0x18000ec35  mov     [r11-50h], rax
0x18000ec39  mov     [r11-48h], rdx
0x18000ec3d  mov     r12d, [rdx]
0x18000ec40  mov     [r11-40h], r12d
0x18000ec44  mov     eax, r12d
0x18000ec47  and     eax, 0FFFFFFFDh
0x18000ec4a  mov     [rdx], eax
0x18000ec4c  mov     rcx, [rcx+18h]
0x18000ec50  mov     rax, [rcx]
0x18000ec53  mov     rax, [rax+20h]
0x18000ec57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec5c  mov     rcx, [rsp+78h]; this
0x18000ec61  test    eax, eax
0x18000ec63  js      loc_18000ECFC
0x18000ec69  test    r12b, 2
0x18000ec6d  jz      short loc_18000ECE0
0x18000ec6f  mov     rcx, [rsi+10h]; psz
0x18000ec73  call    cs:__imp_SysAllocString
0x18000ec79  mov     rbx, rax
0x18000ec7c  mov     [rsp+78h+var_58], rax
0x18000ec81  mov     [rsp+78h+arg_0], 1
0x18000ec8c  mov     rcx, [rsp+78h]; this
0x18000ec91  test    rax, rax
0x18000ec94  jz      short loc_18000ED11
0x18000ec96  add     r14, 20h ; ' '
0x18000ec9a  lea     rax, [rsp+78h+var_58]
0x18000ec9f  cmp     r14, rax
0x18000eca2  jz      short loc_18000ECCE
0x18000eca4  mov     r15, [r14]
0x18000eca7  test    r15, r15
0x18000ecaa  jz      short loc_18000ECC5
0x18000ecac  call    cs:__imp_GetLastError
0x18000ecb2  mov     edi, eax
0x18000ecb4  mov     rcx, r15; bstrString
0x18000ecb7  call    cs:__imp_SysFreeString
0x18000ecbd  mov     ecx, edi; dwErrCode
0x18000ecbf  call    cs:__imp_SetLastError
0x18000ecc5  mov     [r14], rbx
0x18000ecc8  xor     ebx, ebx
0x18000ecca  xor     eax, eax
0x18000eccc  jmp     short loc_18000ECD1
0x18000ecce  mov     rax, rbx
0x18000ecd1  test    rax, rax
0x18000ecd4  jz      short loc_18000ECE0
0x18000ecd6  mov     rcx, rbx; bstrString
0x18000ecd9  call    cs:__imp_SysFreeString
0x18000ecdf  nop
0x18000ece0  mov     [rsi], r12d
0x18000ece3  xor     eax, eax
0x18000ece5  jmp     short loc_18000ECEE
0x18000ece7  mov     eax, [rsp+78h+arg_0]
0x18000ecee  add     rsp, 48h
0x18000ecf2  pop     r15
0x18000ecf4  pop     r14
0x18000ecf6  pop     r12
0x18000ecf8  pop     rdi
0x18000ecf9  pop     rsi
0x18000ecfa  pop     rbx
0x18000ecfb  retn
0x18000ecfc  mov     r9d, eax; char *
0x18000ecff  lea     r8, aMincoreTextinp_2; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x18000ed06  mov     edx, 99h; void *
0x18000ed0b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000ed11  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000ed18  mov     edx, 15F3h; void *
0x18000ed1d  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
