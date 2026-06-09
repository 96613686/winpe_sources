# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180130fc0`
- end: `0x180131075`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1801321f8`
- `0x180132614`

## callees

- `0x180130fc0`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180131063`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180131063`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180131012`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180131012`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180130fe5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180130fe5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180130ffa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180131027`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180130ffa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180131027`

## string_xrefs

- `0x180130fde`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180130ff0`: `RegDeleteKeyExW`
- `0x18013100b`: `advapi32.dll`
- `0x18013101d`: `RegDeleteKeyW`

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
0x180130fc0  mov     [rsp+arg_0], rbx
0x180130fc5  push    rdi
0x180130fc6  sub     rsp, 30h
0x180130fca  mov     rdi, rdx
0x180130fcd  mov     rbx, rcx
0x180130fd0  cmp     qword ptr [rcx+8], 0
0x180130fd5  jnz     short loc_180131031
0x180130fd7  cmp     qword ptr [rcx+10h], 0
0x180130fdc  jnz     short loc_180131031
0x180130fde  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180130fe5  call    cs:__imp_GetModuleHandleW
0x180130feb  test    rax, rax
0x180130fee  jz      short loc_180131006
0x180130ff0  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x180130ff7  mov     rcx, rax; hModule
0x180130ffa  call    cs:__imp_GetProcAddress
0x180131000  mov     [rbx+8], rax
0x180131004  jmp     short loc_180131031
0x180131006  xor     r8d, r8d; dwFlags
0x180131009  xor     edx, edx; hFile
0x18013100b  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x180131012  call    cs:__imp_LoadLibraryExW
0x180131018  test    rax, rax
0x18013101b  jz      short loc_180131031
0x18013101d  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180131024  mov     rcx, rax; hModule
0x180131027  call    cs:__imp_GetProcAddress
0x18013102d  mov     [rbx+10h], rax
0x180131031  mov     rax, [rbx+8]
0x180131035  test    rax, rax
0x180131038  jz      short loc_18013104D
0x18013103a  xor     r9d, r9d
0x18013103d  xor     r8d, r8d
0x180131040  mov     rdx, rdi
0x180131043  mov     rcx, [rbx]
0x180131046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013104b  jmp     short loc_18013106A
0x18013104d  mov     rax, [rbx+10h]
0x180131051  test    rax, rax
0x180131054  jz      short loc_180131063
0x180131056  mov     rdx, rdi
0x180131059  mov     rcx, [rbx]
0x18013105c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180131061  jmp     short loc_18013106A
0x180131063  call    cs:__imp_GetLastError
0x180131069  nop
0x18013106a  mov     rbx, [rsp+38h+arg_0]
0x18013106f  add     rsp, 30h
0x180131073  pop     rdi
0x180131074  retn
```
