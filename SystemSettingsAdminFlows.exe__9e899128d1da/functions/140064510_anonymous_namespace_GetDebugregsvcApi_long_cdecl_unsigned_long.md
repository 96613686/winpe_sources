# _anonymous_namespace_::GetDebugregsvcApi_long_(__cdecl_)(unsigned_long)_

- ea: `0x140064510`
- end: `0x140064586`
- name: `_anonymous_namespace_::GetDebugregsvcApi_long_(__cdecl_)(unsigned_long)_`
- size: `118`
- prototype: `__int64 __fastcall(LPCSTR lpProcName)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x140064bbc`
- `0x140064e6c`

## callees

- `0x14001f3b4`
- `0x140064510`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140064561`
- `KERNEL32!GetProcAddress` at `0x140064561`
- `KERNEL32!LoadLibraryExW` at `0x140064537`
- `KERNEL32!LoadLibraryExW` at `0x140064537`

## string_xrefs

- `0x140064530`: `debugregsvcapi.dll`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::GetDebugregsvcApi_long____cdecl___unsigned_long__(
        LPCSTR lpProcName,
        HMODULE *a2,
        FARPROC *a3)
{
  HMODULE Library; // rax
  const char *v7; // r9
  __int64 v8; // rdx
  FARPROC ProcAddress; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  Library = LoadLibraryExW(L"debugregsvcapi.dll", 0, 0x800u);
  *a2 = Library;
  if ( !Library )
  {
    v8 = 50;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v8,
             (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\developeroptions\\developeroptionsadminflowhandler.cpp",
             v7);
  }
  ProcAddress = GetProcAddress(Library, lpProcName);
  *a3 = ProcAddress;
  if ( !ProcAddress )
  {
    v8 = 53;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v8,
             (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\developeroptions\\developeroptionsadminflowhandler.cpp",
             v7);
  }
  return 0;
}

```

## disassembly

```asm
0x140064510  mov     [rsp+arg_0], rbx
0x140064515  mov     [rsp+arg_8], rsi
0x14006451a  push    rdi
0x14006451b  sub     rsp, 20h
0x14006451f  mov     rdi, r8
0x140064522  mov     rbx, rdx
0x140064525  mov     rsi, rcx
0x140064528  xor     edx, edx; hFile
0x14006452a  mov     r8d, 800h; dwFlags
0x140064530  lea     rcx, aDebugregsvcapi; "debugregsvcapi.dll"
0x140064537  call    cs:__imp_LoadLibraryExW
0x14006453d  mov     [rbx], rax
0x140064540  test    rax, rax
0x140064543  jnz     short loc_14006455B
0x140064545  lea     edx, [rax+32h]; void *
0x140064548  mov     rcx, [rsp+28h]; this
0x14006454d  lea     r8, aPcshellShellSy_32; "pcshell\\shell\\systemsettings\\adminfl"...
0x140064554  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140064559  jmp     short loc_140064576
0x14006455b  mov     rdx, rsi; lpProcName
0x14006455e  mov     rcx, rax; hModule
0x140064561  call    cs:__imp_GetProcAddress
0x140064567  mov     [rdi], rax
0x14006456a  test    rax, rax
0x14006456d  jnz     short loc_140064574
0x14006456f  lea     edx, [rax+35h]
0x140064572  jmp     short loc_140064548
0x140064574  xor     eax, eax
0x140064576  mov     rbx, [rsp+28h+arg_0]
0x14006457b  mov     rsi, [rsp+28h+arg_8]
0x140064580  add     rsp, 20h
0x140064584  pop     rdi
0x140064585  retn
```
