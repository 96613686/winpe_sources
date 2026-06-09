# __FC_Query_Config

- ea: `0x18001d164`
- end: `0x18001d1ca`
- name: `__FC_Query_Config`
- size: `102`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180017388`
- `0x180017444`

## callees

- `0x180018288`
- `0x18001d164`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d195`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d195`

## string_xrefs

- `0x18001d18e`: `__FC_Query_Config`

## pseudocode

```c
__int64 __fastcall _FC_Query_Config(unsigned int a1, unsigned int a2, __int64 a3)
{
  FARPROC ProcAddress; // rax
  HMODULE HostModuleHandle; // rax

  ProcAddress = (FARPROC)`__FC_Query_Config'::`2'::s_pfnQueryConfig;
  if ( `__FC_Query_Config'::`2'::s_pfnQueryConfig )
    return ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))ProcAddress)(a1, a2, a3);
  HostModuleHandle = fc_details_GetHostModuleHandle();
  ProcAddress = GetProcAddress(HostModuleHandle, "__FC_Query_Config");
  `__FC_Query_Config'::`2'::s_pfnQueryConfig = (__int64)ProcAddress;
  if ( ProcAddress )
    return ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))ProcAddress)(a1, a2, a3);
  else
    return 2147500033LL;
}

```

## disassembly

```asm
0x18001d164  mov     [rsp+arg_0], rbx
0x18001d169  mov     [rsp+arg_8], rsi
0x18001d16e  push    rdi
0x18001d16f  sub     rsp, 20h
0x18001d173  mov     rax, cs:?s_pfnQueryConfig@?1??__FC_Query_Config@@9@4P6AJIW4__FC_Query_Flags@@PEAU__FC_Config_Info@@@ZEA; long (*`__FC_Query_Config'::`2'::s_pfnQueryConfig)(uint,__FC_Query_Flags,__FC_Config_Info *)
0x18001d17a  mov     rbx, r8
0x18001d17d  mov     edi, edx
0x18001d17f  mov     esi, ecx
0x18001d181  test    rax, rax
0x18001d184  jnz     short loc_18001D1AE
0x18001d186  call    ?fc_details_GetHostModuleHandle@@YAPEAUHINSTANCE__@@XZ; fc_details_GetHostModuleHandle(void)
0x18001d18b  mov     rcx, rax; hModule
0x18001d18e  lea     rdx, aFcQueryConfig; "__FC_Query_Config"
0x18001d195  call    cs:__imp_GetProcAddress
0x18001d19b  mov     cs:?s_pfnQueryConfig@?1??__FC_Query_Config@@9@4P6AJIW4__FC_Query_Flags@@PEAU__FC_Config_Info@@@ZEA, rax; long (*`__FC_Query_Config'::`2'::s_pfnQueryConfig)(uint,__FC_Query_Flags,__FC_Config_Info *)
0x18001d1a2  test    rax, rax
0x18001d1a5  jnz     short loc_18001D1AE
0x18001d1a7  mov     eax, 80004001h
0x18001d1ac  jmp     short loc_18001D1BA
0x18001d1ae  mov     r8, rbx
0x18001d1b1  mov     edx, edi
0x18001d1b3  mov     ecx, esi
0x18001d1b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1ba  mov     rbx, [rsp+28h+arg_0]
0x18001d1bf  mov     rsi, [rsp+28h+arg_8]
0x18001d1c4  add     rsp, 20h
0x18001d1c8  pop     rdi
0x18001d1c9  retn
```
