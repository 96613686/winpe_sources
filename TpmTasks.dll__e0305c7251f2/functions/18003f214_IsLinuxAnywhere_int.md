# IsLinuxAnywhere(int *)

- ea: `0x18003f214`
- end: `0x18003f650`
- name: `?IsLinuxAnywhere@@YAJPEAH@Z`
- size: `1084`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, installer_update`

## callers

- `0x18003ec28`

## callees

- `0x1800078b0`
- `0x1800078f0`
- `0x1800085b0`
- `0x1800085bc`
- `0x1800085d4`
- `0x18001bd50`
- `0x18001bddc`
- `0x18003c0b8`
- `0x18003f214`
- `0x18003f984`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindNextVolumeW` at `0x18003f53b`
- `api-ms-win-core-file-l1-1-0!FindNextVolumeW` at `0x18003f53b`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x18003f334`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x18003f334`
- `api-ms-win-core-file-l1-1-0!FindFirstVolumeW` at `0x18003f28d`
- `api-ms-win-core-file-l1-1-0!FindFirstVolumeW` at `0x18003f28d`
- `api-ms-win-core-file-l1-1-0!FindVolumeClose` at `0x18003f584`
- `api-ms-win-core-file-l1-1-0!FindVolumeClose` at `0x18003f584`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003f3c4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003f3c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f2a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f435`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f5cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f638`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f2a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f435`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f5cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f638`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f440`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f440`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18003f42d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18003f42d`

## string_xrefs

- `0x18003f612`: `CreateFileW`

## pseudocode

```c
__int64 __fastcall IsLinuxAnywhere(int *a1)
{
  HANDLE FirstVolumeW; // r15
  signed int LastError; // eax
  signed int v4; // edi
  __int64 v5; // rax
  unsigned __int64 v6; // rbx
  DWORD v7; // eax
  DWORD v8; // esi
  HANDLE FileW; // r14
  BOOL v10; // ebx
  signed int v11; // esi
  unsigned __int16 *v12; // rax
  signed int v14; // eax
  int v15; // edi
  unsigned __int16 *v16; // rax
  unsigned __int16 *v17; // [rsp+40h] [rbp-C0h] BYREF
  int v18; // [rsp+48h] [rbp-B8h] BYREF
  DWORD BytesReturned; // [rsp+4Ch] [rbp-B4h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD OutBuffer[8]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE Buf2[112]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR szVolumeName; // [rsp+100h] [rbp+0h] BYREF
  _WORD v24[3]; // [rsp+102h] [rbp+2h] BYREF
  WCHAR DeviceName[260]; // [rsp+108h] [rbp+8h] BYREF
  WCHAR FileName[5]; // [rsp+310h] [rbp+210h] BYREF
  _BYTE v27[518]; // [rsp+31Ah] [rbp+21Ah] BYREF
  WCHAR TargetPath; // [rsp+520h] [rbp+420h] BYREF
  _BYTE v29[14]; // [rsp+522h] [rbp+422h] BYREF
  unsigned __int16 Src[256]; // [rsp+530h] [rbp+430h] BYREF
  unsigned __int16 v31[264]; // [rsp+730h] [rbp+630h] BYREF

  v17 = L"Passed";
  szVolumeName = 0;
  memset_0(v24, 0, 0x206u);
  TargetPath = 0;
  memset_0(v29, 0, 0x206u);
  FirstVolumeW = FindFirstVolumeW(&szVolumeName, 0x104u);
  if ( FirstVolumeW == (HANDLE)-1LL )
  {
    v17 = L"FindFirstVolumeW";
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_33;
  }
  v4 = 0;
  v5 = -1;
  do
    ++v5;
  while ( v24[v5 - 1] );
  while ( 1 )
  {
    if ( szVolumeName != 92 || v24[0] != 92 || v24[1] != 63 || v24[2] != 92 || (v6 = v5 - 1, v24[v6 - 1] != 92) )
    {
      v12 = L"VolumeName";
      v4 = -2147024735;
LABEL_31:
      v17 = v12;
      goto LABEL_32;
    }
    if ( v6 >= 260 )
      _report_rangecheckfailure(&szVolumeName);
    v24[v6 - 1] = 0;
    v7 = QueryDosDeviceW(DeviceName, &TargetPath, 0x104u);
    v24[v6 - 1] = 92;
    v8 = v7;
    if ( !v7 )
      break;
    if ( v7 <= 8 )
    {
      v12 = L"NumCharsDeviceName";
      v4 = -2147024809;
      goto LABEL_31;
    }
    wcscpy(FileName, L"\\\\.\\");
    memset_0(v27, 0, 0x1FEu);
    memcpy_0(&FileName[4], Src, 2LL * (v8 - 8));
    FileW = CreateFileW(FileName, 0x80000000, 3u, 0, 3u, 0, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      v16 = L"CreateFileW";
      goto LABEL_46;
    }
    BytesReturned = 0;
    memset(&Overlapped, 0, sizeof(Overlapped));
    memset_0(OutBuffer, 0, 0x90u);
    v10 = DeviceIoControl(FileW, 0x70048u, 0, 0, OutBuffer, 0x90u, &BytesReturned, &Overlapped);
    v11 = GetLastError();
    CloseHandle(FileW);
    if ( !v10 )
    {
      v17 = L"IOCTL_DISK_GET_PARTITION_INFO_EX";
      if ( v11 <= 0 )
      {
        v4 = v11;
        goto LABEL_32;
      }
      v15 = (unsigned __int16)v11;
LABEL_39:
      v4 = v15 | 0x80070000;
      goto LABEL_32;
    }
    if ( OutBuffer[0] )
    {
      if ( OutBuffer[0] != 1 || memcmp_0(&PARTITION_SYSTEM_GUID, Buf2, 0x10u) )
        goto LABEL_26;
    }
    else if ( !Buf2[1] )
    {
      goto LABEL_26;
    }
    memset_0(v31, 0, 0x208u);
    v4 = StringCchCopyW(v31, 0x104u, L"\\\\.\\");
    if ( v4 < 0 )
      goto LABEL_32;
    v4 = StringCchCatW(v31, 0x104u, Src);
    if ( v4 < 0 )
      goto LABEL_32;
    v4 = StringCchCatW(v31, 0x104u, L"\\EFI");
    if ( v4 < 0 )
      goto LABEL_32;
    v18 = 0;
    v4 = SearchDirectoryForLinuxFiles(v31, &v18, (const unsigned __int16 **)&v17);
    if ( v4 < 0 )
      goto LABEL_32;
    if ( v18 )
    {
      *a1 = v18;
      goto LABEL_32;
    }
LABEL_26:
    if ( !FindNextVolumeW(FirstVolumeW, &szVolumeName, 0x104u) )
    {
      v14 = GetLastError();
      if ( v14 == 18 )
        goto LABEL_32;
      v17 = L"findNextVolumeW";
      if ( v14 <= 0 )
      {
        v4 = v14;
        goto LABEL_32;
      }
      goto LABEL_38;
    }
    v5 = -1;
    do
      ++v5;
    while ( v24[v5 - 1] );
  }
  v16 = L"QueryDosDeviceW";
LABEL_46:
  v17 = v16;
  v14 = GetLastError();
  v4 = v14;
  if ( v14 > 0 )
  {
LABEL_38:
    v15 = (unsigned __int16)v14;
    goto LABEL_39;
  }
LABEL_32:
  FindVolumeClose(FirstVolumeW);
LABEL_33:
  SBServicingLogMessage(
    (wchar_t *)L"Finished IsLinuxAnywhere. hr=%x, linuxFound=%d actionString=%s\n",
    (unsigned int)v4,
    (unsigned int)*a1,
    v17);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18003f214  push    rbp
0x18003f216  push    rbx
0x18003f217  push    rsi
0x18003f218  push    rdi
0x18003f219  push    r12
0x18003f21b  push    r13
0x18003f21d  push    r14
0x18003f21f  push    r15
0x18003f221  lea     rbp, [rsp-858h]
0x18003f229  sub     rsp, 958h
0x18003f230  mov     rax, cs:__security_cookie
0x18003f237  xor     rax, rsp
0x18003f23a  mov     [rbp+890h+var_50], rax
0x18003f241  mov     r12, rcx
0x18003f244  lea     rax, aPassed; "Passed"
0x18003f24b  mov     ebx, 206h
0x18003f250  mov     [rsp+990h+var_950], rax
0x18003f255  xor     r13d, r13d
0x18003f258  lea     rcx, [rbp+890h+var_88E]; void *
0x18003f25c  mov     r8d, ebx; Size
0x18003f25f  mov     [rbp+890h+szVolumeName], r13w
0x18003f264  xor     edx, edx; Val
0x18003f266  call    memset_0
0x18003f26b  mov     r8d, ebx; Size
0x18003f26e  mov     [rbp+890h+TargetPath], r13w
0x18003f276  xor     edx, edx; Val
0x18003f278  lea     rcx, [rbp+890h+var_46E]; void *
0x18003f27f  call    memset_0
0x18003f284  mov     edx, 104h; cchBufferLength
0x18003f289  lea     rcx, [rbp+890h+szVolumeName]; lpszVolumeName
0x18003f28d  call    cs:__imp_FindFirstVolumeW
0x18003f293  mov     r15, rax
0x18003f296  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003f29a  jnz     short loc_18003F2C6
0x18003f29c  lea     rax, aFindfirstvolum; "FindFirstVolumeW"
0x18003f2a3  mov     [rsp+990h+var_950], rax
0x18003f2a8  call    cs:__imp_GetLastError
0x18003f2ae  mov     edi, eax
0x18003f2b0  test    eax, eax
0x18003f2b2  jle     loc_18003F58A
0x18003f2b8  movzx   edi, ax
0x18003f2bb  or      edi, 80070000h
0x18003f2c1  jmp     loc_18003F58A
0x18003f2c6  mov     edi, r13d
0x18003f2c9  lea     rcx, [rbp+890h+szVolumeName]
0x18003f2cd  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003f2d1  inc     rax
0x18003f2d4  cmp     [rcx+rax*2], r13w
0x18003f2d9  jnz     short loc_18003F2D1
0x18003f2db  jmp     loc_18003F55B
0x18003f2e0  cmp     [rbp+890h+var_88E], r14w
0x18003f2e5  jnz     loc_18003F570
0x18003f2eb  cmp     [rbp+890h+var_88C], 3Fh ; '?'
0x18003f2f0  jnz     loc_18003F570
0x18003f2f6  cmp     [rbp+890h+var_88A], r14w
0x18003f2fb  jnz     loc_18003F570
0x18003f301  add     rbx, rbx
0x18003f304  cmp     [rbp+rbx+890h+szVolumeName], r14w
0x18003f30a  jnz     loc_18003F570
0x18003f310  cmp     rbx, 208h
0x18003f317  jnb     loc_18003F64A
0x18003f31d  mov     r8d, 104h; ucchMax
0x18003f323  mov     [rbp+rbx+890h+szVolumeName], r13w
0x18003f329  lea     rdx, [rbp+890h+TargetPath]; lpTargetPath
0x18003f330  lea     rcx, [rbp+890h+DeviceName]; lpDeviceName
0x18003f334  call    cs:__imp_QueryDosDeviceW
0x18003f33a  mov     [rbp+rbx+890h+szVolumeName], r14w
0x18003f340  mov     esi, eax
0x18003f342  test    eax, eax
0x18003f344  jz      loc_18003F62C
0x18003f34a  cmp     eax, 8
0x18003f34d  jbe     loc_18003F61B
0x18003f353  movzx   ecx, word ptr cs:asc_18006FFE8+8; ""
0x18003f35a  xor     edx, edx; Val
0x18003f35c  movsd   xmm0, qword ptr cs:asc_18006FFE8; "\\\\.\\"
0x18003f364  mov     r8d, 1FEh; Size
0x18003f36a  mov     [rbp+890h+var_678], cx
0x18003f371  lea     rcx, [rbp+890h+var_676]; void *
0x18003f378  movsd   qword ptr [rbp+890h+FileName], xmm0
0x18003f380  call    memset_0
0x18003f385  lea     r8d, [rsi-8]
0x18003f389  add     r8, r8; Size
0x18003f38c  lea     rdx, [rbp+890h+Src]; Src
0x18003f393  lea     rcx, [rbp+890h+var_678]; void *
0x18003f39a  call    memcpy_0
0x18003f39f  mov     eax, 3
0x18003f3a4  mov     [rsp+990h+hTemplateFile], r13; hTemplateFile
0x18003f3a9  mov     r8d, eax; dwShareMode
0x18003f3ac  mov     [rsp+990h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x18003f3b1  xor     r9d, r9d; lpSecurityAttributes
0x18003f3b4  mov     [rsp+990h+dwCreationDisposition], eax; dwCreationDisposition
0x18003f3b8  mov     edx, 80000000h; dwDesiredAccess
0x18003f3bd  lea     rcx, [rbp+890h+FileName]; lpFileName
0x18003f3c4  call    cs:__imp_CreateFileW
0x18003f3ca  mov     r14, rax
0x18003f3cd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003f3d1  jz      loc_18003F612
0x18003f3d7  xorps   xmm0, xmm0
0x18003f3da  mov     [rsp+990h+BytesReturned], r13d
0x18003f3df  mov     ebx, 90h
0x18003f3e4  lea     rcx, [rsp+990h+OutBuffer]; void *
0x18003f3e9  mov     r8d, ebx; Size
0x18003f3ec  xor     edx, edx; Val
0x18003f3ee  movups  xmmword ptr [rsp+990h+Overlapped.Internal], xmm0
0x18003f3f3  movups  xmmword ptr [rsp+990h+Overlapped.10h], xmm0
0x18003f3f8  call    memset_0
0x18003f3fd  lea     rax, [rsp+990h+Overlapped]
0x18003f402  xor     r9d, r9d; nInBufferSize
0x18003f405  mov     [rsp+990h+lpOverlapped], rax; lpOverlapped
0x18003f40a  xor     r8d, r8d; lpInBuffer
0x18003f40d  lea     rax, [rsp+990h+BytesReturned]
0x18003f412  mov     edx, 70048h; dwIoControlCode
0x18003f417  mov     [rsp+990h+hTemplateFile], rax; lpBytesReturned
0x18003f41c  mov     rcx, r14; hDevice
0x18003f41f  lea     rax, [rsp+990h+OutBuffer]
0x18003f424  mov     [rsp+990h+dwFlagsAndAttributes], ebx; nOutBufferSize
0x18003f428  mov     qword ptr [rsp+990h+dwCreationDisposition], rax; lpOutBuffer
0x18003f42d  call    cs:__imp_DeviceIoControl
0x18003f433  mov     ebx, eax
0x18003f435  call    cs:__imp_GetLastError
0x18003f43b  mov     rcx, r14; hObject
0x18003f43e  mov     esi, eax
0x18003f440  call    cs:__imp_CloseHandle
0x18003f446  test    ebx, ebx
0x18003f448  jz      loc_18003F5F6
0x18003f44e  mov     eax, [rsp+990h+OutBuffer]
0x18003f452  test    eax, eax
0x18003f454  jnz     short loc_18003F462
0x18003f456  cmp     [rbp+890h+var_8FF], r13b
0x18003f45a  jz      loc_18003F52E
0x18003f460  jmp     short loc_18003F487
0x18003f462  cmp     eax, 1
0x18003f465  jnz     loc_18003F52E
0x18003f46b  lea     r8d, [rax+0Fh]; Size
0x18003f46f  lea     rdx, [rbp+890h+Buf2]; Buf2
0x18003f473  lea     rcx, PARTITION_SYSTEM_GUID; Buf1
0x18003f47a  call    memcmp_0
0x18003f47f  test    eax, eax
0x18003f481  jnz     loc_18003F52E
0x18003f487  xor     edx, edx; Val
0x18003f489  lea     rcx, [rbp+890h+var_260]; void *
0x18003f490  mov     r8d, 208h; Size
0x18003f496  call    memset_0
0x18003f49b  lea     r8, asc_18006FFE8; "\\\\.\\"
0x18003f4a2  mov     edx, 104h; unsigned __int64
0x18003f4a7  lea     rcx, [rbp+890h+var_260]; unsigned __int16 *
0x18003f4ae  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003f4b3  mov     edi, eax
0x18003f4b5  test    eax, eax
0x18003f4b7  js      loc_18003F581
0x18003f4bd  lea     r8, [rbp+890h+Src]; unsigned __int16 *
0x18003f4c4  mov     edx, 104h; unsigned __int64
0x18003f4c9  lea     rcx, [rbp+890h+var_260]; unsigned __int16 *
0x18003f4d0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003f4d5  mov     edi, eax
0x18003f4d7  test    eax, eax
0x18003f4d9  js      loc_18003F581
0x18003f4df  lea     r8, aEfi_0; "\\EFI"
0x18003f4e6  mov     edx, 104h; unsigned __int64
0x18003f4eb  lea     rcx, [rbp+890h+var_260]; unsigned __int16 *
0x18003f4f2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003f4f7  mov     edi, eax
0x18003f4f9  test    eax, eax
0x18003f4fb  js      loc_18003F581
0x18003f501  lea     r8, [rsp+990h+var_950]; unsigned __int16 **
0x18003f506  mov     [rsp+990h+var_948], r13d
0x18003f50b  lea     rdx, [rsp+990h+var_948]; int *
0x18003f510  lea     rcx, [rbp+890h+var_260]; unsigned __int16 *
0x18003f517  call    ?SearchDirectoryForLinuxFiles@@YAJPEBGPEAHPEAPEBG@Z; SearchDirectoryForLinuxFiles(ushort const *,int *,ushort const * *)
0x18003f51c  mov     edi, eax
0x18003f51e  test    eax, eax
0x18003f520  js      short loc_18003F581
0x18003f522  mov     eax, [rsp+990h+var_948]
0x18003f526  test    eax, eax
0x18003f528  jnz     loc_18003F5C6
0x18003f52e  mov     r8d, 104h; cchBufferLength
0x18003f534  lea     rdx, [rbp+890h+szVolumeName]; lpszVolumeName
0x18003f538  mov     rcx, r15; hFindVolume
0x18003f53b  call    cs:__imp_FindNextVolumeW
0x18003f541  test    eax, eax
0x18003f543  jz      loc_18003F5CC
0x18003f549  lea     rcx, [rbp+890h+szVolumeName]
0x18003f54d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003f551  inc     rax
0x18003f554  cmp     [rcx+rax*2], r13w
0x18003f559  jnz     short loc_18003F551
0x18003f55b  mov     r14d, 5Ch ; '\'
0x18003f561  lea     rbx, [rax-1]
0x18003f565  cmp     [rbp+890h+szVolumeName], r14w
0x18003f56a  jz      loc_18003F2E0
0x18003f570  lea     rax, aVolumename; "VolumeName"
0x18003f577  mov     edi, 800700A1h
0x18003f57c  mov     [rsp+990h+var_950], rax
0x18003f581  mov     rcx, r15; hFindVolume
0x18003f584  call    cs:__imp_FindVolumeClose
0x18003f58a  mov     r9, [rsp+990h+var_950]
0x18003f58f  lea     rcx, aFinishedIslinu; "Finished IsLinuxAnywhere. hr=%x, linuxF"...
0x18003f596  mov     r8d, [r12]
0x18003f59a  mov     edx, edi
0x18003f59c  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003f5a1  mov     eax, edi
0x18003f5a3  mov     rcx, [rbp+890h+var_50]
0x18003f5aa  xor     rcx, rsp; StackCookie
0x18003f5ad  call    __security_check_cookie
0x18003f5b2  add     rsp, 958h
0x18003f5b9  pop     r15
0x18003f5bb  pop     r14
0x18003f5bd  pop     r13
0x18003f5bf  pop     r12
0x18003f5c1  pop     rdi
0x18003f5c2  pop     rsi
0x18003f5c3  pop     rbx
0x18003f5c4  pop     rbp
0x18003f5c5  retn
0x18003f5c6  mov     [r12], eax
0x18003f5ca  jmp     short loc_18003F581
0x18003f5cc  call    cs:__imp_GetLastError
0x18003f5d2  cmp     eax, 12h
0x18003f5d5  jz      short loc_18003F581
0x18003f5d7  lea     rcx, aFindnextvolume; "findNextVolumeW"
0x18003f5de  mov     [rsp+990h+var_950], rcx
0x18003f5e3  test    eax, eax
0x18003f5e5  jg      short loc_18003F5EB
0x18003f5e7  mov     edi, eax
0x18003f5e9  jmp     short loc_18003F581
0x18003f5eb  movzx   edi, ax
0x18003f5ee  or      edi, 80070000h
0x18003f5f4  jmp     short loc_18003F581
0x18003f5f6  lea     rax, aIoctlDiskGetPa; "IOCTL_DISK_GET_PARTITION_INFO_EX"
0x18003f5fd  mov     [rsp+990h+var_950], rax
0x18003f602  test    esi, esi
0x18003f604  jg      short loc_18003F60D
0x18003f606  mov     edi, esi
0x18003f608  jmp     loc_18003F581
0x18003f60d  movzx   edi, si
0x18003f610  jmp     short loc_18003F5EE
0x18003f612  lea     rax, aCreatefilew; "CreateFileW"
0x18003f619  jmp     short loc_18003F633
0x18003f61b  lea     rax, aNumcharsdevice; "NumCharsDeviceName"
0x18003f622  mov     edi, 80070057h
0x18003f627  jmp     loc_18003F57C
0x18003f62c  lea     rax, aQuerydosdevice; "QueryDosDeviceW"
0x18003f633  mov     [rsp+990h+var_950], rax
0x18003f638  call    cs:__imp_GetLastError
0x18003f63e  mov     edi, eax
0x18003f640  test    eax, eax
0x18003f642  jle     loc_18003F581
0x18003f648  jmp     short loc_18003F5EB
0x18003f64a  call    __report_rangecheckfailure
```
