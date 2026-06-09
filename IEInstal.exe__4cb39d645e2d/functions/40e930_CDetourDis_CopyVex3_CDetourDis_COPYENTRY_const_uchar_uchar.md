# CDetourDis::CopyVex3(CDetourDis::COPYENTRY const *,uchar *,uchar *)

- ea: `0x40e930`
- end: `0x40e987`
- name: `?CopyVex3@CDetourDis@@IAEPAEPBUCOPYENTRY@1@PAE1@Z`
- size: `87`
- prototype: `unsigned __int8 *__thiscall(CDetourDis *__hidden this, const struct CDetourDis::COPYENTRY *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x40e310`
- `0x40e930`
- `0x40e990`

## pseudocode

```c
unsigned __int8 *__thiscall CDetourDis::CopyVex3(
        CDetourDis *this,
        const struct CDetourDis::COPYENTRY *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4)
{
  if ( (a4[1] & 0xC0) != 0xC0 )
    return CDetourDis::CopyBytes(this, (const struct CDetourDis::COPYENTRY *)&dword_413180, a3, a4);
  *a3 = *a4;
  a3[1] = a4[1];
  a3[2] = a4[2];
  return CDetourDis::CopyVexCommon(this, a4[1] & 0x1F, a3 + 3, a4 + 3);
}

```

## disassembly

```asm
0x40e930  mov     edx, [esp+arg_8]
0x40e934  push    esi
0x40e935  mov     esi, ecx
0x40e937  mov     al, [edx+1]
0x40e93a  and     al, 0C0h
0x40e93c  cmp     al, 0C0h
0x40e93e  jz      short loc_40E953
0x40e940  push    edx; unsigned __int8 *
0x40e941  push    [esp+8+arg_4]; unsigned __int8 *
0x40e945  push    offset dword_413180; struct CDetourDis::COPYENTRY *
0x40e94a  call    ?CopyBytes@CDetourDis@@IAEPAEPBUCOPYENTRY@1@PAE1@Z; CDetourDis::CopyBytes(CDetourDis::COPYENTRY const *,uchar *,uchar *)
0x40e94f  pop     esi
0x40e950  retn    0Ch
0x40e953  mov     ecx, [esp+4+arg_4]
0x40e957  movzx   eax, byte ptr [edx]
0x40e95a  mov     [ecx], al
0x40e95c  movzx   eax, byte ptr [edx+1]
0x40e960  mov     [ecx+1], al
0x40e963  movzx   eax, byte ptr [edx+2]
0x40e967  mov     [ecx+2], al
0x40e96a  lea     eax, [edx+3]
0x40e96d  push    eax; unsigned __int8 *
0x40e96e  lea     eax, [ecx+3]
0x40e971  mov     ecx, esi; this
0x40e973  push    eax; unsigned __int8 *
0x40e974  movzx   eax, byte ptr [edx+1]
0x40e978  and     al, 1Fh
0x40e97a  movzx   eax, al
0x40e97d  push    eax; char
0x40e97e  call    ?CopyVexCommon@CDetourDis@@IAEPAEEPAE0@Z; CDetourDis::CopyVexCommon(uchar,uchar *,uchar *)
0x40e983  pop     esi
0x40e984  retn    0Ch
```
