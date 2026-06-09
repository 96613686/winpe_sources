# _AttributesFromHashing(AslFileMapping &,tagFILEATTRIBUTE *,unsigned __int64,FAR_MODE_FLAGS)

- ea: `0x1800e3cb0`
- end: `0x1800e4533`
- name: `?_AttributesFromHashing@@YAJAEAVAslFileMapping@@PEAUtagFILEATTRIBUTE@@_KW4FAR_MODE_FLAGS@@@Z`
- size: `2179`
- prototype: `__int64 __fastcall(struct AslFileMapping *, _DWORD *, __int64, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180004ea0`
- `0x180005914`
- `0x18004bad0`
- `0x18004c020`
- `0x1800e3cb0`
- `0x1800e5358`
- `0x1800e5428`
- `0x1800e5dec`
- `0x1800e633c`

## string_xrefs

- `0x1800e3dd2`: `_SetFileAttributeValue`
- `0x1800e3eb6`: `_SetFileAttributeValue`
- `0x1800e4088`: `_SetFileAttributeValue`
- `0x1800e42b8`: `_SetFileAttributeValue`
- `0x1800e43b0`: `_SetFileAttributeValue`
- `0x1800e44b0`: `_SetFileAttributeValue`
- `0x1800e3dd9`: `StringCbCopy failed to copy string attribute (index %d) [%x]`
- `0x1800e3ebd`: `StringCbCopy failed to copy string attribute (index %d) [%x]`
- `0x1800e408f`: `StringCbCopy failed to copy string attribute (index %d) [%x]`
- `0x1800e42bf`: `StringCbCopy failed to copy string attribute (index %d) [%x]`
- `0x1800e439b`: `StringCbCopy failed to copy string attribute (index %d) [%x]`
- `0x1800e44a9`: `StringCbCopy failed to copy string attribute (index %d) [%x]`

## pseudocode

```c
__int64 __fastcall _AttributesFromHashing(struct AslFileMapping *a1, _DWORD *a2, __int64 a3, int a4)
{
  int v7; // edi
  int v8; // r10d
  __int64 v9; // rsi
  int v10; // eax
  __int64 v11; // rax
  __int64 v12; // rdx
  unsigned __int64 *v13; // rcx
  _WORD *v14; // r8
  _WORD *v15; // rcx
  int v16; // r10d
  __int64 v17; // rax
  __int64 *v18; // rcx
  __int64 v19; // rdx
  _WORD *v20; // r8
  _WORD *v21; // rcx
  int v22; // eax
  int v23; // eax
  __int64 v24; // r14
  int v25; // r10d
  __int64 v26; // rax
  unsigned __int16 *v27; // rcx
  __int64 v28; // rdx
  _WORD *v29; // r8
  _WORD *v30; // rcx
  __int64 v31; // r15
  __int64 v32; // r12
  unsigned __int16 *v33; // r15
  unsigned __int16 *v34; // r12
  _QWORD *v35; // rax
  __int64 v36; // rcx
  unsigned __int16 *v37; // rdx
  __int64 v38; // r9
  unsigned __int16 *v39; // rax
  unsigned __int16 *v40; // rcx
  __int64 v41; // r9
  int v42; // eax
  int v43; // r10d
  unsigned __int16 *v44; // rax
  __int64 v45; // rdx
  _WORD *v46; // r8
  _WORD *v47; // rcx
  int v48; // edi
  __int64 v49; // rax
  _WORD *v50; // rcx
  _WORD *v51; // r11
  _WORD *v52; // rcx
  int v53; // r9d
  __int64 v54; // r14
  const wchar_t *v55; // rax
  _WORD *v56; // r8
  _WORD *v57; // rcx
  __int64 v59; // [rsp+20h] [rbp-E0h]
  __int64 v60; // [rsp+30h] [rbp-D0h] BYREF
  int v61; // [rsp+38h] [rbp-C8h]
  unsigned __int64 v62; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v63[2]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v64[33]; // [rsp+58h] [rbp-A8h] BYREF
  char v65; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int16 v66[48]; // [rsp+260h] [rbp+160h] BYREF
  _QWORD v67[18]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v61 = a4;
  v62 = 0;
  LODWORD(v60) = 0;
  if ( !a2 )
    return (unsigned int)-2147024809;
  v8 = dword_180119B7C;
  v9 = 260;
  v10 = -1;
  v62 = *(_QWORD *)(*(_QWORD *)a1 + 24LL);
  if ( v62 < 0x100000000LL )
    v10 = v62;
  LODWORD(v60) = v10;
  if ( (unsigned int)dword_180119B7C <= 2 )
  {
    a2[5576] = v62;
  }
  else if ( dword_180119B7C == 3 )
  {
    *((_QWORD *)a2 + 2788) = v62;
  }
  else
  {
    if ( dword_180119B7C != 4 )
      goto LABEL_19;
    v11 = 4;
    v12 = 260;
    v13 = &v62;
    v14 = a2 + 5576;
    do
    {
      if ( !v11 )
        break;
      if ( !*(_WORD *)v13 )
        break;
      *v14 = *(_WORD *)v13;
      v13 = (unsigned __int64 *)((char *)v13 + 2);
      ++v14;
      --v11;
      --v12;
    }
    while ( v12 );
    v15 = v14 - 1;
    if ( v12 )
      v15 = v14;
    *v15 = 0;
    if ( !v12 )
    {
      AslLogCallPrintf(
        1,
        "_SetFileAttributeValue",
        3178,
        "StringCbCopy failed to copy string attribute (index %d) [%x]",
        41,
        -2147024774);
      goto LABEL_19;
    }
  }
  a2[5706] = 41;
  a2[5707] = v8;
  a2[5708] = 1;
LABEL_19:
  v16 = dword_1801197EC;
  if ( (unsigned int)dword_1801197EC <= 2 )
  {
    a2[408] = v60;
    goto LABEL_32;
  }
  if ( dword_1801197EC == 3 )
  {
    *((_QWORD *)a2 + 204) = v60;
    goto LABEL_32;
  }
  if ( dword_1801197EC == 4 )
  {
    v17 = 2;
    v18 = &v60;
    v19 = 260;
    v20 = a2 + 408;
    do
    {
      if ( !v17 )
        break;
      if ( !*(_WORD *)v18 )
        break;
      *v20 = *(_WORD *)v18;
      v18 = (__int64 *)((char *)v18 + 2);
      ++v20;
      --v17;
      --v19;
    }
    while ( v19 );
    v21 = v20 - 1;
    if ( v19 )
      v21 = v20;
    *v21 = 0;
    if ( !v19 )
    {
      AslLogCallPrintf(
        1,
        "_SetFileAttributeValue",
        3178,
        "StringCbCopy failed to copy string attribute (index %d) [%x]",
        3,
        -2147024774);
      goto LABEL_33;
    }
LABEL_32:
    a2[538] = 3;
    a2[539] = v16;
    a2[540] = 1;
  }
LABEL_33:
  if ( a2[1632] == 1 )
    goto LABEL_102;
  v22 = _SetFarAttributeFromAslAttribute(a1, 28, 12, a2);
  v7 = v22;
  if ( v22 < 0 || a2[1764] != 1 )
  {
    LODWORD(v59) = v22;
    AslLogCallPrintf(
      1,
      "_AttributesFromHashing",
      1678,
      "_SetFarAttributeFromAslAttribute failed to set FA_BIN_TYPE [%x]",
      v59);
    return (unsigned int)v7;
  }
  if ( a2[1632] <= 1u || !(_DWORD)v60 )
  {
LABEL_102:
    if ( (a3 & 0x20000) != 0 )
    {
      v53 = dword_18011993C;
      if ( (unsigned int)dword_18011993C <= 2 )
      {
        a2[2312] = 3145776;
        goto LABEL_116;
      }
      if ( dword_18011993C == 3 )
      {
        *((_QWORD *)a2 + 1156) = 0x30003000300030LL;
        goto LABEL_116;
      }
      if ( dword_18011993C == 4 )
      {
        v54 = 45;
        v55 = L"0000da39a3ee5e6b4b0d3255bfef95601890afd80709";
        v56 = a2 + 2312;
        do
        {
          if ( !v54 )
            break;
          if ( !*v55 )
            break;
          *v56++ = *v55++;
          --v54;
          --v9;
        }
        while ( v9 );
        v57 = v56 - 1;
        if ( v9 )
          v57 = v56;
        *v57 = 0;
        if ( !v9 )
        {
          AslLogCallPrintf(
            1,
            "_SetFileAttributeValue",
            3178,
            "StringCbCopy failed to copy string attribute (index %d) [%x]",
            17,
            -2147024774);
          return 1;
        }
LABEL_116:
        a2[2442] = 17;
        a2[2443] = v53;
        a2[2444] = 1;
      }
    }
    return 1;
  }
  v23 = AslFileMappingEnsureMappedAs(*(_QWORD *)a1);
  if ( v23 >= 0 )
  {
    v24 = 45;
    if ( (a3 & 0x20) == 0 )
      goto LABEL_59;
    if ( (int)a2[1632] <= 4 )
      goto LABEL_59;
    memset_0(v66, 0, 0x5Au);
    if ( (int)_ComputePeHeaderHash(a1, v66) < 0 )
      goto LABEL_59;
    v25 = dword_18011981C;
    if ( (unsigned int)dword_18011981C <= 2 )
    {
      a2[680] = *(_DWORD *)v66;
    }
    else if ( dword_18011981C == 3 )
    {
      *((_QWORD *)a2 + 340) = *(_QWORD *)v66;
    }
    else
    {
      if ( dword_18011981C != 4 )
        goto LABEL_59;
      v26 = 45;
      v27 = v66;
      v28 = 260;
      v29 = a2 + 680;
      do
      {
        if ( !v26 )
          break;
        if ( !*v27 )
          break;
        *v29++ = *v27++;
        --v26;
        --v28;
      }
      while ( v28 );
      v30 = v29 - 1;
      if ( v28 )
        v30 = v29;
      *v30 = 0;
      if ( !v28 )
      {
        AslLogCallPrintf(
          1,
          "_SetFileAttributeValue",
          3178,
          "StringCbCopy failed to copy string attribute (index %d) [%x]",
          5,
          -2147024774);
        goto LABEL_59;
      }
    }
    a2[810] = 5;
    a2[811] = v25;
    a2[812] = 1;
LABEL_59:
    v31 = a3 & 0x20000;
    v32 = a3 & 0x80000000000LL;
    if ( !v31 && !v32 )
      return 0;
    memset_0(v66, 0, 0x5Au);
    memset_0(v67, 0, 0x82u);
    v33 = (unsigned __int16 *)((unsigned __int64)v66 & -(__int64)(v31 != 0));
    v34 = (unsigned __int16 *)((unsigned __int64)v67 & -(__int64)(v32 != 0));
    if ( (v61 & 1) == 0 )
    {
      memset_0(v64, 0, 0x208u);
      v35 = *(_QWORD **)a1;
      v63[0] = 1;
      v63[1] = 528;
      v64[0] = *v35;
      v7 = AeWERQueryFileInfo(v63);
      if ( v7 >= 0 )
      {
        v36 = 2147483646;
        v37 = (unsigned __int16 *)&v65;
        v38 = 45;
        v39 = v66;
        do
        {
          if ( !v36 )
            break;
          if ( !*v37 )
            break;
          *v39++ = *v37++;
          --v36;
          --v38;
        }
        while ( v38 );
        v40 = v39 - 1;
        if ( v38 )
          v40 = v39;
        v7 = v38 == 0 ? 0x8007007A : 0;
        *v40 = 0;
      }
    }
    v41 = *(_QWORD *)v66;
    if ( !v66[0] )
    {
      v42 = _ComputeFileHashes(a1, v33, v34);
      v41 = *(_QWORD *)v66;
      v7 = v42;
    }
    if ( v7 < 0 )
      return 0;
    v43 = dword_18011993C;
    if ( (unsigned int)dword_18011993C <= 2 )
    {
      a2[2312] = v41;
    }
    else if ( dword_18011993C == 3 )
    {
      *((_QWORD *)a2 + 1156) = v41;
    }
    else
    {
      if ( dword_18011993C != 4 )
        goto LABEL_87;
      v44 = v66;
      v45 = 260;
      v46 = a2 + 2312;
      do
      {
        if ( !v24 )
          break;
        if ( !*v44 )
          break;
        *v46++ = *v44++;
        --v24;
        --v45;
      }
      while ( v45 );
      v47 = v46 - 1;
      if ( v45 )
        v47 = v46;
      *v47 = 0;
      if ( !v45 )
      {
        AslLogCallPrintf(
          1,
          "_SetFileAttributeValue",
          3178,
          "StringCbCopy failed to copy string attribute (index %d) [%x]",
          17,
          -2147024774);
        goto LABEL_87;
      }
    }
    a2[2442] = 17;
    a2[2443] = v43;
    a2[2444] = 1;
LABEL_87:
    v48 = dword_180119BAC;
    if ( (unsigned int)dword_180119BAC <= 2 )
    {
      a2[5848] = v67[0];
    }
    else if ( dword_180119BAC == 3 )
    {
      *((_QWORD *)a2 + 2924) = v67[0];
    }
    else
    {
      if ( dword_180119BAC != 4 )
        return 0;
      v49 = 65;
      v50 = v67;
      v51 = a2 + 5848;
      do
      {
        if ( !v49 )
          break;
        if ( !*v50 )
          break;
        *v51++ = *v50++;
        --v49;
        --v9;
      }
      while ( v9 );
      v52 = v51 - 1;
      if ( v9 )
        v52 = v51;
      *v52 = 0;
      if ( !v9 )
      {
        AslLogCallPrintf(
          1,
          "_SetFileAttributeValue",
          3178,
          "StringCbCopy failed to copy string attribute (index %d) [%x]",
          43,
          -2147024774);
        return 0;
      }
    }
    a2[5978] = 43;
    a2[5979] = v48;
    a2[5980] = 1;
    return 0;
  }
  v7 = v23 | 0x10000000;
  if ( v23 != -1073741538 )
  {
    LODWORD(v59) = v23 | 0x10000000;
    AslLogCallPrintf(1, "_AttributesFromHashing", 1716, "Failed to ensure the file mapping as data [%x]", v59);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800e3cb0  mov     [rsp-8+arg_10], rbx
0x1800e3cb5  push    rbp
0x1800e3cb6  push    rsi
0x1800e3cb7  push    rdi
0x1800e3cb8  push    r12
0x1800e3cba  push    r13
0x1800e3cbc  push    r14
0x1800e3cbe  push    r15
0x1800e3cc0  lea     rbp, [rsp-260h]
0x1800e3cc8  sub     rsp, 360h
0x1800e3ccf  mov     rax, cs:__security_cookie
0x1800e3cd6  xor     rax, rsp
0x1800e3cd9  mov     [rbp+290h+var_40], rax
0x1800e3ce0  xor     r15d, r15d
0x1800e3ce3  mov     [rsp+390h+var_358], r9d
0x1800e3ce8  mov     [rsp+390h+var_350], r15
0x1800e3ced  mov     r12, r8
0x1800e3cf0  mov     dword ptr [rsp+390h+var_360], r15d
0x1800e3cf5  mov     rbx, rdx
0x1800e3cf8  mov     r13, rcx
0x1800e3cfb  test    rdx, rdx
0x1800e3cfe  jnz     short loc_1800E3D0A
0x1800e3d00  mov     edi, 80070057h
0x1800e3d05  jmp     loc_1800E4507
0x1800e3d0a  mov     rax, [rcx]
0x1800e3d0d  mov     edi, 80004005h
0x1800e3d12  mov     r10d, cs:dword_180119B7C
0x1800e3d19  mov     rcx, 100000000h
0x1800e3d23  mov     esi, 104h
0x1800e3d28  mov     r14d, 1
0x1800e3d2e  mov     rdx, [rax+18h]
0x1800e3d32  or      eax, 0FFFFFFFFh
0x1800e3d35  cmp     rdx, rcx
0x1800e3d38  mov     [rsp+390h+var_350], rdx
0x1800e3d3d  mov     ecx, r10d
0x1800e3d40  cmovb   eax, edx
0x1800e3d43  mov     dword ptr [rsp+390h+var_360], eax
0x1800e3d47  test    r10d, r10d
0x1800e3d4a  jz      loc_1800E3E01
0x1800e3d50  sub     ecx, r14d
0x1800e3d53  jz      loc_1800E3E01
0x1800e3d59  sub     ecx, r14d
0x1800e3d5c  jz      loc_1800E3E01
0x1800e3d62  sub     ecx, r14d
0x1800e3d65  jz      loc_1800E3DF8
0x1800e3d6b  cmp     ecx, r14d
0x1800e3d6e  jnz     loc_1800E3E1F
0x1800e3d74  lea     eax, [r14+3]
0x1800e3d78  mov     edx, esi
0x1800e3d7a  lea     rcx, [rsp+390h+var_350]
0x1800e3d7f  lea     r8, [rbx+5720h]
0x1800e3d86  test    rax, rax
0x1800e3d89  jz      short loc_1800E3DA9
0x1800e3d8b  movzx   r9d, word ptr [rcx]
0x1800e3d8f  test    r9w, r9w
0x1800e3d93  jz      short loc_1800E3DA9
0x1800e3d95  mov     [r8], r9w
0x1800e3d99  add     rcx, 2
0x1800e3d9d  add     r8, 2
0x1800e3da1  sub     rax, r14
0x1800e3da4  sub     rdx, r14
0x1800e3da7  jnz     short loc_1800E3D86
0x1800e3da9  mov     rax, rdx
0x1800e3dac  lea     rcx, [r8-2]
0x1800e3db0  neg     rax
0x1800e3db3  sbb     r9d, r9d
0x1800e3db6  not     r9d
0x1800e3db9  and     r9d, 8007007Ah
0x1800e3dc0  test    rdx, rdx
0x1800e3dc3  cmovnz  rcx, r8
0x1800e3dc7  mov     [rcx], r15w
0x1800e3dcb  jnz     short loc_1800E3E07
0x1800e3dcd  mov     [rsp+390h+var_368], r9d
0x1800e3dd2  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x1800e3dd9  lea     r9, aStringcbcopyFa; "StringCbCopy failed to copy string attr"...
0x1800e3de0  mov     dword ptr [rsp+390h+var_370], 29h ; ')'
0x1800e3de8  mov     r8d, 0C6Ah
0x1800e3dee  mov     ecx, r14d
0x1800e3df1  call    AslLogCallPrintf
0x1800e3df6  jmp     short loc_1800E3E1F
0x1800e3df8  mov     [rbx+5720h], rdx
0x1800e3dff  jmp     short loc_1800E3E07
0x1800e3e01  mov     [rbx+5720h], edx
0x1800e3e07  mov     dword ptr [rbx+5928h], 29h ; ')'
0x1800e3e11  mov     [rbx+592Ch], r10d
0x1800e3e18  mov     [rbx+5930h], r14d
0x1800e3e1f  mov     r10d, cs:dword_1801197EC
0x1800e3e26  mov     ecx, r10d
0x1800e3e29  test    r10d, r10d
0x1800e3e2c  jz      loc_1800E3EEA
0x1800e3e32  sub     ecx, r14d
0x1800e3e35  jz      loc_1800E3EEA
0x1800e3e3b  sub     ecx, r14d
0x1800e3e3e  jz      loc_1800E3EEA
0x1800e3e44  sub     ecx, r14d
0x1800e3e47  jz      loc_1800E3EDC
0x1800e3e4d  cmp     ecx, r14d
0x1800e3e50  jnz     loc_1800E3F0C
0x1800e3e56  mov     eax, 2
0x1800e3e5b  lea     rcx, [rsp+390h+var_360]
0x1800e3e60  mov     rdx, rsi
0x1800e3e63  lea     r8, [rbx+660h]
0x1800e3e6a  test    rax, rax
0x1800e3e6d  jz      short loc_1800E3E8D
0x1800e3e6f  movzx   r9d, word ptr [rcx]
0x1800e3e73  test    r9w, r9w
0x1800e3e77  jz      short loc_1800E3E8D
0x1800e3e79  mov     [r8], r9w
0x1800e3e7d  add     rcx, 2
0x1800e3e81  add     r8, 2
0x1800e3e85  sub     rax, r14
0x1800e3e88  sub     rdx, r14
0x1800e3e8b  jnz     short loc_1800E3E6A
0x1800e3e8d  mov     rax, rdx
0x1800e3e90  lea     rcx, [r8-2]
0x1800e3e94  neg     rax
0x1800e3e97  sbb     r9d, r9d
0x1800e3e9a  not     r9d
0x1800e3e9d  and     r9d, 8007007Ah
0x1800e3ea4  test    rdx, rdx
0x1800e3ea7  cmovnz  rcx, r8
0x1800e3eab  mov     [rcx], r15w
0x1800e3eaf  jnz     short loc_1800E3EF4
0x1800e3eb1  mov     [rsp+390h+var_368], r9d
0x1800e3eb6  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x1800e3ebd  lea     r9, aStringcbcopyFa; "StringCbCopy failed to copy string attr"...
0x1800e3ec4  mov     dword ptr [rsp+390h+var_370], 3
0x1800e3ecc  mov     r8d, 0C6Ah
0x1800e3ed2  mov     ecx, r14d
0x1800e3ed5  call    AslLogCallPrintf
0x1800e3eda  jmp     short loc_1800E3F0C
0x1800e3edc  mov     rax, [rsp+390h+var_360]
0x1800e3ee1  mov     [rbx+660h], rax
0x1800e3ee8  jmp     short loc_1800E3EF4
0x1800e3eea  mov     eax, dword ptr [rsp+390h+var_360]
0x1800e3eee  mov     [rbx+660h], eax
0x1800e3ef4  mov     dword ptr [rbx+868h], 3
0x1800e3efe  mov     [rbx+86Ch], r10d
0x1800e3f05  mov     [rbx+870h], r14d
0x1800e3f0c  cmp     [rbx+1980h], r14d
0x1800e3f13  jz      loc_1800E4406
0x1800e3f19  mov     edx, 1Ch
0x1800e3f1e  mov     r9, rbx
0x1800e3f21  mov     rcx, r13
0x1800e3f24  lea     r8d, [rdx-10h]
0x1800e3f28  call    ?_SetFarAttributeFromAslAttribute@@YAJAEAVAslFileMapping@@W4ASL_ATTRIBUTE_INDEX@@W4FILEATTRID@@PEAUtagFILEATTRIBUTE@@@Z; _SetFarAttributeFromAslAttribute(AslFileMapping &,ASL_ATTRIBUTE_INDEX,FILEATTRID,tagFILEATTRIBUTE *)
0x1800e3f2d  mov     edi, eax
0x1800e3f2f  test    eax, eax
0x1800e3f31  js      short loc_1800E3F3C
0x1800e3f33  cmp     [rbx+1B90h], r14d
0x1800e3f3a  jz      short loc_1800E3F61
0x1800e3f3c  mov     dword ptr [rsp+390h+var_370], eax
0x1800e3f40  lea     r9, aSetfarattribut; "_SetFarAttributeFromAslAttribute failed"...
0x1800e3f47  mov     r8d, 68Eh
0x1800e3f4d  lea     rdx, aAttributesfrom_1; "_AttributesFromHashing"
0x1800e3f54  mov     ecx, r14d
0x1800e3f57  call    AslLogCallPrintf
0x1800e3f5c  jmp     loc_1800E4507
0x1800e3f61  cmp     [rbx+1980h], r14d
0x1800e3f68  jbe     loc_1800E4406
0x1800e3f6e  cmp     dword ptr [rsp+390h+var_360], r15d
0x1800e3f73  jz      loc_1800E4406
0x1800e3f79  mov     rcx, [r13+0]
0x1800e3f7d  call    AslFileMappingEnsureMappedAs
0x1800e3f82  test    eax, eax
0x1800e3f84  jns     short loc_1800E3FAA
0x1800e3f86  mov     edi, eax
0x1800e3f88  bts     edi, 1Ch
0x1800e3f8c  cmp     eax, 0C000011Eh
0x1800e3f91  jz      loc_1800E4507
0x1800e3f97  mov     dword ptr [rsp+390h+var_370], edi
0x1800e3f9b  lea     r9, aFailedToEnsure_0; "Failed to ensure the file mapping as da"...
0x1800e3fa2  mov     r8d, 6B4h
0x1800e3fa8  jmp     short loc_1800E3F4D
0x1800e3faa  mov     r14d, 2Dh ; '-'
0x1800e3fb0  test    r12b, 20h
0x1800e3fb4  jz      loc_1800E40E7
0x1800e3fba  cmp     dword ptr [rbx+1980h], 4
0x1800e3fc1  jle     loc_1800E40E7
0x1800e3fc7  xor     edx, edx; Val
0x1800e3fc9  lea     r8d, [r14+2Dh]; Size
0x1800e3fcd  lea     rcx, [rbp+290h+var_130]; void *
0x1800e3fd4  call    memset_0
0x1800e3fd9  lea     rdx, [rbp+290h+var_130]; unsigned __int16 *
0x1800e3fe0  mov     rcx, r13; struct AslFileMapping *
0x1800e3fe3  call    ?_ComputePeHeaderHash@@YAJAEAVAslFileMapping@@PEAG@Z; _ComputePeHeaderHash(AslFileMapping &,ushort *)
0x1800e3fe8  test    eax, eax
0x1800e3fea  js      loc_1800E40E7
0x1800e3ff0  mov     r10d, cs:dword_18011981C
0x1800e3ff7  mov     ecx, r10d
0x1800e3ffa  test    r10d, r10d
0x1800e3ffd  jz      loc_1800E40C0
0x1800e4003  sub     ecx, 1
0x1800e4006  jz      loc_1800E40C0
0x1800e400c  sub     ecx, 1
0x1800e400f  jz      loc_1800E40C0
0x1800e4015  sub     ecx, 1
0x1800e4018  jz      loc_1800E40B0
0x1800e401e  cmp     ecx, 1
0x1800e4021  jnz     loc_1800E40E7
0x1800e4027  mov     eax, r14d
0x1800e402a  lea     rcx, [rbp+290h+var_130]
0x1800e4031  mov     rdx, rsi
0x1800e4034  lea     r8, [rbx+0AA0h]
0x1800e403b  test    rax, rax
0x1800e403e  jz      short loc_1800E405F
0x1800e4040  movzx   r9d, word ptr [rcx]
0x1800e4044  test    r9w, r9w
0x1800e4048  jz      short loc_1800E405F
0x1800e404a  mov     [r8], r9w
0x1800e404e  add     rcx, 2
0x1800e4052  add     r8, 2
0x1800e4056  dec     rax
0x1800e4059  sub     rdx, 1
0x1800e405d  jnz     short loc_1800E403B
0x1800e405f  mov     rax, rdx
0x1800e4062  lea     rcx, [r8-2]
0x1800e4066  neg     rax
0x1800e4069  sbb     r9d, r9d
0x1800e406c  not     r9d
0x1800e406f  and     r9d, 8007007Ah
0x1800e4076  test    rdx, rdx
0x1800e4079  cmovnz  rcx, r8
0x1800e407d  mov     [rcx], r15w
0x1800e4081  jnz     short loc_1800E40CC
0x1800e4083  mov     [rsp+390h+var_368], r9d
0x1800e4088  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x1800e408f  lea     r9, aStringcbcopyFa; "StringCbCopy failed to copy string attr"...
0x1800e4096  mov     dword ptr [rsp+390h+var_370], 5
0x1800e409e  mov     r8d, 0C6Ah
0x1800e40a4  mov     ecx, 1
0x1800e40a9  call    AslLogCallPrintf
0x1800e40ae  jmp     short loc_1800E40E7
0x1800e40b0  mov     rax, qword ptr [rbp+290h+var_130]
0x1800e40b7  mov     [rbx+0AA0h], rax
0x1800e40be  jmp     short loc_1800E40CC
0x1800e40c0  mov     eax, dword ptr [rbp+290h+var_130]
0x1800e40c6  mov     [rbx+0AA0h], eax
0x1800e40cc  mov     dword ptr [rbx+0CA8h], 5
0x1800e40d6  mov     [rbx+0CACh], r10d
0x1800e40dd  mov     dword ptr [rbx+0CB0h], 1
0x1800e40e7  mov     r15, r12
0x1800e40ea  mov     rax, 80000000000h
0x1800e40f4  and     r15d, 20000h
0x1800e40fb  and     r12, rax
0x1800e40fe  test    r15, r15
0x1800e4101  jnz     short loc_1800E410C
0x1800e4103  test    r12, r12
0x1800e4106  jz      loc_1800E43FB
0x1800e410c  xor     edx, edx; Val
0x1800e410e  lea     rcx, [rbp+290h+var_130]; void *
0x1800e4115  lea     r8d, [rdx+5Ah]; Size
0x1800e4119  call    memset_0
0x1800e411e  xor     edx, edx; Val
0x1800e4120  lea     rcx, [rbp+290h+var_D0]; void *
0x1800e4127  mov     r8d, 82h; Size
0x1800e412d  call    memset_0
0x1800e4132  neg     r15
0x1800e4135  lea     rax, [rbp+290h+var_130]
0x1800e413c  sbb     r15, r15
0x1800e413f  and     r15, rax
0x1800e4142  lea     rax, [rbp+290h+var_D0]
0x1800e4149  neg     r12
0x1800e414c  sbb     r12, r12
0x1800e414f  and     r12, rax
0x1800e4152  test    byte ptr [rsp+390h+var_358], 1
0x1800e4157  jnz     loc_1800E41F3
0x1800e415d  xor     edx, edx; Val
0x1800e415f  lea     rcx, [rsp+390h+var_338]; void *
0x1800e4164  mov     r8d, 208h; Size
0x1800e416a  call    memset_0
0x1800e416f  mov     rax, [r13+0]
0x1800e4173  mov     [rsp+390h+var_340], 1
0x1800e417b  mov     [rsp+390h+var_33C], 210h
0x1800e4183  mov     rcx, [rax]
0x1800e4186  mov     [rsp+390h+var_338], rcx
0x1800e418b  lea     rcx, [rsp+390h+var_340]
0x1800e4190  call    AeWERQueryFileInfo
0x1800e4195  xor     r10d, r10d
0x1800e4198  mov     edi, eax
0x1800e419a  test    eax, eax
0x1800e419c  js      short loc_1800E41F6
0x1800e419e  mov     ecx, 7FFFFFFEh
0x1800e41a3  lea     rdx, [rbp+290h+var_230]
0x1800e41a7  mov     r9, r14
0x1800e41aa  lea     rax, [rbp+290h+var_130]
0x1800e41b1  test    rcx, rcx
0x1800e41b4  jz      short loc_1800E41D5
0x1800e41b6  movzx   r8d, word ptr [rdx]
0x1800e41ba  test    r8w, r8w
0x1800e41be  jz      short loc_1800E41D5
0x1800e41c0  mov     [rax], r8w
0x1800e41c4  add     rdx, 2
0x1800e41c8  add     rax, 2
0x1800e41cc  dec     rcx
0x1800e41cf  sub     r9, 1
0x1800e41d3  jnz     short loc_1800E41B1
0x1800e41d5  test    r9, r9
0x1800e41d8  lea     rcx, [rax-2]
0x1800e41dc  cmovnz  rcx, rax
  ... truncated ...
```
