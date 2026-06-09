# CDetourDis::CopyF3(CDetourDis::COPYENTRY const *,uchar *,uchar *)

- ea: `0x40e7b0`
- end: `0x40e7ee`
- name: `?CopyF3@CDetourDis@@IAEPAEPBUCOPYENTRY@1@PAE1@Z`
- size: `62`
- prototype: `unsigned __int8 *__thiscall(CDetourDis *__hidden this, const struct CDetourDis::COPYENTRY *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x40d1d0`

## pseudocode

```c
unsigned __int8 *__thiscall CDetourDis::CopyF3(
        CDetourDis *this,
        const struct CDetourDis::COPYENTRY *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4)
{
  const struct CDetourDis::COPYENTRY *const *v5; // [esp-Ch] [ebp-18h]

  *((_DWORD *)this + 5) = 1;
  *a3 = *a4;
  v5 = &CDetourDis::s_rceCopyTable + 2 * a4[1];
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
0x40e7b0  mov     edx, [esp+arg_8]
0x40e7b4  push    ebx
0x40e7b5  push    esi
0x40e7b6  mov     ebx, ecx
0x40e7b8  push    edi
0x40e7b9  mov     edi, [esp+0Ch+arg_4]
0x40e7bd  mov     dword ptr [ebx+14h], 1
0x40e7c4  mov     al, [edx]
0x40e7c6  inc     edx
0x40e7c7  mov     [edi], al
0x40e7c9  push    edx
0x40e7ca  movzx   eax, byte ptr [edx]
0x40e7cd  lea     esi, ?s_rceCopyTable@CDetourDis@@1QBUCOPYENTRY@1@B[eax*8]; CDetourDis::COPYENTRY const * const CDetourDis::s_rceCopyTable
0x40e7d4  lea     eax, [edi+1]
0x40e7d7  push    eax
0x40e7d8  push    esi
0x40e7d9  mov     esi, [esi+4]
0x40e7dc  mov     ecx, esi
0x40e7de  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x40e7e4  mov     ecx, ebx
0x40e7e6  call    esi
0x40e7e8  pop     edi
0x40e7e9  pop     esi
0x40e7ea  pop     ebx
0x40e7eb  retn    0Ch
```
