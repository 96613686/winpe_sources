# DLLImage::DLLImage(ushort const *,bool,Win32HandleRAII *)

- ea: `0x18000ed5c`
- end: `0x18000f455`
- name: `??0DLLImage@@QEAA@PEBG_NPEAVWin32HandleRAII@@@Z`
- size: `1785`
- prototype: `DLLImage *__fastcall(DLLImage *this, const unsigned __int16 *, char, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180015010`
- `0x180015d08`

## callees

- `0x180004564`
- `0x18000ed5c`
- `0x18000f830`
- `0x1800197b4`

## import_xrefs

- `KERNEL32!CreateFileMappingW` at `0x18000edfd`
- `KERNEL32!CreateFileMappingW` at `0x18000edfd`
- `KERNEL32!UnmapViewOfFile` at `0x18000ef64`
- `KERNEL32!UnmapViewOfFile` at `0x18000ef64`
- `KERNEL32!MapViewOfFile` at `0x18000ee58`
- `KERNEL32!MapViewOfFile` at `0x18000ee58`
- `KERNEL32!GetFileSize` at `0x18000ee2a`
- `KERNEL32!GetFileSize` at `0x18000ee2a`
- `KERNEL32!CreateFileW` at `0x18000edb5`
- `KERNEL32!CreateFileW` at `0x18000edb5`
- `KERNEL32!CloseHandle` at `0x18000ef74`
- `KERNEL32!CloseHandle` at `0x18000ef8e`
- `KERNEL32!CloseHandle` at `0x18000ef74`
- `KERNEL32!CloseHandle` at `0x18000ef8e`
- `KERNEL32!GetLastError` at `0x18000ee70`
- `KERNEL32!GetLastError` at `0x18000f009`
- `KERNEL32!GetLastError` at `0x18000f071`
- `KERNEL32!GetLastError` at `0x18000f0d9`
- `KERNEL32!GetLastError` at `0x18000f15d`
- `KERNEL32!GetLastError` at `0x18000ee70`
- `KERNEL32!GetLastError` at `0x18000f009`
- `KERNEL32!GetLastError` at `0x18000f071`
- `KERNEL32!GetLastError` at `0x18000f0d9`
- `KERNEL32!GetLastError` at `0x18000f15d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          0x40u,
          (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
          v27);
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
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        0x41u,
        (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
        v25);
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
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        0x42u,
        (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
        v29);
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
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        0x43u,
        (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
        v31);
    }
    hr_error::hr_error((hr_error *)pExceptionObject, v31);
    throw (hr_error *)pExceptionObject;
  }
  if ( FileSize < 0x40 )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        0x44u,
        (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
        -2147024885);
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
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        0x45u,
        (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
        -2147024362);
    }
    hr_error::hr_error((hr_error *)pExceptionObject, -2147024362);
    throw (hr_error *)pExceptionObject;
  }
  if ( (int)v15 + 264 < (unsigned int)v15 )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        0x46u,
        (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
        -2147024362);
    }
    hr_error::hr_error((hr_error *)pExceptionObject, -2147024362);
    throw (hr_error *)pExceptionObject;
  }
  if ( *(_WORD *)v12 != 23117 || FileSize < (int)v15 + 264 )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        0x47u,
        (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
        -2147024885);
    }
    hr_error::hr_error((hr_error *)pExceptionObject, -2147024885);
    throw (hr_error *)pExceptionObject;
  }
  if ( *(unsigned int *)((char *)v12 + v15) != 17744 )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        0x48u,
        (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
        -2147024885);
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
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          0x49u,
          (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
          -2147024362);
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
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          0x4Au,
          (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
          -2147024362);
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
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          0x4Cu,
          (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
          -2147024362);
      }
      hr_error::hr_error((hr_error *)pExceptionObject, -2147024362);
      throw (hr_error *)pExceptionObject;
    }
    if ( FileSize < v19 )
    {
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          0x4Du,
          (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
          -2147024885);
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
0x18000ed5c  mov     r11, rsp
0x18000ed5f  push    rbp
0x18000ed60  push    rdi
0x18000ed61  push    r12
0x18000ed63  push    r14
0x18000ed65  push    r15
0x18000ed67  mov     rbp, rsp
0x18000ed6a  sub     rsp, 70h
0x18000ed6e  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFEh
0x18000ed76  mov     [r11+10h], rbx
0x18000ed7a  mov     [r11+18h], rsi
0x18000ed7e  mov     rbx, r9
0x18000ed81  mov     r12b, r8b
0x18000ed84  mov     rax, rdx
0x18000ed87  mov     r15, rcx
0x18000ed8a  mov     byte ptr [rcx+1], 0
0x18000ed8e  xor     edi, edi
0x18000ed90  mov     [rbp+arg_0], rdi
0x18000ed94  test    r9, r9
0x18000ed97  jnz     short loc_18000EDDD
0x18000ed99  mov     [r11-68h], rdi
0x18000ed9d  mov     [rsp+70h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x18000eda1  mov     [rsp+70h+dwCreationDisposition], 3; dwCreationDisposition
0x18000eda9  mov     edx, 80000000h; dwDesiredAccess
0x18000edae  lea     r8d, [r9+7]; dwShareMode
0x18000edb2  mov     rcx, rax; lpFileName
0x18000edb5  call    cs:__imp_CreateFileW
0x18000edbc  nop     dword ptr [rax+rax+00h]
0x18000edc1  mov     rdi, rax
0x18000edc4  mov     [rbp+arg_0], rax
0x18000edc8  dec     rax
0x18000edcb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000edcf  ja      loc_18000F071
0x18000edd5  mov     r14, rdi
0x18000edd8  mov     rcx, rdi
0x18000eddb  jmp     short loc_18000EDE3
0x18000eddd  xor     r14d, r14d
0x18000ede0  mov     rcx, [r9]; hFile
0x18000ede3  mov     qword ptr [rsp+70h+dwFlagsAndAttributes], 0; lpName
0x18000edec  mov     [rsp+70h+dwCreationDisposition], 0; dwMaximumSizeLow
0x18000edf4  xor     r9d, r9d; dwMaximumSizeHigh
0x18000edf7  xor     edx, edx; lpFileMappingAttributes
0x18000edf9  lea     r8d, [r9+2]; flProtect
0x18000edfd  call    cs:__imp_CreateFileMappingW
0x18000ee04  nop     dword ptr [rax+rax+00h]
0x18000ee09  mov     rsi, rax
0x18000ee0c  mov     [rbp+arg_18], rax
0x18000ee10  dec     rax
0x18000ee13  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000ee17  ja      loc_18000F009
0x18000ee1d  test    rbx, rbx
0x18000ee20  jz      short loc_18000EE25
0x18000ee22  mov     r14, [rbx]
0x18000ee25  xor     edx, edx; lpFileSizeHigh
0x18000ee27  mov     rcx, r14; hFile
0x18000ee2a  call    cs:__imp_GetFileSize
0x18000ee31  nop     dword ptr [rax+rax+00h]
0x18000ee36  mov     r14d, eax
0x18000ee39  cmp     eax, 0FFFFFFFFh
0x18000ee3c  jz      loc_18000F0D9
0x18000ee42  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x18000ee4b  xor     r9d, r9d; dwFileOffsetLow
0x18000ee4e  xor     r8d, r8d; dwFileOffsetHigh
0x18000ee51  lea     edx, [r9+4]; dwDesiredAccess
0x18000ee55  mov     rcx, rsi; hFileMappingObject
0x18000ee58  call    cs:__imp_MapViewOfFile
0x18000ee5f  nop     dword ptr [rax+rax+00h]
0x18000ee64  mov     rbx, rax
0x18000ee67  mov     [rbp+var_28], rax
0x18000ee6b  test    rax, rax
0x18000ee6e  jnz     short loc_18000EE90
0x18000ee70  call    cs:__imp_GetLastError
0x18000ee77  nop     dword ptr [rax+rax+00h]
0x18000ee7c  test    eax, eax
0x18000ee7e  jle     short loc_18000EE8A
0x18000ee80  movzx   eax, ax
0x18000ee83  or      eax, 80070000h
0x18000ee88  test    eax, eax
0x18000ee8a  js      loc_18000F141
0x18000ee90  test    rbx, rbx
0x18000ee93  jz      loc_18000F15D
0x18000ee99  cmp     r14d, 40h ; '@'
0x18000ee9d  jb      loc_18000F1C5
0x18000eea3  mov     eax, [rbx+3Ch]
0x18000eea6  test    eax, eax
0x18000eea8  js      loc_18000EFB7
0x18000eeae  lea     ecx, [rax+108h]
0x18000eeb4  cmp     ecx, eax
0x18000eeb6  jb      loc_18000F403
0x18000eebc  mov     edx, 5A4Dh
0x18000eec1  cmp     [rbx], dx
0x18000eec4  jnz     loc_18000F3B1
0x18000eeca  cmp     r14d, ecx
0x18000eecd  jb      loc_18000F3B1
0x18000eed3  cmp     dword ptr [rax+rbx], 4550h
0x18000eeda  jnz     loc_18000F217
0x18000eee0  mov     byte ptr [r15+1], 1
0x18000eee5  test    r12b, r12b
0x18000eee8  jz      short loc_18000EF61
0x18000eeea  lea     ecx, [rax+18h]
0x18000eeed  cmp     ecx, eax
0x18000eeef  jb      loc_18000F35F
0x18000eef5  movzx   r8d, word ptr [rax+rbx+14h]
0x18000eefb  add     r8d, ecx
0x18000eefe  cmp     r8d, ecx
0x18000ef01  jb      loc_18000F30D
0x18000ef07  movzx   r10d, word ptr [rax+rbx+6]
0x18000ef0d  lea     eax, [r10+r10*4]
0x18000ef11  shl     eax, 3
0x18000ef14  lea     ecx, [rax+r8]
0x18000ef18  cmp     ecx, eax
0x18000ef1a  jb      loc_18000F2BB
0x18000ef20  cmp     r14d, ecx
0x18000ef23  jb      loc_18000F269
0x18000ef29  mov     r9d, r8d
0x18000ef2c  add     r9, rbx
0x18000ef2f  mov     byte ptr [r15], 0
0x18000ef33  xor     r8d, r8d
0x18000ef36  cmp     r8w, r10w
0x18000ef3a  jnb     short loc_18000EF61
0x18000ef3c  movzx   eax, r8w
0x18000ef40  lea     rcx, [rax+rax*4]
0x18000ef44  mov     edx, [r9+rcx*8+24h]
0x18000ef49  test    edx, 20000020h
0x18000ef4f  setnz   al
0x18000ef52  mov     [r15], al
0x18000ef55  inc     r8w
0x18000ef59  test    edx, 20000020h
0x18000ef5f  jz      short loc_18000EF36
0x18000ef61  mov     rcx, rbx; lpBaseAddress
0x18000ef64  call    cs:__imp_UnmapViewOfFile
0x18000ef6b  nop     dword ptr [rax+rax+00h]
0x18000ef70  nop
0x18000ef71  mov     rcx, rsi; hObject
0x18000ef74  call    cs:__imp_CloseHandle
0x18000ef7b  nop     dword ptr [rax+rax+00h]
0x18000ef80  nop
0x18000ef81  lea     rax, [rdi-1]
0x18000ef85  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000ef89  ja      short loc_18000EF9A
0x18000ef8b  mov     rcx, rdi; hObject
0x18000ef8e  call    cs:__imp_CloseHandle
0x18000ef95  nop     dword ptr [rax+rax+00h]
0x18000ef9a  mov     rax, r15
0x18000ef9d  lea     r11, [rsp+70h+var_s0]
0x18000efa2  mov     rbx, [r11+38h]
0x18000efa6  mov     rsi, [r11+40h]
0x18000efaa  mov     rsp, r11
0x18000efad  pop     r15
0x18000efaf  pop     r14
0x18000efb1  pop     r12
0x18000efb3  pop     rdi
0x18000efb4  pop     rbp
0x18000efb5  retn
0x18000efb7  lea     rax, WPP_GLOBAL_Control
0x18000efbe  mov     ebx, 80070216h
0x18000efc3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000efca  cmp     rcx, rax
0x18000efcd  jz      short loc_18000EFED
0x18000efcf  test    byte ptr [rcx+44h], 1
0x18000efd3  jz      short loc_18000EFED
0x18000efd5  mov     edx, 45h ; 'E'
0x18000efda  mov     r9d, ebx
0x18000efdd  lea     r8, WPP_799f402e917533f804c44f52fde54aed_Traceguids
0x18000efe4  mov     rcx, [rcx+38h]
0x18000efe8  call    WPP_SF_d
0x18000efed  mov     edx, ebx; int
0x18000efef  lea     rcx, [rbp+pExceptionObject]; this
0x18000eff3  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18000eff8  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18000efff  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000f003  call    _CxxThrowException_0
0x18000f009  call    cs:__imp_GetLastError
0x18000f010  nop     dword ptr [rax+rax+00h]
0x18000f015  mov     ebx, eax
0x18000f017  test    eax, eax
0x18000f019  jle     short loc_18000F024
0x18000f01b  movzx   ebx, ax
0x18000f01e  or      ebx, 80070000h
0x18000f024  lea     rax, WPP_GLOBAL_Control
0x18000f02b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f032  cmp     rcx, rax
0x18000f035  jz      short loc_18000F055
0x18000f037  test    byte ptr [rcx+44h], 1
0x18000f03b  jz      short loc_18000F055
0x18000f03d  mov     edx, 41h ; 'A'
0x18000f042  mov     r9d, ebx
0x18000f045  lea     r8, WPP_799f402e917533f804c44f52fde54aed_Traceguids
0x18000f04c  mov     rcx, [rcx+38h]
0x18000f050  call    WPP_SF_d
0x18000f055  mov     edx, ebx; int
0x18000f057  lea     rcx, [rbp+pExceptionObject]; this
0x18000f05b  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18000f060  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18000f067  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000f06b  call    _CxxThrowException_0
0x18000f071  call    cs:__imp_GetLastError
0x18000f078  nop     dword ptr [rax+rax+00h]
0x18000f07d  mov     ebx, eax
0x18000f07f  test    eax, eax
0x18000f081  jle     short loc_18000F08C
0x18000f083  movzx   ebx, ax
0x18000f086  or      ebx, 80070000h
0x18000f08c  lea     rax, WPP_GLOBAL_Control
0x18000f093  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f09a  cmp     rcx, rax
0x18000f09d  jz      short loc_18000F0BD
0x18000f09f  test    byte ptr [rcx+44h], 1
0x18000f0a3  jz      short loc_18000F0BD
0x18000f0a5  mov     edx, 40h ; '@'
0x18000f0aa  mov     r9d, ebx
0x18000f0ad  lea     r8, WPP_799f402e917533f804c44f52fde54aed_Traceguids
0x18000f0b4  mov     rcx, [rcx+38h]
0x18000f0b8  call    WPP_SF_d
0x18000f0bd  mov     edx, ebx; int
0x18000f0bf  lea     rcx, [rbp+pExceptionObject]; this
0x18000f0c3  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18000f0c8  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18000f0cf  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000f0d3  call    _CxxThrowException_0
0x18000f0d9  call    cs:__imp_GetLastError
0x18000f0e0  nop     dword ptr [rax+rax+00h]
0x18000f0e5  mov     ebx, eax
0x18000f0e7  test    eax, eax
0x18000f0e9  jle     short loc_18000F0F4
0x18000f0eb  movzx   ebx, ax
0x18000f0ee  or      ebx, 80070000h
0x18000f0f4  lea     rax, WPP_GLOBAL_Control
0x18000f0fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f102  cmp     rcx, rax
0x18000f105  jz      short loc_18000F125
0x18000f107  test    byte ptr [rcx+44h], 1
0x18000f10b  jz      short loc_18000F125
0x18000f10d  mov     edx, 42h ; 'B'
0x18000f112  mov     r9d, ebx
0x18000f115  lea     r8, WPP_799f402e917533f804c44f52fde54aed_Traceguids
0x18000f11c  mov     rcx, [rcx+38h]
0x18000f120  call    WPP_SF_d
0x18000f125  mov     edx, ebx; int
0x18000f127  lea     rcx, [rbp+pExceptionObject]; this
0x18000f12b  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18000f130  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18000f137  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000f13b  call    _CxxThrowException_0
0x18000f141  mov     edx, eax; int
0x18000f143  lea     rcx, [rbp+pExceptionObject]; this
0x18000f147  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18000f14c  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18000f153  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000f157  call    _CxxThrowException_0
0x18000f15d  call    cs:__imp_GetLastError
0x18000f164  nop     dword ptr [rax+rax+00h]
0x18000f169  mov     ebx, eax
0x18000f16b  test    eax, eax
0x18000f16d  jle     short loc_18000F178
0x18000f16f  movzx   ebx, ax
0x18000f172  or      ebx, 80070000h
0x18000f178  lea     rax, WPP_GLOBAL_Control
0x18000f17f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f186  cmp     rcx, rax
0x18000f189  jz      short loc_18000F1A9
0x18000f18b  test    byte ptr [rcx+44h], 1
0x18000f18f  jz      short loc_18000F1A9
0x18000f191  mov     edx, 43h ; 'C'
0x18000f196  mov     r9d, ebx
0x18000f199  lea     r8, WPP_799f402e917533f804c44f52fde54aed_Traceguids
0x18000f1a0  mov     rcx, [rcx+38h]
0x18000f1a4  call    WPP_SF_d
0x18000f1a9  mov     edx, ebx; int
0x18000f1ab  lea     rcx, [rbp+pExceptionObject]; this
0x18000f1af  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18000f1b4  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18000f1bb  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000f1bf  call    _CxxThrowException_0
0x18000f1c5  lea     rax, WPP_GLOBAL_Control
0x18000f1cc  mov     ebx, 8007000Bh
0x18000f1d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f1d8  cmp     rcx, rax
0x18000f1db  jz      short loc_18000F1FB
0x18000f1dd  test    byte ptr [rcx+44h], 1
0x18000f1e1  jz      short loc_18000F1FB
0x18000f1e3  mov     edx, 44h ; 'D'
0x18000f1e8  mov     r9d, ebx
0x18000f1eb  lea     r8, WPP_799f402e917533f804c44f52fde54aed_Traceguids
0x18000f1f2  mov     rcx, [rcx+38h]
0x18000f1f6  call    WPP_SF_d
0x18000f1fb  mov     edx, ebx; int
0x18000f1fd  lea     rcx, [rbp+pExceptionObject]; this
0x18000f201  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18000f206  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18000f20d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000f211  call    _CxxThrowException_0
0x18000f217  lea     rax, WPP_GLOBAL_Control
0x18000f21e  mov     ebx, 8007000Bh
0x18000f223  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f22a  cmp     rcx, rax
0x18000f22d  jz      short loc_18000F24D
0x18000f22f  test    byte ptr [rcx+44h], 1
0x18000f233  jz      short loc_18000F24D
0x18000f235  mov     edx, 48h ; 'H'
  ... truncated ...
```
