# __write_nolock

- ea: `0x419037`
- end: `0x419211`
- name: `__write_nolock`
- size: `474`
- prototype: `int __cdecl(int FileHandle, _BYTE *, DWORD)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x418f45`

## callees

- `0x410369`
- `0x41040d`
- `0x410430`
- `0x410443`
- `0x4187ca`
- `0x418b76`
- `0x418bde`
- `0x418c4f`
- `0x418d2a`
- `0x418e13`
- `0x419037`
- `0x41b23d`

## import_xrefs

- `KERNEL32!WriteFile` at `0x41917d`
- `KERNEL32!WriteFile` at `0x41917d`
- `KERNEL32!GetLastError` at `0x419187`
- `KERNEL32!GetLastError` at `0x419187`

## pseudocode

```c
int __cdecl _write_nolock(int FileHandle, _BYTE *a2, DWORD a3)
{
  _BYTE *v3; // edi
  int v5; // eax
  int v6; // edx
  char v7; // bl
  DWORD *v8; // eax
  DWORD *p_LastError; // esi
  int v10; // ecx
  void *v11; // ecx
  int *v12; // esi
  DWORD LastError; // [esp+Ch] [ebp-28h] BYREF
  DWORD NumberOfBytesWritten; // [esp+10h] [ebp-24h] BYREF
  int v15; // [esp+14h] [ebp-20h]
  DWORD v16; // [esp+18h] [ebp-1Ch]
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
    v6 = dword_43E588[FileHandle >> 6];
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
      v10 = dword_43E588[v19];
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
    if ( (*(_BYTE *)(dword_43E588[v19] + v21 + 40) & 0x40) == 0 || *v3 != 26 )
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
0x419037  mov     edi, edi
0x419039  push    ebp
0x41903a  mov     ebp, esp
0x41903c  sub     esp, 28h
0x41903f  mov     ecx, [ebp+arg_8]
0x419042  mov     [ebp+nNumberOfBytesToWrite], ecx
0x419045  push    ebx
0x419046  push    esi
0x419047  mov     esi, [ebp+FileHandle]
0x41904a  push    edi
0x41904b  mov     edi, [ebp+arg_4]
0x41904e  mov     [ebp+lpBuffer], edi
0x419051  test    ecx, ecx
0x419053  jz      loc_41920A
0x419059  test    edi, edi
0x41905b  jnz     short loc_41907D
0x41905d  call    ___doserrno
0x419062  and     dword ptr [eax], 0
0x419065  call    __errno
0x41906a  mov     dword ptr [eax], 16h
0x419070  call    __invalid_parameter_noinfo
0x419075  or      eax, 0FFFFFFFFh
0x419078  jmp     loc_41920C
0x41907d  mov     eax, esi
0x41907f  mov     edx, esi
0x419081  sar     edx, 6
0x419084  and     eax, 3Fh
0x419087  imul    eax, 38h ; '8'
0x41908a  mov     [ebp+var_10], edx
0x41908d  mov     edx, dword_43E588[edx*4]
0x419094  mov     [ebp+var_8], eax
0x419097  mov     bl, [edx+eax+29h]
0x41909b  cmp     bl, 2
0x41909e  jz      short loc_4190A5
0x4190a0  cmp     bl, 1
0x4190a3  jnz     short loc_4190B0
0x4190a5  mov     eax, ecx
0x4190a7  not     eax
0x4190a9  test    al, 1
0x4190ab  jz      short loc_41905D
0x4190ad  mov     eax, [ebp+var_8]
0x4190b0  test    byte ptr [edx+eax+28h], 20h
0x4190b5  jz      short loc_4190C6
0x4190b7  push    2; dwMoveMethod
0x4190b9  push    0
0x4190bb  push    0; liDistanceToMove
0x4190bd  push    esi; FileHandle
0x4190be  call    __lseeki64_nolock
0x4190c3  add     esp, 10h
0x4190c6  push    esi; FileHandle
0x4190c7  call    ?write_requires_double_translation_nolock@@YA_NH@Z
0x4190cc  pop     ecx
0x4190cd  test    al, al
0x4190cf  jz      short loc_41910A
0x4190d1  test    bl, bl
0x4190d3  jz      short loc_4190F7
0x4190d5  dec     bl
0x4190d7  cmp     bl, 1
0x4190da  ja      loc_4191D4
0x4190e0  push    [ebp+nNumberOfBytesToWrite]
0x4190e3  lea     eax, [ebp+var_28]
0x4190e6  push    edi
0x4190e7  push    eax
0x4190e8  call    ?write_double_translated_unicode_nolock@@YA?AUwrite_result@?A0x17268360@@QBDI@Z
0x4190ed  add     esp, 0Ch
0x4190f0  mov     esi, eax
0x4190f2  jmp     loc_419193
0x4190f7  push    [ebp+nNumberOfBytesToWrite]
0x4190fa  lea     eax, [ebp+var_28]
0x4190fd  push    edi
0x4190fe  push    esi
0x4190ff  push    eax
0x419100  call    ?write_double_translated_ansi_nolock@@YA?AUwrite_result@?A0x17268360@@HQBDI@Z
0x419105  add     esp, 10h
0x419108  jmp     short loc_4190F0
0x41910a  mov     eax, [ebp+var_10]
0x41910d  mov     ecx, dword_43E588[eax*4]
0x419114  mov     eax, [ebp+var_8]
0x419117  cmp     byte ptr [ecx+eax+28h], 0
0x41911c  jge     short loc_419164
0x41911e  movsx   eax, bl
0x419121  sub     eax, 0
0x419124  jz      short loc_419154
0x419126  sub     eax, 1
0x419129  jz      short loc_419144
0x41912b  sub     eax, 1
0x41912e  jnz     loc_4191D4
0x419134  push    [ebp+nNumberOfBytesToWrite]
0x419137  lea     eax, [ebp+var_28]
0x41913a  push    edi
0x41913b  push    esi
0x41913c  push    eax
0x41913d  call    ?write_text_utf16le_nolock@@YA?AUwrite_result@?A0x17268360@@HQBDI@Z
0x419142  jmp     short loc_419105
0x419144  push    [ebp+nNumberOfBytesToWrite]
0x419147  lea     eax, [ebp+var_28]
0x41914a  push    edi
0x41914b  push    esi
0x41914c  push    eax
0x41914d  call    ?write_text_utf8_nolock@@YA?AUwrite_result@?A0x17268360@@HQBDI@Z
0x419152  jmp     short loc_419105
0x419154  push    [ebp+nNumberOfBytesToWrite]
0x419157  lea     eax, [ebp+var_28]
0x41915a  push    edi
0x41915b  push    esi
0x41915c  push    eax
0x41915d  call    ?write_text_ansi_nolock@@YA?AUwrite_result@?A0x17268360@@HQBDI@Z
0x419162  jmp     short loc_419105
0x419164  mov     ecx, [ecx+eax+18h]
0x419168  lea     edi, [ebp+var_28]
0x41916b  xor     eax, eax
0x41916d  stosd
0x41916e  push    0; lpOverlapped
0x419170  stosd
0x419171  stosd
0x419172  lea     eax, [ebp+NumberOfBytesWritten]
0x419175  push    eax; lpNumberOfBytesWritten
0x419176  push    [ebp+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x419179  push    [ebp+lpBuffer]; lpBuffer
0x41917c  push    ecx; hFile
0x41917d  call    ds:WriteFile
0x419183  test    eax, eax
0x419185  jnz     short loc_419190
0x419187  call    ds:GetLastError
0x41918d  mov     [ebp+var_28], eax
0x419190  lea     esi, [ebp+var_28]
0x419193  lea     edi, [ebp+var_1C]
0x419196  movsd
0x419197  movsd
0x419198  movsd
0x419199  mov     eax, [ebp+var_18]
0x41919c  test    eax, eax
0x41919e  jnz     short loc_419205
0x4191a0  mov     eax, [ebp+var_1C]
0x4191a3  test    eax, eax
0x4191a5  jz      short loc_4191D1
0x4191a7  push    5
0x4191a9  pop     esi
0x4191aa  cmp     eax, esi
0x4191ac  jnz     short loc_4191C5
0x4191ae  call    __errno
0x4191b3  mov     dword ptr [eax], 9
0x4191b9  call    ___doserrno
0x4191be  mov     [eax], esi
0x4191c0  jmp     loc_419075
0x4191c5  push    eax
0x4191c6  call    ___acrt_errno_map_os_error
0x4191cb  pop     ecx
0x4191cc  jmp     loc_419075
0x4191d1  mov     edi, [ebp+lpBuffer]
0x4191d4  mov     eax, [ebp+var_10]
0x4191d7  mov     ecx, [ebp+var_8]
0x4191da  mov     eax, dword_43E588[eax*4]
0x4191e1  test    byte ptr [eax+ecx+28h], 40h
0x4191e6  jz      short loc_4191ED
0x4191e8  cmp     byte ptr [edi], 1Ah
0x4191eb  jz      short loc_41920A
0x4191ed  call    __errno
0x4191f2  mov     dword ptr [eax], 1Ch
0x4191f8  call    ___doserrno
0x4191fd  and     dword ptr [eax], 0
0x419200  jmp     loc_419075
0x419205  sub     eax, [ebp+var_14]
0x419208  jmp     short loc_41920C
0x41920a  xor     eax, eax
0x41920c  pop     edi
0x41920d  pop     esi
0x41920e  pop     ebx
0x41920f  leave
0x419210  retn
```
