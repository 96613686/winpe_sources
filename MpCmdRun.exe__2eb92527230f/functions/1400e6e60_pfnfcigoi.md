# pfnfcigoi

- ea: `0x1400e6e60`
- end: `0x1400e7085`
- name: `pfnfcigoi`
- size: `549`
- prototype: `INT_PTR __cdecl(LPSTR pszName, USHORT *pdate, USHORT *ptime, USHORT *pattribs, int *err, void *pv)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x140012e84`
- `0x140036780`
- `0x14004edcc`
- `0x14005d344`
- `0x1400e6e60`
- `0x1401203c0`

## import_xrefs

- `MpClient!MpFreeMemory` at `0x1400e6f50`
- `MpClient!MpFreeMemory` at `0x1400e707a`
- `MpClient!MpFreeMemory` at `0x1400e6f50`
- `MpClient!MpFreeMemory` at `0x1400e707a`
- `MpClient!MpAllocMemory` at `0x1400e6f09`
- `MpClient!MpAllocMemory` at `0x1400e6f09`
- `KERNEL32!CloseHandle` at `0x1400e701c`
- `KERNEL32!CloseHandle` at `0x1400e7068`
- `KERNEL32!CloseHandle` at `0x1400e701c`
- `KERNEL32!CloseHandle` at `0x1400e7068`
- `KERNEL32!MultiByteToWideChar` at `0x1400e6ee8`
- `KERNEL32!MultiByteToWideChar` at `0x1400e6f3b`
- `KERNEL32!MultiByteToWideChar` at `0x1400e6ee8`
- `KERNEL32!MultiByteToWideChar` at `0x1400e6f3b`
- `KERNEL32!CreateFileW` at `0x1400e6fb0`
- `KERNEL32!CreateFileW` at `0x1400e6fb0`
- `KERNEL32!GetFileAttributesW` at `0x1400e6ffd`
- `KERNEL32!GetFileAttributesW` at `0x1400e6ffd`
- `KERNEL32!GetFileInformationByHandle` at `0x1400e6fc9`
- `KERNEL32!GetFileInformationByHandle` at `0x1400e6fc9`
- `KERNEL32!FileTimeToLocalFileTime` at `0x1400e6fe2`
- `KERNEL32!FileTimeToLocalFileTime` at `0x1400e6fe2`
- `KERNEL32!FileTimeToDosDateTime` at `0x1400e6ff4`
- `KERNEL32!FileTimeToDosDateTime` at `0x1400e6ff4`

## pseudocode

```c
INT_PTR __fastcall pfnfcigoi(const CHAR *pszName, USHORT *pdate, USHORT *ptime, USHORT *pattribs, int *err)
{
  int v6; // ebx
  const WCHAR *v7; // rdi
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // rcx
  int cchWideChar; // r15d
  int v12; // r14d
  __int64 v13; // r14
  __int64 v14; // rax
  WCHAR *lpWideCharStr; // rsi
  __int64 v16; // rdx
  __int64 v17; // rcx
  HANDLE FileW; // rax
  void *v20; // rsi
  DWORD FileAttributesW; // eax
  USHORT v22; // ax
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  LPWORD lpFatTime; // [rsp+50h] [rbp-49h] BYREF
  struct _FILETIME LocalFileTime; // [rsp+58h] [rbp-41h] BYREF
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+60h] [rbp-39h] BYREF

  lpFatTime = ptime;
  *err = 0;
  v6 = -1;
  *pdate = 0;
  v7 = 0;
  *ptime = 0;
  *pattribs = 0;
  LocalFileTime = 0;
  memset(&FileInformation, 0, sizeof(FileInformation));
  if ( !pszName )
    goto LABEL_8;
  v8 = MultiByteToWideChar(0xFDE9u, 0, pszName, -1, 0, 0);
  cchWideChar = v8;
  if ( v8 )
  {
    v13 = 2LL * (unsigned int)(v8 + 1);
    v14 = MpAllocMemory(v13);
    lpWideCharStr = (WCHAR *)v14;
    if ( !v14 )
    {
LABEL_8:
      *err = 8;
      return v6;
    }
    sub_1401203C0(v14, 0, v13);
    if ( MultiByteToWideChar(0xFDE9u, 0, pszName, -1, lpWideCharStr, cchWideChar) )
    {
      v7 = lpWideCharStr;
      goto LABEL_11;
    }
    v12 = sub_140012E84(v17, v16);
    MpFreeMemory(lpWideCharStr);
  }
  else
  {
    v12 = sub_140012E84(v10, v9);
  }
  if ( v12 < 0 )
    goto LABEL_8;
LABEL_11:
  FileW = CreateFileW(v7, 0x80000000, 3u, 0, 3u, 0x8000080u, 0);
  v20 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    if ( GetFileInformationByHandle(FileW, &FileInformation) )
    {
      FileTimeToLocalFileTime(&FileInformation.ftLastWriteTime, &LocalFileTime);
      FileTimeToDosDateTime(&LocalFileTime, pdate, lpFatTime);
      FileAttributesW = GetFileAttributesW(v7);
      if ( FileAttributesW == -1 )
        v22 = 0;
      else
        v22 = FileAttributesW & 0x27;
      *pattribs = v22;
      CloseHandle(v20);
      LODWORD(lpFatTime) = 0;
      if ( (unsigned int)sub_14005D344((_DWORD)v7, 0x8000, 64, 256, (__int64)&lpFatTime, 0)
        || (v6 = (int)lpFatTime, (int)lpFatTime < 0) )
      {
        *err = *(_DWORD *)sub_14004EDCC(v24, v23, v25, v26);
      }
    }
    else
    {
      CloseHandle(v20);
    }
  }
  if ( v7 )
    MpFreeMemory(v7);
  return v6;
}

```

## disassembly

```asm
0x1400e6e60  push    rbp
0x1400e6e62  push    rbx
0x1400e6e63  push    rsi
0x1400e6e64  push    rdi
0x1400e6e65  push    r12
0x1400e6e67  push    r13
0x1400e6e69  push    r14
0x1400e6e6b  push    r15
0x1400e6e6d  lea     rbp, [rsp-0Fh]
0x1400e6e72  sub     rsp, 0A8h
0x1400e6e79  mov     rax, cs:__security_cookie
0x1400e6e80  xor     rax, rsp
0x1400e6e83  mov     [rbp+47h+var_48], rax
0x1400e6e87  mov     r12, [rbp+47h+err]
0x1400e6e8b  xor     esi, esi
0x1400e6e8d  xorps   xmm0, xmm0
0x1400e6e90  mov     [rbp+47h+var_98], r9
0x1400e6e94  mov     r13, rcx
0x1400e6e97  mov     [rbp+47h+lpFatTime], r8
0x1400e6e9b  xor     ecx, ecx
0x1400e6e9d  mov     [rbp+47h+lpFatDate], rdx
0x1400e6ea1  mov     [r12], esi
0x1400e6ea5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400e6ea9  mov     [rdx], si
0x1400e6eac  mov     edi, esi
0x1400e6eae  mov     [r8], si
0x1400e6eb2  mov     [r9], si
0x1400e6eb6  mov     [rbp+47h+FileInformation.nFileIndexLow], ecx
0x1400e6eb9  mov     qword ptr [rbp+47h+LocalFileTime.dwLowDateTime], rsi
0x1400e6ebd  movups  xmmword ptr [rbp+47h+FileInformation.dwFileAttributes], xmm0
0x1400e6ec1  movups  xmmword ptr [rbp+47h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x1400e6ec5  movups  xmmword ptr [rbp+47h+FileInformation.nFileSizeHigh], xmm0
0x1400e6ec9  test    r13, r13
0x1400e6ecc  jz      loc_1400E6F5D
0x1400e6ed2  mov     [rsp+0E0h+cchWideChar], esi; cchWideChar
0x1400e6ed6  mov     r9d, ebx; cbMultiByte
0x1400e6ed9  mov     r8, r13; lpMultiByteStr
0x1400e6edc  mov     [rsp+0E0h+lpWideCharStr], rsi; lpWideCharStr
0x1400e6ee1  xor     edx, edx; dwFlags
0x1400e6ee3  mov     ecx, 0FDE9h; CodePage
0x1400e6ee8  call    cs:MultiByteToWideChar
0x1400e6eee  mov     r15d, eax
0x1400e6ef1  test    eax, eax
0x1400e6ef3  jnz     short loc_1400E6EFF
0x1400e6ef5  call    sub_140012E84
0x1400e6efa  mov     r14d, eax
0x1400e6efd  jmp     short loc_1400E6F58
0x1400e6eff  lea     r14d, [rax+1]
0x1400e6f03  add     r14, r14
0x1400e6f06  mov     rcx, r14
0x1400e6f09  call    cs:MpAllocMemory
0x1400e6f0f  mov     rsi, rax
0x1400e6f12  test    rax, rax
0x1400e6f15  jz      short loc_1400E6F5D
0x1400e6f17  mov     r8, r14
0x1400e6f1a  xor     edx, edx
0x1400e6f1c  mov     rcx, rax
0x1400e6f1f  call    sub_1401203C0
0x1400e6f24  mov     r9d, ebx; cbMultiByte
0x1400e6f27  mov     [rsp+0E0h+cchWideChar], r15d; cchWideChar
0x1400e6f2c  mov     r8, r13; lpMultiByteStr
0x1400e6f2f  mov     [rsp+0E0h+lpWideCharStr], rsi; lpWideCharStr
0x1400e6f34  xor     edx, edx; dwFlags
0x1400e6f36  mov     ecx, 0FDE9h; CodePage
0x1400e6f3b  call    cs:MultiByteToWideChar
0x1400e6f41  test    eax, eax
0x1400e6f43  jnz     short loc_1400E6F88
0x1400e6f45  call    sub_140012E84
0x1400e6f4a  mov     rcx, rsi
0x1400e6f4d  mov     r14d, eax
0x1400e6f50  call    cs:__imp_MpFreeMemory
0x1400e6f56  xor     esi, esi
0x1400e6f58  test    r14d, r14d
0x1400e6f5b  jns     short loc_1400E6F8D
0x1400e6f5d  mov     dword ptr [r12], 8
0x1400e6f65  movsxd  rax, ebx
0x1400e6f68  mov     rcx, [rbp+47h+var_48]
0x1400e6f6c  xor     rcx, rsp; StackCookie
0x1400e6f6f  call    __security_check_cookie
0x1400e6f74  add     rsp, 0A8h
0x1400e6f7b  pop     r15
0x1400e6f7d  pop     r14
0x1400e6f7f  pop     r13
0x1400e6f81  pop     r12
0x1400e6f83  pop     rdi
0x1400e6f84  pop     rsi
0x1400e6f85  pop     rbx
0x1400e6f86  pop     rbp
0x1400e6f87  retn
0x1400e6f88  mov     rdi, rsi
0x1400e6f8b  xor     esi, esi
0x1400e6f8d  mov     [rsp+0E0h+hTemplateFile], rsi; hTemplateFile
0x1400e6f92  mov     r8d, 3; dwShareMode
0x1400e6f98  mov     [rsp+0E0h+cchWideChar], 8000080h; dwFlagsAndAttributes
0x1400e6fa0  xor     r9d, r9d; lpSecurityAttributes
0x1400e6fa3  mov     edx, 80000000h; dwDesiredAccess
0x1400e6fa8  mov     dword ptr [rsp+0E0h+lpWideCharStr], r8d; dwCreationDisposition
0x1400e6fad  mov     rcx, rdi; lpFileName
0x1400e6fb0  call    cs:CreateFileW
0x1400e6fb6  mov     rsi, rax
0x1400e6fb9  cmp     rax, rbx
0x1400e6fbc  jz      loc_1400E706E
0x1400e6fc2  lea     rdx, [rbp+47h+FileInformation]; lpFileInformation
0x1400e6fc6  mov     rcx, rax; hFile
0x1400e6fc9  call    cs:GetFileInformationByHandle
0x1400e6fcf  xor     r14d, r14d
0x1400e6fd2  test    eax, eax
0x1400e6fd4  jz      loc_1400E7065
0x1400e6fda  lea     rdx, [rbp+47h+LocalFileTime]; lpLocalFileTime
0x1400e6fde  lea     rcx, [rbp+47h+FileInformation.ftLastWriteTime]; lpFileTime
0x1400e6fe2  call    cs:FileTimeToLocalFileTime
0x1400e6fe8  mov     r8, [rbp+47h+lpFatTime]; lpFatTime
0x1400e6fec  lea     rcx, [rbp+47h+LocalFileTime]; lpFileTime
0x1400e6ff0  mov     rdx, [rbp+47h+lpFatDate]; lpFatDate
0x1400e6ff4  call    cs:FileTimeToDosDateTime
0x1400e6ffa  mov     rcx, rdi; lpFileName
0x1400e6ffd  call    cs:GetFileAttributesW
0x1400e7003  cmp     eax, 0FFFFFFFFh
0x1400e7006  jnz     short loc_1400E700E
0x1400e7008  movzx   eax, r14w
0x1400e700c  jmp     short loc_1400E7012
0x1400e700e  and     ax, 27h
0x1400e7012  mov     rcx, [rbp+47h+var_98]
0x1400e7016  mov     [rcx], ax
0x1400e7019  mov     rcx, rsi; hObject
0x1400e701c  call    cs:__imp_CloseHandle
0x1400e7022  lea     rax, [rbp+47h+lpFatTime]
0x1400e7026  mov     [rsp+0E0h+cchWideChar], r14d
0x1400e702b  mov     edx, 8000h
0x1400e7030  mov     [rsp+0E0h+lpWideCharStr], rax
0x1400e7035  mov     r9d, 100h
0x1400e703b  mov     dword ptr [rbp+47h+lpFatTime], r14d
0x1400e703f  mov     r8d, 40h ; '@'
0x1400e7045  mov     rcx, rdi
0x1400e7048  call    sub_14005D344
0x1400e704d  test    eax, eax
0x1400e704f  jnz     short loc_1400E7058
0x1400e7051  mov     ebx, dword ptr [rbp+47h+lpFatTime]
0x1400e7054  test    ebx, ebx
0x1400e7056  jns     short loc_1400E706E
0x1400e7058  call    sub_14004EDCC
0x1400e705d  mov     ecx, [rax]
0x1400e705f  mov     [r12], ecx
0x1400e7063  jmp     short loc_1400E706E
0x1400e7065  mov     rcx, rsi; hObject
0x1400e7068  call    cs:__imp_CloseHandle
0x1400e706e  test    rdi, rdi
0x1400e7071  jz      loc_1400E6F65
0x1400e7077  mov     rcx, rdi
0x1400e707a  call    cs:__imp_MpFreeMemory
0x1400e7080  jmp     loc_1400E6F65
```
