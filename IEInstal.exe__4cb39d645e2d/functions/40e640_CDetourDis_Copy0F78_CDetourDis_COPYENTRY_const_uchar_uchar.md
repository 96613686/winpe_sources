# CDetourDis::Copy0F78(CDetourDis::COPYENTRY const *,uchar *,uchar *)

- ea: `0x40e640`
- end: `0x40e676`
- name: `?Copy0F78@CDetourDis@@IAEPAEPBUCOPYENTRY@1@PAE1@Z`
- size: `54`
- prototype: `unsigned __int8 *__thiscall(CDetourDis *__hidden this, const struct CDetourDis::COPYENTRY *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x40d1d0`
- `0x40e640`

## pseudocode

```c
unsigned __int8 *__thiscall CDetourDis::Copy0F78(
        CDetourDis *this,
        const struct CDetourDis::COPYENTRY *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4)
{
  int *v4; // esi

  if ( *((_DWORD *)this + 4) || (v4 = &dword_413110, *(_DWORD *)this) )
    v4 = &dword_413118;
  return (unsigned __int8 *)((int (__thiscall *)(CDetourDis *, int *, unsigned __int8 *, unsigned __int8 *))v4[1])(
                              this,
                              v4,
                              a3,
                              a4);
}

```

## disassembly

```asm
0x40e640  push    esi
0x40e641  push    edi
0x40e642  mov     edi, ecx
0x40e644  cmp     dword ptr [edi+10h], 0
0x40e648  jnz     short loc_40E654
0x40e64a  cmp     dword ptr [edi], 0
0x40e64d  mov     esi, offset dword_413110
0x40e652  jz      short loc_40E659
0x40e654  mov     esi, offset dword_413118
0x40e659  push    [esp+8+arg_8]
0x40e65d  push    [esp+0Ch+arg_4]
0x40e661  push    esi
0x40e662  mov     esi, [esi+4]
0x40e665  mov     ecx, esi
0x40e667  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x40e66d  mov     ecx, edi
0x40e66f  call    esi
0x40e671  pop     edi
0x40e672  pop     esi
0x40e673  retn    0Ch
```
