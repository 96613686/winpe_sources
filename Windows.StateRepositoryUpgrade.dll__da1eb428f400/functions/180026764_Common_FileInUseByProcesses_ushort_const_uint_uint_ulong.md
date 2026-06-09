# Common::FileInUseByProcesses(ushort const *,uint,uint *,ulong *)

- ea: `0x180026764`
- end: `0x18002687f`
- name: `?FileInUseByProcesses@Common@@YAJPEBGIPEAIPEAK@Z`
- size: `283`
- prototype: `DWORD __fastcall(LPCWSTR lpFileName, const unsigned __int16 *, _DWORD *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180027404`

## callees

- `0x180003980`
- `0x180026764`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800267d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800267d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002680f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002680f`
- `ntdll!NtQueryInformationFile` at `0x180026804`
- `ntdll!NtQueryInformationFile` at `0x180026804`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18002681b`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18002681b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800267ca`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800267ca`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180026791`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180026791`

## pseudocode

```c
DWORD __fastcall Common::FileInUseByProcesses(
        LPCWSTR lpFileName,
        const unsigned __int16 *a2,
        _DWORD *a3,
        unsigned int *a4)
{
  DWORD dwFlagsAndAttributes; // ebx
  DWORD FileAttributesW; // eax
  HANDLE FileW; // rax
  void *v10; // rbx
  int v12; // edi
  unsigned int v13; // edx
  __int64 v14; // r8
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-438h] BYREF
  _DWORD FileInformation[256]; // [rsp+50h] [rbp-428h] BYREF

  dwFlagsAndAttributes = 0;
  FileAttributesW = GetFileAttributesW(lpFileName);
  if ( FileAttributesW != -1 && (FileAttributesW & 0x10) != 0 )
    dwFlagsAndAttributes = 0x2000000;
  FileW = CreateFileW(lpFileName, 0x80u, 7u, 0, 3u, dwFlagsAndAttributes, 0);
  v10 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return GetLastError();
  IoStatusBlock = 0;
  v12 = NtQueryInformationFile(FileW, &IoStatusBlock, FileInformation, 0x400u, FileProcessIdsUsingFileInformation);
  CloseHandle(v10);
  if ( v12 < 0 )
    return RtlNtStatusToDosErrorNoTeb(v12);
  v13 = FileInformation[0];
  v14 = 0;
  *a3 = FileInformation[0];
  if ( v13 >= 0x64 )
  {
    v13 = 100;
    goto LABEL_11;
  }
  if ( v13 )
  {
    do
    {
LABEL_11:
      a4[v14] = FileInformation[2 * v14 + 2];
      v14 = (unsigned int)(v14 + 1);
    }
    while ( (unsigned int)v14 < v13 );
  }
  return *a3 > 0x64u ? 0xEA : 0;
}

```

## disassembly

```asm
0x180026764  mov     [rsp+arg_8], rbx
0x180026769  push    rsi
0x18002676a  push    rdi
0x18002676b  push    r14
0x18002676d  sub     rsp, 460h
0x180026774  mov     rax, cs:__security_cookie
0x18002677b  xor     rax, rsp
0x18002677e  mov     [rsp+478h+var_28], rax
0x180026786  mov     r14, r9
0x180026789  mov     rsi, r8
0x18002678c  mov     rdi, rcx
0x18002678f  xor     ebx, ebx
0x180026791  call    cs:__imp_GetFileAttributesW
0x180026797  cmp     eax, 0FFFFFFFFh
0x18002679a  jz      short loc_1800267A6
0x18002679c  test    al, 10h
0x18002679e  mov     eax, 2000000h
0x1800267a3  cmovnz  ebx, eax
0x1800267a6  xor     r9d, r9d; lpSecurityAttributes
0x1800267a9  mov     [rsp+478h+hTemplateFile], 0; hTemplateFile
0x1800267b2  mov     [rsp+478h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x1800267b6  mov     edx, 80h; dwDesiredAccess
0x1800267bb  mov     rcx, rdi; lpFileName
0x1800267be  mov     [rsp+478h+dwCreationDisposition], 3; dwCreationDisposition
0x1800267c6  lea     r8d, [r9+7]; dwShareMode
0x1800267ca  call    cs:__imp_CreateFileW
0x1800267d0  mov     rbx, rax
0x1800267d3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800267d7  jnz     short loc_1800267E1
0x1800267d9  call    cs:__imp_GetLastError
0x1800267df  jmp     short loc_18002685B
0x1800267e1  xorps   xmm0, xmm0
0x1800267e4  mov     [rsp+478h+dwCreationDisposition], 2Fh ; '/'; FileInformationClass
0x1800267ec  mov     r9d, 400h; Length
0x1800267f2  lea     r8, [rsp+478h+FileInformation]; FileInformation
0x1800267f7  lea     rdx, [rsp+478h+IoStatusBlock]; IoStatusBlock
0x1800267fc  mov     rcx, rbx; FileHandle
0x1800267ff  movups  xmmword ptr [rsp+478h+IoStatusBlock], xmm0
0x180026804  call    cs:__imp_NtQueryInformationFile
0x18002680a  mov     rcx, rbx; hObject
0x18002680d  mov     edi, eax
0x18002680f  call    cs:__imp_CloseHandle
0x180026815  test    edi, edi
0x180026817  jns     short loc_180026823
0x180026819  mov     ecx, edi; Status
0x18002681b  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180026821  jmp     short loc_18002685B
0x180026823  mov     edx, [rsp+478h+FileInformation]
0x180026827  mov     r9d, 64h ; 'd'
0x18002682d  xor     r8d, r8d
0x180026830  mov     [rsi], edx
0x180026832  cmp     edx, r9d
0x180026835  jb      short loc_18002683C
0x180026837  mov     edx, r9d
0x18002683a  jmp     short loc_180026840
0x18002683c  test    edx, edx
0x18002683e  jz      short loc_180026851
0x180026840  mov     eax, [rsp+r8*8+478h+var_420]
0x180026845  mov     [r14+r8*4], eax
0x180026849  inc     r8d
0x18002684c  cmp     r8d, edx
0x18002684f  jb      short loc_180026840
0x180026851  cmp     r9d, [rsi]
0x180026854  sbb     eax, eax
0x180026856  and     eax, 0EAh
0x18002685b  mov     rcx, [rsp+478h+var_28]
0x180026863  xor     rcx, rsp; StackCookie
0x180026866  call    __security_check_cookie
0x18002686b  mov     rbx, [rsp+478h+arg_8]
0x180026873  add     rsp, 460h
0x18002687a  pop     r14
0x18002687c  pop     rdi
0x18002687d  pop     rsi
0x18002687e  retn
```
