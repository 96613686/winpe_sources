# Rdp::Utils::Props::IPropertyStore_GetUInt32(IPropertyStore *,_tagpropertykey const &,uint *)

- ea: `0x180033a34`
- end: `0x180033abf`
- name: `?IPropertyStore_GetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAI@Z`
- size: `139`
- prototype: `__int64 __fastcall(Rdp::Utils::Props *__hidden this, struct IPropertyStore *, const struct _tagpropertykey *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180034dd0`

## callees

- `0x18000b014`
- `0x180033a34`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180033aa5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180033aa5`

## string_xrefs

- `0x180033a76`: `onecoreuap\termsrv\rdp_bin\win\common/inc/PropsHelpers.h`

## pseudocode

```c
__int64 __fastcall Rdp::Utils::Props::IPropertyStore_GetUInt32(
        Rdp::Utils::Props *this,
        struct IPropertyStore *a2,
        const struct _tagpropertykey *a3,
        unsigned int *a4)
{
  int v5; // eax
  unsigned int v6; // ebx
  PROPVARIANT pvar[2]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v9; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  a3->fmtid.Data1 = 0;
  *(_OWORD *)pvar = 0;
  v9 = 0;
  v5 = (*(__int64 (__fastcall **)(Rdp::Utils::Props *, struct IPropertyStore *, PROPVARIANT *, unsigned int *))(*(_QWORD *)this + 40LL))(
         this,
         a2,
         pvar,
         a4);
  v6 = v5;
  if ( v5 >= 0 )
  {
    if ( LOWORD(pvar[0]) == 19 )
    {
      a3->fmtid.Data1 = (unsigned int)pvar[1];
      v6 = 0;
    }
    else
    {
      v6 = -2147467259;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/PropsHelpers.h",
      (const char *)(unsigned int)v5,
      (int)pvar[0]);
  }
  PropVariantClear(pvar);
  return v6;
}

```

## disassembly

```asm
0x180033a34  mov     [rsp+arg_0], rbx
0x180033a39  push    rdi
0x180033a3a  sub     rsp, 40h
0x180033a3e  mov     rdi, r8
0x180033a41  mov     dword ptr [r8], 0
0x180033a48  xorps   xmm0, xmm0
0x180033a4b  xor     eax, eax
0x180033a4d  movups  xmmword ptr [rsp+48h+pvar], xmm0; int
0x180033a52  mov     [rsp+48h+var_18], rax
0x180033a57  mov     rax, [rcx]
0x180033a5a  lea     r8, [rsp+48h+pvar]
0x180033a5f  mov     rax, [rax+28h]
0x180033a63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a68  mov     ebx, eax
0x180033a6a  test    eax, eax
0x180033a6c  jns     short loc_180033A89
0x180033a6e  mov     rcx, [rsp+48h]; this
0x180033a73  mov     r9d, eax; char *
0x180033a76  lea     r8, aOnecoreuapTerm_13; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x180033a7d  mov     edx, 47h ; 'G'; void *
0x180033a82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033a87  jmp     short loc_180033AA0
0x180033a89  cmp     word ptr [rsp+48h+pvar], 13h
0x180033a8f  jz      short loc_180033A98
0x180033a91  mov     ebx, 80004005h
0x180033a96  jmp     short loc_180033AA0
0x180033a98  mov     eax, dword ptr [rsp+48h+pvar+8]
0x180033a9c  mov     [rdi], eax
0x180033a9e  xor     ebx, ebx
0x180033aa0  lea     rcx, [rsp+48h+pvar]; pvar
0x180033aa5  call    cs:__imp_PropVariantClear
0x180033aac  nop     dword ptr [rax+rax+00h]
0x180033ab1  mov     eax, ebx
0x180033ab3  mov     rbx, [rsp+48h+arg_0]
0x180033ab8  add     rsp, 40h
0x180033abc  pop     rdi
0x180033abd  retn
```
