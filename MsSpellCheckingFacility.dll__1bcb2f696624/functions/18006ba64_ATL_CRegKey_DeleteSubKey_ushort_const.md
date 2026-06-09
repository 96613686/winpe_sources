# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x18006ba64`
- end: `0x18006bb19`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18006b53c`
- `0x180092e58`
- `0x180093290`

## callees

- `0x18006ba64`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18006ba89`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18006ba89`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006bab6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006bab6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006ba9e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006bacb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006ba9e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006bacb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bb07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bb07`

## string_xrefs

- `0x18006ba82`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18006ba94`: `RegDeleteKeyExW`
- `0x18006baaf`: `advapi32.dll`
- `0x18006bac1`: `RegDeleteKeyW`

## pseudocode

```c
DWORD __fastcall ATL::CRegKey::DeleteSubKey(ATL::CRegKey *this, const unsigned __int16 *a2)
{
  HMODULE ModuleHandleW; // rax
  HMODULE Library; // rax
  __int64 (__fastcall *v6)(_QWORD, const unsigned __int16 *, _QWORD, _QWORD); // rax
  __int64 (__fastcall *v8)(_QWORD, const unsigned __int16 *); // rax

  if ( *(_OWORD *)((char *)this + 8) == 0 )
  {
    ModuleHandleW = GetModuleHandleW(L"API-MS-Win-Core-LocalRegistry-L1-1-0.dll");
    if ( ModuleHandleW )
    {
      *((_QWORD *)this + 1) = GetProcAddress(ModuleHandleW, "RegDeleteKeyExW");
    }
    else
    {
      Library = LoadLibraryExW(L"advapi32.dll", 0, 0);
      if ( Library )
        *((_QWORD *)this + 2) = GetProcAddress(Library, "RegDeleteKeyW");
    }
  }
  v6 = (__int64 (__fastcall *)(_QWORD, const unsigned __int16 *, _QWORD, _QWORD))*((_QWORD *)this + 1);
  if ( v6 )
    return v6(*(_QWORD *)this, a2, 0, 0);
  v8 = (__int64 (__fastcall *)(_QWORD, const unsigned __int16 *))*((_QWORD *)this + 2);
  if ( v8 )
    return v8(*(_QWORD *)this, a2);
  else
    return GetLastError();
}

```

## disassembly

```asm
0x18006ba64  mov     [rsp+arg_0], rbx
0x18006ba69  push    rdi
0x18006ba6a  sub     rsp, 30h
0x18006ba6e  mov     rdi, rdx
0x18006ba71  mov     rbx, rcx
0x18006ba74  cmp     qword ptr [rcx+8], 0
0x18006ba79  jnz     short loc_18006BAD5
0x18006ba7b  cmp     qword ptr [rcx+10h], 0
0x18006ba80  jnz     short loc_18006BAD5
0x18006ba82  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18006ba89  call    cs:__imp_GetModuleHandleW
0x18006ba8f  test    rax, rax
0x18006ba92  jz      short loc_18006BAAA
0x18006ba94  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x18006ba9b  mov     rcx, rax; hModule
0x18006ba9e  call    cs:__imp_GetProcAddress
0x18006baa4  mov     [rbx+8], rax
0x18006baa8  jmp     short loc_18006BAD5
0x18006baaa  xor     r8d, r8d; dwFlags
0x18006baad  xor     edx, edx; hFile
0x18006baaf  lea     rcx, LibFileName; "advapi32.dll"
0x18006bab6  call    cs:__imp_LoadLibraryExW
0x18006babc  test    rax, rax
0x18006babf  jz      short loc_18006BAD5
0x18006bac1  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x18006bac8  mov     rcx, rax; hModule
0x18006bacb  call    cs:__imp_GetProcAddress
0x18006bad1  mov     [rbx+10h], rax
0x18006bad5  mov     rax, [rbx+8]
0x18006bad9  test    rax, rax
0x18006badc  jz      short loc_18006BAF1
0x18006bade  xor     r9d, r9d
0x18006bae1  xor     r8d, r8d
0x18006bae4  mov     rdx, rdi
0x18006bae7  mov     rcx, [rbx]
0x18006baea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006baef  jmp     short loc_18006BB0E
0x18006baf1  mov     rax, [rbx+10h]
0x18006baf5  test    rax, rax
0x18006baf8  jz      short loc_18006BB07
0x18006bafa  mov     rdx, rdi
0x18006bafd  mov     rcx, [rbx]
0x18006bb00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bb05  jmp     short loc_18006BB0E
0x18006bb07  call    cs:__imp_GetLastError
0x18006bb0d  nop
0x18006bb0e  mov     rbx, [rsp+38h+arg_0]
0x18006bb13  add     rsp, 30h
0x18006bb17  pop     rdi
0x18006bb18  retn
```
