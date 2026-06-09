# CreateTiffFile(_JOB_QUEUE *,ushort const *,ushort *,ulong)

- ea: `0x14002eb78`
- end: `0x14002efaf`
- name: `?CreateTiffFile@@YAHPEAU_JOB_QUEUE@@PEBGPEAGK@Z`
- size: `1079`
- prototype: `__int64 __fastcall(struct _JOB_QUEUE *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, registry_config`

## callers

- `0x14002efb8`
- `0x14002f168`

## callees

- `0x140002c43`
- `0x140004a30`
- `0x140004b30`
- `0x140004b58`
- `0x140004b98`
- `0x14002e2dc`
- `0x14002eb78`
- `0x140031268`
- `0x1400353dc`
- `0x1400354bc`
- `0x14006dddc`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14002ec5e`
- `KERNEL32!GetLastError` at `0x14002ed3d`
- `KERNEL32!GetLastError` at `0x14002eda5`
- `KERNEL32!GetLastError` at `0x14002ee86`
- `KERNEL32!GetLastError` at `0x14002eedd`
- `KERNEL32!GetLastError` at `0x14002ef6d`
- `KERNEL32!GetLastError` at `0x14002ec5e`
- `KERNEL32!GetLastError` at `0x14002ed3d`
- `KERNEL32!GetLastError` at `0x14002eda5`
- `KERNEL32!GetLastError` at `0x14002ee86`
- `KERNEL32!GetLastError` at `0x14002eedd`
- `KERNEL32!GetLastError` at `0x14002ef6d`
- `KERNEL32!SetLastError` at `0x14002ef65`
- `KERNEL32!SetLastError` at `0x14002ef7a`
- `KERNEL32!SetLastError` at `0x14002ef65`
- `KERNEL32!SetLastError` at `0x14002ef7a`
- `KERNEL32!DeleteFileW` at `0x14002ed73`
- `KERNEL32!DeleteFileW` at `0x14002ef07`
- `KERNEL32!DeleteFileW` at `0x14002ef5c`
- `KERNEL32!DeleteFileW` at `0x14002ed73`
- `KERNEL32!DeleteFileW` at `0x14002ef07`
- `KERNEL32!DeleteFileW` at `0x14002ef5c`
- `KERNEL32!CopyFileW` at `0x14002eebb`
- `KERNEL32!CopyFileW` at `0x14002eebb`
- `FXSTIFF!MergeTiffFiles` at `0x14002ed17`
- `FXSTIFF!MergeTiffFiles` at `0x14002ed17`

## pseudocode

```c
// Hidden C++ exception states: #wind=72 #try_helpers=1
__int64 __fastcall CreateTiffFile(struct _JOB_QUEUE *a1, const unsigned __int16 *a2, unsigned __int16 *a3)
{
  __int64 v6; // rcx
  __int16 v7; // r10
  bool v8; // zf
  struct _JOB_QUEUE *v9; // rbx
  const unsigned __int16 *v10; // rcx
  DWORD LastError; // eax
  __int64 v12; // rdx
  char v13; // al
  char v14; // al
  int v15; // ebx
  CMapDeviceId *v16; // rcx
  __int64 v17; // rdx
  const WCHAR *v18; // rbx
  DWORD v19; // eax
  unsigned int v20; // ebx
  unsigned int v22; // [rsp+40h] [rbp-C0h]
  __int16 v23[8]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR FileName[264]; // [rsp+60h] [rbp-A0h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
  }
  memset_0(FileName, 0, 0x208u);
  v7 = 0;
  v8 = *((_DWORD *)a1 + 9) == 2;
  v23[0] = 0;
  if ( v8 && (v9 = (struct _JOB_QUEUE *)*((_QWORD *)a1 + 73)) != 0 )
  {
    if ( *((_QWORD *)v9 + 23) )
    {
      v10 = (const unsigned __int16 *)*((_QWORD *)v9 + 9);
      if ( v10 )
      {
        if ( !(unsigned int)GetBodyTiffResolution(v10, v23) )
        {
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            LastError = GetLastError();
            v12 = 51;
LABEL_44:
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v12,
              &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
              LastError);
            goto LABEL_58;
          }
          goto LABEL_58;
        }
        v7 = v23[0];
      }
      if ( !(unsigned int)CreateCoverpageTiffFileEx2(
                            v7,
                            *((_DWORD *)a1 + 16),
                            (struct _JOB_QUEUE *)((char *)v9 + 176),
                            (struct _JOB_QUEUE *)((char *)a1 + 448),
                            (struct _JOB_QUEUE *)((char *)v9 + 240),
                            a2,
                            *((const unsigned __int16 **)v9 + 55),
                            FileName,
                            v22) )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_DS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            52,
            (unsigned int)&WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
            *((_DWORD *)a1 + 8),
            *((_QWORD *)v9 + 23));
        }
        goto LABEL_58;
      }
      if ( *((_QWORD *)v9 + 9) && !(unsigned int)MergeTiffFiles(FileName) )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v13 = GetLastError();
          WPP_SF_lSSl(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)FileName, *((_QWORD *)v9 + 9), v13);
        }
        if ( !DeleteFileW(FileName)
          && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v14 = GetLastError();
          WPP_SF_lSl(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            54,
            (unsigned int)&WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
            *((_DWORD *)a1 + 8),
            (__int64)FileName,
            v14);
        }
        goto LABEL_58;
      }
      v15 = StringCchCopyW(a3, 0x104u, FileName);
      if ( v15 < 0 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_57;
        }
        v17 = 55;
LABEL_56:
        WPP_SF_d(*((_QWORD *)v16 + 2), v17, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, (unsigned int)v15);
LABEL_57:
        DeleteFileW(FileName);
        SetLastError((unsigned __int16)v15);
        goto LABEL_58;
      }
      return 1;
    }
  }
  else
  {
    v9 = a1;
  }
  v18 = (const WCHAR *)*((_QWORD *)v9 + 9);
  if ( !a2 )
    a2 = L"tif";
  if ( GenerateUniqueFileNameWithPrefix(v6, *((const wchar_t **)g_pFaxConfig + 12), 0, a2, FileName) )
  {
    if ( !CopyFileW(v18, FileName, 0) )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v19 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, v19);
      }
      DeleteFileW(FileName);
      goto LABEL_58;
    }
    v15 = StringCchCopyW(a3, 0x104u, FileName);
    if ( v15 < 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_57;
      }
      v17 = 50;
      goto LABEL_56;
    }
    return 1;
  }
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    v12 = 48;
    goto LABEL_44;
  }
LABEL_58:
  v20 = 0;
  if ( !GetLastError() )
    SetLastError(0x1Fu);
  return v20;
}

```

## disassembly

```asm
0x14002eb78  mov     [rsp-8+arg_18], rbx
0x14002eb7d  push    rbp
0x14002eb7e  push    rsi
0x14002eb7f  push    rdi
0x14002eb80  push    r13
0x14002eb82  push    r14
0x14002eb84  lea     rbp, [rsp-180h]
0x14002eb8c  sub     rsp, 280h
0x14002eb93  mov     rax, cs:__security_cookie
0x14002eb9a  xor     rax, rsp
0x14002eb9d  mov     [rbp+1A0h+var_30], rax
0x14002eba4  mov     r14, r8
0x14002eba7  mov     rsi, rdx
0x14002ebaa  mov     rdi, rcx
0x14002ebad  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ebb4  lea     r13, WPP_GLOBAL_Control
0x14002ebbb  cmp     rcx, r13
0x14002ebbe  jz      short loc_14002EBE1
0x14002ebc0  test    byte ptr [rcx+1Ch], 4
0x14002ebc4  jz      short loc_14002EBE1
0x14002ebc6  cmp     byte ptr [rcx+19h], 5
0x14002ebca  jb      short loc_14002EBE1
0x14002ebcc  mov     rcx, [rcx+10h]
0x14002ebd0  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002ebd7  mov     edx, 2Fh ; '/'
0x14002ebdc  call    WPP_SF_
0x14002ebe1  xor     edx, edx; Val
0x14002ebe3  lea     rcx, [rsp+2A0h+FileName]; void *
0x14002ebe8  mov     r8d, 208h; Size
0x14002ebee  call    memset_0
0x14002ebf3  xor     r10d, r10d
0x14002ebf6  cmp     dword ptr [rdi+24h], 2
0x14002ebfa  mov     [rsp+2A0h+var_250], r10w
0x14002ec00  jnz     loc_14002EE28
0x14002ec06  mov     rbx, [rdi+248h]
0x14002ec0d  test    rbx, rbx
0x14002ec10  jz      loc_14002EE28
0x14002ec16  cmp     [rbx+0B8h], r10
0x14002ec1d  jz      loc_14002EE2B
0x14002ec23  mov     rcx, [rbx+48h]; unsigned __int16 *
0x14002ec27  test    rcx, rcx
0x14002ec2a  jz      short loc_14002EC74
0x14002ec2c  lea     rdx, [rsp+2A0h+var_250]; __int16 *
0x14002ec31  call    ?GetBodyTiffResolution@@YAHPEBGPEAF@Z; GetBodyTiffResolution(ushort const *,short *)
0x14002ec36  test    eax, eax
0x14002ec38  jnz     short loc_14002EC6E
0x14002ec3a  mov     rax, cs:WPP_GLOBAL_Control
0x14002ec41  cmp     rax, r13
0x14002ec44  jz      loc_14002EF6B
0x14002ec4a  test    byte ptr [rax+1Ch], 4
0x14002ec4e  jz      loc_14002EF6B
0x14002ec54  cmp     byte ptr [rax+19h], 2
0x14002ec58  jb      loc_14002EF6B
0x14002ec5e  call    cs:__imp_GetLastError
0x14002ec64  mov     edx, 33h ; '3'
0x14002ec69  jmp     loc_14002EE91
0x14002ec6e  movzx   r10d, [rsp+2A0h+var_250]
0x14002ec74  mov     edx, [rdi+40h]; unsigned int
0x14002ec77  lea     rcx, [rbx+0F0h]
0x14002ec7e  lea     rax, [rsp+2A0h+FileName]
0x14002ec83  mov     [rsp+2A0h+var_268], rax; unsigned __int16 *
0x14002ec88  lea     r9, [rdi+1C0h]; struct _FAX_PERSONAL_PROFILEW *
0x14002ec8f  mov     rax, [rbx+1B8h]
0x14002ec96  lea     r8, [rbx+0B0h]; struct _FAX_COVERPAGE_INFO_EXW *
0x14002ec9d  mov     [rsp+2A0h+var_270], rax; unsigned __int16 *
0x14002eca2  mov     [rsp+2A0h+var_278], rsi; unsigned __int16 *
0x14002eca7  mov     [rsp+2A0h+var_280], rcx; struct _FAX_PERSONAL_PROFILEW *
0x14002ecac  movzx   ecx, r10w; __int16
0x14002ecb0  call    ?CreateCoverpageTiffFileEx2@@YAHFKPEBU_FAX_COVERPAGE_INFO_EXW@@PEBU_FAX_PERSONAL_PROFILEW@@1PEBG2PEAGK@Z; CreateCoverpageTiffFileEx2(short,ulong,_FAX_COVERPAGE_INFO_EXW const *,_FAX_PERSONAL_PROFILEW const *,_FAX_PERSONAL_PROFILEW const *,ushort const *,ushort const *,ushort *,ulong)
0x14002ecb5  test    eax, eax
0x14002ecb7  jnz     short loc_14002ED05
0x14002ecb9  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ecc0  cmp     rcx, r13
0x14002ecc3  jz      loc_14002EF6B
0x14002ecc9  test    byte ptr [rcx+1Ch], 4
0x14002eccd  jz      loc_14002EF6B
0x14002ecd3  cmp     byte ptr [rcx+19h], 2
0x14002ecd7  jb      loc_14002EF6B
0x14002ecdd  mov     r9d, [rdi+20h]
0x14002ece1  lea     edx, [rax+34h]
0x14002ece4  mov     rax, [rbx+0B8h]
0x14002eceb  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002ecf2  mov     rcx, [rcx+10h]
0x14002ecf6  mov     [rsp+2A0h+var_280], rax
0x14002ecfb  call    WPP_SF_DS
0x14002ed00  jmp     loc_14002EF6B
0x14002ed05  mov     rdx, [rbx+48h]
0x14002ed09  test    rdx, rdx
0x14002ed0c  jz      loc_14002EDDE
0x14002ed12  lea     rcx, [rsp+2A0h+FileName]
0x14002ed17  call    cs:__imp_MergeTiffFiles
0x14002ed1d  test    eax, eax
0x14002ed1f  jnz     loc_14002EDDE
0x14002ed25  mov     rax, cs:WPP_GLOBAL_Control
0x14002ed2c  cmp     rax, r13
0x14002ed2f  jz      short loc_14002ED6E
0x14002ed31  test    byte ptr [rax+1Ch], 4
0x14002ed35  jz      short loc_14002ED6E
0x14002ed37  cmp     byte ptr [rax+19h], 2
0x14002ed3b  jb      short loc_14002ED6E
0x14002ed3d  call    cs:__imp_GetLastError
0x14002ed43  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ed4a  mov     r9d, [rdi+20h]
0x14002ed4e  mov     dword ptr [rsp+2A0h+var_270], eax; char
0x14002ed52  mov     rax, [rbx+48h]
0x14002ed56  mov     rcx, [rcx+10h]; LoggerHandle
0x14002ed5a  mov     [rsp+2A0h+var_278], rax; __int64
0x14002ed5f  lea     rax, [rsp+2A0h+FileName]
0x14002ed64  mov     [rsp+2A0h+var_280], rax; __int64
0x14002ed69  call    WPP_SF_lSSl
0x14002ed6e  lea     rcx, [rsp+2A0h+FileName]; lpFileName
0x14002ed73  call    cs:__imp_DeleteFileW
0x14002ed79  test    eax, eax
0x14002ed7b  jnz     loc_14002EF6B
0x14002ed81  mov     rax, cs:WPP_GLOBAL_Control
0x14002ed88  cmp     rax, r13
0x14002ed8b  jz      loc_14002EF6B
0x14002ed91  test    byte ptr [rax+1Ch], 4
0x14002ed95  jz      loc_14002EF6B
0x14002ed9b  cmp     byte ptr [rax+19h], 2
0x14002ed9f  jb      loc_14002EF6B
0x14002eda5  call    cs:__imp_GetLastError
0x14002edab  mov     rcx, cs:WPP_GLOBAL_Control
0x14002edb2  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002edb9  mov     r9d, [rdi+20h]
0x14002edbd  mov     edx, 36h ; '6'
0x14002edc2  mov     dword ptr [rsp+2A0h+var_278], eax
0x14002edc6  lea     rax, [rsp+2A0h+FileName]
0x14002edcb  mov     [rsp+2A0h+var_280], rax
0x14002edd0  mov     rcx, [rcx+10h]
0x14002edd4  call    WPP_SF_lSl
0x14002edd9  jmp     loc_14002EF6B
0x14002edde  lea     r8, [rsp+2A0h+FileName]; unsigned __int16 *
0x14002ede3  mov     edx, 104h; unsigned __int64
0x14002ede8  mov     rcx, r14; unsigned __int16 *
0x14002edeb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14002edf0  mov     ebx, eax
0x14002edf2  test    eax, eax
0x14002edf4  jns     loc_14002EF82
0x14002edfa  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ee01  cmp     rcx, r13
0x14002ee04  jz      loc_14002EF57
0x14002ee0a  test    byte ptr [rcx+1Ch], 4
0x14002ee0e  jz      loc_14002EF57
0x14002ee14  cmp     byte ptr [rcx+19h], 2
0x14002ee18  jb      loc_14002EF57
0x14002ee1e  mov     edx, 37h ; '7'
0x14002ee23  jmp     loc_14002EF44
0x14002ee28  mov     rbx, rdi
0x14002ee2b  mov     rdx, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x14002ee32  lea     rax, aTif; "tif"
0x14002ee39  mov     rbx, [rbx+48h]
0x14002ee3d  test    rsi, rsi
0x14002ee40  cmovz   rsi, rax
0x14002ee44  lea     rax, [rsp+2A0h+FileName]
0x14002ee49  mov     rdx, [rdx+60h]
0x14002ee4d  mov     r9, rsi
0x14002ee50  xor     r8d, r8d
0x14002ee53  mov     [rsp+2A0h+var_280], rax
0x14002ee58  call    GenerateUniqueFileNameWithPrefix
0x14002ee5d  test    rax, rax
0x14002ee60  jnz     short loc_14002EEB0
0x14002ee62  mov     rax, cs:WPP_GLOBAL_Control
0x14002ee69  cmp     rax, r13
0x14002ee6c  jz      loc_14002EF6B
0x14002ee72  test    byte ptr [rax+1Ch], 4
0x14002ee76  jz      loc_14002EF6B
0x14002ee7c  cmp     byte ptr [rax+19h], 2
0x14002ee80  jb      loc_14002EF6B
0x14002ee86  call    cs:__imp_GetLastError
0x14002ee8c  mov     edx, 30h ; '0'
0x14002ee91  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ee98  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002ee9f  mov     r9d, eax
0x14002eea2  mov     rcx, [rcx+10h]
0x14002eea6  call    WPP_SF_d
0x14002eeab  jmp     loc_14002EF6B
0x14002eeb0  xor     r8d, r8d; bFailIfExists
0x14002eeb3  lea     rdx, [rsp+2A0h+FileName]; lpNewFileName
0x14002eeb8  mov     rcx, rbx; lpExistingFileName
0x14002eebb  call    cs:__imp_CopyFileW
0x14002eec1  test    eax, eax
0x14002eec3  jnz     short loc_14002EF0F
0x14002eec5  mov     rax, cs:WPP_GLOBAL_Control
0x14002eecc  cmp     rax, r13
0x14002eecf  jz      short loc_14002EF02
0x14002eed1  test    byte ptr [rax+1Ch], 4
0x14002eed5  jz      short loc_14002EF02
0x14002eed7  cmp     byte ptr [rax+19h], 2
0x14002eedb  jb      short loc_14002EF02
0x14002eedd  call    cs:__imp_GetLastError
0x14002eee3  mov     rcx, cs:WPP_GLOBAL_Control
0x14002eeea  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002eef1  mov     edx, 31h ; '1'
0x14002eef6  mov     r9d, eax
0x14002eef9  mov     rcx, [rcx+10h]
0x14002eefd  call    WPP_SF_d
0x14002ef02  lea     rcx, [rsp+2A0h+FileName]; lpFileName
0x14002ef07  call    cs:__imp_DeleteFileW
0x14002ef0d  jmp     short loc_14002EF6B
0x14002ef0f  lea     r8, [rsp+2A0h+FileName]; unsigned __int16 *
0x14002ef14  mov     edx, 104h; unsigned __int64
0x14002ef19  mov     rcx, r14; unsigned __int16 *
0x14002ef1c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14002ef21  mov     ebx, eax
0x14002ef23  test    eax, eax
0x14002ef25  jns     short loc_14002EF82
0x14002ef27  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ef2e  cmp     rcx, r13
0x14002ef31  jz      short loc_14002EF57
0x14002ef33  test    byte ptr [rcx+1Ch], 4
0x14002ef37  jz      short loc_14002EF57
0x14002ef39  cmp     byte ptr [rcx+19h], 2
0x14002ef3d  jb      short loc_14002EF57
0x14002ef3f  mov     edx, 32h ; '2'
0x14002ef44  mov     rcx, [rcx+10h]
0x14002ef48  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002ef4f  mov     r9d, ebx
0x14002ef52  call    WPP_SF_d
0x14002ef57  lea     rcx, [rsp+2A0h+FileName]; lpFileName
0x14002ef5c  call    cs:__imp_DeleteFileW
0x14002ef62  movzx   ecx, bx; dwErrCode
0x14002ef65  call    cs:__imp_SetLastError
0x14002ef6b  xor     ebx, ebx
0x14002ef6d  call    cs:__imp_GetLastError
0x14002ef73  test    eax, eax
0x14002ef75  jnz     short loc_14002EF87
0x14002ef77  lea     ecx, [rbx+1Fh]; dwErrCode
0x14002ef7a  call    cs:__imp_SetLastError
0x14002ef80  jmp     short loc_14002EF87
0x14002ef82  mov     ebx, 1
0x14002ef87  mov     eax, ebx
0x14002ef89  mov     rcx, [rbp+1A0h+var_30]
0x14002ef90  xor     rcx, rsp; StackCookie
0x14002ef93  call    __security_check_cookie
0x14002ef98  mov     rbx, [rsp+2A0h+arg_18]
0x14002efa0  add     rsp, 280h
0x14002efa7  pop     r14
0x14002efa9  pop     r13
0x14002efab  pop     rdi
0x14002efac  pop     rsi
0x14002efad  pop     rbp
0x14002efae  retn
```
