# winrt::Windows::Graphics::Internal::Printing::WindowsProtectedPrint::implementation::GetResourceString(uint)

- ea: `0x1800533c0`
- end: `0x18005345f`
- name: `?GetResourceString@implementation@WindowsProtectedPrint@Printing@Internal@Graphics@Windows@winrt@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z`
- size: `159`
- prototype: `__int64 __fastcall(__int64, UINT)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180053250`

## callees

- `0x1800074f4`
- `0x18002138c`
- `0x180023664`
- `0x1800533c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800533de`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800533de`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800533ff`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800533ff`

## string_xrefs

- `0x1800533d7`: `PrintWorkflowService.dll`
- `0x18005344d`: `onecoreuap\printscan\print\workflow\broker\wpp_lib\windowsprotectedprinthandler.cpp`

## pseudocode

```c
__int64 __fastcall winrt::Windows::Graphics::Internal::Printing::WindowsProtectedPrint::implementation::GetResourceString(
        __int64 a1,
        UINT a2)
{
  int StringW; // eax
  const char *v5; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 Buffer; // [rsp+50h] [rbp+18h] BYREF
  HINSTANCE Library; // [rsp+58h] [rbp+20h] BYREF

  Library = LoadLibraryExW(L"PrintWorkflowService.dll", 0, 0x800u);
  Buffer = 0;
  StringW = LoadStringW(Library, a2, (LPWSTR)&Buffer, 0);
  if ( !StringW )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x1E,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\wpp_lib\\windowsprotectedprinthandler.cpp",
      v5);
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  std::wstring::_Construct<1,unsigned short const *>(a1, Buffer, StringW);
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&Library);
  return a1;
}

```

## disassembly

```asm
0x1800533c0  mov     [rsp+arg_0], rbx
0x1800533c5  push    rdi
0x1800533c6  sub     rsp, 30h
0x1800533ca  mov     ebx, edx
0x1800533cc  mov     rdi, rcx
0x1800533cf  xor     edx, edx; hFile
0x1800533d1  mov     r8d, 800h; dwFlags
0x1800533d7  lea     rcx, aPrintworkflows_0; "PrintWorkflowService.dll"
0x1800533de  call    cs:__imp_LoadLibraryExW
0x1800533e4  mov     [rsp+38h+arg_18], rax
0x1800533e9  mov     [rsp+38h+Buffer], 0
0x1800533f2  xor     r9d, r9d; cchBufferMax
0x1800533f5  lea     r8, [rsp+38h+Buffer]; lpBuffer
0x1800533fa  mov     edx, ebx; uID
0x1800533fc  mov     rcx, rax; hInstance
0x1800533ff  call    cs:__imp_LoadStringW
0x180053405  movsxd  r8, eax
0x180053408  mov     rcx, [rsp+38h]; this
0x18005340d  test    eax, eax
0x18005340f  jz      short loc_18005344D
0x180053411  xorps   xmm0, xmm0
0x180053414  movups  xmmword ptr [rdi], xmm0
0x180053417  mov     qword ptr [rdi+10h], 0
0x18005341f  mov     qword ptr [rdi+18h], 0
0x180053427  mov     rdx, [rsp+38h+Buffer]
0x18005342c  mov     rcx, rdi
0x18005342f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180053434  nop
0x180053435  lea     rcx, [rsp+38h+arg_18]
0x18005343a  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18005343f  mov     rax, rdi
0x180053442  mov     rbx, [rsp+38h+arg_0]
0x180053447  add     rsp, 30h
0x18005344b  pop     rdi
0x18005344c  retn
0x18005344d  lea     r8, aOnecoreuapPrin_27; "onecoreuap\\printscan\\print\\workflow"...
0x180053454  mov     edx, 1Eh; void *
0x180053459  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
