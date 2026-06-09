# DoesFileExist(ushort const *)

- ea: `0x140006c80`
- end: `0x140006d1d`
- name: `?DoesFileExist@@YAJPEBG@Z`
- size: `157`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x140007ad8`
- `0x14000b0cc`

## callees

- `0x140002f40`
- `0x140003ab8`
- `0x140005d98`
- `0x140006c80`
- `0x14000a49c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x140006cb8`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x140006cb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006cc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006cc9`

## string_xrefs

- `0x140006ce1`: `onecore\windows\directx\database\updater\exe\main.cpp`

## pseudocode

```c
__int64 __fastcall DoesFileExist(LPCWSTR lpFileName)
{
  const char *v2; // r9
  unsigned int LastError; // ebx
  HANDLE v5[2]; // [rsp+20h] [rbp-278h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-268h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+0h]

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v5[0] = FindFirstFileW(lpFileName, &FindFileData);
  if ( v5[0] == (HANDLE)-1LL )
  {
    if ( GetLastError() == 2 )
      LastError = 1;
    else
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x12,
                    (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\main.cpp",
                    v2);
  }
  else
  {
    LastError = 0;
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(v5);
  return LastError;
}

```

## disassembly

```asm
0x140006c80  push    rbx
0x140006c82  sub     rsp, 290h
0x140006c89  mov     rax, cs:__security_cookie
0x140006c90  xor     rax, rsp
0x140006c93  mov     [rsp+298h+var_18], rax
0x140006c9b  mov     rbx, rcx
0x140006c9e  xor     edx, edx; Val
0x140006ca0  lea     rcx, [rsp+298h+FindFileData]; void *
0x140006ca5  mov     r8d, 250h; Size
0x140006cab  call    memset_0
0x140006cb0  lea     rdx, [rsp+298h+FindFileData]; lpFindFileData
0x140006cb5  mov     rcx, rbx; lpFileName
0x140006cb8  call    cs:__imp_FindFirstFileW
0x140006cbe  mov     [rsp+298h+var_278], rax
0x140006cc3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140006cc7  jnz     short loc_140006CF6
0x140006cc9  call    cs:__imp_GetLastError
0x140006ccf  cmp     eax, 2
0x140006cd2  jnz     short loc_140006CD9
0x140006cd4  lea     ebx, [rax-1]
0x140006cd7  jmp     short loc_140006CF8
0x140006cd9  mov     rcx, [rsp+298h]; this
0x140006ce1  lea     r8, aOnecoreWindows_2; "onecore\\windows\\directx\\database\\up"...
0x140006ce8  mov     edx, 12h; void *
0x140006ced  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140006cf2  mov     ebx, eax
0x140006cf4  jmp     short loc_140006CF8
0x140006cf6  xor     ebx, ebx
0x140006cf8  lea     rcx, [rsp+298h+var_278]
0x140006cfd  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x140006d02  mov     eax, ebx
0x140006d04  mov     rcx, [rsp+298h+var_18]
0x140006d0c  xor     rcx, rsp; StackCookie
0x140006d0f  call    __security_check_cookie
0x140006d14  add     rsp, 290h
0x140006d1b  pop     rbx
0x140006d1c  retn
```
