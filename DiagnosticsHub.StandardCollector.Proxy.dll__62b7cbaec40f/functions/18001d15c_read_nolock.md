# _read_nolock

- ea: `0x18001d15c`
- end: `0x18001d5bb`
- name: `_read_nolock`
- size: `1119`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x18001d03c`

## callees

- `0x180007c00`
- `0x180007e78`
- `0x180007ec4`
- `0x180007ee8`
- `0x180008040`
- `0x1800126d0`
- `0x180016224`
- `0x18001b848`
- `0x18001c9d8`
- `0x18001cc70`
- `0x18001d15c`

## import_xrefs

- `KERNEL32!ReadConsoleW` at `0x18001d3f4`
- `KERNEL32!ReadConsoleW` at `0x18001d3f4`
- `KERNEL32!ReadFile` at `0x18001d44d`
- `KERNEL32!ReadFile` at `0x18001d44d`
- `KERNEL32!GetConsoleMode` at `0x18001d3bf`
- `KERNEL32!GetConsoleMode` at `0x18001d3bf`
- `KERNEL32!GetLastError` at `0x18001d3fe`
- `KERNEL32!GetLastError` at `0x18001d54f`
- `KERNEL32!GetLastError` at `0x18001d3fe`
- `KERNEL32!GetLastError` at `0x18001d54f`

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
0x18001d15c  mov     [rsp+arg_10], rbx
0x18001d161  mov     [rsp+arg_8], rdx
0x18001d166  push    rbp
0x18001d167  push    rsi
0x18001d168  push    rdi
0x18001d169  push    r12
0x18001d16b  push    r13
0x18001d16d  push    r14
0x18001d16f  push    r15
0x18001d171  sub     rsp, 60h
0x18001d175  movsxd  r13, ecx
0x18001d178  mov     r9, rdx
0x18001d17b  mov     r12d, r8d
0x18001d17e  cmp     r13d, 0FFFFFFFEh
0x18001d182  jnz     short loc_18001D19D
0x18001d184  call    __doserrno
0x18001d189  xor     esi, esi
0x18001d18b  mov     [rax], esi
0x18001d18d  call    _errno
0x18001d192  mov     dword ptr [rax], 9
0x18001d198  jmp     loc_18001D5A0
0x18001d19d  xor     esi, esi
0x18001d19f  test    ecx, ecx
0x18001d1a1  js      loc_18001D589
0x18001d1a7  cmp     r13d, cs:_nhandle
0x18001d1ae  jnb     loc_18001D589
0x18001d1b4  mov     rax, r13
0x18001d1b7  lea     edx, [rsi+1]
0x18001d1ba  and     eax, 3Fh
0x18001d1bd  mov     [rsp+98h+var_50], rdx
0x18001d1c2  mov     r8, r13
0x18001d1c5  lea     r11, __pioinfo
0x18001d1cc  shr     r8, 6
0x18001d1d0  mov     [rsp+98h+var_58], r8
0x18001d1d5  lea     r14, [rax+rax*8]
0x18001d1d9  mov     rax, [r11+r8*8]
0x18001d1dd  test    [rax+r14*8+38h], dl
0x18001d1e2  jz      loc_18001D589
0x18001d1e8  cmp     r12d, 7FFFFFFFh
0x18001d1ef  jbe     short loc_18001D208
0x18001d1f1  call    __doserrno
0x18001d1f6  mov     [rax], esi
0x18001d1f8  call    _errno
0x18001d1fd  mov     dword ptr [rax], 16h
0x18001d203  jmp     loc_18001D59B
0x18001d208  test    r12d, r12d
0x18001d20b  jz      loc_18001D585
0x18001d211  test    byte ptr [rax+r14*8+38h], 2
0x18001d217  jnz     loc_18001D585
0x18001d21d  test    r9, r9
0x18001d220  jz      short loc_18001D1F1
0x18001d222  mov     rcx, [rax+r14*8+28h]
0x18001d227  mov     rbx, rsi
0x18001d22a  movsx   r10d, byte ptr [rax+r14*8+39h]
0x18001d230  mov     edi, 4
0x18001d235  mov     [rsp+98h+hConsoleHandle], rcx
0x18001d23a  mov     ecx, r10d
0x18001d23d  mov     [rsp+98h+arg_0], r10b
0x18001d245  sub     ecx, edx
0x18001d247  jz      short loc_18001D27A
0x18001d249  cmp     ecx, edx
0x18001d24b  jnz     short loc_18001D272
0x18001d24d  mov     eax, r12d
0x18001d250  not     eax
0x18001d252  test    dl, al
0x18001d254  jnz     short loc_18001D272
0x18001d256  call    __doserrno
0x18001d25b  mov     [rax], esi
0x18001d25d  call    _errno
0x18001d262  mov     dword ptr [rax], 16h
0x18001d268  call    _invalid_parameter_noinfo
0x18001d26d  jmp     loc_18001D40B
0x18001d272  mov     ebp, r12d
0x18001d275  mov     r15, r9
0x18001d278  jmp     short loc_18001D2F8
0x18001d27a  mov     eax, r12d
0x18001d27d  not     eax
0x18001d27f  test    dl, al
0x18001d281  jz      short loc_18001D256
0x18001d283  mov     ebp, r12d
0x18001d286  shr     ebp, 1
0x18001d288  cmp     ebp, edi
0x18001d28a  cmovb   ebp, edi
0x18001d28d  mov     ecx, ebp; Size
0x18001d28f  call    _malloc_base
0x18001d294  xor     ecx, ecx; Block
0x18001d296  mov     rbx, rax
0x18001d299  call    _free_base
0x18001d29e  xor     ecx, ecx; Block
0x18001d2a0  call    _free_base
0x18001d2a5  mov     r15, rbx
0x18001d2a8  test    rbx, rbx
0x18001d2ab  jnz     short loc_18001D2C8
0x18001d2ad  call    _errno
0x18001d2b2  mov     dword ptr [rax], 0Ch
0x18001d2b8  call    __doserrno
0x18001d2bd  mov     dword ptr [rax], 8
0x18001d2c3  jmp     loc_18001D40B
0x18001d2c8  xor     edx, edx
0x18001d2ca  mov     ecx, r13d
0x18001d2cd  lea     r8d, [rdx+1]
0x18001d2d1  call    _lseeki64_nolock
0x18001d2d6  mov     r8, [rsp+98h+var_58]
0x18001d2db  lea     r11, __pioinfo
0x18001d2e2  mov     r10b, [rsp+98h+arg_0]
0x18001d2ea  mov     edx, 1
0x18001d2ef  mov     rcx, [r11+r8*8]
0x18001d2f3  mov     [rcx+r14*8+30h], rax
0x18001d2f8  mov     rax, [r11+r8*8]
0x18001d2fc  mov     edi, esi
0x18001d2fe  mov     [rsp+98h+var_48], r15
0x18001d303  mov     r9d, 0Ah
0x18001d309  test    byte ptr [rax+r14*8+38h], 48h
0x18001d30f  jz      short loc_18001D38A
0x18001d311  mov     al, [rax+r14*8+3Ah]
0x18001d316  cmp     al, r9b
0x18001d319  jz      short loc_18001D38A
0x18001d31b  test    ebp, ebp
0x18001d31d  jz      short loc_18001D38A
0x18001d31f  mov     [r15], al
0x18001d322  dec     ebp
0x18001d324  mov     rax, [r11+r8*8]
0x18001d328  add     r15, rdx
0x18001d32b  mov     edi, edx
0x18001d32d  mov     [rax+r14*8+3Ah], r9b
0x18001d332  test    r10b, r10b
0x18001d335  jz      short loc_18001D38A
0x18001d337  mov     rax, [r11+r8*8]
0x18001d33b  mov     cl, [rax+r14*8+3Bh]
0x18001d340  cmp     cl, r9b
0x18001d343  jz      short loc_18001D38A
0x18001d345  test    ebp, ebp
0x18001d347  jz      short loc_18001D38A
0x18001d349  mov     [r15], cl
0x18001d34c  lea     edi, [r9-8]
0x18001d350  mov     rax, [r11+r8*8]
0x18001d354  add     r15, rdx
0x18001d357  dec     ebp
0x18001d359  mov     [rax+r14*8+3Bh], r9b
0x18001d35e  cmp     r10b, dl
0x18001d361  jnz     short loc_18001D38A
0x18001d363  mov     rax, [r11+r8*8]
0x18001d367  mov     cl, [rax+r14*8+3Ch]
0x18001d36c  cmp     cl, r9b
0x18001d36f  jz      short loc_18001D38A
0x18001d371  test    ebp, ebp
0x18001d373  jz      short loc_18001D38A
0x18001d375  mov     [r15], cl
0x18001d378  lea     edi, [r9-7]
0x18001d37c  mov     rax, [r11+r8*8]
0x18001d380  add     r15, rdx
0x18001d383  dec     ebp
0x18001d385  mov     [rax+r14*8+3Ch], r9b
0x18001d38a  mov     ecx, r13d; FileHandle
0x18001d38d  mov     [rsp+98h+Mode], esi
0x18001d391  call    _isatty
0x18001d396  test    eax, eax
0x18001d398  jz      loc_18001D429
0x18001d39e  mov     rax, [rsp+98h+var_58]
0x18001d3a3  lea     rcx, __pioinfo
0x18001d3aa  mov     rax, [rcx+rax*8]
0x18001d3ae  cmp     [rax+r14*8+38h], sil
0x18001d3b3  jge     short loc_18001D429
0x18001d3b5  mov     rcx, [rsp+98h+hConsoleHandle]; hConsoleHandle
0x18001d3ba  lea     rdx, [rsp+98h+Mode]; lpMode
0x18001d3bf  call    cs:__imp_GetConsoleMode
0x18001d3c5  test    eax, eax
0x18001d3c7  jz      short loc_18001D429
0x18001d3c9  cmp     [rsp+98h+arg_0], 2
0x18001d3d1  jnz     short loc_18001D42E
0x18001d3d3  mov     rcx, [rsp+98h+hConsoleHandle]; hConsoleInput
0x18001d3d8  lea     r9, [rsp+98h+NumberOfCharsRead]; lpNumberOfCharsRead
0x18001d3e0  shr     ebp, 1
0x18001d3e2  mov     rdx, r15; lpBuffer
0x18001d3e5  mov     r8d, ebp; nNumberOfCharsToRead
0x18001d3e8  mov     [rsp+98h+NumberOfCharsRead], esi
0x18001d3ef  mov     [rsp+98h+pInputControl], rsi; pInputControl
0x18001d3f4  call    cs:__imp_ReadConsoleW
0x18001d3fa  test    eax, eax
0x18001d3fc  jnz     short loc_18001D41D
0x18001d3fe  call    cs:__imp_GetLastError
0x18001d404  mov     ecx, eax
0x18001d406  call    __acrt_errno_map_os_error
0x18001d40b  or      edi, 0FFFFFFFFh
0x18001d40e  mov     rcx, rbx; Block
0x18001d411  call    _free_base
0x18001d416  mov     eax, edi
0x18001d418  jmp     loc_18001D5A3
0x18001d41d  mov     eax, [rsp+98h+NumberOfCharsRead]
0x18001d424  lea     edi, [rdi+rax*2]
0x18001d427  jmp     short loc_18001D470
0x18001d429  mov     byte ptr [rsp+98h+var_50], sil
0x18001d42e  mov     rcx, [rsp+98h+hConsoleHandle]; hFile
0x18001d433  lea     r9, [rsp+98h+NumberOfCharsRead]; lpNumberOfBytesRead
0x18001d43b  mov     r8d, ebp; nNumberOfBytesToRead
0x18001d43e  mov     [rsp+98h+NumberOfCharsRead], esi
0x18001d445  mov     rdx, r15; lpBuffer
0x18001d448  mov     [rsp+98h+pInputControl], rsi; lpOverlapped
0x18001d44d  call    cs:__imp_ReadFile
0x18001d453  test    eax, eax
0x18001d455  jz      loc_18001D54F
0x18001d45b  cmp     [rsp+98h+NumberOfCharsRead], r12d
0x18001d463  ja      loc_18001D54F
0x18001d469  add     edi, [rsp+98h+NumberOfCharsRead]
0x18001d470  mov     rdx, [rsp+98h+var_58]
0x18001d475  lea     r11, __pioinfo
0x18001d47c  mov     rax, [r11+rdx*8]
0x18001d480  cmp     [rax+r14*8+38h], sil
0x18001d485  jge     short loc_18001D40E
0x18001d487  cmp     [rsp+98h+arg_0], 2
0x18001d48f  movsxd  r8, edi
0x18001d492  jz      short loc_18001D4B9
0x18001d494  mov     r9, [rsp+98h+arg_8]
0x18001d49c  mov     rax, r12
0x18001d49f  shr     rax, 1
0x18001d4a2  mov     rdx, r15
0x18001d4a5  mov     ecx, r13d
0x18001d4a8  mov     [rsp+98h+pInputControl], rax
0x18001d4ad  call    translate_ansi_or_utf8_nolock
0x18001d4b2  mov     edi, eax
0x18001d4b4  jmp     loc_18001D40E
0x18001d4b9  shr     r8, 1
0x18001d4bc  cmp     byte ptr [rsp+98h+var_50], sil
0x18001d4c1  jz      short loc_18001D53D
0x18001d4c3  mov     r10, [rsp+98h+var_48]
0x18001d4c8  mov     rax, r10
0x18001d4cb  mov     rdi, r10
0x18001d4ce  lea     r9, [r10+r8*2]
0x18001d4d2  cmp     r10, r9
0x18001d4d5  jnb     short loc_18001D530
0x18001d4d7  mov     esi, 0Ah
0x18001d4dc  movzx   ecx, word ptr [rax]
0x18001d4df  cmp     cx, 1Ah
0x18001d4e3  jz      short loc_18001D51F
0x18001d4e5  cmp     cx, 0Dh
0x18001d4e9  jnz     short loc_18001D505
0x18001d4eb  lea     r8, [rax+2]
0x18001d4ef  cmp     r8, r9
0x18001d4f2  jnb     short loc_18001D505
0x18001d4f4  cmp     [r8], si
0x18001d4f8  jnz     short loc_18001D505
0x18001d4fa  movzx   ecx, si
0x18001d4fd  mov     r11d, 4
0x18001d503  jmp     short loc_18001D50B
0x18001d505  mov     r11d, 2
0x18001d50b  add     rax, r11
0x18001d50e  mov     [rdi], cx
0x18001d511  lea     r8, [rdi+2]
0x18001d515  mov     rdi, r8
0x18001d518  cmp     rax, r9
0x18001d51b  jb      short loc_18001D4DC
0x18001d51d  jmp     short loc_18001D530
0x18001d51f  lea     rcx, __pioinfo
0x18001d526  mov     rax, [rcx+rdx*8]
0x18001d52a  or      byte ptr [rax+r14*8+38h], 2
0x18001d530  sub     rdi, r10
0x18001d533  sar     rdi, 1
0x18001d536  add     edi, edi
0x18001d538  jmp     loc_18001D40E
0x18001d53d  mov     rdx, [rsp+98h+var_48]
0x18001d542  mov     ecx, r13d
0x18001d545  call    translate_text_mode_nolock_wchar_t_
0x18001d54a  jmp     loc_18001D4B2
0x18001d54f  call    cs:__imp_GetLastError
0x18001d555  cmp     eax, 5
0x18001d558  jnz     short loc_18001D575
0x18001d55a  call    _errno
0x18001d55f  mov     dword ptr [rax], 9
0x18001d565  call    __doserrno
0x18001d56a  mov     dword ptr [rax], 5
0x18001d570  jmp     loc_18001D40B
0x18001d575  cmp     eax, 6Dh ; 'm'
0x18001d578  jnz     loc_18001D404
0x18001d57e  mov     edi, esi
0x18001d580  jmp     loc_18001D40E
0x18001d585  xor     eax, eax
0x18001d587  jmp     short loc_18001D5A3
0x18001d589  call    __doserrno
0x18001d58e  mov     [rax], esi
0x18001d590  call    _errno
0x18001d595  mov     dword ptr [rax], 9
0x18001d59b  call    _invalid_parameter_noinfo
0x18001d5a0  or      eax, 0FFFFFFFFh
0x18001d5a3  mov     rbx, [rsp+98h+arg_10]
0x18001d5ab  add     rsp, 60h
0x18001d5af  pop     r15
0x18001d5b1  pop     r14
0x18001d5b3  pop     r13
0x18001d5b5  pop     r12
0x18001d5b7  pop     rdi
0x18001d5b8  pop     rsi
0x18001d5b9  pop     rbp
0x18001d5ba  retn
```
