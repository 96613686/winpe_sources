# AeGetPersistedLocation(ushort *,ulong,ushort const * const)

- ea: `0x180036924`
- end: `0x1800369cf`
- name: `?AeGetPersistedLocation@@YAJPEAGKQEBG@Z`
- size: `171`
- prototype: `__int64 __fastcall(wchar_t *Destination, unsigned int, const unsigned __int16 *const)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180036ad0`

## callees

- `0x1800068fc`
- `0x180036924`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180036948`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180036948`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180036964`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180036964`

## string_xrefs

- `0x18003693f`: `ntdll.dll`
- `0x180036978`: `Amcache`

## pseudocode

```c
__int64 __fastcall AeGetPersistedLocation(wchar_t *Destination, __int64 a2, const wchar_t *a3)
{
  HMODULE Library; // rax
  unsigned int v6; // ebx
  FARPROC ProcAddress; // rax
  int v8; // eax

  Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
  if ( Library && (ProcAddress = GetProcAddress(Library, "RtlGetPersistedStateLocation")) != 0 )
  {
    v8 = ((__int64 (__fastcall *)(const unsigned __int16 *, _QWORD, const wchar_t *, __int64, wchar_t *, int, _QWORD))ProcAddress)(
           L"Amcache",
           0,
           a3,
           1,
           Destination,
           522,
           0);
    v6 = v8 | 0x10000000;
    if ( v8 >= 0 )
      return v6;
  }
  else
  {
    v6 = -2147467259;
  }
  if ( !wcscpy_s(Destination, 0x105u, a3) )
    return 0;
  return v6;
}

```

## disassembly

```asm
0x180036924  mov     [rsp+arg_0], rbx
0x180036929  mov     [rsp+arg_8], rsi
0x18003692e  push    rdi
0x18003692f  sub     rsp, 40h
0x180036933  mov     rdi, r8
0x180036936  mov     rsi, rcx
0x180036939  mov     r8d, 800h; dwFlags
0x18003693f  lea     rcx, LibFileName; "ntdll.dll"
0x180036946  xor     edx, edx; hFile
0x180036948  call    cs:__imp_LoadLibraryExW
0x18003694e  test    rax, rax
0x180036951  jnz     short loc_18003695A
0x180036953  mov     ebx, 80004005h
0x180036958  jmp     short loc_1800369A6
0x18003695a  lea     rdx, aRtlgetpersiste; "RtlGetPersistedStateLocation"
0x180036961  mov     rcx, rax; hModule
0x180036964  call    cs:__imp_GetProcAddress
0x18003696a  test    rax, rax
0x18003696d  jz      short loc_180036953
0x18003696f  mov     [rsp+48h+var_18], 0
0x180036978  lea     rcx, aAmcache; "Amcache"
0x18003697f  mov     [rsp+48h+var_20], 20Ah
0x180036987  mov     r9d, 1
0x18003698d  mov     r8, rdi
0x180036990  mov     [rsp+48h+var_28], rsi
0x180036995  xor     edx, edx
0x180036997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003699c  mov     ebx, eax
0x18003699e  or      ebx, 10000000h
0x1800369a4  jge     short loc_1800369BD
0x1800369a6  mov     r8, rdi; Source
0x1800369a9  mov     edx, 105h; SizeInWords
0x1800369ae  mov     rcx, rsi; Destination
0x1800369b1  call    wcscpy_s
0x1800369b6  xor     ecx, ecx
0x1800369b8  test    eax, eax
0x1800369ba  cmovz   ebx, ecx
0x1800369bd  mov     rsi, [rsp+48h+arg_8]
0x1800369c2  mov     eax, ebx
0x1800369c4  mov     rbx, [rsp+48h+arg_0]
0x1800369c9  add     rsp, 40h
0x1800369cd  pop     rdi
0x1800369ce  retn
```
