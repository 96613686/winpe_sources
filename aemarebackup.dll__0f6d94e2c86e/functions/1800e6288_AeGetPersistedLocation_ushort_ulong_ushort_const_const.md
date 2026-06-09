# AeGetPersistedLocation(ushort *,ulong,ushort const * const)

- ea: `0x1800e6288`
- end: `0x1800e6333`
- name: `?AeGetPersistedLocation@@YAJPEAGKQEBG@Z`
- size: `171`
- prototype: `__int64 __fastcall(wchar_t *Destination, __int64, const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800e633c`

## callees

- `0x1800058f0`
- `0x1800e6288`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e62c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e62c8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800e62ac`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800e62ac`

## string_xrefs

- `0x1800e62a3`: `ntdll.dll`
- `0x1800e62dc`: `Amcache`

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
0x1800e6288  mov     [rsp+arg_0], rbx
0x1800e628d  mov     [rsp+arg_8], rsi
0x1800e6292  push    rdi
0x1800e6293  sub     rsp, 40h
0x1800e6297  mov     rdi, r8
0x1800e629a  mov     rsi, rcx
0x1800e629d  mov     r8d, 800h; dwFlags
0x1800e62a3  lea     rcx, LibFileName; "ntdll.dll"
0x1800e62aa  xor     edx, edx; hFile
0x1800e62ac  call    cs:__imp_LoadLibraryExW
0x1800e62b2  test    rax, rax
0x1800e62b5  jnz     short loc_1800E62BE
0x1800e62b7  mov     ebx, 80004005h
0x1800e62bc  jmp     short loc_1800E630A
0x1800e62be  lea     rdx, aRtlgetpersiste; "RtlGetPersistedStateLocation"
0x1800e62c5  mov     rcx, rax; hModule
0x1800e62c8  call    cs:__imp_GetProcAddress
0x1800e62ce  test    rax, rax
0x1800e62d1  jz      short loc_1800E62B7
0x1800e62d3  mov     [rsp+48h+var_18], 0
0x1800e62dc  lea     rcx, aAmcache; "Amcache"
0x1800e62e3  mov     [rsp+48h+var_20], 20Ah
0x1800e62eb  mov     r9d, 1
0x1800e62f1  mov     r8, rdi
0x1800e62f4  mov     [rsp+48h+var_28], rsi
0x1800e62f9  xor     edx, edx
0x1800e62fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6300  mov     ebx, eax
0x1800e6302  or      ebx, 10000000h
0x1800e6308  jge     short loc_1800E6321
0x1800e630a  mov     r8, rdi; Source
0x1800e630d  mov     edx, 105h; SizeInWords
0x1800e6312  mov     rcx, rsi; Destination
0x1800e6315  call    wcscpy_s
0x1800e631a  xor     ecx, ecx
0x1800e631c  test    eax, eax
0x1800e631e  cmovz   ebx, ecx
0x1800e6321  mov     rsi, [rsp+48h+arg_8]
0x1800e6326  mov     eax, ebx
0x1800e6328  mov     rbx, [rsp+48h+arg_0]
0x1800e632d  add     rsp, 40h
0x1800e6331  pop     rdi
0x1800e6332  retn
```
