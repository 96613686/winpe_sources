# DwCommonROPBlt

- ea: `0x180007378`
- end: `0x180007765`
- name: `DwCommonROPBlt`
- size: `1005`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, __int64, int, __int64, __int64, int, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180006560`
- `0x180006f80`

## callees

- `0x1800028d8`
- `0x180005a8c`
- `0x180005c48`
- `0x180007378`
- `0x180011c50`
- `0x18001241c`
- `0x18001247c`
- `0x18001283c`
- `0x180015f84`
- `0x180019094`
- `0x180019724`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800073bd`
- `KERNEL32!SetLastError` at `0x1800073bd`
- `GDI32!XLATEOBJ_piVector` at `0x180007473`
- `GDI32!XLATEOBJ_piVector` at `0x180007473`

## pseudocode

```c
__int64 __fastcall DwCommonROPBlt(
        _DWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int128 *a5,
        int *a6,
        int *a7,
        __int64 a8,
        unsigned int a9,
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
  if ( a2 && *(_DWORD *)(a2 + 72) == 9 && a9 != 52428 )
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
      if ( *(_DWORD *)(a2 + 72) == 1 && (unsigned int)B1bppBmpHasTransparentColor(a4, v29, 1) )
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
    if ( *(_DWORD *)(a2 + 72) != 1 || !(unsigned int)B1bppBmpHasTransparentColor(a4, v29, 1) )
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
  if ( *(_DWORD *)(a2 + 72) != 1 )
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
    if ( !(unsigned int)B1bppBmpHasTransparentColor(a4, v29, 1) )
      goto LABEL_63;
    v17 = v30;
  }
  v16 = v17 | 0x10;
LABEL_18:
  v30 = v16;
LABEL_63:
  if ( !(unsigned int)SMChangeState(a1, 5) )
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
      GSSendAttributes((_DWORD)a1, a4, 0, 0, a3, (__int64)&v23);
    }
    else
    {
      GSSendAttributes((_DWORD)a1, a4, 0, 0, a3, (__int64)a7);
    }
    GSSendGsave(a1);
    GBSendRect(a1, a7, 0);
    GBPatternFill(a1, v19, a8, a9, 2);
    GSSendGrestore(a1);
    a1[538] &= ~0x100u;
  }
  return a1[860] != 0 ? 2 : 0;
}

```

## disassembly

```asm
0x180007378  push    rbp
0x18000737a  push    rbx
0x18000737b  push    rdi
0x18000737c  push    r12
0x18000737e  push    r14
0x180007380  push    r15
0x180007382  lea     rbp, [rsp-7]
0x180007387  sub     rsp, 0C8h
0x18000738e  xor     eax, eax
0x180007390  xorps   xmm0, xmm0
0x180007393  mov     dword ptr [rbp+2Fh+var_80], eax
0x180007396  mov     r14, r9
0x180007399  mov     r12, r8
0x18000739c  mov     r15, rdx
0x18000739f  mov     rdi, rcx
0x1800073a2  movups  [rbp+2Fh+var_90], xmm0
0x1800073a6  test    rdx, rdx
0x1800073a9  jz      short loc_1800073CD
0x1800073ab  cmp     dword ptr [rdx+48h], 9
0x1800073af  jnz     short loc_1800073CD
0x1800073b1  cmp     [rbp+2Fh+arg_40], 0CCCCh
0x1800073b8  jz      short loc_1800073CD
0x1800073ba  lea     ecx, [rax+32h]; dwErrCode
0x1800073bd  call    cs:__imp_SetLastError
0x1800073c3  mov     eax, 2
0x1800073c8  jmp     loc_180007754
0x1800073cd  movzx   ebx, byte ptr [rbp+2Fh+arg_40]
0x1800073d1  lea     rcx, [rbp+2Fh+var_70]; void *
0x1800073d5  xor     edx, edx; Val
0x1800073d7  lea     r8d, [rdx+40h]; Size
0x1800073db  call    memset_0
0x1800073e0  mov     eax, 88h
0x1800073e5  mov     r8d, 1
0x1800073eb  cmp     ebx, eax
0x1800073ed  ja      loc_180007524
0x1800073f3  jz      loc_1800074F6
0x1800073f9  cmp     ebx, 44h ; 'D'
0x1800073fc  ja      loc_1800074C1
0x180007402  jz      loc_1800075E9
0x180007408  test    ebx, ebx
0x18000740a  jz      loc_1800075DA
0x180007410  cmp     ebx, 0Ah
0x180007413  jz      loc_1800075E0
0x180007419  cmp     ebx, 0Fh
0x18000741c  jz      loc_1800075E0
0x180007422  cmp     ebx, 11h
0x180007425  jz      short loc_180007435
0x180007427  cmp     ebx, 22h ; '"'
0x18000742a  jz      short loc_180007442
0x18000742c  cmp     ebx, 33h ; '3'
0x18000742f  jnz     loc_1800075B0
0x180007435  mov     edx, 8
0x18000743a  mov     [rbp+2Fh+var_64], edx
0x18000743d  jmp     loc_1800075F0
0x180007442  mov     edx, 8
0x180007447  mov     [rbp+2Fh+var_64], edx
0x18000744a  cmp     [r15+48h], r8d
0x18000744e  jnz     loc_1800075F0
0x180007454  cmp     [rbp+2Fh+arg_20], 0
0x180007459  jnz     short loc_1800074A2
0x18000745b  test    r14, r14
0x18000745e  jz      short loc_1800074A2
0x180007460  test    byte ptr [r14+4], 2
0x180007465  jz      short loc_1800074A2
0x180007467  mov     rax, [r14+10h]
0x18000746b  test    rax, rax
0x18000746e  jnz     short loc_180007487
0x180007470  mov     rcx, r14; pxlo
0x180007473  call    cs:__imp_XLATEOBJ_piVector
0x180007479  mov     edx, [rbp+2Fh+var_64]
0x18000747c  mov     r8d, 1
0x180007482  test    rax, rax
0x180007485  jz      short loc_1800074A2
0x180007487  mov     ecx, [rax+4]
0x18000748a  cmp     [rax], ecx
0x18000748c  jnz     short loc_1800074A2
0x18000748e  test    dl, 4
0x180007491  jz      short loc_18000749A
0x180007493  mov     [rbp+2Fh+var_34], r8w
0x180007498  jmp     short loc_1800074B9
0x18000749a  xor     eax, eax
0x18000749c  mov     [rbp+2Fh+var_34], ax
0x1800074a0  jmp     short loc_1800074B9
0x1800074a2  lea     rdx, [rbp+2Fh+var_70]
0x1800074a6  mov     rcx, r14
0x1800074a9  call    B1bppBmpHasTransparentColor
0x1800074ae  test    eax, eax
0x1800074b0  jz      loc_1800075F0
0x1800074b6  mov     edx, [rbp+2Fh+var_64]
0x1800074b9  or      edx, 10h
0x1800074bc  jmp     loc_18000743A
0x1800074c1  cmp     ebx, 50h ; 'P'
0x1800074c4  jz      loc_1800075E0
0x1800074ca  cmp     ebx, 55h ; 'U'
0x1800074cd  jz      loc_1800075D3
0x1800074d3  cmp     ebx, 5Ah ; 'Z'
0x1800074d6  jz      loc_1800075E0
0x1800074dc  cmp     ebx, 5Fh ; '_'
0x1800074df  jz      loc_1800075E0
0x1800074e5  cmp     ebx, 66h ; 'f'
0x1800074e8  jz      loc_1800075E9
0x1800074ee  cmp     ebx, 77h ; 'w'
0x1800074f1  jmp     loc_18000742F
0x1800074f6  mov     [rbp+2Fh+var_64], 4
0x1800074fd  cmp     [r15+48h], r8d
0x180007501  jnz     loc_1800075F0
0x180007507  lea     rdx, [rbp+2Fh+var_70]
0x18000750b  mov     rcx, r14
0x18000750e  call    B1bppBmpHasTransparentColor
0x180007513  test    eax, eax
0x180007515  jz      loc_1800075F0
0x18000751b  or      [rbp+2Fh+var_64], 10h
0x18000751f  jmp     loc_1800075F0
0x180007524  mov     eax, 0BBh
0x180007529  cmp     ebx, eax
0x18000752b  ja      short loc_18000758E
0x18000752d  jz      loc_180007435
0x180007533  mov     eax, ebx
0x180007535  sub     eax, 99h
0x18000753a  jz      loc_180007435
0x180007540  sub     eax, 7
0x180007543  jz      loc_1800075E0
0x180007549  sub     eax, 5
0x18000754c  jz      loc_1800075E0
0x180007552  sub     eax, 5
0x180007555  jz      short loc_1800075D3
0x180007557  sub     eax, 5
0x18000755a  jz      loc_1800075E0
0x180007560  cmp     eax, 9
0x180007563  jnz     short loc_1800075B0
0x180007565  mov     [rbp+2Fh+var_64], 4
0x18000756c  cmp     [r15+48h], r8d
0x180007570  jnz     short loc_180007586
0x180007572  lea     rdx, [rbp+2Fh+var_70]
0x180007576  mov     rcx, r14
0x180007579  call    B1bppBmpHasTransparentColor
0x18000757e  test    eax, eax
0x180007580  jnz     short loc_18000751B
0x180007582  lea     r8d, [rax+1]
0x180007586  mov     eax, r8d
0x180007589  jmp     loc_180007754
0x18000758e  mov     eax, ebx
0x180007590  sub     eax, 0CCh
0x180007595  jz      short loc_1800075E9
0x180007597  sub     eax, 11h
0x18000759a  jz      short loc_1800075E9
0x18000759c  sub     eax, 5
0x18000759f  jz      short loc_180007586
0x1800075a1  sub     eax, 0Ch
0x1800075a4  jz      short loc_1800075E9
0x1800075a6  sub     eax, 2
0x1800075a9  jz      short loc_1800075E0
0x1800075ab  cmp     eax, 0Fh
0x1800075ae  jz      short loc_1800075DA
0x1800075b0  mov     eax, ebx
0x1800075b2  shr     eax, 2
0x1800075b5  xor     eax, ebx
0x1800075b7  test    al, 33h
0x1800075b9  jnz     short loc_1800075E9
0x1800075bb  mov     ecx, ebx
0x1800075bd  mov     eax, ebx
0x1800075bf  and     ecx, 0Fh
0x1800075c2  shr     eax, 4
0x1800075c5  cmp     eax, ecx
0x1800075c7  jnz     short loc_1800075E0
0x1800075c9  mov     eax, ebx
0x1800075cb  shr     eax, 1
0x1800075cd  xor     eax, ebx
0x1800075cf  test    al, 55h
0x1800075d1  jz      short loc_1800075F0
0x1800075d3  xor     eax, eax
0x1800075d5  jmp     loc_180007754
0x1800075da  mov     [rbp+2Fh+var_64], r8d
0x1800075de  jmp     short loc_1800075F0
0x1800075e0  mov     [rbp+2Fh+var_64], 2
0x1800075e7  jmp     short loc_1800075F0
0x1800075e9  mov     [rbp+2Fh+var_64], 4
0x1800075f0  mov     edx, 5
0x1800075f5  mov     rcx, rdi
0x1800075f8  call    SMChangeState
0x1800075fd  test    eax, eax
0x1800075ff  jz      loc_1800073C3
0x180007605  test    byte ptr [rbp+2Fh+var_64], 0Ch
0x180007609  jz      short loc_180007658
0x18000760b  mov     eax, [rbp+2Fh+arg_48]
0x180007611  mov     r9, r14
0x180007614  mov     [rsp+0F0h+var_A8], 0; __int64
0x18000761d  mov     r8, r12
0x180007620  mov     [rsp+0F0h+var_B0], eax; int
0x180007624  mov     rdx, r15
0x180007627  lea     rax, [rbp+2Fh+var_70]
0x18000762b  mov     rcx, rdi; int
0x18000762e  mov     qword ptr [rsp+0F0h+var_B8], rax; int
0x180007633  mov     rax, [rbp+2Fh+arg_30]
0x180007637  mov     [rsp+0F0h+var_C0], 0; __int64
0x180007640  mov     [rsp+0F0h+var_C8], rax; __int64
0x180007645  mov     rax, [rbp+2Fh+arg_28]
0x180007649  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x18000764e  call    BCommonDIBBlt
0x180007653  jmp     loc_180007747
0x180007658  test    byte ptr [rbp+2Fh+var_64], 1
0x18000765c  jz      short loc_18000768E
0x18000765e  xor     eax, eax
0x180007660  lea     r15, [rbp+2Fh+var_90]
0x180007664  xorps   xmm0, xmm0
0x180007667  mov     [rbp+2Fh+var_80], rax
0x18000766b  cmp     ebx, 0FFh
0x180007671  movd    eax, xmm0
0x180007675  mov     ecx, 0FFFFFFh
0x18000767a  movups  [rbp+2Fh+var_90], xmm0
0x18000767e  cmovz   eax, ecx
0x180007681  bts     dword ptr [rdi+868h], 8
0x180007689  mov     dword ptr [rbp+2Fh+var_90], eax
0x18000768c  jmp     short loc_180007692
0x18000768e  mov     r15, [rbp+2Fh+arg_20]
0x180007692  mov     edx, 10h
0x180007697  mov     rcx, rdi
0x18000769a  call    PSProcsetSend
0x18000769f  mov     rbx, [rbp+2Fh+arg_30]
0x1800076a3  test    rbx, rbx
0x1800076a6  jz      short loc_1800076EB
0x1800076a8  cmp     [rbp+2Fh+arg_48], 0
0x1800076af  jz      short loc_1800076EB
0x1800076b1  mov     eax, [rbx+8]
0x1800076b4  mov     ecx, [rbx]
0x1800076b6  cmp     ecx, eax
0x1800076b8  jge     short loc_1800076C2
0x1800076ba  mov     [rbp+2Fh+var_A0], ecx
0x1800076bd  mov     [rbp+2Fh+var_98], eax
0x1800076c0  jmp     short loc_1800076C8
0x1800076c2  mov     [rbp+2Fh+var_98], ecx
0x1800076c5  mov     [rbp+2Fh+var_A0], eax
0x1800076c8  mov     eax, [rbx+0Ch]
0x1800076cb  mov     ecx, [rbx+4]
0x1800076ce  cmp     ecx, eax
0x1800076d0  jge     short loc_1800076DA
0x1800076d2  mov     [rbp+2Fh+var_9C], ecx
0x1800076d5  mov     [rbp+2Fh+var_94], eax
0x1800076d8  jmp     short loc_1800076E0
0x1800076da  mov     [rbp+2Fh+var_94], ecx
0x1800076dd  mov     [rbp+2Fh+var_9C], eax
0x1800076e0  lea     rax, [rbp+2Fh+var_A0]
0x1800076e4  mov     [rsp+0F0h+var_C8], rax
0x1800076e9  jmp     short loc_1800076F0
0x1800076eb  mov     [rsp+0F0h+var_C8], rbx
0x1800076f0  xor     r9d, r9d
0x1800076f3  mov     qword ptr [rsp+0F0h+var_D0], r12
0x1800076f8  xor     r8d, r8d
0x1800076fb  mov     rdx, r14
0x1800076fe  mov     rcx, rdi
0x180007701  call    GSSendAttributes
0x180007706  mov     rcx, rdi
0x180007709  call    GSSendGsave
0x18000770e  xor     r8d, r8d
0x180007711  mov     rdx, rbx
0x180007714  mov     rcx, rdi
0x180007717  call    GBSendRect
0x18000771c  mov     r9d, [rbp+2Fh+arg_40]
0x180007720  mov     rdx, r15
0x180007723  mov     r8, [rbp+2Fh+arg_38]
0x180007727  mov     rcx, rdi
0x18000772a  mov     [rsp+0F0h+var_D0], 2
0x180007732  call    GBPatternFill
0x180007737  mov     rcx, rdi
0x18000773a  call    GSSendGrestore
0x18000773f  btr     dword ptr [rdi+868h], 8
0x180007747  mov     eax, [rdi+0D70h]
0x18000774d  neg     eax
0x18000774f  sbb     eax, eax
0x180007751  and     eax, 2
0x180007754  add     rsp, 0C8h
0x18000775b  pop     r15
0x18000775d  pop     r14
0x18000775f  pop     r12
0x180007761  pop     rdi
0x180007762  pop     rbx
0x180007763  pop     rbp
0x180007764  retn
```
