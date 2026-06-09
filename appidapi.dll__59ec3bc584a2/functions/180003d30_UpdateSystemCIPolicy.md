# UpdateSystemCIPolicy

- ea: `0x180003d30`
- end: `0x180003fcd`
- name: `UpdateSystemCIPolicy`
- size: `669`
- prototype: `__int64 __fastcall(LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001098`
- `0x180003210`
- `0x180003330`
- `0x180003534`
- `0x180003d30`
- `0x1800095c0`

## import_xrefs

- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x180003f91`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x180003f91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f9f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180003e83`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180003e83`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180003e50`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180003e50`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180003dad`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180003dad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ea5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003eb3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ea5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003eb3`
- `ntdll!NtQuerySystemInformation` at `0x180003ed3`
- `ntdll!NtQuerySystemInformation` at `0x180003ed3`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180003f34`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180003f34`

## pseudocode

```c
__int64 __fastcall UpdateSystemCIPolicy(LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite, _DWORD *a3)
{
  DWORD SystemCIPolicyPath; // ebx
  HANDLE FileW; // rax
  void *v9; // rdi
  __int64 v10; // rdx
  signed int SystemBootDir; // edi
  __int64 v12; // r8
  bool v13; // zf
  NTSTATUS v14; // edi
  const WCHAR *p_Block; // rdx
  signed int LastError; // eax
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v18[8]; // [rsp+48h] [rbp-B8h] BYREF
  void *Block; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v20; // [rsp+60h] [rbp-A0h]
  unsigned __int64 v21; // [rsp+68h] [rbp-98h]
  _BYTE v22[8]; // [rsp+70h] [rbp-90h] BYREF
  void *v23; // [rsp+78h] [rbp-88h]
  __int64 v24; // [rsp+88h] [rbp-78h]
  unsigned __int64 v25; // [rsp+90h] [rbp-70h]
  __int128 SystemInformation; // [rsp+98h] [rbp-68h] BYREF
  __int128 v27; // [rsp+A8h] [rbp-58h]
  WCHAR FileName[264]; // [rsp+C0h] [rbp-40h] BYREF

  NumberOfBytesWritten = 0;
  LOWORD(v23) = 0;
  v20 = 0;
  v25 = 7;
  v21 = 7;
  LOWORD(Block) = 0;
  *a3 = 0;
  v24 = 0;
  SystemCIPolicyPath = GetSystemCIPolicyPath(FileName, nNumberOfBytesToWrite);
  if ( !SystemCIPolicyPath )
  {
    if ( !nNumberOfBytesToWrite )
    {
      if ( DeleteFileW(FileName) )
      {
LABEL_4:
        *a3 = 1;
        goto LABEL_5;
      }
LABEL_13:
      SystemCIPolicyPath = GetLastError();
      goto LABEL_5;
    }
    if ( !lpBuffer )
    {
      SystemCIPolicyPath = 87;
      goto LABEL_5;
    }
    FileW = CreateFileW(FileName, 0x40000000u, 0, 0, 2u, 0x80u, 0);
    v9 = FileW;
    if ( FileW == (HANDLE)-1LL )
      goto LABEL_13;
    if ( !WriteFile(FileW, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
    {
      SystemCIPolicyPath = GetLastError();
LABEL_18:
      CloseHandle(v9);
      goto LABEL_5;
    }
    if ( NumberOfBytesWritten != nNumberOfBytesToWrite )
    {
      SystemCIPolicyPath = 38;
      goto LABEL_18;
    }
    CloseHandle(v9);
    SystemInformation = 0;
    v27 = 0;
    if ( NtQuerySystemInformation(SystemBootEnvironmentInformation, &SystemInformation, 0x20u, 0) < 0
      || (_DWORD)v27 != 2 )
    {
      goto LABEL_4;
    }
    SystemBootDir = GetSystemBootDir(v22);
    if ( SystemBootDir < 0 || (SystemBootDir = FormCompleteFilePath(v22, v10, v12, v18), SystemBootDir < 0) )
    {
      v13 = (SystemBootDir & 0xFFFF0000) == -2147024896;
    }
    else
    {
      p_Block = (const WCHAR *)&Block;
      if ( v21 >= 8 )
        p_Block = (const WCHAR *)Block;
      if ( CopyFileExW(FileName, p_Block, 0, 0, 0, 0) )
        goto LABEL_4;
      LastError = GetLastError();
      SystemBootDir = LastError;
      if ( LastError > 0 )
        SystemBootDir = (unsigned __int16)LastError | 0x80070000;
      if ( SystemBootDir >= 0 )
        goto LABEL_4;
      v13 = (SystemBootDir & 0xFFFF0000) == -2147024896;
    }
    if ( v13 )
    {
      SystemCIPolicyPath = (unsigned __int16)SystemBootDir;
    }
    else if ( (SystemBootDir & 0x10000000) != 0 )
    {
      v14 = SystemBootDir & 0xEFFFFFFF;
      if ( v14 < 0 )
      {
        SystemCIPolicyPath = RtlNtStatusToDosErrorNoTeb(v14);
        if ( SystemCIPolicyPath == 317 )
          SystemCIPolicyPath = v14;
      }
      else
      {
        SystemCIPolicyPath = 0;
      }
    }
    else
    {
      SystemCIPolicyPath = SystemBootDir;
    }
  }
LABEL_5:
  if ( v21 >= 8 )
    operator delete(Block);
  v21 = 7;
  v20 = 0;
  LOWORD(Block) = 0;
  if ( v25 >= 8 )
    operator delete(v23);
  return SystemCIPolicyPath;
}

```

## disassembly

```asm
0x180003d30  push    rbp
0x180003d32  push    rbx
0x180003d33  push    rsi
0x180003d34  push    rdi
0x180003d35  push    r13
0x180003d37  push    r14
0x180003d39  push    r15
0x180003d3b  lea     rbp, [rsp-1E0h]
0x180003d43  sub     rsp, 2E0h
0x180003d4a  mov     rax, cs:__security_cookie
0x180003d51  xor     rax, rsp
0x180003d54  mov     [rbp+210h+var_40], rax
0x180003d5b  xor     eax, eax
0x180003d5d  mov     [rsp+310h+NumberOfBytesWritten], 0
0x180003d65  mov     r14, rcx
0x180003d68  mov     word ptr [rsp+310h+var_298], ax
0x180003d6d  mov     r13d, 7
0x180003d73  mov     [rsp+310h+var_2B0], rax
0x180003d78  lea     rcx, [rbp+210h+FileName]; Destination
0x180003d7c  mov     [rbp+210h+var_280], r13
0x180003d80  mov     [rsp+310h+var_2A8], r13
0x180003d85  mov     r15, r8
0x180003d88  mov     word ptr [rsp+310h+Block], ax
0x180003d8d  mov     esi, edx
0x180003d8f  mov     [r8], eax
0x180003d92  mov     [rbp+210h+var_288], 0
0x180003d9a  call    ?GetSystemCIPolicyPath@@YAKPEAGI@Z; GetSystemCIPolicyPath(ushort *,uint)
0x180003d9f  mov     ebx, eax
0x180003da1  test    eax, eax
0x180003da3  jnz     short loc_180003DC2
0x180003da5  test    esi, esi
0x180003da7  jnz     short loc_180003E1D
0x180003da9  lea     rcx, [rbp+210h+FileName]; lpFileName
0x180003dad  call    cs:__imp_DeleteFileW
0x180003db3  test    eax, eax
0x180003db5  jz      loc_180003E5F
0x180003dbb  mov     dword ptr [r15], 1
0x180003dc2  cmp     [rsp+310h+var_2A8], 8
0x180003dc8  jb      short loc_180003DD4
0x180003dca  mov     rcx, [rsp+310h+Block]; Block
0x180003dcf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003dd4  xor     eax, eax
0x180003dd6  mov     [rsp+310h+var_2A8], r13
0x180003ddb  cmp     [rbp+210h+var_280], 8
0x180003de0  mov     [rsp+310h+var_2B0], 0
0x180003de9  mov     word ptr [rsp+310h+Block], ax
0x180003dee  jb      short loc_180003DFA
0x180003df0  mov     rcx, [rsp+310h+var_298]; Block
0x180003df5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003dfa  mov     eax, ebx
0x180003dfc  mov     rcx, [rbp+210h+var_40]
0x180003e03  xor     rcx, rsp; StackCookie
0x180003e06  call    __security_check_cookie
0x180003e0b  add     rsp, 2E0h
0x180003e12  pop     r15
0x180003e14  pop     r14
0x180003e16  pop     r13
0x180003e18  pop     rdi
0x180003e19  pop     rsi
0x180003e1a  pop     rbx
0x180003e1b  pop     rbp
0x180003e1c  retn
0x180003e1d  test    r14, r14
0x180003e20  jnz     short loc_180003E28
0x180003e22  lea     ebx, [r14+57h]
0x180003e26  jmp     short loc_180003DC2
0x180003e28  mov     [rsp+310h+hTemplateFile], 0; hTemplateFile
0x180003e31  lea     rcx, [rbp+210h+FileName]; lpFileName
0x180003e35  mov     [rsp+310h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180003e3d  xor     r9d, r9d; lpSecurityAttributes
0x180003e40  xor     r8d, r8d; dwShareMode
0x180003e43  mov     [rsp+310h+dwCreationDisposition], 2; dwCreationDisposition
0x180003e4b  mov     edx, 40000000h; dwDesiredAccess
0x180003e50  call    cs:__imp_CreateFileW
0x180003e56  mov     rdi, rax
0x180003e59  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180003e5d  jnz     short loc_180003E6C
0x180003e5f  call    cs:__imp_GetLastError
0x180003e65  mov     ebx, eax
0x180003e67  jmp     loc_180003DC2
0x180003e6c  lea     r9, [rsp+310h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180003e71  mov     qword ptr [rsp+310h+dwCreationDisposition], 0; lpOverlapped
0x180003e7a  mov     r8d, esi; nNumberOfBytesToWrite
0x180003e7d  mov     rdx, r14; lpBuffer
0x180003e80  mov     rcx, rdi; hFile
0x180003e83  call    cs:__imp_WriteFile
0x180003e89  test    eax, eax
0x180003e8b  jnz     short loc_180003E97
0x180003e8d  call    cs:__imp_GetLastError
0x180003e93  mov     ebx, eax
0x180003e95  jmp     short loc_180003EA2
0x180003e97  cmp     [rsp+310h+NumberOfBytesWritten], esi
0x180003e9b  jz      short loc_180003EB0
0x180003e9d  mov     ebx, 26h ; '&'
0x180003ea2  mov     rcx, rdi; hObject
0x180003ea5  call    cs:__imp_CloseHandle
0x180003eab  jmp     loc_180003DC2
0x180003eb0  mov     rcx, rdi; hObject
0x180003eb3  call    cs:__imp_CloseHandle
0x180003eb9  xor     r9d, r9d; ReturnLength
0x180003ebc  lea     rdx, [rbp+210h+SystemInformation]; SystemInformation
0x180003ec0  xorps   xmm0, xmm0
0x180003ec3  movups  [rbp+210h+SystemInformation], xmm0
0x180003ec7  lea     r8d, [r9+20h]; SystemInformationLength
0x180003ecb  lea     ecx, [r9+5Ah]; SystemInformationClass
0x180003ecf  movups  [rbp+210h+var_268], xmm0
0x180003ed3  call    cs:__imp_NtQuerySystemInformation
0x180003ed9  test    eax, eax
0x180003edb  js      loc_180003DBB
0x180003ee1  cmp     dword ptr [rbp+210h+var_268], 3
0x180003ee5  jge     loc_180003DBB
0x180003eeb  cmp     dword ptr [rbp+210h+var_268], 2
0x180003eef  jnz     loc_180003DBB
0x180003ef5  lea     rcx, [rsp+310h+var_2A0]
0x180003efa  call    ?GetSystemBootDir@@YAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@@Z; GetSystemBootDir(std::wstring *)
0x180003eff  mov     edi, eax
0x180003f01  test    eax, eax
0x180003f03  jns     short loc_180003F50
0x180003f05  mov     ecx, edi
0x180003f07  and     ecx, 0FFFF0000h
0x180003f0d  cmp     ecx, 80070000h
0x180003f13  jnz     short loc_180003F1D
0x180003f15  movzx   ebx, di
0x180003f18  jmp     loc_180003DC2
0x180003f1d  bt      edi, 1Ch
0x180003f21  jnb     short loc_180003F49
0x180003f23  and     edi, 0EFFFFFFFh
0x180003f29  jl      short loc_180003F32
0x180003f2b  xor     ebx, ebx
0x180003f2d  jmp     loc_180003DC2
0x180003f32  mov     ecx, edi; Status
0x180003f34  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180003f3a  cmp     eax, 13Dh
0x180003f3f  mov     ebx, eax
0x180003f41  cmovz   ebx, edi
0x180003f44  jmp     loc_180003DC2
0x180003f49  mov     ebx, edi
0x180003f4b  jmp     loc_180003DC2
0x180003f50  lea     r9, [rsp+310h+var_2C8]
0x180003f55  lea     rcx, [rsp+310h+var_2A0]
0x180003f5a  call    ?FormCompleteFilePath@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@PEBG1PEAV12@@Z; FormCompleteFilePath(std::wstring const &,ushort const *,ushort const *,std::wstring *)
0x180003f5f  mov     edi, eax
0x180003f61  test    eax, eax
0x180003f63  js      short loc_180003F05
0x180003f65  cmp     [rsp+310h+var_2A8], 8
0x180003f6b  lea     rdx, [rsp+310h+Block]
0x180003f70  mov     [rsp+310h+dwFlagsAndAttributes], 0; dwCopyFlags
0x180003f78  lea     rcx, [rbp+210h+FileName]; lpExistingFileName
0x180003f7c  cmovnb  rdx, [rsp+310h+Block]; lpNewFileName
0x180003f82  xor     r9d, r9d; lpData
0x180003f85  xor     r8d, r8d; lpProgressRoutine
0x180003f88  mov     qword ptr [rsp+310h+dwCreationDisposition], 0; pbCancel
0x180003f91  call    cs:__imp_CopyFileExW
0x180003f97  test    eax, eax
0x180003f99  jnz     loc_180003DBB
0x180003f9f  call    cs:__imp_GetLastError
0x180003fa5  mov     edi, eax
0x180003fa7  test    eax, eax
0x180003fa9  jle     short loc_180003FB4
0x180003fab  movzx   edi, ax
0x180003fae  or      edi, 80070000h
0x180003fb4  test    edi, edi
0x180003fb6  jns     loc_180003DBB
0x180003fbc  mov     eax, edi
0x180003fbe  and     eax, 0FFFF0000h
0x180003fc3  cmp     eax, 80070000h
0x180003fc8  jmp     loc_180003F13
```
