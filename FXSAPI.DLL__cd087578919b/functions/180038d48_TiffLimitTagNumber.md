# TiffLimitTagNumber

- ea: `0x180038d48`
- end: `0x180039122`
- name: `TiffLimitTagNumber`
- size: `986`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18001e5e0`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x180014314`
- `0x180038d48`
- `0x1800395f8`

## import_xrefs

- `KERNEL32!ReadFile` at `0x180038f59`
- `KERNEL32!ReadFile` at `0x180038f59`
- `KERNEL32!WriteFile` at `0x18003900e`
- `KERNEL32!WriteFile` at `0x1800390d2`
- `KERNEL32!WriteFile` at `0x18003900e`
- `KERNEL32!WriteFile` at `0x1800390d2`
- `KERNEL32!SetFilePointer` at `0x180038ef3`
- `KERNEL32!SetFilePointer` at `0x180038fae`
- `KERNEL32!SetFilePointer` at `0x18003906f`
- `KERNEL32!SetFilePointer` at `0x180038ef3`
- `KERNEL32!SetFilePointer` at `0x180038fae`
- `KERNEL32!SetFilePointer` at `0x18003906f`
- `KERNEL32!CloseHandle` at `0x180038eba`
- `KERNEL32!CloseHandle` at `0x180038eba`
- `KERNEL32!SetLastError` at `0x180038ecc`
- `KERNEL32!SetLastError` at `0x180038ecc`
- `KERNEL32!GetLastError` at `0x180038e00`
- `KERNEL32!GetLastError` at `0x180038f04`
- `KERNEL32!GetLastError` at `0x180038f69`
- `KERNEL32!GetLastError` at `0x180038fbf`
- `KERNEL32!GetLastError` at `0x18003901e`
- `KERNEL32!GetLastError` at `0x180039080`
- `KERNEL32!GetLastError` at `0x1800390e6`
- `KERNEL32!GetLastError` at `0x180038e00`
- `KERNEL32!GetLastError` at `0x180038f04`
- `KERNEL32!GetLastError` at `0x180038f69`
- `KERNEL32!GetLastError` at `0x180038fbf`
- `KERNEL32!GetLastError` at `0x18003901e`
- `KERNEL32!GetLastError` at `0x180039080`
- `KERNEL32!GetLastError` at `0x1800390e6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TiffLimitTagNumber(LPCWSTR lpFileName, int a2)
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
  int Buffer; // [rsp+38h] [rbp-18h] BYREF
  LONG lDistanceToMove[2]; // [rsp+40h] [rbp-10h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-8h] BYREF
  unsigned __int16 v16; // [rsp+98h] [rbp+48h] BYREF
  __int16 v17; // [rsp+9Ah] [rbp+4Ah]
  DWORD NumberOfBytesRead; // [rsp+A0h] [rbp+50h] BYREF
  unsigned int v19; // [rsp+A8h] [rbp+58h] BYREF

  v17 = HIWORD(a2);
  v12 = 54;
  v16 = 0;
  NumberOfBytesRead = 0;
  Buffer = 0;
  hObject = (HANDLE)-1LL;
  *(_QWORD *)lDistanceToMove = 0;
  v19 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids);
  }
  if ( !(unsigned int)TiffOpenFile(lpFileName, &hObject, &v19, lDistanceToMove, &v16) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v3 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      LastError = GetLastError();
      WPP_SF_d(v3, 58, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids, LastError);
    }
    return 0;
  }
  v6 = 0;
  v7 = hObject;
  if ( lDistanceToMove[1] + 12 * (unsigned int)v16 > (unsigned __int64)v19 - 4 )
  {
    v8 = 1392;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids);
    }
    goto LABEL_22;
  }
  v8 = 0;
  if ( v16 <= v12 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids);
    }
    goto LABEL_21;
  }
  if ( SetFilePointer(hObject, lDistanceToMove[1] + 12 * v16, 0, 0) == -1 )
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
  if ( !WriteFile(v7, &v12, 2u, &NumberOfBytesRead, 0) )
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
  if ( SetFilePointer(v7, lDistanceToMove[1] + 12 * v12, 0, 0) == -1 )
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
    WPP_SF_d(v10[2], v11, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids, v9);
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
0x180038d48  mov     [rsp-38h+arg_8], edx
0x180038d4c  push    rbp
0x180038d4d  push    rbx
0x180038d4e  push    rsi
0x180038d4f  push    rdi
0x180038d50  push    r13
0x180038d52  push    r14
0x180038d54  push    r15
0x180038d56  mov     rbp, rsp
0x180038d59  sub     rsp, 50h
0x180038d5d  xor     eax, eax
0x180038d5f  mov     [rbp+var_20], 36h ; '6'
0x180038d66  mov     word ptr [rbp+arg_8], ax
0x180038d6a  mov     rbx, rcx
0x180038d6d  mov     [rbp+NumberOfBytesRead], eax
0x180038d70  mov     [rbp+Buffer], eax
0x180038d73  mov     [rbp+hObject], 0FFFFFFFFFFFFFFFFh
0x180038d7b  mov     qword ptr [rbp+lDistanceToMove], 0
0x180038d83  mov     [rbp+arg_18], 0
0x180038d8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180038d91  lea     r15, WPP_GLOBAL_Control
0x180038d98  lea     r13, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids
0x180038d9f  lea     r14d, [rax+2]
0x180038da3  cmp     rcx, r15
0x180038da6  jz      short loc_180038DC3
0x180038da8  test    [rcx+1Ch], r14b
0x180038dac  jz      short loc_180038DC3
0x180038dae  cmp     byte ptr [rcx+19h], 5
0x180038db2  jb      short loc_180038DC3
0x180038db4  mov     rcx, [rcx+10h]
0x180038db8  lea     edx, [rax+39h]
0x180038dbb  mov     r8, r13
0x180038dbe  call    WPP_SF_
0x180038dc3  lea     rax, [rbp+arg_8]
0x180038dc7  mov     rcx, rbx; lpFileName
0x180038dca  lea     r9, [rbp+lDistanceToMove]
0x180038dce  mov     [rsp+50h+lpOverlapped], rax; lpBuffer
0x180038dd3  lea     r8, [rbp+arg_18]
0x180038dd7  lea     rdx, [rbp+hObject]
0x180038ddb  call    TiffOpenFile
0x180038de0  test    eax, eax
0x180038de2  jnz     short loc_180038E26
0x180038de4  mov     rbx, cs:WPP_GLOBAL_Control
0x180038deb  cmp     rbx, r15
0x180038dee  jz      short loc_180038E1F
0x180038df0  test    [rbx+1Ch], r14b
0x180038df4  jz      short loc_180038E1F
0x180038df6  cmp     [rbx+19h], r14b
0x180038dfa  jb      short loc_180038E1F
0x180038dfc  mov     rbx, [rbx+10h]
0x180038e00  call    cs:__imp_GetLastError
0x180038e07  nop     dword ptr [rax+rax+00h]
0x180038e0c  mov     edx, 3Ah ; ':'
0x180038e11  mov     r8, r13
0x180038e14  mov     r9d, eax
0x180038e17  mov     rcx, rbx
0x180038e1a  call    WPP_SF_d
0x180038e1f  xor     eax, eax
0x180038e21  jmp     loc_180038EDA
0x180038e26  mov     eax, [rbp+lDistanceToMove+4]
0x180038e29  xor     edi, edi
0x180038e2b  movzx   r9d, word ptr [rbp+arg_8]
0x180038e30  mov     rsi, [rbp+hObject]
0x180038e34  lea     ecx, [r9+r9*2]
0x180038e38  lea     edx, [rax+rcx*4]; lDistanceToMove
0x180038e3b  mov     ecx, [rbp+arg_18]
0x180038e3e  sub     rcx, 4
0x180038e42  mov     eax, edx
0x180038e44  cmp     rax, rcx
0x180038e47  jbe     short loc_180038E77
0x180038e49  mov     ebx, 570h
0x180038e4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180038e55  cmp     rcx, r15
0x180038e58  jz      short loc_180038EB1
0x180038e5a  test    [rcx+1Ch], r14b
0x180038e5e  jz      short loc_180038EB1
0x180038e60  cmp     [rcx+19h], r14b
0x180038e64  jb      short loc_180038EB1
0x180038e66  mov     rcx, [rcx+10h]
0x180038e6a  lea     edx, [rdi+3Bh]
0x180038e6d  mov     r8, r13
0x180038e70  call    WPP_SF_
0x180038e75  jmp     short loc_180038EB1
0x180038e77  mov     eax, [rbp+var_20]
0x180038e7a  xor     ebx, ebx
0x180038e7c  cmp     r9d, eax
0x180038e7f  ja      short loc_180038EEA
0x180038e81  mov     rcx, cs:WPP_GLOBAL_Control
0x180038e88  cmp     rcx, r15
0x180038e8b  jz      short loc_180038EAC
0x180038e8d  test    [rcx+1Ch], r14b
0x180038e91  jz      short loc_180038EAC
0x180038e93  cmp     byte ptr [rcx+19h], 5
0x180038e97  jb      short loc_180038EAC
0x180038e99  mov     rcx, [rcx+10h]
0x180038e9d  lea     edx, [rbx+3Ch]
0x180038ea0  mov     r8, r13
0x180038ea3  mov     dword ptr [rsp+50h+lpOverlapped], eax
0x180038ea7  call    WPP_SF_dd
0x180038eac  mov     edi, 1
0x180038eb1  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180038eb5  jz      short loc_180038EC6
0x180038eb7  mov     rcx, rsi; hObject
0x180038eba  call    cs:__imp_CloseHandle
0x180038ec1  nop     dword ptr [rax+rax+00h]
0x180038ec6  test    edi, edi
0x180038ec8  jnz     short loc_180038ED8
0x180038eca  mov     ecx, ebx; dwErrCode
0x180038ecc  call    cs:__imp_SetLastError
0x180038ed3  nop     dword ptr [rax+rax+00h]
0x180038ed8  mov     eax, edi
0x180038eda  add     rsp, 50h
0x180038ede  pop     r15
0x180038ee0  pop     r14
0x180038ee2  pop     r13
0x180038ee4  pop     rdi
0x180038ee5  pop     rsi
0x180038ee6  pop     rbx
0x180038ee7  pop     rbp
0x180038ee8  retn
0x180038eea  xor     r9d, r9d; dwMoveMethod
0x180038eed  xor     r8d, r8d; lpDistanceToMoveHigh
0x180038ef0  mov     rcx, rsi; hFile
0x180038ef3  call    cs:__imp_SetFilePointer
0x180038efa  nop     dword ptr [rax+rax+00h]
0x180038eff  cmp     eax, 0FFFFFFFFh
0x180038f02  jnz     short loc_180038F43
0x180038f04  call    cs:__imp_GetLastError
0x180038f0b  nop     dword ptr [rax+rax+00h]
0x180038f10  mov     ebx, eax
0x180038f12  mov     rcx, cs:WPP_GLOBAL_Control
0x180038f19  cmp     rcx, r15
0x180038f1c  jz      short loc_180038EB1
0x180038f1e  test    [rcx+1Ch], r14b
0x180038f22  jz      short loc_180038EB1
0x180038f24  cmp     [rcx+19h], r14b
0x180038f28  jb      short loc_180038EB1
0x180038f2a  mov     edx, 3Dh ; '='
0x180038f2f  mov     rcx, [rcx+10h]
0x180038f33  mov     r9d, eax
0x180038f36  mov     r8, r13
0x180038f39  call    WPP_SF_d
0x180038f3e  jmp     loc_180038EB1
0x180038f43  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180038f47  mov     [rsp+50h+lpOverlapped], rbx; lpOverlapped
0x180038f4c  mov     r8d, 4; nNumberOfBytesToRead
0x180038f52  lea     rdx, [rbp+Buffer]; lpBuffer
0x180038f56  mov     rcx, rsi; hFile
0x180038f59  call    cs:__imp_ReadFile
0x180038f60  nop     dword ptr [rax+rax+00h]
0x180038f65  test    eax, eax
0x180038f67  jnz     short loc_180038FA2
0x180038f69  call    cs:__imp_GetLastError
0x180038f70  nop     dword ptr [rax+rax+00h]
0x180038f75  mov     ebx, eax
0x180038f77  mov     rcx, cs:WPP_GLOBAL_Control
0x180038f7e  cmp     rcx, r15
0x180038f81  jz      loc_180038EB1
0x180038f87  test    [rcx+1Ch], r14b
0x180038f8b  jz      loc_180038EB1
0x180038f91  cmp     [rcx+19h], r14b
0x180038f95  jb      loc_180038EB1
0x180038f9b  mov     edx, 3Eh ; '>'
0x180038fa0  jmp     short loc_180038F2F
0x180038fa2  mov     edx, [rbp+lDistanceToMove+4]; lDistanceToMove
0x180038fa5  xor     r9d, r9d; dwMoveMethod
0x180038fa8  xor     r8d, r8d; lpDistanceToMoveHigh
0x180038fab  mov     rcx, rsi; hFile
0x180038fae  call    cs:__imp_SetFilePointer
0x180038fb5  nop     dword ptr [rax+rax+00h]
0x180038fba  cmp     eax, 0FFFFFFFFh
0x180038fbd  jnz     short loc_180038FFB
0x180038fbf  call    cs:__imp_GetLastError
0x180038fc6  nop     dword ptr [rax+rax+00h]
0x180038fcb  mov     ebx, eax
0x180038fcd  mov     rcx, cs:WPP_GLOBAL_Control
0x180038fd4  cmp     rcx, r15
0x180038fd7  jz      loc_180038EB1
0x180038fdd  test    [rcx+1Ch], r14b
0x180038fe1  jz      loc_180038EB1
0x180038fe7  cmp     [rcx+19h], r14b
0x180038feb  jb      loc_180038EB1
0x180038ff1  mov     edx, 3Fh ; '?'
0x180038ff6  jmp     loc_180038F2F
0x180038ffb  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesWritten
0x180038fff  mov     [rsp+50h+lpOverlapped], rbx; lpOverlapped
0x180039004  mov     r8d, r14d; nNumberOfBytesToWrite
0x180039007  lea     rdx, [rbp+var_20]; lpBuffer
0x18003900b  mov     rcx, rsi; hFile
0x18003900e  call    cs:__imp_WriteFile
0x180039015  nop     dword ptr [rax+rax+00h]
0x18003901a  test    eax, eax
0x18003901c  jnz     short loc_18003905A
0x18003901e  call    cs:__imp_GetLastError
0x180039025  nop     dword ptr [rax+rax+00h]
0x18003902a  mov     ebx, eax
0x18003902c  mov     rcx, cs:WPP_GLOBAL_Control
0x180039033  cmp     rcx, r15
0x180039036  jz      loc_180038EB1
0x18003903c  test    [rcx+1Ch], r14b
0x180039040  jz      loc_180038EB1
0x180039046  cmp     [rcx+19h], r14b
0x18003904a  jb      loc_180038EB1
0x180039050  mov     edx, 40h ; '@'
0x180039055  jmp     loc_180038F2F
0x18003905a  mov     eax, [rbp+var_20]
0x18003905d  xor     r9d, r9d; dwMoveMethod
0x180039060  xor     r8d, r8d; lpDistanceToMoveHigh
0x180039063  lea     ecx, [rax+rax*2]
0x180039066  mov     eax, [rbp+lDistanceToMove+4]
0x180039069  lea     edx, [rax+rcx*4]; lDistanceToMove
0x18003906c  mov     rcx, rsi; hFile
0x18003906f  call    cs:__imp_SetFilePointer
0x180039076  nop     dword ptr [rax+rax+00h]
0x18003907b  cmp     eax, 0FFFFFFFFh
0x18003907e  jnz     short loc_1800390BC
0x180039080  call    cs:__imp_GetLastError
0x180039087  nop     dword ptr [rax+rax+00h]
0x18003908c  mov     ebx, eax
0x18003908e  mov     rcx, cs:WPP_GLOBAL_Control
0x180039095  cmp     rcx, r15
0x180039098  jz      loc_180038EB1
0x18003909e  test    [rcx+1Ch], r14b
0x1800390a2  jz      loc_180038EB1
0x1800390a8  cmp     [rcx+19h], r14b
0x1800390ac  jb      loc_180038EB1
0x1800390b2  mov     edx, 41h ; 'A'
0x1800390b7  jmp     loc_180038F2F
0x1800390bc  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesWritten
0x1800390c0  mov     [rsp+50h+lpOverlapped], rbx; lpOverlapped
0x1800390c5  mov     r8d, 4; nNumberOfBytesToWrite
0x1800390cb  lea     rdx, [rbp+Buffer]; lpBuffer
0x1800390cf  mov     rcx, rsi; hFile
0x1800390d2  call    cs:__imp_WriteFile
0x1800390d9  nop     dword ptr [rax+rax+00h]
0x1800390de  test    eax, eax
0x1800390e0  jnz     loc_180038EAC
0x1800390e6  call    cs:__imp_GetLastError
0x1800390ed  nop     dword ptr [rax+rax+00h]
0x1800390f2  mov     ebx, eax
0x1800390f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800390fb  cmp     rcx, r15
0x1800390fe  jz      loc_180038EB1
0x180039104  test    [rcx+1Ch], r14b
0x180039108  jz      loc_180038EB1
0x18003910e  cmp     [rcx+19h], r14b
0x180039112  jb      loc_180038EB1
0x180039118  mov     edx, 42h ; 'B'
0x18003911d  jmp     loc_180038F2F
```
