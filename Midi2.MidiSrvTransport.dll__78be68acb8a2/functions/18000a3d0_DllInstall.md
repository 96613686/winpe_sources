# DllInstall

- ea: `0x18000a3d0`
- end: `0x18000a3fb`
- name: `DllInstall`
- size: `43`
- prototype: `HRESULT __stdcall(BOOL bInstall, PCWSTR pszCmdLine)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x18000a3d0`
- `0x18000a470`
- `0x18000a560`

## pseudocode

```c
HRESULT __stdcall DllInstall(BOOL bInstall, PCWSTR pszCmdLine)
{
  int v2; // ebx

  if ( !bInstall )
    return DllUnregisterServer();
  v2 = DllRegisterServer();
  if ( v2 < 0 )
    DllUnregisterServer();
  return v2;
}

```

## disassembly

```asm
0x18000a3d0  push    rbx
0x18000a3d2  sub     rsp, 20h
0x18000a3d6  test    ecx, ecx
0x18000a3d8  jz      short loc_18000A3EC
0x18000a3da  call    DllRegisterServer
0x18000a3df  mov     ebx, eax
0x18000a3e1  test    eax, eax
0x18000a3e3  jns     short loc_18000A3F3
0x18000a3e5  call    DllUnregisterServer
0x18000a3ea  jmp     short loc_18000A3F3
0x18000a3ec  call    DllUnregisterServer
0x18000a3f1  mov     ebx, eax
0x18000a3f3  mov     eax, ebx
0x18000a3f5  add     rsp, 20h
0x18000a3f9  pop     rbx
0x18000a3fa  retn
```
