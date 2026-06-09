# Service::RegisterCallback(void)

- ea: `0x18001b820`
- end: `0x18001b8a1`
- name: `?RegisterCallback@Service@@AEAAJXZ`
- size: `129`
- prototype: `__int64 __fastcall(Service *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180041180`

## callees

- `0x180007a00`
- `0x180009538`
- `0x18001b820`
- `0x18001b8a8`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001b84e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001b84e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b870`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b870`

## string_xrefs

- `0x18001b83a`: `cdpsgshims.dll`
- `0x18001b867`: `DllInitialize`

## pseudocode

```c
__int64 __fastcall Service::RegisterCallback(Service *this)
{
  int v2; // ebx
  HMODULE Library; // rax
  HMODULE v4; // rcx
  __int64 (*ProcAddress)(void); // rax

  v2 = SharingPlatform::SharingPlatformStatics::InitializeInternal();
  if ( v2 >= 0 )
  {
    Library = LoadLibraryExW(L"cdpsgshims.dll", 0, 0x800u);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
      (char *)this + 224,
      Library);
    v4 = (HMODULE)*((_QWORD *)this + 28);
    if ( !v4 )
      return (unsigned int)Microsoft::WRL::Details::RegisterObjects<2>(Service::s_module);
    v2 = 0;
    ProcAddress = GetProcAddress(v4, "DllInitialize");
    if ( ProcAddress )
      v2 = ProcAddress();
    if ( v2 >= 0 )
      return (unsigned int)Microsoft::WRL::Details::RegisterObjects<2>(Service::s_module);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18001b820  mov     [rsp+arg_0], rbx
0x18001b825  push    rdi
0x18001b826  sub     rsp, 20h
0x18001b82a  mov     rdi, rcx
0x18001b82d  call    ?InitializeInternal@SharingPlatformStatics@SharingPlatform@@SAJXZ; SharingPlatform::SharingPlatformStatics::InitializeInternal(void)
0x18001b832  mov     ebx, eax
0x18001b834  test    eax, eax
0x18001b836  js      short loc_18001B894
0x18001b838  xor     edx, edx; hFile
0x18001b83a  lea     rcx, LibFileName; "cdpsgshims.dll"
0x18001b841  mov     r8d, 800h; dwFlags
0x18001b847  lea     rbx, [rdi+0E0h]
0x18001b84e  call    cs:__imp_LoadLibraryExW
0x18001b854  mov     rdx, rax
0x18001b857  mov     rcx, rbx
0x18001b85a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x18001b85f  mov     rcx, [rbx]; hModule
0x18001b862  test    rcx, rcx
0x18001b865  jz      short loc_18001B886
0x18001b867  lea     rdx, aDllinitialize; "DllInitialize"
0x18001b86e  xor     ebx, ebx
0x18001b870  call    cs:__imp_GetProcAddress
0x18001b876  test    rax, rax
0x18001b879  jz      short loc_18001B882
0x18001b87b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b880  mov     ebx, eax
0x18001b882  test    ebx, ebx
0x18001b884  js      short loc_18001B894
0x18001b886  mov     rcx, cs:?s_module@Service@@0AEAVCdpServiceModule@@EA; CdpServiceModule & Service::s_module
0x18001b88d  call    ??$RegisterObjects@$01@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBG@Z; Microsoft::WRL::Details::RegisterObjects<2>(Microsoft::WRL::Details::ModuleBase *,ushort const *)
0x18001b892  mov     ebx, eax
0x18001b894  mov     eax, ebx
0x18001b896  mov     rbx, [rsp+28h+arg_0]
0x18001b89b  add     rsp, 20h
0x18001b89f  pop     rdi
0x18001b8a0  retn
```
