# AmiUtilityGetPersistedLocation

- ea: `0x14001ac30`
- end: `0x14001acdc`
- name: `AmiUtilityGetPersistedLocation`
- size: `172`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int64, int)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140018f70`
- `0x140019258`
- `0x140019930`
- `0x140019fa0`
- `0x14001a914`

## callees

- `0x14001ac30`
- `0x1400a8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14001acc4`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14001acc4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001ac6f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001ac6f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14001ac53`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14001ac53`

## string_xrefs

- `0x14001ac49`: `ntdll.dll`

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
0x14001ac30  push    rbx
0x14001ac32  push    rbp
0x14001ac33  push    rsi
0x14001ac34  push    rdi
0x14001ac35  sub     rsp, 48h
0x14001ac39  mov     rbx, r8
0x14001ac3c  mov     esi, edx
0x14001ac3e  mov     rbp, rcx
0x14001ac41  xor     edx, edx; hFile
0x14001ac43  mov     r8d, 800h; dwFlags
0x14001ac49  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x14001ac50  mov     rdi, r9
0x14001ac53  call    cs:__imp_LoadLibraryExW
0x14001ac59  test    rax, rax
0x14001ac5c  jnz     short loc_14001AC65
0x14001ac5e  mov     ebx, 80004005h
0x14001ac63  jmp     short loc_14001ACBB
0x14001ac65  lea     rdx, aRtlgetpersiste; "RtlGetPersistedStateLocation"
0x14001ac6c  mov     rcx, rax; hModule
0x14001ac6f  call    cs:__imp_GetProcAddress
0x14001ac75  mov     r10, rax
0x14001ac78  test    rax, rax
0x14001ac7b  jz      short loc_14001AC5E
0x14001ac7d  xor     r9d, r9d
0x14001ac80  mov     [rsp+68h+var_38], 0
0x14001ac89  cmp     [rsp+68h+arg_20], r9d
0x14001ac91  lea     eax, [rsi+rsi]
0x14001ac94  mov     [rsp+68h+var_40], eax
0x14001ac98  mov     r8, rdi
0x14001ac9b  setz    r9b
0x14001ac9f  mov     [rsp+68h+var_48], rbp
0x14001aca4  xor     edx, edx
0x14001aca6  mov     rcx, rbx
0x14001aca9  mov     rax, r10
0x14001acac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001acb1  mov     ebx, eax
0x14001acb3  or      ebx, 10000000h
0x14001acb9  jge     short loc_14001ACD1
0x14001acbb  mov     rdx, rsi
0x14001acbe  mov     r8, rdi
0x14001acc1  mov     rcx, rbp
0x14001acc4  call    cs:__imp__o_wcscpy_s
0x14001acca  xor     ecx, ecx
0x14001accc  test    eax, eax
0x14001acce  cmovz   ebx, ecx
0x14001acd1  mov     eax, ebx
0x14001acd3  add     rsp, 48h
0x14001acd7  pop     rdi
0x14001acd8  pop     rsi
0x14001acd9  pop     rbp
0x14001acda  pop     rbx
0x14001acdb  retn
```
