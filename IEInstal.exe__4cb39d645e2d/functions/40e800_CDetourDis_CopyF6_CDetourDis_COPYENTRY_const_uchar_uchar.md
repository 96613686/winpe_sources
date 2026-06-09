# CDetourDis::CopyF6(CDetourDis::COPYENTRY const *,uchar *,uchar *)

- ea: `0x40e800`
- end: `0x40e823`
- name: `?CopyF6@CDetourDis@@IAEPAEPBUCOPYENTRY@1@PAE1@Z`
- size: `35`
- prototype: `unsigned __int8 *__thiscall(CDetourDis *__hidden this, const struct CDetourDis::COPYENTRY *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x40e310`

## pseudocode

```c
unsigned __int8 *__thiscall CDetourDis::CopyF6(
        CDetourDis *this,
        const struct CDetourDis::COPYENTRY *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4)
{
  int *v4; // eax

  v4 = &dword_413148;
  if ( (a4[1] & 0x38) == 0 )
    v4 = &dword_413140;
  return CDetourDis::CopyBytes(this, (const struct CDetourDis::COPYENTRY *)v4, a3, a4);
}

```

## disassembly

```asm
0x40e800  mov     eax, [esp+arg_8]
0x40e804  mov     edx, offset dword_413140
0x40e809  push    eax; unsigned __int8 *
0x40e80a  push    [esp+4+arg_4]; unsigned __int8 *
0x40e80e  test    byte ptr [eax+1], 38h
0x40e812  mov     eax, offset dword_413148
0x40e817  cmovz   eax, edx
0x40e81a  push    eax; struct CDetourDis::COPYENTRY *
0x40e81b  call    ?CopyBytes@CDetourDis@@IAEPAEPBUCOPYENTRY@1@PAE1@Z; CDetourDis::CopyBytes(CDetourDis::COPYENTRY const *,uchar *,uchar *)
0x40e820  retn    0Ch
```
