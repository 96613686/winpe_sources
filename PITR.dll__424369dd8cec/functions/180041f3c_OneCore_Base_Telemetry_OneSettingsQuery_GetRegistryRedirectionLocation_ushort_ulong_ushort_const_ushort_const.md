# OneCore::Base::Telemetry::OneSettingsQuery::GetRegistryRedirectionLocation(ushort *,ulong,ushort const *,ushort const *)

- ea: `0x180041f3c`
- end: `0x180041fe0`
- name: `?GetRegistryRedirectionLocation@OneSettingsQuery@Telemetry@Base@OneCore@@QEAAJPEAGKPEBG1@Z`
- size: `164`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *this, unsigned __int16 *, __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800406c0`

## callees

- `0x180041f3c`
- `0x180053010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180041fc6`
- `msvcrt!wcscpy_s` at `0x180041fc6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180041f58`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180041f58`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180041f74`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180041f74`

## string_xrefs

- `0x180041f49`: `ntdll.dll`

## pseudocode

```c
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
0x180041f3c  mov     [rsp+arg_0], rbx
0x180041f41  push    rdi
0x180041f42  sub     rsp, 40h
0x180041f46  mov     rdi, rdx
0x180041f49  lea     rcx, aNtdllDll_2; "ntdll.dll"
0x180041f50  xor     edx, edx; hFile
0x180041f52  mov     r8d, 800h; dwFlags
0x180041f58  call    cs:__imp_LoadLibraryExW
0x180041f5e  test    rax, rax
0x180041f61  jnz     short loc_180041F6A
0x180041f63  mov     ebx, 80004005h
0x180041f68  jmp     short loc_180041FB7
0x180041f6a  lea     rdx, aRtlgetpersiste; "RtlGetPersistedStateLocation"
0x180041f71  mov     rcx, rax; hModule
0x180041f74  call    cs:__imp_GetProcAddress
0x180041f7a  test    rax, rax
0x180041f7d  jz      short loc_180041F63
0x180041f7f  mov     [rsp+48h+var_18], 0
0x180041f88  lea     r8, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180041f8f  mov     [rsp+48h+var_20], 208h
0x180041f97  lea     rcx, pszAgentW; "OneSettingsQuery"
0x180041f9e  xor     r9d, r9d
0x180041fa1  mov     [rsp+48h+var_28], rdi
0x180041fa6  xor     edx, edx
0x180041fa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041fad  mov     ebx, eax
0x180041faf  or      ebx, 10000000h
0x180041fb5  jge     short loc_180041FD3
0x180041fb7  lea     r8, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180041fbe  mov     edx, 104h; SizeInWords
0x180041fc3  mov     rcx, rdi; Destination
0x180041fc6  call    cs:__imp_wcscpy_s
0x180041fcc  xor     ecx, ecx
0x180041fce  test    eax, eax
0x180041fd0  cmovz   ebx, ecx
0x180041fd3  mov     eax, ebx
0x180041fd5  mov     rbx, [rsp+48h+arg_0]
0x180041fda  add     rsp, 40h
0x180041fde  pop     rdi
0x180041fdf  retn
```
