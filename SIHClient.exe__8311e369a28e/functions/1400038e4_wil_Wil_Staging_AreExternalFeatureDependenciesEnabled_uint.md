# wil::Wil_Staging_AreExternalFeatureDependenciesEnabled(uint)

- ea: `0x1400038e4`
- end: `0x1400039f7`
- name: `?Wil_Staging_AreExternalFeatureDependenciesEnabled@wil@@YA_NI@Z`
- size: `275`
- prototype: `bool __fastcall(wil *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140006c38`
- `0x140010d40`

## callees

- `0x1400038e4`
- `0x14004cd00`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400039bb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400039ca`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400039db`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400039bb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400039ca`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400039db`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x140003909`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x140003957`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x140003909`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x140003957`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000392d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000397b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140003990`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000392d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000397b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140003990`

## string_xrefs

- `0x140003950`: `windowsudk.shellcommon.dll`
- `0x140003902`: `kernelbase.dll`

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
0x1400038e4  mov     [rsp+arg_8], rbx
0x1400038e9  mov     [rsp+arg_10], rbp
0x1400038ee  push    rsi
0x1400038ef  push    rdi
0x1400038f0  push    r14
0x1400038f2  sub     rsp, 30h
0x1400038f6  mov     esi, ecx
0x1400038f8  mov     ebx, 800h
0x1400038fd  mov     r8d, ebx; dwFlags
0x140003900  xor     edx, edx; hFile
0x140003902  lea     rcx, LibFileName; "kernelbase.dll"
0x140003909  call    cs:__imp_LoadLibraryExA
0x14000390f  mov     rdi, rax
0x140003912  mov     [rsp+48h+var_28], rax
0x140003917  test    rax, rax
0x14000391a  setnz   r14b
0x14000391e  test    rax, rax
0x140003921  jz      short loc_14000394B
0x140003923  lea     rdx, ProcName; "AreExternalFeatureDependenciesEnabled"
0x14000392a  mov     rcx, rax; hModule
0x14000392d  call    cs:__imp_GetProcAddress
0x140003933  test    rax, rax
0x140003936  jz      short loc_14000394B
0x140003938  mov     ecx, esi
0x14000393a  call    _guard_dispatch_icall
0x14000393f  cmp     eax, 2
0x140003942  setz    sil
0x140003946  jmp     loc_1400039D3
0x14000394b  mov     r8d, ebx; dwFlags
0x14000394e  xor     edx, edx; hFile
0x140003950  lea     rcx, aWindowsudkShel; "windowsudk.shellcommon.dll"
0x140003957  call    cs:__imp_LoadLibraryExA
0x14000395d  mov     rbx, rax
0x140003960  mov     [rsp+48h+var_20], rax
0x140003965  test    rax, rax
0x140003968  setnz   bpl
0x14000396c  test    rax, rax
0x14000396f  jz      short loc_1400039C3
0x140003971  lea     rdx, ProcName; "AreExternalFeatureDependenciesEnabled"
0x140003978  mov     rcx, rax; hModule
0x14000397b  call    cs:__imp_GetProcAddress
0x140003981  test    rax, rax
0x140003984  jnz     short loc_1400039A5
0x140003986  lea     rdx, aGetexternalfea; "GetExternalFeatureState"
0x14000398d  mov     rcx, rbx; hModule
0x140003990  call    cs:__imp_GetProcAddress
0x140003996  test    rax, rax
0x140003999  jnz     short loc_1400039A5
0x14000399b  test    bpl, bpl
0x14000399e  jz      short loc_1400039D0
0x1400039a0  mov     rcx, rbx
0x1400039a3  jmp     short loc_1400039CA
0x1400039a5  mov     ecx, esi
0x1400039a7  call    _guard_dispatch_icall
0x1400039ac  cmp     eax, 2
0x1400039af  setz    sil
0x1400039b3  test    bpl, bpl
0x1400039b6  jz      short loc_1400039D3
0x1400039b8  mov     rcx, rbx; hLibModule
0x1400039bb  call    cs:__imp_FreeLibrary
0x1400039c1  jmp     short loc_1400039D3
0x1400039c3  test    bpl, bpl
0x1400039c6  jz      short loc_1400039D0
0x1400039c8  xor     ecx, ecx; hLibModule
0x1400039ca  call    cs:__imp_FreeLibrary
0x1400039d0  xor     sil, sil
0x1400039d3  test    r14b, r14b
0x1400039d6  jz      short loc_1400039E1
0x1400039d8  mov     rcx, rdi; hLibModule
0x1400039db  call    cs:__imp_FreeLibrary
0x1400039e1  mov     al, sil
0x1400039e4  mov     rbx, [rsp+48h+arg_8]
0x1400039e9  mov     rbp, [rsp+48h+arg_10]
0x1400039ee  add     rsp, 30h
0x1400039f2  pop     r14
0x1400039f4  pop     rdi
0x1400039f5  pop     rsi
0x1400039f6  retn
```
