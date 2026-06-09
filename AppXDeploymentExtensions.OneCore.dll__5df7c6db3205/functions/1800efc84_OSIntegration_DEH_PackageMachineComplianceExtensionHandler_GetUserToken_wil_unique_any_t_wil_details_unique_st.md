# OSIntegration::DEH::PackageMachineComplianceExtensionHandler::GetUserToken(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)

- ea: `0x1800efc84`
- end: `0x1800efe23`
- name: `?GetUserToken@PackageMachineComplianceExtensionHandler@DEH@OSIntegration@@AEAAJAEAV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z`
- size: `415`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800ba3ec`

## callees

- `0x180067050`
- `0x18006cb78`
- `0x180080b84`
- `0x180082dd4`
- `0x180098bf4`
- `0x1800a2854`
- `0x1800baaac`
- `0x1800efc84`
- `0x1800efe2c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800efd91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800efd91`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800efd7c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800efd7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800efcf2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800efe13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800efcf2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800efe13`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800efd24`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800efd24`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800efcc5`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800efcc5`

## string_xrefs

- `0x1800efcd5`: `onecore\admin\appmodel\osim\src\deh\appx\packagemachinecompliance\packagemachinecompliance.cpp`
- `0x1800efd34`: `onecore\admin\appmodel\osim\src\deh\appx\packagemachinecompliance\packagemachinecompliance.cpp`
- `0x1800efda7`: `onecore\admin\appmodel\osim\src\deh\appx\packagemachinecompliance\packagemachinecompliance.cpp`
- `0x1800efd1d`: `Microsoft\Windows\X509Enrollment\FS.token`

## pseudocode

```c
__int64 __fastcall OSIntegration::DEH::PackageMachineComplianceExtensionHandler::GetUserToken(__int64 a1, _QWORD *a2)
{
  HRESULT v4; // eax
  unsigned int v5; // ebx
  HRESULT v7; // eax
  DWORD LastError; // eax
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-30h]
  DWORD dwCreationDispositiona; // [rsp+20h] [rbp-30h]
  _QWORD v11[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  PWSTR ppszPath; // [rsp+70h] [rbp+20h] BYREF
  PWSTR ppszPathOut; // [rsp+80h] [rbp+30h] BYREF
  HANDLE FileW; // [rsp+88h] [rbp+38h] BYREF

  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    a2,
    -1);
  ppszPath = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &ppszPath,
    0);
  v4 = SHGetKnownFolderPath(&FOLDERID_LocalAppData, 0, *(HANDLE *)(a1 + 16), &ppszPath);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x21E,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagemachinecompliance\\packagemachinecompliance.cpp",
      (const char *)(unsigned int)v4,
      dwCreationDisposition);
LABEL_3:
    if ( ppszPath )
      CoTaskMemFree(ppszPath);
    return v5;
  }
  ppszPathOut = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &ppszPathOut,
    0);
  v7 = PathAllocCombine(ppszPath, L"Microsoft\\Windows\\X509Enrollment\\FS.token", 0, &ppszPathOut);
  v5 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x221,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagemachinecompliance\\packagemachinecompliance.cpp",
      (const char *)(unsigned int)v7,
      dwCreationDisposition);
LABEL_8:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&ppszPathOut);
    goto LABEL_3;
  }
  FileW = CreateFileW(ppszPathOut, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v11[0] = *a2;
    *a2 = -1;
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      a2,
      &FileW);
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      &FileW,
      v11);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v11);
  }
  else
  {
    LastError = GetLastError();
    if ( (LastError & 0xFFFFFFFC) != 0 || LastError == 1 )
    {
      v5 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x22E,
             (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagemachinecompliance\\packagemachinecompliance.cpp",
             (const char *)LastError,
             dwCreationDispositiona);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&FileW);
      goto LABEL_8;
    }
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&FileW);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&ppszPathOut);
  if ( ppszPath )
    CoTaskMemFree(ppszPath);
  return 0;
}

```

## disassembly

```asm
0x1800efc84  push    rbp
0x1800efc86  push    rbx
0x1800efc87  push    rdi
0x1800efc88  mov     rbp, rsp
0x1800efc8b  sub     rsp, 50h
0x1800efc8f  mov     rdi, rdx
0x1800efc92  mov     rbx, rcx
0x1800efc95  mov     rcx, rdi
0x1800efc98  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800efc9c  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800efca1  xor     edx, edx
0x1800efca3  mov     [rbp+ppszPath], 0
0x1800efcab  lea     rcx, [rbp+ppszPath]
0x1800efcaf  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800efcb4  mov     r8, [rbx+10h]; hToken
0x1800efcb8  lea     r9, [rbp+ppszPath]; ppszPath
0x1800efcbc  xor     edx, edx; dwFlags
0x1800efcbe  lea     rcx, FOLDERID_LocalAppData; rfid
0x1800efcc5  call    cs:__imp_SHGetKnownFolderPath
0x1800efccb  mov     ebx, eax
0x1800efccd  test    eax, eax
0x1800efccf  jns     short loc_1800EFCFF
0x1800efcd1  mov     rcx, [rbp+18h]; this
0x1800efcd5  lea     r8, aOnecoreAdminAp_15; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800efcdc  mov     r9d, eax; char *
0x1800efcdf  mov     edx, 21Eh; void *
0x1800efce4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800efce9  mov     rcx, [rbp+ppszPath]; pv
0x1800efced  test    rcx, rcx
0x1800efcf0  jz      short loc_1800EFCF8
0x1800efcf2  call    cs:__imp_CoTaskMemFree
0x1800efcf8  mov     eax, ebx
0x1800efcfa  jmp     loc_1800EFE1B
0x1800efcff  xor     edx, edx
0x1800efd01  mov     [rbp+ppszPathOut], 0
0x1800efd09  lea     rcx, [rbp+ppszPathOut]
0x1800efd0d  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800efd12  mov     rcx, [rbp+ppszPath]; pszPathIn
0x1800efd16  lea     r9, [rbp+ppszPathOut]; ppszPathOut
0x1800efd1a  xor     r8d, r8d; dwFlags
0x1800efd1d  lea     rdx, aMicrosoftWindo_5; "Microsoft\\Windows\\X509Enrollment\\FS."...
0x1800efd24  call    cs:__imp_PathAllocCombine
0x1800efd2a  mov     ebx, eax
0x1800efd2c  test    eax, eax
0x1800efd2e  jns     short loc_1800EFD53
0x1800efd30  mov     rcx, [rbp+18h]; this
0x1800efd34  lea     r8, aOnecoreAdminAp_15; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800efd3b  mov     r9d, eax; char *
0x1800efd3e  mov     edx, 221h; void *
0x1800efd43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800efd48  lea     rcx, [rbp+ppszPathOut]
0x1800efd4c  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800efd51  jmp     short loc_1800EFCE9
0x1800efd53  mov     rcx, [rbp+ppszPathOut]; lpFileName
0x1800efd57  xor     r9d, r9d; lpSecurityAttributes
0x1800efd5a  mov     [rsp+50h+hTemplateFile], 0; hTemplateFile
0x1800efd63  mov     edx, 80000000h; dwDesiredAccess
0x1800efd68  mov     [rsp+50h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800efd70  mov     [rsp+50h+dwCreationDisposition], 3; unsigned int
0x1800efd78  lea     r8d, [r9+1]; dwShareMode
0x1800efd7c  call    cs:__imp_CreateFileW
0x1800efd82  mov     [rbp+arg_18], rax
0x1800efd86  inc     rax
0x1800efd89  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800efd8f  jnz     short loc_1800EFDC8
0x1800efd91  call    cs:__imp_GetLastError
0x1800efd97  test    eax, 0FFFFFFFCh
0x1800efd9c  jnz     short loc_1800EFDA3
0x1800efd9e  cmp     eax, 1
0x1800efda1  jnz     short loc_1800EFDF8
0x1800efda3  mov     rcx, [rbp+18h]; this
0x1800efda7  lea     r8, aOnecoreAdminAp_15; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800efdae  mov     r9d, eax; char *
0x1800efdb1  mov     edx, 22Eh; void *
0x1800efdb6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800efdbb  lea     rcx, [rbp+arg_18]
0x1800efdbf  mov     ebx, eax
0x1800efdc1  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800efdc6  jmp     short loc_1800EFD48
0x1800efdc8  mov     rax, [rdi]
0x1800efdcb  lea     rdx, [rbp+arg_18]
0x1800efdcf  mov     rcx, rdi
0x1800efdd2  mov     [rbp+var_10], rax
0x1800efdd6  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x1800efddd  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1800efde2  lea     rdx, [rbp+var_10]
0x1800efde6  lea     rcx, [rbp+arg_18]
0x1800efdea  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1800efdef  lea     rcx, [rbp+var_10]
0x1800efdf3  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800efdf8  lea     rcx, [rbp+arg_18]
0x1800efdfc  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800efe01  lea     rcx, [rbp+ppszPathOut]
0x1800efe05  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800efe0a  mov     rcx, [rbp+ppszPath]; pv
0x1800efe0e  test    rcx, rcx
0x1800efe11  jz      short loc_1800EFE19
0x1800efe13  call    cs:__imp_CoTaskMemFree
0x1800efe19  xor     eax, eax
0x1800efe1b  add     rsp, 50h
0x1800efe1f  pop     rdi
0x1800efe20  pop     rbx
0x1800efe21  pop     rbp
0x1800efe22  retn
```
