# ExecutionManagerHelper::CheckAndInit(void)

- ea: `0x1800134f0`
- end: `0x1800136f3`
- name: `?CheckAndInit@ExecutionManagerHelper@@AEAAJXZ`
- size: `515`
- prototype: `__int64 __fastcall(ExecutionManagerHelper *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x180004eb0`
- `0x180029c84`

## callees

- `0x1800134f0`
- `0x1800136fc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180013518`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001358d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180013602`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180013518`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001358d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180013602`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013562`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800135d7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013650`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013676`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001369c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013562`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800135d7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013650`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013676`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001369c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001353b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800135b0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180013625`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001353b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800135b0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180013625`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800136b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800136b4`

## string_xrefs

- `0x18001350b`: `EmClient.dll`
- `0x180013580`: `RmClient.dll`
- `0x180013558`: `CancelAgentRequests`
- `0x1800135f5`: `EmSvcs.dll`
- `0x1800135cd`: `RmAccessCheck`
- `0x18001366f`: `CreateBackgroundWorkerManager`
- `0x180013646`: `CreateExecutionManager`
- `0x180013695`: `CreateDebugManager`

## pseudocode

```c
__int64 __fastcall ExecutionManagerHelper::CheckAndInit(ExecutionManagerHelper *this)
{
  signed int v1; // ebx
  HMODULE Library; // rbx
  HMODULE v3; // rbx
  HMODULE v4; // rbx
  signed int LastError; // eax

  if ( byte_180096B98 )
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
      qword_180096BA0 = (__int64)GetProcAddress(Library, "CancelAgentRequests");
      if ( !qword_180096BA0 )
        goto LABEL_26;
    }
    v3 = LoadLibraryExW(L"RmClient.dll", 0, 0x800u);
    if ( v3 == qword_180096B88 )
    {
      v3 = qword_180096B88;
    }
    else
    {
      if ( qword_180096B88 )
        FreeLibrary(qword_180096B88);
      qword_180096B88 = v3;
    }
    if ( v3 )
    {
      qword_180096BA8 = (__int64)GetProcAddress(v3, "RmAccessCheck");
      if ( !qword_180096BA8 )
        goto LABEL_26;
    }
    v4 = LoadLibraryExW(L"EmSvcs.dll", 0, 0x800u);
    if ( v4 == qword_180096B90 )
    {
      v4 = qword_180096B90;
    }
    else
    {
      if ( qword_180096B90 )
        FreeLibrary(qword_180096B90);
      qword_180096B90 = v4;
    }
    if ( !v4
      || (qword_180096BB0 = (__int64)GetProcAddress(v4, "CreateExecutionManager")) != 0
      && (qword_180096BB8 = (__int64)GetProcAddress(qword_180096B90, "CreateBackgroundWorkerManager")) != 0
      && (qword_180096BC0 = (__int64)GetProcAddress(qword_180096B90, "CreateDebugManager")) != 0 )
    {
      v1 = 0;
      byte_180096B98 = 1;
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
0x1800134f0  push    rbx
0x1800134f2  sub     rsp, 20h
0x1800134f6  cmp     cs:byte_180096B98, 0
0x1800134fd  jz      short loc_180013509
0x1800134ff  mov     ebx, 1
0x180013504  jmp     loc_1800136EA
0x180013509  xor     edx, edx; hFile
0x18001350b  lea     rcx, aEmclientDll; "EmClient.dll"
0x180013512  mov     r8d, 800h; dwFlags
0x180013518  call    cs:__imp_LoadLibraryExW
0x18001351f  nop     dword ptr [rax+rax+00h]
0x180013524  mov     rbx, rax
0x180013527  mov     rax, cs:?s_ExecutionManagerHelper@@3VExecutionManagerHelper@@A; ExecutionManagerHelper s_ExecutionManagerHelper
0x18001352e  cmp     rbx, rax
0x180013531  jz      short loc_180013550
0x180013533  test    rax, rax
0x180013536  jz      short loc_180013547
0x180013538  mov     rcx, rax; hLibModule
0x18001353b  call    cs:__imp_FreeLibrary
0x180013542  nop     dword ptr [rax+rax+00h]
0x180013547  mov     cs:?s_ExecutionManagerHelper@@3VExecutionManagerHelper@@A, rbx; ExecutionManagerHelper s_ExecutionManagerHelper
0x18001354e  jmp     short loc_180013553
0x180013550  mov     rbx, rax
0x180013553  test    rbx, rbx
0x180013556  jz      short loc_18001357E
0x180013558  lea     rdx, aCancelagentreq; "CancelAgentRequests"
0x18001355f  mov     rcx, rbx; hModule
0x180013562  call    cs:__imp_GetProcAddress
0x180013569  nop     dword ptr [rax+rax+00h]
0x18001356e  mov     cs:qword_180096BA0, rax
0x180013575  test    rax, rax
0x180013578  jz      loc_1800136B4
0x18001357e  xor     edx, edx; hFile
0x180013580  lea     rcx, aRmclientDll; "RmClient.dll"
0x180013587  mov     r8d, 800h; dwFlags
0x18001358d  call    cs:__imp_LoadLibraryExW
0x180013594  nop     dword ptr [rax+rax+00h]
0x180013599  mov     rbx, rax
0x18001359c  mov     rax, cs:qword_180096B88
0x1800135a3  cmp     rbx, rax
0x1800135a6  jz      short loc_1800135C5
0x1800135a8  test    rax, rax
0x1800135ab  jz      short loc_1800135BC
0x1800135ad  mov     rcx, rax; hLibModule
0x1800135b0  call    cs:__imp_FreeLibrary
0x1800135b7  nop     dword ptr [rax+rax+00h]
0x1800135bc  mov     cs:qword_180096B88, rbx
0x1800135c3  jmp     short loc_1800135C8
0x1800135c5  mov     rbx, rax
0x1800135c8  test    rbx, rbx
0x1800135cb  jz      short loc_1800135F3
0x1800135cd  lea     rdx, aRmaccesscheck; "RmAccessCheck"
0x1800135d4  mov     rcx, rbx; hModule
0x1800135d7  call    cs:__imp_GetProcAddress
0x1800135de  nop     dword ptr [rax+rax+00h]
0x1800135e3  mov     cs:qword_180096BA8, rax
0x1800135ea  test    rax, rax
0x1800135ed  jz      loc_1800136B4
0x1800135f3  xor     edx, edx; hFile
0x1800135f5  lea     rcx, aEmsvcsDll; "EmSvcs.dll"
0x1800135fc  mov     r8d, 800h; dwFlags
0x180013602  call    cs:__imp_LoadLibraryExW
0x180013609  nop     dword ptr [rax+rax+00h]
0x18001360e  mov     rbx, rax
0x180013611  mov     rax, cs:qword_180096B90
0x180013618  cmp     rbx, rax
0x18001361b  jz      short loc_18001363A
0x18001361d  test    rax, rax
0x180013620  jz      short loc_180013631
0x180013622  mov     rcx, rax; hLibModule
0x180013625  call    cs:__imp_FreeLibrary
0x18001362c  nop     dword ptr [rax+rax+00h]
0x180013631  mov     cs:qword_180096B90, rbx
0x180013638  jmp     short loc_18001363D
0x18001363a  mov     rbx, rax
0x18001363d  test    rbx, rbx
0x180013640  jz      loc_1800136E1
0x180013646  lea     rdx, aCreateexecutio; "CreateExecutionManager"
0x18001364d  mov     rcx, rbx; hModule
0x180013650  call    cs:__imp_GetProcAddress
0x180013657  nop     dword ptr [rax+rax+00h]
0x18001365c  mov     cs:qword_180096BB0, rax
0x180013663  test    rax, rax
0x180013666  jz      short loc_1800136B4
0x180013668  mov     rcx, cs:qword_180096B90; hModule
0x18001366f  lea     rdx, aCreatebackgrou; "CreateBackgroundWorkerManager"
0x180013676  call    cs:__imp_GetProcAddress
0x18001367d  nop     dword ptr [rax+rax+00h]
0x180013682  mov     cs:qword_180096BB8, rax
0x180013689  test    rax, rax
0x18001368c  jz      short loc_1800136B4
0x18001368e  mov     rcx, cs:qword_180096B90; hModule
0x180013695  lea     rdx, aCreatedebugman; "CreateDebugManager"
0x18001369c  call    cs:__imp_GetProcAddress
0x1800136a3  nop     dword ptr [rax+rax+00h]
0x1800136a8  mov     cs:qword_180096BC0, rax
0x1800136af  test    rax, rax
0x1800136b2  jnz     short loc_1800136E1
0x1800136b4  call    cs:__imp_GetLastError
0x1800136bb  nop     dword ptr [rax+rax+00h]
0x1800136c0  mov     ebx, eax
0x1800136c2  test    eax, eax
0x1800136c4  jle     short loc_1800136CF
0x1800136c6  movzx   ebx, ax
0x1800136c9  or      ebx, 80070000h
0x1800136cf  test    ebx, ebx
0x1800136d1  jns     short loc_1800136EA
0x1800136d3  lea     rcx, ?s_ExecutionManagerHelper@@3VExecutionManagerHelper@@A; this
0x1800136da  call    ?Uninitialize@ExecutionManagerHelper@@AEAAXXZ; ExecutionManagerHelper::Uninitialize(void)
0x1800136df  jmp     short loc_1800136EA
0x1800136e1  xor     ebx, ebx
0x1800136e3  mov     cs:byte_180096B98, 1
0x1800136ea  mov     eax, ebx
0x1800136ec  add     rsp, 20h
0x1800136f0  pop     rbx
0x1800136f1  retn
```
