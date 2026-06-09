# EfspGetFileNameById(_FILE_ID_128 *,ushort const *,ushort * *)

- ea: `0x180043908`
- end: `0x180043bd0`
- name: `?EfspGetFileNameById@@YAJPEAU_FILE_ID_128@@PEBGPEAPEAG@Z`
- size: `712`
- prototype: `int(struct _FILE_ID_128 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180042a3c`
- `0x180042de0`

## callees

- `0x180043908`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180043af9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180043af9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180043ae8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180043ba3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180043ae8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180043ba3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180043bb1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180043bb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043985`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043abd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043b50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043985`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043abd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043b50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043b98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043b98`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180043ab0`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180043b43`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180043ab0`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180043b43`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180043976`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180043976`
- `ntdll!NtClose` at `0x180043b85`
- `ntdll!NtClose` at `0x180043b85`
- `ntdll!NtCreateFile` at `0x180043a27`
- `ntdll!NtCreateFile` at `0x180043a27`
- `ntdll!RtlNtStatusToDosError` at `0x180043a52`
- `ntdll!RtlNtStatusToDosError` at `0x180043a52`

## pseudocode

```c
__int64 __fastcall EfspGetFileNameById(struct _FILE_ID_128 *a1, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  unsigned __int16 *v4; // rsi
  HANDLE FileW; // r13
  signed int LastError; // eax
  unsigned int v7; // edi
  NTSTATUS v8; // ebx
  int v9; // ecx
  signed int v10; // eax
  DWORD FinalPathNameByHandleW; // eax
  __int64 v12; // r12
  signed int v13; // eax
  HANDLE ProcessHeap; // rax
  WCHAR *v15; // rax
  signed int v16; // eax
  HANDLE v17; // rax
  __int128 v19; // [rsp+60h] [rbp-19h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp+7h] BYREF
  void *FileHandle; // [rsp+F8h] [rbp+7Fh] BYREF

  *a3 = 0;
  FileHandle = 0;
  v4 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  v19 = 0;
  FileW = CreateFileW(a2, 0x80000000, 3u, 0, 3u, 0x2000000u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v7, 42, 243);
  }
  else
  {
    LODWORD(v19) = 1048592;
    *((_QWORD *)&v19 + 1) = a1;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = FileW;
    ObjectAttributes.Attributes = 0;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&v19;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v8 = NtCreateFile(&FileHandle, 0x80000000, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 0, 1u, 0x2000u, 0, 0);
    fnEfsLogTrace1Strings(v9, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 42, 12);
    v10 = RtlNtStatusToDosError(v8);
    v7 = v10;
    if ( v10 > 0 )
      v7 = (unsigned __int16)v10 | 0x80070000;
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                v7,
                42,
                12) >= 0 )
    {
      FinalPathNameByHandleW = GetFinalPathNameByHandleW(FileHandle, 0, 0, 0);
      v12 = FinalPathNameByHandleW;
      if ( FinalPathNameByHandleW )
      {
        ProcessHeap = GetProcessHeap();
        v15 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 2 * v12);
        v4 = v15;
        if ( v15 )
        {
          if ( GetFinalPathNameByHandleW(FileHandle, v15, v12, 0) )
          {
            *a3 = v4;
            v4 = 0;
          }
          else
          {
            v16 = GetLastError();
            v7 = v16;
            if ( v16 > 0 )
              v7 = (unsigned __int16)v16 | 0x80070000;
            fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v7, 42, 39);
          }
        }
        else
        {
          v7 = -2147024882;
          fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024882, 42, 30);
        }
      }
      else
      {
        v13 = GetLastError();
        v7 = v13;
        if ( v13 > 0 )
          v7 = (unsigned __int16)v13 | 0x80070000;
        fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v7, 42, 24);
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
  if ( v4 )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v4);
  }
  return v7;
}

```

## disassembly

```asm
0x180043908  mov     [rsp-8+arg_0], rbx
0x18004390d  mov     [rsp-8+arg_10], r8
0x180043912  push    rbp
0x180043913  push    rsi
0x180043914  push    rdi
0x180043915  push    r12
0x180043917  push    r13
0x180043919  lea     rbp, [rsp-37h]
0x18004391e  sub     rsp, 0B0h
0x180043925  xor     r12d, r12d
0x180043928  xorps   xmm0, xmm0
0x18004392b  mov     rax, rdx
0x18004392e  mov     [r8], r12
0x180043931  mov     rbx, rcx
0x180043934  mov     [rsp+0D0h+hTemplateFile], r12; hTemplateFile
0x180043939  xorps   xmm1, xmm1
0x18004393c  mov     [rsp+0D0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180043944  lea     r8d, [r12+3]; dwShareMode
0x180043949  mov     [rbp+57h+FileHandle], r12
0x18004394d  mov     edi, 80000000h
0x180043952  mov     [rsp+0D0h+dwCreationDisposition], r8d; dwCreationDisposition
0x180043957  xor     r9d, r9d; lpSecurityAttributes
0x18004395a  mov     edx, edi; dwDesiredAccess
0x18004395c  mov     rcx, rax; lpFileName
0x18004395f  mov     esi, r12d
0x180043962  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180043966  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18004396a  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18004396e  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180043972  movups  [rbp+57h+var_70], xmm1
0x180043976  call    cs:__imp_CreateFileW
0x18004397c  mov     r13, rax
0x18004397f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180043983  jnz     short loc_1800439C3
0x180043985  call    cs:__imp_GetLastError
0x18004398b  mov     edi, eax
0x18004398d  test    eax, eax
0x18004398f  jle     short loc_18004399A
0x180043991  movzx   edi, ax
0x180043994  or      edi, 80070000h
0x18004399a  mov     [rsp+0D0h+dwCreationDisposition], 3F3h
0x1800439a2  mov     rcx, cs:g_hPublisher
0x1800439a9  lea     rdx, EFS_TRACE_ERROR
0x1800439b0  mov     r9d, 2Ah ; '*'
0x1800439b6  mov     r8d, edi
0x1800439b9  call    fnEfsLogTrace1
0x1800439be  jmp     loc_180043B7C
0x1800439c3  mov     [rsp+0D0h+EaLength], r12d; EaLength
0x1800439c8  lea     rax, [rbp+57h+var_70]
0x1800439cc  mov     [rsp+0D0h+EaBuffer], r12; EaBuffer
0x1800439d1  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800439d5  mov     [rsp+0D0h+CreateOptions], 2000h; CreateOptions
0x1800439dd  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800439e1  mov     [rsp+0D0h+CreateDisposition], 1; CreateDisposition
0x1800439e9  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800439ed  mov     dword ptr [rsp+0D0h+hTemplateFile], r12d; ShareAccess
0x1800439f2  xorps   xmm0, xmm0
0x1800439f5  mov     [rsp+0D0h+dwFlagsAndAttributes], 80h; FileAttributes
0x1800439fd  mov     edx, edi; DesiredAccess
0x1800439ff  mov     qword ptr [rsp+0D0h+dwCreationDisposition], r12; AllocationSize
0x180043a04  mov     dword ptr [rbp+57h+var_70], 100010h
0x180043a0b  mov     qword ptr [rbp+57h+var_70+8], rbx
0x180043a0f  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180043a16  mov     [rbp+57h+ObjectAttributes.RootDirectory], r13
0x180043a1a  mov     [rbp+57h+ObjectAttributes.Attributes], r12d
0x180043a1e  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180043a22  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180043a27  call    cs:__imp_NtCreateFile
0x180043a2d  mov     r9d, 2Ah ; '*'
0x180043a33  mov     [rsp+0D0h+dwCreationDisposition], 40Ch
0x180043a3b  lea     r8, sourceString
0x180043a42  mov     ebx, eax
0x180043a44  lea     rdx, EFS_TRACE_START_EVENT
0x180043a4b  call    fnEfsLogTrace1Strings
0x180043a50  mov     ecx, ebx; Status
0x180043a52  call    cs:__imp_RtlNtStatusToDosError
0x180043a58  mov     edi, eax
0x180043a5a  test    eax, eax
0x180043a5c  jle     short loc_180043A67
0x180043a5e  movzx   edi, ax
0x180043a61  or      edi, 80070000h
0x180043a67  mov     rcx, cs:g_hPublisher
0x180043a6e  lea     r9, sourceString
0x180043a75  mov     dword ptr [rsp+0D0h+hTemplateFile], 40Ch
0x180043a7d  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180043a84  mov     [rsp+0D0h+dwFlagsAndAttributes], 2Ah ; '*'
0x180043a8c  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180043a93  mov     [rsp+0D0h+dwCreationDisposition], edi
0x180043a97  call    fnEfsLogTrace1String1Dword
0x180043a9c  test    eax, eax
0x180043a9e  js      loc_180043B7C
0x180043aa4  mov     rcx, [rbp+57h+FileHandle]; hFile
0x180043aa8  xor     r9d, r9d; dwFlags
0x180043aab  xor     r8d, r8d; cchFilePath
0x180043aae  xor     edx, edx; lpszFilePath
0x180043ab0  call    cs:__imp_GetFinalPathNameByHandleW
0x180043ab6  mov     r12d, eax
0x180043ab9  test    eax, eax
0x180043abb  jnz     short loc_180043AE2
0x180043abd  call    cs:__imp_GetLastError
0x180043ac3  xor     r12d, r12d
0x180043ac6  mov     edi, eax
0x180043ac8  test    eax, eax
0x180043aca  jle     short loc_180043AD5
0x180043acc  movzx   edi, ax
0x180043acf  or      edi, 80070000h
0x180043ad5  mov     [rsp+0D0h+dwCreationDisposition], 418h
0x180043add  jmp     loc_1800439A2
0x180043ae2  mov     rbx, r12
0x180043ae5  add     rbx, rbx
0x180043ae8  call    cs:__imp_GetProcessHeap
0x180043aee  mov     r8, rbx; dwBytes
0x180043af1  mov     edx, 8; dwFlags
0x180043af6  mov     rcx, rax; hHeap
0x180043af9  call    cs:__imp_HeapAlloc
0x180043aff  mov     rsi, rax
0x180043b02  test    rax, rax
0x180043b05  jnz     short loc_180043B36
0x180043b07  mov     rcx, cs:g_hPublisher
0x180043b0e  lea     r9d, [rax+2Ah]
0x180043b12  mov     r8d, 8007000Eh
0x180043b18  mov     [rsp+0D0h+dwCreationDisposition], 41Eh
0x180043b20  lea     rdx, EFS_TRACE_ERROR
0x180043b27  mov     edi, 8007000Eh
0x180043b2c  call    fnEfsLogTrace1
0x180043b31  xor     r12d, r12d
0x180043b34  jmp     short loc_180043B7C
0x180043b36  mov     rcx, [rbp+57h+FileHandle]; hFile
0x180043b3a  xor     r9d, r9d; dwFlags
0x180043b3d  mov     r8d, r12d; cchFilePath
0x180043b40  mov     rdx, rsi; lpszFilePath
0x180043b43  call    cs:__imp_GetFinalPathNameByHandleW
0x180043b49  xor     r12d, r12d
0x180043b4c  test    eax, eax
0x180043b4e  jnz     short loc_180043B72
0x180043b50  call    cs:__imp_GetLastError
0x180043b56  mov     edi, eax
0x180043b58  test    eax, eax
0x180043b5a  jle     short loc_180043B65
0x180043b5c  movzx   edi, ax
0x180043b5f  or      edi, 80070000h
0x180043b65  mov     [rsp+0D0h+dwCreationDisposition], 427h
0x180043b6d  jmp     loc_1800439A2
0x180043b72  mov     rax, [rbp+57h+arg_10]
0x180043b76  mov     [rax], rsi
0x180043b79  mov     rsi, r12
0x180043b7c  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180043b80  test    rcx, rcx
0x180043b83  jz      short loc_180043B8F
0x180043b85  call    cs:__imp_NtClose
0x180043b8b  mov     [rbp+57h+FileHandle], r12
0x180043b8f  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x180043b93  jz      short loc_180043B9E
0x180043b95  mov     rcx, r13; hObject
0x180043b98  call    cs:__imp_CloseHandle
0x180043b9e  test    rsi, rsi
0x180043ba1  jz      short loc_180043BB7
0x180043ba3  call    cs:__imp_GetProcessHeap
0x180043ba9  mov     r8, rsi; lpMem
0x180043bac  xor     edx, edx; dwFlags
0x180043bae  mov     rcx, rax; hHeap
0x180043bb1  call    cs:__imp_HeapFree
0x180043bb7  mov     rbx, [rsp+0D0h+arg_0]
0x180043bbf  mov     eax, edi
0x180043bc1  add     rsp, 0B0h
0x180043bc8  pop     r13
0x180043bca  pop     r12
0x180043bcc  pop     rdi
0x180043bcd  pop     rsi
0x180043bce  pop     rbp
0x180043bcf  retn
```
