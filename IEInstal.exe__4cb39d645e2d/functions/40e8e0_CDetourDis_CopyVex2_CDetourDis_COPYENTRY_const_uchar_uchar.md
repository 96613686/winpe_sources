# CDetourDis::CopyVex2(CDetourDis::COPYENTRY const *,uchar *,uchar *)

- ea: `0x40e8e0`
- end: `0x40e928`
- name: `?CopyVex2@CDetourDis@@IAEPAEPBUCOPYENTRY@1@PAE1@Z`
- size: `72`
- prototype: `unsigned __int8 *__thiscall(CDetourDis *__hidden this, const struct CDetourDis::COPYENTRY *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x40e310`
- `0x40e8e0`
- `0x40e990`

## pseudocode

```c
unsigned __int8 *__thiscall CDetourDis::CopyVex2(
        CDetourDis *this,
        const struct CDetourDis::COPYENTRY *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4)
{
  if ( (a4[1] & 0xC0) != 0xC0 )
    return CDetourDis::CopyBytes(this, (const struct CDetourDis::COPYENTRY *)&dword_413188, a3, a4);
  *a3 = *a4;
  a3[1] = a4[1];
  return CDetourDis::CopyVexCommon(this, 1, a3 + 2, a4 + 2);
}

```

## disassembly

```asm
0x40e8e0  mov     edx, [esp+arg_8]
0x40e8e4  push    esi
0x40e8e5  mov     esi, ecx
0x40e8e7  mov     al, [edx+1]
0x40e8ea  and     al, 0C0h
0x40e8ec  cmp     al, 0C0h
0x40e8ee  jz      short loc_40E903
0x40e8f0  push    edx; unsigned __int8 *
0x40e8f1  push    [esp+8+arg_4]; unsigned __int8 *
0x40e8f5  push    offset dword_413188; struct CDetourDis::COPYENTRY *
0x40e8fa  call    ?CopyBytes@CDetourDis@@IAEPAEPBUCOPYENTRY@1@PAE1@Z; CDetourDis::CopyBytes(CDetourDis::COPYENTRY const *,uchar *,uchar *)
0x40e8ff  pop     esi
0x40e900  retn    0Ch
0x40e903  mov     ecx, [esp+4+arg_4]
0x40e907  movzx   eax, byte ptr [edx]
0x40e90a  mov     [ecx], al
0x40e90c  movzx   eax, byte ptr [edx+1]
0x40e910  mov     [ecx+1], al
0x40e913  lea     eax, [edx+2]
0x40e916  push    eax; unsigned __int8 *
0x40e917  lea     eax, [ecx+2]
0x40e91a  mov     ecx, esi; this
0x40e91c  push    eax; unsigned __int8 *
0x40e91d  push    1; char
0x40e91f  call    ?CopyVexCommon@CDetourDis@@IAEPAEEPAE0@Z; CDetourDis::CopyVexCommon(uchar,uchar *,uchar *)
0x40e924  pop     esi
0x40e925  retn    0Ch
```
