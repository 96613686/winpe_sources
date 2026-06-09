# _read_nolock

- ea: `0x18033bf1c`
- end: `0x18033c381`
- name: `_read_nolock`
- size: `1125`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x18033be04`
- `0x180346a20`

## callees

- `0x180334620`
- `0x180334700`
- `0x180334750`
- `0x180334770`
- `0x18033b8d4`
- `0x18033bb04`
- `0x18033bf1c`
- `0x18033ce88`
- `0x18034962c`
- `0x18034a22c`
- `0x18034ee8c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18033c1c3`
- `KERNEL32!GetLastError` at `0x18033c315`
- `KERNEL32!GetLastError` at `0x18033c1c3`
- `KERNEL32!GetLastError` at `0x18033c315`
- `KERNEL32!ReadFile` at `0x18033c20b`
- `KERNEL32!ReadFile` at `0x18033c20b`
- `KERNEL32!GetConsoleMode` at `0x18033c18a`
- `KERNEL32!GetConsoleMode` at `0x18033c18a`
- `KERNEL32!ReadConsoleW` at `0x18033c1b9`
- `KERNEL32!ReadConsoleW` at `0x18033c1b9`

## pseudocode

```c
__int64 __fastcall read_nolock(unsigned int a1, _BYTE *a2, unsigned int a3)
{
  unsigned __int64 v5; // r12
  unsigned __int64 v6; // rbp
  __int64 v7; // rdx
  __int64 v8; // rax
  _BYTE *v9; // rbx
  int v10; // r10d
  DWORD v11; // r14d
  _BYTE *v12; // r15
  __int64 v13; // rax
  __int64 v14; // rax
  int v15; // edi
  char v16; // cl
  char v17; // cl
  char v18; // cl
  DWORD LastError; // eax
  int v20; // edi
  __int64 v22; // rdx
  int v23; // eax
  _WORD *v24; // r8
  __int16 *v25; // rcx
  unsigned __int64 v26; // rax
  _WORD *v27; // rdi
  unsigned __int64 v28; // r10
  _WORD *v29; // rax
  __int16 v30; // r9
  DWORD Mode; // [rsp+30h] [rbp-68h] BYREF
  HANDLE hConsoleHandle; // [rsp+38h] [rbp-60h]
  __int64 v33; // [rsp+40h] [rbp-58h]
  __int64 v34; // [rsp+48h] [rbp-50h]
  _WORD *v35; // [rsp+50h] [rbp-48h]
  char v36; // [rsp+A0h] [rbp+8h]
  DWORD NumberOfCharsRead; // [rsp+B8h] [rbp+20h] BYREF

  v5 = a3;
  if ( a1 != -2 )
  {
    if ( (a1 & 0x80000000) == 0
      && a1 < nhandle
      && (v34 = 1,
          v6 = (unsigned __int64)(a1 & 0x3F) << 6,
          v7 = (__int64)(int)a1 >> 6,
          v33 = v7,
          v8 = _pioinfo[v7],
          (*(_BYTE *)(v8 + v6 + 56) & 1) != 0) )
    {
      if ( a3 <= 0x7FFFFFFF )
      {
        if ( !a3 || (*(_BYTE *)(v8 + v6 + 56) & 2) != 0 )
          return 0;
        if ( a2 )
        {
          v9 = 0;
          v10 = *(char *)(v8 + v6 + 57);
          hConsoleHandle = *(HANDLE *)(v8 + v6 + 40);
          v36 = v10;
          if ( v10 == 1 )
          {
            if ( (a3 & 1) == 0 )
            {
              v11 = a3 >> 1;
              if ( a3 >> 1 < 4 )
                v11 = 4;
              v9 = malloc_base(v11);
              free_base(0);
              free_base(0);
              v12 = v9;
              if ( v9 )
              {
                v13 = lseeki64_nolock(a1, 0, 1);
                v7 = v33;
                LOBYTE(v10) = v36;
                *(_QWORD *)(_pioinfo[v33] + v6 + 48) = v13;
                goto LABEL_22;
              }
              *errno() = 12;
              *_doserrno() = 8;
LABEL_38:
              v20 = -1;
              goto LABEL_39;
            }
          }
          else if ( v10 != 2 || (a3 & 1) == 0 )
          {
            v11 = a3;
            v12 = a2;
LABEL_22:
            v14 = _pioinfo[v7];
            v15 = 0;
            v35 = v12;
            if ( (*(_BYTE *)(v14 + v6 + 56) & 0x48) != 0 )
            {
              v16 = *(_BYTE *)(v14 + v6 + 58);
              if ( v16 != 10 )
              {
                *v12 = v16;
                --v11;
                ++v12;
                v15 = 1;
                *(_BYTE *)(_pioinfo[v7] + v6 + 58) = 10;
                if ( (_BYTE)v10 )
                {
                  v17 = *(_BYTE *)(_pioinfo[v7] + v6 + 59);
                  if ( v17 != 10 )
                  {
                    if ( v11 )
                    {
                      *v12 = v17;
                      v15 = 2;
                      ++v12;
                      --v11;
                      *(_BYTE *)(_pioinfo[v7] + v6 + 59) = 10;
                      if ( (_BYTE)v10 == 1 )
                      {
                        v18 = *(_BYTE *)(_pioinfo[v7] + v6 + 60);
                        if ( v18 != 10 )
                        {
                          if ( v11 )
                          {
                            *v12 = v18;
                            v15 = 3;
                            ++v12;
                            --v11;
                            *(_BYTE *)(_pioinfo[v7] + v6 + 60) = 10;
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
            if ( isatty(a1) && *(char *)(_pioinfo[v33] + v6 + 56) < 0 && GetConsoleMode(hConsoleHandle, &Mode) )
            {
              if ( v36 == 2 )
              {
                if ( !ReadConsoleW(hConsoleHandle, v12, v11 >> 1, &NumberOfCharsRead, 0) )
                {
                  LastError = GetLastError();
LABEL_37:
                  _acrt_errno_map_os_error(LastError);
                  goto LABEL_38;
                }
                v20 = v15 + 2 * NumberOfCharsRead;
                goto LABEL_45;
              }
            }
            else
            {
              LOBYTE(v34) = 0;
            }
            if ( !ReadFile(hConsoleHandle, v12, v11, &NumberOfCharsRead, 0) || NumberOfCharsRead > (unsigned int)v5 )
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
                v20 = 0;
                goto LABEL_39;
              }
              goto LABEL_37;
            }
            v20 = NumberOfCharsRead + v15;
LABEL_45:
            v22 = v33;
            if ( *(char *)(_pioinfo[v33] + v6 + 56) < 0 )
            {
              if ( v36 == 2 )
              {
                if ( (_BYTE)v34 )
                {
                  v24 = v35;
                  v25 = v35;
                  v26 = (unsigned __int64)v20 >> 1;
                  v27 = v35;
                  v28 = (unsigned __int64)&v35[v26];
                  if ( (unsigned __int64)v35 < v28 )
                  {
                    v29 = v35 + 1;
                    while ( 1 )
                    {
                      v30 = *v25;
                      if ( *v25 == 26 )
                        break;
                      if ( v30 == 13 && (unsigned __int64)v29 < v28 && *v29 == 10 )
                      {
                        v25 += 2;
                        *v27 = 10;
                        v29 += 2;
                        ++v27;
                      }
                      else
                      {
                        *v27 = v30;
                        ++v25;
                        ++v27;
                        ++v29;
                      }
                      if ( (unsigned __int64)v25 >= v28 )
                        goto LABEL_61;
                    }
                    *(_BYTE *)(_pioinfo[v22] + v6 + 56) |= 2u;
                  }
LABEL_61:
                  v20 = 2 * (v27 - v24);
                  goto LABEL_39;
                }
                v23 = translate_text_mode_nolock_wchar_t_(a1, v35, (unsigned __int64)v20 >> 1);
              }
              else
              {
                v23 = translate_ansi_or_utf8_nolock(a1, v12, v20, a2, v5 >> 1);
              }
              v20 = v23;
            }
LABEL_39:
            free_base(v9);
            return (unsigned int)v20;
          }
          *_doserrno() = 0;
          *errno() = 22;
          invalid_parameter_noinfo();
          goto LABEL_38;
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
0x18033bf1c  mov     [rsp+arg_10], rbx
0x18033bf21  mov     [rsp+arg_8], rdx
0x18033bf26  push    rbp
0x18033bf27  push    rsi
0x18033bf28  push    rdi
0x18033bf29  push    r12
0x18033bf2b  push    r13
0x18033bf2d  push    r14
0x18033bf2f  push    r15
0x18033bf31  sub     rsp, 60h
0x18033bf35  movsxd  r13, ecx
0x18033bf38  mov     r9, rdx
0x18033bf3b  mov     r12d, r8d
0x18033bf3e  cmp     r13d, 0FFFFFFFEh
0x18033bf42  jnz     short loc_18033BF5D
0x18033bf44  call    __doserrno
0x18033bf49  xor     esi, esi
0x18033bf4b  mov     [rax], esi
0x18033bf4d  call    _errno
0x18033bf52  mov     dword ptr [rax], 9
0x18033bf58  jmp     loc_18033C366
0x18033bf5d  xor     esi, esi
0x18033bf5f  test    ecx, ecx
0x18033bf61  js      loc_18033C34F
0x18033bf67  cmp     r13d, cs:_nhandle
0x18033bf6e  jnb     loc_18033C34F
0x18033bf74  mov     rbp, r13
0x18033bf77  lea     r8d, [rsi+1]
0x18033bf7b  and     ebp, 3Fh
0x18033bf7e  mov     [rsp+98h+var_50], r8
0x18033bf83  mov     rdx, r13
0x18033bf86  shl     rbp, 6
0x18033bf8a  sar     rdx, 6
0x18033bf8e  lea     r11, __pioinfo
0x18033bf95  mov     [rsp+98h+var_58], rdx
0x18033bf9a  mov     rax, [r11+rdx*8]
0x18033bf9e  test    [rax+rbp+38h], r8b
0x18033bfa3  jz      loc_18033C34F
0x18033bfa9  cmp     r12d, 7FFFFFFFh
0x18033bfb0  jbe     short loc_18033BFC9
0x18033bfb2  call    __doserrno
0x18033bfb7  mov     [rax], esi
0x18033bfb9  call    _errno
0x18033bfbe  mov     dword ptr [rax], 16h
0x18033bfc4  jmp     loc_18033C361
0x18033bfc9  test    r12d, r12d
0x18033bfcc  jz      loc_18033C34B
0x18033bfd2  test    byte ptr [rax+rbp+38h], 2
0x18033bfd7  jnz     loc_18033C34B
0x18033bfdd  test    r9, r9
0x18033bfe0  jz      short loc_18033BFB2
0x18033bfe2  mov     rcx, [rax+rbp+28h]
0x18033bfe7  mov     rbx, rsi
0x18033bfea  movsx   r10d, byte ptr [rax+rbp+39h]
0x18033bff0  mov     edi, 4
0x18033bff5  mov     [rsp+98h+hConsoleHandle], rcx
0x18033bffa  mov     ecx, r10d
0x18033bffd  mov     [rsp+98h+arg_0], r10b
0x18033c005  sub     ecx, r8d
0x18033c008  jz      short loc_18033C024
0x18033c00a  sub     ecx, r8d
0x18033c00d  jnz     short loc_18033C019
0x18033c00f  mov     eax, r12d
0x18033c012  not     eax
0x18033c014  test    r8b, al
0x18033c017  jz      short loc_18033C02E
0x18033c019  mov     r14d, r12d
0x18033c01c  mov     r15, r9
0x18033c01f  jmp     loc_18033C0C4
0x18033c024  mov     eax, r12d
0x18033c027  not     eax
0x18033c029  test    r8b, al
0x18033c02c  jnz     short loc_18033C04A
0x18033c02e  call    __doserrno
0x18033c033  mov     [rax], esi
0x18033c035  call    _errno
0x18033c03a  mov     dword ptr [rax], 16h
0x18033c040  call    _invalid_parameter_noinfo
0x18033c045  jmp     loc_18033C1D0
0x18033c04a  mov     r14d, r12d
0x18033c04d  shr     r14d, 1
0x18033c050  cmp     r14d, edi
0x18033c053  cmovb   r14d, edi
0x18033c057  mov     ecx, r14d; Size
0x18033c05a  call    _malloc_base
0x18033c05f  xor     ecx, ecx; Block
0x18033c061  mov     rbx, rax
0x18033c064  call    _free_base
0x18033c069  xor     ecx, ecx; Block
0x18033c06b  call    _free_base
0x18033c070  mov     r15, rbx
0x18033c073  test    rbx, rbx
0x18033c076  jnz     short loc_18033C093
0x18033c078  call    _errno
0x18033c07d  mov     dword ptr [rax], 0Ch
0x18033c083  call    __doserrno
0x18033c088  mov     dword ptr [rax], 8
0x18033c08e  jmp     loc_18033C1D0
0x18033c093  xor     edx, edx
0x18033c095  mov     ecx, r13d
0x18033c098  lea     r8d, [rdx+1]
0x18033c09c  call    _lseeki64_nolock
0x18033c0a1  mov     rdx, [rsp+98h+var_58]
0x18033c0a6  lea     r11, __pioinfo
0x18033c0ad  mov     r10b, [rsp+98h+arg_0]
0x18033c0b5  mov     r8d, 1
0x18033c0bb  mov     rcx, [r11+rdx*8]
0x18033c0bf  mov     [rcx+rbp+30h], rax
0x18033c0c4  mov     rax, [r11+rdx*8]
0x18033c0c8  mov     edi, esi
0x18033c0ca  mov     [rsp+98h+var_48], r15
0x18033c0cf  mov     r9d, 0Ah
0x18033c0d5  test    byte ptr [rax+rbp+38h], 48h
0x18033c0da  jz      short loc_18033C159
0x18033c0dc  mov     cl, [rax+rbp+3Ah]
0x18033c0e0  cmp     cl, r9b
0x18033c0e3  jz      short loc_18033C159
0x18033c0e5  test    r14d, r14d
0x18033c0e8  jz      short loc_18033C159
0x18033c0ea  mov     [r15], cl
0x18033c0ed  dec     r14d
0x18033c0f0  mov     rax, [r11+rdx*8]
0x18033c0f4  add     r15, r8
0x18033c0f7  mov     edi, r8d
0x18033c0fa  mov     [rax+rbp+3Ah], r9b
0x18033c0ff  test    r10b, r10b
0x18033c102  jz      short loc_18033C159
0x18033c104  mov     rax, [r11+rdx*8]
0x18033c108  mov     cl, [rax+rbp+3Bh]
0x18033c10c  cmp     cl, r9b
0x18033c10f  jz      short loc_18033C159
0x18033c111  test    r14d, r14d
0x18033c114  jz      short loc_18033C159
0x18033c116  mov     [r15], cl
0x18033c119  lea     edi, [r9-8]
0x18033c11d  mov     rax, [r11+rdx*8]
0x18033c121  add     r15, r8
0x18033c124  dec     r14d
0x18033c127  mov     [rax+rbp+3Bh], r9b
0x18033c12c  cmp     r10b, r8b
0x18033c12f  jnz     short loc_18033C159
0x18033c131  mov     rax, [r11+rdx*8]
0x18033c135  mov     cl, [rax+rbp+3Ch]
0x18033c139  cmp     cl, r9b
0x18033c13c  jz      short loc_18033C159
0x18033c13e  test    r14d, r14d
0x18033c141  jz      short loc_18033C159
0x18033c143  mov     [r15], cl
0x18033c146  lea     edi, [r9-7]
0x18033c14a  mov     rax, [r11+rdx*8]
0x18033c14e  add     r15, r8
0x18033c151  dec     r14d
0x18033c154  mov     [rax+rbp+3Ch], r9b
0x18033c159  mov     ecx, r13d; FileHandle
0x18033c15c  call    _isatty
0x18033c161  test    eax, eax
0x18033c163  jz      loc_18033C1EE
0x18033c169  mov     rax, [rsp+98h+var_58]
0x18033c16e  lea     rcx, __pioinfo
0x18033c175  mov     rax, [rcx+rax*8]
0x18033c179  test    byte ptr [rax+rbp+38h], 80h
0x18033c17e  jz      short loc_18033C1EE
0x18033c180  mov     rcx, [rsp+98h+hConsoleHandle]; hConsoleHandle
0x18033c185  lea     rdx, [rsp+98h+Mode]; lpMode
0x18033c18a  call    cs:__imp_GetConsoleMode
0x18033c190  test    eax, eax
0x18033c192  jz      short loc_18033C1EE
0x18033c194  cmp     [rsp+98h+arg_0], 2
0x18033c19c  jnz     short loc_18033C1F3
0x18033c19e  mov     rcx, [rsp+98h+hConsoleHandle]; hConsoleInput
0x18033c1a3  lea     r9, [rsp+98h+NumberOfCharsRead]; lpNumberOfCharsRead
0x18033c1ab  shr     r14d, 1
0x18033c1ae  mov     rdx, r15; lpBuffer
0x18033c1b1  mov     r8d, r14d; nNumberOfCharsToRead
0x18033c1b4  mov     [rsp+98h+pInputControl], rsi; pInputControl
0x18033c1b9  call    cs:__imp_ReadConsoleW
0x18033c1bf  test    eax, eax
0x18033c1c1  jnz     short loc_18033C1E2
0x18033c1c3  call    cs:__imp_GetLastError
0x18033c1c9  mov     ecx, eax
0x18033c1cb  call    __acrt_errno_map_os_error
0x18033c1d0  or      edi, 0FFFFFFFFh
0x18033c1d3  mov     rcx, rbx; Block
0x18033c1d6  call    _free_base
0x18033c1db  mov     eax, edi
0x18033c1dd  jmp     loc_18033C369
0x18033c1e2  mov     eax, [rsp+98h+NumberOfCharsRead]
0x18033c1e9  lea     edi, [rdi+rax*2]
0x18033c1ec  jmp     short loc_18033C22E
0x18033c1ee  mov     byte ptr [rsp+98h+var_50], sil
0x18033c1f3  mov     rcx, [rsp+98h+hConsoleHandle]; hFile
0x18033c1f8  lea     r9, [rsp+98h+NumberOfCharsRead]; lpNumberOfBytesRead
0x18033c200  mov     r8d, r14d; nNumberOfBytesToRead
0x18033c203  mov     [rsp+98h+pInputControl], rsi; lpOverlapped
0x18033c208  mov     rdx, r15; lpBuffer
0x18033c20b  call    cs:__imp_ReadFile
0x18033c211  test    eax, eax
0x18033c213  jz      loc_18033C315
0x18033c219  cmp     [rsp+98h+NumberOfCharsRead], r12d
0x18033c221  ja      loc_18033C315
0x18033c227  add     edi, [rsp+98h+NumberOfCharsRead]
0x18033c22e  mov     rdx, [rsp+98h+var_58]
0x18033c233  lea     r11, __pioinfo
0x18033c23a  mov     rax, [r11+rdx*8]
0x18033c23e  test    byte ptr [rax+rbp+38h], 80h
0x18033c243  jz      short loc_18033C1D3
0x18033c245  cmp     [rsp+98h+arg_0], 2
0x18033c24d  jz      short loc_18033C277
0x18033c24f  mov     r9, [rsp+98h+arg_8]
0x18033c257  mov     rax, r12
0x18033c25a  shr     rax, 1
0x18033c25d  mov     rdx, r15
0x18033c260  movsxd  r8, edi
0x18033c263  mov     ecx, r13d
0x18033c266  mov     [rsp+98h+pInputControl], rax
0x18033c26b  call    translate_ansi_or_utf8_nolock
0x18033c270  mov     edi, eax
0x18033c272  jmp     loc_18033C1D3
0x18033c277  mov     rax, [rsp+98h+var_50]
0x18033c27c  test    al, al
0x18033c27e  jz      short loc_18033C2FD
0x18033c280  mov     r8, [rsp+98h+var_48]
0x18033c285  movsxd  rax, edi
0x18033c288  mov     rcx, r8
0x18033c28b  shr     rax, 1
0x18033c28e  mov     rdi, r8
0x18033c291  lea     r10, [r8+rax*2]
0x18033c295  cmp     r8, r10
0x18033c298  jnb     short loc_18033C2F0
0x18033c29a  lea     rax, [r8+2]
0x18033c29e  mov     esi, 0Ah
0x18033c2a3  movzx   r9d, word ptr [rcx]
0x18033c2a7  cmp     r9w, 1Ah
0x18033c2ac  jz      short loc_18033C2E7
0x18033c2ae  cmp     r9w, 0Dh
0x18033c2b3  jnz     short loc_18033C2D0
0x18033c2b5  cmp     rax, r10
0x18033c2b8  jnb     short loc_18033C2D0
0x18033c2ba  cmp     [rax], si
0x18033c2bd  jnz     short loc_18033C2D0
0x18033c2bf  add     rcx, 4
0x18033c2c3  mov     [rdi], si
0x18033c2c6  add     rax, 4
0x18033c2ca  add     rdi, 2
0x18033c2ce  jmp     short loc_18033C2E0
0x18033c2d0  mov     [rdi], r9w
0x18033c2d4  add     rcx, 2
0x18033c2d8  add     rdi, 2
0x18033c2dc  add     rax, 2
0x18033c2e0  cmp     rcx, r10
0x18033c2e3  jb      short loc_18033C2A3
0x18033c2e5  jmp     short loc_18033C2F0
0x18033c2e7  mov     rax, [r11+rdx*8]
0x18033c2eb  or      byte ptr [rax+rbp+38h], 2
0x18033c2f0  sub     rdi, r8
0x18033c2f3  sar     rdi, 1
0x18033c2f6  add     edi, edi
0x18033c2f8  jmp     loc_18033C1D3
0x18033c2fd  mov     rdx, [rsp+98h+var_48]
0x18033c302  mov     ecx, r13d
0x18033c305  movsxd  r8, edi
0x18033c308  shr     r8, 1
0x18033c30b  call    translate_text_mode_nolock_wchar_t_
0x18033c310  jmp     loc_18033C270
0x18033c315  call    cs:__imp_GetLastError
0x18033c31b  cmp     eax, 5
0x18033c31e  jnz     short loc_18033C33B
0x18033c320  call    _errno
0x18033c325  mov     dword ptr [rax], 9
0x18033c32b  call    __doserrno
0x18033c330  mov     dword ptr [rax], 5
0x18033c336  jmp     loc_18033C1D0
0x18033c33b  cmp     eax, 6Dh ; 'm'
0x18033c33e  jnz     loc_18033C1C9
0x18033c344  mov     edi, esi
0x18033c346  jmp     loc_18033C1D3
0x18033c34b  xor     eax, eax
0x18033c34d  jmp     short loc_18033C369
0x18033c34f  call    __doserrno
0x18033c354  mov     [rax], esi
0x18033c356  call    _errno
0x18033c35b  mov     dword ptr [rax], 9
0x18033c361  call    _invalid_parameter_noinfo
0x18033c366  or      eax, 0FFFFFFFFh
0x18033c369  mov     rbx, [rsp+98h+arg_10]
0x18033c371  add     rsp, 60h
0x18033c375  pop     r15
0x18033c377  pop     r14
0x18033c379  pop     r13
0x18033c37b  pop     r12
0x18033c37d  pop     rdi
0x18033c37e  pop     rsi
0x18033c37f  pop     rbp
0x18033c380  retn
```
