# CDetourDis::CopyF2(CDetourDis::COPYENTRY const *,uchar *,uchar *)

- ea: `0x40e760`
- end: `0x40e79e`
- name: `?CopyF2@CDetourDis@@IAEPAEPBUCOPYENTRY@1@PAE1@Z`
- size: `62`
- prototype: `unsigned __int8 *__thiscall(CDetourDis *__hidden this, const struct CDetourDis::COPYENTRY *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x40d1d0`

## pseudocode

```c
unsigned __int8 *__thiscall CDetourDis::CopyF2(
        CDetourDis *this,
        const struct CDetourDis::COPYENTRY *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4)
{
  const struct CDetourDis::COPYENTRY *const *v5; // [esp-Ch] [ebp-18h]

  *((_DWORD *)this + 4) = 1;
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
0x40e760  mov     edx, [esp+arg_8]
0x40e764  push    ebx
0x40e765  push    esi
0x40e766  mov     ebx, ecx
0x40e768  push    edi
0x40e769  mov     edi, [esp+0Ch+arg_4]
0x40e76d  mov     dword ptr [ebx+10h], 1
0x40e774  mov     al, [edx]
0x40e776  inc     edx
0x40e777  mov     [edi], al
0x40e779  push    edx
0x40e77a  movzx   eax, byte ptr [edx]
0x40e77d  lea     esi, ?s_rceCopyTable@CDetourDis@@1QBUCOPYENTRY@1@B[eax*8]; CDetourDis::COPYENTRY const * const CDetourDis::s_rceCopyTable
0x40e784  lea     eax, [edi+1]
0x40e787  push    eax
0x40e788  push    esi
0x40e789  mov     esi, [esi+4]
0x40e78c  mov     ecx, esi
0x40e78e  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x40e794  mov     ecx, ebx
0x40e796  call    esi
0x40e798  pop     edi
0x40e799  pop     esi
0x40e79a  pop     ebx
0x40e79b  retn    0Ch
```
