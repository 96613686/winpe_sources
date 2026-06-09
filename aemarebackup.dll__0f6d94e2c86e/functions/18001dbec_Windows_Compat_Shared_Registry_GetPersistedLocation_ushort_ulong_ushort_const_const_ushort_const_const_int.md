# Windows::Compat::Shared::Registry::GetPersistedLocation(ushort *,ulong,ushort const * const,ushort const * const,int)

- ea: `0x18001dbec`
- end: `0x18001dca2`
- name: `?GetPersistedLocation@Registry@Shared@Compat@Windows@@SAJPEAGKQEBG1H@Z`
- size: `182`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, const unsigned __int16 *const, const unsigned __int16 *const, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800208f8`
- `0x1800246a0`

## callees

- `0x18001dbec`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001dc42`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001dc42`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001dc2c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001dc2c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001dc91`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001dc91`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001dc0d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001dc0d`

## string_xrefs

- `0x18001dc01`: `ntdll.dll`

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
0x18001dbec  push    rbx
0x18001dbee  push    rbp
0x18001dbef  push    rsi
0x18001dbf0  push    rdi
0x18001dbf1  sub     rsp, 48h
0x18001dbf5  mov     rbp, r8
0x18001dbf8  mov     rsi, rcx
0x18001dbfb  mov     r8d, 800h; dwFlags
0x18001dc01  lea     rcx, LibFileName; "ntdll.dll"
0x18001dc08  xor     edx, edx; hFile
0x18001dc0a  mov     rbx, r9
0x18001dc0d  call    cs:__imp_LoadLibraryExW
0x18001dc13  mov     rdi, rax
0x18001dc16  test    rax, rax
0x18001dc19  jnz     short loc_18001DC22
0x18001dc1b  mov     ebx, 80004005h
0x18001dc20  jmp     short loc_18001DC97
0x18001dc22  lea     rdx, aRtlgetpersiste; "RtlGetPersistedStateLocation"
0x18001dc29  mov     rcx, rdi; hModule
0x18001dc2c  call    cs:__imp_GetProcAddress
0x18001dc32  mov     r8, rbx
0x18001dc35  test    rax, rax
0x18001dc38  jnz     short loc_18001DC53
0x18001dc3a  mov     edx, 104h
0x18001dc3f  mov     rcx, rsi
0x18001dc42  call    cs:__imp__o_wcscpy_s
0x18001dc48  test    eax, eax
0x18001dc4a  jz      short loc_18001DC8C
0x18001dc4c  mov     ebx, 80004005h
0x18001dc51  jmp     short loc_18001DC8E
0x18001dc53  xor     r9d, r9d
0x18001dc56  mov     [rsp+68h+var_38], 0
0x18001dc5f  cmp     [rsp+68h+arg_20], r9d
0x18001dc67  mov     rcx, rbp
0x18001dc6a  mov     [rsp+68h+var_40], 208h
0x18001dc72  setz    r9b
0x18001dc76  mov     [rsp+68h+var_48], rsi
0x18001dc7b  xor     edx, edx
0x18001dc7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc82  mov     ebx, eax
0x18001dc84  or      ebx, 10000000h
0x18001dc8a  jl      short loc_18001DC8E
0x18001dc8c  xor     ebx, ebx
0x18001dc8e  mov     rcx, rdi; hLibModule
0x18001dc91  call    cs:__imp_FreeLibrary
0x18001dc97  mov     eax, ebx
0x18001dc99  add     rsp, 48h
0x18001dc9d  pop     rdi
0x18001dc9e  pop     rsi
0x18001dc9f  pop     rbp
0x18001dca0  pop     rbx
0x18001dca1  retn
```
