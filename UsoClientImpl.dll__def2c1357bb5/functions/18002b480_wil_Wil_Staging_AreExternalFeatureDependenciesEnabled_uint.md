# wil::Wil_Staging_AreExternalFeatureDependenciesEnabled(uint)

- ea: `0x18002b480`
- end: `0x18002b593`
- name: `?Wil_Staging_AreExternalFeatureDependenciesEnabled@wil@@YA_NI@Z`
- size: `275`
- prototype: `bool __fastcall(wil *__hidden this, unsigned int)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180028f10`
- `0x1800291f8`
- `0x1800294e0`
- `0x18002b59c`
- `0x180047094`
- `0x1800473bc`

## callees

- `0x18002b480`
- `0x18005c5e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002b557`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002b566`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002b577`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002b557`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002b566`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002b577`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b4c9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b517`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b52c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b4c9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b517`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b52c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18002b4a5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18002b4f3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18002b4a5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18002b4f3`

## string_xrefs

- `0x18002b49e`: `kernelbase.dll`
- `0x18002b4ec`: `windowsudk.shellcommon.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall wil::Wil_Staging_AreExternalFeatureDependenciesEnabled(wil *this)
{
  unsigned int v1; // esi
  HMODULE Library; // rax
  HMODULE v3; // rdi
  bool v4; // r14
  FARPROC ProcAddress; // rax
  bool v6; // si
  HMODULE v7; // rax
  HMODULE v8; // rbx
  bool v9; // bp
  FARPROC v10; // rax

  v1 = (unsigned int)this;
  Library = LoadLibraryExA("kernelbase.dll", 0, 0x800u);
  v3 = Library;
  v4 = Library != 0;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "AreExternalFeatureDependenciesEnabled");
    if ( ProcAddress )
    {
      v6 = ((unsigned int (__fastcall *)(_QWORD))ProcAddress)(v1) == 2;
      goto LABEL_12;
    }
  }
  v7 = LoadLibraryExA("windowsudk.shellcommon.dll", 0, 0x800u);
  v8 = v7;
  v9 = v7 != 0;
  if ( !v7 )
    goto LABEL_11;
  v10 = GetProcAddress(v7, "AreExternalFeatureDependenciesEnabled");
  if ( !v10 )
  {
    v10 = GetProcAddress(v8, "GetExternalFeatureState");
    if ( !v10 )
    {
      if ( v9 )
        FreeLibrary(v8);
LABEL_11:
      v6 = 0;
      goto LABEL_12;
    }
  }
  v6 = ((unsigned int (__fastcall *)(_QWORD))v10)(v1) == 2;
  if ( v9 )
    FreeLibrary(v8);
LABEL_12:
  if ( v4 )
    FreeLibrary(v3);
  return v6;
}

```

## disassembly

```asm
0x18002b480  mov     [rsp+arg_8], rbx
0x18002b485  mov     [rsp+arg_10], rbp
0x18002b48a  push    rsi
0x18002b48b  push    rdi
0x18002b48c  push    r14
0x18002b48e  sub     rsp, 30h
0x18002b492  mov     esi, ecx
0x18002b494  mov     ebx, 800h
0x18002b499  mov     r8d, ebx; dwFlags
0x18002b49c  xor     edx, edx; hFile
0x18002b49e  lea     rcx, aKernelbaseDll_0; "kernelbase.dll"
0x18002b4a5  call    cs:__imp_LoadLibraryExA
0x18002b4ab  mov     rdi, rax
0x18002b4ae  mov     [rsp+48h+var_28], rax
0x18002b4b3  test    rax, rax
0x18002b4b6  setnz   r14b
0x18002b4ba  test    rax, rax
0x18002b4bd  jz      short loc_18002B4E7
0x18002b4bf  lea     rdx, aAreexternalfea; "AreExternalFeatureDependenciesEnabled"
0x18002b4c6  mov     rcx, rax; hModule
0x18002b4c9  call    cs:__imp_GetProcAddress
0x18002b4cf  test    rax, rax
0x18002b4d2  jz      short loc_18002B4E7
0x18002b4d4  mov     ecx, esi
0x18002b4d6  call    _guard_dispatch_icall
0x18002b4db  cmp     eax, 2
0x18002b4de  setz    sil
0x18002b4e2  jmp     loc_18002B56F
0x18002b4e7  mov     r8d, ebx; dwFlags
0x18002b4ea  xor     edx, edx; hFile
0x18002b4ec  lea     rcx, aWindowsudkShel; "windowsudk.shellcommon.dll"
0x18002b4f3  call    cs:__imp_LoadLibraryExA
0x18002b4f9  mov     rbx, rax
0x18002b4fc  mov     [rsp+48h+var_20], rax
0x18002b501  test    rax, rax
0x18002b504  setnz   bpl
0x18002b508  test    rax, rax
0x18002b50b  jz      short loc_18002B55F
0x18002b50d  lea     rdx, aAreexternalfea; "AreExternalFeatureDependenciesEnabled"
0x18002b514  mov     rcx, rax; hModule
0x18002b517  call    cs:__imp_GetProcAddress
0x18002b51d  test    rax, rax
0x18002b520  jnz     short loc_18002B541
0x18002b522  lea     rdx, aGetexternalfea; "GetExternalFeatureState"
0x18002b529  mov     rcx, rbx; hModule
0x18002b52c  call    cs:__imp_GetProcAddress
0x18002b532  test    rax, rax
0x18002b535  jnz     short loc_18002B541
0x18002b537  test    bpl, bpl
0x18002b53a  jz      short loc_18002B56C
0x18002b53c  mov     rcx, rbx
0x18002b53f  jmp     short loc_18002B566
0x18002b541  mov     ecx, esi
0x18002b543  call    _guard_dispatch_icall
0x18002b548  cmp     eax, 2
0x18002b54b  setz    sil
0x18002b54f  test    bpl, bpl
0x18002b552  jz      short loc_18002B56F
0x18002b554  mov     rcx, rbx; hLibModule
0x18002b557  call    cs:__imp_FreeLibrary
0x18002b55d  jmp     short loc_18002B56F
0x18002b55f  test    bpl, bpl
0x18002b562  jz      short loc_18002B56C
0x18002b564  xor     ecx, ecx; hLibModule
0x18002b566  call    cs:__imp_FreeLibrary
0x18002b56c  xor     sil, sil
0x18002b56f  test    r14b, r14b
0x18002b572  jz      short loc_18002B57D
0x18002b574  mov     rcx, rdi; hLibModule
0x18002b577  call    cs:__imp_FreeLibrary
0x18002b57d  mov     al, sil
0x18002b580  mov     rbx, [rsp+48h+arg_8]
0x18002b585  mov     rbp, [rsp+48h+arg_10]
0x18002b58a  add     rsp, 30h
0x18002b58e  pop     r14
0x18002b590  pop     rdi
0x18002b591  pop     rsi
0x18002b592  retn
```
