# CDetourDis::CopyBytesPrefix(CDetourDis::COPYENTRY const *,uchar *,uchar *)

- ea: `0x40e4b0`
- end: `0x40e4e7`
- name: `?CopyBytesPrefix@CDetourDis@@IAEPAEPBUCOPYENTRY@1@PAE1@Z`
- size: `55`
- prototype: `unsigned __int8 *__thiscall(CDetourDis *__hidden this, const struct CDetourDis::COPYENTRY *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x40d1d0`

## pseudocode

```c
unsigned __int8 *__thiscall CDetourDis::CopyBytesPrefix(
        CDetourDis *this,
        const struct CDetourDis::COPYENTRY *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4)
{
  const struct CDetourDis::COPYENTRY *const *v5; // [esp-Ch] [ebp-18h]

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
0x40e4b0  mov     edx, [esp+arg_8]
0x40e4b4  push    ebx
0x40e4b5  push    esi
0x40e4b6  push    edi
0x40e4b7  mov     al, [edx]
0x40e4b9  mov     ebx, ecx
0x40e4bb  mov     edi, [esp+0Ch+arg_4]
0x40e4bf  inc     edx
0x40e4c0  push    edx
0x40e4c1  mov     [edi], al
0x40e4c3  movzx   eax, byte ptr [edx]
0x40e4c6  lea     esi, ?s_rceCopyTable@CDetourDis@@1QBUCOPYENTRY@1@B[eax*8]; CDetourDis::COPYENTRY const * const CDetourDis::s_rceCopyTable
0x40e4cd  lea     eax, [edi+1]
0x40e4d0  push    eax
0x40e4d1  push    esi
0x40e4d2  mov     esi, [esi+4]
0x40e4d5  mov     ecx, esi
0x40e4d7  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x40e4dd  mov     ecx, ebx
0x40e4df  call    esi
0x40e4e1  pop     edi
0x40e4e2  pop     esi
0x40e4e3  pop     ebx
0x40e4e4  retn    0Ch
```
