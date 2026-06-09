# Rdp::Utils::Props::IPropertyStore_SetCLSID(IPropertyStore *,_tagpropertykey const &,_GUID const &)

- ea: `0x1800177fc`
- end: `0x18001787f`
- name: `?IPropertyStore_SetCLSID@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@AEBU_GUID@@@Z`
- size: `131`
- prototype: `int(Rdp::Utils::Props *__hidden this, struct IPropertyStore *, const struct _tagpropertykey *, const struct _GUID *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001b1a0`
- `0x18002476c`

## callees

- `0x18000b014`
- `0x1800177fc`
- `0x18003f010`

## import_xrefs

- `PROPSYS!InitPropVariantFromCLSID` at `0x180017827`
- `PROPSYS!InitPropVariantFromCLSID` at `0x180017827`

## string_xrefs

- `0x180017841`: `onecoreuap\termsrv\rdp_bin\win\common/inc/PropsHelpers.h`

## pseudocode

```c
__int64 __fastcall Rdp::Utils::Props::IPropertyStore_SetCLSID(
        Rdp::Utils::Props *this,
        struct IPropertyStore *a2,
        const struct _tagpropertykey *a3,
        const struct _GUID *a4)
{
  HRESULT inited; // eax
  unsigned int v7; // ebx
  int v9[4]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v10; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *(_OWORD *)v9 = 0;
  v10 = 0;
  inited = InitPropVariantFromCLSID(&a3->fmtid, (PROPVARIANT *)v9);
  v7 = inited;
  if ( inited >= 0 )
    return (*(__int64 (__fastcall **)(Rdp::Utils::Props *, struct IPropertyStore *, int *))(*(_QWORD *)this + 48LL))(
             this,
             a2,
             v9);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x189,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/PropsHelpers.h",
    (const char *)(unsigned int)inited,
    v9[0]);
  return v7;
}

```

## disassembly

```asm
0x1800177fc  mov     r11, rsp
0x1800177ff  mov     [r11+8], rbx
0x180017803  mov     [r11+10h], rsi
0x180017807  push    rdi
0x180017808  sub     rsp, 40h
0x18001780c  mov     rsi, rdx
0x18001780f  mov     rdi, rcx
0x180017812  xorps   xmm0, xmm0
0x180017815  xor     eax, eax
0x180017817  movups  xmmword ptr [rsp+48h+var_28], xmm0; int
0x18001781c  mov     [r11-18h], rax
0x180017820  lea     rdx, [r11-28h]; ppropvar
0x180017824  mov     rcx, r8; clsid
0x180017827  call    cs:__imp_InitPropVariantFromCLSID
0x18001782e  nop     dword ptr [rax+rax+00h]
0x180017833  mov     ebx, eax
0x180017835  test    eax, eax
0x180017837  jns     short loc_180017856
0x180017839  mov     rcx, [rsp+48h]; this
0x18001783e  mov     r9d, eax; char *
0x180017841  lea     r8, aOnecoreuapTerm_13; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x180017848  mov     edx, 189h; void *
0x18001784d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017852  mov     eax, ebx
0x180017854  jmp     short loc_18001786E
0x180017856  mov     rax, [rdi]
0x180017859  lea     r8, [rsp+48h+var_28]
0x18001785e  mov     rdx, rsi
0x180017861  mov     rcx, rdi
0x180017864  mov     rax, [rax+30h]
0x180017868  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001786d  nop
0x18001786e  mov     rbx, [rsp+48h+arg_0]
0x180017873  mov     rsi, [rsp+48h+arg_8]
0x180017878  add     rsp, 40h
0x18001787c  pop     rdi
0x18001787d  retn
```
