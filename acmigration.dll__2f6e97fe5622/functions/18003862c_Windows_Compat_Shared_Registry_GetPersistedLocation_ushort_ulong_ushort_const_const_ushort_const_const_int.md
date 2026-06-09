# Windows::Compat::Shared::Registry::GetPersistedLocation(ushort *,ulong,ushort const * const,ushort const * const,int)

- ea: `0x18003862c`
- end: `0x1800386db`
- name: `?GetPersistedLocation@Registry@Shared@Compat@Windows@@SAJPEAGKQEBG1H@Z`
- size: `175`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, const unsigned __int16 *const, const unsigned __int16 *const, int)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800377f0`
- `0x180037c64`
- `0x180038b90`
- `0x1800390fc`
- `0x18004e6e4`

## callees

- `0x18003862c`
- `0x18006a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180038681`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180038681`
- `KERNEL32!FreeLibrary` at `0x1800386c8`
- `KERNEL32!FreeLibrary` at `0x1800386c8`
- `KERNEL32!LoadLibraryExW` at `0x180038648`
- `KERNEL32!LoadLibraryExW` at `0x180038648`
- `KERNEL32!GetProcAddress` at `0x180038667`
- `KERNEL32!GetProcAddress` at `0x180038667`

## string_xrefs

- `0x18003863b`: `ntdll.dll`
- `0x18003866d`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`
- `0x18003869b`: `AppCompatFlags`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Shared::Registry::GetPersistedLocation(
        unsigned __int16 *a1,
        __int64 a2,
        const unsigned __int16 *const a3,
        const unsigned __int16 *const a4)
{
  HMODULE Library; // rax
  HMODULE v6; // rdi
  unsigned int v7; // ebx
  FARPROC ProcAddress; // rax
  int v9; // eax

  Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
  v6 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "RtlGetPersistedStateLocation");
    if ( ProcAddress )
    {
      v9 = ((__int64 (__fastcall *)(const wchar_t *, _QWORD, const wchar_t *, _QWORD, unsigned __int16 *, int, _QWORD))ProcAddress)(
             L"AppCompatFlags",
             0,
             L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags",
             0,
             a1,
             520,
             0);
      v7 = v9 | 0x10000000;
      if ( v9 < 0 )
        goto LABEL_8;
    }
    else if ( (unsigned int)_o_wcscpy_s(a1, 260, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags") )
    {
      v7 = -2147467259;
LABEL_8:
      FreeLibrary(v6);
      return v7;
    }
    v7 = 0;
    goto LABEL_8;
  }
  return (unsigned int)-2147467259;
}

```

## disassembly

```asm
0x18003862c  mov     [rsp+arg_0], rbx
0x180038631  push    rdi
0x180038632  sub     rsp, 40h
0x180038636  mov     rbx, rcx
0x180038639  xor     edx, edx; hFile
0x18003863b  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180038642  mov     r8d, 800h; dwFlags
0x180038648  call    cs:__imp_LoadLibraryExW
0x18003864e  mov     rdi, rax
0x180038651  test    rax, rax
0x180038654  jnz     short loc_18003865D
0x180038656  mov     ebx, 80004005h
0x18003865b  jmp     short loc_1800386CE
0x18003865d  lea     rdx, aRtlgetpersiste; "RtlGetPersistedStateLocation"
0x180038664  mov     rcx, rdi; hModule
0x180038667  call    cs:__imp_GetProcAddress
0x18003866d  lea     r8, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180038674  test    rax, rax
0x180038677  jnz     short loc_180038692
0x180038679  mov     edx, 104h
0x18003867e  mov     rcx, rbx
0x180038681  call    cs:__imp__o_wcscpy_s
0x180038687  test    eax, eax
0x180038689  jz      short loc_1800386C3
0x18003868b  mov     ebx, 80004005h
0x180038690  jmp     short loc_1800386C5
0x180038692  mov     [rsp+48h+var_18], 0
0x18003869b  lea     rcx, aAppcompatflags; "AppCompatFlags"
0x1800386a2  mov     [rsp+48h+var_20], 208h
0x1800386aa  xor     r9d, r9d
0x1800386ad  xor     edx, edx
0x1800386af  mov     [rsp+48h+var_28], rbx
0x1800386b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800386b9  mov     ebx, eax
0x1800386bb  or      ebx, 10000000h
0x1800386c1  jl      short loc_1800386C5
0x1800386c3  xor     ebx, ebx
0x1800386c5  mov     rcx, rdi; hLibModule
0x1800386c8  call    cs:__imp_FreeLibrary
0x1800386ce  mov     eax, ebx
0x1800386d0  mov     rbx, [rsp+48h+arg_0]
0x1800386d5  add     rsp, 40h
0x1800386d9  pop     rdi
0x1800386da  retn
```
