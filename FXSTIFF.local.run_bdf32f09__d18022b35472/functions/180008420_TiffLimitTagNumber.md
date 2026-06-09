# TiffLimitTagNumber

- ea: `0x180008420`
- end: `0x180008795`
- name: `TiffLimitTagNumber`
- size: `885`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x180008420`
- `0x180008c80`
- `0x180009a7c`
- `0x180009aa4`
- `0x180009bd0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800084d1`
- `KERNEL32!GetLastError` at `0x1800085bc`
- `KERNEL32!GetLastError` at `0x180008612`
- `KERNEL32!GetLastError` at `0x18000865c`
- `KERNEL32!GetLastError` at `0x1800086af`
- `KERNEL32!GetLastError` at `0x180008705`
- `KERNEL32!GetLastError` at `0x18000875f`
- `KERNEL32!GetLastError` at `0x1800084d1`
- `KERNEL32!GetLastError` at `0x1800085bc`
- `KERNEL32!GetLastError` at `0x180008612`
- `KERNEL32!GetLastError` at `0x18000865c`
- `KERNEL32!GetLastError` at `0x1800086af`
- `KERNEL32!GetLastError` at `0x180008705`
- `KERNEL32!GetLastError` at `0x18000875f`
- `KERNEL32!SetFilePointer` at `0x1800085b1`
- `KERNEL32!SetFilePointer` at `0x180008651`
- `KERNEL32!SetFilePointer` at `0x1800086fa`
- `KERNEL32!SetFilePointer` at `0x1800085b1`
- `KERNEL32!SetFilePointer` at `0x180008651`
- `KERNEL32!SetFilePointer` at `0x1800086fa`
- `KERNEL32!WriteFile` at `0x1800086a5`
- `KERNEL32!WriteFile` at `0x180008751`
- `KERNEL32!WriteFile` at `0x1800086a5`
- `KERNEL32!WriteFile` at `0x180008751`
- `KERNEL32!SetLastError` at `0x180008591`
- `KERNEL32!SetLastError` at `0x180008591`
- `KERNEL32!ReadFile` at `0x180008608`
- `KERNEL32!ReadFile` at `0x180008608`
- `KERNEL32!CloseHandle` at `0x180008585`
- `KERNEL32!CloseHandle` at `0x180008585`

## pseudocode

```c
__int64 __fastcall TiffLimitTagNumber(LPCWSTR lpFileName, unsigned int a2)
{
  __int64 v3; // rbx
  DWORD LastError; // eax
  unsigned int v6; // edi
  HANDLE v7; // rsi
  DWORD v8; // ebx
  DWORD v9; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  unsigned int v12; // [rsp+30h] [rbp-20h] BYREF
  int Buffer; // [rsp+34h] [rbp-1Ch] BYREF
  LONG lDistanceToMove[2]; // [rsp+38h] [rbp-18h] BYREF
  HANDLE hObject; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v16; // [rsp+98h] [rbp+48h] BYREF
  unsigned __int16 v17; // [rsp+A0h] [rbp+50h] BYREF
  DWORD NumberOfBytesRead; // [rsp+A8h] [rbp+58h] BYREF

  v16 = a2;
  hObject = (HANDLE)-1LL;
  v17 = 0;
  NumberOfBytesRead = 0;
  Buffer = 0;
  *(_QWORD *)lDistanceToMove = 0;
  v12 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids);
  }
  if ( !(unsigned int)TiffOpenFile(lpFileName, &hObject, &v12, lDistanceToMove, &v17) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v3 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      LastError = GetLastError();
      WPP_SF_d(v3, 58, &WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids, LastError);
    }
    return 0;
  }
  v6 = 0;
  v7 = hObject;
  if ( lDistanceToMove[1] + 12 * (unsigned int)v17 > (unsigned __int64)v12 - 4 )
  {
    v8 = 1392;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids);
    }
    goto LABEL_22;
  }
  v8 = 0;
  if ( v17 <= v16 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids, v17, v16);
    }
    goto LABEL_21;
  }
  if ( SetFilePointer(hObject, lDistanceToMove[1] + 12 * v17, 0, 0) == -1 )
  {
    v9 = GetLastError();
    v8 = v9;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_22;
    }
    v11 = 61;
    goto LABEL_32;
  }
  if ( !ReadFile(v7, &Buffer, 4u, &NumberOfBytesRead, 0) )
  {
    v9 = GetLastError();
    v8 = v9;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_22;
    }
    v11 = 62;
    goto LABEL_32;
  }
  if ( SetFilePointer(v7, lDistanceToMove[1], 0, 0) == -1 )
  {
    v9 = GetLastError();
    v8 = v9;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_22;
    }
    v11 = 63;
    goto LABEL_32;
  }
  if ( !WriteFile(v7, &v16, 2u, &NumberOfBytesRead, 0) )
  {
    v9 = GetLastError();
    v8 = v9;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_22;
    }
    v11 = 64;
    goto LABEL_32;
  }
  if ( SetFilePointer(v7, lDistanceToMove[1] + 12 * v16, 0, 0) == -1 )
  {
    v9 = GetLastError();
    v8 = v9;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_22;
    }
    v11 = 65;
    goto LABEL_32;
  }
  if ( !WriteFile(v7, &Buffer, 4u, &NumberOfBytesRead, 0) )
  {
    v9 = GetLastError();
    v8 = v9;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_22;
    }
    v11 = 66;
LABEL_32:
    WPP_SF_d(v10[2], v11, &WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids, v9);
    goto LABEL_22;
  }
LABEL_21:
  v6 = 1;
LABEL_22:
  if ( v7 != (HANDLE)-1LL )
    CloseHandle(v7);
  if ( !v6 )
    SetLastError(v8);
  return v6;
}

```

## disassembly

```asm
0x180008420  mov     [rsp-38h+arg_8], edx
0x180008424  push    rbp
0x180008425  push    rbx
0x180008426  push    rsi
0x180008427  push    rdi
0x180008428  push    r13
0x18000842a  push    r14
0x18000842c  push    r15
0x18000842e  mov     rbp, rsp
0x180008431  sub     rsp, 50h
0x180008435  xor     eax, eax
0x180008437  mov     [rbp+hObject], 0FFFFFFFFFFFFFFFFh
0x18000843f  mov     [rbp+arg_10], ax
0x180008443  mov     rbx, rcx
0x180008446  mov     [rbp+NumberOfBytesRead], eax
0x180008449  mov     [rbp+Buffer], eax
0x18000844c  mov     qword ptr [rbp+lDistanceToMove], 0
0x180008454  mov     [rbp+var_20], 0
0x18000845b  mov     rcx, cs:WPP_GLOBAL_Control
0x180008462  lea     r15, WPP_GLOBAL_Control
0x180008469  lea     r13, WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids
0x180008470  lea     r14d, [rax+2]
0x180008474  cmp     rcx, r15
0x180008477  jz      short loc_180008494
0x180008479  test    [rcx+1Ch], r14b
0x18000847d  jz      short loc_180008494
0x18000847f  cmp     byte ptr [rcx+19h], 5
0x180008483  jb      short loc_180008494
0x180008485  mov     rcx, [rcx+10h]
0x180008489  lea     edx, [rax+39h]
0x18000848c  mov     r8, r13
0x18000848f  call    WPP_SF_
0x180008494  lea     rax, [rbp+arg_10]
0x180008498  mov     rcx, rbx; lpFileName
0x18000849b  lea     r9, [rbp+lDistanceToMove]
0x18000849f  mov     [rsp+50h+lpOverlapped], rax; lpBuffer
0x1800084a4  lea     r8, [rbp+var_20]
0x1800084a8  lea     rdx, [rbp+hObject]
0x1800084ac  call    TiffOpenFile
0x1800084b1  test    eax, eax
0x1800084b3  jnz     short loc_1800084F1
0x1800084b5  mov     rbx, cs:WPP_GLOBAL_Control
0x1800084bc  cmp     rbx, r15
0x1800084bf  jz      short loc_1800084EA
0x1800084c1  test    [rbx+1Ch], r14b
0x1800084c5  jz      short loc_1800084EA
0x1800084c7  cmp     [rbx+19h], r14b
0x1800084cb  jb      short loc_1800084EA
0x1800084cd  mov     rbx, [rbx+10h]
0x1800084d1  call    cs:__imp_GetLastError
0x1800084d7  mov     edx, 3Ah ; ':'
0x1800084dc  mov     r8, r13
0x1800084df  mov     r9d, eax
0x1800084e2  mov     rcx, rbx
0x1800084e5  call    WPP_SF_d
0x1800084ea  xor     eax, eax
0x1800084ec  jmp     loc_180008599
0x1800084f1  mov     eax, [rbp+lDistanceToMove+4]
0x1800084f4  xor     edi, edi
0x1800084f6  movzx   r9d, [rbp+arg_10]
0x1800084fb  mov     rsi, [rbp+hObject]
0x1800084ff  lea     ecx, [r9+r9*2]
0x180008503  lea     edx, [rax+rcx*4]; lDistanceToMove
0x180008506  mov     ecx, [rbp+var_20]
0x180008509  sub     rcx, 4
0x18000850d  mov     eax, edx
0x18000850f  cmp     rax, rcx
0x180008512  jbe     short loc_180008542
0x180008514  mov     ebx, 570h
0x180008519  mov     rcx, cs:WPP_GLOBAL_Control
0x180008520  cmp     rcx, r15
0x180008523  jz      short loc_18000857C
0x180008525  test    [rcx+1Ch], r14b
0x180008529  jz      short loc_18000857C
0x18000852b  cmp     [rcx+19h], r14b
0x18000852f  jb      short loc_18000857C
0x180008531  mov     rcx, [rcx+10h]
0x180008535  lea     edx, [rdi+3Bh]
0x180008538  mov     r8, r13
0x18000853b  call    WPP_SF_
0x180008540  jmp     short loc_18000857C
0x180008542  mov     eax, [rbp+arg_8]
0x180008545  xor     ebx, ebx
0x180008547  cmp     r9d, eax
0x18000854a  ja      short loc_1800085A8
0x18000854c  mov     rcx, cs:WPP_GLOBAL_Control
0x180008553  cmp     rcx, r15
0x180008556  jz      short loc_180008577
0x180008558  test    [rcx+1Ch], r14b
0x18000855c  jz      short loc_180008577
0x18000855e  cmp     byte ptr [rcx+19h], 5
0x180008562  jb      short loc_180008577
0x180008564  mov     rcx, [rcx+10h]
0x180008568  lea     edx, [rbx+3Ch]
0x18000856b  mov     r8, r13
0x18000856e  mov     dword ptr [rsp+50h+lpOverlapped], eax
0x180008572  call    WPP_SF_dd
0x180008577  mov     edi, 1
0x18000857c  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180008580  jz      short loc_18000858B
0x180008582  mov     rcx, rsi; hObject
0x180008585  call    cs:__imp_CloseHandle
0x18000858b  test    edi, edi
0x18000858d  jnz     short loc_180008597
0x18000858f  mov     ecx, ebx; dwErrCode
0x180008591  call    cs:__imp_SetLastError
0x180008597  mov     eax, edi
0x180008599  add     rsp, 50h
0x18000859d  pop     r15
0x18000859f  pop     r14
0x1800085a1  pop     r13
0x1800085a3  pop     rdi
0x1800085a4  pop     rsi
0x1800085a5  pop     rbx
0x1800085a6  pop     rbp
0x1800085a7  retn
0x1800085a8  xor     r9d, r9d; dwMoveMethod
0x1800085ab  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800085ae  mov     rcx, rsi; hFile
0x1800085b1  call    cs:__imp_SetFilePointer
0x1800085b7  cmp     eax, 0FFFFFFFFh
0x1800085ba  jnz     short loc_1800085F2
0x1800085bc  call    cs:__imp_GetLastError
0x1800085c2  mov     ebx, eax
0x1800085c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800085cb  cmp     rcx, r15
0x1800085ce  jz      short loc_18000857C
0x1800085d0  test    [rcx+1Ch], r14b
0x1800085d4  jz      short loc_18000857C
0x1800085d6  cmp     [rcx+19h], r14b
0x1800085da  jb      short loc_18000857C
0x1800085dc  mov     edx, 3Dh ; '='
0x1800085e1  mov     rcx, [rcx+10h]
0x1800085e5  mov     r9d, eax
0x1800085e8  mov     r8, r13
0x1800085eb  call    WPP_SF_d
0x1800085f0  jmp     short loc_18000857C
0x1800085f2  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800085f6  mov     [rsp+50h+lpOverlapped], rbx; lpOverlapped
0x1800085fb  mov     r8d, 4; nNumberOfBytesToRead
0x180008601  lea     rdx, [rbp+Buffer]; lpBuffer
0x180008605  mov     rcx, rsi; hFile
0x180008608  call    cs:__imp_ReadFile
0x18000860e  test    eax, eax
0x180008610  jnz     short loc_180008645
0x180008612  call    cs:__imp_GetLastError
0x180008618  mov     ebx, eax
0x18000861a  mov     rcx, cs:WPP_GLOBAL_Control
0x180008621  cmp     rcx, r15
0x180008624  jz      loc_18000857C
0x18000862a  test    [rcx+1Ch], r14b
0x18000862e  jz      loc_18000857C
0x180008634  cmp     [rcx+19h], r14b
0x180008638  jb      loc_18000857C
0x18000863e  mov     edx, 3Eh ; '>'
0x180008643  jmp     short loc_1800085E1
0x180008645  mov     edx, [rbp+lDistanceToMove+4]; lDistanceToMove
0x180008648  xor     r9d, r9d; dwMoveMethod
0x18000864b  xor     r8d, r8d; lpDistanceToMoveHigh
0x18000864e  mov     rcx, rsi; hFile
0x180008651  call    cs:__imp_SetFilePointer
0x180008657  cmp     eax, 0FFFFFFFFh
0x18000865a  jnz     short loc_180008692
0x18000865c  call    cs:__imp_GetLastError
0x180008662  mov     ebx, eax
0x180008664  mov     rcx, cs:WPP_GLOBAL_Control
0x18000866b  cmp     rcx, r15
0x18000866e  jz      loc_18000857C
0x180008674  test    [rcx+1Ch], r14b
0x180008678  jz      loc_18000857C
0x18000867e  cmp     [rcx+19h], r14b
0x180008682  jb      loc_18000857C
0x180008688  mov     edx, 3Fh ; '?'
0x18000868d  jmp     loc_1800085E1
0x180008692  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesWritten
0x180008696  mov     [rsp+50h+lpOverlapped], rbx; lpOverlapped
0x18000869b  mov     r8d, r14d; nNumberOfBytesToWrite
0x18000869e  lea     rdx, [rbp+arg_8]; lpBuffer
0x1800086a2  mov     rcx, rsi; hFile
0x1800086a5  call    cs:__imp_WriteFile
0x1800086ab  test    eax, eax
0x1800086ad  jnz     short loc_1800086E5
0x1800086af  call    cs:__imp_GetLastError
0x1800086b5  mov     ebx, eax
0x1800086b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800086be  cmp     rcx, r15
0x1800086c1  jz      loc_18000857C
0x1800086c7  test    [rcx+1Ch], r14b
0x1800086cb  jz      loc_18000857C
0x1800086d1  cmp     [rcx+19h], r14b
0x1800086d5  jb      loc_18000857C
0x1800086db  mov     edx, 40h ; '@'
0x1800086e0  jmp     loc_1800085E1
0x1800086e5  mov     eax, [rbp+arg_8]
0x1800086e8  xor     r9d, r9d; dwMoveMethod
0x1800086eb  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800086ee  lea     ecx, [rax+rax*2]
0x1800086f1  mov     eax, [rbp+lDistanceToMove+4]
0x1800086f4  lea     edx, [rax+rcx*4]; lDistanceToMove
0x1800086f7  mov     rcx, rsi; hFile
0x1800086fa  call    cs:__imp_SetFilePointer
0x180008700  cmp     eax, 0FFFFFFFFh
0x180008703  jnz     short loc_18000873B
0x180008705  call    cs:__imp_GetLastError
0x18000870b  mov     ebx, eax
0x18000870d  mov     rcx, cs:WPP_GLOBAL_Control
0x180008714  cmp     rcx, r15
0x180008717  jz      loc_18000857C
0x18000871d  test    [rcx+1Ch], r14b
0x180008721  jz      loc_18000857C
0x180008727  cmp     [rcx+19h], r14b
0x18000872b  jb      loc_18000857C
0x180008731  mov     edx, 41h ; 'A'
0x180008736  jmp     loc_1800085E1
0x18000873b  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesWritten
0x18000873f  mov     [rsp+50h+lpOverlapped], rbx; lpOverlapped
0x180008744  mov     r8d, 4; nNumberOfBytesToWrite
0x18000874a  lea     rdx, [rbp+Buffer]; lpBuffer
0x18000874e  mov     rcx, rsi; hFile
0x180008751  call    cs:__imp_WriteFile
0x180008757  test    eax, eax
0x180008759  jnz     loc_180008577
0x18000875f  call    cs:__imp_GetLastError
0x180008765  mov     ebx, eax
0x180008767  mov     rcx, cs:WPP_GLOBAL_Control
0x18000876e  cmp     rcx, r15
0x180008771  jz      loc_18000857C
0x180008777  test    [rcx+1Ch], r14b
0x18000877b  jz      loc_18000857C
0x180008781  cmp     [rcx+19h], r14b
0x180008785  jb      loc_18000857C
0x18000878b  mov     edx, 42h ; 'B'
0x180008790  jmp     loc_1800085E1
```
