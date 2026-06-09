# Cn::Com::DeferredRelease::CommonCreate(IUnknown *,void (*)(void *),Cn::Com::DeferredRelease::DeferredAction,void *)

- ea: `0x1800207e8`
- end: `0x180020884`
- name: `?CommonCreate@DeferredRelease@Com@Cn@@AEAAXPEAUIUnknown@@P6AXPEAX@ZUDeferredAction@123@1@Z`
- size: `156`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001ebcc`
- `0x180020550`
- `0x180021bfc`

## callees

- `0x18000b0bc`
- `0x1800207e8`
- `0x1800a2108`
- `0x1800c7d64`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18002082a`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18002082a`

## string_xrefs

- `0x180020869`: `onecore\internal\sdk\inc\wil\opensource/wil/safecast.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Cn::Com::DeferredRelease::CommonCreate(__int64 *a1, __int64 a2, __int64 a3, char a4, __int64 a5)
{
  int v9; // eax
  unsigned __int64 v10; // rdi
  __int64 *v11; // rax
  __int64 *v12; // rdx
  __int64 result; // rax
  size_t Count[7]; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  LODWORD(Count[0]) = 0;
  v9 = ULongLongToUInt(0x20u, (unsigned int *)Count);
  if ( v9 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x10F,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/safecast.h",
      (const char *)(unsigned int)v9,
      Count[0]);
  v10 = LODWORD(Count[0]);
  v11 = (__int64 *)calloc(LODWORD(Count[0]), 1u);
  v12 = v11;
  if ( !v11 )
    CFlat::Abandonment::OutOfMemory(v10);
  if ( a2 )
    a3 = a2;
  v11[3] = a3;
  v11[2] = a5;
  result = *a1;
  *v12 = *a1;
  *((_BYTE *)v12 + 8) = a4;
  *a1 = (__int64)v12;
  return result;
}

```

## disassembly

```asm
0x1800207e8  push    rbx
0x1800207ea  push    rbp
0x1800207eb  push    rsi
0x1800207ec  push    rdi
0x1800207ed  push    r14
0x1800207ef  sub     rsp, 30h
0x1800207f3  mov     bl, r9b
0x1800207f6  mov     rsi, r8
0x1800207f9  mov     rbp, rdx
0x1800207fc  mov     r14, rcx
0x1800207ff  mov     dword ptr [rsp+58h+Count], 0; int
0x180020807  lea     rdx, [rsp+58h+Count]; unsigned int *
0x18002080c  mov     ecx, 20h ; ' '; unsigned __int64
0x180020811  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180020816  mov     rcx, [rsp+58h]; this
0x18002081b  test    eax, eax
0x18002081d  js      short loc_180020866
0x18002081f  mov     edi, dword ptr [rsp+58h+Count]
0x180020823  mov     edx, 1; Size
0x180020828  mov     ecx, edi; Count
0x18002082a  call    cs:__imp_calloc
0x180020830  mov     rdx, rax
0x180020833  test    rax, rax
0x180020836  jz      short loc_18002087B
0x180020838  test    rbp, rbp
0x18002083b  cmovnz  rsi, rbp
0x18002083f  mov     [rax+18h], rsi
0x180020843  mov     rax, [rsp+58h+arg_20]
0x18002084b  mov     [rdx+10h], rax
0x18002084f  mov     rax, [r14]
0x180020852  mov     [rdx], rax
0x180020855  mov     [rdx+8], bl
0x180020858  mov     [r14], rdx
0x18002085b  add     rsp, 30h
0x18002085f  pop     r14
0x180020861  pop     rdi
0x180020862  pop     rsi
0x180020863  pop     rbp
0x180020864  pop     rbx
0x180020865  retn
0x180020866  mov     r9d, eax; char *
0x180020869  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180020870  mov     edx, 10Fh; void *
0x180020875  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18002087b  mov     rcx, rdi; unsigned __int64
0x18002087e  call    ?OutOfMemory@Abandonment@CFlat@@SAX_K@Z; CFlat::Abandonment::OutOfMemory(unsigned __int64)
```
