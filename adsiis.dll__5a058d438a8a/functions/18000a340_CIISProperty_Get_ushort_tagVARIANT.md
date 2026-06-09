# CIISProperty::Get(ushort *,tagVARIANT *)

- ea: `0x18000a340`
- end: `0x18000a4e1`
- name: `?Get@CIISProperty@@UEAAJPEAGPEAUtagVARIANT@@@Z`
- size: `417`
- prototype: `int(CIISProperty *__hidden this, unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000a340`
- `0x18000c294`
- `0x18001beb8`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x18000a482`
- `OLEAUT32!__imp_VariantCopy` at `0x18000a482`

## pseudocode

```c
__int64 __fastcall CIISProperty::Get(const VARIANTARG *this, unsigned __int16 *a2, struct tagVARIANT *a3)
{
  unsigned int v5; // edx
  LONG Hi32; // eax
  IRecordInfo *pRecInfo; // rcx
  char v9; // al
  unsigned int v11; // [rsp+38h] [rbp+10h] BYREF
  unsigned int v12; // [rsp+48h] [rbp+20h] BYREF

  if ( a2 && a3 )
  {
    v12 = 0;
    v11 = 0;
    v5 = ValidatePropertyObjProps(a2, &v12, &v11);
    if ( (v5 & 0x80000000) != 0 )
      return v5;
    if ( v11 <= 0x18 )
    {
      switch ( v11 )
      {
        case 0x18u:
          a3->vt = 3;
          Hi32 = *((_DWORD *)&this[2].decVal + 5);
          goto LABEL_21;
        case 0x11u:
          a3->vt = 8;
          pRecInfo = this[1].pRecInfo;
          break;
        case 0x12u:
          a3->vt = 3;
          Hi32 = *(_DWORD *)&this[2].vt;
          goto LABEL_21;
        case 0x13u:
          a3->vt = 3;
          Hi32 = this[2].decVal.Hi32;
          goto LABEL_21;
        case 0x14u:
          a3->vt = 11;
          a3->iVal = -(this[2].iVal != 0);
          return v5;
        case 0x15u:
          a3->vt = 8;
          pRecInfo = this[6].pRecInfo;
          break;
        case 0x16u:
          if ( this[2].cyVal.Hi )
          {
            a3->vt = 3;
            Hi32 = this[2].cyVal.Hi;
            goto LABEL_21;
          }
          return (unsigned int)-2147463163;
        case 0x17u:
          a3->vt = 3;
          Hi32 = *((_DWORD *)&this[2].decVal + 4);
LABEL_21:
          a3->lVal = Hi32;
          return v5;
        default:
          return (unsigned int)-2147463162;
      }
      return (unsigned int)ADsAllocString(pRecInfo, &a3->decVal.Lo32);
    }
    switch ( v11 )
    {
      case 0x19u:
        a3->vt = 11;
        v9 = *((_DWORD *)&this[2].decVal + 5) & 1;
        break;
      case 0x1Bu:
        a3->vt = 11;
        v9 = *((_DWORD *)&this[2].decVal + 5) & 4;
        break;
      case 0x1Cu:
        a3->vt = 11;
        v9 = *((_DWORD *)&this[2].decVal + 5) & 8;
        break;
      case 0x1Du:
        a3->vt = 11;
        v9 = *((_DWORD *)&this[2].decVal + 5) & 0x10;
        break;
      case 0x1Fu:
        a3->vt = 11;
        v9 = *((_DWORD *)&this[2].decVal + 5) & 0x40;
        break;
      case 0x20u:
        return (unsigned int)VariantCopy(a3, this + 3);
      default:
        return (unsigned int)-2147463162;
    }
    a3->iVal = -(v9 != 0);
    return v5;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x18000a340  mov     [rsp+arg_0], rbx
0x18000a345  push    rdi
0x18000a346  sub     rsp, 20h
0x18000a34a  mov     rbx, r8
0x18000a34d  mov     rax, rdx
0x18000a350  mov     rdi, rcx
0x18000a353  test    rdx, rdx
0x18000a356  jz      loc_18000A4D1
0x18000a35c  test    rbx, rbx
0x18000a35f  jz      loc_18000A4D1
0x18000a365  lea     r8, [rsp+28h+arg_8]; unsigned int *
0x18000a36a  mov     [rsp+28h+arg_18], 0
0x18000a372  lea     rdx, [rsp+28h+arg_18]; unsigned int *
0x18000a377  mov     [rsp+28h+arg_8], 0
0x18000a37f  mov     rcx, rax; String2
0x18000a382  call    ?ValidatePropertyObjProps@@YAJPEAGPEAK1@Z; ValidatePropertyObjProps(ushort *,ulong *,ulong *)
0x18000a387  mov     edx, eax
0x18000a389  test    eax, eax
0x18000a38b  js      loc_18000A4CD
0x18000a391  mov     ecx, [rsp+28h+arg_8]
0x18000a395  cmp     ecx, 18h
0x18000a398  ja      loc_18000A456
0x18000a39e  jz      loc_18000A44C
0x18000a3a4  sub     ecx, 11h
0x18000a3a7  jz      loc_18000A433
0x18000a3ad  sub     ecx, 1
0x18000a3b0  jz      short loc_18000A423
0x18000a3b2  sub     ecx, 1
0x18000a3b5  jz      short loc_18000A419
0x18000a3b7  sub     ecx, 1
0x18000a3ba  jz      short loc_18000A401
0x18000a3bc  sub     ecx, 1
0x18000a3bf  jz      short loc_18000A3F3
0x18000a3c1  sub     ecx, 1
0x18000a3c4  jz      short loc_18000A3D9
0x18000a3c6  cmp     ecx, 1
0x18000a3c9  jnz     loc_18000A474
0x18000a3cf  mov     word ptr [rbx], 3
0x18000a3d4  mov     eax, [rdi+40h]
0x18000a3d7  jmp     short loc_18000A42B
0x18000a3d9  cmp     dword ptr [rdi+3Ch], 0
0x18000a3dd  jnz     short loc_18000A3E9
0x18000a3df  mov     edx, 80005005h
0x18000a3e4  jmp     loc_18000A4CD
0x18000a3e9  mov     word ptr [rbx], 3
0x18000a3ee  mov     eax, [rdi+3Ch]
0x18000a3f1  jmp     short loc_18000A42B
0x18000a3f3  mov     word ptr [rbx], 8
0x18000a3f8  mov     rcx, [rdi+0A0h]
0x18000a3ff  jmp     short loc_18000A43C
0x18000a401  mov     word ptr [rbx], 0Bh
0x18000a406  movzx   eax, word ptr [rdi+38h]
0x18000a40a  neg     ax
0x18000a40d  sbb     cx, cx
0x18000a410  mov     [rbx+8], cx
0x18000a414  jmp     loc_18000A4CD
0x18000a419  mov     word ptr [rbx], 3
0x18000a41e  mov     eax, [rdi+34h]
0x18000a421  jmp     short loc_18000A42B
0x18000a423  mov     word ptr [rbx], 3
0x18000a428  mov     eax, [rdi+30h]
0x18000a42b  mov     [rbx+8], eax
0x18000a42e  jmp     loc_18000A4CD
0x18000a433  mov     word ptr [rbx], 8
0x18000a438  mov     rcx, [rdi+28h]
0x18000a43c  lea     rdx, [rbx+8]
0x18000a440  call    ADsAllocString
0x18000a445  mov     edx, eax
0x18000a447  jmp     loc_18000A4CD
0x18000a44c  mov     word ptr [rbx], 3
0x18000a451  mov     eax, [rdi+44h]
0x18000a454  jmp     short loc_18000A42B
0x18000a456  sub     ecx, 19h
0x18000a459  jz      short loc_18000A4BA
0x18000a45b  sub     ecx, 2
0x18000a45e  jz      short loc_18000A4AE
0x18000a460  sub     ecx, 1
0x18000a463  jz      short loc_18000A4A2
0x18000a465  sub     ecx, 1
0x18000a468  jz      short loc_18000A496
0x18000a46a  sub     ecx, 2
0x18000a46d  jz      short loc_18000A48A
0x18000a46f  cmp     ecx, 1
0x18000a472  jz      short loc_18000A47B
0x18000a474  mov     edx, 80005006h
0x18000a479  jmp     short loc_18000A4CD
0x18000a47b  lea     rdx, [rdi+48h]; pvargSrc
0x18000a47f  mov     rcx, rbx; pvargDest
0x18000a482  call    cs:__imp_VariantCopy
0x18000a488  jmp     short loc_18000A445
0x18000a48a  mov     word ptr [rbx], 0Bh
0x18000a48f  mov     eax, [rdi+44h]
0x18000a492  and     al, 40h
0x18000a494  jmp     short loc_18000A4C4
0x18000a496  mov     word ptr [rbx], 0Bh
0x18000a49b  mov     eax, [rdi+44h]
0x18000a49e  and     al, 10h
0x18000a4a0  jmp     short loc_18000A4C4
0x18000a4a2  mov     word ptr [rbx], 0Bh
0x18000a4a7  mov     eax, [rdi+44h]
0x18000a4aa  and     al, 8
0x18000a4ac  jmp     short loc_18000A4C4
0x18000a4ae  mov     word ptr [rbx], 0Bh
0x18000a4b3  mov     eax, [rdi+44h]
0x18000a4b6  and     al, 4
0x18000a4b8  jmp     short loc_18000A4C4
0x18000a4ba  mov     word ptr [rbx], 0Bh
0x18000a4bf  mov     eax, [rdi+44h]
0x18000a4c2  and     al, 1
0x18000a4c4  neg     al
0x18000a4c6  sbb     ax, ax
0x18000a4c9  mov     [rbx+8], ax
0x18000a4cd  mov     eax, edx
0x18000a4cf  jmp     short loc_18000A4D6
0x18000a4d1  mov     eax, 80004003h
0x18000a4d6  mov     rbx, [rsp+28h+arg_0]
0x18000a4db  add     rsp, 20h
0x18000a4df  pop     rdi
0x18000a4e0  retn
```
