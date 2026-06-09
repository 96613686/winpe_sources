# TiffOpenFile

- ea: `0x1800395f8`
- end: `0x18003992d`
- name: `TiffOpenFile`
- size: `821`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, HANDLE *, unsigned int *, void *, _WORD *lpBuffer)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180038d48`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x1800308e0`
- `0x1800395f8`

## import_xrefs

- `KERNEL32!ReadFile` at `0x180039786`
- `KERNEL32!ReadFile` at `0x18003986f`
- `KERNEL32!ReadFile` at `0x180039786`
- `KERNEL32!ReadFile` at `0x18003986f`
- `KERNEL32!GetFileSize` at `0x1800396c8`
- `KERNEL32!GetFileSize` at `0x1800396c8`
- `KERNEL32!SetFilePointer` at `0x180039809`
- `KERNEL32!SetFilePointer` at `0x180039809`
- `KERNEL32!CloseHandle` at `0x1800398ef`
- `KERNEL32!CloseHandle` at `0x1800398ef`
- `KERNEL32!SetLastError` at `0x18003990d`
- `KERNEL32!SetLastError` at `0x18003990d`
- `KERNEL32!GetLastError` at `0x18003969d`
- `KERNEL32!GetLastError` at `0x1800396e6`
- `KERNEL32!GetLastError` at `0x180039796`
- `KERNEL32!GetLastError` at `0x180039819`
- `KERNEL32!GetLastError` at `0x18003987f`
- `KERNEL32!GetLastError` at `0x18003969d`
- `KERNEL32!GetLastError` at `0x1800396e6`
- `KERNEL32!GetLastError` at `0x180039796`
- `KERNEL32!GetLastError` at `0x180039819`
- `KERNEL32!GetLastError` at `0x18003987f`

## pseudocode

```c
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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids);
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
        WPP_SF_(v19[2], v20, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids);
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
    WPP_SF_d(v17[2], v18, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids, LastError);
    goto LABEL_47;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v10 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v11 = GetLastError();
    WPP_SF_d(v10, 28, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids, v11);
  }
  return 0;
}

```

## disassembly

```asm
0x1800395f8  mov     rax, rsp
0x1800395fb  push    rbx
0x1800395fc  push    rbp
0x1800395fd  push    rsi
0x1800395fe  push    rdi
0x1800395ff  push    r12
0x180039601  push    r13
0x180039603  push    r14
0x180039605  push    r15
0x180039607  sub     rsp, 48h
0x18003960b  mov     rbx, r9
0x18003960e  mov     dword ptr [rax+10h], 0
0x180039615  mov     r14, r8
0x180039618  mov     rsi, rdx
0x18003961b  mov     rdi, rcx
0x18003961e  mov     rcx, cs:WPP_GLOBAL_Control
0x180039625  lea     r12, WPP_GLOBAL_Control
0x18003962c  lea     r13, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids
0x180039633  mov     ebp, 2
0x180039638  cmp     rcx, r12
0x18003963b  jz      short loc_180039658
0x18003963d  test    [rcx+1Ch], bpl
0x180039641  jz      short loc_180039658
0x180039643  cmp     byte ptr [rcx+19h], 5
0x180039647  jb      short loc_180039658
0x180039649  mov     rcx, [rcx+10h]
0x18003964d  lea     edx, [rbp+19h]
0x180039650  mov     r8, r13
0x180039653  call    WPP_SF_
0x180039658  mov     [rsp+88h+var_60], 0; int
0x180039660  xor     r8d, r8d; dwShareMode
0x180039663  mov     edx, 0C0000000h; dwDesiredAccess
0x180039668  mov     dword ptr [rsp+88h+lpOverlapped], 3; DWORD
0x180039670  mov     rcx, rdi; lpFileName
0x180039673  call    InternalSafeCreateFile
0x180039678  mov     [rsi], rax
0x18003967b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003967f  jnz     short loc_1800396C3
0x180039681  mov     rbx, cs:WPP_GLOBAL_Control
0x180039688  cmp     rbx, r12
0x18003968b  jz      short loc_1800396BC
0x18003968d  test    [rbx+1Ch], bpl
0x180039691  jz      short loc_1800396BC
0x180039693  cmp     [rbx+19h], bpl
0x180039697  jb      short loc_1800396BC
0x180039699  mov     rbx, [rbx+10h]
0x18003969d  call    cs:__imp_GetLastError
0x1800396a4  nop     dword ptr [rax+rax+00h]
0x1800396a9  mov     edx, 1Ch
0x1800396ae  mov     r8, r13
0x1800396b1  mov     r9d, eax
0x1800396b4  mov     rcx, rbx
0x1800396b7  call    WPP_SF_d
0x1800396bc  xor     eax, eax
0x1800396be  jmp     loc_18003991B
0x1800396c3  xor     edx, edx; lpFileSizeHigh
0x1800396c5  mov     rcx, rax; hFile
0x1800396c8  call    cs:__imp_GetFileSize
0x1800396cf  nop     dword ptr [rax+rax+00h]
0x1800396d4  mov     r15, [rsp+88h+lpBuffer]
0x1800396dc  or      edi, 0FFFFFFFFh
0x1800396df  mov     [r14], eax
0x1800396e2  cmp     eax, edi
0x1800396e4  jnz     short loc_180039731
0x1800396e6  call    cs:__imp_GetLastError
0x1800396ed  nop     dword ptr [rax+rax+00h]
0x1800396f2  mov     ebx, eax
0x1800396f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800396fb  cmp     rcx, r12
0x1800396fe  jz      loc_1800398E4
0x180039704  test    [rcx+1Ch], bpl
0x180039708  jz      loc_1800398E4
0x18003970e  cmp     [rcx+19h], bpl
0x180039712  jb      loc_1800398E4
0x180039718  mov     edx, 1Dh
0x18003971d  mov     rcx, [rcx+10h]
0x180039721  mov     r9d, eax
0x180039724  mov     r8, r13
0x180039727  call    WPP_SF_d
0x18003972c  jmp     loc_1800398E4
0x180039731  cmp     eax, 8
0x180039734  ja      short loc_180039769
0x180039736  mov     ebx, 570h
0x18003973b  mov     rcx, cs:WPP_GLOBAL_Control
0x180039742  cmp     rcx, r12
0x180039745  jz      loc_1800398E4
0x18003974b  test    [rcx+1Ch], bpl
0x18003974f  jz      loc_1800398E4
0x180039755  cmp     [rcx+19h], bpl
0x180039759  jb      loc_1800398E4
0x18003975f  mov     edx, 1Eh
0x180039764  jmp     loc_1800398D8
0x180039769  mov     rcx, [rsi]; hFile
0x18003976c  lea     r9, [rsp+88h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180039774  mov     r8d, 8; nNumberOfBytesToRead
0x18003977a  mov     [rsp+88h+lpOverlapped], 0; lpOverlapped
0x180039783  mov     rdx, rbx; lpBuffer
0x180039786  call    cs:__imp_ReadFile
0x18003978d  nop     dword ptr [rax+rax+00h]
0x180039792  test    eax, eax
0x180039794  jnz     short loc_1800397D2
0x180039796  call    cs:__imp_GetLastError
0x18003979d  nop     dword ptr [rax+rax+00h]
0x1800397a2  mov     ebx, eax
0x1800397a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800397ab  cmp     rcx, r12
0x1800397ae  jz      loc_1800398E4
0x1800397b4  test    [rcx+1Ch], bpl
0x1800397b8  jz      loc_1800398E4
0x1800397be  cmp     [rcx+19h], bpl
0x1800397c2  jb      loc_1800398E4
0x1800397c8  mov     edx, 1Fh
0x1800397cd  jmp     loc_18003971D
0x1800397d2  mov     eax, 4949h
0x1800397d7  cmp     [rbx], ax
0x1800397da  jnz     loc_1800398B6
0x1800397e0  cmp     word ptr [rbx+2], 2Ah ; '*'
0x1800397e5  jnz     loc_1800398B6
0x1800397eb  mov     edx, [rbx+4]; lDistanceToMove
0x1800397ee  cmp     edx, 8
0x1800397f1  jb      loc_1800398B6
0x1800397f7  cmp     edx, [r14]
0x1800397fa  ja      loc_1800398B6
0x180039800  mov     rcx, [rsi]; hFile
0x180039803  xor     r9d, r9d; dwMoveMethod
0x180039806  xor     r8d, r8d; lpDistanceToMoveHigh
0x180039809  call    cs:__imp_SetFilePointer
0x180039810  nop     dword ptr [rax+rax+00h]
0x180039815  cmp     eax, edi
0x180039817  jnz     short loc_180039855
0x180039819  call    cs:__imp_GetLastError
0x180039820  nop     dword ptr [rax+rax+00h]
0x180039825  mov     ebx, eax
0x180039827  mov     rcx, cs:WPP_GLOBAL_Control
0x18003982e  cmp     rcx, r12
0x180039831  jz      loc_1800398E4
0x180039837  test    [rcx+1Ch], bpl
0x18003983b  jz      loc_1800398E4
0x180039841  cmp     [rcx+19h], bpl
0x180039845  jb      loc_1800398E4
0x18003984b  mov     edx, 21h ; '!'
0x180039850  jmp     loc_18003971D
0x180039855  mov     rcx, [rsi]; hFile
0x180039858  lea     r9, [rsp+88h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180039860  mov     r8d, ebp; nNumberOfBytesToRead
0x180039863  mov     [rsp+88h+lpOverlapped], 0; lpOverlapped
0x18003986c  mov     rdx, r15; lpBuffer
0x18003986f  call    cs:__imp_ReadFile
0x180039876  nop     dword ptr [rax+rax+00h]
0x18003987b  test    eax, eax
0x18003987d  jnz     short loc_1800398AF
0x18003987f  call    cs:__imp_GetLastError
0x180039886  nop     dword ptr [rax+rax+00h]
0x18003988b  mov     ebx, eax
0x18003988d  mov     rcx, cs:WPP_GLOBAL_Control
0x180039894  cmp     rcx, r12
0x180039897  jz      short loc_1800398E4
0x180039899  test    [rcx+1Ch], bpl
0x18003989d  jz      short loc_1800398E4
0x18003989f  cmp     [rcx+19h], bpl
0x1800398a3  jb      short loc_1800398E4
0x1800398a5  mov     edx, 22h ; '"'
0x1800398aa  jmp     loc_18003971D
0x1800398af  mov     edi, 1
0x1800398b4  jmp     short loc_180039919
0x1800398b6  mov     ebx, 570h
0x1800398bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800398c2  cmp     rcx, r12
0x1800398c5  jz      short loc_1800398E4
0x1800398c7  test    [rcx+1Ch], bpl
0x1800398cb  jz      short loc_1800398E4
0x1800398cd  cmp     [rcx+19h], bpl
0x1800398d1  jb      short loc_1800398E4
0x1800398d3  mov     edx, 20h ; ' '
0x1800398d8  mov     rcx, [rcx+10h]
0x1800398dc  mov     r8, r13
0x1800398df  call    WPP_SF_
0x1800398e4  xor     edi, edi
0x1800398e6  cmp     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x1800398ea  jz      short loc_180039902
0x1800398ec  mov     rcx, [rsi]; hObject
0x1800398ef  call    cs:__imp_CloseHandle
0x1800398f6  nop     dword ptr [rax+rax+00h]
0x1800398fb  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x180039902  xor     ecx, ecx
0x180039904  mov     [r14], edi
0x180039907  mov     [r15], cx
0x18003990b  mov     ecx, ebx; dwErrCode
0x18003990d  call    cs:__imp_SetLastError
0x180039914  nop     dword ptr [rax+rax+00h]
0x180039919  mov     eax, edi
0x18003991b  add     rsp, 48h
0x18003991f  pop     r15
0x180039921  pop     r14
0x180039923  pop     r13
0x180039925  pop     r12
0x180039927  pop     rdi
0x180039928  pop     rsi
0x180039929  pop     rbp
0x18003992a  pop     rbx
0x18003992b  retn
```
