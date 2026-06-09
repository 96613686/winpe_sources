# boost::filesystem::detail::_anonymous_namespace_::init_winapi_func_ptrs

- ea: `0x140007930`
- end: `0x140007a34`
- name: `boost::filesystem::detail::_anonymous_namespace_::init_winapi_func_ptrs`
- size: `260`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, reparse_path, loader_planting`

## callees

- `0x140007930`
- `0x140009970`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x140007942`
- `KERNEL32!GetModuleHandleW` at `0x1400079e5`
- `KERNEL32!GetModuleHandleW` at `0x140007942`
- `KERNEL32!GetModuleHandleW` at `0x1400079e5`
- `KERNEL32!GetProcAddress` at `0x140007963`
- `KERNEL32!GetProcAddress` at `0x14000797f`
- `KERNEL32!GetProcAddress` at `0x14000799b`
- `KERNEL32!GetProcAddress` at `0x1400079b4`
- `KERNEL32!GetProcAddress` at `0x140007a02`
- `KERNEL32!GetProcAddress` at `0x140007a1b`
- `KERNEL32!GetProcAddress` at `0x140007963`
- `KERNEL32!GetProcAddress` at `0x14000797f`
- `KERNEL32!GetProcAddress` at `0x14000799b`
- `KERNEL32!GetProcAddress` at `0x1400079b4`
- `KERNEL32!GetProcAddress` at `0x140007a02`
- `KERNEL32!GetProcAddress` at `0x140007a1b`

## string_xrefs

- `0x140007936`: `kernel32.dll`
- `0x14000796a`: `SetFileInformationByHandle`
- `0x140007986`: `CreateHardLinkW`
- `0x1400079a2`: `CreateSymbolicLinkW`
- `0x1400079f8`: `NtCreateFile`
- `0x140007a09`: `NtQueryDirectoryFile`
- `0x1400079de`: `ntdll.dll`

## pseudocode

```c
void boost::filesystem::detail::_anonymous_namespace_::init_winapi_func_ptrs()
{
  HMODULE ModuleHandleW; // rax
  HMODULE v1; // rdi
  int (__high *v2)(void *, enum boost::filesystem::detail::file_info_by_handle_class, void *, unsigned int); // rbx
  __int64 v3; // rsi
  HMODULE v4; // rax
  boost::filesystem::detail *v5; // rcx
  HMODULE v6; // rbx

  ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
  v1 = ModuleHandleW;
  if ( ModuleHandleW )
  {
    boost::filesystem::detail::get_file_information_by_handle_ex_api = (int (__high *)(void *, enum boost::filesystem::detail::file_info_by_handle_class, void *, unsigned int))GetProcAddress(ModuleHandleW, "GetFileInformationByHandleEx");
    v2 = boost::filesystem::detail::get_file_information_by_handle_ex_api;
    qword_1400D15F0 = (__int64)GetProcAddress(v1, "SetFileInformationByHandle");
    v3 = qword_1400D15F0;
    qword_1400D15E0 = (__int64)GetProcAddress(v1, "CreateHardLinkW");
    qword_1400D15E8 = (__int64)GetProcAddress(v1, "CreateSymbolicLinkW");
    if ( v2 )
    {
      if ( v3 )
        dword_1400D15F8 = 3;
    }
  }
  v4 = GetModuleHandleW(L"ntdll.dll");
  v6 = v4;
  if ( v4 )
  {
    boost::filesystem::detail::nt_create_file_api = (int (*)(void **, unsigned int, struct boost::filesystem::detail::object_attributes *, struct boost::filesystem::detail::io_status_block *, union _LARGE_INTEGER *, unsigned int, unsigned int, unsigned int, unsigned int, void *, unsigned int))GetProcAddress(v4, "NtCreateFile");
    boost::filesystem::detail::nt_query_directory_file_api = (int (__high *)(void *, void *, void (__high *)(void *, struct boost::filesystem::detail::io_status_block *, unsigned int), void *, struct boost::filesystem::detail::io_status_block *, void *, unsigned int, enum boost::filesystem::detail::file_information_class, unsigned __int8, struct boost::filesystem::detail::unicode_string *, unsigned __int8))GetProcAddress(v6, "NtQueryDirectoryFile");
  }
  boost::filesystem::detail::init_directory_iterator_impl(v5);
}

```

## disassembly

```asm
0x140007930  push    rbx
0x140007932  sub     rsp, 20h
0x140007936  lea     rcx, ModuleName; "kernel32.dll"
0x14000793d  mov     [rsp+28h+arg_8], rdi
0x140007942  call    cs:__imp_GetModuleHandleW
0x140007948  mov     rdi, rax
0x14000794b  test    rax, rax
0x14000794e  jz      loc_1400079DE
0x140007954  lea     rdx, ProcName; "GetFileInformationByHandleEx"
0x14000795b  mov     [rsp+28h+arg_0], rsi
0x140007960  mov     rcx, rax; hModule
0x140007963  call    cs:__imp_GetProcAddress
0x140007969  nop
0x14000796a  lea     rdx, aSetfileinforma; "SetFileInformationByHandle"
0x140007971  mov     cs:?get_file_information_by_handle_ex_api@detail@filesystem@boost@@3P6AHPEAXW4file_info_by_handle_class@123@0K@ZEA, rax; int (*boost::filesystem::detail::get_file_information_by_handle_ex_api)(void *,boost::filesystem::detail::file_info_by_handle_class,void *,ulong)
0x140007978  mov     rcx, rdi; hModule
0x14000797b  nop
0x14000797c  mov     rbx, rax
0x14000797f  call    cs:__imp_GetProcAddress
0x140007985  nop
0x140007986  lea     rdx, aCreatehardlink; "CreateHardLinkW"
0x14000798d  mov     cs:qword_1400D15F0, rax
0x140007994  mov     rcx, rdi; hModule
0x140007997  nop
0x140007998  mov     rsi, rax
0x14000799b  call    cs:__imp_GetProcAddress
0x1400079a1  nop
0x1400079a2  lea     rdx, aCreatesymbolic; "CreateSymbolicLinkW"
0x1400079a9  mov     cs:qword_1400D15E0, rax
0x1400079b0  mov     rcx, rdi; hModule
0x1400079b3  nop
0x1400079b4  call    cs:__imp_GetProcAddress
0x1400079ba  nop
0x1400079bb  mov     cs:qword_1400D15E8, rax
0x1400079c2  nop
0x1400079c3  test    rbx, rbx
0x1400079c6  jz      short loc_1400079D9
0x1400079c8  test    rsi, rsi
0x1400079cb  jz      short loc_1400079D9
0x1400079cd  nop
0x1400079ce  mov     cs:dword_1400D15F8, 3
0x1400079d8  nop
0x1400079d9  mov     rsi, [rsp+28h+arg_0]
0x1400079de  lea     rcx, aNtdllDll; "ntdll.dll"
0x1400079e5  call    cs:__imp_GetModuleHandleW
0x1400079eb  mov     rdi, [rsp+28h+arg_8]
0x1400079f0  mov     rbx, rax
0x1400079f3  test    rax, rax
0x1400079f6  jz      short loc_140007A2A
0x1400079f8  lea     rdx, aNtcreatefile; "NtCreateFile"
0x1400079ff  mov     rcx, rax; hModule
0x140007a02  call    cs:__imp_GetProcAddress
0x140007a08  nop
0x140007a09  lea     rdx, aNtquerydirecto; "NtQueryDirectoryFile"
0x140007a10  mov     cs:?nt_create_file_api@detail@filesystem@boost@@3P6AJPEAPEAXKPEAUobject_attributes@123@PEAUio_status_block@123@PEAT_LARGE_INTEGER@@KKKKPEAXK@ZEA, rax; long (*boost::filesystem::detail::nt_create_file_api)(void * *,ulong,boost::filesystem::detail::object_attributes *,boost::filesystem::detail::io_status_block *,_LARGE_INTEGER *,ulong,ulong,ulong,ulong,void *,ulong)
0x140007a17  mov     rcx, rbx; hModule
0x140007a1a  nop
0x140007a1b  call    cs:__imp_GetProcAddress
0x140007a21  nop
0x140007a22  mov     cs:?nt_query_directory_file_api@detail@filesystem@boost@@3P6AJPEAX0P6AX0PEAUio_status_block@123@K@Z010KW4file_information_class@123@EPEAUunicode_string@123@E@ZEA, rax; long (*boost::filesystem::detail::nt_query_directory_file_api)(void *,void *,void (*)(void *,boost::filesystem::detail::io_status_block *,ulong),void *,boost::filesystem::detail::io_status_block *,void *,ulong,boost::filesystem::detail::file_information_class,uchar,boost::filesystem::detail::unicode_string *,uchar)
0x140007a29  nop
0x140007a2a  add     rsp, 20h
0x140007a2e  pop     rbx
0x140007a2f  jmp     ?init_directory_iterator_impl@detail@filesystem@boost@@YAXXZ; boost::filesystem::detail::init_directory_iterator_impl(void)
```
