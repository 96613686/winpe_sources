# __write_nolock

- ea: `0x414012`
- end: `0x4141ec`
- name: `__write_nolock`
- size: `474`
- prototype: `int __cdecl(int FileHandle, _BYTE *, DWORD)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x413f20`

## callees

- `0x40de54`
- `0x40ff73`
- `0x40ff96`
- `0x40ffa9`
- `0x4137a5`
- `0x413b51`
- `0x413bb9`
- `0x413c2a`
- `0x413d05`
- `0x413dee`
- `0x414012`
- `0x41466f`

## import_xrefs

- `KERNEL32!GetLastError` at `0x414162`
- `KERNEL32!GetLastError` at `0x414162`
- `KERNEL32!WriteFile` at `0x414158`
- `KERNEL32!WriteFile` at `0x414158`

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
    v6 = dword_4181B0[FileHandle >> 6];
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
      v10 = dword_4181B0[v19];
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
    if ( (*(_BYTE *)(dword_4181B0[v19] + v21 + 40) & 0x40) == 0 || *v3 != 26 )
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
0x414012  mov     edi, edi
0x414014  push    ebp
0x414015  mov     ebp, esp
0x414017  sub     esp, 28h
0x41401a  mov     ecx, [ebp+arg_8]
0x41401d  mov     [ebp+nNumberOfBytesToWrite], ecx
0x414020  push    ebx
0x414021  push    esi
0x414022  mov     esi, [ebp+FileHandle]
0x414025  push    edi
0x414026  mov     edi, [ebp+arg_4]
0x414029  mov     [ebp+lpBuffer], edi
0x41402c  test    ecx, ecx
0x41402e  jz      loc_4141E5
0x414034  test    edi, edi
0x414036  jnz     short loc_414058
0x414038  call    ___doserrno
0x41403d  and     dword ptr [eax], 0
0x414040  call    __errno
0x414045  mov     dword ptr [eax], 16h
0x41404b  call    __invalid_parameter_noinfo
0x414050  or      eax, 0FFFFFFFFh
0x414053  jmp     loc_4141E7
0x414058  mov     eax, esi
0x41405a  mov     edx, esi
0x41405c  sar     edx, 6
0x41405f  and     eax, 3Fh
0x414062  imul    eax, 38h ; '8'
0x414065  mov     [ebp+var_10], edx
0x414068  mov     edx, dword_4181B0[edx*4]
0x41406f  mov     [ebp+var_8], eax
0x414072  mov     bl, [edx+eax+29h]
0x414076  cmp     bl, 2
0x414079  jz      short loc_414080
0x41407b  cmp     bl, 1
0x41407e  jnz     short loc_41408B
0x414080  mov     eax, ecx
0x414082  not     eax
0x414084  test    al, 1
0x414086  jz      short loc_414038
0x414088  mov     eax, [ebp+var_8]
0x41408b  test    byte ptr [edx+eax+28h], 20h
0x414090  jz      short loc_4140A1
0x414092  push    2; dwMoveMethod
0x414094  push    0
0x414096  push    0; liDistanceToMove
0x414098  push    esi; FileHandle
0x414099  call    __lseeki64_nolock
0x41409e  add     esp, 10h
0x4140a1  push    esi; FileHandle
0x4140a2  call    ?write_requires_double_translation_nolock@@YA_NH@Z
0x4140a7  pop     ecx
0x4140a8  test    al, al
0x4140aa  jz      short loc_4140E5
0x4140ac  test    bl, bl
0x4140ae  jz      short loc_4140D2
0x4140b0  dec     bl
0x4140b2  cmp     bl, 1
0x4140b5  ja      loc_4141AF
0x4140bb  push    [ebp+nNumberOfBytesToWrite]
0x4140be  lea     eax, [ebp+var_28]
0x4140c1  push    edi
0x4140c2  push    eax
0x4140c3  call    ?write_double_translated_unicode_nolock@@YA?AUwrite_result@?A0x17268360@@QBDI@Z
0x4140c8  add     esp, 0Ch
0x4140cb  mov     esi, eax
0x4140cd  jmp     loc_41416E
0x4140d2  push    [ebp+nNumberOfBytesToWrite]
0x4140d5  lea     eax, [ebp+var_28]
0x4140d8  push    edi
0x4140d9  push    esi
0x4140da  push    eax
0x4140db  call    ?write_double_translated_ansi_nolock@@YA?AUwrite_result@?A0x17268360@@HQBDI@Z
0x4140e0  add     esp, 10h
0x4140e3  jmp     short loc_4140CB
0x4140e5  mov     eax, [ebp+var_10]
0x4140e8  mov     ecx, dword_4181B0[eax*4]
0x4140ef  mov     eax, [ebp+var_8]
0x4140f2  cmp     byte ptr [ecx+eax+28h], 0
0x4140f7  jge     short loc_41413F
0x4140f9  movsx   eax, bl
0x4140fc  sub     eax, 0
0x4140ff  jz      short loc_41412F
0x414101  sub     eax, 1
0x414104  jz      short loc_41411F
0x414106  sub     eax, 1
0x414109  jnz     loc_4141AF
0x41410f  push    [ebp+nNumberOfBytesToWrite]
0x414112  lea     eax, [ebp+var_28]
0x414115  push    edi
0x414116  push    esi
0x414117  push    eax
0x414118  call    ?write_text_utf16le_nolock@@YA?AUwrite_result@?A0x17268360@@HQBDI@Z
0x41411d  jmp     short loc_4140E0
0x41411f  push    [ebp+nNumberOfBytesToWrite]
0x414122  lea     eax, [ebp+var_28]
0x414125  push    edi
0x414126  push    esi
0x414127  push    eax
0x414128  call    ?write_text_utf8_nolock@@YA?AUwrite_result@?A0x17268360@@HQBDI@Z
0x41412d  jmp     short loc_4140E0
0x41412f  push    [ebp+nNumberOfBytesToWrite]
0x414132  lea     eax, [ebp+var_28]
0x414135  push    edi
0x414136  push    esi
0x414137  push    eax
0x414138  call    ?write_text_ansi_nolock@@YA?AUwrite_result@?A0x17268360@@HQBDI@Z
0x41413d  jmp     short loc_4140E0
0x41413f  mov     ecx, [ecx+eax+18h]
0x414143  lea     edi, [ebp+var_28]
0x414146  xor     eax, eax
0x414148  stosd
0x414149  push    0; lpOverlapped
0x41414b  stosd
0x41414c  stosd
0x41414d  lea     eax, [ebp+NumberOfBytesWritten]
0x414150  push    eax; lpNumberOfBytesWritten
0x414151  push    [ebp+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x414154  push    [ebp+lpBuffer]; lpBuffer
0x414157  push    ecx; hFile
0x414158  call    ds:WriteFile
0x41415e  test    eax, eax
0x414160  jnz     short loc_41416B
0x414162  call    ds:GetLastError
0x414168  mov     [ebp+var_28], eax
0x41416b  lea     esi, [ebp+var_28]
0x41416e  lea     edi, [ebp+var_1C]
0x414171  movsd
0x414172  movsd
0x414173  movsd
0x414174  mov     eax, [ebp+var_18]
0x414177  test    eax, eax
0x414179  jnz     short loc_4141E0
0x41417b  mov     eax, [ebp+var_1C]
0x41417e  test    eax, eax
0x414180  jz      short loc_4141AC
0x414182  push    5
0x414184  pop     esi
0x414185  cmp     eax, esi
0x414187  jnz     short loc_4141A0
0x414189  call    __errno
0x41418e  mov     dword ptr [eax], 9
0x414194  call    ___doserrno
0x414199  mov     [eax], esi
0x41419b  jmp     loc_414050
0x4141a0  push    eax
0x4141a1  call    ___acrt_errno_map_os_error
0x4141a6  pop     ecx
0x4141a7  jmp     loc_414050
0x4141ac  mov     edi, [ebp+lpBuffer]
0x4141af  mov     eax, [ebp+var_10]
0x4141b2  mov     ecx, [ebp+var_8]
0x4141b5  mov     eax, dword_4181B0[eax*4]
0x4141bc  test    byte ptr [eax+ecx+28h], 40h
0x4141c1  jz      short loc_4141C8
0x4141c3  cmp     byte ptr [edi], 1Ah
0x4141c6  jz      short loc_4141E5
0x4141c8  call    __errno
0x4141cd  mov     dword ptr [eax], 1Ch
0x4141d3  call    ___doserrno
0x4141d8  and     dword ptr [eax], 0
0x4141db  jmp     loc_414050
0x4141e0  sub     eax, [ebp+var_14]
0x4141e3  jmp     short loc_4141E7
0x4141e5  xor     eax, eax
0x4141e7  pop     edi
0x4141e8  pop     esi
0x4141e9  pop     ebx
0x4141ea  leave
0x4141eb  retn
```
