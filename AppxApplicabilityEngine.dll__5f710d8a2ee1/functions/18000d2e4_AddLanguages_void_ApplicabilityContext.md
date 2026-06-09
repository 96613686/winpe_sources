# AddLanguages(void *,ApplicabilityContext *)

- ea: `0x18000d2e4`
- end: `0x18000d504`
- name: `?AddLanguages@@YAXPEAXPEAVApplicabilityContext@@@Z`
- size: `544`
- prototype: `void __fastcall(void *, struct ApplicabilityContext *)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800098c0`
- `0x180016c10`

## callees

- `0x18000a1ec`
- `0x18000ae80`
- `0x18000d2e4`
- `0x18000d6f4`
- `0x18000db80`
- `0x18000fb54`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000d343`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000d343`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18000d323`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18000d323`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18000d4da`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18000d4da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000d42d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000d42d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d355`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d3c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d4e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d355`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d3c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d4e5`

## string_xrefs

- `0x18000d31c`: `bcp47langs.dll`

## pseudocode

```c
void __fastcall AddLanguages(void *a1, struct ApplicabilityContext *a2)
{
  HMODULE Library; // rax
  HMODULE v5; // rdi
  FARPROC ProcAddress; // rbx
  int v7; // edx
  int v8; // ecx
  int v9; // ebx
  int v10; // edx
  int v11; // ecx
  int AppropriateUserPreferredAndDisplayLanguagesForUser; // ebx
  PCWSTR StringRawBuffer; // rax
  _QWORD *v14; // rbx
  _QWORD *v15; // rsi
  __int64 (__fastcall ***v16)(_QWORD, _QWORD *); // rax
  _QWORD *v17; // rdx
  int v18; // edx
  int v19; // ecx
  int v20; // r15d
  int v21; // [rsp+20h] [rbp-40h]
  _QWORD v22[5]; // [rsp+38h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  HSTRING string; // [rsp+A0h] [rbp+40h] BYREF
  HMODULE v25; // [rsp+A8h] [rbp+48h]

  string = 0;
  Library = LoadLibraryExW(L"bcp47langs.dll", 0, 0x800u);
  v5 = Library;
  v25 = Library;
  if ( Library && (ProcAddress = GetProcAddress(Library, "GetAppropriateUserPreferredAndDisplayLanguagesForUser")) != 0 )
  {
    WindowsDeleteString(string);
    string = 0;
    v9 = ((__int64 (__fastcall *)(void *, __int64, HSTRING *))ProcAddress)(a1, 59, &string);
    if ( v9 == -2147023266 && (Microsoft_Windows_ApplicabilityEngineEnableBits & 2) != 0 )
      McTemplateU0zqd_EventWriteTransfer(
        v8,
        v7,
        (unsigned int)L"onecoreuap\\base\\mrt\\applicability\\src\\formatter.cpp",
        27,
        94);
    if ( v9 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1B,
        (unsigned int)"onecoreuap\\base\\mrt\\applicability\\src\\formatter.cpp",
        (const char *)(unsigned int)v9,
        v21);
  }
  else
  {
    WindowsDeleteString(string);
    string = 0;
    AppropriateUserPreferredAndDisplayLanguagesForUser = GetAppropriateUserPreferredAndDisplayLanguagesForUser(a1);
    if ( AppropriateUserPreferredAndDisplayLanguagesForUser == -2147023266
      && (Microsoft_Windows_ApplicabilityEngineEnableBits & 2) != 0 )
    {
      McTemplateU0zqd_EventWriteTransfer(
        v11,
        v10,
        (unsigned int)L"onecoreuap\\base\\mrt\\applicability\\src\\formatter.cpp",
        33,
        94);
    }
    if ( AppropriateUserPreferredAndDisplayLanguagesForUser < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x21,
        (unsigned int)"onecoreuap\\base\\mrt\\applicability\\src\\formatter.cpp",
        (const char *)(unsigned int)AppropriateUserPreferredAndDisplayLanguagesForUser,
        v21);
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  WstringContainerFromDelimitedString<std::vector<std::wstring>>(v22, StringRawBuffer);
  v14 = (_QWORD *)v22[0];
  v15 = (_QWORD *)v22[1];
  while ( v14 != v15 )
  {
    v16 = (__int64 (__fastcall ***)(_QWORD, _QWORD *))(**(__int64 (__fastcall ***)(struct ApplicabilityContext *))a2)(a2);
    if ( v14[3] < 8u )
      v17 = v14;
    else
      v17 = (_QWORD *)*v14;
    v20 = (**v16)(v16, v17);
    if ( v20 == -2147023266 && (Microsoft_Windows_ApplicabilityEngineEnableBits & 2) != 0 )
      McTemplateU0zqd_EventWriteTransfer(
        v19,
        v18,
        (unsigned int)L"onecoreuap\\base\\mrt\\applicability\\src\\formatter.cpp",
        39,
        94);
    if ( v20 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x27,
        (unsigned int)"onecoreuap\\base\\mrt\\applicability\\src\\formatter.cpp",
        (const char *)(unsigned int)v20,
        v21);
    v14 += 5;
  }
  std::vector<std::wstring>::_Tidy(v22);
  if ( v5 )
    FreeLibrary(v5);
  WindowsDeleteString(string);
}

```

## disassembly

```asm
0x18000d2e4  mov     rax, rsp
0x18000d2e7  push    rbp
0x18000d2e8  push    rdi
0x18000d2e9  push    r12
0x18000d2eb  push    r14
0x18000d2ed  push    r15
0x18000d2ef  mov     rbp, rsp
0x18000d2f2  sub     rsp, 60h
0x18000d2f6  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFEh
0x18000d2fe  mov     [rax+8], rbx
0x18000d302  mov     [rax+10h], rsi
0x18000d306  mov     r12, rdx
0x18000d309  mov     rsi, rcx
0x18000d30c  mov     [rbp+string], 0
0x18000d314  xor     edx, edx; hFile
0x18000d316  mov     r8d, 800h; dwFlags
0x18000d31c  lea     rcx, LibFileName; "bcp47langs.dll"
0x18000d323  call    cs:__imp_LoadLibraryExW
0x18000d329  mov     rdi, rax
0x18000d32c  mov     [rbp+arg_18], rax
0x18000d330  test    rax, rax
0x18000d333  jz      loc_18000D3C0
0x18000d339  lea     rdx, ProcName; "GetAppropriateUserPreferredAndDisplayLa"...
0x18000d340  mov     rcx, rax; hModule
0x18000d343  call    cs:__imp_GetProcAddress
0x18000d349  mov     rbx, rax
0x18000d34c  test    rax, rax
0x18000d34f  jz      short loc_18000D3C0
0x18000d351  mov     rcx, [rbp+string]; string
0x18000d355  call    cs:__imp_WindowsDeleteString
0x18000d35b  mov     [rbp+string], 0
0x18000d363  mov     edx, 3Bh ; ';'
0x18000d368  lea     r8, [rbp+string]
0x18000d36c  mov     rcx, rsi
0x18000d36f  mov     rax, rbx
0x18000d372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d377  mov     ebx, eax
0x18000d379  mov     esi, 1Bh
0x18000d37e  mov     r14d, 8007065Eh
0x18000d384  cmp     eax, r14d
0x18000d387  jnz     short loc_18000D3A6
0x18000d389  test    cs:Microsoft_Windows_ApplicabilityEngineEnableBits, 2
0x18000d390  jz      short loc_18000D3A6
0x18000d392  mov     [rsp+60h+var_40], r14d; int
0x18000d397  mov     r9d, esi
0x18000d39a  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\mrt\\applicability\\s"...
0x18000d3a1  call    McTemplateU0zqd_EventWriteTransfer
0x18000d3a6  mov     rcx, [rbp+28h]; this
0x18000d3aa  test    ebx, ebx
0x18000d3ac  jns     short loc_18000D427
0x18000d3ae  mov     r9d, ebx; char *
0x18000d3b1  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\mrt\\applicability\\s"...
0x18000d3b8  mov     edx, esi; void *
0x18000d3ba  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000d3c0  mov     rcx, [rbp+string]; string
0x18000d3c4  call    cs:__imp_WindowsDeleteString
0x18000d3ca  mov     [rbp+string], 0
0x18000d3d2  lea     r8, [rbp+string]
0x18000d3d6  mov     rcx, rsi; void *
0x18000d3d9  call    GetAppropriateUserPreferredAndDisplayLanguagesForUser
0x18000d3de  mov     ebx, eax
0x18000d3e0  mov     esi, 21h ; '!'
0x18000d3e5  mov     r14d, 8007065Eh
0x18000d3eb  cmp     eax, r14d
0x18000d3ee  jnz     short loc_18000D40D
0x18000d3f0  test    cs:Microsoft_Windows_ApplicabilityEngineEnableBits, 2
0x18000d3f7  jz      short loc_18000D40D
0x18000d3f9  mov     [rsp+60h+var_40], r14d; int
0x18000d3fe  mov     r9d, esi
0x18000d401  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\mrt\\applicability\\s"...
0x18000d408  call    McTemplateU0zqd_EventWriteTransfer
0x18000d40d  mov     rcx, [rbp+28h]; this
0x18000d411  test    ebx, ebx
0x18000d413  jns     short loc_18000D427
0x18000d415  mov     r9d, ebx; char *
0x18000d418  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\mrt\\applicability\\s"...
0x18000d41f  mov     edx, esi; void *
0x18000d421  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000d427  xor     edx, edx; length
0x18000d429  mov     rcx, [rbp+string]; string
0x18000d42d  call    cs:__imp_WindowsGetStringRawBuffer
0x18000d433  mov     rdx, rax
0x18000d436  lea     rcx, [rbp+var_28]
0x18000d43a  call    ??$WstringContainerFromDelimitedString@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEBGG@Z; WstringContainerFromDelimitedString<std::vector<std::wstring>>(ushort const *,ushort)
0x18000d43f  nop
0x18000d440  mov     rbx, [rbp+var_28]
0x18000d444  mov     rsi, [rbp+var_20]
0x18000d448  cmp     rbx, rsi
0x18000d44b  jz      short loc_18000D4C8
0x18000d44d  mov     rax, [r12]
0x18000d451  mov     rcx, r12
0x18000d454  mov     rax, [rax]
0x18000d457  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d45c  mov     rcx, [rax]
0x18000d45f  mov     r8, [rcx]
0x18000d462  cmp     qword ptr [rbx+18h], 8
0x18000d467  jb      short loc_18000D46E
0x18000d469  mov     rdx, [rbx]
0x18000d46c  jmp     short loc_18000D471
0x18000d46e  mov     rdx, rbx
0x18000d471  mov     rcx, rax
0x18000d474  mov     rax, r8
0x18000d477  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d47c  mov     r15d, eax
0x18000d47f  cmp     eax, r14d
0x18000d482  jnz     short loc_18000D4A4
0x18000d484  test    cs:Microsoft_Windows_ApplicabilityEngineEnableBits, 2
0x18000d48b  jz      short loc_18000D4A4
0x18000d48d  mov     [rsp+60h+var_40], r14d; int
0x18000d492  mov     r9d, 27h ; '''
0x18000d498  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\mrt\\applicability\\s"...
0x18000d49f  call    McTemplateU0zqd_EventWriteTransfer
0x18000d4a4  mov     rcx, [rbp+28h]; this
0x18000d4a8  test    r15d, r15d
0x18000d4ab  js      short loc_18000D4B3
0x18000d4ad  add     rbx, 28h ; '('
0x18000d4b1  jmp     short loc_18000D448
0x18000d4b3  mov     r9d, r15d; char *
0x18000d4b6  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\mrt\\applicability\\s"...
0x18000d4bd  mov     edx, 27h ; '''; void *
0x18000d4c2  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000d4c8  lea     rcx, [rbp+var_28]
0x18000d4cc  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18000d4d1  nop
0x18000d4d2  test    rdi, rdi
0x18000d4d5  jz      short loc_18000D4E1
0x18000d4d7  mov     rcx, rdi; hLibModule
0x18000d4da  call    cs:__imp_FreeLibrary
0x18000d4e0  nop
0x18000d4e1  mov     rcx, [rbp+string]; string
0x18000d4e5  call    cs:__imp_WindowsDeleteString
0x18000d4eb  lea     r11, [rsp+60h+var_s0]
0x18000d4f0  mov     rbx, [r11+30h]
0x18000d4f4  mov     rsi, [r11+38h]
0x18000d4f8  mov     rsp, r11
0x18000d4fb  pop     r15
0x18000d4fd  pop     r14
0x18000d4ff  pop     r12
0x18000d501  pop     rdi
0x18000d502  pop     rbp
0x18000d503  retn
```
