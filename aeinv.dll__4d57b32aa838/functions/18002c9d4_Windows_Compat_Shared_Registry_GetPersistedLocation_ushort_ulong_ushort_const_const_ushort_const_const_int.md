# Windows::Compat::Shared::Registry::GetPersistedLocation(ushort *,ulong,ushort const * const,ushort const * const,int)

- ea: `0x18002c9d4`
- end: `0x18002ca8a`
- name: `?GetPersistedLocation@Registry@Shared@Compat@Windows@@SAJPEAGKQEBG1H@Z`
- size: `182`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180053728`
- `0x180065240`

## callees

- `0x18002c9d4`
- `0x180130010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002ca2a`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002ca2a`
- `KERNEL32!LoadLibraryExW` at `0x18002c9f5`
- `KERNEL32!LoadLibraryExW` at `0x18002c9f5`
- `KERNEL32!FreeLibrary` at `0x18002ca79`
- `KERNEL32!FreeLibrary` at `0x18002ca79`
- `KERNEL32!GetProcAddress` at `0x18002ca14`
- `KERNEL32!GetProcAddress` at `0x18002ca14`

## string_xrefs

- `0x18002c9e9`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Shared::Registry::GetPersistedLocation(
        unsigned __int16 *a1,
        __int64 a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5)
{
  HMODULE Library; // rax
  HMODULE v9; // rdi
  unsigned int v10; // ebx
  FARPROC ProcAddress; // rax
  int v12; // eax

  Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
  v9 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "RtlGetPersistedStateLocation");
    if ( ProcAddress )
    {
      v12 = ((__int64 (__fastcall *)(const unsigned __int16 *, _QWORD, const unsigned __int16 *, bool, unsigned __int16 *, int, _QWORD))ProcAddress)(
              a3,
              0,
              a4,
              a5 == 0,
              a1,
              520,
              0);
      v10 = v12 | 0x10000000;
      if ( v12 < 0 )
        goto LABEL_8;
    }
    else if ( (unsigned int)_o_wcscpy_s(a1, 260, a4) )
    {
      v10 = -2147467259;
LABEL_8:
      FreeLibrary(v9);
      return v10;
    }
    v10 = 0;
    goto LABEL_8;
  }
  return (unsigned int)-2147467259;
}

```

## disassembly

```asm
0x18002c9d4  push    rbx
0x18002c9d6  push    rbp
0x18002c9d7  push    rsi
0x18002c9d8  push    rdi
0x18002c9d9  sub     rsp, 48h
0x18002c9dd  mov     rbp, r8
0x18002c9e0  mov     rsi, rcx
0x18002c9e3  mov     r8d, 800h; dwFlags
0x18002c9e9  lea     rcx, LibFileName; "ntdll.dll"
0x18002c9f0  xor     edx, edx; hFile
0x18002c9f2  mov     rbx, r9
0x18002c9f5  call    cs:__imp_LoadLibraryExW
0x18002c9fb  mov     rdi, rax
0x18002c9fe  test    rax, rax
0x18002ca01  jnz     short loc_18002CA0A
0x18002ca03  mov     ebx, 80004005h
0x18002ca08  jmp     short loc_18002CA7F
0x18002ca0a  lea     rdx, aRtlgetpersiste; "RtlGetPersistedStateLocation"
0x18002ca11  mov     rcx, rdi; hModule
0x18002ca14  call    cs:__imp_GetProcAddress
0x18002ca1a  mov     r8, rbx
0x18002ca1d  test    rax, rax
0x18002ca20  jnz     short loc_18002CA3B
0x18002ca22  mov     edx, 104h
0x18002ca27  mov     rcx, rsi
0x18002ca2a  call    cs:__imp__o_wcscpy_s
0x18002ca30  test    eax, eax
0x18002ca32  jz      short loc_18002CA74
0x18002ca34  mov     ebx, 80004005h
0x18002ca39  jmp     short loc_18002CA76
0x18002ca3b  xor     r9d, r9d
0x18002ca3e  mov     [rsp+68h+var_38], 0
0x18002ca47  cmp     [rsp+68h+arg_20], r9d
0x18002ca4f  mov     rcx, rbp
0x18002ca52  mov     [rsp+68h+var_40], 208h
0x18002ca5a  setz    r9b
0x18002ca5e  mov     [rsp+68h+var_48], rsi
0x18002ca63  xor     edx, edx
0x18002ca65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ca6a  mov     ebx, eax
0x18002ca6c  or      ebx, 10000000h
0x18002ca72  jl      short loc_18002CA76
0x18002ca74  xor     ebx, ebx
0x18002ca76  mov     rcx, rdi; hLibModule
0x18002ca79  call    cs:__imp_FreeLibrary
0x18002ca7f  mov     eax, ebx
0x18002ca81  add     rsp, 48h
0x18002ca85  pop     rdi
0x18002ca86  pop     rsi
0x18002ca87  pop     rbp
0x18002ca88  pop     rbx
0x18002ca89  retn
```
