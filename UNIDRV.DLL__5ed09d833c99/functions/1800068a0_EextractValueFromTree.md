# EextractValueFromTree

- ea: `0x1800068a0`
- end: `0x18000714a`
- name: `EextractValueFromTree`
- size: `2218`
- prototype: `__int64 __fastcall(_QWORD *, unsigned int, int *, __int64, int *, unsigned int, __int64, unsigned int Src, unsigned int *)`
- caller_count: `10`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180004a90`
- `0x180004df0`
- `0x180004f20`
- `0x180005020`
- `0x180005420`
- `0x180005544`
- `0x180005b20`
- `0x1800063d0`
- `0x1800071a0`
- `0x180007320`

## callees

- `0x1800068a0`
- `0x180007150`
- `0x180076660`

## string_xrefs

- `0x180006ced`: `Critical: VtransferValue: Data to copy not found in heap.  Value not copied`
- `0x18000707f`: `Critical: VtransferValue: Data to copy not found in heap.`

## pseudocode

```c
__int64 __fastcall EextractValueFromTree(
        _QWORD *a1,
        unsigned int a2,
        int *a3,
        __int64 a4,
        int *a5,
        int a6,
        __int64 a7,
        unsigned int Src,
        unsigned int *a9)
{
  unsigned int v9; // r11d
  int *v10; // r15
  unsigned __int64 v12; // rdi
  _QWORD *v13; // r14
  unsigned int v14; // esi
  __int64 v15; // rdx
  int v16; // ebx
  unsigned int v17; // r12d
  __int64 result; // rax
  int v20; // r13d
  int *v21; // rbp
  unsigned int v22; // ecx
  int v23; // r9d
  __int64 v24; // rax
  int v25; // eax
  int v26; // eax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rcx
  unsigned int v30; // edi
  unsigned int *p_Src; // r14
  unsigned int v32; // ebp
  int *v33; // r9
  unsigned int v34; // edx
  __int64 v35; // rcx
  unsigned int v36; // edi
  unsigned int *v37; // r14
  unsigned int v38; // ebp
  int *v39; // r9
  unsigned int v40; // edx
  unsigned __int64 v41; // rcx
  int *v42; // rdi
  unsigned int v43; // r9d
  unsigned int v44; // r9d
  unsigned __int64 v45; // rcx
  unsigned int *v46; // rdi
  __int64 v47; // rax
  int v48; // edx
  int v49; // edx
  unsigned int v50; // r9d
  __int64 v51; // rax
  int v52; // edi
  int v53; // edi
  unsigned int v54; // r11d
  unsigned int v55; // [rsp+20h] [rbp-38h]
  __int64 v56; // [rsp+28h] [rbp-30h] BYREF

  v9 = Src;
  v10 = a3;
  if ( Src >= 0x200 )
    return 0;
  v12 = *(unsigned int *)(a1[12] + 4LL) * (unsigned __int64)*(unsigned int *)(a1[12] + 8LL);
  if ( v12 > 0xFFFFFFFF )
  {
    WriteDbgTraceErrorGpd((__int64)"EextractValueFromTree", "EextractValueFromTree: Unexpected: String heap too large.");
    return 0;
  }
  v13 = (_QWORD *)(a1[22] + 32LL * a2);
  v14 = *((_DWORD *)v13 + 3);
  if ( v14 > (unsigned int)a4 )
  {
    WriteDbgTraceErrorGpd(
      (__int64)"EextractValueFromTree",
      "EextractValueFromTree: Destination too small to hold data.");
    return 0;
  }
  v15 = (unsigned int)a6;
  v16 = *((_DWORD *)v13 + 6);
  v17 = *((_DWORD *)v13 + 2);
  if ( a6 == 0x7FFFFFFF )
  {
    if ( (v16 & 0x40000) != 0 )
    {
      if ( v14 == 4 )
      {
        *a3 &= ~v17;
        goto LABEL_8;
      }
LABEL_154:
      WriteDbgTraceErrorGpd((__int64)"EsetDefault", "EsetDefault: Bit fields must be size DWORD");
      return 3;
    }
    if ( (v16 & 0x80000) != 0 )
    {
      if ( v14 != 4 )
        goto LABEL_154;
      *a3 |= v17;
    }
    else if ( (v16 & 2) == 0 )
    {
      Src = *((_DWORD *)v13 + 2);
      v33 = a3;
      v34 = v14;
      if ( v14 > 4 )
      {
        v41 = (unsigned __int64)(v14 - 1) >> 2;
        v42 = a3;
        while ( v41 )
        {
          *v42++ = v17;
          --v41;
        }
        do
        {
          ++v33;
          v34 -= 4;
        }
        while ( v34 > 4 );
      }
      if ( v34 )
        memcpy_0(v33, &Src, v34);
    }
LABEL_8:
    if ( (v16 & 1) != 0 )
    {
      WriteDbgTraceErrorGpd(
        (__int64)"EsetDefault",
        "EsetDefault: a required keyword is missing from the GPD file. %s",
        *v13);
    }
    else
    {
      if ( (v16 & 0x20) == 0 )
        return (v16 & 0x200 | 0x100u) >> 8;
      v43 = 0;
      if ( v14 )
      {
        while ( !*((_BYTE *)v10 + v43) )
        {
          if ( ++v43 >= v14 )
            goto LABEL_108;
        }
        return (v16 & 0x200 | 0x100u) >> 8;
      }
LABEL_108:
      if ( v43 != v14 )
        return (v16 & 0x200 | 0x100u) >> 8;
      WriteDbgTraceErrorGpd(
        (__int64)"EsetDefault",
        "EextractValueFromTree: None of several initializers found.  %s",
        *v13);
    }
    return 3;
  }
  if ( a6 >= 0 )
  {
    a3 = (int *)a1[18];
    if ( a3[5 * a6] == -1 )
    {
      v55 = a6;
      LODWORD(v15) = a3[5 * a6 + 2];
    }
    else
    {
      v55 = -1;
    }
    a4 = 0;
    while ( 1 )
    {
      if ( (_DWORD)v15 == -1 )
        goto LABEL_55;
      v20 = a3[5 * (unsigned int)v15];
      v21 = &a3[5 * (unsigned int)v15];
      v22 = v20;
      if ( v20 == v9 )
      {
        LODWORD(v56) = 0;
        v44 = *a9;
        if ( *a9 )
        {
          v54 = v56;
          do
          {
            if ( !*(_BYTE *)(a7 + 2LL * v22 + 1) )
              break;
            ++v54;
            v22 = *(unsigned __int8 *)(a7 + 2LL * v22 + 1);
          }
          while ( v54 < v44 );
          a3 = (int *)a1[18];
        }
        v9 = Src;
        if ( *(_BYTE *)(a7 + 2LL * v22 + 1) )
          *a9 = v44 + 1;
        else
          *a9 = 0;
      }
      v23 = *(unsigned __int8 *)(a7 + 2LL * v22);
      if ( v23 == 255 )
      {
        *a5 = v20;
        return 2;
      }
      if ( v23 == 254 )
      {
        WriteDbgTraceErrorGpd(
          (__int64)"EextractValueFromTree",
          "EextractValueFromTree: Fatal syntax error, circular dependency in default options.");
        return 0;
      }
      if ( v21[1] != v23 )
      {
        do
        {
          v24 = (unsigned int)a3[5 * (unsigned int)v15 + 2];
          if ( (_DWORD)v24 == -1 )
            break;
          LODWORD(v15) = a3[5 * (unsigned int)v15 + 2];
        }
        while ( a3[5 * v24 + 1] != v23 );
      }
      v25 = a3[5 * (unsigned int)v15 + 1];
      if ( v25 != v23 && v25 != -1 )
        break;
      v26 = a3[5 * (unsigned int)v15 + 4];
      a4 = 0;
      if ( v26 == 1 )
      {
        v27 = (unsigned int)v15;
        goto LABEL_28;
      }
      if ( v26 )
        goto LABEL_55;
      LODWORD(v15) = a3[5 * (unsigned int)v15 + 3];
    }
    a4 = 0;
LABEL_55:
    v27 = v55;
LABEL_28:
    if ( (_DWORD)v27 != -1 && a3[5 * v27 + 4] == 1 )
    {
      v28 = (unsigned int)a3[5 * v27 + 3];
      v29 = a1[16];
      v30 = v12 - v28;
      Src = v28;
      if ( (v16 & 0xC0000) == 0 )
      {
        v56 = 0;
        if ( (v16 & 0x100) != 0 )
        {
          p_Src = &Src;
          Src = v28 & 0x7FFFFFFF;
          goto LABEL_58;
        }
        p_Src = (unsigned int *)(v29 + v28);
        if ( (v16 & 0x40) != 0 )
        {
          if ( v30 < 4 )
            goto LABEL_123;
          v30 -= 4;
          v32 = 4;
          ++p_Src;
        }
        else if ( (v16 & 8) != 0 )
        {
          if ( v30 < 8 )
            goto LABEL_123;
          v32 = 8;
          v47 = v29 + p_Src[1];
          p_Src = (unsigned int *)&v56;
          v56 = v47;
          v30 = 8;
        }
        else
        {
          if ( (v16 & 4) != 0 )
          {
            if ( v30 < 8 )
              goto LABEL_123;
            ++p_Src;
          }
          else
          {
            if ( (v16 & 0x1000) == 0 )
            {
              v32 = v14;
              goto LABEL_37;
            }
            if ( v30 < 8 )
            {
LABEL_123:
              WriteDbgTraceErrorGpd(
                (__int64)"VtransferValue",
                "Critical: VtransferValue: Data to be copied exceeds heap size",
                a3,
                0,
                v55,
                v56);
              return 1;
            }
          }
LABEL_58:
          v32 = 4;
        }
        if ( v32 != v14 )
        {
          WriteDbgTraceErrorGpd(
            (__int64)"VtransferValue",
            "VtransferValue: Snapshot table contains invalid data size.",
            a3,
            0);
          if ( v14 < v32 )
            return 1;
        }
LABEL_37:
        if ( v30 >= v32 && v30 >= v14 )
        {
          memcpy_0(v10, p_Src, v32);
          if ( v14 == 4 )
          {
            if ( (v16 & 0x80u) != 0 )
            {
              *v10 <<= 10;
            }
            else if ( (v16 & 0x800) != 0 )
            {
              *v10 <<= 20;
            }
            if ( (v16 & 0x10) != 0 )
              *v10 |= 0x80000000;
          }
          return 1;
        }
LABEL_84:
        WriteDbgTraceErrorGpd(
          (__int64)"VtransferValue",
          "Critical: VtransferValue: Data to copy not found in heap.  Value not copied",
          a3,
          a4,
          v55,
          v56);
        return 1;
      }
      if ( v14 == 4 && v30 >= 4 )
      {
        v48 = *v10;
        if ( *(_DWORD *)(v28 + v29) )
          v49 = v17 | v48;
        else
          v49 = ~v17 & v48;
        result = 1;
        *v10 = v49;
        return result;
      }
LABEL_157:
      WriteDbgTraceErrorGpd(
        (__int64)"VtransferValue",
        "Critical: VtransferValue: Data to copy not found in heap.",
        a3,
        a4,
        v55,
        v56);
      return 1;
    }
    if ( (v16 & 0x40000) != 0 )
    {
      if ( v14 == 4 )
      {
        *v10 &= ~v17;
        goto LABEL_65;
      }
LABEL_161:
      WriteDbgTraceErrorGpd((__int64)"EsetDefault", "EsetDefault: Bit fields must be size DWORD", a3, 0, v55);
      return 3;
    }
    if ( (v16 & 0x80000) != 0 )
    {
      if ( v14 != 4 )
        goto LABEL_161;
      *v10 |= v17;
    }
    else if ( (v16 & 2) == 0 )
    {
      Src = v17;
      v39 = v10;
      v40 = v14;
      if ( v14 > 4 )
      {
        v45 = (unsigned __int64)(v14 - 1) >> 2;
        v46 = (unsigned int *)v10;
        while ( v45 )
        {
          *v46++ = v17;
          --v45;
        }
        do
        {
          ++v39;
          v40 -= 4;
        }
        while ( v40 > 4 );
      }
      if ( v40 )
        memcpy_0(v39, &Src, v40);
    }
LABEL_65:
    if ( (v16 & 1) != 0 )
    {
      WriteDbgTraceErrorGpd(
        (__int64)"EsetDefault",
        "EsetDefault: a required keyword is missing from the GPD file. %s",
        *v13);
    }
    else
    {
      if ( (v16 & 0x20) == 0 )
        return (v16 & 0x200 | 0x100u) >> 8;
      v50 = 0;
      if ( v14 )
      {
        while ( !*((_BYTE *)v10 + v50) )
        {
          if ( ++v50 >= v14 )
            goto LABEL_134;
        }
        return (v16 & 0x200 | 0x100u) >> 8;
      }
LABEL_134:
      if ( v50 != v14 )
        return (v16 & 0x200 | 0x100u) >> 8;
      WriteDbgTraceErrorGpd(
        (__int64)"EsetDefault",
        "EextractValueFromTree: None of several initializers found.  %s",
        *v13);
    }
    return 3;
  }
  v35 = a1[16];
  LODWORD(v15) = a6 & 0x7FFFFFFF;
  v36 = v12 - (a6 & 0x7FFFFFFF);
  Src = a6 & 0x7FFFFFFF;
  if ( (v16 & 0xC0000) == 0 )
  {
    a4 = 0;
    v56 = 0;
    if ( (v16 & 0x100) == 0 )
    {
      v37 = (unsigned int *)(v35 + (unsigned int)v15);
      if ( (v16 & 0x40) != 0 )
      {
        if ( v36 < 4 )
          goto LABEL_123;
        v36 -= 4;
        v38 = 4;
        ++v37;
      }
      else
      {
        if ( (v16 & 8) == 0 )
        {
          if ( (v16 & 4) != 0 )
          {
            if ( v36 < 8 )
              goto LABEL_123;
            ++v37;
          }
          else
          {
            if ( (v16 & 0x1000) == 0 )
            {
              v38 = v14;
LABEL_75:
              if ( v36 < v38 || v36 < v14 )
                goto LABEL_84;
              memcpy_0(v10, v37, v38);
              if ( v14 != 4 )
                return 1;
              if ( (v16 & 0x80u) != 0 )
              {
                *v10 <<= 10;
              }
              else if ( (v16 & 0x800) != 0 )
              {
                *v10 <<= 20;
              }
              if ( (v16 & 0x10) == 0 )
                return 1;
              *v10 |= 0x80000000;
              return 1;
            }
            if ( v36 < 8 )
              goto LABEL_123;
          }
          goto LABEL_101;
        }
        if ( v36 < 8 )
          goto LABEL_123;
        v38 = 8;
        v51 = v35 + v37[1];
        v37 = (unsigned int *)&v56;
        v56 = v51;
        v36 = 8;
      }
LABEL_102:
      if ( v38 != v14 )
      {
        WriteDbgTraceErrorGpd((__int64)"VtransferValue", "VtransferValue: Snapshot table contains invalid data size.");
        if ( v14 < v38 )
          return 1;
      }
      goto LABEL_75;
    }
    v37 = &Src;
LABEL_101:
    v38 = 4;
    goto LABEL_102;
  }
  if ( v14 != 4 || v36 < 4 )
    goto LABEL_157;
  v52 = *a3;
  if ( *(_DWORD *)(v15 + v35) )
    v53 = v17 | v52;
  else
    v53 = ~v17 & v52;
  result = 1;
  *a3 = v53;
  return result;
}

```

## disassembly

```asm
0x1800068a0  push    r15
0x1800068a2  sub     rsp, 50h
0x1800068a6  mov     r11d, [rsp+58h+Src]
0x1800068ae  mov     r15, r8
0x1800068b1  mov     r10, rcx
0x1800068b4  cmp     r11d, 200h
0x1800068bb  jnb     loc_180006B46
0x1800068c1  mov     rax, [rcx+60h]
0x1800068c5  mov     [rsp+58h+arg_8], rbp
0x1800068ca  mov     ebp, 0FFFFFFFFh
0x1800068cf  mov     [rsp+58h+var_10], rdi
0x1800068d4  mov     edi, [rax+8]
0x1800068d7  mov     eax, [rax+4]
0x1800068da  imul    rdi, rax
0x1800068de  cmp     rdi, rbp
0x1800068e1  ja      loc_180006991
0x1800068e7  mov     [rsp+58h+arg_10], rsi
0x1800068ec  mov     [rsp+58h+var_28], r14
0x1800068f1  mov     r14d, edx
0x1800068f4  shl     r14, 5
0x1800068f8  add     r14, [rcx+0B0h]
0x1800068ff  mov     esi, [r14+0Ch]
0x180006903  cmp     esi, r9d
0x180006906  ja      loc_180007065
0x18000690c  mov     edx, [rsp+58h+arg_28]
0x180006913  mov     [rsp+58h+arg_0], rbx
0x180006918  mov     ebx, [r14+18h]
0x18000691c  mov     [rsp+58h+var_18], r12
0x180006921  mov     r12d, [r14+8]
0x180006925  cmp     edx, 7FFFFFFFh
0x18000692b  jnz     loc_1800069B8
0x180006931  bt      ebx, 12h
0x180006935  jnb     loc_180006B50
0x18000693b  cmp     esi, 4
0x18000693e  jnz     loc_18000703D
0x180006944  not     r12d
0x180006947  and     [r8], r12d
0x18000694a  test    bl, 1
0x18000694d  jnz     loc_180007006
0x180006953  test    bl, 20h
0x180006956  jnz     loc_180006DDD
0x18000695c  and     ebx, 200h
0x180006962  bts     ebx, 8
0x180006966  shr     ebx, 8
0x180006969  mov     eax, ebx
0x18000696b  mov     r12, [rsp+58h+var_18]
0x180006970  mov     rbx, [rsp+58h+arg_0]
0x180006975  mov     rsi, [rsp+58h+arg_10]
0x18000697a  mov     r14, [rsp+58h+var_28]
0x18000697f  mov     rbp, [rsp+58h+arg_8]
0x180006984  mov     rdi, [rsp+58h+var_10]
0x180006989  add     rsp, 50h
0x18000698d  pop     r15
0x18000698f  retn
0x180006991  lea     rdx, aEextractvaluef; "EextractValueFromTree: Unexpected: Stri"...
0x180006998  lea     rcx, aEextractvaluef_0; "EextractValueFromTree"
0x18000699f  call    WriteDbgTraceErrorGpd
0x1800069a4  mov     rbp, [rsp+58h+arg_8]
0x1800069a9  xor     eax, eax
0x1800069ab  mov     rdi, [rsp+58h+var_10]
0x1800069b0  add     rsp, 50h
0x1800069b4  pop     r15
0x1800069b6  retn
0x1800069b8  mov     [rsp+58h+var_20], r13
0x1800069bd  test    edx, edx
0x1800069bf  js      loc_180006C35
0x1800069c5  mov     r8, [rcx+90h]
0x1800069cc  lea     rcx, [rdx+rdx*4]
0x1800069d0  cmp     [r8+rcx*4], ebp
0x1800069d4  jz      loc_180007026
0x1800069da  mov     [rsp+58h+var_38], ebp
0x1800069de  xor     r9d, r9d
0x1800069e1  cmp     edx, ebp
0x1800069e3  jz      loc_180006BA4
0x1800069e9  mov     eax, edx
0x1800069eb  lea     rcx, [rax+rax*4]
0x1800069ef  mov     r13d, [r8+rcx*4]
0x1800069f3  lea     rbp, [r8+rcx*4]
0x1800069f7  mov     ecx, r13d
0x1800069fa  cmp     r13d, r11d
0x1800069fd  jz      loc_180006E0F
0x180006a03  mov     eax, ecx
0x180006a05  mov     rcx, [rsp+58h+arg_30]
0x180006a0d  movzx   r9d, byte ptr [rcx+rax*2]
0x180006a12  cmp     r9d, 0FFh
0x180006a19  jz      loc_180006F4D
0x180006a1f  cmp     r9d, 0FEh
0x180006a26  jz      loc_18000711F
0x180006a2c  cmp     [rbp+4], r9d
0x180006a30  mov     ebp, 0FFFFFFFFh
0x180006a35  jz      short loc_180006A5C
0x180006a37  nop     word ptr [rax+rax+00000000h]
0x180006a40  mov     eax, edx
0x180006a42  lea     rcx, [rax+rax*4]
0x180006a46  mov     eax, [r8+rcx*4+8]
0x180006a4b  cmp     eax, ebp
0x180006a4d  jz      short loc_180006A5C
0x180006a4f  lea     rcx, [rax+rax*4]
0x180006a53  mov     edx, eax
0x180006a55  cmp     [r8+rcx*4+4], r9d
0x180006a5a  jnz     short loc_180006A40
0x180006a5c  mov     eax, edx
0x180006a5e  lea     rcx, [rax+rax*4]
0x180006a62  mov     eax, [r8+rcx*4+4]
0x180006a67  cmp     eax, r9d
0x180006a6a  jnz     loc_180006B99
0x180006a70  mov     eax, [r8+rcx*4+10h]
0x180006a75  xor     r9d, r9d
0x180006a78  cmp     eax, 1
0x180006a7b  jnz     loc_180006D05
0x180006a81  mov     eax, edx
0x180006a83  cmp     eax, ebp
0x180006a85  jz      loc_180006BF1
0x180006a8b  lea     rcx, [rax+rax*4]
0x180006a8f  cmp     dword ptr [r8+rcx*4+10h], 1
0x180006a95  jnz     loc_180006BF1
0x180006a9b  mov     eax, [r8+rcx*4+0Ch]
0x180006aa0  mov     rcx, [r10+80h]
0x180006aa7  sub     edi, eax
0x180006aa9  mov     [rsp+58h+Src], eax
0x180006ab0  test    ebx, 0C0000h
0x180006ab6  jnz     loc_180006EE8
0x180006abc  mov     [rsp+58h+var_30], r9
0x180006ac1  bt      ebx, 8
0x180006ac5  jb      loc_180006D81
0x180006acb  lea     r14, [rcx+rax]
0x180006acf  test    bl, 40h
0x180006ad2  jnz     loc_180006E90
0x180006ad8  test    bl, 8
0x180006adb  jnz     loc_180006EC6
0x180006ae1  test    bl, 4
0x180006ae4  jnz     loc_180006BAD
0x180006aea  bt      ebx, 0Ch
0x180006aee  jb      loc_180006EA5
0x180006af4  mov     ebp, esi
0x180006af6  cmp     edi, ebp
0x180006af8  jb      loc_180006CED
0x180006afe  cmp     edi, esi
0x180006b00  jb      loc_180006CED
0x180006b06  mov     r8d, ebp; Size
0x180006b09  mov     rdx, r14; Src
0x180006b0c  mov     rcx, r15; void *
0x180006b0f  call    memcpy_0
0x180006b14  cmp     esi, 4
0x180006b17  jnz     short loc_180006B37
0x180006b19  test    bl, bl
0x180006b1b  js      loc_180006CE4
0x180006b21  bt      ebx, 0Bh
0x180006b25  jb      loc_180007139
0x180006b2b  test    bl, 10h
0x180006b2e  jz      short loc_180006B37
0x180006b30  or      dword ptr [r15], 80000000h
0x180006b37  mov     eax, 1
0x180006b3c  mov     r13, [rsp+58h+var_20]
0x180006b41  jmp     loc_18000696B
0x180006b46  xor     eax, eax
0x180006b48  add     rsp, 50h
0x180006b4c  pop     r15
0x180006b4e  retn
0x180006b50  bt      ebx, 13h
0x180006b54  jb      loc_180007034
0x180006b5a  test    bl, 2
0x180006b5d  jnz     loc_18000694A
0x180006b63  mov     [rsp+58h+Src], r12d
0x180006b6b  mov     r9, r15
0x180006b6e  mov     edx, esi
0x180006b70  cmp     esi, 4
0x180006b73  ja      loc_180006D60
0x180006b79  test    edx, edx
0x180006b7b  jz      loc_18000694A
0x180006b81  mov     r8d, edx; Size
0x180006b84  mov     rcx, r9; void *
0x180006b87  lea     rdx, [rsp+58h+Src]; Src
0x180006b8f  call    memcpy_0
0x180006b94  jmp     loc_18000694A
0x180006b99  cmp     eax, ebp
0x180006b9b  jz      loc_180006A70
0x180006ba1  xor     r9d, r9d
0x180006ba4  mov     eax, [rsp+58h+var_38]
0x180006ba8  jmp     loc_180006A83
0x180006bad  cmp     edi, 8
0x180006bb0  jb      loc_180006EAE
0x180006bb6  add     r14, 4
0x180006bba  mov     ebp, 4
0x180006bbf  cmp     ebp, esi
0x180006bc1  jz      loc_180006AF6
0x180006bc7  lea     rdx, aVtransfervalue_0; "VtransferValue: Snapshot table contains"...
0x180006bce  lea     rcx, aVtransfervalue; "VtransferValue"
0x180006bd5  call    WriteDbgTraceErrorGpd
0x180006bda  cmp     esi, ebp
0x180006bdc  jnb     loc_180006AF6
0x180006be2  mov     r13, [rsp+58h+var_20]
0x180006be7  mov     eax, 1
0x180006bec  jmp     loc_18000696B
0x180006bf1  bt      ebx, 12h
0x180006bf5  jnb     loc_180006D17
0x180006bfb  cmp     esi, 4
0x180006bfe  jnz     loc_1800070BB
0x180006c04  not     r12d
0x180006c07  and     [r15], r12d
0x180006c0a  test    bl, 1
0x180006c0d  jnz     loc_18000708B
0x180006c13  test    bl, 20h
0x180006c16  jnz     loc_180006F1B
0x180006c1c  mov     r13, [rsp+58h+var_20]
0x180006c21  and     ebx, 200h
0x180006c27  bts     ebx, 8
0x180006c2b  shr     ebx, 8
0x180006c2e  mov     eax, ebx
0x180006c30  jmp     loc_18000696B
0x180006c35  mov     rcx, [rcx+80h]
0x180006c3c  btr     edx, 1Fh
0x180006c40  sub     edi, edx
0x180006c42  mov     [rsp+58h+Src], edx
0x180006c49  test    ebx, 0C0000h
0x180006c4f  jnz     loc_180006FB4
0x180006c55  xor     r9d, r9d
0x180006c58  mov     [rsp+58h+var_30], r9
0x180006c5d  bt      ebx, 8
0x180006c61  jb      loc_180006E62
0x180006c67  mov     r14d, edx
0x180006c6a  add     r14, rcx
0x180006c6d  test    bl, 40h
0x180006c70  jnz     loc_180006F67
0x180006c76  test    bl, 8
0x180006c79  jnz     loc_180006F8E
0x180006c7f  test    bl, 4
0x180006c82  jnz     loc_180006D99
0x180006c88  bt      ebx, 0Ch
0x180006c8c  jb      loc_180006F80
0x180006c92  mov     ebp, esi
0x180006c94  cmp     edi, ebp
0x180006c96  jb      short loc_180006CED
0x180006c98  cmp     edi, esi
0x180006c9a  jb      short loc_180006CED
0x180006c9c  mov     r8d, ebp; Size
0x180006c9f  mov     rdx, r14; Src
0x180006ca2  mov     rcx, r15; void *
0x180006ca5  call    memcpy_0
0x180006caa  cmp     esi, 4
0x180006cad  jnz     loc_180006B37
0x180006cb3  test    bl, bl
0x180006cb5  js      loc_180006E59
0x180006cbb  bt      ebx, 0Bh
0x180006cbf  jb      loc_1800070E7
0x180006cc5  test    bl, 10h
0x180006cc8  jz      loc_180006B37
0x180006cce  or      dword ptr [r15], 80000000h
0x180006cd5  mov     eax, 1
0x180006cda  mov     r13, [rsp+58h+var_20]
0x180006cdf  jmp     loc_18000696B
0x180006ce4  shl     dword ptr [r15], 0Ah
0x180006ce8  jmp     loc_180006B2B
0x180006ced  lea     rdx, aCriticalVtrans_1; "Critical: VtransferValue: Data to copy "...
0x180006cf4  lea     rcx, aVtransfervalue; "VtransferValue"
0x180006cfb  call    WriteDbgTraceErrorGpd
0x180006d00  jmp     loc_180006B37
0x180006d05  test    eax, eax
0x180006d07  jnz     loc_180006BA4
0x180006d0d  mov     edx, [r8+rcx*4+0Ch]
0x180006d12  jmp     loc_1800069E1
0x180006d17  bt      ebx, 13h
0x180006d1b  jb      loc_1800070B2
0x180006d21  test    bl, 2
0x180006d24  jnz     loc_180006C0A
0x180006d2a  mov     [rsp+58h+Src], r12d
0x180006d32  mov     r9, r15
0x180006d35  mov     edx, esi
0x180006d37  cmp     esi, 4
0x180006d3a  ja      loc_180006E6F
0x180006d40  test    edx, edx
0x180006d42  jz      loc_180006C0A
0x180006d48  mov     r8d, edx; Size
0x180006d4b  mov     rcx, r9; void *
0x180006d4e  lea     rdx, [rsp+58h+Src]; Src
0x180006d56  call    memcpy_0
0x180006d5b  jmp     loc_180006C0A
0x180006d60  lea     ecx, [rsi-1]
0x180006d63  mov     rax, r12
0x180006d66  shr     rcx, 2
0x180006d6a  mov     rdi, r15
0x180006d6d  rep stosd
0x180006d6f  add     r9, 4
0x180006d73  add     edx, 0FFFFFFFCh
0x180006d76  cmp     edx, 4
0x180006d79  jbe     loc_180006B79
0x180006d7f  jmp     short loc_180006D6F
0x180006d81  btr     eax, 1Fh
0x180006d85  lea     r14, [rsp+58h+Src]
0x180006d8d  mov     [rsp+58h+Src], eax
0x180006d94  jmp     loc_180006BBA
0x180006d99  cmp     edi, 8
0x180006d9c  jb      loc_180006EAE
0x180006da2  add     r14, 4
0x180006da6  mov     ebp, 4
0x180006dab  cmp     ebp, esi
0x180006dad  jz      loc_180006C94
0x180006db3  lea     rdx, aVtransfervalue_0; "VtransferValue: Snapshot table contains"...
0x180006dba  lea     rcx, aVtransfervalue; "VtransferValue"
0x180006dc1  call    WriteDbgTraceErrorGpd
  ... truncated ...
```
