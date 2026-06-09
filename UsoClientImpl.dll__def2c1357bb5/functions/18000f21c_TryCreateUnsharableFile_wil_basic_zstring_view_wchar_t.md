# TryCreateUnsharableFile(wil::basic_zstring_view<wchar_t>)

- ea: `0x18000f21c`
- end: `0x18000f368`
- name: `?TryCreateUnsharableFile@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$basic_zstring_view@_W@2@@Z`
- size: `332`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, installer_update`

## callers

- `0x18000f370`
- `0x18000f580`

## callees

- `0x180009380`
- `0x18000f21c`
- `0x18002ebe8`
- `0x18002ed7c`
- `0x18002ff90`
- `0x180033b00`
- `0x1800482e8`
- `0x180056500`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f30e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f30e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000f2f3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000f2f3`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall TryCreateUnsharableFile(_QWORD *a1, _QWORD *a2)
{
  void *v4; // rsi
  __int64 v5; // rax
  __int64 v6; // rbx
  const WCHAR *v7; // rcx
  HANDLE FileW; // rax
  const char *v9; // r9
  bool v10; // zf
  char v11; // al
  _QWORD v13[3]; // [rsp+50h] [rbp-39h] BYREF
  _BYTE v14[32]; // [rsp+68h] [rbp-21h] BYREF
  _BYTE v15[32]; // [rsp+88h] [rbp-1h] BYREF
  LPCWSTR lpFileName[4]; // [rsp+A8h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v13[2] = a1;
  v4 = (void *)Windows::FileSystem::UsoPrivate(v13, v15);
  v5 = -1;
  do
    ++v5;
  while ( *(_WORD *)(*a2 + 2 * v5) );
  v13[0] = *a2;
  v13[1] = v5;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v14, v13);
  v6 = std::filesystem::path::operator/=(v4);
  std::wstring::~wstring(v14);
  std::wstring::wstring(lpFileName, v6);
  std::wstring::~wstring(v15);
  *a1 = 0;
  v7 = (const WCHAR *)lpFileName;
  if ( lpFileName[3] > (LPCWSTR)7 )
    v7 = lpFileName[0];
  FileW = CreateFileW(v7, 0x10000000u, 0, 0, 2u, 0x4000000u, 0);
  *a1 = FileW;
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 || (v10 = GetLastError() == 32, v11 = 1, v10) )
    v11 = 0;
  if ( v11 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x19D,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\clientImpl\\ClientImpl.cpp",
      v9);
  std::wstring::~wstring(lpFileName);
  return a1;
}

```

## disassembly

```asm
0x18000f21c  mov     [rsp-8+arg_8], rbx
0x18000f221  mov     [rsp-8+arg_10], rsi
0x18000f226  push    rbp
0x18000f227  push    rdi
0x18000f228  push    r15
0x18000f22a  lea     rbp, [rsp-47h]
0x18000f22f  sub     rsp, 0D0h
0x18000f236  mov     rax, cs:__security_cookie
0x18000f23d  xor     rax, rsp
0x18000f240  mov     [rbp+57h+var_18], rax
0x18000f244  mov     rbx, rdx
0x18000f247  mov     rdi, rcx
0x18000f24a  mov     [rbp+57h+var_80], rcx
0x18000f24e  xor     r15d, r15d
0x18000f251  mov     [rbp+57h+var_A0], r15d
0x18000f255  lea     rdx, [rbp+57h+var_58]
0x18000f259  lea     rcx, [rbp+57h+var_90]
0x18000f25d  call    ?UsoPrivate@FileSystem@Windows@@UEAA?AVpath@filesystem@std@@XZ; Windows::FileSystem::UsoPrivate(void)
0x18000f262  mov     rsi, rax
0x18000f265  mov     rcx, [rbx]
0x18000f268  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f26c  inc     rax
0x18000f26f  cmp     [rcx+rax*2], r15w
0x18000f274  jnz     short loc_18000F26C
0x18000f276  mov     [rbp+57h+var_90], rcx
0x18000f27a  mov     [rbp+57h+var_88], rax
0x18000f27e  lea     rdx, [rbp+57h+var_90]
0x18000f282  lea     rcx, [rbp+57h+var_78]
0x18000f286  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x18000f28b  mov     [rbp+57h+var_A0], 2
0x18000f292  lea     rdx, [rbp+57h+var_78]
0x18000f296  mov     rcx, rsi; void *
0x18000f299  call    ??_0path@filesystem@std@@QEAAAEAV012@AEBV012@@Z; std::filesystem::path::operator/=(std::filesystem::path const &)
0x18000f29e  mov     rbx, rax
0x18000f2a1  lea     rcx, [rbp+57h+var_78]; void *
0x18000f2a5  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000f2aa  mov     rdx, rbx
0x18000f2ad  lea     rcx, [rbp+57h+lpFileName]
0x18000f2b1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000f2b6  nop
0x18000f2b7  lea     rcx, [rbp+57h+var_58]; void *
0x18000f2bb  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000f2c0  xor     eax, eax
0x18000f2c2  mov     [rdi], rax
0x18000f2c5  lea     rcx, [rbp+57h+lpFileName]
0x18000f2c9  cmp     [rbp+57h+var_20], 7
0x18000f2ce  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x18000f2d3  mov     [rsp+0E0h+hTemplateFile], r15; hTemplateFile
0x18000f2d8  mov     [rsp+0E0h+dwFlagsAndAttributes], 4000000h; dwFlagsAndAttributes
0x18000f2e0  mov     [rsp+0E0h+dwCreationDisposition], 2; dwCreationDisposition
0x18000f2e8  xor     r9d, r9d; lpSecurityAttributes
0x18000f2eb  xor     r8d, r8d; dwShareMode
0x18000f2ee  mov     edx, 10000000h; dwDesiredAccess
0x18000f2f3  call    cs:__imp_CreateFileW
0x18000f2f9  mov     [rdi], rax
0x18000f2fc  mov     [rbp+57h+var_A0], 3
0x18000f303  inc     rax
0x18000f306  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000f30c  jnz     short loc_18000F31B
0x18000f30e  call    cs:__imp_GetLastError
0x18000f314  cmp     eax, 20h ; ' '
0x18000f317  mov     al, 1
0x18000f319  jnz     short loc_18000F31E
0x18000f31b  mov     al, r15b
0x18000f31e  mov     rcx, [rbp+5Fh]; this
0x18000f322  test    al, al
0x18000f324  jnz     short loc_18000F356
0x18000f326  lea     rcx, [rbp+57h+lpFileName]; void *
0x18000f32a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000f32f  mov     rax, rdi
0x18000f332  mov     rcx, [rbp+57h+var_18]
0x18000f336  xor     rcx, rsp; StackCookie
0x18000f339  call    __security_check_cookie
0x18000f33e  lea     r11, [rsp+0E0h+var_10]
0x18000f346  mov     rbx, [r11+28h]
0x18000f34a  mov     rsi, [r11+30h]
0x18000f34e  mov     rsp, r11
0x18000f351  pop     r15
0x18000f353  pop     rdi
0x18000f354  pop     rbp
0x18000f355  retn
0x18000f356  lea     r8, aCW1SSrcOrchest_3; "C:\\__w\\1\\s\\src\\orchestrator\\clien"...
0x18000f35d  mov     edx, 19Dh; void *
0x18000f362  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
