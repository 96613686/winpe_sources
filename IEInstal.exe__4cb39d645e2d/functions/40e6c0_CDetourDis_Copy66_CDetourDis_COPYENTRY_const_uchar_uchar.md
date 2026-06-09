# CDetourDis::Copy66(CDetourDis::COPYENTRY const *,uchar *,uchar *)

- ea: `0x40e6c0`
- end: `0x40e6fd`
- name: `?Copy66@CDetourDis@@IAEPAEPBUCOPYENTRY@1@PAE1@Z`
- size: `61`
- prototype: `unsigned __int8 *__thiscall(CDetourDis *__hidden this, const struct CDetourDis::COPYENTRY *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x40d1d0`

## pseudocode

```c
unsigned __int8 *__thiscall CDetourDis::Copy66(
        CDetourDis *this,
        const struct CDetourDis::COPYENTRY *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4)
{
  const struct CDetourDis::COPYENTRY *const *v5; // [esp-Ch] [ebp-18h]

  *(_DWORD *)this = 1;
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
0x40e6c0  mov     edx, [esp+arg_8]
0x40e6c4  push    ebx
0x40e6c5  push    esi
0x40e6c6  mov     ebx, ecx
0x40e6c8  push    edi
0x40e6c9  mov     edi, [esp+0Ch+arg_4]
0x40e6cd  mov     dword ptr [ebx], 1
0x40e6d3  mov     al, [edx]
0x40e6d5  inc     edx
0x40e6d6  mov     [edi], al
0x40e6d8  push    edx
0x40e6d9  movzx   eax, byte ptr [edx]
0x40e6dc  lea     esi, ?s_rceCopyTable@CDetourDis@@1QBUCOPYENTRY@1@B[eax*8]; CDetourDis::COPYENTRY const * const CDetourDis::s_rceCopyTable
0x40e6e3  lea     eax, [edi+1]
0x40e6e6  push    eax
0x40e6e7  push    esi
0x40e6e8  mov     esi, [esi+4]
0x40e6eb  mov     ecx, esi
0x40e6ed  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x40e6f3  mov     ecx, ebx
0x40e6f5  call    esi
0x40e6f7  pop     edi
0x40e6f8  pop     esi
0x40e6f9  pop     ebx
0x40e6fa  retn    0Ch
```
