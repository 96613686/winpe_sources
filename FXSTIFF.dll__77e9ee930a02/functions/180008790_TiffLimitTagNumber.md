# TiffLimitTagNumber

- ea: `0x180008790`
- end: `0x180008b63`
- name: `TiffLimitTagNumber`
- size: `979`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x180008790`
- `0x180009088`
- `0x180009f04`
- `0x180009f34`
- `0x18000a070`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180008841`
- `KERNEL32!GetLastError` at `0x180008945`
- `KERNEL32!GetLastError` at `0x1800089aa`
- `KERNEL32!GetLastError` at `0x180008a00`
- `KERNEL32!GetLastError` at `0x180008a5f`
- `KERNEL32!GetLastError` at `0x180008ac1`
- `KERNEL32!GetLastError` at `0x180008b27`
- `KERNEL32!GetLastError` at `0x180008841`
- `KERNEL32!GetLastError` at `0x180008945`
- `KERNEL32!GetLastError` at `0x1800089aa`
- `KERNEL32!GetLastError` at `0x180008a00`
- `KERNEL32!GetLastError` at `0x180008a5f`
- `KERNEL32!GetLastError` at `0x180008ac1`
- `KERNEL32!GetLastError` at `0x180008b27`
- `KERNEL32!SetFilePointer` at `0x180008934`
- `KERNEL32!SetFilePointer` at `0x1800089ef`
- `KERNEL32!SetFilePointer` at `0x180008ab0`
- `KERNEL32!SetFilePointer` at `0x180008934`
- `KERNEL32!SetFilePointer` at `0x1800089ef`
- `KERNEL32!SetFilePointer` at `0x180008ab0`
- `KERNEL32!WriteFile` at `0x180008a4f`
- `KERNEL32!WriteFile` at `0x180008b13`
- `KERNEL32!WriteFile` at `0x180008a4f`
- `KERNEL32!WriteFile` at `0x180008b13`
- `KERNEL32!SetLastError` at `0x18000890d`
- `KERNEL32!SetLastError` at `0x18000890d`
- `KERNEL32!ReadFile` at `0x18000899a`
- `KERNEL32!ReadFile` at `0x18000899a`
- `KERNEL32!CloseHandle` at `0x1800088fb`
- `KERNEL32!CloseHandle` at `0x1800088fb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180008790  mov     [rsp-38h+arg_8], edx
0x180008794  push    rbp
0x180008795  push    rbx
0x180008796  push    rsi
0x180008797  push    rdi
0x180008798  push    r13
0x18000879a  push    r14
0x18000879c  push    r15
0x18000879e  mov     rbp, rsp
0x1800087a1  sub     rsp, 50h
0x1800087a5  xor     eax, eax
0x1800087a7  mov     [rbp+hObject], 0FFFFFFFFFFFFFFFFh
0x1800087af  mov     [rbp+arg_10], ax
0x1800087b3  mov     rbx, rcx
0x1800087b6  mov     [rbp+NumberOfBytesRead], eax
0x1800087b9  mov     [rbp+Buffer], eax
0x1800087bc  mov     qword ptr [rbp+lDistanceToMove], 0
0x1800087c4  mov     [rbp+var_20], 0
0x1800087cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800087d2  lea     r15, WPP_GLOBAL_Control
0x1800087d9  lea     r13, WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids
0x1800087e0  lea     r14d, [rax+2]
0x1800087e4  cmp     rcx, r15
0x1800087e7  jz      short loc_180008804
0x1800087e9  test    [rcx+1Ch], r14b
0x1800087ed  jz      short loc_180008804
0x1800087ef  cmp     byte ptr [rcx+19h], 5
0x1800087f3  jb      short loc_180008804
0x1800087f5  mov     rcx, [rcx+10h]
0x1800087f9  lea     edx, [rax+39h]
0x1800087fc  mov     r8, r13
0x1800087ff  call    WPP_SF_
0x180008804  lea     rax, [rbp+arg_10]
0x180008808  mov     rcx, rbx; lpFileName
0x18000880b  lea     r9, [rbp+lDistanceToMove]
0x18000880f  mov     [rsp+50h+lpOverlapped], rax; lpBuffer
0x180008814  lea     r8, [rbp+var_20]
0x180008818  lea     rdx, [rbp+hObject]
0x18000881c  call    TiffOpenFile
0x180008821  test    eax, eax
0x180008823  jnz     short loc_180008867
0x180008825  mov     rbx, cs:WPP_GLOBAL_Control
0x18000882c  cmp     rbx, r15
0x18000882f  jz      short loc_180008860
0x180008831  test    [rbx+1Ch], r14b
0x180008835  jz      short loc_180008860
0x180008837  cmp     [rbx+19h], r14b
0x18000883b  jb      short loc_180008860
0x18000883d  mov     rbx, [rbx+10h]
0x180008841  call    cs:__imp_GetLastError
0x180008848  nop     dword ptr [rax+rax+00h]
0x18000884d  mov     edx, 3Ah ; ':'
0x180008852  mov     r8, r13
0x180008855  mov     r9d, eax
0x180008858  mov     rcx, rbx
0x18000885b  call    WPP_SF_d
0x180008860  xor     eax, eax
0x180008862  jmp     loc_18000891B
0x180008867  mov     eax, [rbp+lDistanceToMove+4]
0x18000886a  xor     edi, edi
0x18000886c  movzx   r9d, [rbp+arg_10]
0x180008871  mov     rsi, [rbp+hObject]
0x180008875  lea     ecx, [r9+r9*2]
0x180008879  lea     edx, [rax+rcx*4]; lDistanceToMove
0x18000887c  mov     ecx, [rbp+var_20]
0x18000887f  sub     rcx, 4
0x180008883  mov     eax, edx
0x180008885  cmp     rax, rcx
0x180008888  jbe     short loc_1800088B8
0x18000888a  mov     ebx, 570h
0x18000888f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008896  cmp     rcx, r15
0x180008899  jz      short loc_1800088F2
0x18000889b  test    [rcx+1Ch], r14b
0x18000889f  jz      short loc_1800088F2
0x1800088a1  cmp     [rcx+19h], r14b
0x1800088a5  jb      short loc_1800088F2
0x1800088a7  mov     rcx, [rcx+10h]
0x1800088ab  lea     edx, [rdi+3Bh]
0x1800088ae  mov     r8, r13
0x1800088b1  call    WPP_SF_
0x1800088b6  jmp     short loc_1800088F2
0x1800088b8  mov     eax, [rbp+arg_8]
0x1800088bb  xor     ebx, ebx
0x1800088bd  cmp     r9d, eax
0x1800088c0  ja      short loc_18000892B
0x1800088c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800088c9  cmp     rcx, r15
0x1800088cc  jz      short loc_1800088ED
0x1800088ce  test    [rcx+1Ch], r14b
0x1800088d2  jz      short loc_1800088ED
0x1800088d4  cmp     byte ptr [rcx+19h], 5
0x1800088d8  jb      short loc_1800088ED
0x1800088da  mov     rcx, [rcx+10h]
0x1800088de  lea     edx, [rbx+3Ch]
0x1800088e1  mov     r8, r13
0x1800088e4  mov     dword ptr [rsp+50h+lpOverlapped], eax
0x1800088e8  call    WPP_SF_dd
0x1800088ed  mov     edi, 1
0x1800088f2  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800088f6  jz      short loc_180008907
0x1800088f8  mov     rcx, rsi; hObject
0x1800088fb  call    cs:__imp_CloseHandle
0x180008902  nop     dword ptr [rax+rax+00h]
0x180008907  test    edi, edi
0x180008909  jnz     short loc_180008919
0x18000890b  mov     ecx, ebx; dwErrCode
0x18000890d  call    cs:__imp_SetLastError
0x180008914  nop     dword ptr [rax+rax+00h]
0x180008919  mov     eax, edi
0x18000891b  add     rsp, 50h
0x18000891f  pop     r15
0x180008921  pop     r14
0x180008923  pop     r13
0x180008925  pop     rdi
0x180008926  pop     rsi
0x180008927  pop     rbx
0x180008928  pop     rbp
0x180008929  retn
0x18000892b  xor     r9d, r9d; dwMoveMethod
0x18000892e  xor     r8d, r8d; lpDistanceToMoveHigh
0x180008931  mov     rcx, rsi; hFile
0x180008934  call    cs:__imp_SetFilePointer
0x18000893b  nop     dword ptr [rax+rax+00h]
0x180008940  cmp     eax, 0FFFFFFFFh
0x180008943  jnz     short loc_180008984
0x180008945  call    cs:__imp_GetLastError
0x18000894c  nop     dword ptr [rax+rax+00h]
0x180008951  mov     ebx, eax
0x180008953  mov     rcx, cs:WPP_GLOBAL_Control
0x18000895a  cmp     rcx, r15
0x18000895d  jz      short loc_1800088F2
0x18000895f  test    [rcx+1Ch], r14b
0x180008963  jz      short loc_1800088F2
0x180008965  cmp     [rcx+19h], r14b
0x180008969  jb      short loc_1800088F2
0x18000896b  mov     edx, 3Dh ; '='
0x180008970  mov     rcx, [rcx+10h]
0x180008974  mov     r9d, eax
0x180008977  mov     r8, r13
0x18000897a  call    WPP_SF_d
0x18000897f  jmp     loc_1800088F2
0x180008984  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180008988  mov     [rsp+50h+lpOverlapped], rbx; lpOverlapped
0x18000898d  mov     r8d, 4; nNumberOfBytesToRead
0x180008993  lea     rdx, [rbp+Buffer]; lpBuffer
0x180008997  mov     rcx, rsi; hFile
0x18000899a  call    cs:__imp_ReadFile
0x1800089a1  nop     dword ptr [rax+rax+00h]
0x1800089a6  test    eax, eax
0x1800089a8  jnz     short loc_1800089E3
0x1800089aa  call    cs:__imp_GetLastError
0x1800089b1  nop     dword ptr [rax+rax+00h]
0x1800089b6  mov     ebx, eax
0x1800089b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800089bf  cmp     rcx, r15
0x1800089c2  jz      loc_1800088F2
0x1800089c8  test    [rcx+1Ch], r14b
0x1800089cc  jz      loc_1800088F2
0x1800089d2  cmp     [rcx+19h], r14b
0x1800089d6  jb      loc_1800088F2
0x1800089dc  mov     edx, 3Eh ; '>'
0x1800089e1  jmp     short loc_180008970
0x1800089e3  mov     edx, [rbp+lDistanceToMove+4]; lDistanceToMove
0x1800089e6  xor     r9d, r9d; dwMoveMethod
0x1800089e9  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800089ec  mov     rcx, rsi; hFile
0x1800089ef  call    cs:__imp_SetFilePointer
0x1800089f6  nop     dword ptr [rax+rax+00h]
0x1800089fb  cmp     eax, 0FFFFFFFFh
0x1800089fe  jnz     short loc_180008A3C
0x180008a00  call    cs:__imp_GetLastError
0x180008a07  nop     dword ptr [rax+rax+00h]
0x180008a0c  mov     ebx, eax
0x180008a0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008a15  cmp     rcx, r15
0x180008a18  jz      loc_1800088F2
0x180008a1e  test    [rcx+1Ch], r14b
0x180008a22  jz      loc_1800088F2
0x180008a28  cmp     [rcx+19h], r14b
0x180008a2c  jb      loc_1800088F2
0x180008a32  mov     edx, 3Fh ; '?'
0x180008a37  jmp     loc_180008970
0x180008a3c  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesWritten
0x180008a40  mov     [rsp+50h+lpOverlapped], rbx; lpOverlapped
0x180008a45  mov     r8d, r14d; nNumberOfBytesToWrite
0x180008a48  lea     rdx, [rbp+arg_8]; lpBuffer
0x180008a4c  mov     rcx, rsi; hFile
0x180008a4f  call    cs:__imp_WriteFile
0x180008a56  nop     dword ptr [rax+rax+00h]
0x180008a5b  test    eax, eax
0x180008a5d  jnz     short loc_180008A9B
0x180008a5f  call    cs:__imp_GetLastError
0x180008a66  nop     dword ptr [rax+rax+00h]
0x180008a6b  mov     ebx, eax
0x180008a6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180008a74  cmp     rcx, r15
0x180008a77  jz      loc_1800088F2
0x180008a7d  test    [rcx+1Ch], r14b
0x180008a81  jz      loc_1800088F2
0x180008a87  cmp     [rcx+19h], r14b
0x180008a8b  jb      loc_1800088F2
0x180008a91  mov     edx, 40h ; '@'
0x180008a96  jmp     loc_180008970
0x180008a9b  mov     eax, [rbp+arg_8]
0x180008a9e  xor     r9d, r9d; dwMoveMethod
0x180008aa1  xor     r8d, r8d; lpDistanceToMoveHigh
0x180008aa4  lea     ecx, [rax+rax*2]
0x180008aa7  mov     eax, [rbp+lDistanceToMove+4]
0x180008aaa  lea     edx, [rax+rcx*4]; lDistanceToMove
0x180008aad  mov     rcx, rsi; hFile
0x180008ab0  call    cs:__imp_SetFilePointer
0x180008ab7  nop     dword ptr [rax+rax+00h]
0x180008abc  cmp     eax, 0FFFFFFFFh
0x180008abf  jnz     short loc_180008AFD
0x180008ac1  call    cs:__imp_GetLastError
0x180008ac8  nop     dword ptr [rax+rax+00h]
0x180008acd  mov     ebx, eax
0x180008acf  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ad6  cmp     rcx, r15
0x180008ad9  jz      loc_1800088F2
0x180008adf  test    [rcx+1Ch], r14b
0x180008ae3  jz      loc_1800088F2
0x180008ae9  cmp     [rcx+19h], r14b
0x180008aed  jb      loc_1800088F2
0x180008af3  mov     edx, 41h ; 'A'
0x180008af8  jmp     loc_180008970
0x180008afd  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesWritten
0x180008b01  mov     [rsp+50h+lpOverlapped], rbx; lpOverlapped
0x180008b06  mov     r8d, 4; nNumberOfBytesToWrite
0x180008b0c  lea     rdx, [rbp+Buffer]; lpBuffer
0x180008b10  mov     rcx, rsi; hFile
0x180008b13  call    cs:__imp_WriteFile
0x180008b1a  nop     dword ptr [rax+rax+00h]
0x180008b1f  test    eax, eax
0x180008b21  jnz     loc_1800088ED
0x180008b27  call    cs:__imp_GetLastError
0x180008b2e  nop     dword ptr [rax+rax+00h]
0x180008b33  mov     ebx, eax
0x180008b35  mov     rcx, cs:WPP_GLOBAL_Control
0x180008b3c  cmp     rcx, r15
0x180008b3f  jz      loc_1800088F2
0x180008b45  test    [rcx+1Ch], r14b
0x180008b49  jz      loc_1800088F2
0x180008b4f  cmp     [rcx+19h], r14b
0x180008b53  jb      loc_1800088F2
0x180008b59  mov     edx, 42h ; 'B'
0x180008b5e  jmp     loc_180008970
```
