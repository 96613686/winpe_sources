# Cortana::ConstraintIndex::Search::SettingsJsonGenerator::IsSettingsCacheOnDiskValid(void)

- ea: `0x1800cf0f0`
- end: `0x1800cf1f2`
- name: `?IsSettingsCacheOnDiskValid@SettingsJsonGenerator@Search@ConstraintIndex@Cortana@@SA_NXZ`
- size: `258`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x1800c38c0`
- `0x1800c38e0`

## callees

- `0x1800049e0`
- `0x18000617a`
- `0x18000619e`
- `0x18003ff8c`
- `0x1800cd3f4`
- `0x1800ceea0`
- `0x1800cf0f0`
- `0x1800cf1f8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800cf191`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800cf191`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800cf16b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800cf16b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool Cortana::ConstraintIndex::Search::SettingsJsonGenerator::IsSettingsCacheOnDiskValid(void)
{
  bool v0; // di
  HSTRING SettingsCacheLocation; // rbx
  HSTRING v2; // rsi
  const WCHAR *StringRawBuffer_0; // rax
  char *FileW; // rax
  void *v5; // rdx
  unsigned int v6; // r8d
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-48h]
  char *v9; // [rsp+40h] [rbp-28h] BYREF
  LARGE_INTEGER FileSize; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v0 = 0;
  SettingsCacheLocation = (HSTRING)Cortana::ConstraintIndex::Search::SettingsJsonGenerator::GetSettingsCacheLocation();
  v2 = (HSTRING)__abi_winrt_ptrto_string_ctor(SettingsCacheLocation);
  WindowsDeleteString_0(SettingsCacheLocation);
  StringRawBuffer_0 = WindowsGetStringRawBuffer_0(v2, 0);
  FileW = (char *)CreateFileW(StringRawBuffer_0, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v9 = FileW;
  FileSize.QuadPart = 0;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL && GetFileSizeEx(FileW, &FileSize) )
  {
    if ( FileSize.HighPart <= 0 )
      v0 = FileSize.LowPart != 0;
    else
      wil::details::in1diag3::Log_Hr(retaddr, v5, v6, (const char *)0x800700DFLL, dwCreationDisposition);
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v9);
  WindowsDeleteString_0(v2);
  return v0;
}

```

## disassembly

```asm
0x1800cf0f0  mov     [rsp+arg_0], rbx
0x1800cf0f5  mov     [rsp+arg_8], rsi
0x1800cf0fa  push    rdi
0x1800cf0fb  sub     rsp, 60h
0x1800cf0ff  mov     rax, cs:__security_cookie
0x1800cf106  xor     rax, rsp
0x1800cf109  mov     [rsp+68h+var_18], rax
0x1800cf10e  xor     dil, dil
0x1800cf111  call    ?GetSettingsCacheLocation@SettingsJsonGenerator@Search@ConstraintIndex@Cortana@@SAPE$AAVString@Platform@@XZ; Cortana::ConstraintIndex::Search::SettingsJsonGenerator::GetSettingsCacheLocation(void)
0x1800cf116  mov     rbx, rax
0x1800cf119  mov     [rsp+68h+var_28], rax
0x1800cf11e  mov     rcx, rax
0x1800cf121  call    ?__abi_winrt_ptrto_string_ctor@@YAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_ctor(Platform::String const volatile *)
0x1800cf126  mov     rsi, rax
0x1800cf129  mov     [rsp+68h+var_28], rax
0x1800cf12e  mov     rcx, rbx; string
0x1800cf131  call    WindowsDeleteString_0
0x1800cf136  xor     edx, edx; length
0x1800cf138  mov     rcx, rsi; string
0x1800cf13b  call    WindowsGetStringRawBuffer_0
0x1800cf140  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x1800cf149  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800cf151  mov     [rsp+68h+dwCreationDisposition], 3; int
0x1800cf159  xor     r9d, r9d; lpSecurityAttributes
0x1800cf15c  lea     ebx, [r9+1]
0x1800cf160  mov     r8d, ebx; dwShareMode
0x1800cf163  mov     edx, 80000000h; dwDesiredAccess
0x1800cf168  mov     rcx, rax; lpFileName
0x1800cf16b  call    cs:__imp_CreateFileW
0x1800cf171  mov     [rsp+68h+var_28], rax
0x1800cf176  mov     qword ptr [rsp+68h+FileSize], 0
0x1800cf17f  lea     rcx, [rax-1]
0x1800cf183  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800cf187  ja      short loc_1800CF1C0
0x1800cf189  lea     rdx, [rsp+68h+FileSize]; lpFileSize
0x1800cf18e  mov     rcx, rax; hFile
0x1800cf191  call    cs:__imp_GetFileSizeEx
0x1800cf197  test    eax, eax
0x1800cf199  jz      short loc_1800CF1C0
0x1800cf19b  cmp     dword ptr [rsp+68h+FileSize+4], 0
0x1800cf1a0  jle     short loc_1800CF1B4
0x1800cf1a2  mov     rcx, [rsp+68h]; this
0x1800cf1a7  mov     r9d, 800700DFh; char *
0x1800cf1ad  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800cf1b2  jmp     short loc_1800CF1C0
0x1800cf1b4  movzx   edi, dil
0x1800cf1b8  cmp     dword ptr [rsp+68h+FileSize], 0
0x1800cf1bd  cmova   edi, ebx
0x1800cf1c0  lea     rcx, [rsp+68h+var_28]
0x1800cf1c5  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800cf1ca  mov     rcx, rsi; string
0x1800cf1cd  call    WindowsDeleteString_0
0x1800cf1d2  mov     al, dil
0x1800cf1d5  mov     rcx, [rsp+68h+var_18]
0x1800cf1da  xor     rcx, rsp; StackCookie
0x1800cf1dd  call    __security_check_cookie
0x1800cf1e2  mov     rbx, [rsp+68h+arg_0]
0x1800cf1e7  mov     rsi, [rsp+68h+arg_8]
0x1800cf1ec  add     rsp, 60h
0x1800cf1f0  pop     rdi
0x1800cf1f1  retn
```
