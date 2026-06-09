# DllEntryPoint

- ea: `0x10010a51`
- end: `0x10010a74`
- name: `DllEntryPoint`
- size: `35`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x10010920`
- `0x10010a51`
- `0x10010c7b`

## pseudocode

```c
BOOL __stdcall DllEntryPoint(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    __security_init_cookie();
  return dllmain_dispatch(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x10010a51  push    ebp
0x10010a52  mov     ebp, esp
0x10010a54  cmp     [ebp+fdwReason], 1
0x10010a58  jnz     short loc_10010A5F
0x10010a5a  call    ___security_init_cookie
0x10010a5f  push    [ebp+lpReserved]; lpvReserved
0x10010a62  push    [ebp+fdwReason]; fdwReason
0x10010a65  push    [ebp+hinstDLL]; hinstDLL
0x10010a68  call    ?dllmain_dispatch@@YAHQAUHINSTANCE__@@KQAX@Z
0x10010a6d  add     esp, 0Ch
0x10010a70  pop     ebp
0x10010a71  retn    0Ch
```
