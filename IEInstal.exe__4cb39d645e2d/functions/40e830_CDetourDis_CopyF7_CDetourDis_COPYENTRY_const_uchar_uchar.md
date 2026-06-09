# CDetourDis::CopyF7(CDetourDis::COPYENTRY const *,uchar *,uchar *)

- ea: `0x40e830`
- end: `0x40e853`
- name: `?CopyF7@CDetourDis@@IAEPAEPBUCOPYENTRY@1@PAE1@Z`
- size: `35`
- prototype: `unsigned __int8 *__thiscall(CDetourDis *__hidden this, const struct CDetourDis::COPYENTRY *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x40e310`

## pseudocode

```c
unsigned __int8 *__thiscall CDetourDis::CopyF7(
        CDetourDis *this,
        const struct CDetourDis::COPYENTRY *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4)
{
  int *v4; // eax

  v4 = &dword_413158;
  if ( (a4[1] & 0x38) == 0 )
    v4 = &dword_413150;
  return CDetourDis::CopyBytes(this, (const struct CDetourDis::COPYENTRY *)v4, a3, a4);
}

```

## disassembly

```asm
0x40e830  mov     eax, [esp+arg_8]
0x40e834  mov     edx, offset dword_413150
0x40e839  push    eax; unsigned __int8 *
0x40e83a  push    [esp+4+arg_4]; unsigned __int8 *
0x40e83e  test    byte ptr [eax+1], 38h
0x40e842  mov     eax, offset dword_413158
0x40e847  cmovz   eax, edx
0x40e84a  push    eax; struct CDetourDis::COPYENTRY *
0x40e84b  call    ?CopyBytes@CDetourDis@@IAEPAEPBUCOPYENTRY@1@PAE1@Z; CDetourDis::CopyBytes(CDetourDis::COPYENTRY const *,uchar *,uchar *)
0x40e850  retn    0Ch
```
