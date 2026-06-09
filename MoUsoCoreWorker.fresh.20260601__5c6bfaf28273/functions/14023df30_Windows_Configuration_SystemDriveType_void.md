# Windows::Configuration::SystemDriveType(void)

- ea: `0x14023df30`
- end: `0x14023e0f5`
- name: `?SystemDriveType@Configuration@Windows@@UEAA?AW4DriveType@1SystemInterface@@XZ`
- size: `453`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x14002ad90`
- `0x14003c578`
- `0x14003f4a8`
- `0x140045404`
- `0x14018b0dc`
- `0x14023df30`
- `0x140379070`
- `0x140380bd0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x14023df7e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x14023df7e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14023e0ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14023e0ab`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14023e019`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14023e019`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14023e06a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14023e06a`

## string_xrefs

- `0x14023e07b`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Configuration.cpp`
- `0x14023e0e0`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Configuration.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 Windows::Configuration::SystemDriveType()
{
  unsigned int v0; // edi
  const char *v1; // r9
  WCHAR v2; // bx
  const WCHAR *v3; // rcx
  char *FileW; // rbx
  const char *v5; // r9
  __int64 v7; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR v8; // [rsp+58h] [rbp-A8h]
  __int64 v9; // [rsp+60h] [rbp-A0h]
  __int64 *v10; // [rsp+68h] [rbp-98h]
  DWORD BytesReturned; // [rsp+70h] [rbp-90h] BYREF
  int InBuffer; // [rsp+78h] [rbp-88h] BYREF
  __int64 v13; // [rsp+7Ch] [rbp-84h]
  __int64 OutBuffer; // [rsp+88h] [rbp-78h] BYREF
  int v15; // [rsp+90h] [rbp-70h]
  LPCWSTR lpFileName[5]; // [rsp+98h] [rbp-68h] BYREF
  WCHAR Buffer[264]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  v0 = 0;
  memset(Buffer, 0, 0x208u);
  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x81,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Configuration.cpp",
      v1);
  v2 = Buffer[0];
  wil::com_ptr_t<ABI::Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::com_ptr_t<ABI::Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v7);
  v8 = v2;
  v7 = 0x6000000000000000LL;
  v9 = 1;
  v10 = &v7;
  std::vformat<0>(lpFileName);
  v3 = (const WCHAR *)lpFileName;
  if ( lpFileName[3] > (LPCWSTR)7 )
    v3 = lpFileName[0];
  FileW = (char *)CreateFileW(v3, 0, 3u, 0, 3u, 0, 0);
  v13 = 0;
  InBuffer = 7;
  OutBuffer = 0;
  v15 = 0;
  BytesReturned = 0;
  if ( DeviceIoControl(FileW, 0x2D1400u, &InBuffer, 0xCu, &OutBuffer, 0xCu, &BytesReturned, 0) )
  {
    v0 = 1;
    if ( !(_BYTE)v15 )
      v0 = 2;
  }
  else
  {
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x9D,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Configuration.cpp",
      v5);
  }
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileW);
  std::wstring::~wstring(lpFileName);
  return v0;
}

```

## disassembly

```asm
0x14023df30  mov     [rsp-8+arg_0], rbx
0x14023df35  mov     [rsp-8+arg_8], rdi
0x14023df3a  push    rbp
0x14023df3b  lea     rbp, [rsp-1E0h]
0x14023df43  sub     rsp, 2E0h
0x14023df4a  mov     rax, cs:__security_cookie
0x14023df51  xor     rax, rsp
0x14023df54  mov     [rbp+1E0h+var_10], rax
0x14023df5b  xor     edi, edi
0x14023df5d  xor     edx, edx; Val
0x14023df5f  mov     r8d, 208h; Size
0x14023df65  lea     rcx, [rbp+1E0h+Buffer]; void *
0x14023df69  call    memset
0x14023df6e  mov     rbx, [rbp+1E8h]
0x14023df75  mov     edx, 104h; uSize
0x14023df7a  lea     rcx, [rbp+1E0h+Buffer]; lpBuffer
0x14023df7e  call    cs:__imp_GetSystemDirectoryW
0x14023df84  test    eax, eax
0x14023df86  jz      loc_14023E0E0
0x14023df8c  movzx   ebx, [rbp+1E0h+Buffer]
0x14023df90  lea     rcx, [rsp+2E0h+var_290]
0x14023df95  call    ??0?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@ABI@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ABI::Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::com_ptr_t<ABI::Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x14023df9a  mov     [rsp+2E0h+var_288], bx
0x14023df9f  mov     rax, 6000000000000000h
0x14023dfa9  mov     [rsp+2E0h+var_290], rax
0x14023dfae  lea     rax, asc_14046FE90; "\\\\.\\{}:"
0x14023dfb5  mov     qword ptr [rsp+2E0h+var_2A0], rax
0x14023dfba  mov     qword ptr [rsp+2E0h+var_2A0+8], 7
0x14023dfc3  mov     [rsp+2E0h+var_280], 1
0x14023dfcc  lea     rax, [rsp+2E0h+var_290]
0x14023dfd1  mov     [rsp+2E0h+var_278], rax
0x14023dfd6  movaps  xmm0, [rsp+2E0h+var_2A0]
0x14023dfdb  movdqa  [rsp+2E0h+var_2A0], xmm0
0x14023dfe1  lea     r8, [rsp+2E0h+var_280]
0x14023dfe6  lea     rdx, [rsp+2E0h+var_2A0]
0x14023dfeb  lea     rcx, [rbp+1E0h+lpFileName]; Src
0x14023dfef  call    ??$vformat@$0A@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@V?$basic_string_view@_WU?$char_traits@_W@std@@@0@V?$basic_format_args@V?$basic_format_context@V?$back_insert_iterator@V?$_Fmt_buffer@_W@std@@@std@@_W@std@@@0@@Z; std::vformat<0>(std::wstring_view,std::basic_format_args<std::basic_format_context<std::back_insert_iterator<std::_Fmt_buffer<wchar_t>>,wchar_t>>)
0x14023dff4  lea     rcx, [rbp+1E0h+lpFileName]
0x14023dff8  cmp     [rbp+1E0h+var_230], 7
0x14023dffd  cmova   rcx, [rbp+1E0h+lpFileName]; lpFileName
0x14023e002  mov     [rsp+2E0h+hTemplateFile], rdi; hTemplateFile
0x14023e007  mov     [rsp+2E0h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x14023e00b  lea     r8d, [rdi+3]; dwShareMode
0x14023e00f  mov     [rsp+2E0h+dwCreationDisposition], r8d; dwCreationDisposition
0x14023e014  xor     r9d, r9d; lpSecurityAttributes
0x14023e017  xor     edx, edx; dwDesiredAccess
0x14023e019  call    cs:__imp_CreateFileW
0x14023e01f  mov     rbx, rax
0x14023e022  mov     [rsp+2E0h+var_264], rdi
0x14023e027  mov     [rsp+2E0h+InBuffer], 7
0x14023e02f  xor     eax, eax
0x14023e031  mov     [rbp+1E0h+OutBuffer], rax
0x14023e035  mov     [rbp+1E0h+var_250], eax
0x14023e038  mov     [rsp+2E0h+BytesReturned], edi
0x14023e03c  mov     [rsp+2E0h+lpOverlapped], rdi; lpOverlapped
0x14023e041  lea     rax, [rsp+2E0h+BytesReturned]
0x14023e046  mov     [rsp+2E0h+hTemplateFile], rax; lpBytesReturned
0x14023e04b  lea     r9d, [rdi+0Ch]; nInBufferSize
0x14023e04f  mov     [rsp+2E0h+dwFlagsAndAttributes], r9d; nOutBufferSize
0x14023e054  lea     rax, [rbp+1E0h+OutBuffer]
0x14023e058  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rax; lpOutBuffer
0x14023e05d  lea     r8, [rsp+2E0h+InBuffer]; lpInBuffer
0x14023e062  mov     edx, 2D1400h; dwIoControlCode
0x14023e067  mov     rcx, rbx; hDevice
0x14023e06a  call    cs:__imp_DeviceIoControl
0x14023e070  test    eax, eax
0x14023e072  jnz     short loc_14023E08E
0x14023e074  mov     rcx, [rbp+1E8h]; this
0x14023e07b  lea     r8, aCW1SSrcOrchest_26; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14023e082  mov     edx, 9Dh; void *
0x14023e087  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x14023e08c  jmp     short loc_14023E09E
0x14023e08e  cmp     byte ptr [rbp+1E0h+var_250], dil
0x14023e092  mov     edi, 1
0x14023e097  jnz     short loc_14023E09E
0x14023e099  mov     edi, 2
0x14023e09e  lea     rcx, [rbx-1]
0x14023e0a2  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x14023e0a6  ja      short loc_14023E0B1
0x14023e0a8  mov     rcx, rbx; hObject
0x14023e0ab  call    cs:__imp_CloseHandle
0x14023e0b1  lea     rcx, [rbp+1E0h+lpFileName]
0x14023e0b5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14023e0ba  mov     eax, edi
0x14023e0bc  mov     rcx, [rbp+1E0h+var_10]
0x14023e0c3  xor     rcx, rsp; StackCookie
0x14023e0c6  call    __security_check_cookie
0x14023e0cb  lea     r11, [rsp+2E0h+var_s0]
0x14023e0d3  mov     rbx, [r11+10h]
0x14023e0d7  mov     rdi, [r11+18h]
0x14023e0db  mov     rsp, r11
0x14023e0de  pop     rbp
0x14023e0df  retn
0x14023e0e0  lea     r8, aCW1SSrcOrchest_26; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14023e0e7  mov     edx, 81h; void *
0x14023e0ec  mov     rcx, rbx; this
0x14023e0ef  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
