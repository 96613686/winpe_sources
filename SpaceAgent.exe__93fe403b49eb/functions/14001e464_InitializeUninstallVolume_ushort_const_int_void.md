# InitializeUninstallVolume(ushort const *,int,void * *)

- ea: `0x14001e464`
- end: `0x14001e719`
- name: `?InitializeUninstallVolume@@YAHPEBGHPEAPEAX@Z`
- size: `693`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, reparse_path, installer_update`

## callers

- `0x14001a530`

## callees

- `0x1400027fc`
- `0x140008190`
- `0x14001d6f4`
- `0x14001d738`
- `0x14001e1dc`
- `0x14001e464`
- `0x14001e720`
- `0x14001e808`
- `0x14001eaa4`
- `0x14001eb94`
- `0x14001edc0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14001e6a4`
- `KERNEL32!CloseHandle` at `0x14001e6a4`
- `KERNEL32!HeapAlloc` at `0x14001e4af`
- `KERNEL32!HeapAlloc` at `0x14001e51f`
- `KERNEL32!HeapAlloc` at `0x14001e4af`
- `KERNEL32!HeapAlloc` at `0x14001e51f`
- `KERNEL32!HeapFree` at `0x14001e6d6`
- `KERNEL32!HeapFree` at `0x14001e6d6`
- `KERNEL32!GetProcessHeap` at `0x14001e495`
- `KERNEL32!GetProcessHeap` at `0x14001e495`
- `KERNEL32!SetLastError` at `0x14001e4c0`
- `KERNEL32!SetLastError` at `0x14001e55c`
- `KERNEL32!SetLastError` at `0x14001e6e9`
- `KERNEL32!SetLastError` at `0x14001e4c0`
- `KERNEL32!SetLastError` at `0x14001e55c`
- `KERNEL32!SetLastError` at `0x14001e6e9`
- `KERNEL32!GetLastError` at `0x14001e4c6`
- `KERNEL32!GetLastError` at `0x14001e57a`
- `KERNEL32!GetLastError` at `0x14001e58d`
- `KERNEL32!GetLastError` at `0x14001e657`
- `KERNEL32!GetLastError` at `0x14001e68d`
- `KERNEL32!GetLastError` at `0x14001e4c6`
- `KERNEL32!GetLastError` at `0x14001e57a`
- `KERNEL32!GetLastError` at `0x14001e58d`
- `KERNEL32!GetLastError` at `0x14001e657`
- `KERNEL32!GetLastError` at `0x14001e68d`
- `KERNEL32!DeviceIoControl` at `0x14001e684`
- `KERNEL32!DeviceIoControl` at `0x14001e684`
- `KERNEL32!CreateFileW` at `0x14001e645`
- `KERNEL32!CreateFileW` at `0x14001e645`

## pseudocode

```c
__int64 __fastcall InitializeUninstallVolume(const unsigned __int16 *a1, __int64 a2, void **a3)
{
  unsigned int VolumeIdentifierFromPath; // r15d
  char *v5; // rax
  LPVOID *v6; // r13
  DWORD LastError; // r12d
  LPVOID *v8; // rdi
  unsigned int *v9; // r14
  _QWORD *v10; // rbx
  HANDLE *v11; // rsi
  int v12; // eax
  DWORD v13; // ecx
  unsigned __int64 v14; // r15
  unsigned __int16 *v15; // rax
  HANDLE FileW; // rax
  unsigned __int64 v18; // [rsp+40h] [rbp-79h] BYREF
  HANDLE hHeap; // [rsp+48h] [rbp-71h]
  void **v20; // [rsp+50h] [rbp-69h]
  WCHAR FileName[48]; // [rsp+60h] [rbp-59h] BYREF
  int v22; // [rsp+C0h] [rbp+7h]

  v20 = a3;
  VolumeIdentifierFromPath = 0;
  hHeap = GetProcessHeap();
  v18 = 0;
  v5 = (char *)HeapAlloc(hHeap, 0, 0x28u);
  v6 = (LPVOID *)v5;
  if ( !v5 )
  {
    SetLastError(8u);
    LastError = GetLastError();
LABEL_33:
    v6 = 0;
    goto LABEL_34;
  }
  v8 = (LPVOID *)(v5 + 8);
  *(_QWORD *)v5 = 0;
  v9 = (unsigned int *)(v5 + 16);
  *((_QWORD *)v5 + 1) = 0;
  v10 = v5 + 24;
  *((_DWORD *)v5 + 4) = 0;
  v11 = (HANDLE *)(v5 + 32);
  *((_QWORD *)v5 + 3) = 0;
  *((_QWORD *)v5 + 4) = -1;
  v12 = StringCchLengthW(a1, 0x8000u, &v18);
  v13 = v12;
  if ( v12 < 0 )
    goto LABEL_8;
  v14 = v18 + 1;
  v15 = (unsigned __int16 *)HeapAlloc(hHeap, 0, 2 * (v18 + 1));
  *v6 = v15;
  if ( !v15 )
  {
    VolumeIdentifierFromPath = 0;
    v13 = 8;
LABEL_10:
    SetLastError(v13);
LABEL_22:
    LastError = GetLastError();
LABEL_25:
    if ( *v11 != (HANDLE)-1LL )
      CloseHandle(*v11);
    if ( *v10 )
      AbortUninstallVolume_FreeMountPoints(*v9);
    if ( *v8 )
      AbortUninstallVolume_FreeAccessPaths(*v8);
    if ( *v6 )
      HeapFree(hHeap, 0, *v6);
    goto LABEL_33;
  }
  v12 = StringCchCopyW(v15, v14, a1);
  v13 = v12;
  if ( v12 < 0 )
  {
    VolumeIdentifierFromPath = 0;
LABEL_8:
    if ( (v12 & 0x1FFF0000) == 0x70000 )
      v13 = (unsigned __int16)v13;
    goto LABEL_10;
  }
  VolumeIdentifierFromPath = GetVolumeIdentifierFromPath(a1, FileName);
  if ( VolumeIdentifierFromPath )
  {
    LODWORD(v18) = 0;
    VolumeIdentifierFromPath = InitializeUninstallVolume_IsVolumeHidden(a1);
    if ( VolumeIdentifierFromPath )
    {
      if ( !(_DWORD)v18 )
      {
        LODWORD(v18) = 0;
        v22 = 92;
        VolumeIdentifierFromPath = InitializeUninstallVolume_GetAccessPaths(FileName);
        if ( VolumeIdentifierFromPath )
        {
          VolumeIdentifierFromPath = InitializeUninstallVolume_IsVolumeRaw(FileName, &v18);
          if ( VolumeIdentifierFromPath )
          {
            if ( !(_DWORD)v18 )
            {
              VolumeIdentifierFromPath = InitializeUninstallVolume_GetMountPoints(FileName);
              if ( VolumeIdentifierFromPath )
              {
                LOWORD(v22) = 0;
                FileW = CreateFileW(FileName, 0xC0000000, 3u, 0, 3u, 0, 0);
                *v11 = FileW;
                if ( FileW == (HANDLE)-1LL )
                {
                  VolumeIdentifierFromPath = 0;
                  goto LABEL_22;
                }
                VolumeIdentifierFromPath = DeviceIoControl(FileW, 0x90018u, 0, 0, 0, 0, 0, 0);
              }
            }
          }
        }
      }
    }
  }
  else if ( GetLastError() == 2 )
  {
    VolumeIdentifierFromPath = 1;
    LastError = GetLastError();
    goto LABEL_34;
  }
  LastError = GetLastError();
  if ( !VolumeIdentifierFromPath )
    goto LABEL_25;
LABEL_34:
  *v20 = v6;
  SetLastError(LastError);
  return VolumeIdentifierFromPath;
}

```

## disassembly

```asm
0x14001e464  mov     [rsp-8+arg_8], rbx
0x14001e469  push    rbp
0x14001e46a  push    rsi
0x14001e46b  push    rdi
0x14001e46c  push    r12
0x14001e46e  push    r13
0x14001e470  push    r14
0x14001e472  push    r15
0x14001e474  lea     rbp, [rsp-27h]
0x14001e479  sub     rsp, 0E0h
0x14001e480  mov     rax, cs:__security_cookie
0x14001e487  xor     rax, rsp
0x14001e48a  mov     [rbp+57h+var_40], rax
0x14001e48e  mov     [rbp+57h+var_C0], r8
0x14001e492  mov     r12, rcx
0x14001e495  call    cs:__imp_GetProcessHeap
0x14001e49b  xor     r15d, r15d
0x14001e49e  xor     edx, edx; dwFlags
0x14001e4a0  mov     rcx, rax; hHeap
0x14001e4a3  mov     [rbp+57h+hHeap], rax
0x14001e4a7  mov     [rbp+57h+var_D0], r15
0x14001e4ab  lea     r8d, [r15+28h]; dwBytes
0x14001e4af  call    cs:__imp_HeapAlloc
0x14001e4b5  mov     r13, rax
0x14001e4b8  test    rax, rax
0x14001e4bb  jnz     short loc_14001E4D4
0x14001e4bd  lea     ecx, [rax+8]; dwErrCode
0x14001e4c0  call    cs:__imp_SetLastError
0x14001e4c6  call    cs:__imp_GetLastError
0x14001e4cc  mov     r12d, eax
0x14001e4cf  jmp     loc_14001E6DC
0x14001e4d4  lea     rdi, [rax+8]
0x14001e4d8  mov     [rax], r15
0x14001e4db  lea     r14, [rax+10h]
0x14001e4df  mov     [rdi], r15
0x14001e4e2  lea     rbx, [rax+18h]
0x14001e4e6  mov     [r14], r15d
0x14001e4e9  lea     rsi, [rax+20h]
0x14001e4ed  mov     [rbx], r15
0x14001e4f0  lea     r8, [rbp+57h+var_D0]; unsigned __int64 *
0x14001e4f4  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x14001e4fb  mov     edx, 8000h; unsigned __int64
0x14001e500  mov     rcx, r12; unsigned __int16 *
0x14001e503  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x14001e508  mov     ecx, eax
0x14001e50a  test    eax, eax
0x14001e50c  js      short loc_14001E54D
0x14001e50e  mov     r15, [rbp+57h+var_D0]
0x14001e512  xor     edx, edx; dwFlags
0x14001e514  mov     rcx, [rbp+57h+hHeap]; hHeap
0x14001e518  inc     r15
0x14001e51b  lea     r8, [r15+r15]; dwBytes
0x14001e51f  call    cs:__imp_HeapAlloc
0x14001e525  mov     [r13+0], rax
0x14001e529  test    rax, rax
0x14001e52c  jnz     short loc_14001E536
0x14001e52e  xor     r15d, r15d
0x14001e531  lea     ecx, [rax+8]
0x14001e534  jmp     short loc_14001E55C
0x14001e536  mov     r8, r12; unsigned __int16 *
0x14001e539  mov     rdx, r15; unsigned __int64
0x14001e53c  mov     rcx, rax; unsigned __int16 *
0x14001e53f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14001e544  mov     ecx, eax
0x14001e546  test    eax, eax
0x14001e548  jns     short loc_14001E567
0x14001e54a  xor     r15d, r15d
0x14001e54d  and     eax, 1FFF0000h
0x14001e552  cmp     eax, 70000h
0x14001e557  jnz     short loc_14001E55C
0x14001e559  movzx   ecx, cx; dwErrCode
0x14001e55c  call    cs:__imp_SetLastError
0x14001e562  jmp     loc_14001E657
0x14001e567  lea     rdx, [rbp+57h+FileName]; unsigned __int16 *
0x14001e56b  mov     rcx, r12; unsigned __int16 *
0x14001e56e  call    ?GetVolumeIdentifierFromPath@@YAHPEBGPEAG@Z; GetVolumeIdentifierFromPath(ushort const *,ushort *)
0x14001e573  mov     r15d, eax
0x14001e576  test    eax, eax
0x14001e578  jnz     short loc_14001E59B
0x14001e57a  call    cs:__imp_GetLastError
0x14001e580  cmp     eax, 2
0x14001e583  jnz     loc_14001E68D
0x14001e589  lea     r15d, [rax-1]
0x14001e58d  call    cs:__imp_GetLastError
0x14001e593  mov     r12d, eax
0x14001e596  jmp     loc_14001E6DF
0x14001e59b  lea     rdx, [rbp+57h+var_D0]
0x14001e59f  mov     dword ptr [rbp+57h+var_D0], 0
0x14001e5a6  mov     rcx, r12; DevicePath
0x14001e5a9  call    InitializeUninstallVolume_IsVolumeHidden
0x14001e5ae  xor     r12d, r12d
0x14001e5b1  mov     r15d, eax
0x14001e5b4  test    eax, eax
0x14001e5b6  jz      loc_14001E68D
0x14001e5bc  cmp     dword ptr [rbp+57h+var_D0], r12d
0x14001e5c0  jnz     loc_14001E68D
0x14001e5c6  mov     rdx, rdi
0x14001e5c9  mov     dword ptr [rbp+57h+var_D0], r12d
0x14001e5cd  lea     rcx, [rbp+57h+FileName]; lpszVolumeName
0x14001e5d1  mov     [rbp+57h+var_50], 5Ch ; '\'
0x14001e5d8  call    InitializeUninstallVolume_GetAccessPaths
0x14001e5dd  mov     r15d, eax
0x14001e5e0  test    eax, eax
0x14001e5e2  jz      loc_14001E68D
0x14001e5e8  lea     rdx, [rbp+57h+var_D0]
0x14001e5ec  lea     rcx, [rbp+57h+FileName]
0x14001e5f0  call    InitializeUninstallVolume_IsVolumeRaw
0x14001e5f5  mov     r15d, eax
0x14001e5f8  test    eax, eax
0x14001e5fa  jz      loc_14001E68D
0x14001e600  cmp     dword ptr [rbp+57h+var_D0], r12d
0x14001e604  jnz     loc_14001E68D
0x14001e60a  mov     r8, rbx
0x14001e60d  lea     rcx, [rbp+57h+FileName]; lpszRootPathName
0x14001e611  mov     rdx, r14
0x14001e614  call    InitializeUninstallVolume_GetMountPoints
0x14001e619  mov     r15d, eax
0x14001e61c  test    eax, eax
0x14001e61e  jz      short loc_14001E68D
0x14001e620  mov     [rsp+110h+hTemplateFile], r12; hTemplateFile
0x14001e625  lea     r8d, [r12+3]; dwShareMode
0x14001e62a  mov     [rsp+110h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x14001e62f  lea     rcx, [rbp+57h+FileName]; lpFileName
0x14001e633  xor     r9d, r9d; lpSecurityAttributes
0x14001e636  mov     [rsp+110h+dwCreationDisposition], r8d; dwCreationDisposition
0x14001e63b  mov     edx, 0C0000000h; dwDesiredAccess
0x14001e640  mov     word ptr [rbp+57h+var_50], r12w
0x14001e645  call    cs:__imp_CreateFileW
0x14001e64b  mov     [rsi], rax
0x14001e64e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001e652  jnz     short loc_14001E662
0x14001e654  mov     r15d, r12d
0x14001e657  call    cs:__imp_GetLastError
0x14001e65d  mov     r12d, eax
0x14001e660  jmp     short loc_14001E69B
0x14001e662  mov     [rsp+110h+lpOverlapped], r12; lpOverlapped
0x14001e667  xor     r9d, r9d; nInBufferSize
0x14001e66a  mov     [rsp+110h+hTemplateFile], r12; lpBytesReturned
0x14001e66f  xor     r8d, r8d; lpInBuffer
0x14001e672  mov     [rsp+110h+dwFlagsAndAttributes], r12d; nOutBufferSize
0x14001e677  mov     edx, 90018h; dwIoControlCode
0x14001e67c  mov     rcx, rax; hDevice
0x14001e67f  mov     qword ptr [rsp+110h+dwCreationDisposition], r12; lpOutBuffer
0x14001e684  call    cs:__imp_DeviceIoControl
0x14001e68a  mov     r15d, eax
0x14001e68d  call    cs:__imp_GetLastError
0x14001e693  mov     r12d, eax
0x14001e696  test    r15d, r15d
0x14001e699  jnz     short loc_14001E6DF
0x14001e69b  cmp     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x14001e69f  jz      short loc_14001E6AA
0x14001e6a1  mov     rcx, [rsi]; hObject
0x14001e6a4  call    cs:__imp_CloseHandle
0x14001e6aa  mov     rdx, [rbx]
0x14001e6ad  test    rdx, rdx
0x14001e6b0  jz      short loc_14001E6BA
0x14001e6b2  mov     ecx, [r14]
0x14001e6b5  call    AbortUninstallVolume_FreeMountPoints
0x14001e6ba  mov     rcx, [rdi]; lpMem
0x14001e6bd  test    rcx, rcx
0x14001e6c0  jz      short loc_14001E6C7
0x14001e6c2  call    AbortUninstallVolume_FreeAccessPaths
0x14001e6c7  mov     r8, [r13+0]; lpMem
0x14001e6cb  test    r8, r8
0x14001e6ce  jz      short loc_14001E6DC
0x14001e6d0  mov     rcx, [rbp+57h+hHeap]; hHeap
0x14001e6d4  xor     edx, edx; dwFlags
0x14001e6d6  call    cs:__imp_HeapFree
0x14001e6dc  xor     r13d, r13d
0x14001e6df  mov     rax, [rbp+57h+var_C0]
0x14001e6e3  mov     ecx, r12d; dwErrCode
0x14001e6e6  mov     [rax], r13
0x14001e6e9  call    cs:__imp_SetLastError
0x14001e6ef  mov     eax, r15d
0x14001e6f2  mov     rcx, [rbp+57h+var_40]
0x14001e6f6  xor     rcx, rsp; StackCookie
0x14001e6f9  call    __security_check_cookie
0x14001e6fe  mov     rbx, [rsp+110h+arg_8]
0x14001e706  add     rsp, 0E0h
0x14001e70d  pop     r15
0x14001e70f  pop     r14
0x14001e711  pop     r13
0x14001e713  pop     r12
0x14001e715  pop     rdi
0x14001e716  pop     rsi
0x14001e717  pop     rbp
0x14001e718  retn
```
