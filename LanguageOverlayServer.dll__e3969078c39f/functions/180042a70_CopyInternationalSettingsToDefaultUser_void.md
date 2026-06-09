# CopyInternationalSettingsToDefaultUser(void)

- ea: `0x180042a70`
- end: `0x180042b1d`
- name: `?CopyInternationalSettingsToDefaultUser@@YAJXZ`
- size: `173`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180042460`

## callees

- `0x180009064`
- `0x1800166e0`
- `0x180042a70`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180042ab7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180042ab7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180042b0a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180042b0a`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180042a81`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180042a81`

## string_xrefs

- `0x180042a99`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\deviceinternationalsettings.cpp`
- `0x180042ac7`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\deviceinternationalsettings.cpp`
- `0x180042af0`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\deviceinternationalsettings.cpp`
- `0x180042aad`: `IntlCopyDefaultUserLocale`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 CopyInternationalSettingsToDefaultUser(void)
{
  HMODULE LibraryW; // rax
  const char *v1; // r9
  HMODULE v2; // rbx
  FARPROC ProcAddress; // rax
  const char *v5; // r9
  int LastError; // eax
  unsigned int v7; // eax
  unsigned int v8; // edi
  unsigned int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  LibraryW = LoadLibraryW(L"intl.cpl");
  v2 = LibraryW;
  if ( !LibraryW )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xA2,
             (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\deviceinternationalsettings.cpp",
             v1);
  ProcAddress = GetProcAddress(LibraryW, "IntlCopyDefaultUserLocale");
  if ( ProcAddress )
  {
    v7 = ((__int64 (__fastcall *)(__int64))ProcAddress)(1);
    if ( !v7 )
    {
      v8 = 0;
      goto LABEL_9;
    }
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0xA7,
                  (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\deviceinternationalsettings.cpp",
                  (const char *)v7,
                  v9);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xA6,
                  (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\deviceinternationalsettings.cpp",
                  v5);
  }
  v8 = LastError;
LABEL_9:
  FreeLibrary(v2);
  return v8;
}

```

## disassembly

```asm
0x180042a70  mov     [rsp+arg_8], rbx
0x180042a75  push    rdi; unsigned int
0x180042a76  sub     rsp, 20h
0x180042a7a  lea     rcx, LibFileName; "intl.cpl"
0x180042a81  call    cs:__imp_LoadLibraryW
0x180042a87  mov     rbx, rax
0x180042a8a  mov     [rsp+28h+arg_0], rax
0x180042a8f  test    rax, rax
0x180042a92  jnz     short loc_180042AAD
0x180042a94  mov     rcx, [rsp+28h]; this
0x180042a99  lea     r8, aOnecoreBaseLan_19; "onecore\\base\\languageoverlay\\service"...
0x180042aa0  mov     edx, 0A2h; void *
0x180042aa5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180042aaa  nop
0x180042aab  jmp     short loc_180042B12
0x180042aad  lea     rdx, aIntlcopydefaul; "IntlCopyDefaultUserLocale"
0x180042ab4  mov     rcx, rbx; hModule
0x180042ab7  call    cs:__imp_GetProcAddress
0x180042abd  test    rax, rax
0x180042ac0  jnz     short loc_180042ADA
0x180042ac2  mov     rcx, [rsp+28h]; this
0x180042ac7  lea     r8, aOnecoreBaseLan_19; "onecore\\base\\languageoverlay\\service"...
0x180042ace  mov     edx, 0A6h; void *
0x180042ad3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180042ad8  jmp     short loc_180042B01
0x180042ada  mov     ecx, 1
0x180042adf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042ae4  test    eax, eax
0x180042ae6  jz      short loc_180042B05
0x180042ae8  mov     rcx, [rsp+28h]; this
0x180042aed  mov     r9d, eax; char *
0x180042af0  lea     r8, aOnecoreBaseLan_19; "onecore\\base\\languageoverlay\\service"...
0x180042af7  mov     edx, 0A7h; void *
0x180042afc  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180042b01  mov     edi, eax
0x180042b03  jmp     short loc_180042B07
0x180042b05  xor     edi, edi
0x180042b07  mov     rcx, rbx; hLibModule
0x180042b0a  call    cs:__imp_FreeLibrary
0x180042b10  mov     eax, edi
0x180042b12  mov     rbx, [rsp+28h+arg_8]
0x180042b17  add     rsp, 20h
0x180042b1b  pop     rdi
0x180042b1c  retn
```
