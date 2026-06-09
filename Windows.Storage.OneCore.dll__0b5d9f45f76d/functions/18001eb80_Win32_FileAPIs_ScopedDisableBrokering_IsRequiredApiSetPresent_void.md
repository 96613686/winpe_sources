# Win32::FileAPIs::ScopedDisableBrokering::IsRequiredApiSetPresent(void)

- ea: `0x18001eb80`
- end: `0x18001ec0c`
- name: `?IsRequiredApiSetPresent@ScopedDisableBrokering@FileAPIs@Win32@@SA_NXZ`
- size: `140`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001c234`
- `0x18001c730`

## callees

- `0x18001eb80`
- `0x180020f1c`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001ebaf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001ebaf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001ebc5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001ebc5`

## string_xrefs

- `0x18001eba6`: `ntdll.dll`
- `0x18001ebd7`: `ext-ms-win-winrt-storage-win32broker-l1-1-0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool Win32::FileAPIs::ScopedDisableBrokering::IsRequiredApiSetPresent(void)
{
  int v0; // eax
  FARPROC ProcAddress; // rax
  int v2; // eax
  HMODULE phModule; // [rsp+30h] [rbp+8h] BYREF

  v0 = Win32::FileAPIs::ScopedDisableBrokering::ApiSetState;
  if ( !Win32::FileAPIs::ScopedDisableBrokering::ApiSetState )
  {
    phModule = 0;
    Win32::FileAPIs::ScopedDisableBrokering::unique_hmodule::release((Win32::FileAPIs::ScopedDisableBrokering::unique_hmodule *)&phModule);
    if ( GetModuleHandleExW(0, L"ntdll.dll", &phModule)
      && (ProcAddress = GetProcAddress(phModule, "RtlIsApiSetImplemented")) != 0 )
    {
      v2 = ((((int (__fastcall *)(const char *))ProcAddress)("ext-ms-win-winrt-storage-win32broker-l1-1-0") >> 31) & 1)
         + 1;
    }
    else
    {
      v2 = 2;
    }
    Win32::FileAPIs::ScopedDisableBrokering::ApiSetState = v2;
    Win32::FileAPIs::ScopedDisableBrokering::unique_hmodule::release((Win32::FileAPIs::ScopedDisableBrokering::unique_hmodule *)&phModule);
    v0 = Win32::FileAPIs::ScopedDisableBrokering::ApiSetState;
  }
  return v0 == 1;
}

```

## disassembly

```asm
0x18001eb80  sub     rsp, 28h
0x18001eb84  mov     eax, cs:?ApiSetState@ScopedDisableBrokering@FileAPIs@Win32@@0W4ApiPresence@123@A; Win32::FileAPIs::ScopedDisableBrokering::ApiPresence Win32::FileAPIs::ScopedDisableBrokering::ApiSetState
0x18001eb8a  test    eax, eax
0x18001eb8c  jnz     short loc_18001EC01
0x18001eb8e  mov     [rsp+28h+phModule], 0
0x18001eb97  lea     rcx, [rsp+28h+phModule]; this
0x18001eb9c  call    ?release@unique_hmodule@ScopedDisableBrokering@FileAPIs@Win32@@QEAAXXZ; Win32::FileAPIs::ScopedDisableBrokering::unique_hmodule::release(void)
0x18001eba1  lea     r8, [rsp+28h+phModule]; phModule
0x18001eba6  lea     rdx, ModuleName; "ntdll.dll"
0x18001ebad  xor     ecx, ecx; dwFlags
0x18001ebaf  call    cs:__imp_GetModuleHandleExW
0x18001ebb5  test    eax, eax
0x18001ebb7  jz      short loc_18001EBD0
0x18001ebb9  lea     rdx, ProcName; "RtlIsApiSetImplemented"
0x18001ebc0  mov     rcx, [rsp+28h+phModule]; hModule
0x18001ebc5  call    cs:__imp_GetProcAddress
0x18001ebcb  test    rax, rax
0x18001ebce  jnz     short loc_18001EBD7
0x18001ebd0  mov     eax, 2
0x18001ebd5  jmp     short loc_18001EBEB
0x18001ebd7  lea     rcx, aExtMsWinWinrtS_6; "ext-ms-win-winrt-storage-win32broker-l1"...
0x18001ebde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ebe3  sar     eax, 1Fh
0x18001ebe6  and     eax, 1
0x18001ebe9  inc     eax
0x18001ebeb  mov     cs:?ApiSetState@ScopedDisableBrokering@FileAPIs@Win32@@0W4ApiPresence@123@A, eax; Win32::FileAPIs::ScopedDisableBrokering::ApiPresence Win32::FileAPIs::ScopedDisableBrokering::ApiSetState
0x18001ebf1  lea     rcx, [rsp+28h+phModule]; this
0x18001ebf6  call    ?release@unique_hmodule@ScopedDisableBrokering@FileAPIs@Win32@@QEAAXXZ; Win32::FileAPIs::ScopedDisableBrokering::unique_hmodule::release(void)
0x18001ebfb  mov     eax, cs:?ApiSetState@ScopedDisableBrokering@FileAPIs@Win32@@0W4ApiPresence@123@A; Win32::FileAPIs::ScopedDisableBrokering::ApiPresence Win32::FileAPIs::ScopedDisableBrokering::ApiSetState
0x18001ec01  cmp     eax, 1
0x18001ec04  setz    al
0x18001ec07  add     rsp, 28h
0x18001ec0b  retn
```
