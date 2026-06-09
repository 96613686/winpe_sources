# CItemIDFactory<_ITEMID,1450709556>::GetPropertyFromIDList(_ITEMIDLIST const *,_tagpropertykey const &,tagPROPVARIANT *)

- ea: `0x180005ab8`
- end: `0x180005b23`
- name: `?GetPropertyFromIDList@?$CItemIDFactory@U_ITEMID@@$0FGHIBCDE@@@SAJPEFBU_ITEMIDLIST@@AEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, PROPVARIANT *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800048e0`
- `0x180006890`
- `0x1800094a0`

## callees

- `0x180005ab8`
- `0x180005b2c`

## import_xrefs

- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x180005afc`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x180005afc`

## pseudocode

```c
__int64 __fastcall CItemIDFactory<_ITEMID,1450709556>::GetPropertyFromIDList(
        unsigned __int16 *a1,
        __int64 a2,
        PROPVARIANT *a3)
{
  unsigned __int16 *v4; // rax
  const PROPERTYKEY *v5; // r8
  HRESULT v6; // r9d

  *(_OWORD *)&a3->vt = 0;
  a3->bstrblobVal.pData = 0;
  v4 = CItemIDFactory<_ITEMID,1450709556>::_IsValid(a1);
  if ( v4 )
  {
    if ( v4[5] )
    {
      if ( v4 != (unsigned __int16 *)-26LL )
      {
        v6 = PSGetPropertyFromPropertyStorage((PCUSERIALIZEDPROPSTORAGE)(v4 + 13), v4[5], v5, a3);
        if ( v6 >= 0 && !a3->vt )
          return (unsigned int)-2147023288;
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180005ab8  mov     [rsp+arg_0], rbx
0x180005abd  push    rdi
0x180005abe  sub     rsp, 20h
0x180005ac2  mov     rbx, r8
0x180005ac5  xor     eax, eax
0x180005ac7  xorps   xmm0, xmm0
0x180005aca  mov     r8, rdx
0x180005acd  mov     r9d, 80070057h
0x180005ad3  movups  xmmword ptr [rbx], xmm0
0x180005ad6  mov     [rbx+10h], rax
0x180005ada  call    ?_IsValid@?$CItemIDFactory@U_ITEMID@@$0FGHIBCDE@@@CAPEFBUCHILDITEMID@1@PEFBU_ITEMIDLIST@@@Z; CItemIDFactory<_ITEMID,1450709556>::_IsValid(_ITEMIDLIST const *)
0x180005adf  xor     edi, edi
0x180005ae1  test    rax, rax
0x180005ae4  jz      short loc_180005B15
0x180005ae6  cmp     [rax+0Ah], di
0x180005aea  jz      short loc_180005B15
0x180005aec  lea     rcx, [rax+1Ah]; psps
0x180005af0  test    rcx, rcx
0x180005af3  jz      short loc_180005B15
0x180005af5  movzx   edx, word ptr [rax+0Ah]; cb
0x180005af9  mov     r9, rbx; ppropvar
0x180005afc  call    cs:__imp_PSGetPropertyFromPropertyStorage
0x180005b02  mov     r9d, eax
0x180005b05  test    eax, eax
0x180005b07  js      short loc_180005B15
0x180005b09  cmp     [rbx], di
0x180005b0c  mov     eax, 80070648h
0x180005b11  cmovz   r9d, eax
0x180005b15  mov     rbx, [rsp+28h+arg_0]
0x180005b1a  mov     eax, r9d
0x180005b1d  add     rsp, 20h
0x180005b21  pop     rdi
0x180005b22  retn
```
