# AeGetPersistedLocation(ushort *,ulong,ushort const * const)

- ea: `0x18012526c`
- end: `0x180125317`
- name: `?AeGetPersistedLocation@@YAJPEAGKQEBG@Z`
- size: `171`
- prototype: `__int64 __fastcall(wchar_t *Destination, __int64, const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18005466c`

## callees

- `0x18005a898`
- `0x18012526c`
- `0x180130010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180125290`
- `KERNEL32!LoadLibraryExW` at `0x180125290`
- `KERNEL32!GetProcAddress` at `0x1801252ac`
- `KERNEL32!GetProcAddress` at `0x1801252ac`

## string_xrefs

- `0x180125287`: `ntdll.dll`
- `0x1801252c0`: `Amcache`

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
0x18012526c  mov     [rsp+arg_0], rbx
0x180125271  mov     [rsp+arg_8], rsi
0x180125276  push    rdi
0x180125277  sub     rsp, 40h
0x18012527b  mov     rdi, r8
0x18012527e  mov     rsi, rcx
0x180125281  mov     r8d, 800h; dwFlags
0x180125287  lea     rcx, LibFileName; "ntdll.dll"
0x18012528e  xor     edx, edx; hFile
0x180125290  call    cs:__imp_LoadLibraryExW
0x180125296  test    rax, rax
0x180125299  jnz     short loc_1801252A2
0x18012529b  mov     ebx, 80004005h
0x1801252a0  jmp     short loc_1801252EE
0x1801252a2  lea     rdx, aRtlgetpersiste; "RtlGetPersistedStateLocation"
0x1801252a9  mov     rcx, rax; hModule
0x1801252ac  call    cs:__imp_GetProcAddress
0x1801252b2  test    rax, rax
0x1801252b5  jz      short loc_18012529B
0x1801252b7  mov     [rsp+48h+var_18], 0
0x1801252c0  lea     rcx, aAmcache; "Amcache"
0x1801252c7  mov     [rsp+48h+var_20], 20Ah
0x1801252cf  mov     r9d, 1
0x1801252d5  mov     r8, rdi
0x1801252d8  mov     [rsp+48h+var_28], rsi
0x1801252dd  xor     edx, edx
0x1801252df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801252e4  mov     ebx, eax
0x1801252e6  or      ebx, 10000000h
0x1801252ec  jge     short loc_180125305
0x1801252ee  mov     r8, rdi; Source
0x1801252f1  mov     edx, 105h; SizeInWords
0x1801252f6  mov     rcx, rsi; Destination
0x1801252f9  call    wcscpy_s
0x1801252fe  xor     ecx, ecx
0x180125300  test    eax, eax
0x180125302  cmovz   ebx, ecx
0x180125305  mov     rsi, [rsp+48h+arg_8]
0x18012530a  mov     eax, ebx
0x18012530c  mov     rbx, [rsp+48h+arg_0]
0x180125311  add     rsp, 40h
0x180125315  pop     rdi
0x180125316  retn
```
