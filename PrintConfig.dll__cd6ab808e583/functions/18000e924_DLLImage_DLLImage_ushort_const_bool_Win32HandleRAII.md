# DLLImage::DLLImage(ushort const *,bool,Win32HandleRAII *)

- ea: `0x18000e924`
- end: `0x18000efd4`
- name: `??0DLLImage@@QEAA@PEBG_NPEAVWin32HandleRAII@@@Z`
- size: `1712`
- prototype: `DLLImage *__fastcall(DLLImage *this, const unsigned __int16 *, char, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180014720`
- `0x180015388`

## callees

- `0x180004424`
- `0x18000e924`
- `0x18000f380`
- `0x180018bbc`

## import_xrefs

- `KERNEL32!CreateFileMappingW` at `0x18000e9bf`
- `KERNEL32!CreateFileMappingW` at `0x18000e9bf`
- `KERNEL32!UnmapViewOfFile` at `0x18000eb0e`
- `KERNEL32!UnmapViewOfFile` at `0x18000eb0e`
- `KERNEL32!MapViewOfFile` at `0x18000ea0e`
- `KERNEL32!MapViewOfFile` at `0x18000ea0e`
- `KERNEL32!GetFileSize` at `0x18000e9e6`
- `KERNEL32!GetFileSize` at `0x18000e9e6`
- `KERNEL32!CreateFileW` at `0x18000e97d`
- `KERNEL32!CreateFileW` at `0x18000e97d`
- `KERNEL32!CloseHandle` at `0x18000eb18`
- `KERNEL32!CloseHandle` at `0x18000eb2c`
- `KERNEL32!CloseHandle` at `0x18000eb18`
- `KERNEL32!CloseHandle` at `0x18000eb2c`
- `KERNEL32!GetLastError` at `0x18000ea20`
- `KERNEL32!GetLastError` at `0x18000eba0`
- `KERNEL32!GetLastError` at `0x18000ec02`
- `KERNEL32!GetLastError` at `0x18000ec64`
- `KERNEL32!GetLastError` at `0x18000ece2`
- `KERNEL32!GetLastError` at `0x18000ea20`
- `KERNEL32!GetLastError` at `0x18000eba0`
- `KERNEL32!GetLastError` at `0x18000ec02`
- `KERNEL32!GetLastError` at `0x18000ec64`
- `KERNEL32!GetLastError` at `0x18000ece2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
DLLImage *__fastcall DLLImage::DLLImage(DLLImage *this, const unsigned __int16 *a2, char a3, void **a4)
{
  char *FileW; // rdi
  void *v8; // r14
  void *v9; // rcx
  char *FileMappingW; // rsi
  DWORD FileSize; // r14d
  unsigned int *v12; // rbx
  signed int v13; // eax
  bool v14; // sf
  __int64 v15; // rax
  unsigned int v16; // ecx
  unsigned int v17; // r8d
  int v18; // r10d
  unsigned int v19; // ecx
  char *v20; // r9
  unsigned __int16 v21; // r8
  int v22; // edx
  signed int v24; // eax
  unsigned int v25; // ebx
  signed int LastError; // eax
  unsigned int v27; // ebx
  signed int v28; // eax
  unsigned int v29; // ebx
  signed int v30; // eax
  unsigned int v31; // ebx
  _BYTE pExceptionObject[32]; // [rsp+50h] [rbp-20h] BYREF

  *((_BYTE *)this + 1) = 0;
  FileW = 0;
  if ( a4 )
  {
    v8 = 0;
    v9 = *a4;
  }
  else
  {
    FileW = (char *)CreateFileW(a2, 0x80000000, 7u, 0, 3u, 0, 0);
    if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      v27 = LastError;
      if ( LastError > 0 )
        v27 = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 64, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids, v27);
      }
      hr_error::hr_error((hr_error *)pExceptionObject, v27);
      throw (hr_error *)pExceptionObject;
    }
    v8 = FileW;
    v9 = FileW;
  }
  FileMappingW = (char *)CreateFileMappingW(v9, 0, 2u, 0, 0, 0);
  if ( (unsigned __int64)(FileMappingW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v24 = GetLastError();
    v25 = v24;
    if ( v24 > 0 )
      v25 = (unsigned __int16)v24 | 0x80070000;
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 65, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids, v25);
    }
    hr_error::hr_error((hr_error *)pExceptionObject, v25);
    throw (hr_error *)pExceptionObject;
  }
  if ( a4 )
    v8 = *a4;
  FileSize = GetFileSize(v8, 0);
  if ( FileSize == -1 )
  {
    v28 = GetLastError();
    v29 = v28;
    if ( v28 > 0 )
      v29 = (unsigned __int16)v28 | 0x80070000;
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 66, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids, v29);
    }
    hr_error::hr_error((hr_error *)pExceptionObject, v29);
    throw (hr_error *)pExceptionObject;
  }
  v12 = (unsigned int *)MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
  if ( !v12 )
  {
    v13 = GetLastError();
    v14 = v13 < 0;
    if ( v13 > 0 )
    {
      v13 = (unsigned __int16)v13 | 0x80070000;
      v14 = v13 < 0;
    }
    if ( v14 )
    {
      hr_error::hr_error((hr_error *)pExceptionObject, v13);
      throw (hr_error *)pExceptionObject;
    }
  }
  if ( !v12 )
  {
    v30 = GetLastError();
    v31 = v30;
    if ( v30 > 0 )
      v31 = (unsigned __int16)v30 | 0x80070000;
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 67, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids, v31);
    }
    hr_error::hr_error((hr_error *)pExceptionObject, v31);
    throw (hr_error *)pExceptionObject;
  }
  if ( FileSize < 0x40 )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 68, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids, 2147942411LL);
    }
    hr_error::hr_error((hr_error *)pExceptionObject, -2147024885);
    throw (hr_error *)pExceptionObject;
  }
  v15 = v12[15];
  if ( (int)v15 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 69, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids, 2147942934LL);
    }
    hr_error::hr_error((hr_error *)pExceptionObject, -2147024362);
    throw (hr_error *)pExceptionObject;
  }
  if ( (int)v15 + 264 < (unsigned int)v15 )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 70, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids, 2147942934LL);
    }
    hr_error::hr_error((hr_error *)pExceptionObject, -2147024362);
    throw (hr_error *)pExceptionObject;
  }
  if ( *(_WORD *)v12 != 23117 || FileSize < (int)v15 + 264 )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 71, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids, 2147942411LL);
    }
    hr_error::hr_error((hr_error *)pExceptionObject, -2147024885);
    throw (hr_error *)pExceptionObject;
  }
  if ( *(unsigned int *)((char *)v12 + v15) != 17744 )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 72, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids, 2147942411LL);
    }
    hr_error::hr_error((hr_error *)pExceptionObject, -2147024885);
    throw (hr_error *)pExceptionObject;
  }
  *((_BYTE *)this + 1) = 1;
  if ( a3 )
  {
    v16 = v15 + 24;
    if ( (int)v15 + 24 < (unsigned int)v15 )
    {
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 73, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids, 2147942934LL);
      }
      hr_error::hr_error((hr_error *)pExceptionObject, -2147024362);
      throw (hr_error *)pExceptionObject;
    }
    v17 = v16 + *(unsigned __int16 *)((char *)v12 + v15 + 20);
    if ( v17 < v16 )
    {
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 74, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids, 2147942934LL);
      }
      hr_error::hr_error((hr_error *)pExceptionObject, -2147024362);
      throw (hr_error *)pExceptionObject;
    }
    v18 = *(unsigned __int16 *)((char *)v12 + v15 + 6);
    v19 = 40 * v18 + v17;
    if ( v19 < 40 * v18 )
    {
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 76, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids, 2147942934LL);
      }
      hr_error::hr_error((hr_error *)pExceptionObject, -2147024362);
      throw (hr_error *)pExceptionObject;
    }
    if ( FileSize < v19 )
    {
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 77, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids, 2147942411LL);
      }
      hr_error::hr_error((hr_error *)pExceptionObject, -2147024885);
      throw (hr_error *)pExceptionObject;
    }
    v20 = (char *)v12 + v17;
    *(_BYTE *)this = 0;
    v21 = 0;
    do
    {
      if ( v21 >= (unsigned __int16)v18 )
        break;
      v22 = *(_DWORD *)&v20[40 * v21 + 36];
      *(_BYTE *)this = (v22 & 0x20000020) != 0;
      ++v21;
    }
    while ( (v22 & 0x20000020) == 0 );
  }
  UnmapViewOfFile(v12);
  CloseHandle(FileMappingW);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileW);
  return this;
}

```

## disassembly

```asm
0x18000e924  mov     r11, rsp
0x18000e927  push    rbp
0x18000e928  push    rdi
0x18000e929  push    r12
0x18000e92b  push    r14
0x18000e92d  push    r15
0x18000e92f  mov     rbp, rsp
0x18000e932  sub     rsp, 70h
0x18000e936  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFEh
0x18000e93e  mov     [r11+10h], rbx
0x18000e942  mov     [r11+18h], rsi
0x18000e946  mov     rbx, r9
0x18000e949  mov     r12b, r8b
0x18000e94c  mov     rax, rdx
0x18000e94f  mov     r15, rcx
0x18000e952  mov     byte ptr [rcx+1], 0
0x18000e956  xor     edi, edi
0x18000e958  mov     [rbp+arg_0], rdi
0x18000e95c  test    r9, r9
0x18000e95f  jnz     short loc_18000E99F
0x18000e961  mov     [r11-68h], rdi
0x18000e965  mov     [rsp+70h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x18000e969  mov     [rsp+70h+dwCreationDisposition], 3; dwCreationDisposition
0x18000e971  mov     edx, 80000000h; dwDesiredAccess
0x18000e976  lea     r8d, [r9+7]; dwShareMode
0x18000e97a  mov     rcx, rax; lpFileName
0x18000e97d  call    cs:__imp_CreateFileW
0x18000e983  mov     rdi, rax
0x18000e986  mov     [rbp+arg_0], rax
0x18000e98a  dec     rax
0x18000e98d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000e991  ja      loc_18000EC02
0x18000e997  mov     r14, rdi
0x18000e99a  mov     rcx, rdi
0x18000e99d  jmp     short loc_18000E9A5
0x18000e99f  xor     r14d, r14d
0x18000e9a2  mov     rcx, [r9]; hFile
0x18000e9a5  mov     qword ptr [rsp+70h+dwFlagsAndAttributes], 0; lpName
0x18000e9ae  mov     [rsp+70h+dwCreationDisposition], 0; dwMaximumSizeLow
0x18000e9b6  xor     r9d, r9d; dwMaximumSizeHigh
0x18000e9b9  xor     edx, edx; lpFileMappingAttributes
0x18000e9bb  lea     r8d, [r9+2]; flProtect
0x18000e9bf  call    cs:__imp_CreateFileMappingW
0x18000e9c5  mov     rsi, rax
0x18000e9c8  mov     [rbp+arg_18], rax
0x18000e9cc  dec     rax
0x18000e9cf  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000e9d3  ja      loc_18000EBA0
0x18000e9d9  test    rbx, rbx
0x18000e9dc  jz      short loc_18000E9E1
0x18000e9de  mov     r14, [rbx]
0x18000e9e1  xor     edx, edx; lpFileSizeHigh
0x18000e9e3  mov     rcx, r14; hFile
0x18000e9e6  call    cs:__imp_GetFileSize
0x18000e9ec  mov     r14d, eax
0x18000e9ef  cmp     eax, 0FFFFFFFFh
0x18000e9f2  jz      loc_18000EC64
0x18000e9f8  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x18000ea01  xor     r9d, r9d; dwFileOffsetLow
0x18000ea04  xor     r8d, r8d; dwFileOffsetHigh
0x18000ea07  lea     edx, [r9+4]; dwDesiredAccess
0x18000ea0b  mov     rcx, rsi; hFileMappingObject
0x18000ea0e  call    cs:__imp_MapViewOfFile
0x18000ea14  mov     rbx, rax
0x18000ea17  mov     [rbp+var_28], rax
0x18000ea1b  test    rax, rax
0x18000ea1e  jnz     short loc_18000EA3A
0x18000ea20  call    cs:__imp_GetLastError
0x18000ea26  test    eax, eax
0x18000ea28  jle     short loc_18000EA34
0x18000ea2a  movzx   eax, ax
0x18000ea2d  or      eax, 80070000h
0x18000ea32  test    eax, eax
0x18000ea34  js      loc_18000ECC6
0x18000ea3a  test    rbx, rbx
0x18000ea3d  jz      loc_18000ECE2
0x18000ea43  cmp     r14d, 40h ; '@'
0x18000ea47  jb      loc_18000ED44
0x18000ea4d  mov     eax, [rbx+3Ch]
0x18000ea50  test    eax, eax
0x18000ea52  js      loc_18000EB4E
0x18000ea58  lea     ecx, [rax+108h]
0x18000ea5e  cmp     ecx, eax
0x18000ea60  jb      loc_18000EF82
0x18000ea66  mov     edx, 5A4Dh
0x18000ea6b  cmp     [rbx], dx
0x18000ea6e  jnz     loc_18000EF30
0x18000ea74  cmp     r14d, ecx
0x18000ea77  jb      loc_18000EF30
0x18000ea7d  cmp     dword ptr [rax+rbx], 4550h
0x18000ea84  jnz     loc_18000ED96
0x18000ea8a  mov     byte ptr [r15+1], 1
0x18000ea8f  test    r12b, r12b
0x18000ea92  jz      short loc_18000EB0B
0x18000ea94  lea     ecx, [rax+18h]
0x18000ea97  cmp     ecx, eax
0x18000ea99  jb      loc_18000EEDE
0x18000ea9f  movzx   r8d, word ptr [rax+rbx+14h]
0x18000eaa5  add     r8d, ecx
0x18000eaa8  cmp     r8d, ecx
0x18000eaab  jb      loc_18000EE8C
0x18000eab1  movzx   r10d, word ptr [rax+rbx+6]
0x18000eab7  lea     eax, [r10+r10*4]
0x18000eabb  shl     eax, 3
0x18000eabe  lea     ecx, [rax+r8]
0x18000eac2  cmp     ecx, eax
0x18000eac4  jb      loc_18000EE3A
0x18000eaca  cmp     r14d, ecx
0x18000eacd  jb      loc_18000EDE8
0x18000ead3  mov     r9d, r8d
0x18000ead6  add     r9, rbx
0x18000ead9  mov     byte ptr [r15], 0
0x18000eadd  xor     r8d, r8d
0x18000eae0  cmp     r8w, r10w
0x18000eae4  jnb     short loc_18000EB0B
0x18000eae6  movzx   eax, r8w
0x18000eaea  lea     rcx, [rax+rax*4]
0x18000eaee  mov     edx, [r9+rcx*8+24h]
0x18000eaf3  test    edx, 20000020h
0x18000eaf9  setnz   al
0x18000eafc  mov     [r15], al
0x18000eaff  inc     r8w
0x18000eb03  test    edx, 20000020h
0x18000eb09  jz      short loc_18000EAE0
0x18000eb0b  mov     rcx, rbx; lpBaseAddress
0x18000eb0e  call    cs:__imp_UnmapViewOfFile
0x18000eb14  nop
0x18000eb15  mov     rcx, rsi; hObject
0x18000eb18  call    cs:__imp_CloseHandle
0x18000eb1e  nop
0x18000eb1f  lea     rax, [rdi-1]
0x18000eb23  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000eb27  ja      short loc_18000EB32
0x18000eb29  mov     rcx, rdi; hObject
0x18000eb2c  call    cs:__imp_CloseHandle
0x18000eb32  mov     rax, r15
0x18000eb35  lea     r11, [rsp+70h+var_s0]
0x18000eb3a  mov     rbx, [r11+38h]
0x18000eb3e  mov     rsi, [r11+40h]
0x18000eb42  mov     rsp, r11
0x18000eb45  pop     r15
0x18000eb47  pop     r14
0x18000eb49  pop     r12
0x18000eb4b  pop     rdi
0x18000eb4c  pop     rbp
0x18000eb4d  retn
0x18000eb4e  lea     rax, WPP_GLOBAL_Control
0x18000eb55  mov     ebx, 80070216h
0x18000eb5a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eb61  cmp     rcx, rax
0x18000eb64  jz      short loc_18000EB84
0x18000eb66  test    byte ptr [rcx+44h], 1
0x18000eb6a  jz      short loc_18000EB84
0x18000eb6c  mov     edx, 45h ; 'E'
0x18000eb71  mov     r9d, ebx
0x18000eb74  lea     r8, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids
0x18000eb7b  mov     rcx, [rcx+38h]
0x18000eb7f  call    WPP_SF_d
0x18000eb84  mov     edx, ebx; int
0x18000eb86  lea     rcx, [rbp+pExceptionObject]; this
0x18000eb8a  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18000eb8f  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18000eb96  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000eb9a  call    _CxxThrowException_0
0x18000eba0  call    cs:__imp_GetLastError
0x18000eba6  mov     ebx, eax
0x18000eba8  test    eax, eax
0x18000ebaa  jle     short loc_18000EBB5
0x18000ebac  movzx   ebx, ax
0x18000ebaf  or      ebx, 80070000h
0x18000ebb5  lea     rax, WPP_GLOBAL_Control
0x18000ebbc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ebc3  cmp     rcx, rax
0x18000ebc6  jz      short loc_18000EBE6
0x18000ebc8  test    byte ptr [rcx+44h], 1
0x18000ebcc  jz      short loc_18000EBE6
0x18000ebce  mov     edx, 41h ; 'A'
0x18000ebd3  mov     r9d, ebx
0x18000ebd6  lea     r8, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids
0x18000ebdd  mov     rcx, [rcx+38h]
0x18000ebe1  call    WPP_SF_d
0x18000ebe6  mov     edx, ebx; int
0x18000ebe8  lea     rcx, [rbp+pExceptionObject]; this
0x18000ebec  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18000ebf1  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18000ebf8  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000ebfc  call    _CxxThrowException_0
0x18000ec02  call    cs:__imp_GetLastError
0x18000ec08  mov     ebx, eax
0x18000ec0a  test    eax, eax
0x18000ec0c  jle     short loc_18000EC17
0x18000ec0e  movzx   ebx, ax
0x18000ec11  or      ebx, 80070000h
0x18000ec17  lea     rax, WPP_GLOBAL_Control
0x18000ec1e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec25  cmp     rcx, rax
0x18000ec28  jz      short loc_18000EC48
0x18000ec2a  test    byte ptr [rcx+44h], 1
0x18000ec2e  jz      short loc_18000EC48
0x18000ec30  mov     edx, 40h ; '@'
0x18000ec35  mov     r9d, ebx
0x18000ec38  lea     r8, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids
0x18000ec3f  mov     rcx, [rcx+38h]
0x18000ec43  call    WPP_SF_d
0x18000ec48  mov     edx, ebx; int
0x18000ec4a  lea     rcx, [rbp+pExceptionObject]; this
0x18000ec4e  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18000ec53  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18000ec5a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000ec5e  call    _CxxThrowException_0
0x18000ec64  call    cs:__imp_GetLastError
0x18000ec6a  mov     ebx, eax
0x18000ec6c  test    eax, eax
0x18000ec6e  jle     short loc_18000EC79
0x18000ec70  movzx   ebx, ax
0x18000ec73  or      ebx, 80070000h
0x18000ec79  lea     rax, WPP_GLOBAL_Control
0x18000ec80  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec87  cmp     rcx, rax
0x18000ec8a  jz      short loc_18000ECAA
0x18000ec8c  test    byte ptr [rcx+44h], 1
0x18000ec90  jz      short loc_18000ECAA
0x18000ec92  mov     edx, 42h ; 'B'
0x18000ec97  mov     r9d, ebx
0x18000ec9a  lea     r8, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids
0x18000eca1  mov     rcx, [rcx+38h]
0x18000eca5  call    WPP_SF_d
0x18000ecaa  mov     edx, ebx; int
0x18000ecac  lea     rcx, [rbp+pExceptionObject]; this
0x18000ecb0  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18000ecb5  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18000ecbc  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000ecc0  call    _CxxThrowException_0
0x18000ecc6  mov     edx, eax; int
0x18000ecc8  lea     rcx, [rbp+pExceptionObject]; this
0x18000eccc  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18000ecd1  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18000ecd8  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000ecdc  call    _CxxThrowException_0
0x18000ece2  call    cs:__imp_GetLastError
0x18000ece8  mov     ebx, eax
0x18000ecea  test    eax, eax
0x18000ecec  jle     short loc_18000ECF7
0x18000ecee  movzx   ebx, ax
0x18000ecf1  or      ebx, 80070000h
0x18000ecf7  lea     rax, WPP_GLOBAL_Control
0x18000ecfe  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed05  cmp     rcx, rax
0x18000ed08  jz      short loc_18000ED28
0x18000ed0a  test    byte ptr [rcx+44h], 1
0x18000ed0e  jz      short loc_18000ED28
0x18000ed10  mov     edx, 43h ; 'C'
0x18000ed15  mov     r9d, ebx
0x18000ed18  lea     r8, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids
0x18000ed1f  mov     rcx, [rcx+38h]
0x18000ed23  call    WPP_SF_d
0x18000ed28  mov     edx, ebx; int
0x18000ed2a  lea     rcx, [rbp+pExceptionObject]; this
0x18000ed2e  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18000ed33  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18000ed3a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000ed3e  call    _CxxThrowException_0
0x18000ed44  lea     rax, WPP_GLOBAL_Control
0x18000ed4b  mov     ebx, 8007000Bh
0x18000ed50  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed57  cmp     rcx, rax
0x18000ed5a  jz      short loc_18000ED7A
0x18000ed5c  test    byte ptr [rcx+44h], 1
0x18000ed60  jz      short loc_18000ED7A
0x18000ed62  mov     edx, 44h ; 'D'
0x18000ed67  mov     r9d, ebx
0x18000ed6a  lea     r8, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids
0x18000ed71  mov     rcx, [rcx+38h]
0x18000ed75  call    WPP_SF_d
0x18000ed7a  mov     edx, ebx; int
0x18000ed7c  lea     rcx, [rbp+pExceptionObject]; this
0x18000ed80  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18000ed85  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18000ed8c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000ed90  call    _CxxThrowException_0
0x18000ed96  lea     rax, WPP_GLOBAL_Control
0x18000ed9d  mov     ebx, 8007000Bh
0x18000eda2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eda9  cmp     rcx, rax
0x18000edac  jz      short loc_18000EDCC
0x18000edae  test    byte ptr [rcx+44h], 1
0x18000edb2  jz      short loc_18000EDCC
0x18000edb4  mov     edx, 48h ; 'H'
0x18000edb9  mov     r9d, ebx
0x18000edbc  lea     r8, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids
0x18000edc3  mov     rcx, [rcx+38h]
0x18000edc7  call    WPP_SF_d
0x18000edcc  mov     edx, ebx; int
0x18000edce  lea     rcx, [rbp+pExceptionObject]; this
0x18000edd2  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18000edd7  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18000edde  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000ede2  call    _CxxThrowException_0
0x18000ede8  lea     rax, WPP_GLOBAL_Control
0x18000edef  mov     ebx, 8007000Bh
  ... truncated ...
```
