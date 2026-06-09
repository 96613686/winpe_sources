# CDetourDis::Copy0F00(CDetourDis::COPYENTRY const *,uchar *,uchar *)

- ea: `0x40e600`
- end: `0x40e636`
- name: `?Copy0F00@CDetourDis@@IAEPAEPBUCOPYENTRY@1@PAE1@Z`
- size: `54`
- prototype: `unsigned __int8 *__thiscall(CDetourDis *__hidden this, const struct CDetourDis::COPYENTRY *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x40d1d0`

## pseudocode

```c
unsigned __int8 *__thiscall CDetourDis::Copy0F00(
        CDetourDis *this,
        const struct CDetourDis::COPYENTRY *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4)
{
  int *v4; // esi

  v4 = &dword_413128;
  if ( (a4[1] & 0x38) != 0x30 )
    v4 = &dword_413120;
  return (unsigned __int8 *)((int (__thiscall *)(CDetourDis *, int *, unsigned __int8 *, unsigned __int8 *))v4[1])(
                              this,
                              v4,
                              a3,
                              a4);
}

```

## disassembly

```asm
0x40e600  mov     edx, [esp+arg_8]
0x40e604  push    esi
0x40e605  push    edi
0x40e606  mov     edi, ecx
0x40e608  mov     esi, offset dword_413128
0x40e60d  mov     al, [edx+1]
0x40e610  mov     ecx, offset dword_413120
0x40e615  and     al, 38h
0x40e617  cmp     al, 30h ; '0'
0x40e619  push    edx
0x40e61a  push    [esp+0Ch+arg_4]
0x40e61e  cmovnz  esi, ecx
0x40e621  push    esi
0x40e622  mov     esi, [esi+4]
0x40e625  mov     ecx, esi
0x40e627  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x40e62d  mov     ecx, edi
0x40e62f  call    esi
0x40e631  pop     edi
0x40e632  pop     esi
0x40e633  retn    0Ch
```
