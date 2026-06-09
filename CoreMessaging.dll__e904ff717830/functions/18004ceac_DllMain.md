# DllMain

- ea: `0x18004ceac`
- end: `0x18004cf40`
- name: `DllMain`
- size: `148`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting`

## callers

- `0x18009d4e4`

## callees

- `0x18004bf20`
- `0x18004c510`
- `0x18004ceac`
- `0x18004cf48`
- `0x18004cf90`
- `0x18004e148`
- `0x18005afd0`
- `0x18007cfc0`
- `0x18007d070`
- `0x180083900`
- `0x180084c60`
- `0x1800856d0`
- `0x1800860c0`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18004cef6`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18004cef6`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  __int64 v3; // rbp
  BOOL v4; // ebx
  CuiSystem$ *v5; // rcx
  unsigned int i; // edi
  __int64 v7; // rcx

  if ( fdwReason == 1 )
  {
    DisableThreadLibraryCalls(hinstDLL);
    Cn::Process::Host = (struct Cn::ICnHost *)&g_cnHost;
    Cn::Process::Initialize();
    CuiSystem$::StaticInit$(v5);
    for ( i = 0; i < 9; ++i )
    {
      v7 = (int)i;
      LOBYTE(v7) = 1;
      funcs_18004CED7[i](v7);
    }
  }
  else if ( !fdwReason )
  {
    v3 = 8;
    v4 = lpvReserved != 0;
    do
      funcs_18004CED7[v3--](0);
    while ( v3 != -1 );
    Cn::Process::Uninitialize((unsigned int)(v4 + 1));
    Cn::Process::Host = 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18004ceac  push    rbx
0x18004ceae  push    rbp
0x18004ceaf  push    rsi
0x18004ceb0  push    rdi
0x18004ceb1  sub     rsp, 28h
0x18004ceb5  cmp     edx, 1
0x18004ceb8  jz      short loc_18004CEF6
0x18004ceba  xor     edi, edi
0x18004cebc  test    edx, edx
0x18004cebe  jnz     short loc_18004CF32
0x18004cec0  neg     r8
0x18004cec3  lea     ebp, [rdi+8]
0x18004cec6  lea     rsi, funcs_18004CED7
0x18004cecd  sbb     ebx, ebx
0x18004cecf  neg     ebx
0x18004ced1  mov     rax, ds:(funcs_18004CED7 - 1800DBA50h)[rsi+rbp*8]
0x18004ced5  xor     ecx, ecx; bool
0x18004ced7  call    _guard_dispatch_icall$thunk$10345483385596137414; Microsoft::CoreUI::Registrar::RegistrarClient::InitializeClass(bool)
0x18004cedc  dec     rbp
0x18004cedf  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x18004cee3  jnz     short loc_18004CED1
0x18004cee5  lea     ecx, [rbx+1]
0x18004cee8  call    ?Uninitialize@Process@Cn@@SAXUShutdownKind@12@@Z; Cn::Process::Uninitialize(Cn::Process::ShutdownKind)
0x18004ceed  mov     cs:?Host@Process@Cn@@2PEAUICnHost@2@EA, rdi; Cn::ICnHost * Cn::Process::Host
0x18004cef4  jmp     short loc_18004CF32
0x18004cef6  call    cs:__imp_DisableThreadLibraryCalls
0x18004cefc  lea     rax, ?g_cnHost@@3VCoreUIHost@@A; CoreUIHost g_cnHost
0x18004cf03  mov     cs:?Host@Process@Cn@@2PEAUICnHost@2@EA, rax; Cn::ICnHost * Cn::Process::Host
0x18004cf0a  call    ?Initialize@Process@Cn@@SAXXZ; Cn::Process::Initialize(void)
0x18004cf0f  call    ?StaticInit$@CuiSystem$@@YA_NXZ; CuiSystem$::StaticInit$(void)
0x18004cf14  xor     edi, edi
0x18004cf16  lea     rsi, funcs_18004CED7
0x18004cf1d  movsxd  rcx, edi
0x18004cf20  mov     rax, ds:(funcs_18004CED7 - 1800DBA50h)[rsi+rcx*8]
0x18004cf24  mov     cl, 1; bool
0x18004cf26  call    _guard_dispatch_icall$thunk$10345483385596137414; Microsoft::CoreUI::Registrar::RegistrarClient::InitializeClass(bool)
0x18004cf2b  inc     edi
0x18004cf2d  cmp     edi, 9
0x18004cf30  jb      short loc_18004CF1D
0x18004cf32  mov     eax, 1
0x18004cf37  add     rsp, 28h
0x18004cf3b  pop     rdi
0x18004cf3c  pop     rsi
0x18004cf3d  pop     rbp
0x18004cf3e  pop     rbx
0x18004cf3f  retn
```
