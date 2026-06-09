# MemoryMapTiffFile

- ea: `0x180005890`
- end: `0x180005c2a`
- name: `MemoryMapTiffFile`
- size: `922`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, DWORD *, LPCVOID *, HANDLE *, HANDLE *, DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180005450`

## callees

- `0x180005890`
- `0x180009f04`
- `0x180009f34`
- `0x180009f78`
- `0x1800131b4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180005916`
- `KERNEL32!GetLastError` at `0x180005971`
- `KERNEL32!GetLastError` at `0x180005a34`
- `KERNEL32!GetLastError` at `0x180005a97`
- `KERNEL32!GetLastError` at `0x180005ba8`
- `KERNEL32!GetLastError` at `0x180005916`
- `KERNEL32!GetLastError` at `0x180005971`
- `KERNEL32!GetLastError` at `0x180005a34`
- `KERNEL32!GetLastError` at `0x180005a97`
- `KERNEL32!GetLastError` at `0x180005ba8`
- `KERNEL32!UnmapViewOfFile` at `0x180005b7c`
- `KERNEL32!UnmapViewOfFile` at `0x180005b7c`
- `KERNEL32!SetLastError` at `0x180005c0c`
- `KERNEL32!SetLastError` at `0x180005c0c`
- `KERNEL32!MapViewOfFile` at `0x180005a82`
- `KERNEL32!MapViewOfFile` at `0x180005a82`
- `KERNEL32!CreateFileMappingW` at `0x180005a20`
- `KERNEL32!CreateFileMappingW` at `0x180005a20`
- `KERNEL32!GetFileSize` at `0x18000595e`
- `KERNEL32!GetFileSize` at `0x18000595e`
- `KERNEL32!CloseHandle` at `0x180005bd3`
- `KERNEL32!CloseHandle` at `0x180005be8`
- `KERNEL32!CloseHandle` at `0x180005bd3`
- `KERNEL32!CloseHandle` at `0x180005be8`

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
0x180005890  push    rbx
0x180005892  push    rbp
0x180005893  push    rsi
0x180005894  push    rdi
0x180005895  push    r12
0x180005897  push    r14
0x180005899  push    r15
0x18000589b  sub     rsp, 40h
0x18000589f  mov     r14, r9
0x1800058a2  mov     rbp, r8
0x1800058a5  mov     rbx, rdx
0x1800058a8  mov     rsi, rcx
0x1800058ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800058b2  lea     rax, WPP_GLOBAL_Control
0x1800058b9  mov     r12b, 2
0x1800058bc  cmp     rcx, rax
0x1800058bf  jz      short loc_1800058E2
0x1800058c1  test    [rcx+1Ch], r12b
0x1800058c5  jz      short loc_1800058E2
0x1800058c7  cmp     byte ptr [rcx+19h], 5
0x1800058cb  jb      short loc_1800058E2
0x1800058cd  mov     rcx, [rcx+10h]
0x1800058d1  lea     r8, WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids
0x1800058d8  mov     edx, 7Fh
0x1800058dd  call    WPP_SF_
0x1800058e2  mov     dword ptr [rsp+78h+lpName], 0; int
0x1800058ea  mov     edx, 80000000h; dwDesiredAccess
0x1800058ef  mov     r8d, 1; dwShareMode
0x1800058f5  mov     [rsp+78h+dwMaximumSizeLow], 3; DWORD
0x1800058fd  mov     rcx, rsi; lpFileName
0x180005900  call    InternalSafeCreateFile
0x180005905  mov     r15, [rsp+78h+arg_20]
0x18000590d  mov     [r14], rax
0x180005910  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180005914  jnz     short loc_180005959
0x180005916  call    cs:__imp_GetLastError
0x18000591d  nop     dword ptr [rax+rax+00h]
0x180005922  mov     edi, eax
0x180005924  mov     rcx, cs:WPP_GLOBAL_Control
0x18000592b  lea     rax, WPP_GLOBAL_Control
0x180005932  cmp     rcx, rax
0x180005935  jz      loc_180005ADC
0x18000593b  test    [rcx+1Ch], r12b
0x18000593f  jz      loc_180005ADC
0x180005945  cmp     [rcx+19h], r12b
0x180005949  jb      loc_180005ADC
0x18000594f  mov     edx, 80h
0x180005954  jmp     loc_180005AC9
0x180005959  xor     edx, edx; lpFileSizeHigh
0x18000595b  mov     rcx, rax; hFile
0x18000595e  call    cs:__imp_GetFileSize
0x180005965  nop     dword ptr [rax+rax+00h]
0x18000596a  mov     [rbx], eax
0x18000596c  cmp     eax, 0FFFFFFFFh
0x18000596f  jnz     short loc_1800059B4
0x180005971  call    cs:__imp_GetLastError
0x180005978  nop     dword ptr [rax+rax+00h]
0x18000597d  mov     edi, eax
0x18000597f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005986  lea     rax, WPP_GLOBAL_Control
0x18000598d  cmp     rcx, rax
0x180005990  jz      loc_180005ADC
0x180005996  test    [rcx+1Ch], r12b
0x18000599a  jz      loc_180005ADC
0x1800059a0  cmp     [rcx+19h], r12b
0x1800059a4  jb      loc_180005ADC
0x1800059aa  mov     edx, 81h
0x1800059af  jmp     loc_180005AC9
0x1800059b4  cmp     eax, 8
0x1800059b7  jnb     short loc_180005A01
0x1800059b9  mov     edi, 0Bh
0x1800059be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800059c5  lea     rsi, WPP_GLOBAL_Control
0x1800059cc  cmp     rcx, rsi
0x1800059cf  jz      loc_180005B73
0x1800059d5  test    [rcx+1Ch], r12b
0x1800059d9  jz      loc_180005B73
0x1800059df  cmp     [rcx+19h], r12b
0x1800059e3  jb      loc_180005B73
0x1800059e9  mov     rcx, [rcx+10h]
0x1800059ed  lea     edx, [rdi+77h]
0x1800059f0  lea     r8, WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids
0x1800059f7  call    WPP_SF_
0x1800059fc  jmp     loc_180005B73
0x180005a01  mov     rcx, [r14]; hFile
0x180005a04  xor     r9d, r9d; dwMaximumSizeHigh
0x180005a07  mov     [rsp+78h+lpName], 0; lpName
0x180005a10  xor     edx, edx; lpFileMappingAttributes
0x180005a12  mov     r8d, 8000002h; flProtect
0x180005a18  mov     [rsp+78h+dwMaximumSizeLow], 0; dwMaximumSizeLow
0x180005a20  call    cs:__imp_CreateFileMappingW
0x180005a27  nop     dword ptr [rax+rax+00h]
0x180005a2c  mov     [r15], rax
0x180005a2f  test    rax, rax
0x180005a32  jnz     short loc_180005A6C
0x180005a34  call    cs:__imp_GetLastError
0x180005a3b  nop     dword ptr [rax+rax+00h]
0x180005a40  mov     edi, eax
0x180005a42  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a49  lea     rax, WPP_GLOBAL_Control
0x180005a50  cmp     rcx, rax
0x180005a53  jz      loc_180005ADC
0x180005a59  test    [rcx+1Ch], r12b
0x180005a5d  jz      short loc_180005ADC
0x180005a5f  cmp     [rcx+19h], r12b
0x180005a63  jb      short loc_180005ADC
0x180005a65  mov     edx, 83h
0x180005a6a  jmp     short loc_180005AC9
0x180005a6c  xor     r9d, r9d; dwFileOffsetLow
0x180005a6f  mov     qword ptr [rsp+78h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x180005a78  xor     r8d, r8d; dwFileOffsetHigh
0x180005a7b  mov     rcx, rax; hFileMappingObject
0x180005a7e  lea     edx, [r9+4]; dwDesiredAccess
0x180005a82  call    cs:__imp_MapViewOfFile
0x180005a89  nop     dword ptr [rax+rax+00h]
0x180005a8e  mov     [rbp+0], rax
0x180005a92  test    rax, rax
0x180005a95  jnz     short loc_180005AEE
0x180005a97  call    cs:__imp_GetLastError
0x180005a9e  nop     dword ptr [rax+rax+00h]
0x180005aa3  mov     edi, eax
0x180005aa5  mov     rcx, cs:WPP_GLOBAL_Control
0x180005aac  lea     rax, WPP_GLOBAL_Control
0x180005ab3  cmp     rcx, rax
0x180005ab6  jz      short loc_180005ADC
0x180005ab8  test    [rcx+1Ch], r12b
0x180005abc  jz      short loc_180005ADC
0x180005abe  cmp     [rcx+19h], r12b
0x180005ac2  jb      short loc_180005ADC
0x180005ac4  mov     edx, 84h
0x180005ac9  mov     rcx, [rcx+10h]
0x180005acd  lea     r8, WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids
0x180005ad4  mov     r9d, edi
0x180005ad7  call    WPP_SF_d
0x180005adc  test    edi, edi
0x180005ade  jnz     loc_180005B6C
0x180005ae4  mov     eax, 1
0x180005ae9  jmp     loc_180005C1A
0x180005aee  mov     ecx, 4949h
0x180005af3  cmp     [rax], cx
0x180005af6  jnz     short loc_180005B39
0x180005af8  cmp     word ptr [rax+2], 2Ah ; '*'
0x180005afd  jnz     short loc_180005B39
0x180005aff  mov     ecx, [rax+4]
0x180005b02  mov     rax, [rsp+78h+arg_28]
0x180005b0a  mov     [rax], ecx
0x180005b0c  cmp     ecx, [rbx]
0x180005b0e  jbe     short loc_180005AE4
0x180005b10  mov     edi, 0Bh
0x180005b15  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b1c  lea     rax, WPP_GLOBAL_Control
0x180005b23  cmp     rcx, rax
0x180005b26  jz      short loc_180005B6C
0x180005b28  test    [rcx+1Ch], r12b
0x180005b2c  jz      short loc_180005B6C
0x180005b2e  cmp     [rcx+19h], r12b
0x180005b32  jb      short loc_180005B6C
0x180005b34  lea     edx, [rdi+7Bh]
0x180005b37  jmp     short loc_180005B60
0x180005b39  mov     edi, 0Bh
0x180005b3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b45  lea     rax, WPP_GLOBAL_Control
0x180005b4c  cmp     rcx, rax
0x180005b4f  jz      short loc_180005B6C
0x180005b51  test    [rcx+1Ch], r12b
0x180005b55  jz      short loc_180005B6C
0x180005b57  cmp     [rcx+19h], r12b
0x180005b5b  jb      short loc_180005B6C
0x180005b5d  lea     edx, [rdi+7Ah]
0x180005b60  mov     rcx, [rcx+10h]
0x180005b64  mov     r9, rsi
0x180005b67  call    WPP_SF_S
0x180005b6c  lea     rsi, WPP_GLOBAL_Control
0x180005b73  mov     rcx, [rbp+0]; lpBaseAddress
0x180005b77  test    rcx, rcx
0x180005b7a  jz      short loc_180005BCB
0x180005b7c  call    cs:__imp_UnmapViewOfFile
0x180005b83  nop     dword ptr [rax+rax+00h]
0x180005b88  test    eax, eax
0x180005b8a  jnz     short loc_180005BCB
0x180005b8c  mov     rbx, cs:WPP_GLOBAL_Control
0x180005b93  cmp     rbx, rsi
0x180005b96  jz      short loc_180005BCB
0x180005b98  test    [rbx+1Ch], r12b
0x180005b9c  jz      short loc_180005BCB
0x180005b9e  cmp     [rbx+19h], r12b
0x180005ba2  jb      short loc_180005BCB
0x180005ba4  mov     rbx, [rbx+10h]
0x180005ba8  call    cs:__imp_GetLastError
0x180005baf  nop     dword ptr [rax+rax+00h]
0x180005bb4  mov     edx, 87h
0x180005bb9  lea     r8, WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids
0x180005bc0  mov     r9d, eax
0x180005bc3  mov     rcx, rbx
0x180005bc6  call    WPP_SF_d
0x180005bcb  mov     rcx, [r15]; hObject
0x180005bce  test    rcx, rcx
0x180005bd1  jz      short loc_180005BDF
0x180005bd3  call    cs:__imp_CloseHandle
0x180005bda  nop     dword ptr [rax+rax+00h]
0x180005bdf  cmp     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x180005be3  jz      short loc_180005BF4
0x180005be5  mov     rcx, [r14]; hObject
0x180005be8  call    cs:__imp_CloseHandle
0x180005bef  nop     dword ptr [rax+rax+00h]
0x180005bf4  mov     qword ptr [rbp+0], 0
0x180005bfc  mov     ecx, edi; dwErrCode
0x180005bfe  mov     qword ptr [r15], 0
0x180005c05  mov     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x180005c0c  call    cs:__imp_SetLastError
0x180005c13  nop     dword ptr [rax+rax+00h]
0x180005c18  xor     eax, eax
0x180005c1a  add     rsp, 40h
0x180005c1e  pop     r15
0x180005c20  pop     r14
0x180005c22  pop     r12
0x180005c24  pop     rdi
0x180005c25  pop     rsi
0x180005c26  pop     rbp
0x180005c27  pop     rbx
0x180005c28  retn
```
