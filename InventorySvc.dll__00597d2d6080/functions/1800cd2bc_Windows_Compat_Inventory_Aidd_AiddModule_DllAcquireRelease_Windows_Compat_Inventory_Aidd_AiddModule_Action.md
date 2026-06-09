# Windows::Compat::Inventory::Aidd::AiddModule::DllAcquireRelease(Windows::Compat::Inventory::Aidd::AiddModule::Action)

- ea: `0x1800cd2bc`
- end: `0x1800cd54c`
- name: `?DllAcquireRelease@AiddModule@Aidd@Inventory@Compat@Windows@@AEAAJW4Action@12345@@Z`
- size: `656`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800cd590`
- `0x1800cd6e0`

## callees

- `0x1800152d0`
- `0x1800cd2bc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800cd38e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800cd3a2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800cd3b6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800cd38e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800cd3a2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800cd3b6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800cd30d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800cd30d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800cd329`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800cd421`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800cd498`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800cd329`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800cd421`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800cd498`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800cd2dd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800cd2dd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cd4c9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cd4fe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cd52e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cd4c9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cd4fe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cd52e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800cd331`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800cd429`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800cd4a0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800cd331`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800cd429`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800cd4a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cd31e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cd340`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cd366`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cd3e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cd416`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cd44f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cd48d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cd31e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cd340`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cd366`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cd3e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cd416`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cd44f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cd48d`

## string_xrefs

- `0x1800cd4dc`: `RefCount is already 0 [%#x]`
- `0x1800cd306`: `aidd.dll`
- `0x1800cd34a`: `LoadLibraryExW aidd failed [%d]`
- `0x1800cd357`: `Windows::Compat::Inventory::Aidd::AiddModule::DllAcquireRelease`
- `0x1800cd3fd`: `Windows::Compat::Inventory::Aidd::AiddModule::DllAcquireRelease`
- `0x1800cd4e9`: `Windows::Compat::Inventory::Aidd::AiddModule::DllAcquireRelease`
- `0x1800cd519`: `Windows::Compat::Inventory::Aidd::AiddModule::DllAcquireRelease`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Inventory::Aidd::AiddModule::DllAcquireRelease(__int64 a1, int a2)
{
  int v4; // eax
  HMODULE Library; // rsi
  HMODULE v6; // rbp
  DWORD LastError; // ebx
  DWORD v8; // eax
  signed int v9; // eax
  unsigned int v10; // ebx
  FARPROC ProcAddress; // rax
  DWORD v12; // eax
  HMODULE v13; // rsi
  DWORD v14; // ebx
  signed int v15; // eax
  int v16; // eax
  HMODULE v17; // rsi
  DWORD v18; // ebx

  AcquireSRWLockExclusive(&stru_1800FF8B8);
  if ( !a2 )
  {
    v4 = dword_1800FF8B0;
    if ( !dword_1800FF8B0 )
    {
      Library = LoadLibraryExW(L"aidd.dll", 0, 0x800u);
      v6 = *(HMODULE *)a1;
      if ( *(_QWORD *)a1 )
      {
        LastError = GetLastError();
        FreeLibrary(v6);
        SetLastError(LastError);
      }
      *(_QWORD *)a1 = Library;
      if ( !Library )
      {
        v8 = GetLastError();
        AslLogCallPrintf(
          1,
          "Windows::Compat::Inventory::Aidd::AiddModule::DllAcquireRelease",
          178,
          "LoadLibraryExW aidd failed [%d]",
          v8);
        v9 = GetLastError();
        v10 = v9;
        if ( v9 > 0 )
          v10 = (unsigned __int16)v9 | 0x80070000;
        goto LABEL_26;
      }
      *(_QWORD *)(a1 + 16) = GetProcAddress(Library, "AiddInitialize");
      *(_QWORD *)(a1 + 24) = GetProcAddress(*(HMODULE *)a1, "AiddUninitialize");
      ProcAddress = GetProcAddress(*(HMODULE *)a1, "AiddIsEnabled");
      *(_QWORD *)(a1 + 8) = ProcAddress;
      if ( !*(_QWORD *)(a1 + 16) || !*(_QWORD *)(a1 + 24) || !ProcAddress )
      {
        v12 = GetLastError();
        AslLogCallPrintf(
          1,
          "Windows::Compat::Inventory::Aidd::AiddModule::DllAcquireRelease",
          190,
          "GetProcAddress failed [%d]",
          v12);
        v13 = *(HMODULE *)a1;
        if ( *(_QWORD *)a1 )
        {
          v14 = GetLastError();
          FreeLibrary(v13);
          SetLastError(v14);
        }
        *(_QWORD *)a1 = 0;
        *(_QWORD *)(a1 + 16) = 0;
        *(_QWORD *)(a1 + 24) = 0;
        *(_QWORD *)(a1 + 8) = 0;
        v15 = GetLastError();
        if ( v15 > 0 )
          v15 = (unsigned __int16)v15 | 0x80070000;
        v10 = v15;
        goto LABEL_26;
      }
      v4 = dword_1800FF8B0;
    }
    dword_1800FF8B0 = v4 + 1;
    goto LABEL_24;
  }
  if ( a2 == 1 )
  {
    v16 = dword_1800FF8B0;
    if ( dword_1800FF8B0 <= 0 )
    {
      v10 = -2147467259;
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::Aidd::AiddModule::DllAcquireRelease",
        211,
        "RefCount is already 0 [%#x]",
        -2147467259);
LABEL_26:
      ReleaseSRWLockExclusive(&stru_1800FF8B8);
      return v10;
    }
    --dword_1800FF8B0;
    if ( v16 == 1 )
    {
      v17 = *(HMODULE *)a1;
      if ( *(_QWORD *)a1 )
      {
        v18 = GetLastError();
        FreeLibrary(v17);
        SetLastError(v18);
      }
      *(_QWORD *)a1 = 0;
      *(_QWORD *)(a1 + 16) = 0;
      *(_QWORD *)(a1 + 24) = 0;
      *(_QWORD *)(a1 + 8) = 0;
    }
LABEL_24:
    ReleaseSRWLockExclusive(&stru_1800FF8B8);
    return 0;
  }
  AslLogCallPrintf(1, "Windows::Compat::Inventory::Aidd::AiddModule::DllAcquireRelease", 225, "Invalid action [%d]", a2);
  ReleaseSRWLockExclusive(&stru_1800FF8B8);
  return 160;
}

```

## disassembly

```asm
0x1800cd2bc  mov     [rsp+arg_0], rbx
0x1800cd2c1  mov     [rsp+arg_18], rbp
0x1800cd2c6  push    rsi
0x1800cd2c7  push    rdi
0x1800cd2c8  push    r15
0x1800cd2ca  sub     rsp, 30h
0x1800cd2ce  mov     ebx, edx
0x1800cd2d0  mov     rdi, rcx
0x1800cd2d3  lea     r15, stru_1800FF8B8
0x1800cd2da  mov     rcx, r15; SRWLock
0x1800cd2dd  call    cs:__imp_AcquireSRWLockExclusive
0x1800cd2e3  mov     [rsp+48h+arg_10], r15
0x1800cd2e8  test    ebx, ebx
0x1800cd2ea  jnz     loc_1800CD468
0x1800cd2f0  mov     eax, cs:dword_1800FF8B0
0x1800cd2f6  test    eax, eax
0x1800cd2f8  jnz     loc_1800CD3D9
0x1800cd2fe  xor     edx, edx; hFile
0x1800cd300  mov     r8d, 800h; dwFlags
0x1800cd306  lea     rcx, aAiddDll; "aidd.dll"
0x1800cd30d  call    cs:__imp_LoadLibraryExW
0x1800cd313  mov     rsi, rax
0x1800cd316  mov     rbp, [rdi]
0x1800cd319  test    rbp, rbp
0x1800cd31c  jz      short loc_1800CD338
0x1800cd31e  call    cs:__imp_GetLastError
0x1800cd324  mov     ebx, eax
0x1800cd326  mov     rcx, rbp; hLibModule
0x1800cd329  call    cs:__imp_FreeLibrary
0x1800cd32f  mov     ecx, ebx; dwErrCode
0x1800cd331  call    cs:__imp_SetLastError
0x1800cd337  nop
0x1800cd338  mov     [rdi], rsi
0x1800cd33b  test    rsi, rsi
0x1800cd33e  jnz     short loc_1800CD384
0x1800cd340  call    cs:__imp_GetLastError
0x1800cd346  mov     [rsp+48h+var_28], eax
0x1800cd34a  lea     r9, aLoadlibraryexw_0; "LoadLibraryExW aidd failed [%d]"
0x1800cd351  mov     r8d, 0B2h
0x1800cd357  lea     rdx, aWindowsCompatI_2; "Windows::Compat::Inventory::Aidd::AiddM"...
0x1800cd35e  lea     ecx, [rsi+1]
0x1800cd361  call    AslLogCallPrintf
0x1800cd366  call    cs:__imp_GetLastError
0x1800cd36c  mov     ebx, eax
0x1800cd36e  test    eax, eax
0x1800cd370  jle     loc_1800CD4FB
0x1800cd376  movzx   ebx, ax
0x1800cd379  or      ebx, 80070000h
0x1800cd37f  jmp     loc_1800CD4FB
0x1800cd384  lea     rdx, aAiddinitialize; "AiddInitialize"
0x1800cd38b  mov     rcx, rsi; hModule
0x1800cd38e  call    cs:__imp_GetProcAddress
0x1800cd394  mov     [rdi+10h], rax
0x1800cd398  lea     rdx, aAidduninitiali; "AiddUninitialize"
0x1800cd39f  mov     rcx, [rdi]; hModule
0x1800cd3a2  call    cs:__imp_GetProcAddress
0x1800cd3a8  mov     [rdi+18h], rax
0x1800cd3ac  lea     rdx, aAiddisenabled; "AiddIsEnabled"
0x1800cd3b3  mov     rcx, [rdi]; hModule
0x1800cd3b6  call    cs:__imp_GetProcAddress
0x1800cd3bc  mov     [rdi+8], rax
0x1800cd3c0  cmp     qword ptr [rdi+10h], 0
0x1800cd3c5  jz      short loc_1800CD3E6
0x1800cd3c7  cmp     qword ptr [rdi+18h], 0
0x1800cd3cc  jz      short loc_1800CD3E6
0x1800cd3ce  test    rax, rax
0x1800cd3d1  jz      short loc_1800CD3E6
0x1800cd3d3  mov     eax, cs:dword_1800FF8B0
0x1800cd3d9  inc     eax
0x1800cd3db  mov     cs:dword_1800FF8B0, eax
0x1800cd3e1  jmp     loc_1800CD4C6
0x1800cd3e6  call    cs:__imp_GetLastError
0x1800cd3ec  mov     [rsp+48h+var_28], eax
0x1800cd3f0  lea     r9, aGetprocaddress_1; "GetProcAddress failed [%d]"
0x1800cd3f7  mov     r8d, 0BEh
0x1800cd3fd  lea     rdx, aWindowsCompatI_2; "Windows::Compat::Inventory::Aidd::AiddM"...
0x1800cd404  mov     ecx, 1
0x1800cd409  call    AslLogCallPrintf
0x1800cd40e  mov     rsi, [rdi]
0x1800cd411  test    rsi, rsi
0x1800cd414  jz      short loc_1800CD430
0x1800cd416  call    cs:__imp_GetLastError
0x1800cd41c  mov     ebx, eax
0x1800cd41e  mov     rcx, rsi; hLibModule
0x1800cd421  call    cs:__imp_FreeLibrary
0x1800cd427  mov     ecx, ebx; dwErrCode
0x1800cd429  call    cs:__imp_SetLastError
0x1800cd42f  nop
0x1800cd430  mov     qword ptr [rdi], 0
0x1800cd437  mov     qword ptr [rdi+10h], 0
0x1800cd43f  mov     qword ptr [rdi+18h], 0
0x1800cd447  mov     qword ptr [rdi+8], 0
0x1800cd44f  call    cs:__imp_GetLastError
0x1800cd455  test    eax, eax
0x1800cd457  jle     short loc_1800CD461
0x1800cd459  movzx   eax, ax
0x1800cd45c  or      eax, 80070000h
0x1800cd461  mov     ebx, eax
0x1800cd463  jmp     loc_1800CD4FB
0x1800cd468  cmp     ebx, 1
0x1800cd46b  jnz     loc_1800CD508
0x1800cd471  mov     eax, cs:dword_1800FF8B0
0x1800cd477  test    eax, eax
0x1800cd479  jle     short loc_1800CD4D3
0x1800cd47b  sub     eax, ebx
0x1800cd47d  mov     cs:dword_1800FF8B0, eax
0x1800cd483  jnz     short loc_1800CD4C6
0x1800cd485  mov     rsi, [rdi]
0x1800cd488  test    rsi, rsi
0x1800cd48b  jz      short loc_1800CD4A7
0x1800cd48d  call    cs:__imp_GetLastError
0x1800cd493  mov     ebx, eax
0x1800cd495  mov     rcx, rsi; hLibModule
0x1800cd498  call    cs:__imp_FreeLibrary
0x1800cd49e  mov     ecx, ebx; dwErrCode
0x1800cd4a0  call    cs:__imp_SetLastError
0x1800cd4a6  nop
0x1800cd4a7  mov     qword ptr [rdi], 0
0x1800cd4ae  mov     qword ptr [rdi+10h], 0
0x1800cd4b6  mov     qword ptr [rdi+18h], 0
0x1800cd4be  mov     qword ptr [rdi+8], 0
0x1800cd4c6  mov     rcx, r15; SRWLock
0x1800cd4c9  call    cs:__imp_ReleaseSRWLockExclusive
0x1800cd4cf  xor     eax, eax
0x1800cd4d1  jmp     short loc_1800CD539
0x1800cd4d3  mov     ebx, 80004005h
0x1800cd4d8  mov     [rsp+48h+var_28], ebx
0x1800cd4dc  lea     r9, aRefcountIsAlre; "RefCount is already 0 [%#x]"
0x1800cd4e3  mov     r8d, 0D3h
0x1800cd4e9  lea     rdx, aWindowsCompatI_2; "Windows::Compat::Inventory::Aidd::AiddM"...
0x1800cd4f0  mov     ecx, 1
0x1800cd4f5  call    AslLogCallPrintf
0x1800cd4fa  nop
0x1800cd4fb  mov     rcx, r15; SRWLock
0x1800cd4fe  call    cs:__imp_ReleaseSRWLockExclusive
0x1800cd504  mov     eax, ebx
0x1800cd506  jmp     short loc_1800CD539
0x1800cd508  mov     [rsp+48h+var_28], ebx
0x1800cd50c  lea     r9, aInvalidActionD; "Invalid action [%d]"
0x1800cd513  mov     r8d, 0E1h
0x1800cd519  lea     rdx, aWindowsCompatI_2; "Windows::Compat::Inventory::Aidd::AiddM"...
0x1800cd520  mov     ecx, 1
0x1800cd525  call    AslLogCallPrintf
0x1800cd52a  nop
0x1800cd52b  mov     rcx, r15; SRWLock
0x1800cd52e  call    cs:__imp_ReleaseSRWLockExclusive
0x1800cd534  mov     eax, 0A0h
0x1800cd539  mov     rbx, [rsp+48h+arg_0]
0x1800cd53e  mov     rbp, [rsp+48h+arg_18]
0x1800cd543  add     rsp, 30h
0x1800cd547  pop     r15
0x1800cd549  pop     rdi
0x1800cd54a  pop     rsi
0x1800cd54b  retn
```
