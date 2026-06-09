# GetPropVariantElement(tagPROPVARIANT const *,ulong,tagPROPVARIANT *)

- ea: `0x18001fa18`
- end: `0x18001faf4`
- name: `?GetPropVariantElement@@YAJPEBUtagPROPVARIANT@@KPEAU1@@Z`
- size: `220`
- prototype: `__int64 __fastcall(const struct tagPROPVARIANT *, unsigned int, struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012afc`
- `0x18001e644`

## callees

- `0x18001fa18`
- `0x18001fafc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18001fad4`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18001fad4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001fa2c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001fae3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001fa2c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001fae3`

## pseudocode

```c
__int64 __fastcall GetPropVariantElement(const struct tagPROPVARIANT *a1, unsigned int a2, struct tagPROPVARIANT *a3)
{
  __int64 v4; // rsi
  unsigned int v6; // ebp
  unsigned int v7; // r9d
  VARTYPE vt; // dx
  VARTYPE v9; // dx

  v4 = a2;
  PropVariantClear(a3);
  v6 = -2147024809;
  if ( (unsigned int)v4 >= GetPropVariantElementCount(a1) )
    goto LABEL_19;
  vt = a1->vt;
  if ( a1->vt != 2 && a1->vt != 3 && a1->vt != 16 && a1->vt != 17 && (unsigned int)a1->vt - 18 >= 2 )
  {
    if ( (vt & 0x1000) == 0 )
    {
LABEL_19:
      PropVariantClear(a3);
      return v6;
    }
    v6 = 0;
    v9 = vt & 0xEFFF;
    a3->vt = v9;
    if ( v9 != 2 )
    {
      if ( v9 == 3 )
      {
LABEL_15:
        a3->lVal = *(_DWORD *)&a1->bstrblobVal.pData[4 * v4];
        return v6;
      }
      if ( v9 == 16 || v9 == 17 )
      {
        a3->cVal = a1->bstrblobVal.pData[v4];
        return v6;
      }
      if ( v9 != 18 )
      {
        if ( v9 != 19 )
        {
          v6 = v7;
          goto LABEL_19;
        }
        goto LABEL_15;
      }
    }
    a3->iVal = *(_WORD *)&a1->bstrblobVal.pData[2 * v4];
    return v6;
  }
  v6 = PropVariantCopy(a3, a1);
  if ( (v6 & 0x80000000) != 0 )
    goto LABEL_19;
  return v6;
}

```

## disassembly

```asm
0x18001fa18  push    rbx
0x18001fa1a  push    rbp
0x18001fa1b  push    rsi
0x18001fa1c  push    rdi
0x18001fa1d  sub     rsp, 28h
0x18001fa21  mov     rdi, rcx
0x18001fa24  mov     esi, edx
0x18001fa26  mov     rcx, r8; pvar
0x18001fa29  mov     rbx, r8
0x18001fa2c  call    cs:__imp_PropVariantClear
0x18001fa32  mov     r9d, 80070057h
0x18001fa38  mov     rcx, rdi; struct tagPROPVARIANT *
0x18001fa3b  mov     ebp, r9d
0x18001fa3e  call    ?GetPropVariantElementCount@@YAKPEBUtagPROPVARIANT@@@Z; GetPropVariantElementCount(tagPROPVARIANT const *)
0x18001fa43  cmp     esi, eax
0x18001fa45  jnb     loc_18001FAE0
0x18001fa4b  movzx   edx, word ptr [rdi]
0x18001fa4e  mov     ecx, edx
0x18001fa50  sub     ecx, 2
0x18001fa53  jz      short loc_18001FACE
0x18001fa55  sub     ecx, 1
0x18001fa58  jz      short loc_18001FACE
0x18001fa5a  sub     ecx, 0Dh
0x18001fa5d  jz      short loc_18001FACE
0x18001fa5f  sub     ecx, 1
0x18001fa62  jz      short loc_18001FACE
0x18001fa64  sub     ecx, 1
0x18001fa67  jz      short loc_18001FACE
0x18001fa69  cmp     ecx, 1
0x18001fa6c  jz      short loc_18001FACE
0x18001fa6e  bt      dx, 0Ch
0x18001fa73  jnb     short loc_18001FAE0
0x18001fa75  mov     eax, 0EFFFh
0x18001fa7a  xor     ebp, ebp
0x18001fa7c  and     dx, ax
0x18001fa7f  movzx   ecx, dx
0x18001fa82  mov     [rbx], cx
0x18001fa85  sub     ecx, 2
0x18001fa88  jz      short loc_18001FAB4
0x18001fa8a  sub     ecx, 1
0x18001fa8d  jz      short loc_18001FAA8
0x18001fa8f  sub     ecx, 0Dh
0x18001fa92  jz      short loc_18001FAC2
0x18001fa94  sub     ecx, 1
0x18001fa97  jz      short loc_18001FAC2
0x18001fa99  sub     ecx, 1
0x18001fa9c  jz      short loc_18001FAB4
0x18001fa9e  cmp     ecx, 1
0x18001faa1  jz      short loc_18001FAA8
0x18001faa3  mov     ebp, r9d
0x18001faa6  jmp     short loc_18001FAE0
0x18001faa8  mov     rax, [rdi+10h]
0x18001faac  mov     ecx, [rax+rsi*4]
0x18001faaf  mov     [rbx+8], ecx
0x18001fab2  jmp     short loc_18001FAE9
0x18001fab4  mov     rax, [rdi+10h]
0x18001fab8  movzx   ecx, word ptr [rax+rsi*2]
0x18001fabc  mov     [rbx+8], cx
0x18001fac0  jmp     short loc_18001FAE9
0x18001fac2  mov     rax, [rdi+10h]
0x18001fac6  mov     cl, [rsi+rax]
0x18001fac9  mov     [rbx+8], cl
0x18001facc  jmp     short loc_18001FAE9
0x18001face  mov     rdx, rdi; pvarSrc
0x18001fad1  mov     rcx, rbx; pvarDest
0x18001fad4  call    cs:__imp_PropVariantCopy
0x18001fada  mov     ebp, eax
0x18001fadc  test    eax, eax
0x18001fade  jns     short loc_18001FAE9
0x18001fae0  mov     rcx, rbx; pvar
0x18001fae3  call    cs:__imp_PropVariantClear
0x18001fae9  mov     eax, ebp
0x18001faeb  add     rsp, 28h
0x18001faef  pop     rdi
0x18001faf0  pop     rsi
0x18001faf1  pop     rbp
0x18001faf2  pop     rbx
0x18001faf3  retn
```
