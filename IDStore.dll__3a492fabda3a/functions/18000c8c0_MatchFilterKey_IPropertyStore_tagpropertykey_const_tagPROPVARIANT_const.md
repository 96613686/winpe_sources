# MatchFilterKey(IPropertyStore *,_tagpropertykey const *,tagPROPVARIANT const *)

- ea: `0x18000c8c0`
- end: `0x18000c9ef`
- name: `?MatchFilterKey@@YAEPEAUIPropertyStore@@PEBU_tagpropertykey@@PEBUtagPROPVARIANT@@@Z`
- size: `303`
- prototype: `unsigned __int8 __fastcall(struct IPropertyStore *, const struct _tagpropertykey *, const PROPVARIANT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012b10`

## callees

- `0x18000c8c0`
- `0x18000c9f8`
- `0x18000ca30`
- `0x1800144f4`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000c941`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000c941`
- `PROPSYS!PropVariantCompareEx` at `0x18000c930`
- `PROPSYS!PropVariantCompareEx` at `0x18000c930`

## pseudocode

```c
unsigned __int8 __fastcall MatchFilterKey(
        struct IPropertyStore *a1,
        const struct _tagpropertykey *a2,
        const PROPVARIANT *a3)
{
  struct IPropertyStoreVtbl *lpVtbl; // rax
  unsigned __int8 v7; // si
  int v8; // eax
  __int64 i; // rbx
  const unsigned __int16 *v10; // rdx
  struct tagPROPVARIANT propvar2; // [rsp+30h] [rbp-28h] BYREF

  if ( !a2 || !a3 )
    return 1;
  lpVtbl = a1->lpVtbl;
  v7 = 0;
  memset(&propvar2, 0, sizeof(propvar2));
  v8 = ((__int64 (__fastcall *)(struct IPropertyStore *, const struct _tagpropertykey *, struct tagPROPVARIANT *))lpVtbl->GetValue)(
         a1,
         a2,
         &propvar2);
  if ( v8 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 120, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids, a2->pid, v8);
    }
  }
  else if ( (unsigned int)operator==(a2) )
  {
    if ( *(_WORD *)a3 == 4127 )
    {
      for ( i = 0; (unsigned int)i < *((_DWORD *)a3 + 2); i = (unsigned int)(i + 1) )
      {
        v10 = *(const unsigned __int16 **)(*((_QWORD *)a3 + 2) + 8 * i);
        if ( !v10 || !ContainsKeyword(&propvar2, v10) )
          goto LABEL_7;
      }
      v7 = 1;
    }
    else if ( *(_WORD *)a3 == 31 )
    {
      v7 = ContainsKeyword(&propvar2, *((const unsigned __int16 **)a3 + 1));
    }
  }
  else
  {
    v7 = PropVariantCompareEx(a3, (const PROPVARIANT *const)&propvar2, PVCU_DEFAULT, 8) == 0;
  }
LABEL_7:
  PropVariantClear((PROPVARIANT *)&propvar2);
  return v7;
}

```

## disassembly

```asm
0x18000c8c0  mov     [rsp+arg_8], rbx
0x18000c8c5  push    rdi
0x18000c8c6  sub     rsp, 50h
0x18000c8ca  mov     rdi, r8
0x18000c8cd  mov     rbx, rdx
0x18000c8d0  test    rdx, rdx
0x18000c8d3  jnz     short loc_18000C8E2
0x18000c8d5  mov     al, 1
0x18000c8d7  mov     rbx, [rsp+58h+arg_8]
0x18000c8dc  add     rsp, 50h
0x18000c8e0  pop     rdi
0x18000c8e1  retn
0x18000c8e2  test    rdi, rdi
0x18000c8e5  jz      short loc_18000C8D5
0x18000c8e7  xor     eax, eax
0x18000c8e9  mov     [rsp+58h+arg_0], rsi
0x18000c8ee  mov     [rsp+58h+var_18], rax
0x18000c8f3  lea     r8, [rsp+58h+propvar2]
0x18000c8f8  mov     rax, [rcx]
0x18000c8fb  xorps   xmm0, xmm0
0x18000c8fe  xor     sil, sil
0x18000c901  movups  xmmword ptr [rsp+58h+propvar2], xmm0
0x18000c906  mov     rax, [rax+28h]
0x18000c90a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c90f  test    eax, eax
0x18000c911  js      short loc_18000C981
0x18000c913  mov     rcx, rbx
0x18000c916  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x18000c91b  test    eax, eax
0x18000c91d  jnz     short loc_18000C95B
0x18000c91f  mov     r9d, 8; flags
0x18000c925  lea     rdx, [rsp+58h+propvar2]; propvar2
0x18000c92a  xor     r8d, r8d; unit
0x18000c92d  mov     rcx, rdi; propvar1
0x18000c930  call    cs:__imp_PropVariantCompareEx
0x18000c936  test    eax, eax
0x18000c938  setz    sil
0x18000c93c  lea     rcx, [rsp+58h+propvar2]; pvar
0x18000c941  call    cs:__imp_PropVariantClear
0x18000c947  mov     rbx, [rsp+58h+arg_8]
0x18000c94c  movzx   eax, sil
0x18000c950  mov     rsi, [rsp+58h+arg_0]
0x18000c955  add     rsp, 50h
0x18000c959  pop     rdi
0x18000c95a  retn
0x18000c95b  movzx   eax, word ptr [rdi]
0x18000c95e  mov     ecx, 101Fh
0x18000c963  cmp     ax, cx
0x18000c966  jz      short loc_18000C9B9
0x18000c968  cmp     ax, 1Fh
0x18000c96c  jnz     short loc_18000C93C
0x18000c96e  mov     rdx, [rdi+8]; unsigned __int16 *
0x18000c972  lea     rcx, [rsp+58h+propvar2]; struct tagPROPVARIANT *
0x18000c977  call    ?ContainsKeyword@@YAEPEBUtagPROPVARIANT@@PEBG@Z; ContainsKeyword(tagPROPVARIANT const *,ushort const *)
0x18000c97c  movzx   esi, al
0x18000c97f  jmp     short loc_18000C93C
0x18000c981  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c988  lea     rdx, WPP_GLOBAL_Control
0x18000c98f  cmp     rcx, rdx
0x18000c992  jz      short loc_18000C93C
0x18000c994  test    byte ptr [rcx+1Ch], 4
0x18000c998  jz      short loc_18000C93C
0x18000c99a  mov     r9d, [rbx+10h]
0x18000c99e  lea     r8, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids
0x18000c9a5  mov     rcx, [rcx+10h]
0x18000c9a9  mov     edx, 78h ; 'x'
0x18000c9ae  mov     [rsp+58h+var_38], eax
0x18000c9b2  call    WPP_SF_DD
0x18000c9b7  jmp     short loc_18000C93C
0x18000c9b9  xor     ebx, ebx
0x18000c9bb  cmp     ebx, [rdi+8]
0x18000c9be  jnb     short loc_18000C9E7
0x18000c9c0  mov     rax, [rdi+10h]
0x18000c9c4  mov     rdx, [rax+rbx*8]; unsigned __int16 *
0x18000c9c8  test    rdx, rdx
0x18000c9cb  jz      loc_18000C93C
0x18000c9d1  lea     rcx, [rsp+58h+propvar2]; struct tagPROPVARIANT *
0x18000c9d6  call    ?ContainsKeyword@@YAEPEBUtagPROPVARIANT@@PEBG@Z; ContainsKeyword(tagPROPVARIANT const *,ushort const *)
0x18000c9db  test    al, al
0x18000c9dd  jz      loc_18000C93C
0x18000c9e3  inc     ebx
0x18000c9e5  jmp     short loc_18000C9BB
0x18000c9e7  mov     sil, 1
0x18000c9ea  jmp     loc_18000C93C
```
