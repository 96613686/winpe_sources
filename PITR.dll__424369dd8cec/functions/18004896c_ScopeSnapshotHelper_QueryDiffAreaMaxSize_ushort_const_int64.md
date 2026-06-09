# ScopeSnapshotHelper::QueryDiffAreaMaxSize(ushort const *,__int64 *)

- ea: `0x18004896c`
- end: `0x180048b27`
- name: `?QueryDiffAreaMaxSize@ScopeSnapshotHelper@@SAJPEBGPEA_J@Z`
- size: `443`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path`

## callers

- `0x180048564`

## callees

- `0x1800023d8`
- `0x18004896c`
- `0x180050300`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180048a66`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180048a66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800489c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048ac4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800489c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048ac4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048af5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048af5`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180048aba`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180048aba`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1800489b6`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1800489b6`

## pseudocode

```c
__int64 __fastcall ScopeSnapshotHelper::QueryDiffAreaMaxSize(const unsigned __int16 *a1, __int64 *a2)
{
  signed int LastError; // eax
  unsigned int v4; // ebx
  __int64 v5; // rax
  unsigned __int64 v6; // rcx
  HANDLE FileW; // rsi
  signed int v8; // eax
  __int64 v9; // rcx
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  __int128 OutBuffer; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v13; // [rsp+58h] [rbp-A8h]
  WCHAR FileName[8]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v15; // [rsp+70h] [rbp-90h]
  __int128 v16; // [rsp+80h] [rbp-80h]
  __int128 v17; // [rsp+90h] [rbp-70h]
  __int128 v18; // [rsp+A0h] [rbp-60h]
  __int128 v19; // [rsp+B0h] [rbp-50h]
  int v20; // [rsp+C0h] [rbp-40h]
  WCHAR szVolumeName[8]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v22; // [rsp+E0h] [rbp-20h]
  __int128 v23; // [rsp+F0h] [rbp-10h]
  __int128 v24; // [rsp+100h] [rbp+0h]
  __int128 v25; // [rsp+110h] [rbp+10h]
  __int128 v26; // [rsp+120h] [rbp+20h]
  int v27; // [rsp+130h] [rbp+30h]

  v13 = 0;
  OutBuffer = 0;
  BytesReturned = 0;
  if ( !GetVolumeNameForVolumeMountPointW(a1, szVolumeName, 0x32u) )
    goto LABEL_2;
  *(_OWORD *)FileName = *(_OWORD *)szVolumeName;
  v15 = v22;
  v16 = v23;
  v17 = v24;
  v20 = v27;
  v5 = -1;
  v18 = v25;
  v19 = v26;
  do
    ++v5;
  while ( FileName[v5] );
  v6 = 2 * v5 - 2;
  if ( v6 >= 0x64 )
    _report_rangecheckfailure();
  *(WCHAR *)((char *)FileName + v6) = 0;
  FileW = CreateFileW(FileName, 0xC0000000, 3u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
LABEL_2:
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    v13 = 0;
    *a2 = 0;
    OutBuffer = 0;
    if ( DeviceIoControl(FileW, 0x53002Cu, 0, 0, &OutBuffer, 0x18u, &BytesReturned, 0) )
    {
      v9 = v13;
      v4 = 0;
      *a2 = v13;
      if ( !v9 )
        *a2 = -1;
    }
    else
    {
      v8 = GetLastError();
      v4 = v8;
      if ( v8 > 0 )
        v4 = (unsigned __int16)v8 | 0x80070000;
    }
    CloseHandle(FileW);
  }
  return v4;
}

```

## disassembly

```asm
0x18004896c  mov     [rsp-8+arg_10], rbx
0x180048971  mov     [rsp-8+arg_18], rsi
0x180048976  push    rbp
0x180048977  push    rdi
0x180048978  push    r14
0x18004897a  lea     rbp, [rsp-50h]
0x18004897f  sub     rsp, 150h
0x180048986  mov     rax, cs:__security_cookie
0x18004898d  xor     rax, rsp
0x180048990  mov     [rbp+60h+var_20], rax
0x180048994  xor     eax, eax
0x180048996  mov     rdi, rdx
0x180048999  xorps   xmm0, xmm0
0x18004899c  mov     [rsp+160h+var_108], rax
0x1800489a1  xor     r14d, r14d
0x1800489a4  lea     rdx, [rbp+60h+szVolumeName]; lpszVolumeName
0x1800489a8  movups  [rsp+160h+OutBuffer], xmm0
0x1800489ad  lea     r8d, [rax+32h]; cchBufferLength
0x1800489b1  mov     [rsp+160h+BytesReturned], r14d
0x1800489b6  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1800489bc  test    eax, eax
0x1800489be  jnz     short loc_1800489DE
0x1800489c0  call    cs:__imp_GetLastError
0x1800489c6  mov     ebx, eax
0x1800489c8  test    eax, eax
0x1800489ca  jle     loc_180048AFB
0x1800489d0  movzx   ebx, ax
0x1800489d3  or      ebx, 80070000h
0x1800489d9  jmp     loc_180048AFB
0x1800489de  movaps  xmm0, xmmword ptr [rbp+60h+szVolumeName]
0x1800489e2  lea     rcx, [rsp+160h+FileName]
0x1800489e7  movaps  xmm1, [rbp+60h+var_80]
0x1800489eb  mov     eax, [rbp+60h+var_30]
0x1800489ee  movaps  xmmword ptr [rsp+160h+FileName], xmm0
0x1800489f3  movaps  xmm0, [rbp+60h+var_70]
0x1800489f7  movaps  [rsp+160h+var_F0], xmm1
0x1800489fc  movaps  xmm1, [rbp+60h+var_60]
0x180048a00  movaps  [rbp+60h+var_E0], xmm0
0x180048a04  movaps  xmm0, [rbp+60h+var_50]
0x180048a08  movaps  [rbp+60h+var_D0], xmm1
0x180048a0c  movaps  xmm1, [rbp+60h+var_40]
0x180048a10  mov     [rbp+60h+var_A0], eax
0x180048a13  or      rax, 0FFFFFFFFFFFFFFFFh
0x180048a17  movaps  [rbp+60h+var_C0], xmm0
0x180048a1b  movaps  [rbp+60h+var_B0], xmm1
0x180048a1f  inc     rax
0x180048a22  cmp     [rcx+rax*2], r14w
0x180048a27  jnz     short loc_180048A1F
0x180048a29  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x180048a31  cmp     rcx, 64h ; 'd'
0x180048a35  jnb     loc_180048B21
0x180048a3b  mov     [rsp+rcx+160h+FileName], r14w
0x180048a41  mov     r8d, 3; dwShareMode
0x180048a47  mov     [rsp+160h+hTemplateFile], r14; hTemplateFile
0x180048a4c  lea     rcx, [rsp+160h+FileName]; lpFileName
0x180048a51  mov     [rsp+160h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180048a59  xor     r9d, r9d; lpSecurityAttributes
0x180048a5c  mov     edx, 0C0000000h; dwDesiredAccess
0x180048a61  mov     [rsp+160h+dwCreationDisposition], r8d; dwCreationDisposition
0x180048a66  call    cs:__imp_CreateFileW
0x180048a6c  mov     rsi, rax
0x180048a6f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180048a73  jz      loc_1800489C0
0x180048a79  xor     eax, eax
0x180048a7b  mov     [rsp+160h+lpOverlapped], r14; lpOverlapped
0x180048a80  mov     [rsp+160h+var_108], rax
0x180048a85  xorps   xmm0, xmm0
0x180048a88  lea     rax, [rsp+160h+BytesReturned]
0x180048a8d  mov     [rdi], r14
0x180048a90  mov     [rsp+160h+hTemplateFile], rax; lpBytesReturned
0x180048a95  xor     r9d, r9d; nInBufferSize
0x180048a98  lea     rax, [rsp+160h+OutBuffer]
0x180048a9d  mov     [rsp+160h+dwFlagsAndAttributes], 18h; nOutBufferSize
0x180048aa5  xor     r8d, r8d; lpInBuffer
0x180048aa8  mov     qword ptr [rsp+160h+dwCreationDisposition], rax; lpOutBuffer
0x180048aad  mov     edx, 53002Ch; dwIoControlCode
0x180048ab2  mov     rcx, rsi; hDevice
0x180048ab5  movups  [rsp+160h+OutBuffer], xmm0
0x180048aba  call    cs:__imp_DeviceIoControl
0x180048ac0  test    eax, eax
0x180048ac2  jnz     short loc_180048ADB
0x180048ac4  call    cs:__imp_GetLastError
0x180048aca  mov     ebx, eax
0x180048acc  test    eax, eax
0x180048ace  jle     short loc_180048AF2
0x180048ad0  movzx   ebx, ax
0x180048ad3  or      ebx, 80070000h
0x180048ad9  jmp     short loc_180048AF2
0x180048adb  mov     rcx, [rsp+160h+var_108]
0x180048ae0  mov     ebx, r14d
0x180048ae3  mov     [rdi], rcx
0x180048ae6  test    rcx, rcx
0x180048ae9  jnz     short loc_180048AF2
0x180048aeb  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x180048af2  mov     rcx, rsi; hObject
0x180048af5  call    cs:__imp_CloseHandle
0x180048afb  mov     eax, ebx
0x180048afd  mov     rcx, [rbp+60h+var_20]
0x180048b01  xor     rcx, rsp; StackCookie
0x180048b04  call    __security_check_cookie
0x180048b09  lea     r11, [rsp+160h+var_10]
0x180048b11  mov     rbx, [r11+30h]
0x180048b15  mov     rsi, [r11+38h]
0x180048b19  mov     rsp, r11
0x180048b1c  pop     r14
0x180048b1e  pop     rdi
0x180048b1f  pop     rbp
0x180048b20  retn
0x180048b21  call    __report_rangecheckfailure
```
