# GetResourceString(uint)

- ea: `0x18000cab8`
- end: `0x18000cb4d`
- name: `?GetResourceString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z`
- size: `149`
- prototype: `__int64 __fastcall(__int64, UINT)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18000cc58`
- `0x180012918`
- `0x180012a58`

## callees

- `0x180007cd4`
- `0x18000a700`
- `0x18000cab8`
- `0x18000f118`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000caef`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000caef`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000cace`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000cace`

## string_xrefs

- `0x18000cac7`: `PrinterCleanUpTask.dll`
- `0x18000cafe`: `printscan\print\shared\printercleanuptask\lib\util.h`

## pseudocode

```c
__int64 __fastcall GetResourceString(__int64 a1, UINT a2)
{
  int StringW; // eax
  const char *v5; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 Buffer; // [rsp+50h] [rbp+18h] BYREF
  HINSTANCE LibraryW; // [rsp+58h] [rbp+20h] BYREF

  LibraryW = LoadLibraryW(L"PrinterCleanUpTask.dll");
  Buffer = 0;
  StringW = LoadStringW(LibraryW, a2, (LPWSTR)&Buffer, 0);
  if ( !StringW )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xA,
      (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\util.h",
      v5);
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  std::wstring::_Construct<1,unsigned short const *>(a1, Buffer, StringW);
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&LibraryW);
  return a1;
}

```

## disassembly

```asm
0x18000cab8  mov     [rsp+arg_0], rbx
0x18000cabd  push    rdi
0x18000cabe  sub     rsp, 30h
0x18000cac2  mov     ebx, edx
0x18000cac4  mov     rdi, rcx
0x18000cac7  lea     rcx, aPrintercleanup_0; "PrinterCleanUpTask.dll"
0x18000cace  call    cs:__imp_LoadLibraryW
0x18000cad4  mov     [rsp+38h+arg_18], rax
0x18000cad9  mov     [rsp+38h+Buffer], 0
0x18000cae2  xor     r9d, r9d; cchBufferMax
0x18000cae5  lea     r8, [rsp+38h+Buffer]; lpBuffer
0x18000caea  mov     edx, ebx; uID
0x18000caec  mov     rcx, rax; hInstance
0x18000caef  call    cs:__imp_LoadStringW
0x18000caf5  mov     rcx, [rsp+38h]; this
0x18000cafa  test    eax, eax
0x18000cafc  jnz     short loc_18000CB0E
0x18000cafe  lea     r8, aPrintscanPrint_3; "printscan\\print\\shared\\printercleanu"...
0x18000cb05  lea     edx, [rax+0Ah]; void *
0x18000cb08  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000cb0e  xorps   xmm0, xmm0
0x18000cb11  movups  xmmword ptr [rdi], xmm0
0x18000cb14  mov     qword ptr [rdi+10h], 0
0x18000cb1c  mov     qword ptr [rdi+18h], 0
0x18000cb24  movsxd  r8, eax
0x18000cb27  mov     rdx, [rsp+38h+Buffer]
0x18000cb2c  mov     rcx, rdi
0x18000cb2f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000cb34  nop
0x18000cb35  lea     rcx, [rsp+38h+arg_18]
0x18000cb3a  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18000cb3f  mov     rax, rdi
0x18000cb42  mov     rbx, [rsp+38h+arg_0]
0x18000cb47  add     rsp, 30h
0x18000cb4b  pop     rdi
0x18000cb4c  retn
```
