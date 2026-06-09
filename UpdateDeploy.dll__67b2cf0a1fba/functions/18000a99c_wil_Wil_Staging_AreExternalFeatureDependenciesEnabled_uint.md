# wil::Wil_Staging_AreExternalFeatureDependenciesEnabled(uint)

- ea: `0x18000a99c`
- end: `0x18000aaaf`
- name: `?Wil_Staging_AreExternalFeatureDependenciesEnabled@wil@@YA_NI@Z`
- size: `275`
- prototype: `bool __fastcall(wil *__hidden this, unsigned int)`
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000aab8`
- `0x18000d5d0`
- `0x18000d6f0`
- `0x18000da64`
- `0x180037978`
- `0x180044c84`
- `0x180051238`
- `0x180052dfc`

## callees

- `0x18000a99c`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18000a9c1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18000aa0f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18000a9c1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18000aa0f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000aa73`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000aa82`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000aa93`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000aa73`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000aa82`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000aa93`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a9e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000aa33`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000aa48`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a9e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000aa33`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000aa48`

## string_xrefs

- `0x18000a9ba`: `kernelbase.dll`
- `0x18000aa08`: `windowsudk.shellcommon.dll`

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
0x18000a99c  mov     [rsp+arg_8], rbx
0x18000a9a1  mov     [rsp+arg_10], rbp
0x18000a9a6  push    rsi
0x18000a9a7  push    rdi
0x18000a9a8  push    r14
0x18000a9aa  sub     rsp, 30h
0x18000a9ae  mov     esi, ecx
0x18000a9b0  mov     ebx, 800h
0x18000a9b5  mov     r8d, ebx; dwFlags
0x18000a9b8  xor     edx, edx; hFile
0x18000a9ba  lea     rcx, LibFileName; "kernelbase.dll"
0x18000a9c1  call    cs:__imp_LoadLibraryExA
0x18000a9c7  mov     rdi, rax
0x18000a9ca  mov     [rsp+48h+var_28], rax
0x18000a9cf  test    rax, rax
0x18000a9d2  setnz   r14b
0x18000a9d6  test    rax, rax
0x18000a9d9  jz      short loc_18000AA03
0x18000a9db  lea     rdx, aAreexternalfea; "AreExternalFeatureDependenciesEnabled"
0x18000a9e2  mov     rcx, rax; hModule
0x18000a9e5  call    cs:__imp_GetProcAddress
0x18000a9eb  test    rax, rax
0x18000a9ee  jz      short loc_18000AA03
0x18000a9f0  mov     ecx, esi
0x18000a9f2  call    _guard_dispatch_icall
0x18000a9f7  cmp     eax, 2
0x18000a9fa  setz    sil
0x18000a9fe  jmp     loc_18000AA8B
0x18000aa03  mov     r8d, ebx; dwFlags
0x18000aa06  xor     edx, edx; hFile
0x18000aa08  lea     rcx, aWindowsudkShel; "windowsudk.shellcommon.dll"
0x18000aa0f  call    cs:__imp_LoadLibraryExA
0x18000aa15  mov     rbx, rax
0x18000aa18  mov     [rsp+48h+var_20], rax
0x18000aa1d  test    rax, rax
0x18000aa20  setnz   bpl
0x18000aa24  test    rax, rax
0x18000aa27  jz      short loc_18000AA7B
0x18000aa29  lea     rdx, aAreexternalfea; "AreExternalFeatureDependenciesEnabled"
0x18000aa30  mov     rcx, rax; hModule
0x18000aa33  call    cs:__imp_GetProcAddress
0x18000aa39  test    rax, rax
0x18000aa3c  jnz     short loc_18000AA5D
0x18000aa3e  lea     rdx, aGetexternalfea; "GetExternalFeatureState"
0x18000aa45  mov     rcx, rbx; hModule
0x18000aa48  call    cs:__imp_GetProcAddress
0x18000aa4e  test    rax, rax
0x18000aa51  jnz     short loc_18000AA5D
0x18000aa53  test    bpl, bpl
0x18000aa56  jz      short loc_18000AA88
0x18000aa58  mov     rcx, rbx
0x18000aa5b  jmp     short loc_18000AA82
0x18000aa5d  mov     ecx, esi
0x18000aa5f  call    _guard_dispatch_icall
0x18000aa64  cmp     eax, 2
0x18000aa67  setz    sil
0x18000aa6b  test    bpl, bpl
0x18000aa6e  jz      short loc_18000AA8B
0x18000aa70  mov     rcx, rbx; hLibModule
0x18000aa73  call    cs:__imp_FreeLibrary
0x18000aa79  jmp     short loc_18000AA8B
0x18000aa7b  test    bpl, bpl
0x18000aa7e  jz      short loc_18000AA88
0x18000aa80  xor     ecx, ecx; hLibModule
0x18000aa82  call    cs:__imp_FreeLibrary
0x18000aa88  xor     sil, sil
0x18000aa8b  test    r14b, r14b
0x18000aa8e  jz      short loc_18000AA99
0x18000aa90  mov     rcx, rdi; hLibModule
0x18000aa93  call    cs:__imp_FreeLibrary
0x18000aa99  mov     al, sil
0x18000aa9c  mov     rbx, [rsp+48h+arg_8]
0x18000aaa1  mov     rbp, [rsp+48h+arg_10]
0x18000aaa6  add     rsp, 30h
0x18000aaaa  pop     r14
0x18000aaac  pop     rdi
0x18000aaad  pop     rsi
0x18000aaae  retn
```
