# StateRepository::Logging::Initialize(_tlgProvider_t const *,wchar_t const *,void (*)(int,char const *),void (*)(int,char const *),void (*)(int,char const *),void (*)(int,char const *),void (*)(int,char const *),void (*)(void *,char const *),void (*)(void *,char const *,uint),StateRepository::Logging::InitializeFlags)

- ea: `0x180102e1c`
- end: `0x180102fe3`
- name: `?Initialize@Logging@StateRepository@@YAJPEBU_tlgProvider_t@@PEB_WP6AXHPEBD@Z3333P6AXPEAX2@ZP6AX42I@ZW4InitializeFlags@12@@Z`
- size: `455`
- prototype: `__int64(__int64, __int64, __int64, ...)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18010165c`

## callees

- `0x1800bf150`
- `0x1800eabf4`
- `0x180102288`
- `0x180102e1c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180102e53`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180102e53`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180102e6b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180102e6b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180102ec1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180102f1e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180102fb2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180102ec1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180102f1e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180102fb2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180102fba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180102fba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180102fa7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180102fa7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180102f10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180102f10`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x180102e79`

## string_xrefs

- `0x180102e4c`: `kernelbase.dll`
- `0x180102e80`: `CapabilityAccessManager.log`
- `0x180102ea8`: `onecore\base\appmodel\staterepository\dataaccesslayer\logging.cpp`
- `0x180102efc`: `onecore\base\appmodel\staterepository\dataaccesslayer\logging.cpp`
- `0x180102e61`: `GetTempPath2W`

## pseudocode

```c
__int64 StateRepository::Logging::Initialize(__int64 a1, __int64 a2, __int64 a3, ...)
{
  HMODULE Library; // rax
  unsigned __int64 v5; // r8
  HMODULE v6; // rdi
  void *ProcAddress; // rbp
  HLOCAL v8; // rbx
  int v10; // eax
  unsigned int v11; // esi
  HMODULE v12; // rsi
  DWORD LastError; // ebx
  int v14; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HLOCAL hMem; // [rsp+58h] [rbp+20h] BYREF
  va_list hMema; // [rsp+58h] [rbp+20h]
  __int64 v18; // [rsp+60h] [rbp+28h]
  __int64 v19; // [rsp+68h] [rbp+30h]
  __int64 v20; // [rsp+70h] [rbp+38h]
  __int64 v21; // [rsp+78h] [rbp+40h]
  __int64 v22; // [rsp+80h] [rbp+48h]
  __int64 v23; // [rsp+88h] [rbp+50h]
  va_list va1; // [rsp+90h] [rbp+58h] BYREF

  va_start(va1, a3);
  va_start(hMema, a3);
  hMem = va_arg(va1, HLOCAL);
  v18 = va_arg(va1, _QWORD);
  v19 = va_arg(va1, _QWORD);
  v20 = va_arg(va1, _QWORD);
  v21 = va_arg(va1, _QWORD);
  v22 = va_arg(va1, _QWORD);
  v23 = va_arg(va1, _QWORD);
  if ( (v23 & 2) != 0 )
    return 0;
  Library = LoadLibraryExW(L"kernelbase.dll", 0, 0x800u);
  v6 = Library;
  if ( !Library || (ProcAddress = GetProcAddress(Library, "GetTempPath2W")) == 0 )
    ProcAddress = GetTempPathW;
  wil::make_hlocal_string_nothrow((wil *)hMema, L"CapabilityAccessManager.log", v5);
  v8 = hMem;
  if ( !hMem )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4A,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\logging.cpp",
      (const char *)0x8007000ELL,
      v14);
    if ( v6 )
      FreeLibrary(v6);
    return 2147942414LL;
  }
  v10 = sqlite3_config(16, StateRepository::Logging::sqliteLogCallback);
  v11 = v10;
  if ( v10 > 0 )
    v11 = (unsigned __int16)v10 | 0x87AF0000;
  if ( (v11 & 0x80000000) == 0 )
  {
    qword_1801403D8 = a1;
    ::hMem = v8;
    qword_180140400 = (__int64)Windows::Internal::CapabilityAccess::Desktop::Storage::Database::LoggerTrace;
    qword_180140408 = (__int64)Windows::Internal::CapabilityAccess::Desktop::Storage::Database::LoggerTrace;
    qword_1801403F0 = (__int64)Windows::Internal::CapabilityAccess::Desktop::Storage::Database::LoggerTrace;
    qword_1801403F8 = (__int64)Windows::Internal::CapabilityAccess::Desktop::Storage::Database::LoggerTrace;
    qword_1801403E0 = (__int64)Windows::Internal::CapabilityAccess::Desktop::Storage::Database::LoggerTrace;
    qword_1801403E8 = (__int64)Windows::Internal::CapabilityAccess::Desktop::Storage::Database::LoggerTrace;
    qword_1801403D0 = (__int64)Windows::Internal::CapabilityAccess::Desktop::Storage::Database::LoggerTrace;
    v12 = hLibModule;
    if ( hLibModule )
    {
      LastError = GetLastError();
      FreeLibrary(v12);
      SetLastError(LastError);
    }
    hLibModule = v6;
    qword_1801403C8 = (__int64)ProcAddress;
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4C,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\logging.cpp",
    (const char *)v11,
    v14);
  LocalFree(v8);
  if ( v6 )
    FreeLibrary(v6);
  return v11;
}

```

## disassembly

```asm
0x180102e1c  mov     [rsp+arg_0], rbx
0x180102e21  mov     [rsp+arg_8], rbp
0x180102e26  mov     [rsp+hMem], r9
0x180102e2b  push    rsi
0x180102e2c  push    rdi
0x180102e2d  push    r14; int
0x180102e2f  sub     rsp, 20h
0x180102e33  mov     r14, rcx
0x180102e36  test    byte ptr [rsp+38h+arg_48], 2
0x180102e3e  jnz     loc_180102FCE
0x180102e44  xor     edx, edx; hFile
0x180102e46  mov     r8d, 800h; dwFlags
0x180102e4c  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180102e53  call    cs:__imp_LoadLibraryExW
0x180102e59  mov     rdi, rax
0x180102e5c  test    rax, rax
0x180102e5f  jz      short loc_180102E79
0x180102e61  lea     rdx, aGettemppath2w; "GetTempPath2W"
0x180102e68  mov     rcx, rax; hModule
0x180102e6b  call    cs:__imp_GetProcAddress
0x180102e71  mov     rbp, rax
0x180102e74  test    rax, rax
0x180102e77  jnz     short loc_180102E80
0x180102e79  mov     rbp, cs:__imp_GetTempPathW
0x180102e80  lea     rdx, aCapabilityacce_0; "CapabilityAccessManager.log"
0x180102e87  lea     rcx, [rsp+38h+hMem]; this
0x180102e8c  call    ?make_hlocal_string_nothrow@wil@@YA@PEB_W_K@Z; wil::make_hlocal_string_nothrow(wchar_t const *,unsigned __int64)
0x180102e91  mov     rbx, [rsp+38h+hMem]
0x180102e96  test    rbx, rbx
0x180102e99  jnz     short loc_180102ECE
0x180102e9b  mov     rcx, [rsp+38h]; this
0x180102ea0  mov     ebx, 8007000Eh
0x180102ea5  mov     r9d, ebx; char *
0x180102ea8  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appmodel\\staterepositor"...
0x180102eaf  mov     edx, 4Ah ; 'J'; void *
0x180102eb4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180102eb9  test    rdi, rdi
0x180102ebc  jz      short loc_180102EC7
0x180102ebe  mov     rcx, rdi; hLibModule
0x180102ec1  call    cs:__imp_FreeLibrary
0x180102ec7  mov     eax, ebx
0x180102ec9  jmp     loc_180102FD0
0x180102ece  xor     r8d, r8d
0x180102ed1  lea     rdx, ?sqliteLogCallback@Logging@StateRepository@@YAXPEAXHPEBD@Z; StateRepository::Logging::sqliteLogCallback(void *,int,char const *)
0x180102ed8  lea     ecx, [r8+10h]
0x180102edc  call    sqlite3_config
0x180102ee1  mov     esi, eax
0x180102ee3  test    eax, eax
0x180102ee5  jle     short loc_180102EF0
0x180102ee7  movzx   esi, ax
0x180102eea  or      esi, 87AF0000h
0x180102ef0  test    esi, esi
0x180102ef2  jns     short loc_180102F2B
0x180102ef4  mov     rcx, [rsp+38h]; this
0x180102ef9  mov     r9d, esi; char *
0x180102efc  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appmodel\\staterepositor"...
0x180102f03  mov     edx, 4Ch ; 'L'; void *
0x180102f08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180102f0d  mov     rcx, rbx; hMem
0x180102f10  call    cs:__imp_LocalFree
0x180102f16  test    rdi, rdi
0x180102f19  jz      short loc_180102F24
0x180102f1b  mov     rcx, rdi; hLibModule
0x180102f1e  call    cs:__imp_FreeLibrary
0x180102f24  mov     eax, esi
0x180102f26  jmp     loc_180102FD0
0x180102f2b  mov     cs:qword_1801403D8, r14
0x180102f32  mov     cs:hMem, rbx
0x180102f39  lea     rax, ?LoggerTrace@Database@Storage@Desktop@CapabilityAccess@Internal@Windows@@YAXPEAXPEBD@Z; Windows::Internal::CapabilityAccess::Desktop::Storage::Database::LoggerTrace(void *,char const *)
0x180102f40  mov     cs:qword_180140400, rax
0x180102f47  lea     rax, ?LoggerTrace@Database@Storage@Desktop@CapabilityAccess@Internal@Windows@@YAXPEAXPEBD@Z; Windows::Internal::CapabilityAccess::Desktop::Storage::Database::LoggerTrace(void *,char const *)
0x180102f4e  mov     cs:qword_180140408, rax
0x180102f55  lea     rax, ?LoggerTrace@Database@Storage@Desktop@CapabilityAccess@Internal@Windows@@YAXPEAXPEBD@Z; Windows::Internal::CapabilityAccess::Desktop::Storage::Database::LoggerTrace(void *,char const *)
0x180102f5c  mov     cs:qword_1801403F0, rax
0x180102f63  lea     rax, ?LoggerTrace@Database@Storage@Desktop@CapabilityAccess@Internal@Windows@@YAXPEAXPEBD@Z; Windows::Internal::CapabilityAccess::Desktop::Storage::Database::LoggerTrace(void *,char const *)
0x180102f6a  mov     cs:qword_1801403F8, rax
0x180102f71  lea     rax, ?LoggerTrace@Database@Storage@Desktop@CapabilityAccess@Internal@Windows@@YAXPEAXPEBD@Z; Windows::Internal::CapabilityAccess::Desktop::Storage::Database::LoggerTrace(void *,char const *)
0x180102f78  mov     cs:qword_1801403E0, rax
0x180102f7f  lea     rax, ?LoggerTrace@Database@Storage@Desktop@CapabilityAccess@Internal@Windows@@YAXPEAXPEBD@Z; Windows::Internal::CapabilityAccess::Desktop::Storage::Database::LoggerTrace(void *,char const *)
0x180102f86  mov     cs:qword_1801403E8, rax
0x180102f8d  lea     rax, ?LoggerTrace@Database@Storage@Desktop@CapabilityAccess@Internal@Windows@@YAXPEAXPEBD@Z; Windows::Internal::CapabilityAccess::Desktop::Storage::Database::LoggerTrace(void *,char const *)
0x180102f94  mov     cs:qword_1801403D0, rax
0x180102f9b  mov     rsi, cs:hLibModule
0x180102fa2  test    rsi, rsi
0x180102fa5  jz      short loc_180102FC0
0x180102fa7  call    cs:__imp_GetLastError
0x180102fad  mov     ebx, eax
0x180102faf  mov     rcx, rsi; hLibModule
0x180102fb2  call    cs:__imp_FreeLibrary
0x180102fb8  mov     ecx, ebx; dwErrCode
0x180102fba  call    cs:__imp_SetLastError
0x180102fc0  mov     cs:hLibModule, rdi
0x180102fc7  mov     cs:qword_1801403C8, rbp
0x180102fce  xor     eax, eax
0x180102fd0  mov     rbx, [rsp+38h+arg_0]
0x180102fd5  mov     rbp, [rsp+38h+arg_8]
0x180102fda  add     rsp, 20h
0x180102fde  pop     r14
0x180102fe0  pop     rdi
0x180102fe1  pop     rsi
0x180102fe2  retn
```
