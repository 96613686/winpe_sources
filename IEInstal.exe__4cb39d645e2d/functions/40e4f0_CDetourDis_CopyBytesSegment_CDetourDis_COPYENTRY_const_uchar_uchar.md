# CDetourDis::CopyBytesSegment(CDetourDis::COPYENTRY const *,uchar *,uchar *)

- ea: `0x40e4f0`
- end: `0x40e52e`
- name: `?CopyBytesSegment@CDetourDis@@IAEPAEPBUCOPYENTRY@1@PAE1@Z`
- size: `62`
- prototype: `unsigned __int8 *__thiscall(CDetourDis *__hidden this, const struct CDetourDis::COPYENTRY *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x40d1d0`

## pseudocode

```c
unsigned __int8 *__thiscall CDetourDis::CopyBytesSegment(
        CDetourDis *this,
        const struct CDetourDis::COPYENTRY *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4)
{
  const struct CDetourDis::COPYENTRY *const *v5; // [esp-Ch] [ebp-18h]

  *((_BYTE *)this + 24) = *a4;
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
0x40e4f0  mov     edx, [esp+arg_8]
0x40e4f4  push    ebx
0x40e4f5  push    esi
0x40e4f6  mov     ebx, ecx
0x40e4f8  movzx   eax, byte ptr [edx]
0x40e4fb  push    edi
0x40e4fc  mov     edi, [esp+0Ch+arg_4]
0x40e500  mov     [ebx+18h], al
0x40e503  movzx   eax, byte ptr [edx]
0x40e506  inc     edx
0x40e507  push    edx
0x40e508  mov     [edi], al
0x40e50a  movzx   eax, byte ptr [edx]
0x40e50d  lea     esi, ?s_rceCopyTable@CDetourDis@@1QBUCOPYENTRY@1@B[eax*8]; CDetourDis::COPYENTRY const * const CDetourDis::s_rceCopyTable
0x40e514  lea     eax, [edi+1]
0x40e517  push    eax
0x40e518  push    esi
0x40e519  mov     esi, [esi+4]
0x40e51c  mov     ecx, esi
0x40e51e  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x40e524  mov     ecx, ebx
0x40e526  call    esi
0x40e528  pop     edi
0x40e529  pop     esi
0x40e52a  pop     ebx
0x40e52b  retn    0Ch
```
