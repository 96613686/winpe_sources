# MemoryMapTiffFile

- ea: `0x1800057a0`
- end: `0x180005aed`
- name: `MemoryMapTiffFile`
- size: `845`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, DWORD *, LPCVOID *, HANDLE *, HANDLE *, DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180005380`

## callees

- `0x1800057a0`
- `0x180009a7c`
- `0x180009aa4`
- `0x180009ae4`
- `0x180012ad4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180005826`
- `KERNEL32!GetLastError` at `0x180005875`
- `KERNEL32!GetLastError` at `0x18000592c`
- `KERNEL32!GetLastError` at `0x18000597f`
- `KERNEL32!GetLastError` at `0x180005a84`
- `KERNEL32!GetLastError` at `0x180005826`
- `KERNEL32!GetLastError` at `0x180005875`
- `KERNEL32!GetLastError` at `0x18000592c`
- `KERNEL32!GetLastError` at `0x18000597f`
- `KERNEL32!GetLastError` at `0x180005a84`
- `KERNEL32!UnmapViewOfFile` at `0x180005a5e`
- `KERNEL32!UnmapViewOfFile` at `0x180005a5e`
- `KERNEL32!SetLastError` at `0x180005ad6`
- `KERNEL32!SetLastError` at `0x180005ad6`
- `KERNEL32!MapViewOfFile` at `0x180005970`
- `KERNEL32!MapViewOfFile` at `0x180005970`
- `KERNEL32!CreateFileMappingW` at `0x18000591e`
- `KERNEL32!CreateFileMappingW` at `0x18000591e`
- `KERNEL32!GetFileSize` at `0x180005868`
- `KERNEL32!GetFileSize` at `0x180005868`
- `KERNEL32!CloseHandle` at `0x180005aa9`
- `KERNEL32!CloseHandle` at `0x180005ab8`
- `KERNEL32!CloseHandle` at `0x180005aa9`
- `KERNEL32!CloseHandle` at `0x180005ab8`

## pseudocode

```c
__int64 __fastcall MemoryMapTiffFile(LPCWSTR lpFileName, DWORD *a2, LPCVOID *a3, HANDLE *a4, HANDLE *a5, DWORD *a6)
{
  void *File; // rax
  DWORD LastError; // edi
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  DWORD FileSize; // eax
  HANDLE FileMappingW; // rax
  DWORD *v16; // rax
  __int64 v17; // r8
  DWORD v19; // ecx
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rbx
  DWORD v23; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 127, &WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids);
  }
  File = (void *)InternalSafeCreateFile(lpFileName, 0x80000000, 1u, 3u, 0);
  *a4 = File;
  if ( File == (void *)-1LL )
  {
    LastError = GetLastError();
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = 128;
LABEL_30:
      WPP_SF_d(v12[2], v13, &WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids, LastError);
      goto LABEL_31;
    }
    goto LABEL_31;
  }
  FileSize = GetFileSize(File, 0);
  *a2 = FileSize;
  if ( FileSize == -1 )
  {
    LastError = GetLastError();
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = 129;
      goto LABEL_30;
    }
LABEL_31:
    if ( !LastError )
      return 1;
    goto LABEL_45;
  }
  if ( FileSize < 8 )
  {
    LastError = 11;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 130, &WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids);
    }
    goto LABEL_45;
  }
  FileMappingW = CreateFileMappingW(*a4, 0, 0x8000002u, 0, 0, 0);
  *a5 = FileMappingW;
  if ( !FileMappingW )
  {
    LastError = GetLastError();
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = 131;
      goto LABEL_30;
    }
    goto LABEL_31;
  }
  v16 = (DWORD *)MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
  *a3 = v16;
  if ( !v16 )
  {
    LastError = GetLastError();
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = 132;
      goto LABEL_30;
    }
    goto LABEL_31;
  }
  if ( *(_WORD *)v16 != 18761 || *((_WORD *)v16 + 1) != 42 )
  {
    LastError = 11;
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_45;
    }
    v21 = 133;
    goto LABEL_44;
  }
  v19 = v16[1];
  *a6 = v19;
  if ( v19 <= *a2 )
    return 1;
  LastError = 11;
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v21 = 134;
LABEL_44:
    WPP_SF_S(v20[2], v21, v17, lpFileName);
  }
LABEL_45:
  if ( *a3
    && !UnmapViewOfFile(*a3)
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v22 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v23 = GetLastError();
    WPP_SF_d(v22, 135, &WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids, v23);
  }
  if ( *a5 )
    CloseHandle(*a5);
  if ( *a4 != (HANDLE)-1LL )
    CloseHandle(*a4);
  *a3 = 0;
  *a5 = 0;
  *a4 = (HANDLE)-1LL;
  SetLastError(LastError);
  return 0;
}

```

## disassembly

```asm
0x1800057a0  push    rbx
0x1800057a2  push    rbp
0x1800057a3  push    rsi
0x1800057a4  push    rdi
0x1800057a5  push    r12
0x1800057a7  push    r14
0x1800057a9  push    r15
0x1800057ab  sub     rsp, 40h
0x1800057af  mov     r14, r9
0x1800057b2  mov     rbp, r8
0x1800057b5  mov     rbx, rdx
0x1800057b8  mov     rsi, rcx
0x1800057bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800057c2  lea     rax, WPP_GLOBAL_Control
0x1800057c9  mov     r12b, 2
0x1800057cc  cmp     rcx, rax
0x1800057cf  jz      short loc_1800057F2
0x1800057d1  test    [rcx+1Ch], r12b
0x1800057d5  jz      short loc_1800057F2
0x1800057d7  cmp     byte ptr [rcx+19h], 5
0x1800057db  jb      short loc_1800057F2
0x1800057dd  mov     rcx, [rcx+10h]
0x1800057e1  lea     r8, WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids
0x1800057e8  mov     edx, 7Fh
0x1800057ed  call    WPP_SF_
0x1800057f2  mov     dword ptr [rsp+78h+lpName], 0; int
0x1800057fa  mov     edx, 80000000h; dwDesiredAccess
0x1800057ff  mov     r8d, 1; dwShareMode
0x180005805  mov     [rsp+78h+dwMaximumSizeLow], 3; DWORD
0x18000580d  mov     rcx, rsi; lpFileName
0x180005810  call    InternalSafeCreateFile
0x180005815  mov     r15, [rsp+78h+arg_20]
0x18000581d  mov     [r14], rax
0x180005820  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180005824  jnz     short loc_180005863
0x180005826  call    cs:__imp_GetLastError
0x18000582c  mov     edi, eax
0x18000582e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005835  lea     rax, WPP_GLOBAL_Control
0x18000583c  cmp     rcx, rax
0x18000583f  jz      loc_1800059BE
0x180005845  test    [rcx+1Ch], r12b
0x180005849  jz      loc_1800059BE
0x18000584f  cmp     [rcx+19h], r12b
0x180005853  jb      loc_1800059BE
0x180005859  mov     edx, 80h
0x18000585e  jmp     loc_1800059AB
0x180005863  xor     edx, edx; lpFileSizeHigh
0x180005865  mov     rcx, rax; hFile
0x180005868  call    cs:__imp_GetFileSize
0x18000586e  mov     [rbx], eax
0x180005870  cmp     eax, 0FFFFFFFFh
0x180005873  jnz     short loc_1800058B2
0x180005875  call    cs:__imp_GetLastError
0x18000587b  mov     edi, eax
0x18000587d  mov     rcx, cs:WPP_GLOBAL_Control
0x180005884  lea     rax, WPP_GLOBAL_Control
0x18000588b  cmp     rcx, rax
0x18000588e  jz      loc_1800059BE
0x180005894  test    [rcx+1Ch], r12b
0x180005898  jz      loc_1800059BE
0x18000589e  cmp     [rcx+19h], r12b
0x1800058a2  jb      loc_1800059BE
0x1800058a8  mov     edx, 81h
0x1800058ad  jmp     loc_1800059AB
0x1800058b2  cmp     eax, 8
0x1800058b5  jnb     short loc_1800058FF
0x1800058b7  mov     edi, 0Bh
0x1800058bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800058c3  lea     rsi, WPP_GLOBAL_Control
0x1800058ca  cmp     rcx, rsi
0x1800058cd  jz      loc_180005A55
0x1800058d3  test    [rcx+1Ch], r12b
0x1800058d7  jz      loc_180005A55
0x1800058dd  cmp     [rcx+19h], r12b
0x1800058e1  jb      loc_180005A55
0x1800058e7  mov     rcx, [rcx+10h]
0x1800058eb  lea     edx, [rdi+77h]
0x1800058ee  lea     r8, WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids
0x1800058f5  call    WPP_SF_
0x1800058fa  jmp     loc_180005A55
0x1800058ff  mov     rcx, [r14]; hFile
0x180005902  xor     r9d, r9d; dwMaximumSizeHigh
0x180005905  mov     [rsp+78h+lpName], 0; lpName
0x18000590e  xor     edx, edx; lpFileMappingAttributes
0x180005910  mov     r8d, 8000002h; flProtect
0x180005916  mov     [rsp+78h+dwMaximumSizeLow], 0; dwMaximumSizeLow
0x18000591e  call    cs:__imp_CreateFileMappingW
0x180005924  mov     [r15], rax
0x180005927  test    rax, rax
0x18000592a  jnz     short loc_18000595A
0x18000592c  call    cs:__imp_GetLastError
0x180005932  mov     edi, eax
0x180005934  mov     rcx, cs:WPP_GLOBAL_Control
0x18000593b  lea     rax, WPP_GLOBAL_Control
0x180005942  cmp     rcx, rax
0x180005945  jz      short loc_1800059BE
0x180005947  test    [rcx+1Ch], r12b
0x18000594b  jz      short loc_1800059BE
0x18000594d  cmp     [rcx+19h], r12b
0x180005951  jb      short loc_1800059BE
0x180005953  mov     edx, 83h
0x180005958  jmp     short loc_1800059AB
0x18000595a  xor     r9d, r9d; dwFileOffsetLow
0x18000595d  mov     qword ptr [rsp+78h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x180005966  xor     r8d, r8d; dwFileOffsetHigh
0x180005969  mov     rcx, rax; hFileMappingObject
0x18000596c  lea     edx, [r9+4]; dwDesiredAccess
0x180005970  call    cs:__imp_MapViewOfFile
0x180005976  mov     [rbp+0], rax
0x18000597a  test    rax, rax
0x18000597d  jnz     short loc_1800059D0
0x18000597f  call    cs:__imp_GetLastError
0x180005985  mov     edi, eax
0x180005987  mov     rcx, cs:WPP_GLOBAL_Control
0x18000598e  lea     rax, WPP_GLOBAL_Control
0x180005995  cmp     rcx, rax
0x180005998  jz      short loc_1800059BE
0x18000599a  test    [rcx+1Ch], r12b
0x18000599e  jz      short loc_1800059BE
0x1800059a0  cmp     [rcx+19h], r12b
0x1800059a4  jb      short loc_1800059BE
0x1800059a6  mov     edx, 84h
0x1800059ab  mov     rcx, [rcx+10h]
0x1800059af  lea     r8, WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids
0x1800059b6  mov     r9d, edi
0x1800059b9  call    WPP_SF_d
0x1800059be  test    edi, edi
0x1800059c0  jnz     loc_180005A4E
0x1800059c6  mov     eax, 1
0x1800059cb  jmp     loc_180005ADE
0x1800059d0  mov     ecx, 4949h
0x1800059d5  cmp     [rax], cx
0x1800059d8  jnz     short loc_180005A1B
0x1800059da  cmp     word ptr [rax+2], 2Ah ; '*'
0x1800059df  jnz     short loc_180005A1B
0x1800059e1  mov     ecx, [rax+4]
0x1800059e4  mov     rax, [rsp+78h+arg_28]
0x1800059ec  mov     [rax], ecx
0x1800059ee  cmp     ecx, [rbx]
0x1800059f0  jbe     short loc_1800059C6
0x1800059f2  mov     edi, 0Bh
0x1800059f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800059fe  lea     rax, WPP_GLOBAL_Control
0x180005a05  cmp     rcx, rax
0x180005a08  jz      short loc_180005A4E
0x180005a0a  test    [rcx+1Ch], r12b
0x180005a0e  jz      short loc_180005A4E
0x180005a10  cmp     [rcx+19h], r12b
0x180005a14  jb      short loc_180005A4E
0x180005a16  lea     edx, [rdi+7Bh]
0x180005a19  jmp     short loc_180005A42
0x180005a1b  mov     edi, 0Bh
0x180005a20  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a27  lea     rax, WPP_GLOBAL_Control
0x180005a2e  cmp     rcx, rax
0x180005a31  jz      short loc_180005A4E
0x180005a33  test    [rcx+1Ch], r12b
0x180005a37  jz      short loc_180005A4E
0x180005a39  cmp     [rcx+19h], r12b
0x180005a3d  jb      short loc_180005A4E
0x180005a3f  lea     edx, [rdi+7Ah]
0x180005a42  mov     rcx, [rcx+10h]
0x180005a46  mov     r9, rsi
0x180005a49  call    WPP_SF_S
0x180005a4e  lea     rsi, WPP_GLOBAL_Control
0x180005a55  mov     rcx, [rbp+0]; lpBaseAddress
0x180005a59  test    rcx, rcx
0x180005a5c  jz      short loc_180005AA1
0x180005a5e  call    cs:__imp_UnmapViewOfFile
0x180005a64  test    eax, eax
0x180005a66  jnz     short loc_180005AA1
0x180005a68  mov     rbx, cs:WPP_GLOBAL_Control
0x180005a6f  cmp     rbx, rsi
0x180005a72  jz      short loc_180005AA1
0x180005a74  test    [rbx+1Ch], r12b
0x180005a78  jz      short loc_180005AA1
0x180005a7a  cmp     [rbx+19h], r12b
0x180005a7e  jb      short loc_180005AA1
0x180005a80  mov     rbx, [rbx+10h]
0x180005a84  call    cs:__imp_GetLastError
0x180005a8a  mov     edx, 87h
0x180005a8f  lea     r8, WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids
0x180005a96  mov     r9d, eax
0x180005a99  mov     rcx, rbx
0x180005a9c  call    WPP_SF_d
0x180005aa1  mov     rcx, [r15]; hObject
0x180005aa4  test    rcx, rcx
0x180005aa7  jz      short loc_180005AAF
0x180005aa9  call    cs:__imp_CloseHandle
0x180005aaf  cmp     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x180005ab3  jz      short loc_180005ABE
0x180005ab5  mov     rcx, [r14]; hObject
0x180005ab8  call    cs:__imp_CloseHandle
0x180005abe  mov     qword ptr [rbp+0], 0
0x180005ac6  mov     ecx, edi; dwErrCode
0x180005ac8  mov     qword ptr [r15], 0
0x180005acf  mov     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x180005ad6  call    cs:__imp_SetLastError
0x180005adc  xor     eax, eax
0x180005ade  add     rsp, 40h
0x180005ae2  pop     r15
0x180005ae4  pop     r14
0x180005ae6  pop     r12
0x180005ae8  pop     rdi
0x180005ae9  pop     rsi
0x180005aea  pop     rbp
0x180005aeb  pop     rbx
0x180005aec  retn
```
