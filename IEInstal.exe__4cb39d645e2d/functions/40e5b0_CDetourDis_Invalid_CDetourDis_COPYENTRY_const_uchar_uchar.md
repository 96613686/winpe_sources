# CDetourDis::Invalid(CDetourDis::COPYENTRY const *,uchar *,uchar *)

- ea: `0x40e5b0`
- end: `0x40e5b8`
- name: `?Invalid@CDetourDis@@IAEPAEPBUCOPYENTRY@1@PAE1@Z`
- size: `8`
- prototype: `unsigned __int8 *__thiscall(CDetourDis *__hidden this, const struct CDetourDis::COPYENTRY *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
unsigned __int8 *__thiscall CDetourDis::Invalid(
        CDetourDis *this,
        const struct CDetourDis::COPYENTRY *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4)
{
  return a4 + 1;
}

```

## disassembly

```asm
0x40e5b0  mov     eax, [esp+arg_8]
0x40e5b4  inc     eax
0x40e5b5  retn    0Ch
```
