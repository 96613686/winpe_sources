# CDetourDis::CopyVexCommon(uchar,uchar *,uchar *)

- ea: `0x40e990`
- end: `0x40ea1a`
- name: `?CopyVexCommon@CDetourDis@@IAEPAEEPAE0@Z`
- size: `138`
- prototype: `unsigned __int8 *__thiscall(CDetourDis *__hidden this, char, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x40e8e0`
- `0x40e930`

## callees

- `0x40d1d0`
- `0x40e990`

## pseudocode

```c
unsigned __int8 *__thiscall CDetourDis::CopyVexCommon(
        CDetourDis *this,
        char a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4)
{
  int *v4; // esi

  *((_DWORD *)this + 3) = 1;
  switch ( a2 )
  {
    case 1:
      v4 = (int *)(&CDetourDis::s_rceCopyTable0F + 2 * *a4);
      break;
    case 2:
      v4 = &dword_413168;
      break;
    case 3:
      v4 = &dword_413170;
      break;
    default:
      v4 = &dword_413178;
      break;
  }
  switch ( *(a4 - 1) & 3 )
  {
    case 1:
      *(_DWORD *)this = 1;
      break;
    case 2:
      *((_DWORD *)this + 5) = 1;
      break;
    case 3:
      *((_DWORD *)this + 4) = 1;
      break;
  }
  return (unsigned __int8 *)((int (__thiscall *)(CDetourDis *, int *, unsigned __int8 *, unsigned __int8 *))v4[1])(
                              this,
                              v4,
                              a3,
                              a4);
}

```

## disassembly

```asm
0x40e990  movzx   eax, [esp+arg_0]
0x40e995  push    esi
0x40e996  push    edi
0x40e997  mov     edi, ecx
0x40e999  mov     ecx, [esp+8+arg_8]
0x40e99d  mov     dword ptr [edi+0Ch], 1
0x40e9a4  sub     eax, 1
0x40e9a7  jz      short loc_40E9C8
0x40e9a9  sub     eax, 1
0x40e9ac  jz      short loc_40E9C1
0x40e9ae  sub     eax, 1
0x40e9b1  jz      short loc_40E9BA
0x40e9b3  mov     esi, offset dword_413178
0x40e9b8  jmp     short loc_40E9D2
0x40e9ba  mov     esi, offset dword_413170
0x40e9bf  jmp     short loc_40E9D2
0x40e9c1  mov     esi, offset dword_413168
0x40e9c6  jmp     short loc_40E9D2
0x40e9c8  movzx   eax, byte ptr [ecx]
0x40e9cb  lea     esi, ?s_rceCopyTable0F@CDetourDis@@1QBUCOPYENTRY@1@B[eax*8]; CDetourDis::COPYENTRY const * const CDetourDis::s_rceCopyTable0F
0x40e9d2  movzx   eax, byte ptr [ecx-1]
0x40e9d6  and     eax, 3
0x40e9d9  sub     eax, 1
0x40e9dc  jz      short loc_40E9FA
0x40e9de  sub     eax, 1
0x40e9e1  jz      short loc_40E9F1
0x40e9e3  sub     eax, 1
0x40e9e6  jnz     short loc_40EA00
0x40e9e8  mov     dword ptr [edi+10h], 1
0x40e9ef  jmp     short loc_40EA00
0x40e9f1  mov     dword ptr [edi+14h], 1
0x40e9f8  jmp     short loc_40EA00
0x40e9fa  mov     dword ptr [edi], 1
0x40ea00  push    ecx
0x40ea01  push    [esp+0Ch+arg_4]
0x40ea05  push    esi
0x40ea06  mov     esi, [esi+4]
0x40ea09  mov     ecx, esi
0x40ea0b  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x40ea11  mov     ecx, edi
0x40ea13  call    esi
0x40ea15  pop     edi
0x40ea16  pop     esi
0x40ea17  retn    0Ch
```
