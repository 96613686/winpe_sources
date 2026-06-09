# Windows::Compat::Shared::Registry::GetPersistedLocation(ushort *,ulong,ushort const * const,ushort const * const,int)

- ea: `0x180014e44`
- end: `0x180014efa`
- name: `?GetPersistedLocation@Registry@Shared@Compat@Windows@@SAJPEAGKQEBG1H@Z`
- size: `182`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, const unsigned __int16 *const, const unsigned __int16 *const, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180012c20`
- `0x180016ff8`

## callees

- `0x180014e44`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180014e9a`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180014e9a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180014ee9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180014ee9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180014e65`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180014e65`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180014e84`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180014e84`

## string_xrefs

- `0x180014e59`: `ntdll.dll`

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
0x180014e44  push    rbx
0x180014e46  push    rbp
0x180014e47  push    rsi
0x180014e48  push    rdi
0x180014e49  sub     rsp, 48h
0x180014e4d  mov     rbp, r8
0x180014e50  mov     rsi, rcx
0x180014e53  mov     r8d, 800h; dwFlags
0x180014e59  lea     rcx, LibFileName; "ntdll.dll"
0x180014e60  xor     edx, edx; hFile
0x180014e62  mov     rbx, r9
0x180014e65  call    cs:__imp_LoadLibraryExW
0x180014e6b  mov     rdi, rax
0x180014e6e  test    rax, rax
0x180014e71  jnz     short loc_180014E7A
0x180014e73  mov     ebx, 80004005h
0x180014e78  jmp     short loc_180014EEF
0x180014e7a  lea     rdx, aRtlgetpersiste; "RtlGetPersistedStateLocation"
0x180014e81  mov     rcx, rdi; hModule
0x180014e84  call    cs:__imp_GetProcAddress
0x180014e8a  mov     r8, rbx
0x180014e8d  test    rax, rax
0x180014e90  jnz     short loc_180014EAB
0x180014e92  mov     edx, 104h
0x180014e97  mov     rcx, rsi
0x180014e9a  call    cs:__imp__o_wcscpy_s
0x180014ea0  test    eax, eax
0x180014ea2  jz      short loc_180014EE4
0x180014ea4  mov     ebx, 80004005h
0x180014ea9  jmp     short loc_180014EE6
0x180014eab  xor     r9d, r9d
0x180014eae  mov     [rsp+68h+var_38], 0
0x180014eb7  cmp     [rsp+68h+arg_20], r9d
0x180014ebf  mov     rcx, rbp
0x180014ec2  mov     [rsp+68h+var_40], 208h
0x180014eca  setz    r9b
0x180014ece  mov     [rsp+68h+var_48], rsi
0x180014ed3  xor     edx, edx
0x180014ed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014eda  mov     ebx, eax
0x180014edc  or      ebx, 10000000h
0x180014ee2  jl      short loc_180014EE6
0x180014ee4  xor     ebx, ebx
0x180014ee6  mov     rcx, rdi; hLibModule
0x180014ee9  call    cs:__imp_FreeLibrary
0x180014eef  mov     eax, ebx
0x180014ef1  add     rsp, 48h
0x180014ef5  pop     rdi
0x180014ef6  pop     rsi
0x180014ef7  pop     rbp
0x180014ef8  pop     rbx
0x180014ef9  retn
```
