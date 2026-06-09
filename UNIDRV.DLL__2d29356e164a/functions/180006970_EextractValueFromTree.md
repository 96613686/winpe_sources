# EextractValueFromTree

- ea: `0x180006970`
- end: `0x180007219`
- name: `EextractValueFromTree`
- size: `2217`
- prototype: ``
- caller_count: `10`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180004b70`
- `0x180004ed0`
- `0x180005000`
- `0x180005100`
- `0x180005500`
- `0x180005620`
- `0x180005bf0`
- `0x1800064a0`
- `0x180007270`
- `0x1800073f0`

## callees

- `0x180006970`
- `0x180007220`
- `0x180074580`

## string_xrefs

- `0x180006dbc`: `Critical: VtransferValue: Data to copy not found in heap.  Value not copied`
- `0x18000714e`: `Critical: VtransferValue: Data to copy not found in heap.`

## pseudocode

```c
__int64 __fastcall EextractValueFromTree(
        _QWORD *a1,
        unsigned int a2,
        int *a3,
        __int64 a4,
        int *a5,
        unsigned int a6,
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
  unsigned int *v42; // rdi
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
    WriteDbgTraceErrorGpd("EextractValueFromTree", "EextractValueFromTree: Unexpected: String heap too large.");
    return 0;
  }
  v13 = (_QWORD *)(a1[22] + 32LL * a2);
  v14 = *((_DWORD *)v13 + 3);
  if ( v14 > (unsigned int)a4 )
  {
    WriteDbgTraceErrorGpd("EextractValueFromTree", "EextractValueFromTree: Destination too small to hold data.");
    return 0;
  }
  v15 = a6;
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
      WriteDbgTraceErrorGpd("EsetDefault", "EsetDefault: Bit fields must be size DWORD");
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
        v42 = (unsigned int *)a3;
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
      WriteDbgTraceErrorGpd("EsetDefault", "EsetDefault: a required keyword is missing from the GPD file. %s", *v13);
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
      WriteDbgTraceErrorGpd("EsetDefault", "EextractValueFromTree: None of several initializers found.  %s", *v13);
    }
    return 3;
  }
  if ( (a6 & 0x80000000) == 0 )
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
          "EextractValueFromTree",
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
                "VtransferValue",
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
          WriteDbgTraceErrorGpd("VtransferValue", "VtransferValue: Snapshot table contains invalid data size.", a3, 0);
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
          "VtransferValue",
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
        "VtransferValue",
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
      WriteDbgTraceErrorGpd("EsetDefault", "EsetDefault: Bit fields must be size DWORD", a3, 0, v55);
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
      WriteDbgTraceErrorGpd("EsetDefault", "EsetDefault: a required keyword is missing from the GPD file. %s", *v13);
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
      WriteDbgTraceErrorGpd("EsetDefault", "EextractValueFromTree: None of several initializers found.  %s", *v13);
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
        WriteDbgTraceErrorGpd("VtransferValue", "VtransferValue: Snapshot table contains invalid data size.");
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
0x180006970  push    r15
0x180006972  sub     rsp, 50h
0x180006976  mov     r11d, [rsp+58h+Src]
0x18000697e  mov     r15, r8
0x180006981  mov     r10, rcx
0x180006984  cmp     r11d, 200h
0x18000698b  jnb     loc_180006C16
0x180006991  mov     rax, [rcx+60h]
0x180006995  mov     [rsp+58h+arg_8], rbp
0x18000699a  mov     ebp, 0FFFFFFFFh
0x18000699f  mov     [rsp+58h+var_10], rdi
0x1800069a4  mov     edi, [rax+8]
0x1800069a7  mov     eax, [rax+4]
0x1800069aa  imul    rdi, rax
0x1800069ae  cmp     rdi, rbp
0x1800069b1  ja      loc_180006A60
0x1800069b7  mov     [rsp+58h+arg_10], rsi
0x1800069bc  mov     [rsp+58h+var_28], r14
0x1800069c1  mov     r14d, edx
0x1800069c4  shl     r14, 5
0x1800069c8  add     r14, [rcx+0B0h]
0x1800069cf  mov     esi, [r14+0Ch]
0x1800069d3  cmp     esi, r9d
0x1800069d6  ja      loc_180007134
0x1800069dc  mov     edx, [rsp+58h+arg_28]
0x1800069e3  mov     [rsp+58h+arg_0], rbx
0x1800069e8  mov     ebx, [r14+18h]
0x1800069ec  mov     [rsp+58h+var_18], r12
0x1800069f1  mov     r12d, [r14+8]
0x1800069f5  cmp     edx, 7FFFFFFFh
0x1800069fb  jnz     loc_180006A86
0x180006a01  bt      ebx, 12h
0x180006a05  jnb     loc_180006C1F
0x180006a0b  cmp     esi, 4
0x180006a0e  jnz     loc_18000710C
0x180006a14  not     r12d
0x180006a17  and     [r8], r12d
0x180006a1a  test    bl, 1
0x180006a1d  jnz     loc_1800070D5
0x180006a23  test    bl, 20h
0x180006a26  jnz     loc_180006EAC
0x180006a2c  and     ebx, 200h
0x180006a32  bts     ebx, 8
0x180006a36  shr     ebx, 8
0x180006a39  mov     eax, ebx
0x180006a3b  mov     r12, [rsp+58h+var_18]
0x180006a40  mov     rbx, [rsp+58h+arg_0]
0x180006a45  mov     rsi, [rsp+58h+arg_10]
0x180006a4a  mov     r14, [rsp+58h+var_28]
0x180006a4f  mov     rbp, [rsp+58h+arg_8]
0x180006a54  mov     rdi, [rsp+58h+var_10]
0x180006a59  add     rsp, 50h
0x180006a5d  pop     r15
0x180006a5f  retn
0x180006a60  lea     rdx, aEextractvaluef; "EextractValueFromTree: Unexpected: Stri"...
0x180006a67  lea     rcx, aEextractvaluef_0; "EextractValueFromTree"
0x180006a6e  call    WriteDbgTraceErrorGpd
0x180006a73  mov     rbp, [rsp+58h+arg_8]
0x180006a78  xor     eax, eax
0x180006a7a  mov     rdi, [rsp+58h+var_10]
0x180006a7f  add     rsp, 50h
0x180006a83  pop     r15
0x180006a85  retn
0x180006a86  mov     [rsp+58h+var_20], r13
0x180006a8b  test    edx, edx
0x180006a8d  js      loc_180006D04
0x180006a93  mov     r8, [rcx+90h]
0x180006a9a  lea     rcx, [rdx+rdx*4]
0x180006a9e  cmp     [r8+rcx*4], ebp
0x180006aa2  jz      loc_1800070F5
0x180006aa8  mov     [rsp+58h+var_38], ebp
0x180006aac  xor     r9d, r9d
0x180006aaf  cmp     edx, ebp
0x180006ab1  jz      loc_180006C73
0x180006ab7  mov     eax, edx
0x180006ab9  lea     rcx, [rax+rax*4]
0x180006abd  mov     r13d, [r8+rcx*4]
0x180006ac1  lea     rbp, [r8+rcx*4]
0x180006ac5  mov     ecx, r13d
0x180006ac8  cmp     r13d, r11d
0x180006acb  jz      loc_180006EDE
0x180006ad1  mov     eax, ecx
0x180006ad3  mov     rcx, [rsp+58h+arg_30]
0x180006adb  movzx   r9d, byte ptr [rcx+rax*2]
0x180006ae0  cmp     r9d, 0FFh
0x180006ae7  jz      loc_18000701C
0x180006aed  cmp     r9d, 0FEh
0x180006af4  jz      loc_1800071EE
0x180006afa  cmp     [rbp+4], r9d
0x180006afe  mov     ebp, 0FFFFFFFFh
0x180006b03  jz      short loc_180006B2C
0x180006b05  nop     word ptr [rax+rax+00000000h]
0x180006b10  mov     eax, edx
0x180006b12  lea     rcx, [rax+rax*4]
0x180006b16  mov     eax, [r8+rcx*4+8]
0x180006b1b  cmp     eax, ebp
0x180006b1d  jz      short loc_180006B2C
0x180006b1f  lea     rcx, [rax+rax*4]
0x180006b23  mov     edx, eax
0x180006b25  cmp     [r8+rcx*4+4], r9d
0x180006b2a  jnz     short loc_180006B10
0x180006b2c  mov     eax, edx
0x180006b2e  lea     rcx, [rax+rax*4]
0x180006b32  mov     eax, [r8+rcx*4+4]
0x180006b37  cmp     eax, r9d
0x180006b3a  jnz     loc_180006C68
0x180006b40  mov     eax, [r8+rcx*4+10h]
0x180006b45  xor     r9d, r9d
0x180006b48  cmp     eax, 1
0x180006b4b  jnz     loc_180006DD4
0x180006b51  mov     eax, edx
0x180006b53  cmp     eax, ebp
0x180006b55  jz      loc_180006CC0
0x180006b5b  lea     rcx, [rax+rax*4]
0x180006b5f  cmp     dword ptr [r8+rcx*4+10h], 1
0x180006b65  jnz     loc_180006CC0
0x180006b6b  mov     eax, [r8+rcx*4+0Ch]
0x180006b70  mov     rcx, [r10+80h]
0x180006b77  sub     edi, eax
0x180006b79  mov     [rsp+58h+Src], eax
0x180006b80  test    ebx, 0C0000h
0x180006b86  jnz     loc_180006FB7
0x180006b8c  mov     [rsp+58h+var_30], r9
0x180006b91  bt      ebx, 8
0x180006b95  jb      loc_180006E50
0x180006b9b  lea     r14, [rcx+rax]
0x180006b9f  test    bl, 40h
0x180006ba2  jnz     loc_180006F5F
0x180006ba8  test    bl, 8
0x180006bab  jnz     loc_180006F95
0x180006bb1  test    bl, 4
0x180006bb4  jnz     loc_180006C7C
0x180006bba  bt      ebx, 0Ch
0x180006bbe  jb      loc_180006F74
0x180006bc4  mov     ebp, esi
0x180006bc6  cmp     edi, ebp
0x180006bc8  jb      loc_180006DBC
0x180006bce  cmp     edi, esi
0x180006bd0  jb      loc_180006DBC
0x180006bd6  mov     r8d, ebp; Size
0x180006bd9  mov     rdx, r14; Src
0x180006bdc  mov     rcx, r15; void *
0x180006bdf  call    memcpy_0
0x180006be4  cmp     esi, 4
0x180006be7  jnz     short loc_180006C07
0x180006be9  test    bl, bl
0x180006beb  js      loc_180006DB3
0x180006bf1  bt      ebx, 0Bh
0x180006bf5  jb      loc_180007208
0x180006bfb  test    bl, 10h
0x180006bfe  jz      short loc_180006C07
0x180006c00  or      dword ptr [r15], 80000000h
0x180006c07  mov     eax, 1
0x180006c0c  mov     r13, [rsp+58h+var_20]
0x180006c11  jmp     loc_180006A3B
0x180006c16  xor     eax, eax
0x180006c18  add     rsp, 50h
0x180006c1c  pop     r15
0x180006c1e  retn
0x180006c1f  bt      ebx, 13h
0x180006c23  jb      loc_180007103
0x180006c29  test    bl, 2
0x180006c2c  jnz     loc_180006A1A
0x180006c32  mov     [rsp+58h+Src], r12d
0x180006c3a  mov     r9, r15
0x180006c3d  mov     edx, esi
0x180006c3f  cmp     esi, 4
0x180006c42  ja      loc_180006E2F
0x180006c48  test    edx, edx
0x180006c4a  jz      loc_180006A1A
0x180006c50  mov     r8d, edx; Size
0x180006c53  mov     rcx, r9; void *
0x180006c56  lea     rdx, [rsp+58h+Src]; Src
0x180006c5e  call    memcpy_0
0x180006c63  jmp     loc_180006A1A
0x180006c68  cmp     eax, ebp
0x180006c6a  jz      loc_180006B40
0x180006c70  xor     r9d, r9d
0x180006c73  mov     eax, [rsp+58h+var_38]
0x180006c77  jmp     loc_180006B53
0x180006c7c  cmp     edi, 8
0x180006c7f  jb      loc_180006F7D
0x180006c85  add     r14, 4
0x180006c89  mov     ebp, 4
0x180006c8e  cmp     ebp, esi
0x180006c90  jz      loc_180006BC6
0x180006c96  lea     rdx, aVtransfervalue_0; "VtransferValue: Snapshot table contains"...
0x180006c9d  lea     rcx, aVtransfervalue; "VtransferValue"
0x180006ca4  call    WriteDbgTraceErrorGpd
0x180006ca9  cmp     esi, ebp
0x180006cab  jnb     loc_180006BC6
0x180006cb1  mov     r13, [rsp+58h+var_20]
0x180006cb6  mov     eax, 1
0x180006cbb  jmp     loc_180006A3B
0x180006cc0  bt      ebx, 12h
0x180006cc4  jnb     loc_180006DE6
0x180006cca  cmp     esi, 4
0x180006ccd  jnz     loc_18000718A
0x180006cd3  not     r12d
0x180006cd6  and     [r15], r12d
0x180006cd9  test    bl, 1
0x180006cdc  jnz     loc_18000715A
0x180006ce2  test    bl, 20h
0x180006ce5  jnz     loc_180006FEA
0x180006ceb  mov     r13, [rsp+58h+var_20]
0x180006cf0  and     ebx, 200h
0x180006cf6  bts     ebx, 8
0x180006cfa  shr     ebx, 8
0x180006cfd  mov     eax, ebx
0x180006cff  jmp     loc_180006A3B
0x180006d04  mov     rcx, [rcx+80h]
0x180006d0b  btr     edx, 1Fh
0x180006d0f  sub     edi, edx
0x180006d11  mov     [rsp+58h+Src], edx
0x180006d18  test    ebx, 0C0000h
0x180006d1e  jnz     loc_180007083
0x180006d24  xor     r9d, r9d
0x180006d27  mov     [rsp+58h+var_30], r9
0x180006d2c  bt      ebx, 8
0x180006d30  jb      loc_180006F31
0x180006d36  mov     r14d, edx
0x180006d39  add     r14, rcx
0x180006d3c  test    bl, 40h
0x180006d3f  jnz     loc_180007036
0x180006d45  test    bl, 8
0x180006d48  jnz     loc_18000705D
0x180006d4e  test    bl, 4
0x180006d51  jnz     loc_180006E68
0x180006d57  bt      ebx, 0Ch
0x180006d5b  jb      loc_18000704F
0x180006d61  mov     ebp, esi
0x180006d63  cmp     edi, ebp
0x180006d65  jb      short loc_180006DBC
0x180006d67  cmp     edi, esi
0x180006d69  jb      short loc_180006DBC
0x180006d6b  mov     r8d, ebp; Size
0x180006d6e  mov     rdx, r14; Src
0x180006d71  mov     rcx, r15; void *
0x180006d74  call    memcpy_0
0x180006d79  cmp     esi, 4
0x180006d7c  jnz     loc_180006C07
0x180006d82  test    bl, bl
0x180006d84  js      loc_180006F28
0x180006d8a  bt      ebx, 0Bh
0x180006d8e  jb      loc_1800071B6
0x180006d94  test    bl, 10h
0x180006d97  jz      loc_180006C07
0x180006d9d  or      dword ptr [r15], 80000000h
0x180006da4  mov     eax, 1
0x180006da9  mov     r13, [rsp+58h+var_20]
0x180006dae  jmp     loc_180006A3B
0x180006db3  shl     dword ptr [r15], 0Ah
0x180006db7  jmp     loc_180006BFB
0x180006dbc  lea     rdx, aCriticalVtrans_1; "Critical: VtransferValue: Data to copy "...
0x180006dc3  lea     rcx, aVtransfervalue; "VtransferValue"
0x180006dca  call    WriteDbgTraceErrorGpd
0x180006dcf  jmp     loc_180006C07
0x180006dd4  test    eax, eax
0x180006dd6  jnz     loc_180006C73
0x180006ddc  mov     edx, [r8+rcx*4+0Ch]
0x180006de1  jmp     loc_180006AAF
0x180006de6  bt      ebx, 13h
0x180006dea  jb      loc_180007181
0x180006df0  test    bl, 2
0x180006df3  jnz     loc_180006CD9
0x180006df9  mov     [rsp+58h+Src], r12d
0x180006e01  mov     r9, r15
0x180006e04  mov     edx, esi
0x180006e06  cmp     esi, 4
0x180006e09  ja      loc_180006F3E
0x180006e0f  test    edx, edx
0x180006e11  jz      loc_180006CD9
0x180006e17  mov     r8d, edx; Size
0x180006e1a  mov     rcx, r9; void *
0x180006e1d  lea     rdx, [rsp+58h+Src]; Src
0x180006e25  call    memcpy_0
0x180006e2a  jmp     loc_180006CD9
0x180006e2f  lea     ecx, [rsi-1]
0x180006e32  mov     rax, r12
0x180006e35  shr     rcx, 2
0x180006e39  mov     rdi, r15
0x180006e3c  rep stosd
0x180006e3e  add     r9, 4
0x180006e42  add     edx, 0FFFFFFFCh
0x180006e45  cmp     edx, 4
0x180006e48  jbe     loc_180006C48
0x180006e4e  jmp     short loc_180006E3E
0x180006e50  btr     eax, 1Fh
0x180006e54  lea     r14, [rsp+58h+Src]
0x180006e5c  mov     [rsp+58h+Src], eax
0x180006e63  jmp     loc_180006C89
0x180006e68  cmp     edi, 8
0x180006e6b  jb      loc_180006F7D
0x180006e71  add     r14, 4
0x180006e75  mov     ebp, 4
0x180006e7a  cmp     ebp, esi
0x180006e7c  jz      loc_180006D63
0x180006e82  lea     rdx, aVtransfervalue_0; "VtransferValue: Snapshot table contains"...
0x180006e89  lea     rcx, aVtransfervalue; "VtransferValue"
0x180006e90  call    WriteDbgTraceErrorGpd
  ... truncated ...
```
