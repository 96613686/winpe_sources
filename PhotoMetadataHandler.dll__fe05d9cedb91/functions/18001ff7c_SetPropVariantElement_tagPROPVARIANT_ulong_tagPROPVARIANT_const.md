# SetPropVariantElement(tagPROPVARIANT *,ulong,tagPROPVARIANT const *)

- ea: `0x18001ff7c`
- end: `0x180020056`
- name: `?SetPropVariantElement@@YAJPEAUtagPROPVARIANT@@KPEBU1@@Z`
- size: `218`
- prototype: `__int64 __fastcall(struct tagPROPVARIANT *, unsigned int, const struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001f724`

## callees

- `0x18001fafc`
- `0x18001ff7c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18002003f`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18002003f`

## pseudocode

```c
__int64 __fastcall SetPropVariantElement(struct tagPROPVARIANT *a1, unsigned int a2, const struct tagPROPVARIANT *a3)
{
  int vt; // edi
  __int64 v4; // rbx
  unsigned int v5; // r9d
  __int64 v6; // r10
  unsigned __int16 *v7; // r11
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx

  vt = a1->vt;
  v4 = a2;
  if ( vt == 2 || a1->vt == 3 || a1->vt == 16 || a1->vt == 17 || (unsigned int)a1->vt - 18 < 2 )
    return (unsigned int)PropVariantCopy(a1, a3);
  v5 = -2147024809;
  if ( (vt & 0x1000) != 0 && a2 < GetPropVariantElementCount(a1) )
  {
    v8 = *v7;
    if ( (vt & 0xFFFFEFFF) == v8 )
    {
      v5 = 0;
      v9 = v8 - 2;
      if ( v9 )
      {
        v10 = v9 - 1;
        if ( !v10 )
          goto LABEL_17;
        v11 = v10 - 13;
        if ( !v11 || (v12 = v11 - 1) == 0 )
        {
          *(_BYTE *)(v4 + *(_QWORD *)(v6 + 16)) = *((_BYTE *)v7 + 8);
          return v5;
        }
        v13 = v12 - 1;
        if ( v13 )
        {
          if ( v13 != 1 )
            return (unsigned int)-2147024809;
LABEL_17:
          *(_DWORD *)(*(_QWORD *)(v6 + 16) + 4 * v4) = *((_DWORD *)v7 + 2);
          return v5;
        }
      }
      *(_WORD *)(*(_QWORD *)(v6 + 16) + 2 * v4) = v7[4];
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18001ff7c  mov     [rsp+arg_0], rbx
0x18001ff81  push    rdi
0x18001ff82  sub     rsp, 20h
0x18001ff86  movzx   edi, word ptr [rcx]
0x18001ff89  mov     r11, r8
0x18001ff8c  mov     r9d, edi
0x18001ff8f  mov     ebx, edx
0x18001ff91  mov     r10, rcx
0x18001ff94  sub     r9d, 2
0x18001ff98  jz      loc_18002003C
0x18001ff9e  sub     r9d, 1
0x18001ffa2  jz      loc_18002003C
0x18001ffa8  sub     r9d, 0Dh
0x18001ffac  jz      loc_18002003C
0x18001ffb2  sub     r9d, 1
0x18001ffb6  jz      loc_18002003C
0x18001ffbc  sub     r9d, 1
0x18001ffc0  jz      short loc_18002003C
0x18001ffc2  cmp     r9d, 1
0x18001ffc6  jz      short loc_18002003C
0x18001ffc8  bt      di, 0Ch
0x18001ffcd  mov     r9d, 80070057h
0x18001ffd3  jnb     short loc_180020048
0x18001ffd5  call    ?GetPropVariantElementCount@@YAKPEBUtagPROPVARIANT@@@Z; GetPropVariantElementCount(tagPROPVARIANT const *)
0x18001ffda  cmp     ebx, eax
0x18001ffdc  jnb     short loc_180020048
0x18001ffde  movzx   ecx, word ptr [r11]
0x18001ffe2  btr     edi, 0Ch
0x18001ffe6  cmp     edi, ecx
0x18001ffe8  jnz     short loc_180020048
0x18001ffea  xor     r9d, r9d
0x18001ffed  sub     ecx, 2
0x18001fff0  jz      short loc_18002002D
0x18001fff2  sub     ecx, 1
0x18001fff5  jz      short loc_180020020
0x18001fff7  sub     ecx, 0Dh
0x18001fffa  jz      short loc_180020013
0x18001fffc  sub     ecx, 1
0x18001ffff  jz      short loc_180020013
0x180020001  sub     ecx, 1
0x180020004  jz      short loc_18002002D
0x180020006  cmp     ecx, 1
0x180020009  jz      short loc_180020020
0x18002000b  mov     r9d, 80070057h
0x180020011  jmp     short loc_180020048
0x180020013  mov     rcx, [r10+10h]
0x180020017  mov     al, [r11+8]
0x18002001b  mov     [rbx+rcx], al
0x18002001e  jmp     short loc_180020048
0x180020020  mov     rcx, [r10+10h]
0x180020024  mov     eax, [r11+8]
0x180020028  mov     [rcx+rbx*4], eax
0x18002002b  jmp     short loc_180020048
0x18002002d  mov     rcx, [r10+10h]; pvarDest
0x180020031  movzx   eax, word ptr [r11+8]
0x180020036  mov     [rcx+rbx*2], ax
0x18002003a  jmp     short loc_180020048
0x18002003c  mov     rdx, r11; pvarSrc
0x18002003f  call    cs:__imp_PropVariantCopy
0x180020045  mov     r9d, eax
0x180020048  mov     rbx, [rsp+28h+arg_0]
0x18002004d  mov     eax, r9d
0x180020050  add     rsp, 20h
0x180020054  pop     rdi
0x180020055  retn
```
