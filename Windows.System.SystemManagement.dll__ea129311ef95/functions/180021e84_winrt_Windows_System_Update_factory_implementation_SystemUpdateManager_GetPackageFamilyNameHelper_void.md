# winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::GetPackageFamilyNameHelper(void)

- ea: `0x180021e84`
- end: `0x180021f3e`
- name: `?GetPackageFamilyNameHelper@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `186`
- prototype: `__int64 __fastcall(CallerIdentity *, __int64, void **)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180021f44`
- `0x1800242c0`

## callees

- `0x1800191a8`
- `0x18001f51c`
- `0x18001f688`
- `0x180021e84`
- `0x180027574`
- `0x180027800`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021ef6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021ef6`

## pseudocode

```c
__int64 __fastcall winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::GetPackageFamilyNameHelper(
        CallerIdentity *a1,
        __int64 a2,
        void **a3)
{
  int CallingProcessHandle; // ebx
  unsigned __int16 **v5; // r8
  char *v6; // rcx
  const wchar_t *v7; // rdx
  const wchar_t **v9; // [rsp+28h] [rbp-18h] BYREF
  __int64 v10; // [rsp+30h] [rbp-10h] BYREF
  char v11; // [rsp+38h] [rbp-8h]
  HANDLE hObject; // [rsp+50h] [rbp+10h] BYREF
  const wchar_t *v13; // [rsp+60h] [rbp+20h] BYREF

  v13 = 0;
  v9 = &v13;
  v11 = 1;
  v10 = 0;
  hObject = 0;
  CallingProcessHandle = CallerIdentity::GetCallingProcessHandle(a1, (unsigned int)&hObject, a3);
  if ( CallingProcessHandle >= 0 )
    CallingProcessHandle = CallerIdentity::GetPackageFamilyNameFromProcess(hObject, &v10, v5);
  v6 = (char *)hObject;
  hObject = 0;
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v6);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v9);
  v7 = v13;
  if ( CallingProcessHandle < 0 )
    v7 = L"NoPackageFamilyName";
  std::wstring::wstring(a2, v7);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v13);
  return a2;
}

```

## disassembly

```asm
0x180021e84  mov     [rsp-8+arg_8], rbx
0x180021e89  mov     [rsp-8+arg_18], rdi
0x180021e8e  mov     [rsp-8+hObject], rcx
0x180021e93  push    rbp
0x180021e94  mov     rbp, rsp
0x180021e97  sub     rsp, 40h
0x180021e9b  mov     rdi, rdx
0x180021e9e  mov     [rbp+arg_10], 0
0x180021ea6  lea     rax, [rbp+arg_10]
0x180021eaa  mov     [rbp+var_18], rax
0x180021eae  mov     [rbp+var_8], 1
0x180021eb2  mov     [rbp+var_10], 0
0x180021eba  mov     [rbp+hObject], 0
0x180021ec2  lea     rdx, [rbp+hObject]; unsigned int
0x180021ec6  call    ?GetCallingProcessHandle@CallerIdentity@@YAJKPEAPEAX@Z; CallerIdentity::GetCallingProcessHandle(ulong,void * *)
0x180021ecb  mov     ebx, eax
0x180021ecd  test    eax, eax
0x180021ecf  js      short loc_180021EE0
0x180021ed1  lea     rdx, [rbp+var_10]; void *
0x180021ed5  mov     rcx, [rbp+hObject]; hProcess
0x180021ed9  call    ?GetPackageFamilyNameFromProcess@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetPackageFamilyNameFromProcess(void *,ushort * *)
0x180021ede  mov     ebx, eax
0x180021ee0  mov     rcx, [rbp+hObject]; hObject
0x180021ee4  mov     [rbp+hObject], 0
0x180021eec  lea     rax, [rcx-1]
0x180021ef0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180021ef4  ja      short loc_180021EFD
0x180021ef6  call    cs:__imp_CloseHandle
0x180021efc  nop
0x180021efd  lea     rcx, [rbp+var_18]
0x180021f01  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180021f06  shr     ebx, 1Fh
0x180021f09  xor     bl, 1
0x180021f0c  mov     rcx, rdi
0x180021f0f  mov     rdx, [rbp+arg_10]
0x180021f13  jnz     short loc_180021F1C
0x180021f15  lea     rdx, aNopackagefamil; "NoPackageFamilyName"
0x180021f1c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180021f21  nop
0x180021f22  lea     rcx, [rbp+arg_10]
0x180021f26  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180021f2b  mov     rax, rdi
0x180021f2e  mov     rbx, [rsp+40h+arg_8]
0x180021f33  mov     rdi, [rsp+40h+arg_18]
0x180021f38  add     rsp, 40h
0x180021f3c  pop     rbp
0x180021f3d  retn
```
