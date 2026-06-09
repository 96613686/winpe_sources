# SpSignSkuRequiresSignedInf

- ea: `0x14002cc2c`
- end: `0x14002ccd3`
- name: `SpSignSkuRequiresSignedInf`
- size: `167`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x14002e0d4`

## callees

- `0x14002cc2c`
- `0x140047010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14002cc7e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14002cc7e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14002ccb1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14002ccb1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14002cc66`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14002cc66`
- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x14002cc4d`
- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x14002cc4d`

## string_xrefs

- `0x14002cc59`: `WLDP.DLL`

## pseudocode

```c
__int64 __fastcall SpSignSkuRequiresSignedInf(_DWORD *a1)
{
  HMODULE Library; // rax
  HMODULE v3; // rbx
  FARPROC ProcAddress; // rax
  int v5; // eax
  unsigned int v6; // edi
  int v8; // [rsp+38h] [rbp+10h] BYREF

  v8 = 0;
  if ( !IsApiSetImplemented("ext-ms-win-setupapi-inf-l1-1-0") )
  {
    v6 = 0;
    *a1 = 1;
    return v6;
  }
  Library = LoadLibraryExW(L"WLDP.DLL", 0, 0x800u);
  v3 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "WldpQueryWindowsLockdownMode");
    if ( ProcAddress )
    {
      v5 = ((__int64 (__fastcall *)(int *))ProcAddress)(&v8);
      if ( v5 < 0 )
      {
        v6 = (unsigned __int16)v5;
LABEL_7:
        FreeLibrary(v3);
        return v6;
      }
    }
  }
  *a1 = v8 != 0;
  v6 = 0;
  if ( v3 )
    goto LABEL_7;
  return v6;
}

```

## disassembly

```asm
0x14002cc2c  mov     [rsp+arg_0], rbx
0x14002cc31  mov     [rsp+arg_10], rsi
0x14002cc36  push    rdi
0x14002cc37  sub     rsp, 20h
0x14002cc3b  mov     rsi, rcx
0x14002cc3e  mov     [rsp+28h+arg_8], 0
0x14002cc46  lea     rcx, Contract; "ext-ms-win-setupapi-inf-l1-1-0"
0x14002cc4d  call    cs:__imp_IsApiSetImplemented
0x14002cc53  test    eax, eax
0x14002cc55  jz      short loc_14002CCB9
0x14002cc57  xor     edx, edx; hFile
0x14002cc59  lea     rcx, aWldpDll; "WLDP.DLL"
0x14002cc60  mov     r8d, 800h; dwFlags
0x14002cc66  call    cs:__imp_LoadLibraryExW
0x14002cc6c  mov     rbx, rax
0x14002cc6f  test    rax, rax
0x14002cc72  jz      short loc_14002CC9C
0x14002cc74  lea     rdx, aWldpquerywindo; "WldpQueryWindowsLockdownMode"
0x14002cc7b  mov     rcx, rax; hModule
0x14002cc7e  call    cs:__imp_GetProcAddress
0x14002cc84  test    rax, rax
0x14002cc87  jz      short loc_14002CC9C
0x14002cc89  lea     rcx, [rsp+28h+arg_8]
0x14002cc8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002cc93  test    eax, eax
0x14002cc95  jns     short loc_14002CC9C
0x14002cc97  movzx   edi, ax
0x14002cc9a  jmp     short loc_14002CCAE
0x14002cc9c  xor     eax, eax
0x14002cc9e  cmp     [rsp+28h+arg_8], eax
0x14002cca2  setnz   al
0x14002cca5  mov     [rsi], eax
0x14002cca7  xor     edi, edi
0x14002cca9  test    rbx, rbx
0x14002ccac  jz      short loc_14002CCC1
0x14002ccae  mov     rcx, rbx; hLibModule
0x14002ccb1  call    cs:__imp_FreeLibrary
0x14002ccb7  jmp     short loc_14002CCC1
0x14002ccb9  xor     edi, edi
0x14002ccbb  mov     dword ptr [rsi], 1
0x14002ccc1  mov     rbx, [rsp+28h+arg_0]
0x14002ccc6  mov     eax, edi
0x14002ccc8  mov     rsi, [rsp+28h+arg_10]
0x14002cccd  add     rsp, 20h
0x14002ccd1  pop     rdi
0x14002ccd2  retn
```
