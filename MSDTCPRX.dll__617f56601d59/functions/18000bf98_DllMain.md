# DllMain

- ea: `0x18000bf98`
- end: `0x18000c076`
- name: `DllMain`
- size: `222`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x18001d5f4`

## callees

- `0x180001008`
- `0x18000ab78`
- `0x18000bf98`
- `0x180012aa0`
- `0x18001d178`
- `0x18004eabc`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18000c05b`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18000c05b`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000bfb7`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000c010`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000bfb7`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000c010`
- `msvcrt!fclose` at `0x18000c02e`
- `msvcrt!fclose` at `0x18000c02e`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  CNameService *v5; // rsi
  REGHANDLE v7; // rcx

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      DisableThreadLibraryCalls(hinstDLL);
      qword_1800D70F0 = (__int64)hinstDLL;
      if ( !hinstDLL )
        return 0;
      sg_pCNameSvc = 0;
    }
  }
  else
  {
    v5 = sg_pCNameSvc;
    if ( sg_pCNameSvc )
    {
      CNameService::~CNameService(sg_pCNameSvc);
      operator delete(v5);
    }
  }
  if ( !(unsigned int)CmDllMain(hinstDLL, fdwReason, lpvReserved) )
    return 0;
  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      DisableThreadLibraryCalls(hinstDLL);
      SafeAllocaInitialize();
      TraceLoggingRegisterEx_EventRegister_EventSetInformation();
    }
  }
  else
  {
    if ( g_pfile )
    {
      fclose(g_pfile);
      g_pfile = 0;
    }
    v7 = RegHandle;
    dword_1800D5000 = 0;
    RegHandle = 0;
    EventUnregister(v7);
  }
  return 1;
}

```

## disassembly

```asm
0x18000bf98  mov     [rsp+arg_0], rbx
0x18000bf9d  mov     [rsp+arg_8], rsi
0x18000bfa2  push    rdi
0x18000bfa3  sub     rsp, 20h
0x18000bfa7  mov     ebx, edx
0x18000bfa9  mov     rdi, rcx
0x18000bfac  mov     eax, edx
0x18000bfae  test    edx, edx
0x18000bfb0  jz      short loc_18000BFD6
0x18000bfb2  cmp     eax, 1
0x18000bfb5  jnz     short loc_18000BFF2
0x18000bfb7  call    cs:__imp_DisableThreadLibraryCalls
0x18000bfbd  mov     cs:qword_1800D70F0, rdi
0x18000bfc4  test    rdi, rdi
0x18000bfc7  jz      short loc_18000C000
0x18000bfc9  mov     cs:?sg_pCNameSvc@@3PEAVCNameService@@EA, 0; CNameService * sg_pCNameSvc
0x18000bfd4  jmp     short loc_18000BFF2
0x18000bfd6  mov     rsi, cs:?sg_pCNameSvc@@3PEAVCNameService@@EA; CNameService * sg_pCNameSvc
0x18000bfdd  test    rsi, rsi
0x18000bfe0  jz      short loc_18000BFF2
0x18000bfe2  mov     rcx, rsi; this
0x18000bfe5  call    ??1CNameService@@QEAA@XZ; CNameService::~CNameService(void)
0x18000bfea  mov     rcx, rsi; Block
0x18000bfed  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000bff2  mov     edx, ebx; unsigned int
0x18000bff4  mov     rcx, rdi; HINSTANCE
0x18000bff7  call    ?CmDllMain@@YAHPEAUHINSTANCE__@@KPEAX@Z; CmDllMain(HINSTANCE__ *,ulong,void *)
0x18000bffc  test    eax, eax
0x18000bffe  jnz     short loc_18000C004
0x18000c000  xor     eax, eax
0x18000c002  jmp     short loc_18000C066
0x18000c004  test    ebx, ebx
0x18000c006  jz      short loc_18000C022
0x18000c008  cmp     ebx, 1
0x18000c00b  jnz     short loc_18000C061
0x18000c00d  mov     rcx, rdi; hLibModule
0x18000c010  call    cs:__imp_DisableThreadLibraryCalls
0x18000c016  call    SafeAllocaInitialize
0x18000c01b  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000c020  jmp     short loc_18000C061
0x18000c022  mov     rcx, cs:?g_pfile@@3PEAU_iobuf@@EA; Stream
0x18000c029  test    rcx, rcx
0x18000c02c  jz      short loc_18000C03F
0x18000c02e  call    cs:__imp_fclose
0x18000c034  mov     cs:?g_pfile@@3PEAU_iobuf@@EA, 0; _iobuf * g_pfile
0x18000c03f  mov     rcx, cs:RegHandle; RegHandle
0x18000c046  mov     cs:dword_1800D5000, 0
0x18000c050  mov     cs:RegHandle, 0
0x18000c05b  call    cs:__imp_EventUnregister
0x18000c061  mov     eax, 1
0x18000c066  mov     rbx, [rsp+28h+arg_0]
0x18000c06b  mov     rsi, [rsp+28h+arg_8]
0x18000c070  add     rsp, 20h
0x18000c074  pop     rdi
0x18000c075  retn
```
