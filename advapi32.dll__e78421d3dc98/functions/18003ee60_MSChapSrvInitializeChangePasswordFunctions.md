# MSChapSrvInitializeChangePasswordFunctions

- ea: `0x18003ee60`
- end: `0x18003f06f`
- name: `MSChapSrvInitializeChangePasswordFunctions`
- size: `527`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003ead0`
- `0x18003ed90`

## callees

- `0x18003ee60`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18003f046`
- `ntdll!RtlLeaveCriticalSection` at `0x18003f061`
- `ntdll!RtlLeaveCriticalSection` at `0x18003f046`
- `ntdll!RtlLeaveCriticalSection` at `0x18003f061`
- `ntdll!RtlEnterCriticalSection` at `0x18003ee7a`
- `ntdll!RtlEnterCriticalSection` at `0x18003ee7a`
- `KERNEL32!GetLastError` at `0x18003efc2`
- `KERNEL32!GetLastError` at `0x18003efc2`
- `KERNEL32!GetProcAddress` at `0x18003eebc`
- `KERNEL32!GetProcAddress` at `0x18003eee0`
- `KERNEL32!GetProcAddress` at `0x18003ef04`
- `KERNEL32!GetProcAddress` at `0x18003ef28`
- `KERNEL32!GetProcAddress` at `0x18003ef4c`
- `KERNEL32!GetProcAddress` at `0x18003ef6c`
- `KERNEL32!GetProcAddress` at `0x18003ef8c`
- `KERNEL32!GetProcAddress` at `0x18003efac`
- `KERNEL32!GetProcAddress` at `0x18003eebc`
- `KERNEL32!GetProcAddress` at `0x18003eee0`
- `KERNEL32!GetProcAddress` at `0x18003ef04`
- `KERNEL32!GetProcAddress` at `0x18003ef28`
- `KERNEL32!GetProcAddress` at `0x18003ef4c`
- `KERNEL32!GetProcAddress` at `0x18003ef6c`
- `KERNEL32!GetProcAddress` at `0x18003ef8c`
- `KERNEL32!GetProcAddress` at `0x18003efac`
- `KERNEL32!FreeLibrary` at `0x18003efd6`
- `KERNEL32!FreeLibrary` at `0x18003efd6`
- `KERNEL32!LoadLibraryExW` at `0x18003ee9c`
- `KERNEL32!LoadLibraryExW` at `0x18003ee9c`

## string_xrefs

- `0x18003ee8f`: `samlib.dll`
- `0x18003eed9`: `SamOpenDomain`
- `0x18003ef21`: `SamOpenUser`

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
0x18003ee60  push    rbx
0x18003ee62  sub     rsp, 20h
0x18003ee66  cmp     cs:gAreChangePasswordFunctionsInitialized, 0
0x18003ee6d  jnz     loc_18003F067
0x18003ee73  lea     rcx, MSChapChangePassword; CriticalSection
0x18003ee7a  call    cs:__imp_RtlEnterCriticalSection
0x18003ee80  cmp     cs:gAreChangePasswordFunctionsInitialized, 0
0x18003ee87  jnz     loc_18003F05A
0x18003ee8d  xor     edx, edx; hFile
0x18003ee8f  lea     rcx, aSamlibDll; "samlib.dll"
0x18003ee96  mov     r8d, 800h; dwFlags
0x18003ee9c  call    cs:__imp_LoadLibraryExW
0x18003eea2  mov     cs:hSamlib, rax
0x18003eea9  test    rax, rax
0x18003eeac  jz      loc_18003EFC2
0x18003eeb2  lea     rdx, aSamconnect; "SamConnect"
0x18003eeb9  mov     rcx, rax; hModule
0x18003eebc  call    cs:__imp_GetProcAddress
0x18003eec2  mov     cs:FnSamConnect, rax
0x18003eec9  test    rax, rax
0x18003eecc  jz      loc_18003EFC2
0x18003eed2  mov     rcx, cs:hSamlib; hModule
0x18003eed9  lea     rdx, aSamopendomain; "SamOpenDomain"
0x18003eee0  call    cs:__imp_GetProcAddress
0x18003eee6  mov     cs:FnSamOpenDomain, rax
0x18003eeed  test    rax, rax
0x18003eef0  jz      loc_18003EFC2
0x18003eef6  mov     rcx, cs:hSamlib; hModule
0x18003eefd  lea     rdx, aSamlookupnames; "SamLookupNamesInDomain"
0x18003ef04  call    cs:__imp_GetProcAddress
0x18003ef0a  mov     cs:FnSamLookupNamesInDomain, rax
0x18003ef11  test    rax, rax
0x18003ef14  jz      loc_18003EFC2
0x18003ef1a  mov     rcx, cs:hSamlib; hModule
0x18003ef21  lea     rdx, aSamopenuser; "SamOpenUser"
0x18003ef28  call    cs:__imp_GetProcAddress
0x18003ef2e  mov     cs:FnSamOpenUser, rax
0x18003ef35  test    rax, rax
0x18003ef38  jz      loc_18003EFC2
0x18003ef3e  mov     rcx, cs:hSamlib; hModule
0x18003ef45  lea     rdx, aSamclosehandle; "SamCloseHandle"
0x18003ef4c  call    cs:__imp_GetProcAddress
0x18003ef52  mov     cs:FnSamCloseHandle, rax
0x18003ef59  test    rax, rax
0x18003ef5c  jz      short loc_18003EFC2
0x18003ef5e  mov     rcx, cs:hSamlib; hModule
0x18003ef65  lea     rdx, aSamfreememory; "SamFreeMemory"
0x18003ef6c  call    cs:__imp_GetProcAddress
0x18003ef72  mov     cs:FnSamFreeMemory, rax
0x18003ef79  test    rax, rax
0x18003ef7c  jz      short loc_18003EFC2
0x18003ef7e  mov     rcx, cs:hSamlib; hModule
0x18003ef85  lea     rdx, aSamichangepass; "SamiChangePasswordUser"
0x18003ef8c  call    cs:__imp_GetProcAddress
0x18003ef92  mov     cs:FnSamiChangePasswordUser, rax
0x18003ef99  test    rax, rax
0x18003ef9c  jz      short loc_18003EFC2
0x18003ef9e  mov     rcx, cs:hSamlib; hModule
0x18003efa5  lea     rdx, aSamichangepass_0; "SamiChangePasswordUser2"
0x18003efac  call    cs:__imp_GetProcAddress
0x18003efb2  mov     cs:FnSamiChangePasswordUser2, rax
0x18003efb9  test    rax, rax
0x18003efbc  jnz     loc_18003F050
0x18003efc2  call    cs:__imp_GetLastError
0x18003efc8  mov     ebx, eax
0x18003efca  mov     rcx, cs:hSamlib; hLibModule
0x18003efd1  test    rcx, rcx
0x18003efd4  jz      short loc_18003EFE7
0x18003efd6  call    cs:__imp_FreeLibrary
0x18003efdc  mov     cs:hSamlib, 0
0x18003efe7  lea     rcx, MSChapChangePassword; CriticalSection
0x18003efee  mov     cs:FnSamConnect, 0
0x18003eff9  mov     cs:FnSamOpenDomain, 0
0x18003f004  mov     cs:FnSamLookupNamesInDomain, 0
0x18003f00f  mov     cs:FnSamOpenUser, 0
0x18003f01a  mov     cs:FnSamiChangePasswordUser, 0
0x18003f025  mov     cs:FnSamiChangePasswordUser2, 0
0x18003f030  mov     cs:FnSamCloseHandle, 0
0x18003f03b  mov     cs:FnSamFreeMemory, 0
0x18003f046  call    cs:__imp_RtlLeaveCriticalSection
0x18003f04c  mov     eax, ebx
0x18003f04e  jmp     short loc_18003F069
0x18003f050  mov     cs:gAreChangePasswordFunctionsInitialized, 1
0x18003f05a  lea     rcx, MSChapChangePassword; CriticalSection
0x18003f061  call    cs:__imp_RtlLeaveCriticalSection
0x18003f067  xor     eax, eax
0x18003f069  add     rsp, 20h
0x18003f06d  pop     rbx
0x18003f06e  retn
```
