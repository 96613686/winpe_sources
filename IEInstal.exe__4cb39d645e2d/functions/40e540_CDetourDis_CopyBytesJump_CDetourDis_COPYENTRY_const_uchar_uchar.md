# CDetourDis::CopyBytesJump(CDetourDis::COPYENTRY const *,uchar *,uchar *)

- ea: `0x40e540`
- end: `0x40e5a7`
- name: `?CopyBytesJump@CDetourDis@@IAEPAEPBUCOPYENTRY@1@PAE1@Z`
- size: `103`
- prototype: `unsigned __int8 *__thiscall(CDetourDis *__hidden this, const struct CDetourDis::COPYENTRY *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x40e540`

## pseudocode

```c
unsigned __int8 *__thiscall CDetourDis::CopyBytesJump(
        CDetourDis *this,
        const struct CDetourDis::COPYENTRY *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4)
{
  int v5; // esi
  unsigned __int8 *v6; // ecx
  unsigned __int8 *result; // eax

  v5 = (char)a4[1];
  **((_DWORD **)this + 7) = &a4[v5 + 2];
  v6 = &a4[v5 - (_DWORD)a3];
  if ( *a4 == 0xEB )
  {
    *a3 = -23;
    result = a4 + 2;
    *(_DWORD *)(a3 + 1) = v6 - 3;
    **((_DWORD **)this + 8) = 3;
  }
  else
  {
    *a3 = 15;
    a3[1] = *a4 & 0xF | 0x80;
    *(_DWORD *)(a3 + 2) = v6 - 4;
    **((_DWORD **)this + 8) = 4;
    return a4 + 2;
  }
  return result;
}

```

## disassembly

```asm
0x40e540  push    ebx
0x40e541  push    ebp
0x40e542  push    esi
0x40e543  mov     ebx, ecx
0x40e545  push    edi
0x40e546  mov     edi, [esp+10h+arg_8]
0x40e54a  mov     eax, [ebx+1Ch]
0x40e54d  movsx   esi, byte ptr [edi+1]
0x40e551  lea     edx, [edi+2]
0x40e554  add     edx, esi
0x40e556  mov     [eax], edx
0x40e558  mov     edx, [esp+10h+arg_4]
0x40e55c  sub     esi, edx
0x40e55e  cmp     byte ptr [edi], 0EBh
0x40e561  lea     ecx, [esi+edi]
0x40e564  jnz     short loc_40E582
0x40e566  mov     byte ptr [edx], 0E9h
0x40e569  lea     eax, [edi+2]
0x40e56c  add     ecx, 0FFFFFFFDh
0x40e56f  pop     edi
0x40e570  mov     [edx+1], ecx
0x40e573  mov     ecx, [ebx+20h]
0x40e576  pop     esi
0x40e577  pop     ebp
0x40e578  pop     ebx
0x40e579  mov     dword ptr [ecx], 3
0x40e57f  retn    0Ch
0x40e582  mov     byte ptr [edx], 0Fh
0x40e585  mov     al, [edi]
0x40e587  and     al, 0Fh
0x40e589  or      al, 80h
0x40e58b  mov     [edx+1], al
0x40e58e  lea     eax, [ecx-4]
0x40e591  mov     [edx+2], eax
0x40e594  mov     eax, [ebx+20h]
0x40e597  mov     dword ptr [eax], 4
0x40e59d  lea     eax, [edi+2]
0x40e5a0  pop     edi
0x40e5a1  pop     esi
0x40e5a2  pop     ebp
0x40e5a3  pop     ebx
0x40e5a4  retn    0Ch
```
