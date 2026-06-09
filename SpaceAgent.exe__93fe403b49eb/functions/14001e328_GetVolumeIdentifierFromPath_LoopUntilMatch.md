# GetVolumeIdentifierFromPath_LoopUntilMatch

- ea: `0x14001e328`
- end: `0x14001e45e`
- name: `GetVolumeIdentifierFromPath_LoopUntilMatch`
- size: `310`
- prototype: `__int64 __fastcall(HANDLE hFindVolume)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14001e1dc`

## callees

- `0x14001e328`
- `0x14001edc0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14001e3db`
- `KERNEL32!CloseHandle` at `0x14001e41f`
- `KERNEL32!CloseHandle` at `0x14001e3db`
- `KERNEL32!CloseHandle` at `0x14001e41f`
- `KERNEL32!FindNextVolumeW` at `0x14001e3f7`
- `KERNEL32!FindNextVolumeW` at `0x14001e3f7`
- `KERNEL32!SetLastError` at `0x14001e435`
- `KERNEL32!SetLastError` at `0x14001e435`
- `KERNEL32!GetLastError` at `0x14001e40e`
- `KERNEL32!GetLastError` at `0x14001e42b`
- `KERNEL32!GetLastError` at `0x14001e40e`
- `KERNEL32!GetLastError` at `0x14001e42b`
- `KERNEL32!DeviceIoControl` at `0x14001e3bf`
- `KERNEL32!DeviceIoControl` at `0x14001e3bf`
- `KERNEL32!CreateFileW` at `0x14001e37e`
- `KERNEL32!CreateFileW` at `0x14001e37e`

## pseudocode

```c
__int64 __fastcall GetVolumeIdentifierFromPath_LoopUntilMatch(
        HANDLE hFindVolume,
        unsigned int a2,
        unsigned int a3,
        __int64 a4)
{
  __int64 FileW; // rdi
  unsigned int NextVolumeW; // ebx
  BOOL v10; // eax
  DWORD LastError; // esi
  BOOL v12; // eax
  _QWORD OutBuffer[2]; // [rsp+40h] [rbp-48h] BYREF

  while ( 1 )
  {
    OutBuffer[0] = 0;
    LODWORD(OutBuffer[1]) = 0;
    FileW = (__int64)CreateFileW((LPCWSTR)a4, 0x20000u, 3u, 0, 3u, 0, 0);
    if ( FileW != -1 )
    {
      NextVolumeW = DeviceIoControl((HANDLE)FileW, 0x2D1080u, 0, 0, OutBuffer, 0xCu, 0, 0);
      if ( NextVolumeW )
      {
        if ( *(_QWORD *)((char *)OutBuffer + 4) == __PAIR64__(a3, a2) )
          break;
      }
      v10 = CloseHandle((HANDLE)FileW);
      FileW = -1;
      NextVolumeW = v10;
      if ( !v10 )
        break;
    }
    NextVolumeW = FindNextVolumeW(hFindVolume, (LPWSTR)a4, 0x32u);
    if ( !NextVolumeW )
      break;
    *(_WORD *)(a4 + 96) = 0;
  }
  LastError = GetLastError();
  if ( FileW != -1 )
  {
    v12 = CloseHandle((HANDLE)FileW);
    if ( NextVolumeW )
    {
      NextVolumeW = v12;
      LastError = GetLastError();
    }
  }
  SetLastError(LastError);
  return NextVolumeW;
}

```

## disassembly

```asm
0x14001e328  mov     [rsp+arg_8], rbx
0x14001e32d  push    rbp
0x14001e32e  push    rsi
0x14001e32f  push    rdi
0x14001e330  push    r14
0x14001e332  push    r15
0x14001e334  sub     rsp, 60h
0x14001e338  mov     rax, cs:__security_cookie
0x14001e33f  xor     rax, rsp
0x14001e342  mov     [rsp+88h+var_38], rax
0x14001e347  mov     rsi, r9
0x14001e34a  mov     ebp, r8d
0x14001e34d  mov     r14d, edx
0x14001e350  mov     r15, rcx
0x14001e353  xor     eax, eax
0x14001e355  xor     r9d, r9d; lpSecurityAttributes
0x14001e358  mov     [rsp+88h+hTemplateFile], rax; hTemplateFile
0x14001e35d  mov     edx, 20000h; dwDesiredAccess
0x14001e362  mov     [rsp+88h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x14001e366  mov     rcx, rsi; lpFileName
0x14001e369  mov     qword ptr [rsp+88h+OutBuffer], rax
0x14001e36e  lea     r8d, [rax+3]; dwShareMode
0x14001e372  mov     dword ptr [rsp+88h+OutBuffer+8], eax
0x14001e376  mov     [rsp+88h+dwCreationDisposition], 3; dwCreationDisposition
0x14001e37e  call    cs:__imp_CreateFileW
0x14001e384  mov     rdi, rax
0x14001e387  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001e38b  jz      short loc_14001E3EB
0x14001e38d  mov     [rsp+88h+lpOverlapped], 0; lpOverlapped
0x14001e396  lea     rax, [rsp+88h+OutBuffer]
0x14001e39b  mov     [rsp+88h+hTemplateFile], 0; lpBytesReturned
0x14001e3a4  xor     r9d, r9d; nInBufferSize
0x14001e3a7  mov     [rsp+88h+dwFlagsAndAttributes], 0Ch; nOutBufferSize
0x14001e3af  xor     r8d, r8d; lpInBuffer
0x14001e3b2  mov     edx, 2D1080h; dwIoControlCode
0x14001e3b7  mov     qword ptr [rsp+88h+dwCreationDisposition], rax; lpOutBuffer
0x14001e3bc  mov     rcx, rdi; hDevice
0x14001e3bf  call    cs:__imp_DeviceIoControl
0x14001e3c5  mov     ebx, eax
0x14001e3c7  test    eax, eax
0x14001e3c9  jz      short loc_14001E3D8
0x14001e3cb  cmp     dword ptr [rsp+88h+OutBuffer+4], r14d
0x14001e3d0  jnz     short loc_14001E3D8
0x14001e3d2  cmp     dword ptr [rsp+88h+OutBuffer+8], ebp
0x14001e3d6  jz      short loc_14001E40E
0x14001e3d8  mov     rcx, rdi; hObject
0x14001e3db  call    cs:__imp_CloseHandle
0x14001e3e1  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14001e3e5  mov     ebx, eax
0x14001e3e7  test    eax, eax
0x14001e3e9  jz      short loc_14001E40E
0x14001e3eb  mov     r8d, 32h ; '2'; cchBufferLength
0x14001e3f1  mov     rdx, rsi; lpszVolumeName
0x14001e3f4  mov     rcx, r15; hFindVolume
0x14001e3f7  call    cs:__imp_FindNextVolumeW
0x14001e3fd  mov     ebx, eax
0x14001e3ff  test    eax, eax
0x14001e401  jz      short loc_14001E40E
0x14001e403  xor     eax, eax
0x14001e405  mov     [rsi+60h], ax
0x14001e409  jmp     loc_14001E353
0x14001e40e  call    cs:__imp_GetLastError
0x14001e414  mov     esi, eax
0x14001e416  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x14001e41a  jz      short loc_14001E433
0x14001e41c  mov     rcx, rdi; hObject
0x14001e41f  call    cs:__imp_CloseHandle
0x14001e425  test    ebx, ebx
0x14001e427  jz      short loc_14001E433
0x14001e429  mov     ebx, eax
0x14001e42b  call    cs:__imp_GetLastError
0x14001e431  mov     esi, eax
0x14001e433  mov     ecx, esi; dwErrCode
0x14001e435  call    cs:__imp_SetLastError
0x14001e43b  mov     eax, ebx
0x14001e43d  mov     rcx, [rsp+88h+var_38]
0x14001e442  xor     rcx, rsp; StackCookie
0x14001e445  call    __security_check_cookie
0x14001e44a  mov     rbx, [rsp+88h+arg_8]
0x14001e452  add     rsp, 60h
0x14001e456  pop     r15
0x14001e458  pop     r14
0x14001e45a  pop     rdi
0x14001e45b  pop     rsi
0x14001e45c  pop     rbp
0x14001e45d  retn
```
