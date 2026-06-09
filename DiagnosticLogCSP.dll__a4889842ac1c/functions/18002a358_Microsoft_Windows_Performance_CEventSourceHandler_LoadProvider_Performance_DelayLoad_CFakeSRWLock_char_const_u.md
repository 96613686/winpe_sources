# Microsoft::Windows::Performance::CEventSourceHandler::LoadProvider<Performance::DelayLoad::CFakeSRWLock>(char const *,ulong,Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock> &)

- ea: `0x18002a358`
- end: `0x18002a5eb`
- name: `??$LoadProvider@VCFakeSRWLock@DelayLoad@Performance@@@CEventSourceHandler@Performance@Windows@Microsoft@@AEAAJPEBDKAEAV?$CDelayLoadedModule@VCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@1@@Z`
- size: `659`
- prototype: `signed int __fastcall(__int64, const void *, DWORD, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002a5f4`

## callees

- `0x180001b60`
- `0x1800271c8`
- `0x18002a358`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002a400`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002a400`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002a3a0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002a3a0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a3c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a3c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a4ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a4fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a53c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a4ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a4fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a53c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a550`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a550`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002a5b9`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002a5b9`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002a52d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002a52d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002a4ec`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002a4ec`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18002a482`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18002a4a2`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18002a482`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18002a4a2`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18002a3f0`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18002a3f0`

## string_xrefs

- `0x18002a399`: `kernelbase.dll`
- `0x18002a3b6`: `GetTempPath2W`
- `0x18002a569`: `TdhLoadManifest`

## pseudocode

```c
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
0x18002a358  mov     [rsp-8+arg_0], rbx
0x18002a35d  push    rbp
0x18002a35e  push    rsi
0x18002a35f  push    rdi
0x18002a360  push    r12
0x18002a362  push    r13
0x18002a364  push    r14
0x18002a366  push    r15
0x18002a368  lea     rbp, [rsp-3A0h]
0x18002a370  sub     rsp, 4A0h
0x18002a377  mov     rax, cs:__security_cookie
0x18002a37e  xor     rax, rsp
0x18002a381  mov     [rbp+3D0h+var_40], rax
0x18002a388  mov     r12, r9
0x18002a38b  mov     r15d, r8d
0x18002a38e  mov     r14, rdx
0x18002a391  xor     edx, edx; hFile
0x18002a393  mov     r8d, 800h; dwFlags
0x18002a399  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18002a3a0  call    cs:__imp_LoadLibraryExW
0x18002a3a6  mov     rbx, rax
0x18002a3a9  mov     qword ptr [rsp+4D0h+NumberOfBytesWritten], rax
0x18002a3ae  xor     r13d, r13d
0x18002a3b1  test    rax, rax
0x18002a3b4  jz      short loc_18002A3E2
0x18002a3b6  lea     rdx, aGettemppath2w; "GetTempPath2W"
0x18002a3bd  mov     rcx, rax; hModule
0x18002a3c0  call    cs:__imp_GetProcAddress
0x18002a3c6  test    rax, rax
0x18002a3c9  jz      short loc_18002A3E2
0x18002a3cb  lea     rdx, [rbp+3D0h+Buffer]
0x18002a3d2  mov     edi, 104h
0x18002a3d7  mov     ecx, edi
0x18002a3d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a3de  mov     esi, eax
0x18002a3e0  jmp     short loc_18002A3FD
0x18002a3e2  lea     rdx, [rbp+3D0h+Buffer]; lpBuffer
0x18002a3e9  mov     edi, 104h
0x18002a3ee  mov     ecx, edi; nBufferLength
0x18002a3f0  call    cs:__imp_GetTempPathW
0x18002a3f6  mov     esi, eax
0x18002a3f8  test    rbx, rbx
0x18002a3fb  jz      short loc_18002A406
0x18002a3fd  mov     rcx, rbx; hLibModule
0x18002a400  call    cs:__imp_FreeLibrary
0x18002a406  test    esi, esi
0x18002a408  jz      short loc_18002A411
0x18002a40a  lea     eax, [rsi+1]
0x18002a40d  cmp     eax, edi
0x18002a40f  jbe     short loc_18002A46C
0x18002a411  mov     eax, 7FFFFFFEh
0x18002a416  lea     rdx, PathName; "."
0x18002a41d  lea     rcx, [rbp+3D0h+Buffer]
0x18002a424  test    rax, rax
0x18002a427  jz      short loc_18002A448
0x18002a429  movzx   r8d, word ptr [rdx]
0x18002a42d  test    r8w, r8w
0x18002a431  jz      short loc_18002A448
0x18002a433  add     rdx, 2
0x18002a437  mov     [rcx], r8w
0x18002a43b  add     rcx, 2
0x18002a43f  dec     rax
0x18002a442  sub     rdi, 1
0x18002a446  jnz     short loc_18002A424
0x18002a448  mov     rax, rdi
0x18002a44b  neg     rax
0x18002a44e  sbb     eax, eax
0x18002a450  not     eax
0x18002a452  and     eax, 8007007Ah
0x18002a457  lea     rdx, [rcx-2]
0x18002a45b  test    rdi, rdi
0x18002a45e  cmovnz  rdx, rcx
0x18002a462  mov     [rdx], r13w
0x18002a466  jz      loc_18002A5C1
0x18002a46c  lea     r9, [rsp+4D0h+TempFileName]; lpTempFileName
0x18002a471  xor     r8d, r8d; uUnique
0x18002a474  lea     rdx, PrefixString; "xpf"
0x18002a47b  lea     rcx, [rbp+3D0h+Buffer]; lpPathName
0x18002a482  call    cs:__imp_GetTempFileNameW
0x18002a488  test    eax, eax
0x18002a48a  jnz     short loc_18002A4C7
0x18002a48c  lea     r9, [rsp+4D0h+TempFileName]; lpTempFileName
0x18002a491  xor     r8d, r8d; uUnique
0x18002a494  lea     rdx, PrefixString; "xpf"
0x18002a49b  lea     rcx, PathName; "."
0x18002a4a2  call    cs:__imp_GetTempFileNameW
0x18002a4a8  test    eax, eax
0x18002a4aa  jnz     short loc_18002A4C7
0x18002a4ac  call    cs:__imp_GetLastError
0x18002a4b2  test    eax, eax
0x18002a4b4  jle     loc_18002A5C1
0x18002a4ba  movzx   eax, ax
0x18002a4bd  or      eax, 80070000h
0x18002a4c2  jmp     loc_18002A5C1
0x18002a4c7  mov     [rsp+4D0h+hTemplateFile], r13; hTemplateFile
0x18002a4cc  mov     [rsp+4D0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002a4d4  mov     [rsp+4D0h+dwCreationDisposition], 2; dwCreationDisposition
0x18002a4dc  xor     r9d, r9d; lpSecurityAttributes
0x18002a4df  xor     r8d, r8d; dwShareMode
0x18002a4e2  mov     edx, 40000000h; dwDesiredAccess
0x18002a4e7  lea     rcx, [rsp+4D0h+TempFileName]; lpFileName
0x18002a4ec  call    cs:__imp_CreateFileW
0x18002a4f2  mov     rsi, rax
0x18002a4f5  test    rax, rax
0x18002a4f8  jnz     short loc_18002A512
0x18002a4fa  call    cs:__imp_GetLastError
0x18002a500  mov     ebx, eax
0x18002a502  mov     edi, 80070000h
0x18002a507  test    eax, eax
0x18002a509  jle     short loc_18002A556
0x18002a50b  movzx   ebx, ax
0x18002a50e  or      ebx, edi
0x18002a510  jmp     short loc_18002A556
0x18002a512  mov     ebx, r13d
0x18002a515  mov     [rsp+4D0h+NumberOfBytesWritten], r13d
0x18002a51a  mov     qword ptr [rsp+4D0h+dwCreationDisposition], r13; lpOverlapped
0x18002a51f  lea     r9, [rsp+4D0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002a524  mov     r8d, r15d; nNumberOfBytesToWrite
0x18002a527  mov     rdx, r14; lpBuffer
0x18002a52a  mov     rcx, rsi; hFile
0x18002a52d  call    cs:__imp_WriteFile
0x18002a533  mov     edi, 80070000h
0x18002a538  test    eax, eax
0x18002a53a  jnz     short loc_18002A54D
0x18002a53c  call    cs:__imp_GetLastError
0x18002a542  mov     ebx, eax
0x18002a544  test    eax, eax
0x18002a546  jle     short loc_18002A54D
0x18002a548  movzx   ebx, ax
0x18002a54b  or      ebx, edi
0x18002a54d  mov     rcx, rsi; hObject
0x18002a550  call    cs:__imp_CloseHandle
0x18002a556  test    ebx, ebx
0x18002a558  js      short loc_18002A5BF
0x18002a55a  lea     rax, [rsp+4D0h+TempFileName]
0x18002a55f  mov     qword ptr [rsp+4D0h+NumberOfBytesWritten], rax
0x18002a564  mov     [rsp+4D0h+var_488], r12
0x18002a569  lea     rax, aTdhloadmanifes; "TdhLoadManifest"
0x18002a570  mov     [rsp+4D0h+var_480], rax
0x18002a575  mov     [rsp+4D0h+var_478], r13
0x18002a57a  mov     [rsp+4D0h+var_470], r13b
0x18002a57f  lea     rcx, [rsp+4D0h+var_488]
0x18002a584  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18002a589  test    rax, rax
0x18002a58c  jz      short loc_18002A5B1
0x18002a58e  lea     rcx, [rsp+4D0h+var_488]
0x18002a593  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18002a598  lea     rcx, [rsp+4D0h+TempFileName]
0x18002a59d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a5a2  mov     ebx, eax
0x18002a5a4  test    eax, eax
0x18002a5a6  jz      short loc_18002A5B1
0x18002a5a8  jle     short loc_18002A5B4
0x18002a5aa  movzx   ebx, ax
0x18002a5ad  or      ebx, edi
0x18002a5af  jmp     short loc_18002A5B4
0x18002a5b1  mov     ebx, r13d
0x18002a5b4  lea     rcx, [rsp+4D0h+TempFileName]; lpFileName
0x18002a5b9  call    cs:__imp_DeleteFileW
0x18002a5bf  mov     eax, ebx
0x18002a5c1  mov     rcx, [rbp+3D0h+var_40]
0x18002a5c8  xor     rcx, rsp; StackCookie
0x18002a5cb  call    __security_check_cookie
0x18002a5d0  mov     rbx, [rsp+4D0h+arg_0]
0x18002a5d8  add     rsp, 4A0h
0x18002a5df  pop     r15
0x18002a5e1  pop     r14
0x18002a5e3  pop     r13
0x18002a5e5  pop     r12
0x18002a5e7  pop     rdi
0x18002a5e8  pop     rsi
0x18002a5e9  pop     rbp
0x18002a5ea  retn
```
