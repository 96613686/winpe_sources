# wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)

- ea: `0x180013f64`
- end: `0x180013fc9`
- name: `??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `101`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800139c8`
- `0x180013a54`
- `0x180013ae0`
- `0x180013b6c`
- `0x180027bf4`
- `0x180027c80`
- `0x180027d0c`
- `0x180027d98`

## callees

- `0x180013f64`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180013f91`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180013f91`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013fa8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013fa8`

## string_xrefs

- `0x180013f8a`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(
        __int64 *a1)
{
  __int64 v1; // rbx
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax

  v1 = *a1;
  if ( *a1 )
  {
    ProcAddress = (FARPROC)`TestClose'::`2'::s_pfnTestClose;
    if ( `TestClose'::`2'::s_pfnTestClose )
      goto LABEL_6;
    ModuleHandleW = g_tip_details_kernelbaseModuleHandle;
    if ( !g_tip_details_kernelbaseModuleHandle )
    {
      ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
      g_tip_details_kernelbaseModuleHandle = ModuleHandleW;
    }
    ProcAddress = GetProcAddress(ModuleHandleW, "TestClose");
    `TestClose'::`2'::s_pfnTestClose = (__int64)ProcAddress;
    if ( ProcAddress )
LABEL_6:
      ((void (__fastcall *)(__int64))ProcAddress)(v1);
  }
}

```

## disassembly

```asm
0x180013f64  push    rbx
0x180013f66  sub     rsp, 20h
0x180013f6a  mov     rbx, [rcx]
0x180013f6d  test    rbx, rbx
0x180013f70  jz      short loc_180013FC3
0x180013f72  mov     rax, cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x180013f79  test    rax, rax
0x180013f7c  jnz     short loc_180013FBA
0x180013f7e  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180013f85  test    rax, rax
0x180013f88  jnz     short loc_180013F9E
0x180013f8a  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180013f91  call    cs:__imp_GetModuleHandleW
0x180013f97  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180013f9e  lea     rdx, aTestclose; "TestClose"
0x180013fa5  mov     rcx, rax; hModule
0x180013fa8  call    cs:__imp_GetProcAddress
0x180013fae  mov     cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA, rax; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x180013fb5  test    rax, rax
0x180013fb8  jz      short loc_180013FC3
0x180013fba  mov     rcx, rbx
0x180013fbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fc2  nop
0x180013fc3  add     rsp, 20h
0x180013fc7  pop     rbx
0x180013fc8  retn
```
