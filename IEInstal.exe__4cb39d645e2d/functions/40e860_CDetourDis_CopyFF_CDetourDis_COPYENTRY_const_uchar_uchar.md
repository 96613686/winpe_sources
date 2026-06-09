# CDetourDis::CopyFF(CDetourDis::COPYENTRY const *,uchar *,uchar *)

- ea: `0x40e860`
- end: `0x40e8d8`
- name: `?CopyFF@CDetourDis@@IAEPAEPBUCOPYENTRY@1@PAE1@Z`
- size: `120`
- prototype: `unsigned __int8 *__thiscall(CDetourDis *__hidden this, const struct CDetourDis::COPYENTRY *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x40e310`
- `0x40e860`

## pseudocode

```c
unsigned __int8 *__thiscall CDetourDis::CopyFF(
        CDetourDis *this,
        const struct CDetourDis::COPYENTRY *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4)
{
  unsigned __int8 *result; // eax
  unsigned __int8 v6; // cl
  unsigned __int8 *v7; // edx
  char v8; // cl
  char v9; // al
  unsigned __int8 *v10; // eax

  result = CDetourDis::CopyBytes(this, (const struct CDetourDis::COPYENTRY *)&dword_413160, a3, a4);
  v6 = a4[1];
  v7 = result;
  if ( v6 == 21 || v6 == 37 )
  {
    v9 = *((_BYTE *)this + 24);
    if ( v9 && v9 != 46 )
      goto LABEL_5;
    v10 = *(unsigned __int8 **)(a4 + 2);
    if ( CDetourDis::s_fLimitReferencesToModule )
    {
      if ( v10 < CDetourDis::s_pbModuleBeg || v10 >= CDetourDis::s_pbModuleEnd )
        goto LABEL_5;
    }
    **((_DWORD **)this + 7) = *(_DWORD *)v10;
    return v7;
  }
  else
  {
    v8 = v6 & 0x30;
    if ( v8 == 16 || v8 == 32 )
    {
LABEL_5:
      **((_DWORD **)this + 7) = -1;
      return v7;
    }
  }
  return result;
}

```

## disassembly

```asm
0x40e860  push    esi
0x40e861  push    edi
0x40e862  mov     edi, [esp+8+arg_8]
0x40e866  mov     esi, ecx
0x40e868  push    edi; unsigned __int8 *
0x40e869  push    [esp+0Ch+arg_4]; unsigned __int8 *
0x40e86d  push    offset dword_413160; struct CDetourDis::COPYENTRY *
0x40e872  call    ?CopyBytes@CDetourDis@@IAEPAEPBUCOPYENTRY@1@PAE1@Z; CDetourDis::CopyBytes(CDetourDis::COPYENTRY const *,uchar *,uchar *)
0x40e877  mov     cl, [edi+1]
0x40e87a  mov     edx, eax
0x40e87c  cmp     cl, 15h
0x40e87f  jz      short loc_40E8A3
0x40e881  cmp     cl, 25h ; '%'
0x40e884  jz      short loc_40E8A3
0x40e886  and     cl, 30h
0x40e889  cmp     cl, 10h
0x40e88c  jz      short loc_40E893
0x40e88e  cmp     cl, 20h ; ' '
0x40e891  jnz     short loc_40E8D3
0x40e893  mov     eax, [esi+1Ch]
0x40e896  pop     edi
0x40e897  pop     esi
0x40e898  mov     dword ptr [eax], 0FFFFFFFFh
0x40e89e  mov     eax, edx
0x40e8a0  retn    0Ch
0x40e8a3  mov     al, [esi+18h]
0x40e8a6  test    al, al
0x40e8a8  jz      short loc_40E8AE
0x40e8aa  cmp     al, 2Eh ; '.'
0x40e8ac  jnz     short loc_40E893
0x40e8ae  cmp     ds:?s_fLimitReferencesToModule@CDetourDis@@1HA, 0; int CDetourDis::s_fLimitReferencesToModule
0x40e8b5  mov     eax, [edi+2]
0x40e8b8  jz      short loc_40E8CA
0x40e8ba  cmp     eax, ds:?s_pbModuleBeg@CDetourDis@@1PAEA; uchar * CDetourDis::s_pbModuleBeg
0x40e8c0  jb      short loc_40E893
0x40e8c2  cmp     eax, ds:?s_pbModuleEnd@CDetourDis@@1PAEA; uchar * CDetourDis::s_pbModuleEnd
0x40e8c8  jnb     short loc_40E893
0x40e8ca  mov     ecx, [esi+1Ch]
0x40e8cd  mov     eax, [eax]
0x40e8cf  mov     [ecx], eax
0x40e8d1  mov     eax, edx
0x40e8d3  pop     edi
0x40e8d4  pop     esi
0x40e8d5  retn    0Ch
```
