# Locale::Resources::Initialize(IRequestContext &)

- ea: `0x1800c9ed0`
- end: `0x1800ca1c6`
- name: `?Initialize@Resources@Locale@@QEAA_NAEAVIRequestContext@@@Z`
- size: `758`
- prototype: `bool __fastcall(Locale::Resources *__hidden this, struct IRequestContext *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x1800c9ed0`
- `0x180112380`
- `0x1801123a8`
- `0x1801123e8`
- `0x1801133b0`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9f8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9fb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca05f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca086`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca134`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca155`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9f8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9fb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca05f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca086`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca134`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca155`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800c9f54`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800ca021`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800c9f54`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800ca021`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800c9f6c`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800ca03b`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800c9f6c`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800ca03b`
- `api-ms-win-core-localization-obsolete-l1-1-0!EnumUILanguagesW` at `0x1800ca115`
- `api-ms-win-core-localization-obsolete-l1-1-0!EnumUILanguagesW` at `0x1800ca115`

## string_xrefs

- `0x1800ca001`: `winhttp.dll`
- `0x1800ca018`: `winhttp.dll`
- `0x1800ca06f`: `winhttp.dll`
- `0x1800c9f31`: `WsmRes.dll`
- `0x1800c9f47`: `WsmRes.dll`
- `0x1800c9f9f`: `WsmRes.dll`
- `0x1800c9fce`: `LoadLibrary`
- `0x1800ca09e`: `LoadLibrary`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
bool __fastcall Locale::Resources::Initialize(Locale::Resources *this, struct IRequestContext *a2)
{
  PVOID *v4; // rcx
  HMODULE Library; // rax
  HMODULE v6; // rcx
  HMODULE v7; // rdi
  char LastError; // al
  signed int v9; // eax
  __int64 v10; // rdx
  HMODULE v11; // rax
  HMODULE v12; // rcx
  HMODULE v13; // rdi
  char v14; // al
  signed int v15; // eax
  __int64 v16; // rdx
  bool result; // al
  DWORD v18; // eax
  signed int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rax

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_6bbf9a32e5ac3c927ca3bd482110411f_Traceguids);
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 7) & 0x1000) != 0 )
      WPP_SF_S(v4[2], 16, &WPP_6bbf9a32e5ac3c927ca3bd482110411f_Traceguids, L"WsmRes.dll");
  }
  Library = LoadLibraryExW(L"WsmRes.dll", 0, 0x860u);
  v6 = *(HMODULE *)this;
  v7 = Library;
  *(_QWORD *)this = 0;
  if ( v6 )
    FreeLibrary(v6);
  *(_QWORD *)this = v7;
  if ( !v7 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        (unsigned int)&WPP_6bbf9a32e5ac3c927ca3bd482110411f_Traceguids,
        (unsigned int)L"WsmRes.dll",
        LastError);
    }
    v9 = GetLastError();
    v10 = (unsigned int)v9;
    if ( v9 > 0 )
      v10 = (unsigned __int16)v9 | 0x80070000;
    (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, const wchar_t *, _DWORD))(*(_QWORD *)a2 + 96LL))(
      a2,
      v10,
      1077134176,
      L"LoadLibrary",
      v10);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_6bbf9a32e5ac3c927ca3bd482110411f_Traceguids, L"winhttp.dll");
  v11 = LoadLibraryExW(L"winhttp.dll", 0, 0);
  v12 = (HMODULE)*((_QWORD *)this + 1);
  v13 = v11;
  *((_QWORD *)this + 1) = 0;
  if ( v12 )
    FreeLibrary(v12);
  *((_QWORD *)this + 1) = v13;
  if ( !v13 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    {
      v14 = GetLastError();
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        (unsigned int)&WPP_6bbf9a32e5ac3c927ca3bd482110411f_Traceguids,
        (unsigned int)L"winhttp.dll",
        v14);
    }
    v15 = GetLastError();
    v16 = (unsigned int)v15;
    if ( v15 > 0 )
      v16 = (unsigned __int16)v15 | 0x80070000;
    (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, const wchar_t *, _DWORD))(*(_QWORD *)a2 + 96LL))(
      a2,
      v16,
      1077134176,
      L"LoadLibrary",
      v16);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_6bbf9a32e5ac3c927ca3bd482110411f_Traceguids);
  result = (**((__int64 (__fastcall ***)(char *, struct IRequestContext *))this + 2))((char *)this + 16, a2);
  if ( result )
  {
    Locale::Resources::g_CallbackContext = a2;
    Locale::Resources::g_CallbackMap = (__int64)this + 16;
    if ( !EnumUILanguagesW(Locale::Resources::AddLocale, 0, 0) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      {
        v18 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_6bbf9a32e5ac3c927ca3bd482110411f_Traceguids, v18);
      }
      v19 = GetLastError();
      v20 = (unsigned int)v19;
      if ( v19 > 0 )
        v20 = (unsigned __int16)v19 | 0x80070000;
      (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, const wchar_t *, _DWORD))(*(_QWORD *)a2 + 96LL))(
        a2,
        v20,
        1077134176,
        L"EnumSystemLocales",
        v20);
    }
    v21 = *(_QWORD *)a2;
    Locale::Resources::g_CallbackContext = 0;
    Locale::Resources::g_CallbackMap = 0;
    return (*(unsigned int (__fastcall **)(struct IRequestContext *))(v21 + 144))(a2) == 1;
  }
  return result;
}

```

## disassembly

```asm
0x1800c9ed0  push    rbx
0x1800c9ed2  push    rsi
0x1800c9ed3  push    rdi
0x1800c9ed4  push    r13
0x1800c9ed6  push    r14
0x1800c9ed8  push    r15
0x1800c9eda  sub     rsp, 38h
0x1800c9ede  mov     rbx, rdx
0x1800c9ee1  mov     rsi, rcx
0x1800c9ee4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c9eeb  lea     r14, WPP_GLOBAL_Control
0x1800c9ef2  lea     r15, WPP_6bbf9a32e5ac3c927ca3bd482110411f_Traceguids
0x1800c9ef9  mov     r13d, 1000h
0x1800c9eff  cmp     rcx, r14
0x1800c9f02  jz      short loc_1800C9F45
0x1800c9f04  test    [rcx+1Ch], r13d
0x1800c9f08  jz      short loc_1800C9F22
0x1800c9f0a  mov     rcx, [rcx+10h]
0x1800c9f0e  mov     edx, 0Fh
0x1800c9f13  mov     r8, r15
0x1800c9f16  call    WPP_SF_
0x1800c9f1b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c9f22  cmp     rcx, r14
0x1800c9f25  jz      short loc_1800C9F45
0x1800c9f27  test    [rcx+1Ch], r13d
0x1800c9f2b  jz      short loc_1800C9F45
0x1800c9f2d  mov     rcx, [rcx+10h]
0x1800c9f31  lea     r9, aWsmresDll; "WsmRes.dll"
0x1800c9f38  mov     edx, 10h
0x1800c9f3d  mov     r8, r15
0x1800c9f40  call    WPP_SF_S
0x1800c9f45  xor     edx, edx; hFile
0x1800c9f47  lea     rcx, aWsmresDll; "WsmRes.dll"
0x1800c9f4e  mov     r8d, 860h; dwFlags
0x1800c9f54  call    cs:__imp_LoadLibraryExW
0x1800c9f5a  mov     rcx, [rsi]; hLibModule
0x1800c9f5d  mov     rdi, rax
0x1800c9f60  mov     qword ptr [rsi], 0
0x1800c9f67  test    rcx, rcx
0x1800c9f6a  jz      short loc_1800C9F72
0x1800c9f6c  call    cs:__imp_FreeLibrary
0x1800c9f72  mov     [rsi], rdi
0x1800c9f75  test    rdi, rdi
0x1800c9f78  jnz     short loc_1800C9FEB
0x1800c9f7a  mov     rax, cs:WPP_GLOBAL_Control
0x1800c9f81  cmp     rax, r14
0x1800c9f84  jz      short loc_1800C9FB6
0x1800c9f86  test    dword ptr [rax+1Ch], 800h
0x1800c9f8d  jz      short loc_1800C9FB6
0x1800c9f8f  call    cs:__imp_GetLastError
0x1800c9f95  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c9f9c  lea     edx, [rdi+11h]
0x1800c9f9f  lea     r9, aWsmresDll; "WsmRes.dll"
0x1800c9fa6  mov     [rsp+68h+var_48], eax
0x1800c9faa  mov     r8, r15
0x1800c9fad  mov     rcx, [rcx+10h]
0x1800c9fb1  call    WPP_SF_Sd
0x1800c9fb6  call    cs:__imp_GetLastError
0x1800c9fbc  mov     edx, eax
0x1800c9fbe  test    eax, eax
0x1800c9fc0  jle     short loc_1800C9FCB
0x1800c9fc2  movzx   edx, ax
0x1800c9fc5  or      edx, 80070000h
0x1800c9fcb  mov     rax, [rbx]
0x1800c9fce  lea     r9, aLoadlibrary; "LoadLibrary"
0x1800c9fd5  mov     r8d, 4033C360h
0x1800c9fdb  mov     [rsp+68h+var_48], edx
0x1800c9fdf  mov     rcx, rbx
0x1800c9fe2  mov     rax, [rax+60h]
0x1800c9fe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9feb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c9ff2  cmp     rcx, r14
0x1800c9ff5  jz      short loc_1800CA015
0x1800c9ff7  test    [rcx+1Ch], r13d
0x1800c9ffb  jz      short loc_1800CA015
0x1800c9ffd  mov     rcx, [rcx+10h]
0x1800ca001  lea     r9, aWinhttpDll_0; "winhttp.dll"
0x1800ca008  mov     edx, 12h
0x1800ca00d  mov     r8, r15
0x1800ca010  call    WPP_SF_S
0x1800ca015  xor     r8d, r8d; dwFlags
0x1800ca018  lea     rcx, aWinhttpDll_0; "winhttp.dll"
0x1800ca01f  xor     edx, edx; hFile
0x1800ca021  call    cs:__imp_LoadLibraryExW
0x1800ca027  mov     rcx, [rsi+8]; hLibModule
0x1800ca02b  mov     rdi, rax
0x1800ca02e  mov     qword ptr [rsi+8], 0
0x1800ca036  test    rcx, rcx
0x1800ca039  jz      short loc_1800CA041
0x1800ca03b  call    cs:__imp_FreeLibrary
0x1800ca041  mov     [rsi+8], rdi
0x1800ca045  test    rdi, rdi
0x1800ca048  jnz     short loc_1800CA0BB
0x1800ca04a  mov     rax, cs:WPP_GLOBAL_Control
0x1800ca051  cmp     rax, r14
0x1800ca054  jz      short loc_1800CA086
0x1800ca056  test    dword ptr [rax+1Ch], 800h
0x1800ca05d  jz      short loc_1800CA086
0x1800ca05f  call    cs:__imp_GetLastError
0x1800ca065  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ca06c  lea     edx, [rdi+13h]
0x1800ca06f  lea     r9, aWinhttpDll_0; "winhttp.dll"
0x1800ca076  mov     [rsp+68h+var_48], eax
0x1800ca07a  mov     r8, r15
0x1800ca07d  mov     rcx, [rcx+10h]
0x1800ca081  call    WPP_SF_Sd
0x1800ca086  call    cs:__imp_GetLastError
0x1800ca08c  mov     edx, eax
0x1800ca08e  test    eax, eax
0x1800ca090  jle     short loc_1800CA09B
0x1800ca092  movzx   edx, ax
0x1800ca095  or      edx, 80070000h
0x1800ca09b  mov     rax, [rbx]
0x1800ca09e  lea     r9, aLoadlibrary; "LoadLibrary"
0x1800ca0a5  mov     r8d, 4033C360h
0x1800ca0ab  mov     [rsp+68h+var_48], edx
0x1800ca0af  mov     rcx, rbx
0x1800ca0b2  mov     rax, [rax+60h]
0x1800ca0b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca0bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ca0c2  cmp     rcx, r14
0x1800ca0c5  jz      short loc_1800CA0DE
0x1800ca0c7  test    [rcx+1Ch], r13d
0x1800ca0cb  jz      short loc_1800CA0DE
0x1800ca0cd  mov     rcx, [rcx+10h]
0x1800ca0d1  mov     edx, 14h
0x1800ca0d6  mov     r8, r15
0x1800ca0d9  call    WPP_SF_
0x1800ca0de  lea     rdi, [rsi+10h]
0x1800ca0e2  mov     rdx, rbx
0x1800ca0e5  mov     rax, [rdi]
0x1800ca0e8  mov     rcx, rdi
0x1800ca0eb  mov     rax, [rax]
0x1800ca0ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca0f3  test    al, al
0x1800ca0f5  jz      loc_1800CA1B8
0x1800ca0fb  xor     r8d, r8d; lParam
0x1800ca0fe  mov     cs:?g_CallbackContext@Resources@Locale@@0PEAVIRequestContext@@EA, rbx; IRequestContext * Locale::Resources::g_CallbackContext
0x1800ca105  xor     edx, edx; dwFlags
0x1800ca107  mov     cs:?g_CallbackMap@Resources@Locale@@0PEAV?$SafeMap@VKey@Locale@@KV?$SafeMap_Iterator@VKey@Locale@@K@@@@EA, rdi; SafeMap<Locale::Key,ulong,SafeMap_Iterator<Locale::Key,ulong>> * Locale::Resources::g_CallbackMap
0x1800ca10e  lea     rcx, ?AddLocale@Resources@Locale@@CAHPEAG_J@Z; lpUILanguageEnumProc
0x1800ca115  call    cs:__imp_EnumUILanguagesW
0x1800ca11b  test    eax, eax
0x1800ca11d  jnz     short loc_1800CA18A
0x1800ca11f  mov     rax, cs:WPP_GLOBAL_Control
0x1800ca126  cmp     rax, r14
0x1800ca129  jz      short loc_1800CA155
0x1800ca12b  test    dword ptr [rax+1Ch], 800h
0x1800ca132  jz      short loc_1800CA155
0x1800ca134  call    cs:__imp_GetLastError
0x1800ca13a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ca141  mov     edx, 15h
0x1800ca146  mov     r9d, eax
0x1800ca149  mov     r8, r15
0x1800ca14c  mov     rcx, [rcx+10h]
0x1800ca150  call    WPP_SF_d
0x1800ca155  call    cs:__imp_GetLastError
0x1800ca15b  mov     edx, eax
0x1800ca15d  test    eax, eax
0x1800ca15f  jle     short loc_1800CA16A
0x1800ca161  movzx   edx, ax
0x1800ca164  or      edx, 80070000h
0x1800ca16a  mov     rax, [rbx]
0x1800ca16d  lea     r9, aEnumsystemloca; "EnumSystemLocales"
0x1800ca174  mov     r8d, 4033C360h
0x1800ca17a  mov     [rsp+68h+var_48], edx
0x1800ca17e  mov     rcx, rbx
0x1800ca181  mov     rax, [rax+60h]
0x1800ca185  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca18a  mov     rax, [rbx]
0x1800ca18d  mov     rcx, rbx
0x1800ca190  mov     cs:?g_CallbackContext@Resources@Locale@@0PEAVIRequestContext@@EA, 0; IRequestContext * Locale::Resources::g_CallbackContext
0x1800ca19b  mov     cs:?g_CallbackMap@Resources@Locale@@0PEAV?$SafeMap@VKey@Locale@@KV?$SafeMap_Iterator@VKey@Locale@@K@@@@EA, 0; SafeMap<Locale::Key,ulong,SafeMap_Iterator<Locale::Key,ulong>> * Locale::Resources::g_CallbackMap
0x1800ca1a6  mov     rax, [rax+90h]
0x1800ca1ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca1b2  cmp     eax, 1
0x1800ca1b5  setz    al
0x1800ca1b8  add     rsp, 38h
0x1800ca1bc  pop     r15
0x1800ca1be  pop     r14
0x1800ca1c0  pop     r13
0x1800ca1c2  pop     rdi
0x1800ca1c3  pop     rsi
0x1800ca1c4  pop     rbx
0x1800ca1c5  retn
```
