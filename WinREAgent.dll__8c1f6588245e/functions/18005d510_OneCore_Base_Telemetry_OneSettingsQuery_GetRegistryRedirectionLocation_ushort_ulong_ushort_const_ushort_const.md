# OneCore::Base::Telemetry::OneSettingsQuery::GetRegistryRedirectionLocation(ushort *,ulong,ushort const *,ushort const *)

- ea: `0x18005d510`
- end: `0x18005d5b4`
- name: `?GetRegistryRedirectionLocation@OneSettingsQuery@Telemetry@Base@OneCore@@QEAAJPEAGKPEBG1@Z`
- size: `164`
- prototype: `int(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this, unsigned __int16 *, unsigned int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005b910`

## callees

- `0x18005d510`
- `0x18006f010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18005d59a`
- `msvcrt!wcscpy_s` at `0x18005d59a`
- `KERNEL32!LoadLibraryExW` at `0x18005d52c`
- `KERNEL32!LoadLibraryExW` at `0x18005d52c`
- `KERNEL32!GetProcAddress` at `0x18005d548`
- `KERNEL32!GetProcAddress` at `0x18005d548`

## string_xrefs

- `0x18005d51d`: `ntdll.dll`

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
0x18005d510  mov     [rsp+arg_0], rbx
0x18005d515  push    rdi
0x18005d516  sub     rsp, 40h
0x18005d51a  mov     rdi, rdx
0x18005d51d  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18005d524  xor     edx, edx; hFile
0x18005d526  mov     r8d, 800h; dwFlags
0x18005d52c  call    cs:__imp_LoadLibraryExW
0x18005d532  test    rax, rax
0x18005d535  jnz     short loc_18005D53E
0x18005d537  mov     ebx, 80004005h
0x18005d53c  jmp     short loc_18005D58B
0x18005d53e  lea     rdx, aRtlgetpersiste; "RtlGetPersistedStateLocation"
0x18005d545  mov     rcx, rax; hModule
0x18005d548  call    cs:__imp_GetProcAddress
0x18005d54e  test    rax, rax
0x18005d551  jz      short loc_18005D537
0x18005d553  mov     [rsp+48h+var_18], 0
0x18005d55c  lea     r8, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18005d563  mov     [rsp+48h+var_20], 208h
0x18005d56b  lea     rcx, pszAgentW; "OneSettingsQuery"
0x18005d572  xor     r9d, r9d
0x18005d575  mov     [rsp+48h+var_28], rdi
0x18005d57a  xor     edx, edx
0x18005d57c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d581  mov     ebx, eax
0x18005d583  or      ebx, 10000000h
0x18005d589  jge     short loc_18005D5A7
0x18005d58b  lea     r8, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18005d592  mov     edx, 104h; SizeInWords
0x18005d597  mov     rcx, rdi; Destination
0x18005d59a  call    cs:__imp_wcscpy_s
0x18005d5a0  xor     ecx, ecx
0x18005d5a2  test    eax, eax
0x18005d5a4  cmovz   ebx, ecx
0x18005d5a7  mov     eax, ebx
0x18005d5a9  mov     rbx, [rsp+48h+arg_0]
0x18005d5ae  add     rsp, 40h
0x18005d5b2  pop     rdi
0x18005d5b3  retn
```
