# CItemIDFactory<DSPROFILEITEM,999534523>::GetPropertyFromIDList(_ITEMIDLIST_RELATIVE const *,_tagpropertykey const &,tagPROPVARIANT *)

- ea: `0x180002720`
- end: `0x18000279b`
- name: `?GetPropertyFromIDList@?$CItemIDFactory@UDSPROFILEITEM@@$0DLJDKPLL@@@SAJPEFBU_ITEMIDLIST_RELATIVE@@AEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z`
- size: `123`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001b54`
- `0x180002b48`
- `0x180003950`

## callees

- `0x180002720`

## import_xrefs

- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x180002784`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x180002784`

## pseudocode

```c
HRESULT __fastcall CItemIDFactory<DSPROFILEITEM,999534523>::GetPropertyFromIDList(
        unsigned __int16 *a1,
        const PROPERTYKEY *a2,
        PROPVARIANT *a3)
{
  HRESULT result; // eax
  unsigned __int64 v6; // rcx
  __int64 v7; // r8

  *(_OWORD *)&a3->vt = 0;
  a3->bstrblobVal.pData = 0;
  result = -2147024809;
  if ( a1 )
  {
    v6 = *a1;
    if ( (unsigned int)v6 >= 0x12 && *(_DWORD *)(a1 + 3) == 999534523 )
    {
      v7 = a1[5];
      if ( v6 >= v7 + 18 )
      {
        if ( (_WORD)v7 )
        {
          if ( a1 != (unsigned __int16 *)-18LL )
          {
            result = PSGetPropertyFromPropertyStorage((PCUSERIALIZEDPROPSTORAGE)(a1 + 9), v7, a2, a3);
            if ( result >= 0 && !a3->vt )
              return -2147023288;
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002720  push    rbx
0x180002722  sub     rsp, 20h
0x180002726  xor     eax, eax
0x180002728  xorps   xmm0, xmm0
0x18000272b  mov     rbx, r8
0x18000272e  mov     r10, rdx
0x180002731  mov     r9, rcx
0x180002734  movups  xmmword ptr [r8], xmm0
0x180002738  mov     [r8+10h], rax
0x18000273c  mov     eax, 80070057h
0x180002741  test    rcx, rcx
0x180002744  jz      short loc_180002766
0x180002746  movzx   ecx, word ptr [rcx]
0x180002749  cmp     ecx, 12h
0x18000274c  jb      short loc_180002766
0x18000274e  cmp     dword ptr [r9+6], 3B93AFBBh
0x180002756  jnz     short loc_180002766
0x180002758  movzx   r8d, word ptr [r9+0Ah]
0x18000275d  lea     rdx, [r8+12h]
0x180002761  cmp     rcx, rdx
0x180002764  jnb     short loc_18000276C
0x180002766  add     rsp, 20h
0x18000276a  pop     rbx
0x18000276b  retn
0x18000276c  test    r8w, r8w
0x180002770  jz      short loc_180002766
0x180002772  lea     rcx, [r9+12h]; psps
0x180002776  test    rcx, rcx
0x180002779  jz      short loc_180002766
0x18000277b  mov     edx, r8d; cb
0x18000277e  mov     r9, rbx; ppropvar
0x180002781  mov     r8, r10; rpkey
0x180002784  call    cs:__imp_PSGetPropertyFromPropertyStorage
0x18000278a  test    eax, eax
0x18000278c  js      short loc_180002766
0x18000278e  cmp     word ptr [rbx], 0
0x180002792  jnz     short loc_180002766
0x180002794  mov     eax, 80070648h
0x180002799  jmp     short loc_180002766
```
