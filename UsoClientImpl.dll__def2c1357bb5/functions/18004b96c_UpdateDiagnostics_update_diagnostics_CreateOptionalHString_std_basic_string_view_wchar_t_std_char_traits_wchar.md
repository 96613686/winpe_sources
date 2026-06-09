# UpdateDiagnostics::update_diagnostics::_CreateOptionalHString(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)

- ea: `0x18004b96c`
- end: `0x18004b9fe`
- name: `?_CreateOptionalHString@update_diagnostics@UpdateDiagnostics@@CAPEAUHSTRING__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `146`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x18004ba04`

## callees

- `0x180034a30`
- `0x18004b96c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b999`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b999`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004b9ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004b9ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b9a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b9a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004b9c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004b9c2`

## pseudocode

```c
HSTRING __fastcall UpdateDiagnostics::update_diagnostics::_CreateOptionalHString(__int64 a1, HSTRING *a2)
{
  HSTRING v5; // rbp
  DWORD LastError; // ebx
  UINT32 v7; // edx
  const WCHAR *v8; // rcx
  HRESULT String; // eax
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !*(_QWORD *)(a1 + 8) )
    return 0;
  v5 = *a2;
  if ( *a2 )
  {
    LastError = GetLastError();
    WindowsDeleteString(v5);
    SetLastError(LastError);
  }
  v7 = *(_DWORD *)(a1 + 8);
  v8 = *(const WCHAR **)a1;
  *a2 = 0;
  String = WindowsCreateString(v8, v7, a2);
  if ( String < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1BB,
      (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\inc\\UpDiag.hpp",
      (const char *)(unsigned int)String,
      v10);
  return *a2;
}

```

## disassembly

```asm
0x18004b96c  mov     [rsp+arg_0], rbx
0x18004b971  mov     [rsp+arg_8], rbp
0x18004b976  mov     [rsp+arg_10], rsi
0x18004b97b  push    rdi; int
0x18004b97c  sub     rsp, 20h
0x18004b980  cmp     qword ptr [rcx+8], 0
0x18004b985  mov     rdi, rdx
0x18004b988  mov     rsi, rcx
0x18004b98b  jnz     short loc_18004B991
0x18004b98d  xor     eax, eax
0x18004b98f  jmp     short loc_18004B9CF
0x18004b991  mov     rbp, [rdx]
0x18004b994  test    rbp, rbp
0x18004b997  jz      short loc_18004B9B2
0x18004b999  call    cs:__imp_GetLastError
0x18004b99f  mov     rcx, rbp; string
0x18004b9a2  mov     ebx, eax
0x18004b9a4  call    cs:__imp_WindowsDeleteString
0x18004b9aa  mov     ecx, ebx; dwErrCode
0x18004b9ac  call    cs:__imp_SetLastError
0x18004b9b2  mov     edx, [rsi+8]; length
0x18004b9b5  mov     r8, rdi; string
0x18004b9b8  mov     rcx, [rsi]; sourceString
0x18004b9bb  mov     qword ptr [rdi], 0
0x18004b9c2  call    cs:__imp_WindowsCreateString
0x18004b9c8  test    eax, eax
0x18004b9ca  js      short loc_18004B9E4
0x18004b9cc  mov     rax, [rdi]
0x18004b9cf  mov     rbx, [rsp+28h+arg_0]
0x18004b9d4  mov     rbp, [rsp+28h+arg_8]
0x18004b9d9  mov     rsi, [rsp+28h+arg_10]
0x18004b9de  add     rsp, 20h
0x18004b9e2  pop     rdi
0x18004b9e3  retn
0x18004b9e4  mov     rcx, [rsp+28h]; this
0x18004b9e9  lea     r8, aCW1SSrcCalliop; "C:\\__w\\1\\s\\src\\Calliope\\inc\\UpDi"...
0x18004b9f0  mov     r9d, eax; char *
0x18004b9f3  mov     edx, 1BBh; void *
0x18004b9f8  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
