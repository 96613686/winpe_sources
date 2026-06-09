# MSChapSrvInitializeChangePasswordFunctions

- ea: `0x180043c5c`
- end: `0x180043ec0`
- name: `MSChapSrvInitializeChangePasswordFunctions`
- size: `612`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800438a0`
- `0x180043b70`

## callees

- `0x180043c5c`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180043e8a`
- `ntdll!RtlLeaveCriticalSection` at `0x180043eab`
- `ntdll!RtlLeaveCriticalSection` at `0x180043e8a`
- `ntdll!RtlLeaveCriticalSection` at `0x180043eab`
- `ntdll!RtlEnterCriticalSection` at `0x180043c76`
- `ntdll!RtlEnterCriticalSection` at `0x180043c76`
- `KERNEL32!GetLastError` at `0x180043dfa`
- `KERNEL32!GetLastError` at `0x180043dfa`
- `KERNEL32!GetProcAddress` at `0x180043cc4`
- `KERNEL32!GetProcAddress` at `0x180043cee`
- `KERNEL32!GetProcAddress` at `0x180043d18`
- `KERNEL32!GetProcAddress` at `0x180043d42`
- `KERNEL32!GetProcAddress` at `0x180043d6c`
- `KERNEL32!GetProcAddress` at `0x180043d92`
- `KERNEL32!GetProcAddress` at `0x180043db8`
- `KERNEL32!GetProcAddress` at `0x180043dde`
- `KERNEL32!GetProcAddress` at `0x180043cc4`
- `KERNEL32!GetProcAddress` at `0x180043cee`
- `KERNEL32!GetProcAddress` at `0x180043d18`
- `KERNEL32!GetProcAddress` at `0x180043d42`
- `KERNEL32!GetProcAddress` at `0x180043d6c`
- `KERNEL32!GetProcAddress` at `0x180043d92`
- `KERNEL32!GetProcAddress` at `0x180043db8`
- `KERNEL32!GetProcAddress` at `0x180043dde`
- `KERNEL32!FreeLibrary` at `0x180043e14`
- `KERNEL32!FreeLibrary` at `0x180043e14`
- `KERNEL32!LoadLibraryExW` at `0x180043c9e`
- `KERNEL32!LoadLibraryExW` at `0x180043c9e`

## string_xrefs

- `0x180043c91`: `samlib.dll`
- `0x180043ce7`: `SamOpenDomain`
- `0x180043d3b`: `SamOpenUser`

## pseudocode

```c
__int64 MSChapSrvInitializeChangePasswordFunctions()
{
  HMODULE Library; // rax
  DWORD LastError; // ebx

  if ( gAreChangePasswordFunctionsInitialized )
    return 0;
  RtlEnterCriticalSection(&MSChapChangePassword);
  if ( gAreChangePasswordFunctionsInitialized )
  {
LABEL_16:
    RtlLeaveCriticalSection(&MSChapChangePassword);
    return 0;
  }
  Library = LoadLibraryExW(L"samlib.dll", 0, 0x800u);
  hSamlib = Library;
  if ( Library )
  {
    FnSamConnect = (__int64)GetProcAddress(Library, "SamConnect");
    if ( FnSamConnect )
    {
      FnSamOpenDomain = (__int64)GetProcAddress(hSamlib, "SamOpenDomain");
      if ( FnSamOpenDomain )
      {
        FnSamLookupNamesInDomain = (__int64)GetProcAddress(hSamlib, "SamLookupNamesInDomain");
        if ( FnSamLookupNamesInDomain )
        {
          FnSamOpenUser = (__int64)GetProcAddress(hSamlib, "SamOpenUser");
          if ( FnSamOpenUser )
          {
            FnSamCloseHandle = (__int64)GetProcAddress(hSamlib, "SamCloseHandle");
            if ( FnSamCloseHandle )
            {
              FnSamFreeMemory = (__int64)GetProcAddress(hSamlib, "SamFreeMemory");
              if ( FnSamFreeMemory )
              {
                FnSamiChangePasswordUser = (__int64)GetProcAddress(hSamlib, "SamiChangePasswordUser");
                if ( FnSamiChangePasswordUser )
                {
                  FnSamiChangePasswordUser2 = (__int64)GetProcAddress(hSamlib, "SamiChangePasswordUser2");
                  if ( FnSamiChangePasswordUser2 )
                  {
                    gAreChangePasswordFunctionsInitialized = 1;
                    goto LABEL_16;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  LastError = GetLastError();
  if ( hSamlib )
  {
    FreeLibrary(hSamlib);
    hSamlib = 0;
  }
  FnSamConnect = 0;
  FnSamOpenDomain = 0;
  FnSamLookupNamesInDomain = 0;
  FnSamOpenUser = 0;
  FnSamiChangePasswordUser = 0;
  FnSamiChangePasswordUser2 = 0;
  FnSamCloseHandle = 0;
  FnSamFreeMemory = 0;
  RtlLeaveCriticalSection(&MSChapChangePassword);
  return LastError;
}

```

## disassembly

```asm
0x180043c5c  push    rbx
0x180043c5e  sub     rsp, 20h
0x180043c62  cmp     cs:gAreChangePasswordFunctionsInitialized, 0
0x180043c69  jnz     loc_180043EB7
0x180043c6f  lea     rcx, MSChapChangePassword; CriticalSection
0x180043c76  call    cs:__imp_RtlEnterCriticalSection
0x180043c7d  nop     dword ptr [rax+rax+00h]
0x180043c82  cmp     cs:gAreChangePasswordFunctionsInitialized, 0
0x180043c89  jnz     loc_180043EA4
0x180043c8f  xor     edx, edx; hFile
0x180043c91  lea     rcx, aSamlibDll; "samlib.dll"
0x180043c98  mov     r8d, 800h; dwFlags
0x180043c9e  call    cs:__imp_LoadLibraryExW
0x180043ca5  nop     dword ptr [rax+rax+00h]
0x180043caa  mov     cs:hSamlib, rax
0x180043cb1  test    rax, rax
0x180043cb4  jz      loc_180043DFA
0x180043cba  lea     rdx, aSamconnect; "SamConnect"
0x180043cc1  mov     rcx, rax; hModule
0x180043cc4  call    cs:__imp_GetProcAddress
0x180043ccb  nop     dword ptr [rax+rax+00h]
0x180043cd0  mov     cs:FnSamConnect, rax
0x180043cd7  test    rax, rax
0x180043cda  jz      loc_180043DFA
0x180043ce0  mov     rcx, cs:hSamlib; hModule
0x180043ce7  lea     rdx, aSamopendomain; "SamOpenDomain"
0x180043cee  call    cs:__imp_GetProcAddress
0x180043cf5  nop     dword ptr [rax+rax+00h]
0x180043cfa  mov     cs:FnSamOpenDomain, rax
0x180043d01  test    rax, rax
0x180043d04  jz      loc_180043DFA
0x180043d0a  mov     rcx, cs:hSamlib; hModule
0x180043d11  lea     rdx, aSamlookupnames; "SamLookupNamesInDomain"
0x180043d18  call    cs:__imp_GetProcAddress
0x180043d1f  nop     dword ptr [rax+rax+00h]
0x180043d24  mov     cs:FnSamLookupNamesInDomain, rax
0x180043d2b  test    rax, rax
0x180043d2e  jz      loc_180043DFA
0x180043d34  mov     rcx, cs:hSamlib; hModule
0x180043d3b  lea     rdx, aSamopenuser; "SamOpenUser"
0x180043d42  call    cs:__imp_GetProcAddress
0x180043d49  nop     dword ptr [rax+rax+00h]
0x180043d4e  mov     cs:FnSamOpenUser, rax
0x180043d55  test    rax, rax
0x180043d58  jz      loc_180043DFA
0x180043d5e  mov     rcx, cs:hSamlib; hModule
0x180043d65  lea     rdx, aSamclosehandle; "SamCloseHandle"
0x180043d6c  call    cs:__imp_GetProcAddress
0x180043d73  nop     dword ptr [rax+rax+00h]
0x180043d78  mov     cs:FnSamCloseHandle, rax
0x180043d7f  test    rax, rax
0x180043d82  jz      short loc_180043DFA
0x180043d84  mov     rcx, cs:hSamlib; hModule
0x180043d8b  lea     rdx, aSamfreememory; "SamFreeMemory"
0x180043d92  call    cs:__imp_GetProcAddress
0x180043d99  nop     dword ptr [rax+rax+00h]
0x180043d9e  mov     cs:FnSamFreeMemory, rax
0x180043da5  test    rax, rax
0x180043da8  jz      short loc_180043DFA
0x180043daa  mov     rcx, cs:hSamlib; hModule
0x180043db1  lea     rdx, aSamichangepass; "SamiChangePasswordUser"
0x180043db8  call    cs:__imp_GetProcAddress
0x180043dbf  nop     dword ptr [rax+rax+00h]
0x180043dc4  mov     cs:FnSamiChangePasswordUser, rax
0x180043dcb  test    rax, rax
0x180043dce  jz      short loc_180043DFA
0x180043dd0  mov     rcx, cs:hSamlib; hModule
0x180043dd7  lea     rdx, aSamichangepass_0; "SamiChangePasswordUser2"
0x180043dde  call    cs:__imp_GetProcAddress
0x180043de5  nop     dword ptr [rax+rax+00h]
0x180043dea  mov     cs:FnSamiChangePasswordUser2, rax
0x180043df1  test    rax, rax
0x180043df4  jnz     loc_180043E9A
0x180043dfa  call    cs:__imp_GetLastError
0x180043e01  nop     dword ptr [rax+rax+00h]
0x180043e06  mov     ebx, eax
0x180043e08  mov     rcx, cs:hSamlib; hLibModule
0x180043e0f  test    rcx, rcx
0x180043e12  jz      short loc_180043E2B
0x180043e14  call    cs:__imp_FreeLibrary
0x180043e1b  nop     dword ptr [rax+rax+00h]
0x180043e20  mov     cs:hSamlib, 0
0x180043e2b  lea     rcx, MSChapChangePassword; CriticalSection
0x180043e32  mov     cs:FnSamConnect, 0
0x180043e3d  mov     cs:FnSamOpenDomain, 0
0x180043e48  mov     cs:FnSamLookupNamesInDomain, 0
0x180043e53  mov     cs:FnSamOpenUser, 0
0x180043e5e  mov     cs:FnSamiChangePasswordUser, 0
0x180043e69  mov     cs:FnSamiChangePasswordUser2, 0
0x180043e74  mov     cs:FnSamCloseHandle, 0
0x180043e7f  mov     cs:FnSamFreeMemory, 0
0x180043e8a  call    cs:__imp_RtlLeaveCriticalSection
0x180043e91  nop     dword ptr [rax+rax+00h]
0x180043e96  mov     eax, ebx
0x180043e98  jmp     short loc_180043EB9
0x180043e9a  mov     cs:gAreChangePasswordFunctionsInitialized, 1
0x180043ea4  lea     rcx, MSChapChangePassword; CriticalSection
0x180043eab  call    cs:__imp_RtlLeaveCriticalSection
0x180043eb2  nop     dword ptr [rax+rax+00h]
0x180043eb7  xor     eax, eax
0x180043eb9  add     rsp, 20h
0x180043ebd  pop     rbx
0x180043ebe  retn
```
