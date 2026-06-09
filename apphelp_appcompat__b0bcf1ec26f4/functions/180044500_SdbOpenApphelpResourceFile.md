# SdbOpenApphelpResourceFile

- ea: `0x180044500`
- end: `0x1800445d4`
- name: `SdbOpenApphelpResourceFile`
- size: `212`
- prototype: `__int64 __fastcall(LPCWSTR lpLibFileName)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180044b60`
- `0x180046254`

## callees

- `0x18000f114`
- `0x180044500`
- `0x18004afa4`
- `0x180059235`
- `0x180059270`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180044577`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180044577`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044585`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044585`

## string_xrefs

- `0x180044549`: `SdbGetPathResourceDll failed.`
- `0x180044556`: `SdbOpenApphelpResourceFile`
- `0x1800445a1`: `SdbOpenApphelpResourceFile`
- `0x18004458f`: `Failed to open the Apphelp resource file %ws [Gle=%u]`

## pseudocode

```c
HMODULE __fastcall SdbOpenApphelpResourceFile(LPCWSTR lpLibFileName)
{
  HMODULE Library; // rbx
  const WCHAR *v3; // rcx
  DWORD LastError; // [rsp+28h] [rbp-230h]
  _BYTE v6[528]; // [rsp+30h] [rbp-228h] BYREF

  memset_0(v6, 0, 0x208u);
  if ( lpLibFileName )
  {
    v3 = lpLibFileName;
  }
  else
  {
    if ( !(unsigned int)SdbGetPathResourceDll(v6) )
    {
      Library = 0;
      AslLogCallPrintf(1, "SdbOpenApphelpResourceFile", 254, "SdbGetPathResourceDll failed.");
      return Library;
    }
    v3 = (const WCHAR *)v6;
  }
  Library = LoadLibraryExW(v3, 0, 2u);
  if ( !Library )
  {
    LastError = GetLastError();
    AslLogCallPrintf(
      1,
      "SdbOpenApphelpResourceFile",
      265,
      "Failed to open the Apphelp resource file %ws [Gle=%u]",
      lpLibFileName,
      LastError);
  }
  return Library;
}

```

## disassembly

```asm
0x180044500  mov     [rsp+arg_8], rbx
0x180044505  push    rdi
0x180044506  sub     rsp, 250h
0x18004450d  mov     rax, cs:__security_cookie
0x180044514  xor     rax, rsp
0x180044517  mov     [rsp+258h+var_18], rax
0x18004451f  mov     rdi, rcx
0x180044522  xor     edx, edx; Val
0x180044524  lea     rcx, [rsp+258h+var_228]; void *
0x180044529  mov     r8d, 208h; Size
0x18004452f  call    memset_0
0x180044534  test    rdi, rdi
0x180044537  jnz     short loc_18004456E
0x180044539  lea     rcx, [rsp+258h+var_228]
0x18004453e  call    SdbGetPathResourceDll
0x180044543  test    eax, eax
0x180044545  jnz     short loc_180044567
0x180044547  xor     ebx, ebx
0x180044549  lea     r9, aSdbgetpathreso; "SdbGetPathResourceDll failed."
0x180044550  mov     r8d, 0FEh
0x180044556  lea     rdx, aSdbopenapphelp_4; "SdbOpenApphelpResourceFile"
0x18004455d  lea     ecx, [rdi+1]
0x180044560  call    AslLogCallPrintf
0x180044565  jmp     short loc_1800445B0
0x180044567  lea     rcx, [rsp+258h+var_228]
0x18004456c  jmp     short loc_180044571
0x18004456e  mov     rcx, rdi; lpLibFileName
0x180044571  xor     edx, edx; hFile
0x180044573  lea     r8d, [rdx+2]; dwFlags
0x180044577  call    cs:__imp_LoadLibraryExW
0x18004457d  mov     rbx, rax
0x180044580  test    rax, rax
0x180044583  jnz     short loc_1800445B0
0x180044585  call    cs:__imp_GetLastError
0x18004458b  mov     [rsp+258h+var_230], eax
0x18004458f  lea     r9, aFailedToOpenTh_3; "Failed to open the Apphelp resource fil"...
0x180044596  mov     r8d, 109h
0x18004459c  mov     [rsp+258h+var_238], rdi
0x1800445a1  lea     rdx, aSdbopenapphelp_4; "SdbOpenApphelpResourceFile"
0x1800445a8  lea     ecx, [rbx+1]
0x1800445ab  call    AslLogCallPrintf
0x1800445b0  mov     rax, rbx
0x1800445b3  mov     rcx, [rsp+258h+var_18]
0x1800445bb  xor     rcx, rsp; StackCookie
0x1800445be  call    __security_check_cookie
0x1800445c3  mov     rbx, [rsp+258h+arg_8]
0x1800445cb  add     rsp, 250h
0x1800445d2  pop     rdi
0x1800445d3  retn
```
