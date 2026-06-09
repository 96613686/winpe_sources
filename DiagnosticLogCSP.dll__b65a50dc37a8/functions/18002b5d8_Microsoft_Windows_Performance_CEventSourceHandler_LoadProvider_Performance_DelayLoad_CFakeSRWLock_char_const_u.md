# Microsoft::Windows::Performance::CEventSourceHandler::LoadProvider<Performance::DelayLoad::CFakeSRWLock>(char const *,ulong,Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock> &)

- ea: `0x18002b5d8`
- end: `0x18002b8ba`
- name: `??$LoadProvider@VCFakeSRWLock@DelayLoad@Performance@@@CEventSourceHandler@Performance@Windows@Microsoft@@AEAAJPEBDKAEAV?$CDelayLoadedModule@VCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@1@@Z`
- size: `738`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002b8c0`

## callees

- `0x180001b90`
- `0x18002834c`
- `0x18002b5d8`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002b692`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002b692`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002b620`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002b620`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b646`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b646`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b750`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b7aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b7f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b750`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b7aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b7f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b812`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b812`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002b881`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002b881`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002b7e3`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002b7e3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002b796`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002b796`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18002b71a`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18002b740`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18002b71a`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18002b740`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18002b67c`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18002b67c`

## string_xrefs

- `0x18002b619`: `kernelbase.dll`
- `0x18002b63c`: `GetTempPath2W`
- `0x18002b831`: `TdhLoadManifest`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
signed int __fastcall Microsoft::Windows::Performance::CEventSourceHandler::LoadProvider<Performance::DelayLoad::CFakeSRWLock>(
        __int64 a1,
        const void *a2,
        DWORD a3,
        __int64 a4)
{
  HMODULE Library; // rax
  HMODULE v8; // rbx
  FARPROC ProcAddress; // rax
  __int64 v10; // rdi
  DWORD TempPathW; // esi
  __int64 v12; // rax
  const WCHAR *v13; // rdx
  WCHAR *v14; // rcx
  WCHAR v15; // r8
  signed int result; // eax
  WCHAR *v17; // rdx
  HANDLE FileW; // rax
  void *v19; // rsi
  signed int v20; // eax
  signed int v21; // ebx
  signed int LastError; // eax
  __int64 (__fastcall *v23)(WCHAR *); // rax
  int v24; // eax
  DWORD NumberOfBytesWritten[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v26[3]; // [rsp+48h] [rbp-B8h] BYREF
  char v27; // [rsp+60h] [rbp-A0h]
  WCHAR TempFileName[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Buffer[264]; // [rsp+280h] [rbp+180h] BYREF

  Library = LoadLibraryExW(L"kernelbase.dll", 0, 0x800u);
  v8 = Library;
  *(_QWORD *)NumberOfBytesWritten = Library;
  if ( Library && (ProcAddress = GetProcAddress(Library, "GetTempPath2W")) != 0 )
  {
    v10 = 260;
    TempPathW = ((__int64 (__fastcall *)(__int64, WCHAR *))ProcAddress)(260, Buffer);
  }
  else
  {
    v10 = 260;
    TempPathW = GetTempPathW(0x104u, Buffer);
    if ( !v8 )
      goto LABEL_6;
  }
  FreeLibrary(v8);
LABEL_6:
  if ( TempPathW && TempPathW + 1 <= 0x104 )
    goto LABEL_36;
  v12 = 2147483646;
  v13 = L".";
  v14 = Buffer;
  do
  {
    if ( !v12 )
      break;
    v15 = *v13;
    if ( !*v13 )
      break;
    ++v13;
    *v14++ = v15;
    --v12;
    --v10;
  }
  while ( v10 );
  result = v10 == 0 ? 0x8007007A : 0;
  v17 = v14 - 1;
  if ( v10 )
    v17 = v14;
  *v17 = 0;
  if ( v10 )
  {
LABEL_36:
    if ( GetTempFileNameW(Buffer, L"xpf", 0, TempFileName) || GetTempFileNameW(L".", L"xpf", 0, TempFileName) )
    {
      FileW = CreateFileW(TempFileName, 0x40000000u, 0, 0, 2u, 0x80u, 0);
      v19 = FileW;
      if ( FileW )
      {
        v21 = 0;
        NumberOfBytesWritten[0] = 0;
        if ( !WriteFile(FileW, a2, a3, NumberOfBytesWritten, 0) )
        {
          LastError = GetLastError();
          v21 = LastError;
          if ( LastError > 0 )
            v21 = (unsigned __int16)LastError | 0x80070000;
        }
        CloseHandle(v19);
      }
      else
      {
        v20 = GetLastError();
        v21 = v20;
        if ( v20 > 0 )
          v21 = (unsigned __int16)v20 | 0x80070000;
      }
      if ( v21 >= 0 )
      {
        *(_QWORD *)NumberOfBytesWritten = TempFileName;
        v26[0] = a4;
        v26[1] = "TdhLoadManifest";
        v26[2] = 0;
        v27 = 0;
        if ( Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)(v26)
          && (v23 = (__int64 (__fastcall *)(WCHAR *))Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)(v26),
              v24 = v23(TempFileName),
              (v21 = v24) != 0) )
        {
          if ( v24 > 0 )
            v21 = (unsigned __int16)v24 | 0x80070000;
        }
        else
        {
          v21 = 0;
        }
        DeleteFileW(TempFileName);
      }
      return v21;
    }
    else
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002b5d8  mov     [rsp-8+arg_0], rbx
0x18002b5dd  push    rbp
0x18002b5de  push    rsi
0x18002b5df  push    rdi
0x18002b5e0  push    r12
0x18002b5e2  push    r13
0x18002b5e4  push    r14
0x18002b5e6  push    r15
0x18002b5e8  lea     rbp, [rsp-3A0h]
0x18002b5f0  sub     rsp, 4A0h
0x18002b5f7  mov     rax, cs:__security_cookie
0x18002b5fe  xor     rax, rsp
0x18002b601  mov     [rbp+3D0h+var_40], rax
0x18002b608  mov     r12, r9
0x18002b60b  mov     r15d, r8d
0x18002b60e  mov     r14, rdx
0x18002b611  xor     edx, edx; hFile
0x18002b613  mov     r8d, 800h; dwFlags
0x18002b619  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18002b620  call    cs:__imp_LoadLibraryExW
0x18002b627  nop     dword ptr [rax+rax+00h]
0x18002b62c  mov     rbx, rax
0x18002b62f  mov     qword ptr [rsp+4D0h+NumberOfBytesWritten], rax
0x18002b634  xor     r13d, r13d
0x18002b637  test    rax, rax
0x18002b63a  jz      short loc_18002B66E
0x18002b63c  lea     rdx, aGettemppath2w; "GetTempPath2W"
0x18002b643  mov     rcx, rax; hModule
0x18002b646  call    cs:__imp_GetProcAddress
0x18002b64d  nop     dword ptr [rax+rax+00h]
0x18002b652  test    rax, rax
0x18002b655  jz      short loc_18002B66E
0x18002b657  lea     rdx, [rbp+3D0h+Buffer]
0x18002b65e  mov     edi, 104h
0x18002b663  mov     ecx, edi
0x18002b665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b66a  mov     esi, eax
0x18002b66c  jmp     short loc_18002B68F
0x18002b66e  lea     rdx, [rbp+3D0h+Buffer]; lpBuffer
0x18002b675  mov     edi, 104h
0x18002b67a  mov     ecx, edi; nBufferLength
0x18002b67c  call    cs:__imp_GetTempPathW
0x18002b683  nop     dword ptr [rax+rax+00h]
0x18002b688  mov     esi, eax
0x18002b68a  test    rbx, rbx
0x18002b68d  jz      short loc_18002B69E
0x18002b68f  mov     rcx, rbx; hLibModule
0x18002b692  call    cs:__imp_FreeLibrary
0x18002b699  nop     dword ptr [rax+rax+00h]
0x18002b69e  test    esi, esi
0x18002b6a0  jz      short loc_18002B6A9
0x18002b6a2  lea     eax, [rsi+1]
0x18002b6a5  cmp     eax, edi
0x18002b6a7  jbe     short loc_18002B704
0x18002b6a9  mov     eax, 7FFFFFFEh
0x18002b6ae  lea     rdx, PathName; "."
0x18002b6b5  lea     rcx, [rbp+3D0h+Buffer]
0x18002b6bc  test    rax, rax
0x18002b6bf  jz      short loc_18002B6E0
0x18002b6c1  movzx   r8d, word ptr [rdx]
0x18002b6c5  test    r8w, r8w
0x18002b6c9  jz      short loc_18002B6E0
0x18002b6cb  add     rdx, 2
0x18002b6cf  mov     [rcx], r8w
0x18002b6d3  add     rcx, 2
0x18002b6d7  dec     rax
0x18002b6da  sub     rdi, 1
0x18002b6de  jnz     short loc_18002B6BC
0x18002b6e0  mov     rax, rdi
0x18002b6e3  neg     rax
0x18002b6e6  sbb     eax, eax
0x18002b6e8  not     eax
0x18002b6ea  and     eax, 8007007Ah
0x18002b6ef  lea     rdx, [rcx-2]
0x18002b6f3  test    rdi, rdi
0x18002b6f6  cmovnz  rdx, rcx
0x18002b6fa  mov     [rdx], r13w
0x18002b6fe  jz      loc_18002B88F
0x18002b704  lea     r9, [rsp+4D0h+TempFileName]; lpTempFileName
0x18002b709  xor     r8d, r8d; uUnique
0x18002b70c  lea     rdx, PrefixString; "xpf"
0x18002b713  lea     rcx, [rbp+3D0h+Buffer]; lpPathName
0x18002b71a  call    cs:__imp_GetTempFileNameW
0x18002b721  nop     dword ptr [rax+rax+00h]
0x18002b726  test    eax, eax
0x18002b728  jnz     short loc_18002B771
0x18002b72a  lea     r9, [rsp+4D0h+TempFileName]; lpTempFileName
0x18002b72f  xor     r8d, r8d; uUnique
0x18002b732  lea     rdx, PrefixString; "xpf"
0x18002b739  lea     rcx, PathName; "."
0x18002b740  call    cs:__imp_GetTempFileNameW
0x18002b747  nop     dword ptr [rax+rax+00h]
0x18002b74c  test    eax, eax
0x18002b74e  jnz     short loc_18002B771
0x18002b750  call    cs:__imp_GetLastError
0x18002b757  nop     dword ptr [rax+rax+00h]
0x18002b75c  test    eax, eax
0x18002b75e  jle     loc_18002B88F
0x18002b764  movzx   eax, ax
0x18002b767  or      eax, 80070000h
0x18002b76c  jmp     loc_18002B88F
0x18002b771  mov     [rsp+4D0h+hTemplateFile], r13; hTemplateFile
0x18002b776  mov     [rsp+4D0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002b77e  mov     [rsp+4D0h+dwCreationDisposition], 2; dwCreationDisposition
0x18002b786  xor     r9d, r9d; lpSecurityAttributes
0x18002b789  xor     r8d, r8d; dwShareMode
0x18002b78c  mov     edx, 40000000h; dwDesiredAccess
0x18002b791  lea     rcx, [rsp+4D0h+TempFileName]; lpFileName
0x18002b796  call    cs:__imp_CreateFileW
0x18002b79d  nop     dword ptr [rax+rax+00h]
0x18002b7a2  mov     rsi, rax
0x18002b7a5  test    rax, rax
0x18002b7a8  jnz     short loc_18002B7C8
0x18002b7aa  call    cs:__imp_GetLastError
0x18002b7b1  nop     dword ptr [rax+rax+00h]
0x18002b7b6  mov     ebx, eax
0x18002b7b8  mov     edi, 80070000h
0x18002b7bd  test    eax, eax
0x18002b7bf  jle     short loc_18002B81E
0x18002b7c1  movzx   ebx, ax
0x18002b7c4  or      ebx, edi
0x18002b7c6  jmp     short loc_18002B81E
0x18002b7c8  mov     ebx, r13d
0x18002b7cb  mov     [rsp+4D0h+NumberOfBytesWritten], r13d
0x18002b7d0  mov     qword ptr [rsp+4D0h+dwCreationDisposition], r13; lpOverlapped
0x18002b7d5  lea     r9, [rsp+4D0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002b7da  mov     r8d, r15d; nNumberOfBytesToWrite
0x18002b7dd  mov     rdx, r14; lpBuffer
0x18002b7e0  mov     rcx, rsi; hFile
0x18002b7e3  call    cs:__imp_WriteFile
0x18002b7ea  nop     dword ptr [rax+rax+00h]
0x18002b7ef  mov     edi, 80070000h
0x18002b7f4  test    eax, eax
0x18002b7f6  jnz     short loc_18002B80F
0x18002b7f8  call    cs:__imp_GetLastError
0x18002b7ff  nop     dword ptr [rax+rax+00h]
0x18002b804  mov     ebx, eax
0x18002b806  test    eax, eax
0x18002b808  jle     short loc_18002B80F
0x18002b80a  movzx   ebx, ax
0x18002b80d  or      ebx, edi
0x18002b80f  mov     rcx, rsi; hObject
0x18002b812  call    cs:__imp_CloseHandle
0x18002b819  nop     dword ptr [rax+rax+00h]
0x18002b81e  test    ebx, ebx
0x18002b820  js      short loc_18002B88D
0x18002b822  lea     rax, [rsp+4D0h+TempFileName]
0x18002b827  mov     qword ptr [rsp+4D0h+NumberOfBytesWritten], rax
0x18002b82c  mov     [rsp+4D0h+var_488], r12
0x18002b831  lea     rax, aTdhloadmanifes; "TdhLoadManifest"
0x18002b838  mov     [rsp+4D0h+var_480], rax
0x18002b83d  mov     [rsp+4D0h+var_478], r13
0x18002b842  mov     [rsp+4D0h+var_470], r13b
0x18002b847  lea     rcx, [rsp+4D0h+var_488]
0x18002b84c  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18002b851  test    rax, rax
0x18002b854  jz      short loc_18002B879
0x18002b856  lea     rcx, [rsp+4D0h+var_488]
0x18002b85b  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18002b860  lea     rcx, [rsp+4D0h+TempFileName]
0x18002b865  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b86a  mov     ebx, eax
0x18002b86c  test    eax, eax
0x18002b86e  jz      short loc_18002B879
0x18002b870  jle     short loc_18002B87C
0x18002b872  movzx   ebx, ax
0x18002b875  or      ebx, edi
0x18002b877  jmp     short loc_18002B87C
0x18002b879  mov     ebx, r13d
0x18002b87c  lea     rcx, [rsp+4D0h+TempFileName]; lpFileName
0x18002b881  call    cs:__imp_DeleteFileW
0x18002b888  nop     dword ptr [rax+rax+00h]
0x18002b88d  mov     eax, ebx
0x18002b88f  mov     rcx, [rbp+3D0h+var_40]
0x18002b896  xor     rcx, rsp; StackCookie
0x18002b899  call    __security_check_cookie
0x18002b89e  mov     rbx, [rsp+4D0h+arg_0]
0x18002b8a6  add     rsp, 4A0h
0x18002b8ad  pop     r15
0x18002b8af  pop     r14
0x18002b8b1  pop     r13
0x18002b8b3  pop     r12
0x18002b8b5  pop     rdi
0x18002b8b6  pop     rsi
0x18002b8b7  pop     rbp
0x18002b8b8  retn
```
