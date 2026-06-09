# TryDeleteMoveCopyFileForRecoveryOrBackup(ushort *,ushort *,RECOVERY_FILE_ACTION,ushort *)

- ea: `0x140036aa8`
- end: `0x1400370f1`
- name: `?TryDeleteMoveCopyFileForRecoveryOrBackup@@YAXPEAG0W4RECOVERY_FILE_ACTION@@0@Z`
- size: `1609`
- prototype: `_UNKNOWN **__fastcall(__int64, __int64, int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x14001a270`
- `0x1400370f8`

## callees

- `0x140009904`
- `0x140009a04`
- `0x140009af0`
- `0x140009c08`
- `0x1400163c0`
- `0x140017cd4`
- `0x140036aa8`
- `0x14003fbb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140036ec0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140036f34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003702b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140036ec0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140036f34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003702b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140036faa`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140036faa`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x140036e52`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x140036e52`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x140036ecd`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x140036ecd`

## pseudocode

```c
_UNKNOWN **__fastcall TryDeleteMoveCopyFileForRecoveryOrBackup(
        __int64 a1,
        __int64 a2,
        int a3,
        const unsigned __int16 *a4)
{
  const unsigned __int16 *v4; // rdi
  __int64 v7; // rbx
  _WORD *v8; // rax
  __int64 v9; // rcx
  unsigned int v10; // r8d
  __int64 v11; // r8
  __int64 v12; // rdx
  const unsigned __int16 *v13; // rax
  unsigned int v14; // ecx
  __int64 v15; // r13
  _UNKNOWN **result; // rax
  __int64 v17; // r12
  WCHAR *v18; // r8
  __int64 v19; // rax
  WCHAR *v20; // rcx
  unsigned __int64 v21; // rdx
  WCHAR *v22; // rcx
  unsigned int v23; // r9d
  _QWORD *v24; // rcx
  int v25; // edx
  __int64 v26; // rcx
  int v27; // r8d
  __int64 v28; // rdx
  _WORD *v29; // rax
  WCHAR *v30; // rax
  WCHAR *v31; // rdx
  WCHAR *v32; // rcx
  signed int v33; // r8d
  _QWORD *v34; // rcx
  int v35; // edx
  _QWORD *v36; // rcx
  __int64 v37; // rdx
  WCHAR *v38; // r9
  DWORD LastError; // eax
  int v40; // edx
  WCHAR *v41; // rcx
  _QWORD *v42; // rcx
  int v43; // edx
  int v44; // r9d
  char v45; // [rsp+28h] [rbp-D8h]
  WCHAR NewFileName[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR ExistingFileName[264]; // [rsp+250h] [rbp+150h] BYREF

  v4 = a4;
  if ( !a1 )
  {
    LOBYTE(v10) = 87;
LABEL_107:
    v42 = WPP_GLOBAL_Control;
    result = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return result;
    }
    v43 = 10;
    v44 = a1;
    return (_UNKNOWN **)WPP_SF_Sd(v42[2], v43, (unsigned int)WPP_35806d468ac3359b7b679ca6b7a243e6_Traceguids, v44, v10);
  }
  v7 = 260;
  v8 = (_WORD *)a1;
  v9 = 260;
  do
  {
    if ( !*v8 )
      break;
    ++v8;
    --v9;
  }
  while ( v9 );
  v10 = v9 == 0 ? 0x80070057 : 0;
  if ( !v9 )
    goto LABEL_107;
  v11 = (2 * (260 - v9)) & -(__int64)(v9 != 0);
  if ( !a4 )
  {
    LOBYTE(v14) = 87;
LABEL_100:
    result = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return result;
    }
    v45 = v14;
    v25 = 11;
    v26 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    return (_UNKNOWN **)WPP_SF_SSd(
                          v26,
                          v25,
                          (unsigned int)WPP_35806d468ac3359b7b679ca6b7a243e6_Traceguids,
                          (_DWORD)a4,
                          a1,
                          v45);
  }
  v12 = 260;
  v13 = a4;
  do
  {
    if ( !*v13 )
      break;
    ++v13;
    --v12;
  }
  while ( v12 );
  v14 = v12 == 0 ? 0x80070057 : 0;
  if ( !v12 )
    goto LABEL_100;
  v15 = (2 * (260 - v12)) & -(__int64)(v12 != 0);
  if ( (unsigned __int64)(v11 + v15) >= 0x206 )
  {
    result = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      return (_UNKNOWN **)WPP_SF_SS(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            12,
                            (unsigned int)WPP_35806d468ac3359b7b679ca6b7a243e6_Traceguids,
                            (_DWORD)a4,
                            a1);
    }
    return result;
  }
  v17 = 2147483646;
  v18 = ExistingFileName;
  v19 = 2147483646;
  v20 = (WCHAR *)a1;
  v21 = 260;
  do
  {
    if ( !v19 )
      break;
    if ( !*v20 )
      break;
    *v18++ = *v20++;
    --v19;
    --v21;
  }
  while ( v21 );
  v22 = v18 - 1;
  v23 = v21 == 0 ? 0x8007007A : 0;
  if ( v21 )
    v22 = v18;
  *v22 = 0;
  if ( !v21 )
  {
    v24 = WPP_GLOBAL_Control;
    result = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return result;
    }
    v25 = 13;
    v45 = v23;
LABEL_28:
    v26 = v24[2];
    LODWORD(a4) = (_DWORD)v4;
    return (_UNKNOWN **)WPP_SF_SSd(
                          v26,
                          v25,
                          (unsigned int)WPP_35806d468ac3359b7b679ca6b7a243e6_Traceguids,
                          (_DWORD)a4,
                          a1,
                          v45);
  }
  v27 = StringCbCatW(ExistingFileName, v21, v4);
  if ( v27 < 0 )
  {
    v24 = WPP_GLOBAL_Control;
    result = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return result;
    }
    v25 = 14;
    v45 = v27;
    goto LABEL_28;
  }
  if ( !a3 )
  {
    if ( DeleteFileW(ExistingFileName) )
    {
      v36 = WPP_GLOBAL_Control;
      result = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
      {
        return result;
      }
      v37 = 23;
      v38 = ExistingFileName;
      return (_UNKNOWN **)WPP_SF_S(v36[2], v37, WPP_35806d468ac3359b7b679ca6b7a243e6_Traceguids, v38);
    }
    result = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return result;
    }
    LastError = GetLastError();
    v40 = 24;
    v41 = ExistingFileName;
    return (_UNKNOWN **)WPP_SF_DS(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          v40,
                          (unsigned int)WPP_35806d468ac3359b7b679ca6b7a243e6_Traceguids,
                          LastError,
                          (__int64)v41);
  }
  if ( !a2 )
  {
    LOBYTE(v10) = 87;
LABEL_85:
    v42 = WPP_GLOBAL_Control;
    result = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return result;
    }
    v43 = 15;
    v44 = a2;
    return (_UNKNOWN **)WPP_SF_Sd(v42[2], v43, (unsigned int)WPP_35806d468ac3359b7b679ca6b7a243e6_Traceguids, v44, v10);
  }
  v28 = 260;
  v29 = (_WORD *)a2;
  do
  {
    if ( !*v29 )
      break;
    ++v29;
    --v28;
  }
  while ( v28 );
  v10 = v28 == 0 ? 0x80070057 : 0;
  if ( !v28 )
    goto LABEL_85;
  if ( v15 + ((2 * (260 - v28)) & (unsigned __int64)-(__int64)(v28 != 0)) < 0x206 )
  {
    v30 = (WCHAR *)a2;
    v31 = NewFileName;
    do
    {
      if ( !v17 )
        break;
      if ( !*v30 )
        break;
      *v31++ = *v30++;
      --v17;
      --v7;
    }
    while ( v7 );
    v32 = v31 - 1;
    v33 = v7 == 0 ? 0x8007007A : 0;
    if ( v7 )
      v32 = v31;
    *v32 = 0;
    if ( !v7 )
    {
      v34 = WPP_GLOBAL_Control;
      result = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return result;
      }
      v35 = 17;
      return (_UNKNOWN **)WPP_SF_SSd(
                            v34[2],
                            v35,
                            (unsigned int)WPP_35806d468ac3359b7b679ca6b7a243e6_Traceguids,
                            (_DWORD)v4,
                            a2,
                            v33);
    }
    v33 = StringCbCatW(NewFileName, (unsigned __int64)v31, v4);
    if ( v33 < 0 )
    {
      v34 = WPP_GLOBAL_Control;
      result = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return result;
      }
      v35 = 18;
      return (_UNKNOWN **)WPP_SF_SSd(
                            v34[2],
                            v35,
                            (unsigned int)WPP_35806d468ac3359b7b679ca6b7a243e6_Traceguids,
                            (_DWORD)v4,
                            a2,
                            v33);
    }
    if ( a3 == 2 )
    {
      if ( CopyFileW(ExistingFileName, NewFileName, 0) )
      {
        v36 = WPP_GLOBAL_Control;
        result = &WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
        {
          return result;
        }
        v37 = 19;
LABEL_68:
        v38 = NewFileName;
        return (_UNKNOWN **)WPP_SF_S(v36[2], v37, WPP_35806d468ac3359b7b679ca6b7a243e6_Traceguids, v38);
      }
      result = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return result;
      }
      LastError = GetLastError();
      v40 = 20;
    }
    else
    {
      if ( MoveFileW(ExistingFileName, NewFileName) )
      {
        v36 = WPP_GLOBAL_Control;
        result = &WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
        {
          return result;
        }
        v37 = 21;
        goto LABEL_68;
      }
      result = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return result;
      }
      LastError = GetLastError();
      v40 = 22;
    }
    v41 = NewFileName;
    return (_UNKNOWN **)WPP_SF_DS(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          v40,
                          (unsigned int)WPP_35806d468ac3359b7b679ca6b7a243e6_Traceguids,
                          LastError,
                          (__int64)v41);
  }
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    return (_UNKNOWN **)WPP_SF_SS(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          16,
                          (unsigned int)WPP_35806d468ac3359b7b679ca6b7a243e6_Traceguids,
                          (_DWORD)v4,
                          a2);
  }
  return result;
}

```

## disassembly

```asm
0x140036aa8  mov     [rsp-8+arg_10], rbx
0x140036aad  push    rbp
0x140036aae  push    rsi
0x140036aaf  push    rdi
0x140036ab0  push    r12
0x140036ab2  push    r13
0x140036ab4  push    r14
0x140036ab6  push    r15
0x140036ab8  lea     rbp, [rsp-370h]
0x140036ac0  sub     rsp, 470h
0x140036ac7  mov     rax, cs:__security_cookie
0x140036ace  xor     rax, rsp
0x140036ad1  mov     [rbp+3A0h+var_40], rax
0x140036ad8  xor     r10d, r10d
0x140036adb  mov     [rsp+4A0h+var_470], r8d
0x140036ae0  mov     rdi, r9
0x140036ae3  mov     r15, rdx
0x140036ae6  mov     r14, rcx
0x140036ae9  test    rcx, rcx
0x140036aec  jz      loc_140037085
0x140036af2  mov     ebx, 104h
0x140036af7  mov     rax, r14
0x140036afa  mov     ecx, ebx
0x140036afc  cmp     [rax], r10w
0x140036b00  jz      short loc_140036B0C
0x140036b02  add     rax, 2
0x140036b06  sub     rcx, 1
0x140036b0a  jnz     short loc_140036AFC
0x140036b0c  mov     rax, rcx
0x140036b0f  mov     esi, 80070057h
0x140036b14  neg     rax
0x140036b17  sbb     r8d, r8d
0x140036b1a  not     r8d
0x140036b1d  and     r8d, esi
0x140036b20  test    rcx, rcx
0x140036b23  jz      loc_14003708B
0x140036b29  mov     rax, rbx
0x140036b2c  sub     rax, rcx
0x140036b2f  add     rax, rax
0x140036b32  neg     rcx
0x140036b35  sbb     r8, r8
0x140036b38  and     r8, rax
0x140036b3b  test    rdi, rdi
0x140036b3e  jz      loc_140037042
0x140036b44  mov     rdx, rbx
0x140036b47  mov     rax, rdi
0x140036b4a  cmp     [rax], r10w
0x140036b4e  jz      short loc_140036B5A
0x140036b50  add     rax, 2
0x140036b54  sub     rdx, 1
0x140036b58  jnz     short loc_140036B4A
0x140036b5a  mov     rax, rdx
0x140036b5d  neg     rax
0x140036b60  sbb     ecx, ecx
0x140036b62  not     ecx
0x140036b64  and     ecx, esi
0x140036b66  test    rdx, rdx
0x140036b69  jz      loc_140037044
0x140036b6f  mov     rax, rbx
0x140036b72  sub     rax, rdx
0x140036b75  add     rax, rax
0x140036b78  neg     rdx
0x140036b7b  sbb     r13, r13
0x140036b7e  and     r13, rax
0x140036b81  lea     rax, [r8+r13]
0x140036b85  cmp     rax, 206h
0x140036b8b  jb      short loc_140036BD7
0x140036b8d  mov     rcx, cs:WPP_GLOBAL_Control
0x140036b94  lea     rax, WPP_GLOBAL_Control
0x140036b9b  cmp     rcx, rax
0x140036b9e  jz      loc_1400370C7
0x140036ba4  test    byte ptr [rcx+1Ch], 1
0x140036ba8  jz      loc_1400370C7
0x140036bae  cmp     byte ptr [rcx+19h], 2
0x140036bb2  jb      loc_1400370C7
0x140036bb8  mov     edx, 0Ch
0x140036bbd  mov     [rsp+4A0h+var_480], r14
0x140036bc2  mov     rcx, [rcx+10h]
0x140036bc6  lea     r8, WPP_35806d468ac3359b7b679ca6b7a243e6_Traceguids
0x140036bcd  call    WPP_SF_SS
0x140036bd2  jmp     loc_1400370C7
0x140036bd7  mov     r12d, 7FFFFFFEh
0x140036bdd  lea     r8, [rbp+3A0h+ExistingFileName]
0x140036be4  mov     eax, r12d
0x140036be7  mov     rcx, r14
0x140036bea  mov     rdx, rbx
0x140036bed  test    rax, rax
0x140036bf0  jz      short loc_140036C11
0x140036bf2  movzx   r9d, word ptr [rcx]
0x140036bf6  test    r9w, r9w
0x140036bfa  jz      short loc_140036C11
0x140036bfc  mov     [r8], r9w
0x140036c00  add     rcx, 2
0x140036c04  add     r8, 2
0x140036c08  dec     rax
0x140036c0b  sub     rdx, 1; unsigned __int64
0x140036c0f  jnz     short loc_140036BED
0x140036c11  mov     rax, rdx
0x140036c14  lea     rcx, [r8-2]
0x140036c18  neg     rax
0x140036c1b  sbb     r9d, r9d
0x140036c1e  not     r9d
0x140036c21  and     r9d, 8007007Ah
0x140036c28  test    rdx, rdx
0x140036c2b  cmovnz  rcx, r8
0x140036c2f  mov     [rcx], r10w
0x140036c33  jnz     short loc_140036C76
0x140036c35  mov     rcx, cs:WPP_GLOBAL_Control
0x140036c3c  lea     rax, WPP_GLOBAL_Control
0x140036c43  cmp     rcx, rax
0x140036c46  jz      loc_1400370C7
0x140036c4c  test    byte ptr [rcx+1Ch], 1
0x140036c50  jz      loc_1400370C7
0x140036c56  cmp     byte ptr [rcx+19h], 2
0x140036c5a  jb      loc_1400370C7
0x140036c60  mov     edx, 0Dh
0x140036c65  mov     dword ptr [rsp+4A0h+var_478], r9d
0x140036c6a  mov     rcx, [rcx+10h]
0x140036c6e  mov     r9, rdi
0x140036c71  jmp     loc_140037072
0x140036c76  mov     r8, rdi; unsigned __int16 *
0x140036c79  lea     rcx, [rbp+3A0h+ExistingFileName]; unsigned __int16 *
0x140036c80  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x140036c85  xor     r9d, r9d
0x140036c88  mov     r8d, eax
0x140036c8b  test    eax, eax
0x140036c8d  jns     short loc_140036CC5
0x140036c8f  mov     rcx, cs:WPP_GLOBAL_Control
0x140036c96  lea     rax, WPP_GLOBAL_Control
0x140036c9d  cmp     rcx, rax
0x140036ca0  jz      loc_1400370C7
0x140036ca6  test    byte ptr [rcx+1Ch], 1
0x140036caa  jz      loc_1400370C7
0x140036cb0  cmp     byte ptr [rcx+19h], 2
0x140036cb4  jb      loc_1400370C7
0x140036cba  lea     edx, [r9+0Eh]
0x140036cbe  mov     dword ptr [rsp+4A0h+var_478], r8d
0x140036cc3  jmp     short loc_140036C6A
0x140036cc5  mov     r14d, [rsp+4A0h+var_470]
0x140036cca  test    r14d, r14d
0x140036ccd  jz      loc_140036FA3
0x140036cd3  test    r15, r15
0x140036cd6  jz      loc_140036F68
0x140036cdc  mov     rdx, rbx
0x140036cdf  mov     rax, r15
0x140036ce2  cmp     [rax], r9w
0x140036ce6  jz      short loc_140036CF2
0x140036ce8  add     rax, 2
0x140036cec  sub     rdx, 1
0x140036cf0  jnz     short loc_140036CE2
0x140036cf2  mov     rax, rdx
0x140036cf5  neg     rax
0x140036cf8  sbb     r8d, r8d
0x140036cfb  not     r8d
0x140036cfe  and     r8d, esi
0x140036d01  test    rdx, rdx
0x140036d04  jz      loc_140036F6B
0x140036d0a  mov     rcx, rbx
0x140036d0d  sub     rcx, rdx
0x140036d10  add     rcx, rcx
0x140036d13  neg     rdx
0x140036d16  sbb     rax, rax
0x140036d19  and     rax, rcx
0x140036d1c  add     rax, r13
0x140036d1f  cmp     rax, 206h
0x140036d25  jb      short loc_140036D64
0x140036d27  mov     rcx, cs:WPP_GLOBAL_Control
0x140036d2e  lea     rax, WPP_GLOBAL_Control
0x140036d35  cmp     rcx, rax
0x140036d38  jz      loc_1400370C7
0x140036d3e  test    byte ptr [rcx+1Ch], 1
0x140036d42  jz      loc_1400370C7
0x140036d48  cmp     byte ptr [rcx+19h], 2
0x140036d4c  jb      loc_1400370C7
0x140036d52  mov     edx, 10h
0x140036d57  mov     [rsp+4A0h+var_480], r15
0x140036d5c  mov     r9, rdi
0x140036d5f  jmp     loc_140036BC2
0x140036d64  mov     rax, r15
0x140036d67  lea     rdx, [rsp+4A0h+NewFileName]
0x140036d6c  test    r12, r12
0x140036d6f  jz      short loc_140036D8D
0x140036d71  movzx   ecx, word ptr [rax]
0x140036d74  test    cx, cx
0x140036d77  jz      short loc_140036D8D
0x140036d79  mov     [rdx], cx
0x140036d7c  add     rax, 2
0x140036d80  add     rdx, 2; unsigned __int64
0x140036d84  dec     r12
0x140036d87  sub     rbx, 1
0x140036d8b  jnz     short loc_140036D6C
0x140036d8d  mov     rax, rbx
0x140036d90  lea     rcx, [rdx-2]
0x140036d94  neg     rax
0x140036d97  sbb     r8d, r8d
0x140036d9a  not     r8d
0x140036d9d  and     r8d, 8007007Ah
0x140036da4  test    rbx, rbx
0x140036da7  cmovnz  rcx, rdx
0x140036dab  mov     [rcx], r9w
0x140036daf  jnz     short loc_140036DF7
0x140036db1  mov     rcx, cs:WPP_GLOBAL_Control
0x140036db8  lea     rax, WPP_GLOBAL_Control
0x140036dbf  cmp     rcx, rax
0x140036dc2  jz      loc_1400370C7
0x140036dc8  test    byte ptr [rcx+1Ch], 1
0x140036dcc  jz      loc_1400370C7
0x140036dd2  cmp     byte ptr [rcx+19h], 2
0x140036dd6  jb      loc_1400370C7
0x140036ddc  mov     edx, 11h
0x140036de1  mov     rcx, [rcx+10h]
0x140036de5  mov     r9, rdi
0x140036de8  mov     dword ptr [rsp+4A0h+var_478], r8d
0x140036ded  mov     [rsp+4A0h+var_480], r15
0x140036df2  jmp     loc_140037077
0x140036df7  mov     r8, rdi; unsigned __int16 *
0x140036dfa  lea     rcx, [rsp+4A0h+NewFileName]; unsigned __int16 *
0x140036dff  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x140036e04  mov     r8d, eax
0x140036e07  test    eax, eax
0x140036e09  jns     short loc_140036E3D
0x140036e0b  mov     rcx, cs:WPP_GLOBAL_Control
0x140036e12  lea     rax, WPP_GLOBAL_Control
0x140036e19  cmp     rcx, rax
0x140036e1c  jz      loc_1400370C7
0x140036e22  test    byte ptr [rcx+1Ch], 1
0x140036e26  jz      loc_1400370C7
0x140036e2c  cmp     byte ptr [rcx+19h], 2
0x140036e30  jb      loc_1400370C7
0x140036e36  mov     edx, 12h
0x140036e3b  jmp     short loc_140036DE1
0x140036e3d  lea     rdx, [rsp+4A0h+NewFileName]; lpNewFileName
0x140036e42  lea     rcx, [rbp+3A0h+ExistingFileName]; lpExistingFileName
0x140036e49  cmp     r14d, 2
0x140036e4d  jnz     short loc_140036ECD
0x140036e4f  xor     r8d, r8d; bFailIfExists
0x140036e52  call    cs:__imp_CopyFileW
0x140036e58  test    eax, eax
0x140036e5a  jz      short loc_140036E95
0x140036e5c  mov     rcx, cs:WPP_GLOBAL_Control
0x140036e63  lea     rax, WPP_GLOBAL_Control
0x140036e6a  cmp     rcx, rax
0x140036e6d  jz      loc_1400370C7
0x140036e73  test    byte ptr [rcx+1Ch], 1
0x140036e77  jz      loc_1400370C7
0x140036e7d  cmp     byte ptr [rcx+19h], 4
0x140036e81  jb      loc_1400370C7
0x140036e87  lea     edx, [r14+11h]
0x140036e8b  lea     r9, [rsp+4A0h+NewFileName]
0x140036e90  jmp     loc_140036FEB
0x140036e95  mov     rcx, cs:WPP_GLOBAL_Control
0x140036e9c  lea     rax, WPP_GLOBAL_Control
0x140036ea3  cmp     rcx, rax
0x140036ea6  jz      loc_1400370C7
0x140036eac  test    byte ptr [rcx+1Ch], 1
0x140036eb0  jz      loc_1400370C7
0x140036eb6  cmp     byte ptr [rcx+19h], 2
0x140036eba  jb      loc_1400370C7
0x140036ec0  call    cs:__imp_GetLastError
0x140036ec6  mov     edx, 14h
0x140036ecb  jmp     short loc_140036F3F
0x140036ecd  call    cs:__imp_MoveFileW
0x140036ed3  test    eax, eax
0x140036ed5  jz      short loc_140036F09
0x140036ed7  mov     rcx, cs:WPP_GLOBAL_Control
0x140036ede  lea     rax, WPP_GLOBAL_Control
0x140036ee5  cmp     rcx, rax
0x140036ee8  jz      loc_1400370C7
0x140036eee  test    byte ptr [rcx+1Ch], 1
0x140036ef2  jz      loc_1400370C7
0x140036ef8  cmp     byte ptr [rcx+19h], 4
0x140036efc  jb      loc_1400370C7
0x140036f02  mov     edx, 15h
0x140036f07  jmp     short loc_140036E8B
0x140036f09  mov     rcx, cs:WPP_GLOBAL_Control
0x140036f10  lea     rax, WPP_GLOBAL_Control
0x140036f17  cmp     rcx, rax
0x140036f1a  jz      loc_1400370C7
0x140036f20  test    byte ptr [rcx+1Ch], 1
0x140036f24  jz      loc_1400370C7
0x140036f2a  cmp     byte ptr [rcx+19h], 2
0x140036f2e  jb      loc_1400370C7
0x140036f34  call    cs:__imp_GetLastError
0x140036f3a  mov     edx, 16h
0x140036f3f  lea     rcx, [rsp+4A0h+NewFileName]
0x140036f44  mov     [rsp+4A0h+var_480], rcx
0x140036f49  lea     r8, WPP_35806d468ac3359b7b679ca6b7a243e6_Traceguids
0x140036f50  mov     rcx, cs:WPP_GLOBAL_Control
0x140036f57  mov     r9d, eax
0x140036f5a  mov     rcx, [rcx+10h]
0x140036f5e  call    WPP_SF_DS
0x140036f63  jmp     loc_1400370C7
0x140036f68  mov     r8d, esi
0x140036f6b  mov     rcx, cs:WPP_GLOBAL_Control
0x140036f72  lea     rax, WPP_GLOBAL_Control
0x140036f79  cmp     rcx, rax
0x140036f7c  jz      loc_1400370C7
0x140036f82  test    byte ptr [rcx+1Ch], 1
0x140036f86  jz      loc_1400370C7
0x140036f8c  cmp     byte ptr [rcx+19h], 2
  ... truncated ...
```
