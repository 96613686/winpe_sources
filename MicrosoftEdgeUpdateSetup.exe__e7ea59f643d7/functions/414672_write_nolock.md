# __write_nolock

- ea: `0x414672`
- end: `0x41484c`
- name: `__write_nolock`
- size: `474`
- prototype: `int __cdecl(int FileHandle, _BYTE *, DWORD)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x414580`

## callees

- `0x40ec26`
- `0x40ecad`
- `0x40ecd0`
- `0x40ece3`
- `0x413e05`
- `0x4141b1`
- `0x414219`
- `0x41428a`
- `0x414365`
- `0x41444e`
- `0x414672`
- `0x4168dd`

## import_xrefs

- `KERNEL32!WriteFile` at `0x4147b8`
- `KERNEL32!WriteFile` at `0x4147b8`
- `KERNEL32!GetLastError` at `0x4147c2`
- `KERNEL32!GetLastError` at `0x4147c2`

## pseudocode

```c
int __cdecl _write_nolock(int FileHandle, _BYTE *a2, DWORD a3)
{
  _BYTE *v3; // edi
  int v5; // eax
  int v6; // edx
  char v7; // bl
  DWORD *v8; // eax
  unsigned int *p_LastError; // esi
  int v10; // ecx
  void *v11; // ecx
  int *v12; // esi
  DWORD LastError; // [esp+Ch] [ebp-28h] BYREF
  DWORD NumberOfBytesWritten; // [esp+10h] [ebp-24h] BYREF
  int v15; // [esp+14h] [ebp-20h]
  unsigned int v16; // [esp+18h] [ebp-1Ch]
  int v17; // [esp+1Ch] [ebp-18h]
  int v18; // [esp+20h] [ebp-14h]
  int v19; // [esp+24h] [ebp-10h]
  LPCVOID lpBuffer; // [esp+28h] [ebp-Ch]
  int v21; // [esp+2Ch] [ebp-8h]
  DWORD nNumberOfBytesToWrite; // [esp+30h] [ebp-4h]

  nNumberOfBytesToWrite = a3;
  v3 = a2;
  lpBuffer = a2;
  if ( a3 )
  {
    if ( !a2 )
    {
LABEL_3:
      *__doserrno() = 0;
      *_errno() = 22;
      _invalid_parameter_noinfo();
      return -1;
    }
    v5 = 56 * (FileHandle & 0x3F);
    v19 = FileHandle >> 6;
    v6 = dword_427018[FileHandle >> 6];
    v21 = v5;
    v7 = *(_BYTE *)(v6 + v5 + 41);
    if ( v7 == 2 || v7 == 1 )
    {
      if ( (a3 & 1) != 0 )
        goto LABEL_3;
      v5 = v21;
    }
    if ( (*(_BYTE *)(v6 + v5 + 40) & 0x20) != 0 )
      _lseeki64_nolock(FileHandle, 0, 2u);
    if ( write_requires_double_translation_nolock(FileHandle) )
    {
      if ( !v7 )
      {
        v8 = write_double_translated_ansi_nolock(&LastError, FileHandle, a2, nNumberOfBytesToWrite);
        goto LABEL_15;
      }
      if ( (unsigned __int8)(v7 - 1) <= 1u )
      {
        v8 = write_double_translated_unicode_nolock(&LastError, (unsigned int)a2, nNumberOfBytesToWrite);
LABEL_15:
        p_LastError = v8;
LABEL_28:
        v16 = *p_LastError;
        v12 = (int *)(p_LastError + 1);
        v17 = *v12;
        v18 = v12[1];
        if ( v17 )
          return v17 - v18;
        if ( v16 )
        {
          if ( v16 == 5 )
          {
            *_errno() = 9;
            *__doserrno() = 5;
          }
          else
          {
            __acrt_errno_map_os_error(v16);
          }
          return -1;
        }
        v3 = lpBuffer;
      }
    }
    else
    {
      v10 = dword_427018[v19];
      if ( *(char *)(v10 + v21 + 40) >= 0 )
      {
        v11 = *(void **)(v10 + v21 + 24);
        LastError = 0;
        NumberOfBytesWritten = 0;
        v15 = 0;
        if ( !WriteFile(v11, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
          LastError = GetLastError();
        p_LastError = &LastError;
        goto LABEL_28;
      }
      switch ( v7 )
      {
        case 0:
          v8 = write_text_ansi_nolock(&LastError, FileHandle, (unsigned int)a2, nNumberOfBytesToWrite);
          goto LABEL_15;
        case 1:
          v8 = write_text_utf8_nolock(&LastError, FileHandle, (unsigned int)a2, nNumberOfBytesToWrite);
          goto LABEL_15;
        case 2:
          v8 = write_text_utf16le_nolock(&LastError, FileHandle, (unsigned __int16 *)a2, nNumberOfBytesToWrite);
          goto LABEL_15;
      }
    }
    if ( (*(_BYTE *)(dword_427018[v19] + v21 + 40) & 0x40) == 0 || *v3 != 26 )
    {
      *_errno() = 28;
      *__doserrno() = 0;
      return -1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x414672  mov     edi, edi
0x414674  push    ebp
0x414675  mov     ebp, esp
0x414677  sub     esp, 28h
0x41467a  mov     ecx, [ebp+arg_8]
0x41467d  mov     [ebp+nNumberOfBytesToWrite], ecx
0x414680  push    ebx
0x414681  push    esi
0x414682  mov     esi, [ebp+FileHandle]
0x414685  push    edi
0x414686  mov     edi, [ebp+arg_4]
0x414689  mov     [ebp+lpBuffer], edi
0x41468c  test    ecx, ecx
0x41468e  jz      loc_414845
0x414694  test    edi, edi
0x414696  jnz     short loc_4146B8
0x414698  call    ___doserrno
0x41469d  and     dword ptr [eax], 0
0x4146a0  call    __errno
0x4146a5  mov     dword ptr [eax], 16h
0x4146ab  call    __invalid_parameter_noinfo
0x4146b0  or      eax, 0FFFFFFFFh
0x4146b3  jmp     loc_414847
0x4146b8  mov     eax, esi
0x4146ba  mov     edx, esi
0x4146bc  sar     edx, 6
0x4146bf  and     eax, 3Fh
0x4146c2  imul    eax, 38h ; '8'
0x4146c5  mov     [ebp+var_10], edx
0x4146c8  mov     edx, dword_427018[edx*4]
0x4146cf  mov     [ebp+var_8], eax
0x4146d2  mov     bl, [edx+eax+29h]
0x4146d6  cmp     bl, 2
0x4146d9  jz      short loc_4146E0
0x4146db  cmp     bl, 1
0x4146de  jnz     short loc_4146EB
0x4146e0  mov     eax, ecx
0x4146e2  not     eax
0x4146e4  test    al, 1
0x4146e6  jz      short loc_414698
0x4146e8  mov     eax, [ebp+var_8]
0x4146eb  test    byte ptr [edx+eax+28h], 20h
0x4146f0  jz      short loc_414701
0x4146f2  push    2; dwMoveMethod
0x4146f4  push    0
0x4146f6  push    0; liDistanceToMove
0x4146f8  push    esi; FileHandle
0x4146f9  call    __lseeki64_nolock
0x4146fe  add     esp, 10h
0x414701  push    esi; FileHandle
0x414702  call    ?write_requires_double_translation_nolock@@YA_NH@Z
0x414707  pop     ecx
0x414708  test    al, al
0x41470a  jz      short loc_414745
0x41470c  test    bl, bl
0x41470e  jz      short loc_414732
0x414710  dec     bl
0x414712  cmp     bl, 1
0x414715  ja      loc_41480F
0x41471b  push    [ebp+nNumberOfBytesToWrite]
0x41471e  lea     eax, [ebp+var_28]
0x414721  push    edi
0x414722  push    eax
0x414723  call    ?write_double_translated_unicode_nolock@@YA?AUwrite_result@?A0x17268360@@QBDI@Z
0x414728  add     esp, 0Ch
0x41472b  mov     esi, eax
0x41472d  jmp     loc_4147CE
0x414732  push    [ebp+nNumberOfBytesToWrite]
0x414735  lea     eax, [ebp+var_28]
0x414738  push    edi
0x414739  push    esi
0x41473a  push    eax
0x41473b  call    ?write_double_translated_ansi_nolock@@YA?AUwrite_result@?A0x17268360@@HQBDI@Z
0x414740  add     esp, 10h
0x414743  jmp     short loc_41472B
0x414745  mov     eax, [ebp+var_10]
0x414748  mov     ecx, dword_427018[eax*4]
0x41474f  mov     eax, [ebp+var_8]
0x414752  cmp     byte ptr [ecx+eax+28h], 0
0x414757  jge     short loc_41479F
0x414759  movsx   eax, bl
0x41475c  sub     eax, 0
0x41475f  jz      short loc_41478F
0x414761  sub     eax, 1
0x414764  jz      short loc_41477F
0x414766  sub     eax, 1
0x414769  jnz     loc_41480F
0x41476f  push    [ebp+nNumberOfBytesToWrite]
0x414772  lea     eax, [ebp+var_28]
0x414775  push    edi
0x414776  push    esi
0x414777  push    eax
0x414778  call    ?write_text_utf16le_nolock@@YA?AUwrite_result@?A0x17268360@@HQBDI@Z
0x41477d  jmp     short loc_414740
0x41477f  push    [ebp+nNumberOfBytesToWrite]
0x414782  lea     eax, [ebp+var_28]
0x414785  push    edi
0x414786  push    esi
0x414787  push    eax
0x414788  call    ?write_text_utf8_nolock@@YA?AUwrite_result@?A0x17268360@@HQBDI@Z
0x41478d  jmp     short loc_414740
0x41478f  push    [ebp+nNumberOfBytesToWrite]
0x414792  lea     eax, [ebp+var_28]
0x414795  push    edi
0x414796  push    esi
0x414797  push    eax
0x414798  call    ?write_text_ansi_nolock@@YA?AUwrite_result@?A0x17268360@@HQBDI@Z
0x41479d  jmp     short loc_414740
0x41479f  mov     ecx, [ecx+eax+18h]
0x4147a3  lea     edi, [ebp+var_28]
0x4147a6  xor     eax, eax
0x4147a8  stosd
0x4147a9  push    0; lpOverlapped
0x4147ab  stosd
0x4147ac  stosd
0x4147ad  lea     eax, [ebp+NumberOfBytesWritten]
0x4147b0  push    eax; lpNumberOfBytesWritten
0x4147b1  push    [ebp+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x4147b4  push    [ebp+lpBuffer]; lpBuffer
0x4147b7  push    ecx; hFile
0x4147b8  call    ds:WriteFile
0x4147be  test    eax, eax
0x4147c0  jnz     short loc_4147CB
0x4147c2  call    ds:GetLastError
0x4147c8  mov     [ebp+var_28], eax
0x4147cb  lea     esi, [ebp+var_28]
0x4147ce  lea     edi, [ebp+var_1C]
0x4147d1  movsd
0x4147d2  movsd
0x4147d3  movsd
0x4147d4  mov     eax, [ebp+var_18]
0x4147d7  test    eax, eax
0x4147d9  jnz     short loc_414840
0x4147db  mov     eax, [ebp+var_1C]
0x4147de  test    eax, eax
0x4147e0  jz      short loc_41480C
0x4147e2  push    5
0x4147e4  pop     esi
0x4147e5  cmp     eax, esi
0x4147e7  jnz     short loc_414800
0x4147e9  call    __errno
0x4147ee  mov     dword ptr [eax], 9
0x4147f4  call    ___doserrno
0x4147f9  mov     [eax], esi
0x4147fb  jmp     loc_4146B0
0x414800  push    eax
0x414801  call    ___acrt_errno_map_os_error
0x414806  pop     ecx
0x414807  jmp     loc_4146B0
0x41480c  mov     edi, [ebp+lpBuffer]
0x41480f  mov     eax, [ebp+var_10]
0x414812  mov     ecx, [ebp+var_8]
0x414815  mov     eax, dword_427018[eax*4]
0x41481c  test    byte ptr [eax+ecx+28h], 40h
0x414821  jz      short loc_414828
0x414823  cmp     byte ptr [edi], 1Ah
0x414826  jz      short loc_414845
0x414828  call    __errno
0x41482d  mov     dword ptr [eax], 1Ch
0x414833  call    ___doserrno
0x414838  and     dword ptr [eax], 0
0x41483b  jmp     loc_4146B0
0x414840  sub     eax, [ebp+var_14]
0x414843  jmp     short loc_414847
0x414845  xor     eax, eax
0x414847  pop     edi
0x414848  pop     esi
0x414849  pop     ebx
0x41484a  leave
0x41484b  retn
```
