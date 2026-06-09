# ExecutionManagerHelper::CheckAndInit(void)

- ea: `0x180012b10`
- end: `0x180012cca`
- name: `?CheckAndInit@ExecutionManagerHelper@@AEAAJXZ`
- size: `442`
- prototype: `__int64 __fastcall(ExecutionManagerHelper *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x180004d00`
- `0x180027afc`

## callees

- `0x180012b10`
- `0x180012cd0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180012b38`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180012b9b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180012bfe`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180012b38`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180012b9b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180012bfe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012b76`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012bd9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012c40`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012c60`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012c80`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012b76`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012bd9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012c40`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012c60`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012c80`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180012b55`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180012bb8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180012c1b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180012b55`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180012bb8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180012c1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012c92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012c92`

## string_xrefs

- `0x180012b2b`: `EmClient.dll`
- `0x180012b8e`: `RmClient.dll`
- `0x180012b6c`: `CancelAgentRequests`
- `0x180012bf1`: `EmSvcs.dll`
- `0x180012bcf`: `RmAccessCheck`
- `0x180012c59`: `CreateBackgroundWorkerManager`
- `0x180012c36`: `CreateExecutionManager`
- `0x180012c79`: `CreateDebugManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall ExecutionManagerHelper::CheckAndInit(ExecutionManagerHelper *this)
{
  signed int v1; // ebx
  HMODULE Library; // rbx
  HMODULE v3; // rbx
  HMODULE v4; // rbx
  signed int LastError; // eax

  if ( byte_180090B98 )
  {
    return 1;
  }
  else
  {
    Library = LoadLibraryExW(L"EmClient.dll", 0, 0x800u);
    if ( Library == s_ExecutionManagerHelper )
    {
      Library = s_ExecutionManagerHelper;
    }
    else
    {
      if ( s_ExecutionManagerHelper )
        FreeLibrary(s_ExecutionManagerHelper);
      s_ExecutionManagerHelper = Library;
    }
    if ( Library )
    {
      qword_180090BA0 = (__int64)GetProcAddress(Library, "CancelAgentRequests");
      if ( !qword_180090BA0 )
        goto LABEL_26;
    }
    v3 = LoadLibraryExW(L"RmClient.dll", 0, 0x800u);
    if ( v3 == qword_180090B88 )
    {
      v3 = qword_180090B88;
    }
    else
    {
      if ( qword_180090B88 )
        FreeLibrary(qword_180090B88);
      qword_180090B88 = v3;
    }
    if ( v3 )
    {
      qword_180090BA8 = (__int64)GetProcAddress(v3, "RmAccessCheck");
      if ( !qword_180090BA8 )
        goto LABEL_26;
    }
    v4 = LoadLibraryExW(L"EmSvcs.dll", 0, 0x800u);
    if ( v4 == qword_180090B90 )
    {
      v4 = qword_180090B90;
    }
    else
    {
      if ( qword_180090B90 )
        FreeLibrary(qword_180090B90);
      qword_180090B90 = v4;
    }
    if ( !v4
      || (qword_180090BB0 = (__int64)GetProcAddress(v4, "CreateExecutionManager")) != 0
      && (qword_180090BB8 = (__int64)GetProcAddress(qword_180090B90, "CreateBackgroundWorkerManager")) != 0
      && (qword_180090BC0 = (__int64)GetProcAddress(qword_180090B90, "CreateDebugManager")) != 0 )
    {
      v1 = 0;
      byte_180090B98 = 1;
    }
    else
    {
LABEL_26:
      LastError = GetLastError();
      v1 = LastError;
      if ( LastError > 0 )
        v1 = (unsigned __int16)LastError | 0x80070000;
      if ( v1 < 0 )
        ExecutionManagerHelper::Uninitialize((ExecutionManagerHelper *)&s_ExecutionManagerHelper);
    }
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180012b10  push    rbx
0x180012b12  sub     rsp, 20h
0x180012b16  cmp     cs:byte_180090B98, 0
0x180012b1d  jz      short loc_180012B29
0x180012b1f  mov     ebx, 1
0x180012b24  jmp     loc_180012CC2
0x180012b29  xor     edx, edx; hFile
0x180012b2b  lea     rcx, aEmclientDll; "EmClient.dll"
0x180012b32  mov     r8d, 800h; dwFlags
0x180012b38  call    cs:__imp_LoadLibraryExW
0x180012b3e  mov     rbx, rax
0x180012b41  mov     rax, cs:?s_ExecutionManagerHelper@@3VExecutionManagerHelper@@A; ExecutionManagerHelper s_ExecutionManagerHelper
0x180012b48  cmp     rbx, rax
0x180012b4b  jz      short loc_180012B64
0x180012b4d  test    rax, rax
0x180012b50  jz      short loc_180012B5B
0x180012b52  mov     rcx, rax; hLibModule
0x180012b55  call    cs:__imp_FreeLibrary
0x180012b5b  mov     cs:?s_ExecutionManagerHelper@@3VExecutionManagerHelper@@A, rbx; ExecutionManagerHelper s_ExecutionManagerHelper
0x180012b62  jmp     short loc_180012B67
0x180012b64  mov     rbx, rax
0x180012b67  test    rbx, rbx
0x180012b6a  jz      short loc_180012B8C
0x180012b6c  lea     rdx, aCancelagentreq; "CancelAgentRequests"
0x180012b73  mov     rcx, rbx; hModule
0x180012b76  call    cs:__imp_GetProcAddress
0x180012b7c  mov     cs:qword_180090BA0, rax
0x180012b83  test    rax, rax
0x180012b86  jz      loc_180012C92
0x180012b8c  xor     edx, edx; hFile
0x180012b8e  lea     rcx, aRmclientDll; "RmClient.dll"
0x180012b95  mov     r8d, 800h; dwFlags
0x180012b9b  call    cs:__imp_LoadLibraryExW
0x180012ba1  mov     rbx, rax
0x180012ba4  mov     rax, cs:qword_180090B88
0x180012bab  cmp     rbx, rax
0x180012bae  jz      short loc_180012BC7
0x180012bb0  test    rax, rax
0x180012bb3  jz      short loc_180012BBE
0x180012bb5  mov     rcx, rax; hLibModule
0x180012bb8  call    cs:__imp_FreeLibrary
0x180012bbe  mov     cs:qword_180090B88, rbx
0x180012bc5  jmp     short loc_180012BCA
0x180012bc7  mov     rbx, rax
0x180012bca  test    rbx, rbx
0x180012bcd  jz      short loc_180012BEF
0x180012bcf  lea     rdx, aRmaccesscheck; "RmAccessCheck"
0x180012bd6  mov     rcx, rbx; hModule
0x180012bd9  call    cs:__imp_GetProcAddress
0x180012bdf  mov     cs:qword_180090BA8, rax
0x180012be6  test    rax, rax
0x180012be9  jz      loc_180012C92
0x180012bef  xor     edx, edx; hFile
0x180012bf1  lea     rcx, aEmsvcsDll; "EmSvcs.dll"
0x180012bf8  mov     r8d, 800h; dwFlags
0x180012bfe  call    cs:__imp_LoadLibraryExW
0x180012c04  mov     rbx, rax
0x180012c07  mov     rax, cs:qword_180090B90
0x180012c0e  cmp     rbx, rax
0x180012c11  jz      short loc_180012C2A
0x180012c13  test    rax, rax
0x180012c16  jz      short loc_180012C21
0x180012c18  mov     rcx, rax; hLibModule
0x180012c1b  call    cs:__imp_FreeLibrary
0x180012c21  mov     cs:qword_180090B90, rbx
0x180012c28  jmp     short loc_180012C2D
0x180012c2a  mov     rbx, rax
0x180012c2d  test    rbx, rbx
0x180012c30  jz      loc_180012CB9
0x180012c36  lea     rdx, aCreateexecutio; "CreateExecutionManager"
0x180012c3d  mov     rcx, rbx; hModule
0x180012c40  call    cs:__imp_GetProcAddress
0x180012c46  mov     cs:qword_180090BB0, rax
0x180012c4d  test    rax, rax
0x180012c50  jz      short loc_180012C92
0x180012c52  mov     rcx, cs:qword_180090B90; hModule
0x180012c59  lea     rdx, aCreatebackgrou; "CreateBackgroundWorkerManager"
0x180012c60  call    cs:__imp_GetProcAddress
0x180012c66  mov     cs:qword_180090BB8, rax
0x180012c6d  test    rax, rax
0x180012c70  jz      short loc_180012C92
0x180012c72  mov     rcx, cs:qword_180090B90; hModule
0x180012c79  lea     rdx, aCreatedebugman; "CreateDebugManager"
0x180012c80  call    cs:__imp_GetProcAddress
0x180012c86  mov     cs:qword_180090BC0, rax
0x180012c8d  test    rax, rax
0x180012c90  jnz     short loc_180012CB9
0x180012c92  call    cs:__imp_GetLastError
0x180012c98  mov     ebx, eax
0x180012c9a  test    eax, eax
0x180012c9c  jle     short loc_180012CA7
0x180012c9e  movzx   ebx, ax
0x180012ca1  or      ebx, 80070000h
0x180012ca7  test    ebx, ebx
0x180012ca9  jns     short loc_180012CC2
0x180012cab  lea     rcx, ?s_ExecutionManagerHelper@@3VExecutionManagerHelper@@A; this
0x180012cb2  call    ?Uninitialize@ExecutionManagerHelper@@AEAAXXZ; ExecutionManagerHelper::Uninitialize(void)
0x180012cb7  jmp     short loc_180012CC2
0x180012cb9  xor     ebx, ebx
0x180012cbb  mov     cs:byte_180090B98, 1
0x180012cc2  mov     eax, ebx
0x180012cc4  add     rsp, 20h
0x180012cc8  pop     rbx
0x180012cc9  retn
```
