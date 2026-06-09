# WindowsStorage::Utilities::NtObjectPath::TryFromFileName(ushort const *)

- ea: `0x18000f5cc`
- end: `0x18000f674`
- name: `?TryFromFileName@NtObjectPath@Utilities@WindowsStorage@@SA?AV123@PEBG@Z`
- size: `168`
- prototype: `_QWORD *__fastcall(_QWORD *, const WCHAR *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, reparse_path, registry_config`

## callers

- `0x18000e2fc`
- `0x18000fa4c`
- `0x180015ad4`

## callees

- `0x18000a5e4`
- `0x18000d4e0`
- `0x18000d564`
- `0x18000f5cc`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000f604`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000f604`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f640`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f64b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f640`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f64b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall WindowsStorage::Utilities::NtObjectPath::TryFromFileName(_QWORD *a1, const WCHAR *a2)
{
  HANDLE FileW; // rax
  __int64 v4; // rbx
  __int64 v6; // [rsp+70h] [rbp+18h] BYREF
  HANDLE v7; // [rsp+78h] [rbp+20h] BYREF

  FileW = CreateFileW(a2, 0x80u, 7u, 0, 3u, 0x2000000u, 0);
  v7 = FileW;
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    wil::GetFinalPathNameByHandleW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,256>(
      &v6,
      FileW);
    v4 = v6;
    v6 = 0;
    WindowsDeleteString(0);
    *a1 = v4;
    WindowsDeleteString(0);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v6);
  }
  else
  {
    *a1 = 0;
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v7);
  return a1;
}

```

## disassembly

```asm
0x18000f5cc  mov     [rsp+arg_0], rbx
0x18000f5d1  push    rdi
0x18000f5d2  sub     rsp, 50h
0x18000f5d6  mov     rax, rdx
0x18000f5d9  mov     rdi, rcx
0x18000f5dc  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x18000f5e5  mov     [rsp+58h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18000f5ed  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x18000f5f5  xor     r9d, r9d; lpSecurityAttributes
0x18000f5f8  mov     edx, 80h; dwDesiredAccess
0x18000f5fd  lea     r8d, [r9+7]; dwShareMode
0x18000f601  mov     rcx, rax; lpFileName
0x18000f604  call    cs:__imp_CreateFileW
0x18000f60a  mov     [rsp+58h+arg_18], rax
0x18000f60f  lea     rcx, [rax+1]
0x18000f613  test    rcx, 0FFFFFFFFFFFFFFFEh
0x18000f61a  jnz     short loc_18000F623
0x18000f61c  xor     eax, eax
0x18000f61e  mov     [rdi], rax
0x18000f621  jmp     short loc_18000F65C
0x18000f623  mov     rdx, rax
0x18000f626  lea     rcx, [rsp+58h+arg_10]
0x18000f62b  call    ??$GetFinalPathNameByHandleW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEAXW4VolumePrefix@0@W4PathOptions@0@@Z; wil::GetFinalPathNameByHandleW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,256>(void *,wil::VolumePrefix,wil::PathOptions)
0x18000f630  mov     rbx, [rsp+58h+arg_10]
0x18000f635  mov     [rsp+58h+arg_10], 0
0x18000f63e  xor     ecx, ecx; string
0x18000f640  call    cs:__imp_WindowsDeleteString
0x18000f646  mov     [rdi], rbx
0x18000f649  xor     ecx, ecx; string
0x18000f64b  call    cs:__imp_WindowsDeleteString
0x18000f651  lea     rcx, [rsp+58h+arg_10]
0x18000f656  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18000f65b  nop
0x18000f65c  lea     rcx, [rsp+58h+arg_18]
0x18000f661  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000f666  mov     rax, rdi
0x18000f669  mov     rbx, [rsp+58h+arg_0]
0x18000f66e  add     rsp, 50h
0x18000f672  pop     rdi
0x18000f673  retn
```
