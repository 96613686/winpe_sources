# SetPropVariantElement(tagPROPVARIANT *,ulong,tagPROPVARIANT const *)

- ea: `0x180020f4c`
- end: `0x18002102d`
- name: `?SetPropVariantElement@@YAJPEAUtagPROPVARIANT@@KPEBU1@@Z`
- size: `225`
- prototype: `__int64 __fastcall(struct tagPROPVARIANT *, unsigned int, const struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180020674`

## callees

- `0x180020a9c`
- `0x180020f4c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18002100f`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18002100f`

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
0x180020f4c  mov     [rsp+arg_0], rbx
0x180020f51  push    rdi
0x180020f52  sub     rsp, 20h
0x180020f56  movzx   edi, word ptr [rcx]
0x180020f59  mov     r11, r8
0x180020f5c  mov     r9d, edi
0x180020f5f  mov     ebx, edx
0x180020f61  mov     r10, rcx
0x180020f64  sub     r9d, 2
0x180020f68  jz      loc_18002100C
0x180020f6e  sub     r9d, 1
0x180020f72  jz      loc_18002100C
0x180020f78  sub     r9d, 0Dh
0x180020f7c  jz      loc_18002100C
0x180020f82  sub     r9d, 1
0x180020f86  jz      loc_18002100C
0x180020f8c  sub     r9d, 1
0x180020f90  jz      short loc_18002100C
0x180020f92  cmp     r9d, 1
0x180020f96  jz      short loc_18002100C
0x180020f98  bt      di, 0Ch
0x180020f9d  mov     r9d, 80070057h
0x180020fa3  jnb     short loc_18002101E
0x180020fa5  call    ?GetPropVariantElementCount@@YAKPEBUtagPROPVARIANT@@@Z; GetPropVariantElementCount(tagPROPVARIANT const *)
0x180020faa  cmp     ebx, eax
0x180020fac  jnb     short loc_18002101E
0x180020fae  movzx   ecx, word ptr [r11]
0x180020fb2  btr     edi, 0Ch
0x180020fb6  cmp     edi, ecx
0x180020fb8  jnz     short loc_18002101E
0x180020fba  xor     r9d, r9d
0x180020fbd  sub     ecx, 2
0x180020fc0  jz      short loc_180020FFD
0x180020fc2  sub     ecx, 1
0x180020fc5  jz      short loc_180020FF0
0x180020fc7  sub     ecx, 0Dh
0x180020fca  jz      short loc_180020FE3
0x180020fcc  sub     ecx, 1
0x180020fcf  jz      short loc_180020FE3
0x180020fd1  sub     ecx, 1
0x180020fd4  jz      short loc_180020FFD
0x180020fd6  cmp     ecx, 1
0x180020fd9  jz      short loc_180020FF0
0x180020fdb  mov     r9d, 80070057h
0x180020fe1  jmp     short loc_18002101E
0x180020fe3  mov     rcx, [r10+10h]
0x180020fe7  mov     al, [r11+8]
0x180020feb  mov     [rbx+rcx], al
0x180020fee  jmp     short loc_18002101E
0x180020ff0  mov     rcx, [r10+10h]
0x180020ff4  mov     eax, [r11+8]
0x180020ff8  mov     [rcx+rbx*4], eax
0x180020ffb  jmp     short loc_18002101E
0x180020ffd  mov     rcx, [r10+10h]; pvarDest
0x180021001  movzx   eax, word ptr [r11+8]
0x180021006  mov     [rcx+rbx*2], ax
0x18002100a  jmp     short loc_18002101E
0x18002100c  mov     rdx, r11; pvarSrc
0x18002100f  call    cs:__imp_PropVariantCopy
0x180021016  nop     dword ptr [rax+rax+00h]
0x18002101b  mov     r9d, eax
0x18002101e  mov     rbx, [rsp+28h+arg_0]
0x180021023  mov     eax, r9d
0x180021026  add     rsp, 20h
0x18002102a  pop     rdi
0x18002102b  retn
```
