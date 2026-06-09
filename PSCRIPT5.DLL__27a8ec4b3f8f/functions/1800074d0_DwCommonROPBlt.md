# DwCommonROPBlt

- ea: `0x1800074d0`
- end: `0x1800078ca`
- name: `DwCommonROPBlt`
- size: `1018`
- prototype: `__int64 __fastcall(_DWORD *, SURFOBJ *, __int64, __int64, __int128 *, int *, int *, __int64, unsigned int, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180006670`
- `0x1800070d0`

## callees

- `0x180002938`
- `0x180005b84`
- `0x180005d44`
- `0x1800074d0`
- `0x180012200`
- `0x1800129f0`
- `0x180012a50`
- `0x180012e18`
- `0x1800166c0`
- `0x1800198f8`
- `0x180019fa0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180007515`
- `KERNEL32!SetLastError` at `0x180007515`
- `GDI32!XLATEOBJ_piVector` at `0x1800075d1`
- `GDI32!XLATEOBJ_piVector` at `0x1800075d1`

## pseudocode

```c
__int64 __fastcall DwCommonROPBlt(
        _DWORD *a1,
        SURFOBJ *a2,
        __int64 a3,
        __int64 a4,
        __int128 *a5,
        int *a6,
        int *a7,
        int *a8,
        int a9,
        int a10)
{
  bool v15; // zf
  int v16; // edx
  int v17; // edx
  ULONG *v18; // rax
  __int128 *v19; // r15
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // [rsp+50h] [rbp-71h] BYREF
  int v24; // [rsp+54h] [rbp-6Dh]
  int v25; // [rsp+58h] [rbp-69h]
  int v26; // [rsp+5Ch] [rbp-65h]
  __int128 v27; // [rsp+60h] [rbp-61h] BYREF
  __int64 v28; // [rsp+70h] [rbp-51h]
  int v29[3]; // [rsp+80h] [rbp-41h] BYREF
  int v30; // [rsp+8Ch] [rbp-35h]
  __int16 v31; // [rsp+BCh] [rbp-5h]

  LODWORD(v28) = 0;
  v27 = 0;
  if ( a2 && a2->iBitmapFormat == 9 && a9 != 52428 )
  {
    SetLastError(0x32u);
    return 2;
  }
  memset_0(v29, 0, 0x40u);
  if ( (unsigned __int8)a9 > 0x88u )
  {
    if ( (unsigned __int8)a9 > 0xBBu )
    {
      if ( (unsigned __int8)a9 == 204 || (unsigned __int8)a9 == 221 )
        goto LABEL_62;
      if ( (unsigned __int8)a9 != 226 )
      {
        if ( (unsigned __int8)a9 == 238 )
          goto LABEL_62;
        if ( (unsigned __int8)a9 == 240 )
          goto LABEL_61;
        if ( (unsigned __int8)a9 != 255 )
          goto LABEL_56;
        goto LABEL_60;
      }
    }
    else
    {
      switch ( (unsigned __int8)a9 )
      {
        case 0xBBu:
        case 0x99u:
          goto LABEL_17;
        case 0xA0u:
        case 0xA5u:
          goto LABEL_61;
        case 0xAAu:
          return 0;
        case 0xAFu:
          goto LABEL_61;
      }
      if ( (unsigned __int8)a9 != 184 )
      {
LABEL_56:
        if ( (((unsigned __int8)a9 ^ ((unsigned __int8)a9 >> 2)) & 0x33) == 0 )
        {
          if ( (unsigned __int8)a9 >> 4 == (a9 & 0xF) )
          {
            if ( (((unsigned __int8)a9 ^ ((unsigned __int8)a9 >> 1)) & 0x55) == 0 )
              goto LABEL_63;
            return 0;
          }
          goto LABEL_61;
        }
        goto LABEL_62;
      }
      v30 = 4;
      if ( a2->iBitmapFormat == 1 && (unsigned int)B1bppBmpHasTransparentColor((XLATEOBJ *)a4, (__int64)v29) )
      {
LABEL_38:
        v30 |= 0x10u;
        goto LABEL_63;
      }
    }
    return 1;
  }
  if ( (unsigned __int8)a9 == 136 )
  {
    v30 = 4;
    if ( a2->iBitmapFormat != 1 || !(unsigned int)B1bppBmpHasTransparentColor((XLATEOBJ *)a4, (__int64)v29) )
      goto LABEL_63;
    goto LABEL_38;
  }
  if ( (unsigned __int8)a9 > 0x44u )
  {
    switch ( (unsigned __int8)a9 )
    {
      case 'P':
        goto LABEL_61;
      case 'U':
        return 0;
      case 'Z':
      case '_':
LABEL_61:
        v30 = 2;
        goto LABEL_63;
      case 'f':
LABEL_62:
        v30 = 4;
        goto LABEL_63;
    }
    v15 = (unsigned __int8)a9 == 119;
    goto LABEL_16;
  }
  if ( (unsigned __int8)a9 == 68 )
    goto LABEL_62;
  if ( !(_BYTE)a9 )
  {
LABEL_60:
    v30 = 1;
    goto LABEL_63;
  }
  if ( (unsigned __int8)a9 == 10 || (unsigned __int8)a9 == 15 )
    goto LABEL_61;
  if ( (unsigned __int8)a9 == 17 )
  {
LABEL_17:
    v16 = 8;
    goto LABEL_18;
  }
  if ( (unsigned __int8)a9 != 34 )
  {
    v15 = (unsigned __int8)a9 == 51;
LABEL_16:
    if ( v15 )
      goto LABEL_17;
    goto LABEL_56;
  }
  v17 = 8;
  v30 = 8;
  if ( a2->iBitmapFormat != 1 )
    goto LABEL_63;
  if ( !a5
    && a4
    && (*(_BYTE *)(a4 + 4) & 2) != 0
    && ((v18 = *(ULONG **)(a4 + 16)) != 0 || (v18 = XLATEOBJ_piVector((XLATEOBJ *)a4), v17 = v30, v18))
    && *v18 == v18[1] )
  {
    v31 = (v17 & 4) != 0;
  }
  else
  {
    if ( !(unsigned int)B1bppBmpHasTransparentColor((XLATEOBJ *)a4, (__int64)v29) )
      goto LABEL_63;
    v17 = v30;
  }
  v16 = v17 | 0x10;
LABEL_18:
  v30 = v16;
LABEL_63:
  if ( !(unsigned int)SMChangeState((__int64)a1, 5) )
    return 2;
  if ( (v30 & 0xC) != 0 )
  {
    BCommonDIBBlt(a1, a2, a3, a4, a6, a7, 0, (__int64)v29, a10, 0);
  }
  else
  {
    if ( (v30 & 1) != 0 )
    {
      v19 = &v27;
      v28 = 0;
      v20 = _mm_cvtsi128_si32((__m128i)0LL);
      v27 = 0;
      if ( (unsigned __int8)a9 == 255 )
        v20 = 0xFFFFFF;
      a1[538] |= 0x100u;
      LODWORD(v27) = v20;
    }
    else
    {
      v19 = a5;
    }
    PSProcsetSend(a1, 16);
    if ( a7 && a10 )
    {
      v21 = a7[2];
      if ( *a7 >= v21 )
      {
        v25 = *a7;
        v23 = v21;
      }
      else
      {
        v23 = *a7;
        v25 = v21;
      }
      v22 = a7[3];
      if ( a7[1] >= v22 )
      {
        v26 = a7[1];
        v24 = v22;
      }
      else
      {
        v24 = a7[1];
        v26 = v22;
      }
      GSSendAttributes((__int64)a1, a4, 0, 0, a3, &v23);
    }
    else
    {
      GSSendAttributes((__int64)a1, a4, 0, 0, a3, a7);
    }
    GSSendGsave((__int64)a1);
    GBSendRect((__int64)a1, a7, 0);
    GBPatternFill((__int64)a1, (__int64)v19, a8, a9, 2);
    GSSendGrestore((__int64)a1);
    a1[538] &= ~0x100u;
  }
  return a1[860] != 0 ? 2 : 0;
}

```

## disassembly

```asm
0x1800074d0  push    rbp
0x1800074d2  push    rbx
0x1800074d3  push    rdi
0x1800074d4  push    r12
0x1800074d6  push    r14
0x1800074d8  push    r15
0x1800074da  lea     rbp, [rsp-7]
0x1800074df  sub     rsp, 0C8h
0x1800074e6  xor     eax, eax
0x1800074e8  xorps   xmm0, xmm0
0x1800074eb  mov     dword ptr [rbp+2Fh+var_80], eax
0x1800074ee  mov     r14, r9
0x1800074f1  mov     r12, r8
0x1800074f4  mov     r15, rdx
0x1800074f7  mov     rdi, rcx
0x1800074fa  movups  [rbp+2Fh+var_90], xmm0
0x1800074fe  test    rdx, rdx
0x180007501  jz      short loc_18000752B
0x180007503  cmp     dword ptr [rdx+48h], 9
0x180007507  jnz     short loc_18000752B
0x180007509  cmp     [rbp+2Fh+arg_40], 0CCCCh
0x180007510  jz      short loc_18000752B
0x180007512  lea     ecx, [rax+32h]; dwErrCode
0x180007515  call    cs:__imp_SetLastError
0x18000751c  nop     dword ptr [rax+rax+00h]
0x180007521  mov     eax, 2
0x180007526  jmp     loc_1800078B8
0x18000752b  movzx   ebx, byte ptr [rbp+2Fh+arg_40]
0x18000752f  lea     rcx, [rbp+2Fh+var_70]; void *
0x180007533  xor     edx, edx; Val
0x180007535  lea     r8d, [rdx+40h]; Size
0x180007539  call    memset_0
0x18000753e  mov     eax, 88h
0x180007543  mov     r8d, 1
0x180007549  cmp     ebx, eax
0x18000754b  ja      loc_180007688
0x180007551  jz      loc_18000765A
0x180007557  cmp     ebx, 44h ; 'D'
0x18000755a  ja      loc_180007625
0x180007560  jz      loc_18000774D
0x180007566  test    ebx, ebx
0x180007568  jz      loc_18000773E
0x18000756e  cmp     ebx, 0Ah
0x180007571  jz      loc_180007744
0x180007577  cmp     ebx, 0Fh
0x18000757a  jz      loc_180007744
0x180007580  cmp     ebx, 11h
0x180007583  jz      short loc_180007593
0x180007585  cmp     ebx, 22h ; '"'
0x180007588  jz      short loc_1800075A0
0x18000758a  cmp     ebx, 33h ; '3'
0x18000758d  jnz     loc_180007714
0x180007593  mov     edx, 8
0x180007598  mov     [rbp+2Fh+var_64], edx
0x18000759b  jmp     loc_180007754
0x1800075a0  mov     edx, 8
0x1800075a5  mov     [rbp+2Fh+var_64], edx
0x1800075a8  cmp     [r15+48h], r8d
0x1800075ac  jnz     loc_180007754
0x1800075b2  cmp     [rbp+2Fh+arg_20], 0
0x1800075b7  jnz     short loc_180007606
0x1800075b9  test    r14, r14
0x1800075bc  jz      short loc_180007606
0x1800075be  test    byte ptr [r14+4], 2
0x1800075c3  jz      short loc_180007606
0x1800075c5  mov     rax, [r14+10h]
0x1800075c9  test    rax, rax
0x1800075cc  jnz     short loc_1800075EB
0x1800075ce  mov     rcx, r14; pxlo
0x1800075d1  call    cs:__imp_XLATEOBJ_piVector
0x1800075d8  nop     dword ptr [rax+rax+00h]
0x1800075dd  mov     edx, [rbp+2Fh+var_64]
0x1800075e0  mov     r8d, 1
0x1800075e6  test    rax, rax
0x1800075e9  jz      short loc_180007606
0x1800075eb  mov     ecx, [rax+4]
0x1800075ee  cmp     [rax], ecx
0x1800075f0  jnz     short loc_180007606
0x1800075f2  test    dl, 4
0x1800075f5  jz      short loc_1800075FE
0x1800075f7  mov     [rbp+2Fh+var_34], r8w
0x1800075fc  jmp     short loc_18000761D
0x1800075fe  xor     eax, eax
0x180007600  mov     [rbp+2Fh+var_34], ax
0x180007604  jmp     short loc_18000761D
0x180007606  lea     rdx, [rbp+2Fh+var_70]
0x18000760a  mov     rcx, r14
0x18000760d  call    B1bppBmpHasTransparentColor
0x180007612  test    eax, eax
0x180007614  jz      loc_180007754
0x18000761a  mov     edx, [rbp+2Fh+var_64]
0x18000761d  or      edx, 10h
0x180007620  jmp     loc_180007598
0x180007625  cmp     ebx, 50h ; 'P'
0x180007628  jz      loc_180007744
0x18000762e  cmp     ebx, 55h ; 'U'
0x180007631  jz      loc_180007737
0x180007637  cmp     ebx, 5Ah ; 'Z'
0x18000763a  jz      loc_180007744
0x180007640  cmp     ebx, 5Fh ; '_'
0x180007643  jz      loc_180007744
0x180007649  cmp     ebx, 66h ; 'f'
0x18000764c  jz      loc_18000774D
0x180007652  cmp     ebx, 77h ; 'w'
0x180007655  jmp     loc_18000758D
0x18000765a  mov     [rbp+2Fh+var_64], 4
0x180007661  cmp     [r15+48h], r8d
0x180007665  jnz     loc_180007754
0x18000766b  lea     rdx, [rbp+2Fh+var_70]
0x18000766f  mov     rcx, r14
0x180007672  call    B1bppBmpHasTransparentColor
0x180007677  test    eax, eax
0x180007679  jz      loc_180007754
0x18000767f  or      [rbp+2Fh+var_64], 10h
0x180007683  jmp     loc_180007754
0x180007688  mov     eax, 0BBh
0x18000768d  cmp     ebx, eax
0x18000768f  ja      short loc_1800076F2
0x180007691  jz      loc_180007593
0x180007697  mov     eax, ebx
0x180007699  sub     eax, 99h
0x18000769e  jz      loc_180007593
0x1800076a4  sub     eax, 7
0x1800076a7  jz      loc_180007744
0x1800076ad  sub     eax, 5
0x1800076b0  jz      loc_180007744
0x1800076b6  sub     eax, 5
0x1800076b9  jz      short loc_180007737
0x1800076bb  sub     eax, 5
0x1800076be  jz      loc_180007744
0x1800076c4  cmp     eax, 9
0x1800076c7  jnz     short loc_180007714
0x1800076c9  mov     [rbp+2Fh+var_64], 4
0x1800076d0  cmp     [r15+48h], r8d
0x1800076d4  jnz     short loc_1800076EA
0x1800076d6  lea     rdx, [rbp+2Fh+var_70]
0x1800076da  mov     rcx, r14
0x1800076dd  call    B1bppBmpHasTransparentColor
0x1800076e2  test    eax, eax
0x1800076e4  jnz     short loc_18000767F
0x1800076e6  lea     r8d, [rax+1]
0x1800076ea  mov     eax, r8d
0x1800076ed  jmp     loc_1800078B8
0x1800076f2  mov     eax, ebx
0x1800076f4  sub     eax, 0CCh
0x1800076f9  jz      short loc_18000774D
0x1800076fb  sub     eax, 11h
0x1800076fe  jz      short loc_18000774D
0x180007700  sub     eax, 5
0x180007703  jz      short loc_1800076EA
0x180007705  sub     eax, 0Ch
0x180007708  jz      short loc_18000774D
0x18000770a  sub     eax, 2
0x18000770d  jz      short loc_180007744
0x18000770f  cmp     eax, 0Fh
0x180007712  jz      short loc_18000773E
0x180007714  mov     eax, ebx
0x180007716  shr     eax, 2
0x180007719  xor     eax, ebx
0x18000771b  test    al, 33h
0x18000771d  jnz     short loc_18000774D
0x18000771f  mov     ecx, ebx
0x180007721  mov     eax, ebx
0x180007723  and     ecx, 0Fh
0x180007726  shr     eax, 4
0x180007729  cmp     eax, ecx
0x18000772b  jnz     short loc_180007744
0x18000772d  mov     eax, ebx
0x18000772f  shr     eax, 1
0x180007731  xor     eax, ebx
0x180007733  test    al, 55h
0x180007735  jz      short loc_180007754
0x180007737  xor     eax, eax
0x180007739  jmp     loc_1800078B8
0x18000773e  mov     [rbp+2Fh+var_64], r8d
0x180007742  jmp     short loc_180007754
0x180007744  mov     [rbp+2Fh+var_64], 2
0x18000774b  jmp     short loc_180007754
0x18000774d  mov     [rbp+2Fh+var_64], 4
0x180007754  mov     edx, 5
0x180007759  mov     rcx, rdi
0x18000775c  call    SMChangeState
0x180007761  test    eax, eax
0x180007763  jz      loc_180007521
0x180007769  test    byte ptr [rbp+2Fh+var_64], 0Ch
0x18000776d  jz      short loc_1800077BC
0x18000776f  mov     eax, [rbp+2Fh+arg_48]
0x180007775  mov     r9, r14
0x180007778  mov     [rsp+0F0h+var_A8], 0; __int64
0x180007781  mov     r8, r12
0x180007784  mov     [rsp+0F0h+var_B0], eax; int
0x180007788  mov     rdx, r15
0x18000778b  lea     rax, [rbp+2Fh+var_70]
0x18000778f  mov     rcx, rdi; int
0x180007792  mov     qword ptr [rsp+0F0h+var_B8], rax; int
0x180007797  mov     rax, [rbp+2Fh+arg_30]
0x18000779b  mov     [rsp+0F0h+var_C0], 0; __int64
0x1800077a4  mov     [rsp+0F0h+var_C8], rax; __int64
0x1800077a9  mov     rax, [rbp+2Fh+arg_28]
0x1800077ad  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x1800077b2  call    BCommonDIBBlt
0x1800077b7  jmp     loc_1800078AB
0x1800077bc  test    byte ptr [rbp+2Fh+var_64], 1
0x1800077c0  jz      short loc_1800077F2
0x1800077c2  xor     eax, eax
0x1800077c4  lea     r15, [rbp+2Fh+var_90]
0x1800077c8  xorps   xmm0, xmm0
0x1800077cb  mov     [rbp+2Fh+var_80], rax
0x1800077cf  cmp     ebx, 0FFh
0x1800077d5  movd    eax, xmm0
0x1800077d9  mov     ecx, 0FFFFFFh
0x1800077de  movups  [rbp+2Fh+var_90], xmm0
0x1800077e2  cmovz   eax, ecx
0x1800077e5  bts     dword ptr [rdi+868h], 8
0x1800077ed  mov     dword ptr [rbp+2Fh+var_90], eax
0x1800077f0  jmp     short loc_1800077F6
0x1800077f2  mov     r15, [rbp+2Fh+arg_20]
0x1800077f6  mov     edx, 10h
0x1800077fb  mov     rcx, rdi
0x1800077fe  call    PSProcsetSend
0x180007803  mov     rbx, [rbp+2Fh+arg_30]
0x180007807  test    rbx, rbx
0x18000780a  jz      short loc_18000784F
0x18000780c  cmp     [rbp+2Fh+arg_48], 0
0x180007813  jz      short loc_18000784F
0x180007815  mov     eax, [rbx+8]
0x180007818  mov     ecx, [rbx]
0x18000781a  cmp     ecx, eax
0x18000781c  jge     short loc_180007826
0x18000781e  mov     [rbp+2Fh+var_A0], ecx
0x180007821  mov     [rbp+2Fh+var_98], eax
0x180007824  jmp     short loc_18000782C
0x180007826  mov     [rbp+2Fh+var_98], ecx
0x180007829  mov     [rbp+2Fh+var_A0], eax
0x18000782c  mov     eax, [rbx+0Ch]
0x18000782f  mov     ecx, [rbx+4]
0x180007832  cmp     ecx, eax
0x180007834  jge     short loc_18000783E
0x180007836  mov     [rbp+2Fh+var_9C], ecx
0x180007839  mov     [rbp+2Fh+var_94], eax
0x18000783c  jmp     short loc_180007844
0x18000783e  mov     [rbp+2Fh+var_94], ecx
0x180007841  mov     [rbp+2Fh+var_9C], eax
0x180007844  lea     rax, [rbp+2Fh+var_A0]
0x180007848  mov     [rsp+0F0h+var_C8], rax
0x18000784d  jmp     short loc_180007854
0x18000784f  mov     [rsp+0F0h+var_C8], rbx
0x180007854  xor     r9d, r9d
0x180007857  mov     qword ptr [rsp+0F0h+var_D0], r12
0x18000785c  xor     r8d, r8d
0x18000785f  mov     rdx, r14
0x180007862  mov     rcx, rdi
0x180007865  call    GSSendAttributes
0x18000786a  mov     rcx, rdi
0x18000786d  call    GSSendGsave
0x180007872  xor     r8d, r8d
0x180007875  mov     rdx, rbx
0x180007878  mov     rcx, rdi
0x18000787b  call    GBSendRect
0x180007880  mov     r9d, [rbp+2Fh+arg_40]
0x180007884  mov     rdx, r15
0x180007887  mov     r8, [rbp+2Fh+arg_38]
0x18000788b  mov     rcx, rdi
0x18000788e  mov     [rsp+0F0h+var_D0], 2
0x180007896  call    GBPatternFill
0x18000789b  mov     rcx, rdi
0x18000789e  call    GSSendGrestore
0x1800078a3  btr     dword ptr [rdi+868h], 8
0x1800078ab  mov     eax, [rdi+0D70h]
0x1800078b1  neg     eax
0x1800078b3  sbb     eax, eax
0x1800078b5  and     eax, 2
0x1800078b8  add     rsp, 0C8h
0x1800078bf  pop     r15
0x1800078c1  pop     r14
0x1800078c3  pop     r12
0x1800078c5  pop     rdi
0x1800078c6  pop     rbx
0x1800078c7  pop     rbp
0x1800078c8  retn
```
