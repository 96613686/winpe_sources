# _read_nolock

- ea: `0x140070fec`
- end: `0x14007144b`
- name: `_read_nolock`
- size: `1119`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x140061a9c`
- `0x140070ecc`
- `0x140076038`
- `0x1400764cc`

## callees

- `0x14004f7fc`
- `0x14005af8c`
- `0x14005afd8`
- `0x14005affc`
- `0x140067520`
- `0x140067580`
- `0x1400709a0`
- `0x140070b9c`
- `0x140070fec`
- `0x140071934`
- `0x140075694`

## import_xrefs

- `KERNEL32!ReadFile` at `0x1400712dd`
- `KERNEL32!ReadFile` at `0x1400712dd`
- `KERNEL32!GetLastError` at `0x14007128e`
- `KERNEL32!GetLastError` at `0x1400713df`
- `KERNEL32!GetLastError` at `0x14007128e`
- `KERNEL32!GetLastError` at `0x1400713df`
- `KERNEL32!ReadConsoleW` at `0x140071284`
- `KERNEL32!ReadConsoleW` at `0x140071284`
- `KERNEL32!GetConsoleMode` at `0x14007124f`
- `KERNEL32!GetConsoleMode` at `0x14007124f`

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
0x140070fec  mov     [rsp+arg_10], rbx
0x140070ff1  mov     [rsp+arg_8], rdx
0x140070ff6  push    rbp
0x140070ff7  push    rsi
0x140070ff8  push    rdi
0x140070ff9  push    r12
0x140070ffb  push    r13
0x140070ffd  push    r14
0x140070fff  push    r15
0x140071001  sub     rsp, 60h
0x140071005  movsxd  r13, ecx
0x140071008  mov     r9, rdx
0x14007100b  mov     r12d, r8d
0x14007100e  cmp     r13d, 0FFFFFFFEh
0x140071012  jnz     short loc_14007102D
0x140071014  call    __doserrno
0x140071019  xor     esi, esi
0x14007101b  mov     [rax], esi
0x14007101d  call    _errno
0x140071022  mov     dword ptr [rax], 9
0x140071028  jmp     loc_140071430
0x14007102d  xor     esi, esi
0x14007102f  test    ecx, ecx
0x140071031  js      loc_140071419
0x140071037  cmp     r13d, cs:_nhandle
0x14007103e  jnb     loc_140071419
0x140071044  mov     rax, r13
0x140071047  lea     edx, [rsi+1]
0x14007104a  and     eax, 3Fh
0x14007104d  mov     [rsp+98h+var_50], rdx
0x140071052  mov     r8, r13
0x140071055  lea     r11, __pioinfo
0x14007105c  shr     r8, 6
0x140071060  mov     [rsp+98h+var_58], r8
0x140071065  lea     r14, [rax+rax*8]
0x140071069  mov     rax, [r11+r8*8]
0x14007106d  test    [rax+r14*8+38h], dl
0x140071072  jz      loc_140071419
0x140071078  cmp     r12d, 7FFFFFFFh
0x14007107f  jbe     short loc_140071098
0x140071081  call    __doserrno
0x140071086  mov     [rax], esi
0x140071088  call    _errno
0x14007108d  mov     dword ptr [rax], 16h
0x140071093  jmp     loc_14007142B
0x140071098  test    r12d, r12d
0x14007109b  jz      loc_140071415
0x1400710a1  test    byte ptr [rax+r14*8+38h], 2
0x1400710a7  jnz     loc_140071415
0x1400710ad  test    r9, r9
0x1400710b0  jz      short loc_140071081
0x1400710b2  mov     rcx, [rax+r14*8+28h]
0x1400710b7  mov     rbx, rsi
0x1400710ba  movsx   r10d, byte ptr [rax+r14*8+39h]
0x1400710c0  mov     edi, 4
0x1400710c5  mov     [rsp+98h+hConsoleHandle], rcx
0x1400710ca  mov     ecx, r10d
0x1400710cd  mov     [rsp+98h+arg_0], r10b
0x1400710d5  sub     ecx, edx
0x1400710d7  jz      short loc_14007110A
0x1400710d9  cmp     ecx, edx
0x1400710db  jnz     short loc_140071102
0x1400710dd  mov     eax, r12d
0x1400710e0  not     eax
0x1400710e2  test    dl, al
0x1400710e4  jnz     short loc_140071102
0x1400710e6  call    __doserrno
0x1400710eb  mov     [rax], esi
0x1400710ed  call    _errno
0x1400710f2  mov     dword ptr [rax], 16h
0x1400710f8  call    _invalid_parameter_noinfo
0x1400710fd  jmp     loc_14007129B
0x140071102  mov     ebp, r12d
0x140071105  mov     r15, r9
0x140071108  jmp     short loc_140071188
0x14007110a  mov     eax, r12d
0x14007110d  not     eax
0x14007110f  test    dl, al
0x140071111  jz      short loc_1400710E6
0x140071113  mov     ebp, r12d
0x140071116  shr     ebp, 1
0x140071118  cmp     ebp, edi
0x14007111a  cmovb   ebp, edi
0x14007111d  mov     ecx, ebp; Size
0x14007111f  call    _malloc_base
0x140071124  xor     ecx, ecx; Block
0x140071126  mov     rbx, rax
0x140071129  call    _free_base
0x14007112e  xor     ecx, ecx; Block
0x140071130  call    _free_base
0x140071135  mov     r15, rbx
0x140071138  test    rbx, rbx
0x14007113b  jnz     short loc_140071158
0x14007113d  call    _errno
0x140071142  mov     dword ptr [rax], 0Ch
0x140071148  call    __doserrno
0x14007114d  mov     dword ptr [rax], 8
0x140071153  jmp     loc_14007129B
0x140071158  xor     edx, edx
0x14007115a  mov     ecx, r13d
0x14007115d  lea     r8d, [rdx+1]
0x140071161  call    _lseeki64_nolock
0x140071166  mov     r8, [rsp+98h+var_58]
0x14007116b  lea     r11, __pioinfo
0x140071172  mov     r10b, [rsp+98h+arg_0]
0x14007117a  mov     edx, 1
0x14007117f  mov     rcx, [r11+r8*8]
0x140071183  mov     [rcx+r14*8+30h], rax
0x140071188  mov     rax, [r11+r8*8]
0x14007118c  mov     edi, esi
0x14007118e  mov     [rsp+98h+var_48], r15
0x140071193  mov     r9d, 0Ah
0x140071199  test    byte ptr [rax+r14*8+38h], 48h
0x14007119f  jz      short loc_14007121A
0x1400711a1  mov     al, [rax+r14*8+3Ah]
0x1400711a6  cmp     al, r9b
0x1400711a9  jz      short loc_14007121A
0x1400711ab  test    ebp, ebp
0x1400711ad  jz      short loc_14007121A
0x1400711af  mov     [r15], al
0x1400711b2  dec     ebp
0x1400711b4  mov     rax, [r11+r8*8]
0x1400711b8  add     r15, rdx
0x1400711bb  mov     edi, edx
0x1400711bd  mov     [rax+r14*8+3Ah], r9b
0x1400711c2  test    r10b, r10b
0x1400711c5  jz      short loc_14007121A
0x1400711c7  mov     rax, [r11+r8*8]
0x1400711cb  mov     cl, [rax+r14*8+3Bh]
0x1400711d0  cmp     cl, r9b
0x1400711d3  jz      short loc_14007121A
0x1400711d5  test    ebp, ebp
0x1400711d7  jz      short loc_14007121A
0x1400711d9  mov     [r15], cl
0x1400711dc  lea     edi, [r9-8]
0x1400711e0  mov     rax, [r11+r8*8]
0x1400711e4  add     r15, rdx
0x1400711e7  dec     ebp
0x1400711e9  mov     [rax+r14*8+3Bh], r9b
0x1400711ee  cmp     r10b, dl
0x1400711f1  jnz     short loc_14007121A
0x1400711f3  mov     rax, [r11+r8*8]
0x1400711f7  mov     cl, [rax+r14*8+3Ch]
0x1400711fc  cmp     cl, r9b
0x1400711ff  jz      short loc_14007121A
0x140071201  test    ebp, ebp
0x140071203  jz      short loc_14007121A
0x140071205  mov     [r15], cl
0x140071208  lea     edi, [r9-7]
0x14007120c  mov     rax, [r11+r8*8]
0x140071210  add     r15, rdx
0x140071213  dec     ebp
0x140071215  mov     [rax+r14*8+3Ch], r9b
0x14007121a  mov     ecx, r13d; FileHandle
0x14007121d  mov     [rsp+98h+Mode], esi
0x140071221  call    _isatty
0x140071226  test    eax, eax
0x140071228  jz      loc_1400712B9
0x14007122e  mov     rax, [rsp+98h+var_58]
0x140071233  lea     rcx, __pioinfo
0x14007123a  mov     rax, [rcx+rax*8]
0x14007123e  cmp     [rax+r14*8+38h], sil
0x140071243  jge     short loc_1400712B9
0x140071245  mov     rcx, [rsp+98h+hConsoleHandle]; hConsoleHandle
0x14007124a  lea     rdx, [rsp+98h+Mode]; lpMode
0x14007124f  call    cs:__imp_GetConsoleMode
0x140071255  test    eax, eax
0x140071257  jz      short loc_1400712B9
0x140071259  cmp     [rsp+98h+arg_0], 2
0x140071261  jnz     short loc_1400712BE
0x140071263  mov     rcx, [rsp+98h+hConsoleHandle]; hConsoleInput
0x140071268  lea     r9, [rsp+98h+NumberOfCharsRead]; lpNumberOfCharsRead
0x140071270  shr     ebp, 1
0x140071272  mov     rdx, r15; lpBuffer
0x140071275  mov     r8d, ebp; nNumberOfCharsToRead
0x140071278  mov     [rsp+98h+NumberOfCharsRead], esi
0x14007127f  mov     [rsp+98h+pInputControl], rsi; pInputControl
0x140071284  call    cs:__imp_ReadConsoleW
0x14007128a  test    eax, eax
0x14007128c  jnz     short loc_1400712AD
0x14007128e  call    cs:__imp_GetLastError
0x140071294  mov     ecx, eax
0x140071296  call    __acrt_errno_map_os_error
0x14007129b  or      edi, 0FFFFFFFFh
0x14007129e  mov     rcx, rbx; Block
0x1400712a1  call    _free_base
0x1400712a6  mov     eax, edi
0x1400712a8  jmp     loc_140071433
0x1400712ad  mov     eax, [rsp+98h+NumberOfCharsRead]
0x1400712b4  lea     edi, [rdi+rax*2]
0x1400712b7  jmp     short loc_140071300
0x1400712b9  mov     byte ptr [rsp+98h+var_50], sil
0x1400712be  mov     rcx, [rsp+98h+hConsoleHandle]; hFile
0x1400712c3  lea     r9, [rsp+98h+NumberOfCharsRead]; lpNumberOfBytesRead
0x1400712cb  mov     r8d, ebp; nNumberOfBytesToRead
0x1400712ce  mov     [rsp+98h+NumberOfCharsRead], esi
0x1400712d5  mov     rdx, r15; lpBuffer
0x1400712d8  mov     [rsp+98h+pInputControl], rsi; lpOverlapped
0x1400712dd  call    cs:__imp_ReadFile
0x1400712e3  test    eax, eax
0x1400712e5  jz      loc_1400713DF
0x1400712eb  cmp     [rsp+98h+NumberOfCharsRead], r12d
0x1400712f3  ja      loc_1400713DF
0x1400712f9  add     edi, [rsp+98h+NumberOfCharsRead]
0x140071300  mov     rdx, [rsp+98h+var_58]
0x140071305  lea     r11, __pioinfo
0x14007130c  mov     rax, [r11+rdx*8]
0x140071310  cmp     [rax+r14*8+38h], sil
0x140071315  jge     short loc_14007129E
0x140071317  cmp     [rsp+98h+arg_0], 2
0x14007131f  movsxd  r8, edi
0x140071322  jz      short loc_140071349
0x140071324  mov     r9, [rsp+98h+arg_8]
0x14007132c  mov     rax, r12
0x14007132f  shr     rax, 1
0x140071332  mov     rdx, r15
0x140071335  mov     ecx, r13d
0x140071338  mov     [rsp+98h+pInputControl], rax
0x14007133d  call    translate_ansi_or_utf8_nolock
0x140071342  mov     edi, eax
0x140071344  jmp     loc_14007129E
0x140071349  shr     r8, 1
0x14007134c  cmp     byte ptr [rsp+98h+var_50], sil
0x140071351  jz      short loc_1400713CD
0x140071353  mov     r10, [rsp+98h+var_48]
0x140071358  mov     rax, r10
0x14007135b  mov     rdi, r10
0x14007135e  lea     r9, [r10+r8*2]
0x140071362  cmp     r10, r9
0x140071365  jnb     short loc_1400713C0
0x140071367  mov     esi, 0Ah
0x14007136c  movzx   ecx, word ptr [rax]
0x14007136f  cmp     cx, 1Ah
0x140071373  jz      short loc_1400713AF
0x140071375  cmp     cx, 0Dh
0x140071379  jnz     short loc_140071395
0x14007137b  lea     r8, [rax+2]
0x14007137f  cmp     r8, r9
0x140071382  jnb     short loc_140071395
0x140071384  cmp     [r8], si
0x140071388  jnz     short loc_140071395
0x14007138a  movzx   ecx, si
0x14007138d  mov     r11d, 4
0x140071393  jmp     short loc_14007139B
0x140071395  mov     r11d, 2
0x14007139b  add     rax, r11
0x14007139e  mov     [rdi], cx
0x1400713a1  lea     r8, [rdi+2]
0x1400713a5  mov     rdi, r8
0x1400713a8  cmp     rax, r9
0x1400713ab  jb      short loc_14007136C
0x1400713ad  jmp     short loc_1400713C0
0x1400713af  lea     rcx, __pioinfo
0x1400713b6  mov     rax, [rcx+rdx*8]
0x1400713ba  or      byte ptr [rax+r14*8+38h], 2
0x1400713c0  sub     rdi, r10
0x1400713c3  sar     rdi, 1
0x1400713c6  add     edi, edi
0x1400713c8  jmp     loc_14007129E
0x1400713cd  mov     rdx, [rsp+98h+var_48]
0x1400713d2  mov     ecx, r13d
0x1400713d5  call    translate_text_mode_nolock_wchar_t_
0x1400713da  jmp     loc_140071342
0x1400713df  call    cs:__imp_GetLastError
0x1400713e5  cmp     eax, 5
0x1400713e8  jnz     short loc_140071405
0x1400713ea  call    _errno
0x1400713ef  mov     dword ptr [rax], 9
0x1400713f5  call    __doserrno
0x1400713fa  mov     dword ptr [rax], 5
0x140071400  jmp     loc_14007129B
0x140071405  cmp     eax, 6Dh ; 'm'
0x140071408  jnz     loc_140071294
0x14007140e  mov     edi, esi
0x140071410  jmp     loc_14007129E
0x140071415  xor     eax, eax
0x140071417  jmp     short loc_140071433
0x140071419  call    __doserrno
0x14007141e  mov     [rax], esi
0x140071420  call    _errno
0x140071425  mov     dword ptr [rax], 9
0x14007142b  call    _invalid_parameter_noinfo
0x140071430  or      eax, 0FFFFFFFFh
0x140071433  mov     rbx, [rsp+98h+arg_10]
0x14007143b  add     rsp, 60h
0x14007143f  pop     r15
0x140071441  pop     r14
0x140071443  pop     r13
0x140071445  pop     r12
0x140071447  pop     rdi
0x140071448  pop     rsi
0x140071449  pop     rbp
0x14007144a  retn
```
