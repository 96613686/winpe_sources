# CloudExperienceHostLaunchTask::GenerateImageContent(void)

- ea: `0x180012ab8`
- end: `0x180012b46`
- name: `?GenerateImageContent@CloudExperienceHostLaunchTask@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@XZ`
- size: `142`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180015a90`

## callees

- `0x18000a5c8`
- `0x18000e2bc`
- `0x18000e580`
- `0x180010dc8`
- `0x180012ab8`

## import_xrefs

- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180012af1`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180012af1`

## string_xrefs

- `0x180012b03`: `shell\oobe\user\dll\oobelauncher.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CloudExperienceHostLaunchTask::GenerateImageContent(__int64 a1, __int64 a2)
{
  HRESULT v4; // eax
  int v6; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  PWSTR ppszPath; // [rsp+50h] [rbp+18h] BYREF

  ppszPath = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &ppszPath,
    0);
  v4 = SHGetKnownFolderPath(&FOLDERID_System, 0x5000u, 0, &ppszPath);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xFB,
      (unsigned int)"shell\\oobe\\user\\dll\\oobelauncher.cpp",
      (const char *)(unsigned int)v4,
      v6);
  wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    a2,
    L"<image placement=\"appLogoOverride\" src=\"%ws\\%ws\"/>",
    ppszPath,
    *(_QWORD *)(a1 + 48));
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPath);
  return a2;
}

```

## disassembly

```asm
0x180012ab8  mov     [rsp+arg_0], rbx
0x180012abd  push    rdi
0x180012abe  sub     rsp, 30h
0x180012ac2  mov     rbx, rdx
0x180012ac5  mov     rdi, rcx
0x180012ac8  mov     [rsp+38h+ppszPath], 0
0x180012ad1  xor     edx, edx
0x180012ad3  lea     rcx, [rsp+38h+ppszPath]
0x180012ad8  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180012add  lea     r9, [rsp+38h+ppszPath]; ppszPath
0x180012ae2  xor     r8d, r8d; hToken
0x180012ae5  mov     edx, 5000h; dwFlags
0x180012aea  lea     rcx, FOLDERID_System; rfid
0x180012af1  call    cs:__imp_SHGetKnownFolderPath
0x180012af7  mov     rcx, [rsp+38h]; this
0x180012afc  test    eax, eax
0x180012afe  jns     short loc_180012B15
0x180012b00  mov     r9d, eax; char *
0x180012b03  lea     r8, aShellOobeUserD_6; "shell\\oobe\\user\\dll\\oobelauncher.cp"...
0x180012b0a  mov     edx, 0FBh; void *
0x180012b0f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180012b15  mov     r9, [rdi+30h]
0x180012b19  mov     r8, [rsp+38h+ppszPath]
0x180012b1e  lea     rdx, aImagePlacement; "<image placement=\"appLogoOverride\" sr"...
0x180012b25  mov     rcx, rbx
0x180012b28  call    ??$str_printf@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,...)
0x180012b2d  nop
0x180012b2e  lea     rcx, [rsp+38h+ppszPath]
0x180012b33  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180012b38  mov     rax, rbx
0x180012b3b  mov     rbx, [rsp+38h+arg_0]
0x180012b40  add     rsp, 30h
0x180012b44  pop     rdi
0x180012b45  retn
```
