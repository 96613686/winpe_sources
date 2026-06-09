# OneCore::Base::Telemetry::OneSettingsQuery::GetRegistryRedirectionLocation(ushort *,ulong,ushort const *,ushort const *)

- ea: `0x18001c1c0`
- end: `0x18001c264`
- name: `?GetRegistryRedirectionLocation@OneSettingsQuery@Telemetry@Base@OneCore@@QEAAJPEAGKPEBG1@Z`
- size: `164`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *this, unsigned __int16 *, __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180018ce8`

## callees

- `0x18001c1c0`
- `0x180036010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18001c24a`
- `msvcrt!wcscpy_s` at `0x18001c24a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001c1dc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001c1dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c1f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c1f8`

## string_xrefs

- `0x18001c1cd`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall OneCore::Base::Telemetry::OneSettingsQuery::GetRegistryRedirectionLocation(
        OneCore::Base::Telemetry::OneSettingsQuery *this,
        unsigned __int16 *a2,
        __int64 a3,
        const unsigned __int16 *a4)
{
  HMODULE Library; // rax
  unsigned int v6; // ebx
  FARPROC ProcAddress; // rax
  int v8; // eax

  Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
  if ( Library && (ProcAddress = GetProcAddress(Library, "RtlGetPersistedStateLocation")) != 0 )
  {
    v8 = ((__int64 (__fastcall *)(const WCHAR *, _QWORD, const wchar_t *, _QWORD, unsigned __int16 *, int, _QWORD))ProcAddress)(
           L"OneSettingsQuery",
           0,
           L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OneSettings",
           0,
           a2,
           520,
           0);
    v6 = v8 | 0x10000000;
    if ( v8 >= 0 )
      return v6;
  }
  else
  {
    v6 = -2147467259;
  }
  if ( !wcscpy_s(a2, 0x104u, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OneSettings") )
    return 0;
  return v6;
}

```

## disassembly

```asm
0x18001c1c0  mov     [rsp+arg_0], rbx
0x18001c1c5  push    rdi
0x18001c1c6  sub     rsp, 40h
0x18001c1ca  mov     rdi, rdx
0x18001c1cd  lea     rcx, LibFileName; "ntdll.dll"
0x18001c1d4  xor     edx, edx; hFile
0x18001c1d6  mov     r8d, 800h; dwFlags
0x18001c1dc  call    cs:__imp_LoadLibraryExW
0x18001c1e2  test    rax, rax
0x18001c1e5  jnz     short loc_18001C1EE
0x18001c1e7  mov     ebx, 80004005h
0x18001c1ec  jmp     short loc_18001C23B
0x18001c1ee  lea     rdx, aRtlgetpersiste; "RtlGetPersistedStateLocation"
0x18001c1f5  mov     rcx, rax; hModule
0x18001c1f8  call    cs:__imp_GetProcAddress
0x18001c1fe  test    rax, rax
0x18001c201  jz      short loc_18001C1E7
0x18001c203  mov     [rsp+48h+var_18], 0
0x18001c20c  lea     r8, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001c213  mov     [rsp+48h+var_20], 208h
0x18001c21b  lea     rcx, pszAgentW; "OneSettingsQuery"
0x18001c222  xor     r9d, r9d
0x18001c225  mov     [rsp+48h+var_28], rdi
0x18001c22a  xor     edx, edx
0x18001c22c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c231  mov     ebx, eax
0x18001c233  or      ebx, 10000000h
0x18001c239  jge     short loc_18001C257
0x18001c23b  lea     r8, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001c242  mov     edx, 104h; SizeInWords
0x18001c247  mov     rcx, rdi; Destination
0x18001c24a  call    cs:__imp_wcscpy_s
0x18001c250  xor     ecx, ecx
0x18001c252  test    eax, eax
0x18001c254  cmovz   ebx, ecx
0x18001c257  mov     eax, ebx
0x18001c259  mov     rbx, [rsp+48h+arg_0]
0x18001c25e  add     rsp, 40h
0x18001c262  pop     rdi
0x18001c263  retn
```
