# CLSAPrivate::Init(void)

- ea: `0x1800730c8`
- end: `0x180073199`
- name: `?Init@CLSAPrivate@@QEAAJXZ`
- size: `209`
- prototype: `__int64 __fastcall(CLSAPrivate *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x180072edc`

## callees

- `0x1800730c8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800730dd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800730dd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180073110`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180073129`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180073144`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007315d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007317c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180073110`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180073129`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180073144`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007315d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007317c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800730eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800730eb`

## string_xrefs

- `0x1800730d4`: `advapi32.dll`
- `0x180073106`: `LsaOpenPolicy`
- `0x180073122`: `LsaOpenAccount`
- `0x18007313d`: `LsaCreateAccount`
- `0x180073156`: `LsaGetSystemAccessAccount`
- `0x180073175`: `LsaSetSystemAccessAccount`

## pseudocode

```c
signed int __fastcall CLSAPrivate::Init(CLSAPrivate *this)
{
  HMODULE Library; // rax
  signed int result; // eax
  FARPROC ProcAddress; // rax
  FARPROC v5; // rax
  bool v6; // zf
  FARPROC v7; // rax
  FARPROC v8; // rax
  FARPROC v9; // rax

  Library = LoadLibraryExW(L"advapi32.dll", 0, 0);
  *(_QWORD *)this = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "LsaOpenPolicy");
    *((_QWORD *)this + 1) = ProcAddress;
    if ( ProcAddress )
    {
      v5 = GetProcAddress(*(HMODULE *)this, "LsaOpenAccount");
      v6 = *((_QWORD *)this + 1) == 0;
      *((_QWORD *)this + 2) = v5;
      if ( !v6 )
      {
        v7 = GetProcAddress(*(HMODULE *)this, "LsaCreateAccount");
        *((_QWORD *)this + 3) = v7;
        if ( v7 )
        {
          v8 = GetProcAddress(*(HMODULE *)this, "LsaGetSystemAccessAccount");
          v6 = *((_QWORD *)this + 1) == 0;
          *((_QWORD *)this + 4) = v8;
          if ( !v6 )
          {
            v9 = GetProcAddress(*(HMODULE *)this, "LsaSetSystemAccessAccount");
            v6 = *((_QWORD *)this + 1) == 0;
            *((_QWORD *)this + 5) = v9;
            if ( !v6 )
              return 0;
          }
        }
      }
    }
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800730c8  push    rbx
0x1800730ca  sub     rsp, 20h
0x1800730ce  mov     rbx, rcx
0x1800730d1  xor     r8d, r8d; dwFlags
0x1800730d4  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x1800730db  xor     edx, edx; hFile
0x1800730dd  call    cs:__imp_LoadLibraryExW
0x1800730e3  mov     [rbx], rax
0x1800730e6  test    rax, rax
0x1800730e9  jnz     short loc_180073106
0x1800730eb  call    cs:__imp_GetLastError
0x1800730f1  test    eax, eax
0x1800730f3  jle     loc_180073193
0x1800730f9  movzx   eax, ax
0x1800730fc  or      eax, 80070000h
0x180073101  jmp     loc_180073193
0x180073106  lea     rdx, aLsaopenpolicy; "LsaOpenPolicy"
0x18007310d  mov     rcx, rax; hModule
0x180073110  call    cs:__imp_GetProcAddress
0x180073116  mov     [rbx+8], rax
0x18007311a  test    rax, rax
0x18007311d  jz      short loc_1800730EB
0x18007311f  mov     rcx, [rbx]; hModule
0x180073122  lea     rdx, aLsaopenaccount; "LsaOpenAccount"
0x180073129  call    cs:__imp_GetProcAddress
0x18007312f  cmp     qword ptr [rbx+8], 0
0x180073134  mov     [rbx+10h], rax
0x180073138  jz      short loc_1800730EB
0x18007313a  mov     rcx, [rbx]; hModule
0x18007313d  lea     rdx, aLsacreateaccou; "LsaCreateAccount"
0x180073144  call    cs:__imp_GetProcAddress
0x18007314a  mov     [rbx+18h], rax
0x18007314e  test    rax, rax
0x180073151  jz      short loc_1800730EB
0x180073153  mov     rcx, [rbx]; hModule
0x180073156  lea     rdx, aLsagetsystemac; "LsaGetSystemAccessAccount"
0x18007315d  call    cs:__imp_GetProcAddress
0x180073163  cmp     qword ptr [rbx+8], 0
0x180073168  mov     [rbx+20h], rax
0x18007316c  jz      loc_1800730EB
0x180073172  mov     rcx, [rbx]; hModule
0x180073175  lea     rdx, aLsasetsystemac; "LsaSetSystemAccessAccount"
0x18007317c  call    cs:__imp_GetProcAddress
0x180073182  cmp     qword ptr [rbx+8], 0
0x180073187  mov     [rbx+28h], rax
0x18007318b  jz      loc_1800730EB
0x180073191  xor     eax, eax
0x180073193  add     rsp, 20h
0x180073197  pop     rbx
0x180073198  retn
```
