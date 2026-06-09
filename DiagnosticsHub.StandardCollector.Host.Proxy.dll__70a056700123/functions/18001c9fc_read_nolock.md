# _read_nolock

- ea: `0x18001c9fc`
- end: `0x18001ce5b`
- name: `_read_nolock`
- size: `1119`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x18001c8dc`

## callees

- `0x1800074a0`
- `0x180007718`
- `0x180007764`
- `0x180007788`
- `0x1800078e0`
- `0x180011f70`
- `0x180015ac4`
- `0x18001b0e8`
- `0x18001c278`
- `0x18001c510`
- `0x18001c9fc`

## import_xrefs

- `KERNEL32!ReadConsoleW` at `0x18001cc94`
- `KERNEL32!ReadConsoleW` at `0x18001cc94`
- `KERNEL32!ReadFile` at `0x18001cced`
- `KERNEL32!ReadFile` at `0x18001cced`
- `KERNEL32!GetConsoleMode` at `0x18001cc5f`
- `KERNEL32!GetConsoleMode` at `0x18001cc5f`
- `KERNEL32!GetLastError` at `0x18001cc9e`
- `KERNEL32!GetLastError` at `0x18001cdef`
- `KERNEL32!GetLastError` at `0x18001cc9e`
- `KERNEL32!GetLastError` at `0x18001cdef`

## pseudocode

```c
__int64 __fastcall read_nolock(int a1, __int16 *a2, unsigned int a3)
{
  unsigned __int64 v4; // r12
  unsigned __int64 v5; // r8
  __int64 v6; // rax
  __int16 *v7; // rbx
  int v8; // r10d
  DWORD v9; // ebp
  __int16 *v10; // r15
  __int64 v11; // rax
  __int64 v12; // rax
  int v13; // edi
  char v14; // al
  char v15; // cl
  char v16; // cl
  DWORD LastError; // eax
  int v18; // edi
  unsigned __int64 v20; // rdx
  int v21; // eax
  unsigned __int64 v22; // r8
  __int16 *v23; // r10
  __int16 *v24; // rax
  __int16 *v25; // rdi
  unsigned __int64 v26; // r9
  __int16 v27; // cx
  __int64 v28; // r11
  DWORD Mode; // [rsp+30h] [rbp-68h] BYREF
  HANDLE hConsoleHandle; // [rsp+38h] [rbp-60h]
  unsigned __int64 v31; // [rsp+40h] [rbp-58h]
  __int64 v32; // [rsp+48h] [rbp-50h]
  __int16 *v33; // [rsp+50h] [rbp-48h]
  char v34; // [rsp+A0h] [rbp+8h]
  int v35; // [rsp+A8h] [rbp+10h]
  DWORD NumberOfCharsRead; // [rsp+B8h] [rbp+20h] BYREF

  v35 = (int)a2;
  v4 = a3;
  if ( a1 != -2 )
  {
    if ( a1 >= 0
      && a1 < (unsigned int)nhandle
      && (v32 = 1,
          v5 = (unsigned __int64)a1 >> 6,
          v31 = v5,
          v6 = _pioinfo[v5],
          (*(_BYTE *)(v6 + 72LL * (a1 & 0x3F) + 56) & 1) != 0) )
    {
      if ( (unsigned int)v4 <= 0x7FFFFFFF )
      {
        if ( !(_DWORD)v4 || (*(_BYTE *)(v6 + 72LL * (a1 & 0x3F) + 56) & 2) != 0 )
          return 0;
        if ( a2 )
        {
          v7 = 0;
          v8 = *(char *)(v6 + 72LL * (a1 & 0x3F) + 57);
          hConsoleHandle = *(HANDLE *)(v6 + 72LL * (a1 & 0x3F) + 40);
          v34 = v8;
          if ( v8 == 1 )
          {
            if ( (v4 & 1) != 0 )
            {
LABEL_14:
              *_doserrno() = 0;
              *errno() = 22;
              invalid_parameter_noinfo();
LABEL_38:
              v18 = -1;
              goto LABEL_39;
            }
            v9 = (unsigned int)v4 >> 1;
            if ( (unsigned int)v4 >> 1 < 4 )
              v9 = 4;
            v7 = (__int16 *)malloc_base(v9);
            free_base(0);
            free_base(0);
            v10 = v7;
            if ( !v7 )
            {
              *errno() = 12;
              *_doserrno() = 8;
              goto LABEL_38;
            }
            v11 = lseeki64_nolock((unsigned int)a1, 0, 1);
            v5 = v31;
            LOBYTE(v8) = v34;
            *(_QWORD *)(_pioinfo[v31] + 72LL * (a1 & 0x3F) + 48) = v11;
          }
          else
          {
            if ( v8 == 2 && (v4 & 1) != 0 )
              goto LABEL_14;
            v9 = v4;
            v10 = a2;
          }
          v12 = _pioinfo[v5];
          v13 = 0;
          v33 = v10;
          if ( (*(_BYTE *)(v12 + 72LL * (a1 & 0x3F) + 56) & 0x48) != 0 )
          {
            v14 = *(_BYTE *)(v12 + 72LL * (a1 & 0x3F) + 58);
            if ( v14 != 10 )
            {
              *(_BYTE *)v10 = v14;
              --v9;
              v10 = (__int16 *)((char *)v10 + 1);
              v13 = 1;
              *(_BYTE *)(_pioinfo[v5] + 72LL * (a1 & 0x3F) + 58) = 10;
              if ( (_BYTE)v8 )
              {
                v15 = *(_BYTE *)(_pioinfo[v5] + 72LL * (a1 & 0x3F) + 59);
                if ( v15 != 10 )
                {
                  if ( v9 )
                  {
                    *(_BYTE *)v10 = v15;
                    v13 = 2;
                    v10 = (__int16 *)((char *)v10 + 1);
                    --v9;
                    *(_BYTE *)(_pioinfo[v5] + 72LL * (a1 & 0x3F) + 59) = 10;
                    if ( (_BYTE)v8 == 1 )
                    {
                      v16 = *(_BYTE *)(_pioinfo[v5] + 72LL * (a1 & 0x3F) + 60);
                      if ( v16 != 10 )
                      {
                        if ( v9 )
                        {
                          *(_BYTE *)v10 = v16;
                          v13 = 3;
                          v10 = (__int16 *)((char *)v10 + 1);
                          --v9;
                          *(_BYTE *)(_pioinfo[v5] + 72LL * (a1 & 0x3F) + 60) = 10;
                        }
                      }
                    }
                  }
                }
              }
            }
          }
          Mode = 0;
          if ( isatty(a1)
            && *(char *)(_pioinfo[v31] + 72LL * (a1 & 0x3F) + 56) < 0
            && GetConsoleMode(hConsoleHandle, &Mode) )
          {
            if ( v34 == 2 )
            {
              NumberOfCharsRead = 0;
              if ( !ReadConsoleW(hConsoleHandle, v10, v9 >> 1, &NumberOfCharsRead, 0) )
              {
                LastError = GetLastError();
LABEL_37:
                _acrt_errno_map_os_error(LastError);
                goto LABEL_38;
              }
              v18 = v13 + 2 * NumberOfCharsRead;
              goto LABEL_45;
            }
          }
          else
          {
            LOBYTE(v32) = 0;
          }
          NumberOfCharsRead = 0;
          if ( !ReadFile(hConsoleHandle, v10, v9, &NumberOfCharsRead, 0) || NumberOfCharsRead > (unsigned int)v4 )
          {
            LastError = GetLastError();
            if ( LastError == 5 )
            {
              *errno() = 9;
              *_doserrno() = 5;
              goto LABEL_38;
            }
            if ( LastError == 109 )
            {
              v18 = 0;
              goto LABEL_39;
            }
            goto LABEL_37;
          }
          v18 = NumberOfCharsRead + v13;
LABEL_45:
          v20 = v31;
          if ( *(char *)(_pioinfo[v31] + 72LL * (a1 & 0x3F) + 56) < 0 )
          {
            if ( v34 == 2 )
            {
              v22 = (unsigned __int64)v18 >> 1;
              if ( (_BYTE)v32 )
              {
                v23 = v33;
                v24 = v33;
                v25 = v33;
                v26 = (unsigned __int64)&v33[v22];
                if ( (unsigned __int64)v33 < v26 )
                {
                  while ( 1 )
                  {
                    v27 = *v24;
                    if ( *v24 == 26 )
                      break;
                    if ( v27 == 13 && (unsigned __int64)(v24 + 1) < v26 && v24[1] == 10 )
                    {
                      v27 = 10;
                      v28 = 4;
                    }
                    else
                    {
                      v28 = 2;
                    }
                    v24 = (__int16 *)((char *)v24 + v28);
                    *v25++ = v27;
                    if ( (unsigned __int64)v24 >= v26 )
                      goto LABEL_60;
                  }
                  *(_BYTE *)(_pioinfo[v20] + 72LL * (a1 & 0x3F) + 56) |= 2u;
                }
LABEL_60:
                v18 = 2 * (v25 - v23);
                goto LABEL_39;
              }
              v21 = translate_text_mode_nolock_wchar_t_((unsigned int)a1, v33, v22);
            }
            else
            {
              v21 = translate_ansi_or_utf8_nolock(a1, (_DWORD)v10, v18, v35, v4 >> 1);
            }
            v18 = v21;
          }
LABEL_39:
          free_base(v7);
          return (unsigned int)v18;
        }
      }
      *_doserrno() = 0;
      *errno() = 22;
    }
    else
    {
      *_doserrno() = 0;
      *errno() = 9;
    }
    invalid_parameter_noinfo();
    return 0xFFFFFFFFLL;
  }
  *_doserrno() = 0;
  *errno() = 9;
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x18001c9fc  mov     [rsp+arg_10], rbx
0x18001ca01  mov     [rsp+arg_8], rdx
0x18001ca06  push    rbp
0x18001ca07  push    rsi
0x18001ca08  push    rdi
0x18001ca09  push    r12
0x18001ca0b  push    r13
0x18001ca0d  push    r14
0x18001ca0f  push    r15
0x18001ca11  sub     rsp, 60h
0x18001ca15  movsxd  r13, ecx
0x18001ca18  mov     r9, rdx
0x18001ca1b  mov     r12d, r8d
0x18001ca1e  cmp     r13d, 0FFFFFFFEh
0x18001ca22  jnz     short loc_18001CA3D
0x18001ca24  call    __doserrno
0x18001ca29  xor     esi, esi
0x18001ca2b  mov     [rax], esi
0x18001ca2d  call    _errno
0x18001ca32  mov     dword ptr [rax], 9
0x18001ca38  jmp     loc_18001CE40
0x18001ca3d  xor     esi, esi
0x18001ca3f  test    ecx, ecx
0x18001ca41  js      loc_18001CE29
0x18001ca47  cmp     r13d, cs:_nhandle
0x18001ca4e  jnb     loc_18001CE29
0x18001ca54  mov     rax, r13
0x18001ca57  lea     edx, [rsi+1]
0x18001ca5a  and     eax, 3Fh
0x18001ca5d  mov     [rsp+98h+var_50], rdx
0x18001ca62  mov     r8, r13
0x18001ca65  lea     r11, __pioinfo
0x18001ca6c  shr     r8, 6
0x18001ca70  mov     [rsp+98h+var_58], r8
0x18001ca75  lea     r14, [rax+rax*8]
0x18001ca79  mov     rax, [r11+r8*8]
0x18001ca7d  test    [rax+r14*8+38h], dl
0x18001ca82  jz      loc_18001CE29
0x18001ca88  cmp     r12d, 7FFFFFFFh
0x18001ca8f  jbe     short loc_18001CAA8
0x18001ca91  call    __doserrno
0x18001ca96  mov     [rax], esi
0x18001ca98  call    _errno
0x18001ca9d  mov     dword ptr [rax], 16h
0x18001caa3  jmp     loc_18001CE3B
0x18001caa8  test    r12d, r12d
0x18001caab  jz      loc_18001CE25
0x18001cab1  test    byte ptr [rax+r14*8+38h], 2
0x18001cab7  jnz     loc_18001CE25
0x18001cabd  test    r9, r9
0x18001cac0  jz      short loc_18001CA91
0x18001cac2  mov     rcx, [rax+r14*8+28h]
0x18001cac7  mov     rbx, rsi
0x18001caca  movsx   r10d, byte ptr [rax+r14*8+39h]
0x18001cad0  mov     edi, 4
0x18001cad5  mov     [rsp+98h+hConsoleHandle], rcx
0x18001cada  mov     ecx, r10d
0x18001cadd  mov     [rsp+98h+arg_0], r10b
0x18001cae5  sub     ecx, edx
0x18001cae7  jz      short loc_18001CB1A
0x18001cae9  cmp     ecx, edx
0x18001caeb  jnz     short loc_18001CB12
0x18001caed  mov     eax, r12d
0x18001caf0  not     eax
0x18001caf2  test    dl, al
0x18001caf4  jnz     short loc_18001CB12
0x18001caf6  call    __doserrno
0x18001cafb  mov     [rax], esi
0x18001cafd  call    _errno
0x18001cb02  mov     dword ptr [rax], 16h
0x18001cb08  call    _invalid_parameter_noinfo
0x18001cb0d  jmp     loc_18001CCAB
0x18001cb12  mov     ebp, r12d
0x18001cb15  mov     r15, r9
0x18001cb18  jmp     short loc_18001CB98
0x18001cb1a  mov     eax, r12d
0x18001cb1d  not     eax
0x18001cb1f  test    dl, al
0x18001cb21  jz      short loc_18001CAF6
0x18001cb23  mov     ebp, r12d
0x18001cb26  shr     ebp, 1
0x18001cb28  cmp     ebp, edi
0x18001cb2a  cmovb   ebp, edi
0x18001cb2d  mov     ecx, ebp; Size
0x18001cb2f  call    _malloc_base
0x18001cb34  xor     ecx, ecx; Block
0x18001cb36  mov     rbx, rax
0x18001cb39  call    _free_base
0x18001cb3e  xor     ecx, ecx; Block
0x18001cb40  call    _free_base
0x18001cb45  mov     r15, rbx
0x18001cb48  test    rbx, rbx
0x18001cb4b  jnz     short loc_18001CB68
0x18001cb4d  call    _errno
0x18001cb52  mov     dword ptr [rax], 0Ch
0x18001cb58  call    __doserrno
0x18001cb5d  mov     dword ptr [rax], 8
0x18001cb63  jmp     loc_18001CCAB
0x18001cb68  xor     edx, edx
0x18001cb6a  mov     ecx, r13d
0x18001cb6d  lea     r8d, [rdx+1]
0x18001cb71  call    _lseeki64_nolock
0x18001cb76  mov     r8, [rsp+98h+var_58]
0x18001cb7b  lea     r11, __pioinfo
0x18001cb82  mov     r10b, [rsp+98h+arg_0]
0x18001cb8a  mov     edx, 1
0x18001cb8f  mov     rcx, [r11+r8*8]
0x18001cb93  mov     [rcx+r14*8+30h], rax
0x18001cb98  mov     rax, [r11+r8*8]
0x18001cb9c  mov     edi, esi
0x18001cb9e  mov     [rsp+98h+var_48], r15
0x18001cba3  mov     r9d, 0Ah
0x18001cba9  test    byte ptr [rax+r14*8+38h], 48h
0x18001cbaf  jz      short loc_18001CC2A
0x18001cbb1  mov     al, [rax+r14*8+3Ah]
0x18001cbb6  cmp     al, r9b
0x18001cbb9  jz      short loc_18001CC2A
0x18001cbbb  test    ebp, ebp
0x18001cbbd  jz      short loc_18001CC2A
0x18001cbbf  mov     [r15], al
0x18001cbc2  dec     ebp
0x18001cbc4  mov     rax, [r11+r8*8]
0x18001cbc8  add     r15, rdx
0x18001cbcb  mov     edi, edx
0x18001cbcd  mov     [rax+r14*8+3Ah], r9b
0x18001cbd2  test    r10b, r10b
0x18001cbd5  jz      short loc_18001CC2A
0x18001cbd7  mov     rax, [r11+r8*8]
0x18001cbdb  mov     cl, [rax+r14*8+3Bh]
0x18001cbe0  cmp     cl, r9b
0x18001cbe3  jz      short loc_18001CC2A
0x18001cbe5  test    ebp, ebp
0x18001cbe7  jz      short loc_18001CC2A
0x18001cbe9  mov     [r15], cl
0x18001cbec  lea     edi, [r9-8]
0x18001cbf0  mov     rax, [r11+r8*8]
0x18001cbf4  add     r15, rdx
0x18001cbf7  dec     ebp
0x18001cbf9  mov     [rax+r14*8+3Bh], r9b
0x18001cbfe  cmp     r10b, dl
0x18001cc01  jnz     short loc_18001CC2A
0x18001cc03  mov     rax, [r11+r8*8]
0x18001cc07  mov     cl, [rax+r14*8+3Ch]
0x18001cc0c  cmp     cl, r9b
0x18001cc0f  jz      short loc_18001CC2A
0x18001cc11  test    ebp, ebp
0x18001cc13  jz      short loc_18001CC2A
0x18001cc15  mov     [r15], cl
0x18001cc18  lea     edi, [r9-7]
0x18001cc1c  mov     rax, [r11+r8*8]
0x18001cc20  add     r15, rdx
0x18001cc23  dec     ebp
0x18001cc25  mov     [rax+r14*8+3Ch], r9b
0x18001cc2a  mov     ecx, r13d; FileHandle
0x18001cc2d  mov     [rsp+98h+Mode], esi
0x18001cc31  call    _isatty
0x18001cc36  test    eax, eax
0x18001cc38  jz      loc_18001CCC9
0x18001cc3e  mov     rax, [rsp+98h+var_58]
0x18001cc43  lea     rcx, __pioinfo
0x18001cc4a  mov     rax, [rcx+rax*8]
0x18001cc4e  cmp     [rax+r14*8+38h], sil
0x18001cc53  jge     short loc_18001CCC9
0x18001cc55  mov     rcx, [rsp+98h+hConsoleHandle]; hConsoleHandle
0x18001cc5a  lea     rdx, [rsp+98h+Mode]; lpMode
0x18001cc5f  call    cs:__imp_GetConsoleMode
0x18001cc65  test    eax, eax
0x18001cc67  jz      short loc_18001CCC9
0x18001cc69  cmp     [rsp+98h+arg_0], 2
0x18001cc71  jnz     short loc_18001CCCE
0x18001cc73  mov     rcx, [rsp+98h+hConsoleHandle]; hConsoleInput
0x18001cc78  lea     r9, [rsp+98h+NumberOfCharsRead]; lpNumberOfCharsRead
0x18001cc80  shr     ebp, 1
0x18001cc82  mov     rdx, r15; lpBuffer
0x18001cc85  mov     r8d, ebp; nNumberOfCharsToRead
0x18001cc88  mov     [rsp+98h+NumberOfCharsRead], esi
0x18001cc8f  mov     [rsp+98h+pInputControl], rsi; pInputControl
0x18001cc94  call    cs:__imp_ReadConsoleW
0x18001cc9a  test    eax, eax
0x18001cc9c  jnz     short loc_18001CCBD
0x18001cc9e  call    cs:__imp_GetLastError
0x18001cca4  mov     ecx, eax
0x18001cca6  call    __acrt_errno_map_os_error
0x18001ccab  or      edi, 0FFFFFFFFh
0x18001ccae  mov     rcx, rbx; Block
0x18001ccb1  call    _free_base
0x18001ccb6  mov     eax, edi
0x18001ccb8  jmp     loc_18001CE43
0x18001ccbd  mov     eax, [rsp+98h+NumberOfCharsRead]
0x18001ccc4  lea     edi, [rdi+rax*2]
0x18001ccc7  jmp     short loc_18001CD10
0x18001ccc9  mov     byte ptr [rsp+98h+var_50], sil
0x18001ccce  mov     rcx, [rsp+98h+hConsoleHandle]; hFile
0x18001ccd3  lea     r9, [rsp+98h+NumberOfCharsRead]; lpNumberOfBytesRead
0x18001ccdb  mov     r8d, ebp; nNumberOfBytesToRead
0x18001ccde  mov     [rsp+98h+NumberOfCharsRead], esi
0x18001cce5  mov     rdx, r15; lpBuffer
0x18001cce8  mov     [rsp+98h+pInputControl], rsi; lpOverlapped
0x18001cced  call    cs:__imp_ReadFile
0x18001ccf3  test    eax, eax
0x18001ccf5  jz      loc_18001CDEF
0x18001ccfb  cmp     [rsp+98h+NumberOfCharsRead], r12d
0x18001cd03  ja      loc_18001CDEF
0x18001cd09  add     edi, [rsp+98h+NumberOfCharsRead]
0x18001cd10  mov     rdx, [rsp+98h+var_58]
0x18001cd15  lea     r11, __pioinfo
0x18001cd1c  mov     rax, [r11+rdx*8]
0x18001cd20  cmp     [rax+r14*8+38h], sil
0x18001cd25  jge     short loc_18001CCAE
0x18001cd27  cmp     [rsp+98h+arg_0], 2
0x18001cd2f  movsxd  r8, edi
0x18001cd32  jz      short loc_18001CD59
0x18001cd34  mov     r9, [rsp+98h+arg_8]
0x18001cd3c  mov     rax, r12
0x18001cd3f  shr     rax, 1
0x18001cd42  mov     rdx, r15
0x18001cd45  mov     ecx, r13d
0x18001cd48  mov     [rsp+98h+pInputControl], rax
0x18001cd4d  call    translate_ansi_or_utf8_nolock
0x18001cd52  mov     edi, eax
0x18001cd54  jmp     loc_18001CCAE
0x18001cd59  shr     r8, 1
0x18001cd5c  cmp     byte ptr [rsp+98h+var_50], sil
0x18001cd61  jz      short loc_18001CDDD
0x18001cd63  mov     r10, [rsp+98h+var_48]
0x18001cd68  mov     rax, r10
0x18001cd6b  mov     rdi, r10
0x18001cd6e  lea     r9, [r10+r8*2]
0x18001cd72  cmp     r10, r9
0x18001cd75  jnb     short loc_18001CDD0
0x18001cd77  mov     esi, 0Ah
0x18001cd7c  movzx   ecx, word ptr [rax]
0x18001cd7f  cmp     cx, 1Ah
0x18001cd83  jz      short loc_18001CDBF
0x18001cd85  cmp     cx, 0Dh
0x18001cd89  jnz     short loc_18001CDA5
0x18001cd8b  lea     r8, [rax+2]
0x18001cd8f  cmp     r8, r9
0x18001cd92  jnb     short loc_18001CDA5
0x18001cd94  cmp     [r8], si
0x18001cd98  jnz     short loc_18001CDA5
0x18001cd9a  movzx   ecx, si
0x18001cd9d  mov     r11d, 4
0x18001cda3  jmp     short loc_18001CDAB
0x18001cda5  mov     r11d, 2
0x18001cdab  add     rax, r11
0x18001cdae  mov     [rdi], cx
0x18001cdb1  lea     r8, [rdi+2]
0x18001cdb5  mov     rdi, r8
0x18001cdb8  cmp     rax, r9
0x18001cdbb  jb      short loc_18001CD7C
0x18001cdbd  jmp     short loc_18001CDD0
0x18001cdbf  lea     rcx, __pioinfo
0x18001cdc6  mov     rax, [rcx+rdx*8]
0x18001cdca  or      byte ptr [rax+r14*8+38h], 2
0x18001cdd0  sub     rdi, r10
0x18001cdd3  sar     rdi, 1
0x18001cdd6  add     edi, edi
0x18001cdd8  jmp     loc_18001CCAE
0x18001cddd  mov     rdx, [rsp+98h+var_48]
0x18001cde2  mov     ecx, r13d
0x18001cde5  call    translate_text_mode_nolock_wchar_t_
0x18001cdea  jmp     loc_18001CD52
0x18001cdef  call    cs:__imp_GetLastError
0x18001cdf5  cmp     eax, 5
0x18001cdf8  jnz     short loc_18001CE15
0x18001cdfa  call    _errno
0x18001cdff  mov     dword ptr [rax], 9
0x18001ce05  call    __doserrno
0x18001ce0a  mov     dword ptr [rax], 5
0x18001ce10  jmp     loc_18001CCAB
0x18001ce15  cmp     eax, 6Dh ; 'm'
0x18001ce18  jnz     loc_18001CCA4
0x18001ce1e  mov     edi, esi
0x18001ce20  jmp     loc_18001CCAE
0x18001ce25  xor     eax, eax
0x18001ce27  jmp     short loc_18001CE43
0x18001ce29  call    __doserrno
0x18001ce2e  mov     [rax], esi
0x18001ce30  call    _errno
0x18001ce35  mov     dword ptr [rax], 9
0x18001ce3b  call    _invalid_parameter_noinfo
0x18001ce40  or      eax, 0FFFFFFFFh
0x18001ce43  mov     rbx, [rsp+98h+arg_10]
0x18001ce4b  add     rsp, 60h
0x18001ce4f  pop     r15
0x18001ce51  pop     r14
0x18001ce53  pop     r13
0x18001ce55  pop     r12
0x18001ce57  pop     rdi
0x18001ce58  pop     rsi
0x18001ce59  pop     rbp
0x18001ce5a  retn
```
