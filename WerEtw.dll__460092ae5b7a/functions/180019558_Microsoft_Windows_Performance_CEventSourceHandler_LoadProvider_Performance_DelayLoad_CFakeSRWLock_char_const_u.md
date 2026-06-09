# Microsoft::Windows::Performance::CEventSourceHandler::LoadProvider<Performance::DelayLoad::CFakeSRWLock>(char const *,ulong,Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock> &)

- ea: `0x180019558`
- end: `0x1800197eb`
- name: `??$LoadProvider@VCFakeSRWLock@DelayLoad@Performance@@@CEventSourceHandler@Performance@Windows@Microsoft@@AEAAJPEBDKAEAV?$CDelayLoadedModule@VCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@1@@Z`
- size: `659`
- prototype: `signed int __fastcall(__int64, const void *, DWORD, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800197f4`

## callees

- `0x180001870`
- `0x1800163cc`
- `0x180019558`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800196ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800196fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001973c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800196ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800196fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001973c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180019600`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180019600`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800195a0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800195a0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800195c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800195c0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800196ec`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800196ec`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180019682`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800196a2`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180019682`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800196a2`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800197b9`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800197b9`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001972d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001972d`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x1800195f0`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x1800195f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019750`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019750`

## string_xrefs

- `0x180019599`: `kernelbase.dll`
- `0x1800195b6`: `GetTempPath2W`
- `0x180019769`: `TdhLoadManifest`

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
0x180019558  mov     [rsp-8+arg_0], rbx
0x18001955d  push    rbp
0x18001955e  push    rsi
0x18001955f  push    rdi
0x180019560  push    r12
0x180019562  push    r13
0x180019564  push    r14
0x180019566  push    r15
0x180019568  lea     rbp, [rsp-3A0h]
0x180019570  sub     rsp, 4A0h
0x180019577  mov     rax, cs:__security_cookie
0x18001957e  xor     rax, rsp
0x180019581  mov     [rbp+3D0h+var_40], rax
0x180019588  mov     r12, r9
0x18001958b  mov     r15d, r8d
0x18001958e  mov     r14, rdx
0x180019591  xor     edx, edx; hFile
0x180019593  mov     r8d, 800h; dwFlags
0x180019599  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800195a0  call    cs:__imp_LoadLibraryExW
0x1800195a6  mov     rbx, rax
0x1800195a9  mov     qword ptr [rsp+4D0h+NumberOfBytesWritten], rax
0x1800195ae  xor     r13d, r13d
0x1800195b1  test    rax, rax
0x1800195b4  jz      short loc_1800195E2
0x1800195b6  lea     rdx, aGettemppath2w; "GetTempPath2W"
0x1800195bd  mov     rcx, rax; hModule
0x1800195c0  call    cs:__imp_GetProcAddress
0x1800195c6  test    rax, rax
0x1800195c9  jz      short loc_1800195E2
0x1800195cb  lea     rdx, [rbp+3D0h+Buffer]
0x1800195d2  mov     edi, 104h
0x1800195d7  mov     ecx, edi
0x1800195d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800195de  mov     esi, eax
0x1800195e0  jmp     short loc_1800195FD
0x1800195e2  lea     rdx, [rbp+3D0h+Buffer]; lpBuffer
0x1800195e9  mov     edi, 104h
0x1800195ee  mov     ecx, edi; nBufferLength
0x1800195f0  call    cs:__imp_GetTempPathW
0x1800195f6  mov     esi, eax
0x1800195f8  test    rbx, rbx
0x1800195fb  jz      short loc_180019606
0x1800195fd  mov     rcx, rbx; hLibModule
0x180019600  call    cs:__imp_FreeLibrary
0x180019606  test    esi, esi
0x180019608  jz      short loc_180019611
0x18001960a  lea     eax, [rsi+1]
0x18001960d  cmp     eax, edi
0x18001960f  jbe     short loc_18001966C
0x180019611  mov     eax, 7FFFFFFEh
0x180019616  lea     rdx, PathName; "."
0x18001961d  lea     rcx, [rbp+3D0h+Buffer]
0x180019624  test    rax, rax
0x180019627  jz      short loc_180019648
0x180019629  movzx   r8d, word ptr [rdx]
0x18001962d  test    r8w, r8w
0x180019631  jz      short loc_180019648
0x180019633  add     rdx, 2
0x180019637  mov     [rcx], r8w
0x18001963b  add     rcx, 2
0x18001963f  dec     rax
0x180019642  sub     rdi, 1
0x180019646  jnz     short loc_180019624
0x180019648  mov     rax, rdi
0x18001964b  neg     rax
0x18001964e  sbb     eax, eax
0x180019650  not     eax
0x180019652  and     eax, 8007007Ah
0x180019657  lea     rdx, [rcx-2]
0x18001965b  test    rdi, rdi
0x18001965e  cmovnz  rdx, rcx
0x180019662  mov     [rdx], r13w
0x180019666  jz      loc_1800197C1
0x18001966c  lea     r9, [rsp+4D0h+TempFileName]; lpTempFileName
0x180019671  xor     r8d, r8d; uUnique
0x180019674  lea     rdx, PrefixString; "xpf"
0x18001967b  lea     rcx, [rbp+3D0h+Buffer]; lpPathName
0x180019682  call    cs:__imp_GetTempFileNameW
0x180019688  test    eax, eax
0x18001968a  jnz     short loc_1800196C7
0x18001968c  lea     r9, [rsp+4D0h+TempFileName]; lpTempFileName
0x180019691  xor     r8d, r8d; uUnique
0x180019694  lea     rdx, PrefixString; "xpf"
0x18001969b  lea     rcx, PathName; "."
0x1800196a2  call    cs:__imp_GetTempFileNameW
0x1800196a8  test    eax, eax
0x1800196aa  jnz     short loc_1800196C7
0x1800196ac  call    cs:__imp_GetLastError
0x1800196b2  test    eax, eax
0x1800196b4  jle     loc_1800197C1
0x1800196ba  movzx   eax, ax
0x1800196bd  or      eax, 80070000h
0x1800196c2  jmp     loc_1800197C1
0x1800196c7  mov     [rsp+4D0h+hTemplateFile], r13; hTemplateFile
0x1800196cc  mov     [rsp+4D0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800196d4  mov     [rsp+4D0h+dwCreationDisposition], 2; dwCreationDisposition
0x1800196dc  xor     r9d, r9d; lpSecurityAttributes
0x1800196df  xor     r8d, r8d; dwShareMode
0x1800196e2  mov     edx, 40000000h; dwDesiredAccess
0x1800196e7  lea     rcx, [rsp+4D0h+TempFileName]; lpFileName
0x1800196ec  call    cs:__imp_CreateFileW
0x1800196f2  mov     rsi, rax
0x1800196f5  test    rax, rax
0x1800196f8  jnz     short loc_180019712
0x1800196fa  call    cs:__imp_GetLastError
0x180019700  mov     ebx, eax
0x180019702  mov     edi, 80070000h
0x180019707  test    eax, eax
0x180019709  jle     short loc_180019756
0x18001970b  movzx   ebx, ax
0x18001970e  or      ebx, edi
0x180019710  jmp     short loc_180019756
0x180019712  mov     ebx, r13d
0x180019715  mov     [rsp+4D0h+NumberOfBytesWritten], r13d
0x18001971a  mov     qword ptr [rsp+4D0h+dwCreationDisposition], r13; lpOverlapped
0x18001971f  lea     r9, [rsp+4D0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180019724  mov     r8d, r15d; nNumberOfBytesToWrite
0x180019727  mov     rdx, r14; lpBuffer
0x18001972a  mov     rcx, rsi; hFile
0x18001972d  call    cs:__imp_WriteFile
0x180019733  mov     edi, 80070000h
0x180019738  test    eax, eax
0x18001973a  jnz     short loc_18001974D
0x18001973c  call    cs:__imp_GetLastError
0x180019742  mov     ebx, eax
0x180019744  test    eax, eax
0x180019746  jle     short loc_18001974D
0x180019748  movzx   ebx, ax
0x18001974b  or      ebx, edi
0x18001974d  mov     rcx, rsi; hObject
0x180019750  call    cs:__imp_CloseHandle
0x180019756  test    ebx, ebx
0x180019758  js      short loc_1800197BF
0x18001975a  lea     rax, [rsp+4D0h+TempFileName]
0x18001975f  mov     qword ptr [rsp+4D0h+NumberOfBytesWritten], rax
0x180019764  mov     [rsp+4D0h+var_488], r12
0x180019769  lea     rax, aTdhloadmanifes; "TdhLoadManifest"
0x180019770  mov     [rsp+4D0h+var_480], rax
0x180019775  mov     [rsp+4D0h+var_478], r13
0x18001977a  mov     [rsp+4D0h+var_470], r13b
0x18001977f  lea     rcx, [rsp+4D0h+var_488]
0x180019784  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x180019789  test    rax, rax
0x18001978c  jz      short loc_1800197B1
0x18001978e  lea     rcx, [rsp+4D0h+var_488]
0x180019793  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x180019798  lea     rcx, [rsp+4D0h+TempFileName]
0x18001979d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800197a2  mov     ebx, eax
0x1800197a4  test    eax, eax
0x1800197a6  jz      short loc_1800197B1
0x1800197a8  jle     short loc_1800197B4
0x1800197aa  movzx   ebx, ax
0x1800197ad  or      ebx, edi
0x1800197af  jmp     short loc_1800197B4
0x1800197b1  mov     ebx, r13d
0x1800197b4  lea     rcx, [rsp+4D0h+TempFileName]; lpFileName
0x1800197b9  call    cs:__imp_DeleteFileW
0x1800197bf  mov     eax, ebx
0x1800197c1  mov     rcx, [rbp+3D0h+var_40]
0x1800197c8  xor     rcx, rsp; StackCookie
0x1800197cb  call    __security_check_cookie
0x1800197d0  mov     rbx, [rsp+4D0h+arg_0]
0x1800197d8  add     rsp, 4A0h
0x1800197df  pop     r15
0x1800197e1  pop     r14
0x1800197e3  pop     r13
0x1800197e5  pop     r12
0x1800197e7  pop     rdi
0x1800197e8  pop     rsi
0x1800197e9  pop     rbp
0x1800197ea  retn
```
