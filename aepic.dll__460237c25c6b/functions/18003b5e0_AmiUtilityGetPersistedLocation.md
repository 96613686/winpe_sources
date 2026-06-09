# AmiUtilityGetPersistedLocation

- ea: `0x18003b5e0`
- end: `0x18003b68c`
- name: `AmiUtilityGetPersistedLocation`
- size: `172`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180039f04`
- `0x18003a1e4`
- `0x18003a880`
- `0x18003aefc`
- `0x18003b2c4`

## callees

- `0x18003b5e0`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18003b674`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18003b674`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003b603`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003b603`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003b61f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003b61f`

## string_xrefs

- `0x18003b5f9`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall AmiUtilityGetPersistedLocation(__int64 a1, unsigned int a2, __int64 a3, __int64 a4, int a5)
{
  __int64 v6; // rsi
  HMODULE Library; // rax
  unsigned int v10; // ebx
  FARPROC ProcAddress; // rax
  int v12; // eax

  v6 = a2;
  Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
  if ( Library && (ProcAddress = GetProcAddress(Library, "RtlGetPersistedStateLocation")) != 0 )
  {
    v12 = ((__int64 (__fastcall *)(__int64, _QWORD, __int64, bool, __int64, int, _QWORD))ProcAddress)(
            a3,
            0,
            a4,
            a5 == 0,
            a1,
            2 * (int)v6,
            0);
    v10 = v12 | 0x10000000;
    if ( v12 >= 0 )
      return v10;
  }
  else
  {
    v10 = -2147467259;
  }
  if ( !(unsigned int)_o_wcscpy_s(a1, v6, a4) )
    return 0;
  return v10;
}

```

## disassembly

```asm
0x18003b5e0  push    rbx
0x18003b5e2  push    rbp
0x18003b5e3  push    rsi
0x18003b5e4  push    rdi
0x18003b5e5  sub     rsp, 48h
0x18003b5e9  mov     rbx, r8
0x18003b5ec  mov     esi, edx
0x18003b5ee  mov     rbp, rcx
0x18003b5f1  xor     edx, edx; hFile
0x18003b5f3  mov     r8d, 800h; dwFlags
0x18003b5f9  lea     rcx, LibFileName; "ntdll.dll"
0x18003b600  mov     rdi, r9
0x18003b603  call    cs:__imp_LoadLibraryExW
0x18003b609  test    rax, rax
0x18003b60c  jnz     short loc_18003B615
0x18003b60e  mov     ebx, 80004005h
0x18003b613  jmp     short loc_18003B66B
0x18003b615  lea     rdx, aRtlgetpersiste; "RtlGetPersistedStateLocation"
0x18003b61c  mov     rcx, rax; hModule
0x18003b61f  call    cs:__imp_GetProcAddress
0x18003b625  mov     r10, rax
0x18003b628  test    rax, rax
0x18003b62b  jz      short loc_18003B60E
0x18003b62d  xor     r9d, r9d
0x18003b630  mov     [rsp+68h+var_38], 0
0x18003b639  cmp     [rsp+68h+arg_20], r9d
0x18003b641  lea     eax, [rsi+rsi]
0x18003b644  mov     [rsp+68h+var_40], eax
0x18003b648  mov     r8, rdi
0x18003b64b  setz    r9b
0x18003b64f  mov     [rsp+68h+var_48], rbp
0x18003b654  xor     edx, edx
0x18003b656  mov     rcx, rbx
0x18003b659  mov     rax, r10
0x18003b65c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b661  mov     ebx, eax
0x18003b663  or      ebx, 10000000h
0x18003b669  jge     short loc_18003B681
0x18003b66b  mov     rdx, rsi
0x18003b66e  mov     r8, rdi
0x18003b671  mov     rcx, rbp
0x18003b674  call    cs:__imp__o_wcscpy_s
0x18003b67a  xor     ecx, ecx
0x18003b67c  test    eax, eax
0x18003b67e  cmovz   ebx, ecx
0x18003b681  mov     eax, ebx
0x18003b683  add     rsp, 48h
0x18003b687  pop     rdi
0x18003b688  pop     rsi
0x18003b689  pop     rbp
0x18003b68a  pop     rbx
0x18003b68b  retn
```
