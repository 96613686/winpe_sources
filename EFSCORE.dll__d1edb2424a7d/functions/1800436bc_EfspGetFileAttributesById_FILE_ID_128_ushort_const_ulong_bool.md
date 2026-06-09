# EfspGetFileAttributesById(_FILE_ID_128 *,ushort const *,ulong *,bool *)

- ea: `0x1800436bc`
- end: `0x180043900`
- name: `?EfspGetFileAttributesById@@YAJPEAU_FILE_ID_128@@PEBGPEAKPEA_N@Z`
- size: `580`
- prototype: `int(struct _FILE_ID_128 *, const unsigned __int16 *, unsigned int *, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180043c20`

## callees

- `0x1800436bc`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x1800dddf0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043755`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043892`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043755`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043892`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800438db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800438db`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180043746`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180043746`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180043888`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180043888`
- `ntdll!NtClose` at `0x1800438c4`
- `ntdll!NtClose` at `0x1800438c4`
- `ntdll!NtCreateFile` at `0x1800437f5`
- `ntdll!NtCreateFile` at `0x1800437f5`
- `ntdll!RtlNtStatusToDosError` at `0x180043829`
- `ntdll!RtlNtStatusToDosError` at `0x180043829`

## pseudocode

```c
__int64 __fastcall EfspGetFileAttributesById(
        struct _FILE_ID_128 *a1,
        const unsigned __int16 *a2,
        unsigned int *a3,
        bool *a4)
{
  HANDLE FileW; // r14
  signed int LastError; // eax
  unsigned int v9; // ebx
  int v10; // ecx
  NTSTATUS v11; // edi
  signed int v12; // eax
  signed int v13; // eax
  void *FileHandle; // [rsp+60h] [rbp-69h] BYREF
  __int128 v16; // [rsp+68h] [rbp-61h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-51h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A8h] [rbp-21h] BYREF
  int FileInformation; // [rsp+B8h] [rbp-11h] BYREF
  __int128 v20; // [rsp+BCh] [rbp-Dh]
  __int128 v21; // [rsp+CCh] [rbp+3h]
  int v22; // [rsp+DCh] [rbp+13h]

  FileHandle = 0;
  FileInformation = 0;
  *a4 = 0;
  v22 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  v16 = 0;
  v20 = 0;
  v21 = 0;
  FileW = CreateFileW(a2, 0x80000000, 3u, 0, 3u, 0x2000000u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v9, 42, 135);
  }
  else
  {
    v9 = 0;
    LODWORD(v16) = 1048592;
    *((_QWORD *)&v16 + 1) = a1;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = FileW;
    ObjectAttributes.Attributes = 0;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&v16;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v11 = NtCreateFile(&FileHandle, 0x80u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 0, 1u, 0x2000u, 0, 0);
    if ( v11 != -1073741811 )
    {
      fnEfsLogTrace1Strings(v10, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 42, 164);
      v12 = RtlNtStatusToDosError(v11);
      v9 = v12;
      if ( v12 > 0 )
        v9 = (unsigned __int16)v12 | 0x80070000;
      if ( (int)fnEfsLogTrace1String1Dword(
                  g_hPublisher,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                  (unsigned int)&sourceString,
                  v9,
                  42,
                  164) >= 0 )
      {
        if ( GetFileInformationByHandleEx(FileHandle, FileBasicInfo, &FileInformation, 0x28u) )
        {
          *a3 = HIDWORD(v21);
          *a4 = 1;
        }
        else
        {
          v13 = GetLastError();
          v9 = v13;
          if ( v13 > 0 )
            v9 = (unsigned __int16)v13 | 0x80070000;
          fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v9, 42, 168);
        }
      }
    }
  }
  if ( FileHandle )
  {
    NtClose(FileHandle);
    FileHandle = 0;
  }
  if ( FileW != (HANDLE)-1LL )
    CloseHandle(FileW);
  return v9;
}

```

## disassembly

```asm
0x1800436bc  push    rbp
0x1800436be  push    rbx
0x1800436bf  push    rdi
0x1800436c0  push    r12
0x1800436c2  push    r14
0x1800436c4  push    r15
0x1800436c6  lea     rbp, [rsp-2Fh]
0x1800436cb  sub     rsp, 0F8h
0x1800436d2  mov     rax, cs:__security_cookie
0x1800436d9  xor     rax, rsp
0x1800436dc  mov     [rbp+57h+var_40], rax
0x1800436e0  xorps   xmm0, xmm0
0x1800436e3  mov     [rbp+57h+FileHandle], 0
0x1800436eb  mov     rdi, rcx
0x1800436ee  mov     [rbp+57h+FileInformation], 0
0x1800436f5  xor     ecx, ecx
0x1800436f7  mov     rax, rdx
0x1800436fa  mov     [rsp+120h+hTemplateFile], rcx; hTemplateFile
0x1800436ff  mov     r12, r8
0x180043702  mov     [r9], cl
0x180043705  mov     r15, r9
0x180043708  xorps   xmm1, xmm1
0x18004370b  mov     [rbp+57h+var_44], ecx
0x18004370e  lea     r8d, [rcx+3]; dwShareMode
0x180043712  mov     [rsp+120h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18004371a  mov     rcx, rax; lpFileName
0x18004371d  mov     [rsp+120h+dwCreationDisposition], r8d; dwCreationDisposition
0x180043722  xor     r9d, r9d; lpSecurityAttributes
0x180043725  mov     edx, 80000000h; dwDesiredAccess
0x18004372a  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18004372e  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180043732  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180043736  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18004373a  movups  [rbp+57h+var_B8], xmm1
0x18004373e  movups  [rbp+57h+var_64], xmm0
0x180043742  movups  [rbp+57h+var_54], xmm0
0x180043746  call    cs:__imp_CreateFileW
0x18004374c  mov     r14, rax
0x18004374f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180043753  jnz     short loc_180043793
0x180043755  call    cs:__imp_GetLastError
0x18004375b  mov     ebx, eax
0x18004375d  test    eax, eax
0x18004375f  jle     short loc_18004376A
0x180043761  movzx   ebx, ax
0x180043764  or      ebx, 80070000h
0x18004376a  mov     [rsp+120h+dwCreationDisposition], 387h
0x180043772  mov     rcx, cs:g_hPublisher
0x180043779  lea     rdx, EFS_TRACE_ERROR
0x180043780  mov     r9d, 2Ah ; '*'
0x180043786  mov     r8d, ebx
0x180043789  call    fnEfsLogTrace1
0x18004378e  jmp     loc_1800438BB
0x180043793  xor     ebx, ebx
0x180043795  mov     dword ptr [rbp+57h+var_B8], 100010h
0x18004379c  mov     [rsp+120h+EaLength], ebx; EaLength
0x1800437a0  lea     rax, [rbp+57h+var_B8]
0x1800437a4  mov     [rsp+120h+EaBuffer], rbx; EaBuffer
0x1800437a9  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800437ad  mov     [rsp+120h+CreateOptions], 2000h; CreateOptions
0x1800437b5  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800437b9  mov     [rsp+120h+CreateDisposition], 1; CreateDisposition
0x1800437c1  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800437c5  mov     edx, 80h; DesiredAccess
0x1800437ca  mov     dword ptr [rsp+120h+hTemplateFile], ebx; ShareAccess
0x1800437ce  xorps   xmm0, xmm0
0x1800437d1  mov     [rsp+120h+dwFlagsAndAttributes], edx; FileAttributes
0x1800437d5  mov     qword ptr [rsp+120h+dwCreationDisposition], rbx; AllocationSize
0x1800437da  mov     qword ptr [rbp+57h+var_B8+8], rdi
0x1800437de  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800437e5  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x1800437e9  mov     [rbp+57h+ObjectAttributes.Attributes], ebx
0x1800437ec  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800437f0  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800437f5  call    cs:__imp_NtCreateFile
0x1800437fb  mov     edi, eax
0x1800437fd  cmp     eax, 0C000000Dh
0x180043802  jz      loc_1800438BB
0x180043808  lea     r9d, [rbx+2Ah]
0x18004380c  mov     [rsp+120h+dwCreationDisposition], 3A4h
0x180043814  lea     r8, sourceString
0x18004381b  lea     rdx, EFS_TRACE_START_EVENT
0x180043822  call    fnEfsLogTrace1Strings
0x180043827  mov     ecx, edi; Status
0x180043829  call    cs:__imp_RtlNtStatusToDosError
0x18004382f  mov     ebx, eax
0x180043831  mov     edi, 80070000h
0x180043836  test    eax, eax
0x180043838  jle     short loc_18004383F
0x18004383a  movzx   ebx, ax
0x18004383d  or      ebx, edi
0x18004383f  mov     rcx, cs:g_hPublisher
0x180043846  lea     r9, sourceString
0x18004384d  mov     dword ptr [rsp+120h+hTemplateFile], 3A4h
0x180043855  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x18004385c  mov     [rsp+120h+dwFlagsAndAttributes], 2Ah ; '*'
0x180043864  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x18004386b  mov     [rsp+120h+dwCreationDisposition], ebx
0x18004386f  call    fnEfsLogTrace1String1Dword
0x180043874  test    eax, eax
0x180043876  js      short loc_1800438BB
0x180043878  mov     rcx, [rbp+57h+FileHandle]; hFile
0x18004387c  lea     r8, [rbp+57h+FileInformation]; lpFileInformation
0x180043880  mov     r9d, 28h ; '('; dwBufferSize
0x180043886  xor     edx, edx; FileInformationClass
0x180043888  call    cs:__imp_GetFileInformationByHandleEx
0x18004388e  test    eax, eax
0x180043890  jnz     short loc_1800438B0
0x180043892  call    cs:__imp_GetLastError
0x180043898  mov     ebx, eax
0x18004389a  test    eax, eax
0x18004389c  jle     short loc_1800438A3
0x18004389e  movzx   ebx, ax
0x1800438a1  or      ebx, edi
0x1800438a3  mov     [rsp+120h+dwCreationDisposition], 3A8h
0x1800438ab  jmp     loc_180043772
0x1800438b0  mov     eax, dword ptr [rbp+57h+var_54+0Ch]
0x1800438b3  mov     [r12], eax
0x1800438b7  mov     byte ptr [r15], 1
0x1800438bb  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800438bf  test    rcx, rcx
0x1800438c2  jz      short loc_1800438D2
0x1800438c4  call    cs:__imp_NtClose
0x1800438ca  mov     [rbp+57h+FileHandle], 0
0x1800438d2  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x1800438d6  jz      short loc_1800438E1
0x1800438d8  mov     rcx, r14; hObject
0x1800438db  call    cs:__imp_CloseHandle
0x1800438e1  mov     eax, ebx
0x1800438e3  mov     rcx, [rbp+57h+var_40]
0x1800438e7  xor     rcx, rsp; StackCookie
0x1800438ea  call    __security_check_cookie
0x1800438ef  add     rsp, 0F8h
0x1800438f6  pop     r15
0x1800438f8  pop     r14
0x1800438fa  pop     r12
0x1800438fc  pop     rdi
0x1800438fd  pop     rbx
0x1800438fe  pop     rbp
0x1800438ff  retn
```
