# TelemetryPermissionsDownlevel::IsLessThanWin10TelemetryTypeAllowed(TelemetryType)

- ea: `0x18005ede4`
- end: `0x18005ee4b`
- name: `?IsLessThanWin10TelemetryTypeAllowed@TelemetryPermissionsDownlevel@@CA_NW4TelemetryType@@@Z`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18005dc50`

## callees

- `0x18005ede4`
- `0x18006f010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18005ee00`
- `KERNEL32!LoadLibraryExW` at `0x18005ee00`
- `KERNEL32!FreeLibrary` at `0x18005ee37`
- `KERNEL32!FreeLibrary` at `0x18005ee37`
- `KERNEL32!GetProcAddress` at `0x18005ee18`
- `KERNEL32!GetProcAddress` at `0x18005ee18`

## string_xrefs

- `0x18005edf0`: `ntdll.dll`

## pseudocode

```c
bool TelemetryPermissionsDownlevel::IsLessThanWin10TelemetryTypeAllowed()
{
  bool v0; // di
  HMODULE Library; // rax
  HMODULE v2; // rbx
  FARPROC ProcAddress; // rax

  v0 = 0;
  Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
  v2 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "WinSqmIsOptedInEx");
    if ( ProcAddress )
      v0 = ((unsigned int (__fastcall *)(__int64))ProcAddress)(4) == 1;
    FreeLibrary(v2);
  }
  return v0;
}

```

## disassembly

```asm
0x18005ede4  mov     [rsp+arg_0], rbx
0x18005ede9  push    rdi
0x18005edea  sub     rsp, 20h
0x18005edee  xor     edx, edx; hFile
0x18005edf0  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18005edf7  mov     r8d, 800h; dwFlags
0x18005edfd  xor     dil, dil
0x18005ee00  call    cs:__imp_LoadLibraryExW
0x18005ee06  mov     rbx, rax
0x18005ee09  test    rax, rax
0x18005ee0c  jz      short loc_18005EE3D
0x18005ee0e  lea     rdx, aWinsqmisoptedi; "WinSqmIsOptedInEx"
0x18005ee15  mov     rcx, rax; hModule
0x18005ee18  call    cs:__imp_GetProcAddress
0x18005ee1e  test    rax, rax
0x18005ee21  jz      short loc_18005EE34
0x18005ee23  mov     ecx, 4
0x18005ee28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ee2d  cmp     eax, 1
0x18005ee30  setz    dil
0x18005ee34  mov     rcx, rbx; hLibModule
0x18005ee37  call    cs:__imp_FreeLibrary
0x18005ee3d  mov     rbx, [rsp+28h+arg_0]
0x18005ee42  mov     al, dil
0x18005ee45  add     rsp, 20h
0x18005ee49  pop     rdi
0x18005ee4a  retn
```
