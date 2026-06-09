# ApiSetQueryApiSetPresence

- ea: `0x18003b694`
- end: `0x18003b72c`
- name: `ApiSetQueryApiSetPresence`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180007514`

## callees

- `0x1800295dc`
- `0x18003b694`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003b714`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003b714`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003b6bb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003b6bb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003b6fb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003b6fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b6c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b6c9`

## string_xrefs

- `0x18003b6ae`: `ntdll.dll`
- `0x18003b6cf`: `LoadLibraryExW failed [%d]`

## pseudocode

```c
__int64 __fastcall ApiSetQueryApiSetPresence(__int64 a1, _BYTE *a2)
{
  HMODULE Library; // rax
  HMODULE v5; // rbx
  DWORD LastError; // eax
  FARPROC ProcAddress; // rax

  *a2 = 0;
  Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
  v5 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "ApiSetQueryApiSetPresence");
    if ( ProcAddress )
      ((void (__fastcall *)(__int64, _BYTE *))ProcAddress)(a1, a2);
    FreeLibrary(v5);
  }
  else
  {
    LastError = GetLastError();
    AslLogCallPrintf(1, "ApiSetQueryApiSetPresence", 603, "LoadLibraryExW failed [%d]", LastError);
  }
  return 0;
}

```

## disassembly

```asm
0x18003b694  mov     [rsp+arg_0], rbx
0x18003b699  mov     [rsp+arg_8], rsi
0x18003b69e  push    rdi
0x18003b69f  sub     rsp, 30h
0x18003b6a3  mov     rdi, rdx
0x18003b6a6  mov     byte ptr [rdx], 0
0x18003b6a9  mov     rsi, rcx
0x18003b6ac  xor     edx, edx; hFile
0x18003b6ae  lea     rcx, LibFileName; "ntdll.dll"
0x18003b6b5  mov     r8d, 800h; dwFlags
0x18003b6bb  call    cs:__imp_LoadLibraryExW
0x18003b6c1  mov     rbx, rax
0x18003b6c4  test    rax, rax
0x18003b6c7  jnz     short loc_18003B6F1
0x18003b6c9  call    cs:__imp_GetLastError
0x18003b6cf  lea     r9, aLoadlibraryexw; "LoadLibraryExW failed [%d]"
0x18003b6d6  mov     r8d, 25Bh
0x18003b6dc  lea     rdx, aApisetqueryapi; "ApiSetQueryApiSetPresence"
0x18003b6e3  mov     [rsp+38h+var_18], eax
0x18003b6e7  lea     ecx, [rbx+1]
0x18003b6ea  call    AslLogCallPrintf
0x18003b6ef  jmp     short loc_18003B71A
0x18003b6f1  lea     rdx, aApisetqueryapi; "ApiSetQueryApiSetPresence"
0x18003b6f8  mov     rcx, rbx; hModule
0x18003b6fb  call    cs:__imp_GetProcAddress
0x18003b701  test    rax, rax
0x18003b704  jz      short loc_18003B711
0x18003b706  mov     rdx, rdi
0x18003b709  mov     rcx, rsi
0x18003b70c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b711  mov     rcx, rbx; hLibModule
0x18003b714  call    cs:__imp_FreeLibrary
0x18003b71a  mov     rbx, [rsp+38h+arg_0]
0x18003b71f  xor     eax, eax
0x18003b721  mov     rsi, [rsp+38h+arg_8]
0x18003b726  add     rsp, 30h
0x18003b72a  pop     rdi
0x18003b72b  retn
```
