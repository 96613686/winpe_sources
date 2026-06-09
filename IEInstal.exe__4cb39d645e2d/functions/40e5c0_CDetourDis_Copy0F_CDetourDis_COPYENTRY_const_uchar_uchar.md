# CDetourDis::Copy0F(CDetourDis::COPYENTRY const *,uchar *,uchar *)

- ea: `0x40e5c0`
- end: `0x40e5f7`
- name: `?Copy0F@CDetourDis@@IAEPAEPBUCOPYENTRY@1@PAE1@Z`
- size: `55`
- prototype: `unsigned __int8 *__thiscall(CDetourDis *__hidden this, const struct CDetourDis::COPYENTRY *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x40d1d0`

## pseudocode

```c
unsigned __int8 *__thiscall CDetourDis::Copy0F(
        CDetourDis *this,
        const struct CDetourDis::COPYENTRY *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4)
{
  const struct CDetourDis::COPYENTRY *const *v5; // [esp-Ch] [ebp-18h]

  *a3 = *a4;
  v5 = &CDetourDis::s_rceCopyTable0F + 2 * a4[1];
  return (unsigned __int8 *)(*((int (__thiscall **)(CDetourDis *, const struct CDetourDis::COPYENTRY *const *, unsigned __int8 *, unsigned __int8 *))v5
                             + 1))(
                              this,
                              v5,
                              a3 + 1,
                              a4 + 1);
}

```

## disassembly

```asm
0x40e5c0  mov     edx, [esp+arg_8]
0x40e5c4  push    ebx
0x40e5c5  push    esi
0x40e5c6  push    edi
0x40e5c7  mov     al, [edx]
0x40e5c9  mov     ebx, ecx
0x40e5cb  mov     edi, [esp+0Ch+arg_4]
0x40e5cf  inc     edx
0x40e5d0  push    edx
0x40e5d1  mov     [edi], al
0x40e5d3  movzx   eax, byte ptr [edx]
0x40e5d6  lea     esi, ?s_rceCopyTable0F@CDetourDis@@1QBUCOPYENTRY@1@B[eax*8]; CDetourDis::COPYENTRY const * const CDetourDis::s_rceCopyTable0F
0x40e5dd  lea     eax, [edi+1]
0x40e5e0  push    eax
0x40e5e1  push    esi
0x40e5e2  mov     esi, [esi+4]
0x40e5e5  mov     ecx, esi
0x40e5e7  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x40e5ed  mov     ecx, ebx
0x40e5ef  call    esi
0x40e5f1  pop     edi
0x40e5f2  pop     esi
0x40e5f3  pop     ebx
0x40e5f4  retn    0Ch
```
