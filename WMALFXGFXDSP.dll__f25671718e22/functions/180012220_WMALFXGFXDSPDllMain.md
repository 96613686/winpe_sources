# WMALFXGFXDSPDllMain

- ea: `0x180012220`
- end: `0x18001227f`
- name: `WMALFXGFXDSPDllMain`
- size: `95`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180012220`
- `0x1800154d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180012277`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180012277`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180012263`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180012263`

## pseudocode

```c
BOOL __stdcall WMALFXGFXDSPDllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
  {
    InitializeCriticalSection(&g_CriticalSection);
  }
  else if ( !fdwReason && !lpReserved )
  {
    DeleteCriticalSection(&g_CriticalSection);
  }
  return DllMainCRTStartup(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x180012220  mov     [rsp+arg_0], rbx
0x180012225  mov     [rsp+arg_8], rsi
0x18001222a  push    rdi
0x18001222b  sub     rsp, 20h
0x18001222f  mov     rdi, r8
0x180012232  mov     ebx, edx
0x180012234  mov     rsi, rcx
0x180012237  cmp     edx, 1
0x18001223a  jz      short loc_18001225C
0x18001223c  test    edx, edx
0x18001223e  jz      short loc_18001226B
0x180012240  mov     r8, rdi; lpvReserved
0x180012243  mov     edx, ebx; fdwReason
0x180012245  mov     rcx, rsi; hinstDLL
0x180012248  mov     rbx, [rsp+28h+arg_0]
0x18001224d  mov     rsi, [rsp+28h+arg_8]
0x180012252  add     rsp, 20h
0x180012256  pop     rdi
0x180012257  jmp     _DllMainCRTStartup
0x18001225c  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180012263  call    cs:__imp_InitializeCriticalSection
0x180012269  jmp     short loc_180012240
0x18001226b  test    rdi, rdi
0x18001226e  jnz     short loc_180012240
0x180012270  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180012277  call    cs:__imp_DeleteCriticalSection
0x18001227d  jmp     short loc_180012240
```
