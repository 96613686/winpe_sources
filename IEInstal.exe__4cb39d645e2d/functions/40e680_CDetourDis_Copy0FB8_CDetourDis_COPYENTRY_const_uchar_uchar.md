# CDetourDis::Copy0FB8(CDetourDis::COPYENTRY const *,uchar *,uchar *)

- ea: `0x40e680`
- end: `0x40e6b2`
- name: `?Copy0FB8@CDetourDis@@IAEPAEPBUCOPYENTRY@1@PAE1@Z`
- size: `50`
- prototype: `unsigned __int8 *__thiscall(CDetourDis *__hidden this, const struct CDetourDis::COPYENTRY *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x40d1d0`

## pseudocode

```c
unsigned __int8 *__thiscall CDetourDis::Copy0FB8(
        CDetourDis *this,
        const struct CDetourDis::COPYENTRY *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4)
{
  int *v4; // esi

  v4 = &dword_413130;
  if ( !*((_DWORD *)this + 5) )
    v4 = &dword_413138;
  return (unsigned __int8 *)((int (__thiscall *)(CDetourDis *, int *, unsigned __int8 *, unsigned __int8 *))v4[1])(
                              this,
                              v4,
                              a3,
                              a4);
}

```

## disassembly

```asm
0x40e680  push    esi
0x40e681  push    edi
0x40e682  push    [esp+8+arg_8]
0x40e686  mov     edi, ecx
0x40e688  mov     eax, offset dword_413138
0x40e68d  push    [esp+0Ch+arg_4]
0x40e691  mov     esi, offset dword_413130
0x40e696  cmp     dword ptr [edi+14h], 0
0x40e69a  cmovz   esi, eax
0x40e69d  push    esi
0x40e69e  mov     esi, [esi+4]
0x40e6a1  mov     ecx, esi
0x40e6a3  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x40e6a9  mov     ecx, edi
0x40e6ab  call    esi
0x40e6ad  pop     edi
0x40e6ae  pop     esi
0x40e6af  retn    0Ch
```
