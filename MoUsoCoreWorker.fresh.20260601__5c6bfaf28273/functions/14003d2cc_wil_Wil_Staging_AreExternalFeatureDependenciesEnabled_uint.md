# wil::Wil_Staging_AreExternalFeatureDependenciesEnabled(uint)

- ea: `0x14003d2cc`
- end: `0x14003d3df`
- name: `?Wil_Staging_AreExternalFeatureDependenciesEnabled@wil@@YA_NI@Z`
- size: `275`
- prototype: `bool __fastcall(wil *__hidden this, unsigned int)`
- caller_count: `15`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14003bae4`
- `0x14003be0c`
- `0x14003c0f4`
- `0x14003c640`
- `0x14003cbe0`
- `0x14003d3e8`
- `0x1400c5ca8`
- `0x1400c761c`
- `0x1400c7904`
- `0x1400c7bec`
- `0x1400c7ed4`
- `0x140103e30`
- `0x140115d90`
- `0x1402a06e8`
- `0x1402db210`

## callees

- `0x14003d2cc`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x14003d2f1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x14003d33f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x14003d2f1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x14003d33f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14003d3a3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14003d3b2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14003d3c3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14003d3a3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14003d3b2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14003d3c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003d315`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003d363`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003d378`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003d315`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003d363`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003d378`

## string_xrefs

- `0x14003d2ea`: `kernelbase.dll`
- `0x14003d338`: `windowsudk.shellcommon.dll`

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
0x14003d2cc  mov     [rsp+arg_8], rbx
0x14003d2d1  mov     [rsp+arg_10], rbp
0x14003d2d6  push    rsi
0x14003d2d7  push    rdi
0x14003d2d8  push    r14
0x14003d2da  sub     rsp, 30h
0x14003d2de  mov     esi, ecx
0x14003d2e0  mov     ebx, 800h
0x14003d2e5  mov     r8d, ebx; dwFlags
0x14003d2e8  xor     edx, edx; hFile
0x14003d2ea  lea     rcx, LibFileName; "kernelbase.dll"
0x14003d2f1  call    cs:__imp_LoadLibraryExA
0x14003d2f7  mov     rdi, rax
0x14003d2fa  mov     [rsp+48h+var_28], rax
0x14003d2ff  test    rax, rax
0x14003d302  setnz   r14b
0x14003d306  test    rax, rax
0x14003d309  jz      short loc_14003D333
0x14003d30b  lea     rdx, aAreexternalfea; "AreExternalFeatureDependenciesEnabled"
0x14003d312  mov     rcx, rax; hModule
0x14003d315  call    cs:__imp_GetProcAddress
0x14003d31b  test    rax, rax
0x14003d31e  jz      short loc_14003D333
0x14003d320  mov     ecx, esi
0x14003d322  call    _guard_dispatch_icall
0x14003d327  cmp     eax, 2
0x14003d32a  setz    sil
0x14003d32e  jmp     loc_14003D3BB
0x14003d333  mov     r8d, ebx; dwFlags
0x14003d336  xor     edx, edx; hFile
0x14003d338  lea     rcx, aWindowsudkShel; "windowsudk.shellcommon.dll"
0x14003d33f  call    cs:__imp_LoadLibraryExA
0x14003d345  mov     rbx, rax
0x14003d348  mov     [rsp+48h+var_20], rax
0x14003d34d  test    rax, rax
0x14003d350  setnz   bpl
0x14003d354  test    rax, rax
0x14003d357  jz      short loc_14003D3AB
0x14003d359  lea     rdx, aAreexternalfea; "AreExternalFeatureDependenciesEnabled"
0x14003d360  mov     rcx, rax; hModule
0x14003d363  call    cs:__imp_GetProcAddress
0x14003d369  test    rax, rax
0x14003d36c  jnz     short loc_14003D38D
0x14003d36e  lea     rdx, aGetexternalfea; "GetExternalFeatureState"
0x14003d375  mov     rcx, rbx; hModule
0x14003d378  call    cs:__imp_GetProcAddress
0x14003d37e  test    rax, rax
0x14003d381  jnz     short loc_14003D38D
0x14003d383  test    bpl, bpl
0x14003d386  jz      short loc_14003D3B8
0x14003d388  mov     rcx, rbx
0x14003d38b  jmp     short loc_14003D3B2
0x14003d38d  mov     ecx, esi
0x14003d38f  call    _guard_dispatch_icall
0x14003d394  cmp     eax, 2
0x14003d397  setz    sil
0x14003d39b  test    bpl, bpl
0x14003d39e  jz      short loc_14003D3BB
0x14003d3a0  mov     rcx, rbx; hLibModule
0x14003d3a3  call    cs:__imp_FreeLibrary
0x14003d3a9  jmp     short loc_14003D3BB
0x14003d3ab  test    bpl, bpl
0x14003d3ae  jz      short loc_14003D3B8
0x14003d3b0  xor     ecx, ecx; hLibModule
0x14003d3b2  call    cs:__imp_FreeLibrary
0x14003d3b8  xor     sil, sil
0x14003d3bb  test    r14b, r14b
0x14003d3be  jz      short loc_14003D3C9
0x14003d3c0  mov     rcx, rdi; hLibModule
0x14003d3c3  call    cs:__imp_FreeLibrary
0x14003d3c9  mov     al, sil
0x14003d3cc  mov     rbx, [rsp+48h+arg_8]
0x14003d3d1  mov     rbp, [rsp+48h+arg_10]
0x14003d3d6  add     rsp, 30h
0x14003d3da  pop     r14
0x14003d3dc  pop     rdi
0x14003d3dd  pop     rsi
0x14003d3de  retn
```
