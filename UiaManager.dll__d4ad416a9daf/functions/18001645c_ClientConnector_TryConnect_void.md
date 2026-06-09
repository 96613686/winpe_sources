# ClientConnector::TryConnect(void)

- ea: `0x18001645c`
- end: `0x18001658e`
- name: `?TryConnect@ClientConnector@@AEAAXXZ`
- size: `306`
- prototype: `void __fastcall(ClientConnector *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180015d30`
- `0x180075e70`

## callees

- `0x180011810`
- `0x18001645c`
- `0x180016c74`
- `0x18002991c`
- `0x18002a514`
- `0x180043680`
- `0x180074cf4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016502`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016502`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800164de`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800164de`
- `api-ms-win-core-namedpipe-l1-1-0!SetNamedPipeHandleState` at `0x180016547`
- `api-ms-win-core-namedpipe-l1-1-0!SetNamedPipeHandleState` at `0x180016547`

## string_xrefs

- `0x180016517`: `onecore\windows\accessibletech\uiamanager\dll\namedpipechannel.cpp`
- `0x180016555`: `onecore\windows\accessibletech\uiamanager\dll\namedpipechannel.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ClientConnector::TryConnect(ClientConnector *this)
{
  void **v1; // rdi
  LPCWSTR *v2; // rax
  const WCHAR *v3; // rcx
  HANDLE FileW; // rax
  const char *v5; // r9
  char v6; // bl
  void *v7; // rcx
  const char *v8; // r9
  DWORD Mode[2]; // [rsp+40h] [rbp-30h] BYREF
  LPCWSTR lpFileName[3]; // [rsp+48h] [rbp-28h] BYREF
  unsigned __int64 v11; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  v1 = (void **)((char *)this + 16);
  anonymous_namespace_::GetUiaManagerPipeName((__int64)lpFileName, (_QWORD *)this + 3, 0);
  v2 = lpFileName;
  if ( v11 > 7 )
    v2 = (LPCWSTR *)lpFileName[0];
  *(_QWORD *)Mode = v2;
  UiaManagerTraceLoggingProvider::NamedPipeCreateClientPipe<unsigned short const *>(Mode);
  v3 = (const WCHAR *)lpFileName;
  if ( v11 > 7 )
    v3 = lpFileName[0];
  FileW = CreateFileW(v3, 0xC0000000, 0, 0, 3u, 0x40000000u, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    v1,
    FileW);
  v6 = 1;
  if ( (((unsigned __int64)*v1 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 || GetLastError() == 2 )
    v6 = 0;
  if ( v6 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x319,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\namedpipechannel.cpp",
      v5);
  v7 = *v1;
  if ( (char *)*v1 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    Mode[0] = 2;
    if ( !SetNamedPipeHandleState(v7, Mode, 0, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x31E,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\namedpipechannel.cpp",
        v8);
  }
  std::wstring::_Tidy_deallocate(lpFileName);
}

```

## disassembly

```asm
0x18001645c  mov     [rsp-8+arg_8], rbx
0x180016461  mov     [rsp-8+arg_10], rdi
0x180016466  push    rbp
0x180016467  mov     rbp, rsp
0x18001646a  sub     rsp, 70h
0x18001646e  mov     rax, cs:__security_cookie
0x180016475  xor     rax, rsp
0x180016478  mov     [rbp+var_8], rax
0x18001647c  lea     rdi, [rcx+10h]
0x180016480  lea     rdx, [rcx+18h]
0x180016484  xor     r8d, r8d
0x180016487  lea     rcx, [rbp+lpFileName]
0x18001648b  call    _anonymous_namespace___GetUiaManagerPipeName
0x180016490  nop
0x180016491  lea     rax, [rbp+lpFileName]
0x180016495  cmp     [rbp+var_10], 7
0x18001649a  cmova   rax, [rbp+lpFileName]
0x18001649f  mov     qword ptr [rbp+Mode], rax
0x1800164a3  lea     rcx, [rbp+Mode]
0x1800164a7  call    ??$NamedPipeCreateClientPipe@PEBG@UiaManagerTraceLoggingProvider@@SAX$$QEAPEBG@Z; UiaManagerTraceLoggingProvider::NamedPipeCreateClientPipe<ushort const *>(ushort const * &&)
0x1800164ac  lea     rcx, [rbp+lpFileName]
0x1800164b0  cmp     [rbp+var_10], 7
0x1800164b5  cmova   rcx, [rbp+lpFileName]; lpFileName
0x1800164ba  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x1800164c3  mov     [rsp+70h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x1800164cb  mov     [rsp+70h+dwCreationDisposition], 3; dwCreationDisposition
0x1800164d3  xor     r9d, r9d; lpSecurityAttributes
0x1800164d6  xor     r8d, r8d; dwShareMode
0x1800164d9  mov     edx, 0C0000000h; dwDesiredAccess
0x1800164de  call    cs:__imp_CreateFileW
0x1800164e4  mov     rdx, rax
0x1800164e7  mov     rcx, rdi
0x1800164ea  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800164ef  mov     rax, [rdi]
0x1800164f2  mov     ebx, 1
0x1800164f7  add     rax, rbx
0x1800164fa  test    rax, 0FFFFFFFFFFFFFFFEh
0x180016500  jnz     short loc_18001650D
0x180016502  call    cs:__imp_GetLastError
0x180016508  cmp     eax, 2
0x18001650b  jnz     short loc_18001650F
0x18001650d  xor     bl, bl
0x18001650f  mov     rcx, [rbp+8]; this
0x180016513  test    bl, bl
0x180016515  jz      short loc_180016529
0x180016517  lea     r8, aOnecoreWindows_29; "onecore\\windows\\accessibletech\\uiama"...
0x18001651e  mov     edx, 319h; void *
0x180016523  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180016529  mov     rcx, [rdi]; hNamedPipe
0x18001652c  lea     rax, [rcx-1]
0x180016530  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180016534  ja      short loc_180016567
0x180016536  mov     [rbp+Mode], 2
0x18001653d  xor     r9d, r9d; lpCollectDataTimeout
0x180016540  xor     r8d, r8d; lpMaxCollectionCount
0x180016543  lea     rdx, [rbp+Mode]; lpMode
0x180016547  call    cs:__imp_SetNamedPipeHandleState
0x18001654d  mov     rcx, [rbp+8]; this
0x180016551  test    eax, eax
0x180016553  jnz     short loc_180016567
0x180016555  lea     r8, aOnecoreWindows_29; "onecore\\windows\\accessibletech\\uiama"...
0x18001655c  mov     edx, 31Eh; void *
0x180016561  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180016567  lea     rcx, [rbp+lpFileName]
0x18001656b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180016570  mov     rcx, [rbp+var_8]
0x180016574  xor     rcx, rsp; StackCookie
0x180016577  call    __security_check_cookie
0x18001657c  lea     r11, [rsp+70h+var_s0]
0x180016581  mov     rbx, [r11+18h]
0x180016585  mov     rdi, [r11+20h]
0x180016589  mov     rsp, r11
0x18001658c  pop     rbp
0x18001658d  retn
```
