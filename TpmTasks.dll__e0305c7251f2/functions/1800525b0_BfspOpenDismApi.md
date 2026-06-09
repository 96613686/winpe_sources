# BfspOpenDismApi

- ea: `0x1800525b0`
- end: `0x1800526bb`
- name: `BfspOpenDismApi`
- size: `267`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800526c4`

## callees

- `0x1800525b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800525f9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180052612`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005262b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180052644`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005265d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180052678`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800525f9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180052612`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005262b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180052644`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005265d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180052678`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180052694`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180052694`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800525c9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800525c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800525d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800525d7`

## string_xrefs

- `0x1800525c0`: `DISMAPI.DLL`
- `0x18005260b`: `DismOpenSession`
- `0x18005263d`: `DismDelete`

## pseudocode

```c
__int64 __fastcall BfspOpenDismApi(__int64 a1)
{
  HMODULE Library; // rax
  DWORD LastError; // ebx
  FARPROC ProcAddress; // rax
  FARPROC v5; // rax
  FARPROC v6; // rax
  FARPROC v7; // rax
  FARPROC v8; // rax
  FARPROC v9; // rax

  Library = LoadLibraryExW(L"DISMAPI.DLL", 0, 0);
  *(_QWORD *)a1 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "DismInitialize");
    *(_QWORD *)(a1 + 8) = ProcAddress;
    if ( ProcAddress )
    {
      v5 = GetProcAddress(*(HMODULE *)a1, "DismOpenSession");
      *(_QWORD *)(a1 + 16) = v5;
      if ( v5 )
      {
        v6 = GetProcAddress(*(HMODULE *)a1, "DismGetFeatureInfo");
        *(_QWORD *)(a1 + 24) = v6;
        if ( v6 )
        {
          v7 = GetProcAddress(*(HMODULE *)a1, "DismDelete");
          *(_QWORD *)(a1 + 32) = v7;
          if ( v7 )
          {
            v8 = GetProcAddress(*(HMODULE *)a1, "DismCloseSession");
            *(_QWORD *)(a1 + 40) = v8;
            if ( v8 )
            {
              LastError = 0;
              v9 = GetProcAddress(*(HMODULE *)a1, "DismShutdown");
              *(_QWORD *)(a1 + 48) = v9;
              if ( v9 )
                return LastError;
            }
          }
        }
      }
    }
    LastError = 127;
  }
  else
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 126;
  }
  if ( *(_QWORD *)a1 )
  {
    FreeLibrary(*(HMODULE *)a1);
    *(_QWORD *)a1 = 0;
  }
  if ( (int)LastError > 0 )
    return (unsigned __int16)LastError | 0xC0070000;
  return LastError;
}

```

## disassembly

```asm
0x1800525b0  mov     [rsp+arg_0], rbx
0x1800525b5  push    rdi
0x1800525b6  sub     rsp, 20h
0x1800525ba  mov     rdi, rcx
0x1800525bd  xor     r8d, r8d; dwFlags
0x1800525c0  lea     rcx, aDismapiDll; "DISMAPI.DLL"
0x1800525c7  xor     edx, edx; hFile
0x1800525c9  call    cs:__imp_LoadLibraryExW
0x1800525cf  mov     [rdi], rax
0x1800525d2  test    rax, rax
0x1800525d5  jnz     short loc_1800525EF
0x1800525d7  call    cs:__imp_GetLastError
0x1800525dd  mov     ebx, eax
0x1800525df  test    eax, eax
0x1800525e1  jnz     loc_18005268C
0x1800525e7  lea     ebx, [rax+7Eh]
0x1800525ea  jmp     loc_18005268C
0x1800525ef  lea     rdx, aDisminitialize; "DismInitialize"
0x1800525f6  mov     rcx, rax; hModule
0x1800525f9  call    cs:__imp_GetProcAddress
0x1800525ff  mov     [rdi+8], rax
0x180052603  test    rax, rax
0x180052606  jz      short loc_180052687
0x180052608  mov     rcx, [rdi]; hModule
0x18005260b  lea     rdx, aDismopensessio; "DismOpenSession"
0x180052612  call    cs:__imp_GetProcAddress
0x180052618  mov     [rdi+10h], rax
0x18005261c  test    rax, rax
0x18005261f  jz      short loc_180052687
0x180052621  mov     rcx, [rdi]; hModule
0x180052624  lea     rdx, aDismgetfeature; "DismGetFeatureInfo"
0x18005262b  call    cs:__imp_GetProcAddress
0x180052631  mov     [rdi+18h], rax
0x180052635  test    rax, rax
0x180052638  jz      short loc_180052687
0x18005263a  mov     rcx, [rdi]; hModule
0x18005263d  lea     rdx, aDismdelete; "DismDelete"
0x180052644  call    cs:__imp_GetProcAddress
0x18005264a  mov     [rdi+20h], rax
0x18005264e  test    rax, rax
0x180052651  jz      short loc_180052687
0x180052653  mov     rcx, [rdi]; hModule
0x180052656  lea     rdx, aDismclosesessi; "DismCloseSession"
0x18005265d  call    cs:__imp_GetProcAddress
0x180052663  mov     [rdi+28h], rax
0x180052667  test    rax, rax
0x18005266a  jz      short loc_180052687
0x18005266c  mov     rcx, [rdi]; hModule
0x18005266f  lea     rdx, aDismshutdown; "DismShutdown"
0x180052676  xor     ebx, ebx
0x180052678  call    cs:__imp_GetProcAddress
0x18005267e  mov     [rdi+30h], rax
0x180052682  test    rax, rax
0x180052685  jnz     short loc_1800526AE
0x180052687  mov     ebx, 7Fh
0x18005268c  mov     rcx, [rdi]; hLibModule
0x18005268f  test    rcx, rcx
0x180052692  jz      short loc_1800526A1
0x180052694  call    cs:__imp_FreeLibrary
0x18005269a  mov     qword ptr [rdi], 0
0x1800526a1  test    ebx, ebx
0x1800526a3  jle     short loc_1800526AE
0x1800526a5  movzx   ebx, bx
0x1800526a8  or      ebx, 0C0070000h
0x1800526ae  mov     eax, ebx
0x1800526b0  mov     rbx, [rsp+28h+arg_0]
0x1800526b5  add     rsp, 20h
0x1800526b9  pop     rdi
0x1800526ba  retn
```
