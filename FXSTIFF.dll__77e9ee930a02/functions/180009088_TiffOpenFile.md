# TiffOpenFile

- ea: `0x180009088`
- end: `0x1800093bd`
- name: `TiffOpenFile`
- size: `821`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, HANDLE *, unsigned int *, void *, _WORD *lpBuffer)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180006bb0`
- `0x180008790`

## callees

- `0x180009088`
- `0x180009f04`
- `0x180009f34`
- `0x1800131b4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000912d`
- `KERNEL32!GetLastError` at `0x180009176`
- `KERNEL32!GetLastError` at `0x180009226`
- `KERNEL32!GetLastError` at `0x1800092a9`
- `KERNEL32!GetLastError` at `0x18000930f`
- `KERNEL32!GetLastError` at `0x18000912d`
- `KERNEL32!GetLastError` at `0x180009176`
- `KERNEL32!GetLastError` at `0x180009226`
- `KERNEL32!GetLastError` at `0x1800092a9`
- `KERNEL32!GetLastError` at `0x18000930f`
- `KERNEL32!SetFilePointer` at `0x180009299`
- `KERNEL32!SetFilePointer` at `0x180009299`
- `KERNEL32!SetLastError` at `0x18000939d`
- `KERNEL32!SetLastError` at `0x18000939d`
- `KERNEL32!ReadFile` at `0x180009216`
- `KERNEL32!ReadFile` at `0x1800092ff`
- `KERNEL32!ReadFile` at `0x180009216`
- `KERNEL32!ReadFile` at `0x1800092ff`
- `KERNEL32!GetFileSize` at `0x180009158`
- `KERNEL32!GetFileSize` at `0x180009158`
- `KERNEL32!CloseHandle` at `0x18000937f`
- `KERNEL32!CloseHandle` at `0x18000937f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TiffOpenFile(LPCWSTR lpFileName, HANDLE *a2, unsigned int *a3, void *a4, _WORD *lpBuffer)
{
  void *File; // rax
  __int64 v10; // rbx
  DWORD v11; // eax
  DWORD FileSize; // eax
  _WORD *v14; // r15
  DWORD LastError; // eax
  DWORD v16; // ebx
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  unsigned int v21; // edx
  unsigned int v22; // edi
  DWORD NumberOfBytesRead; // [rsp+98h] [rbp+10h] BYREF

  NumberOfBytesRead = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids);
  }
  File = (void *)InternalSafeCreateFile(lpFileName, 0xC0000000, 0, 3u, 0);
  *a2 = File;
  if ( File != (void *)-1LL )
  {
    FileSize = GetFileSize(File, 0);
    v14 = lpBuffer;
    *a3 = FileSize;
    if ( FileSize == -1 )
    {
      LastError = GetLastError();
      v16 = LastError;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_47;
      }
      v18 = 29;
      goto LABEL_16;
    }
    if ( FileSize <= 8 )
    {
      v16 = 1392;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_47;
      }
      v20 = 30;
      goto LABEL_46;
    }
    if ( ReadFile(*a2, a4, 8u, &NumberOfBytesRead, 0) )
    {
      if ( *(_WORD *)a4 != 18761 || *((_WORD *)a4 + 1) != 42 || (v21 = *((_DWORD *)a4 + 1), v21 < 8) || v21 > *a3 )
      {
        v16 = 1392;
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_47;
        }
        v20 = 32;
LABEL_46:
        WPP_SF_(v19[2], v20, &WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids);
        goto LABEL_47;
      }
      if ( SetFilePointer(*a2, v21, 0, 0) == -1 )
      {
        LastError = GetLastError();
        v16 = LastError;
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_47;
        }
        v18 = 33;
      }
      else
      {
        if ( ReadFile(*a2, v14, 2u, &NumberOfBytesRead, 0) )
          return 1;
        LastError = GetLastError();
        v16 = LastError;
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
LABEL_47:
          v22 = 0;
          if ( *a2 != (HANDLE)-1LL )
          {
            CloseHandle(*a2);
            *a2 = (HANDLE)-1LL;
          }
          *a3 = 0;
          *v14 = 0;
          SetLastError(v16);
          return v22;
        }
        v18 = 34;
      }
    }
    else
    {
      LastError = GetLastError();
      v16 = LastError;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_47;
      }
      v18 = 31;
    }
LABEL_16:
    WPP_SF_d(v17[2], v18, &WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids, LastError);
    goto LABEL_47;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v10 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v11 = GetLastError();
    WPP_SF_d(v10, 28, &WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids, v11);
  }
  return 0;
}

```

## disassembly

```asm
0x180009088  mov     rax, rsp
0x18000908b  push    rbx
0x18000908c  push    rbp
0x18000908d  push    rsi
0x18000908e  push    rdi
0x18000908f  push    r12
0x180009091  push    r13
0x180009093  push    r14
0x180009095  push    r15
0x180009097  sub     rsp, 48h
0x18000909b  mov     rbx, r9
0x18000909e  mov     dword ptr [rax+10h], 0
0x1800090a5  mov     r14, r8
0x1800090a8  mov     rsi, rdx
0x1800090ab  mov     rdi, rcx
0x1800090ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800090b5  lea     r12, WPP_GLOBAL_Control
0x1800090bc  lea     r13, WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids
0x1800090c3  mov     ebp, 2
0x1800090c8  cmp     rcx, r12
0x1800090cb  jz      short loc_1800090E8
0x1800090cd  test    [rcx+1Ch], bpl
0x1800090d1  jz      short loc_1800090E8
0x1800090d3  cmp     byte ptr [rcx+19h], 5
0x1800090d7  jb      short loc_1800090E8
0x1800090d9  mov     rcx, [rcx+10h]
0x1800090dd  lea     edx, [rbp+19h]
0x1800090e0  mov     r8, r13
0x1800090e3  call    WPP_SF_
0x1800090e8  mov     [rsp+88h+var_60], 0; int
0x1800090f0  xor     r8d, r8d; dwShareMode
0x1800090f3  mov     edx, 0C0000000h; dwDesiredAccess
0x1800090f8  mov     dword ptr [rsp+88h+lpOverlapped], 3; DWORD
0x180009100  mov     rcx, rdi; lpFileName
0x180009103  call    InternalSafeCreateFile
0x180009108  mov     [rsi], rax
0x18000910b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000910f  jnz     short loc_180009153
0x180009111  mov     rbx, cs:WPP_GLOBAL_Control
0x180009118  cmp     rbx, r12
0x18000911b  jz      short loc_18000914C
0x18000911d  test    [rbx+1Ch], bpl
0x180009121  jz      short loc_18000914C
0x180009123  cmp     [rbx+19h], bpl
0x180009127  jb      short loc_18000914C
0x180009129  mov     rbx, [rbx+10h]
0x18000912d  call    cs:__imp_GetLastError
0x180009134  nop     dword ptr [rax+rax+00h]
0x180009139  mov     edx, 1Ch
0x18000913e  mov     r8, r13
0x180009141  mov     r9d, eax
0x180009144  mov     rcx, rbx
0x180009147  call    WPP_SF_d
0x18000914c  xor     eax, eax
0x18000914e  jmp     loc_1800093AB
0x180009153  xor     edx, edx; lpFileSizeHigh
0x180009155  mov     rcx, rax; hFile
0x180009158  call    cs:__imp_GetFileSize
0x18000915f  nop     dword ptr [rax+rax+00h]
0x180009164  mov     r15, [rsp+88h+lpBuffer]
0x18000916c  or      edi, 0FFFFFFFFh
0x18000916f  mov     [r14], eax
0x180009172  cmp     eax, edi
0x180009174  jnz     short loc_1800091C1
0x180009176  call    cs:__imp_GetLastError
0x18000917d  nop     dword ptr [rax+rax+00h]
0x180009182  mov     ebx, eax
0x180009184  mov     rcx, cs:WPP_GLOBAL_Control
0x18000918b  cmp     rcx, r12
0x18000918e  jz      loc_180009374
0x180009194  test    [rcx+1Ch], bpl
0x180009198  jz      loc_180009374
0x18000919e  cmp     [rcx+19h], bpl
0x1800091a2  jb      loc_180009374
0x1800091a8  mov     edx, 1Dh
0x1800091ad  mov     rcx, [rcx+10h]
0x1800091b1  mov     r9d, eax
0x1800091b4  mov     r8, r13
0x1800091b7  call    WPP_SF_d
0x1800091bc  jmp     loc_180009374
0x1800091c1  cmp     eax, 8
0x1800091c4  ja      short loc_1800091F9
0x1800091c6  mov     ebx, 570h
0x1800091cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800091d2  cmp     rcx, r12
0x1800091d5  jz      loc_180009374
0x1800091db  test    [rcx+1Ch], bpl
0x1800091df  jz      loc_180009374
0x1800091e5  cmp     [rcx+19h], bpl
0x1800091e9  jb      loc_180009374
0x1800091ef  mov     edx, 1Eh
0x1800091f4  jmp     loc_180009368
0x1800091f9  mov     rcx, [rsi]; hFile
0x1800091fc  lea     r9, [rsp+88h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180009204  mov     r8d, 8; nNumberOfBytesToRead
0x18000920a  mov     [rsp+88h+lpOverlapped], 0; lpOverlapped
0x180009213  mov     rdx, rbx; lpBuffer
0x180009216  call    cs:__imp_ReadFile
0x18000921d  nop     dword ptr [rax+rax+00h]
0x180009222  test    eax, eax
0x180009224  jnz     short loc_180009262
0x180009226  call    cs:__imp_GetLastError
0x18000922d  nop     dword ptr [rax+rax+00h]
0x180009232  mov     ebx, eax
0x180009234  mov     rcx, cs:WPP_GLOBAL_Control
0x18000923b  cmp     rcx, r12
0x18000923e  jz      loc_180009374
0x180009244  test    [rcx+1Ch], bpl
0x180009248  jz      loc_180009374
0x18000924e  cmp     [rcx+19h], bpl
0x180009252  jb      loc_180009374
0x180009258  mov     edx, 1Fh
0x18000925d  jmp     loc_1800091AD
0x180009262  mov     eax, 4949h
0x180009267  cmp     [rbx], ax
0x18000926a  jnz     loc_180009346
0x180009270  cmp     word ptr [rbx+2], 2Ah ; '*'
0x180009275  jnz     loc_180009346
0x18000927b  mov     edx, [rbx+4]; lDistanceToMove
0x18000927e  cmp     edx, 8
0x180009281  jb      loc_180009346
0x180009287  cmp     edx, [r14]
0x18000928a  ja      loc_180009346
0x180009290  mov     rcx, [rsi]; hFile
0x180009293  xor     r9d, r9d; dwMoveMethod
0x180009296  xor     r8d, r8d; lpDistanceToMoveHigh
0x180009299  call    cs:__imp_SetFilePointer
0x1800092a0  nop     dword ptr [rax+rax+00h]
0x1800092a5  cmp     eax, edi
0x1800092a7  jnz     short loc_1800092E5
0x1800092a9  call    cs:__imp_GetLastError
0x1800092b0  nop     dword ptr [rax+rax+00h]
0x1800092b5  mov     ebx, eax
0x1800092b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800092be  cmp     rcx, r12
0x1800092c1  jz      loc_180009374
0x1800092c7  test    [rcx+1Ch], bpl
0x1800092cb  jz      loc_180009374
0x1800092d1  cmp     [rcx+19h], bpl
0x1800092d5  jb      loc_180009374
0x1800092db  mov     edx, 21h ; '!'
0x1800092e0  jmp     loc_1800091AD
0x1800092e5  mov     rcx, [rsi]; hFile
0x1800092e8  lea     r9, [rsp+88h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800092f0  mov     r8d, ebp; nNumberOfBytesToRead
0x1800092f3  mov     [rsp+88h+lpOverlapped], 0; lpOverlapped
0x1800092fc  mov     rdx, r15; lpBuffer
0x1800092ff  call    cs:__imp_ReadFile
0x180009306  nop     dword ptr [rax+rax+00h]
0x18000930b  test    eax, eax
0x18000930d  jnz     short loc_18000933F
0x18000930f  call    cs:__imp_GetLastError
0x180009316  nop     dword ptr [rax+rax+00h]
0x18000931b  mov     ebx, eax
0x18000931d  mov     rcx, cs:WPP_GLOBAL_Control
0x180009324  cmp     rcx, r12
0x180009327  jz      short loc_180009374
0x180009329  test    [rcx+1Ch], bpl
0x18000932d  jz      short loc_180009374
0x18000932f  cmp     [rcx+19h], bpl
0x180009333  jb      short loc_180009374
0x180009335  mov     edx, 22h ; '"'
0x18000933a  jmp     loc_1800091AD
0x18000933f  mov     edi, 1
0x180009344  jmp     short loc_1800093A9
0x180009346  mov     ebx, 570h
0x18000934b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009352  cmp     rcx, r12
0x180009355  jz      short loc_180009374
0x180009357  test    [rcx+1Ch], bpl
0x18000935b  jz      short loc_180009374
0x18000935d  cmp     [rcx+19h], bpl
0x180009361  jb      short loc_180009374
0x180009363  mov     edx, 20h ; ' '
0x180009368  mov     rcx, [rcx+10h]
0x18000936c  mov     r8, r13
0x18000936f  call    WPP_SF_
0x180009374  xor     edi, edi
0x180009376  cmp     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x18000937a  jz      short loc_180009392
0x18000937c  mov     rcx, [rsi]; hObject
0x18000937f  call    cs:__imp_CloseHandle
0x180009386  nop     dword ptr [rax+rax+00h]
0x18000938b  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x180009392  xor     ecx, ecx
0x180009394  mov     [r14], edi
0x180009397  mov     [r15], cx
0x18000939b  mov     ecx, ebx; dwErrCode
0x18000939d  call    cs:__imp_SetLastError
0x1800093a4  nop     dword ptr [rax+rax+00h]
0x1800093a9  mov     eax, edi
0x1800093ab  add     rsp, 48h
0x1800093af  pop     r15
0x1800093b1  pop     r14
0x1800093b3  pop     r13
0x1800093b5  pop     r12
0x1800093b7  pop     rdi
0x1800093b8  pop     rsi
0x1800093b9  pop     rbp
0x1800093ba  pop     rbx
0x1800093bb  retn
```
