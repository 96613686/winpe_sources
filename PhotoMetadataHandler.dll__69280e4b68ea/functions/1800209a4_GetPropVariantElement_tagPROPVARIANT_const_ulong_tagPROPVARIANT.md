# GetPropVariantElement(tagPROPVARIANT const *,ulong,tagPROPVARIANT *)

- ea: `0x1800209a4`
- end: `0x180020a93`
- name: `?GetPropVariantElement@@YAJPEBUtagPROPVARIANT@@KPEAU1@@Z`
- size: `239`
- prototype: `__int64 __fastcall(const struct tagPROPVARIANT *, unsigned int, struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800133d8`
- `0x18001f4b0`

## callees

- `0x1800209a4`
- `0x180020a9c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180020a66`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180020a66`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800209b8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180020a7b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800209b8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180020a7b`

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
0x1800209a4  push    rbx
0x1800209a6  push    rbp
0x1800209a7  push    rsi
0x1800209a8  push    rdi
0x1800209a9  sub     rsp, 28h
0x1800209ad  mov     rdi, rcx
0x1800209b0  mov     esi, edx
0x1800209b2  mov     rcx, r8; pvar
0x1800209b5  mov     rbx, r8
0x1800209b8  call    cs:__imp_PropVariantClear
0x1800209bf  nop     dword ptr [rax+rax+00h]
0x1800209c4  mov     r9d, 80070057h
0x1800209ca  mov     rcx, rdi; struct tagPROPVARIANT *
0x1800209cd  mov     ebp, r9d
0x1800209d0  call    ?GetPropVariantElementCount@@YAKPEBUtagPROPVARIANT@@@Z; GetPropVariantElementCount(tagPROPVARIANT const *)
0x1800209d5  cmp     esi, eax
0x1800209d7  jnb     loc_180020A78
0x1800209dd  movzx   edx, word ptr [rdi]
0x1800209e0  mov     ecx, edx
0x1800209e2  sub     ecx, 2
0x1800209e5  jz      short loc_180020A60
0x1800209e7  sub     ecx, 1
0x1800209ea  jz      short loc_180020A60
0x1800209ec  sub     ecx, 0Dh
0x1800209ef  jz      short loc_180020A60
0x1800209f1  sub     ecx, 1
0x1800209f4  jz      short loc_180020A60
0x1800209f6  sub     ecx, 1
0x1800209f9  jz      short loc_180020A60
0x1800209fb  cmp     ecx, 1
0x1800209fe  jz      short loc_180020A60
0x180020a00  bt      dx, 0Ch
0x180020a05  jnb     short loc_180020A78
0x180020a07  mov     eax, 0EFFFh
0x180020a0c  xor     ebp, ebp
0x180020a0e  and     dx, ax
0x180020a11  movzx   ecx, dx
0x180020a14  mov     [rbx], cx
0x180020a17  sub     ecx, 2
0x180020a1a  jz      short loc_180020A46
0x180020a1c  sub     ecx, 1
0x180020a1f  jz      short loc_180020A3A
0x180020a21  sub     ecx, 0Dh
0x180020a24  jz      short loc_180020A54
0x180020a26  sub     ecx, 1
0x180020a29  jz      short loc_180020A54
0x180020a2b  sub     ecx, 1
0x180020a2e  jz      short loc_180020A46
0x180020a30  cmp     ecx, 1
0x180020a33  jz      short loc_180020A3A
0x180020a35  mov     ebp, r9d
0x180020a38  jmp     short loc_180020A78
0x180020a3a  mov     rax, [rdi+10h]
0x180020a3e  mov     ecx, [rax+rsi*4]
0x180020a41  mov     [rbx+8], ecx
0x180020a44  jmp     short loc_180020A87
0x180020a46  mov     rax, [rdi+10h]
0x180020a4a  movzx   ecx, word ptr [rax+rsi*2]
0x180020a4e  mov     [rbx+8], cx
0x180020a52  jmp     short loc_180020A87
0x180020a54  mov     rax, [rdi+10h]
0x180020a58  mov     cl, [rsi+rax]
0x180020a5b  mov     [rbx+8], cl
0x180020a5e  jmp     short loc_180020A87
0x180020a60  mov     rdx, rdi; pvarSrc
0x180020a63  mov     rcx, rbx; pvarDest
0x180020a66  call    cs:__imp_PropVariantCopy
0x180020a6d  nop     dword ptr [rax+rax+00h]
0x180020a72  mov     ebp, eax
0x180020a74  test    eax, eax
0x180020a76  jns     short loc_180020A87
0x180020a78  mov     rcx, rbx; pvar
0x180020a7b  call    cs:__imp_PropVariantClear
0x180020a82  nop     dword ptr [rax+rax+00h]
0x180020a87  mov     eax, ebp
0x180020a89  add     rsp, 28h
0x180020a8d  pop     rdi
0x180020a8e  pop     rsi
0x180020a8f  pop     rbp
0x180020a90  pop     rbx
0x180020a91  retn
```
