# DllInstall

- ea: `0x18000b4e0`
- end: `0x18000b50b`
- name: `DllInstall`
- size: `43`
- prototype: `HRESULT __stdcall(BOOL bInstall, PCWSTR pszCmdLine)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x18000b4e0`
- `0x18000b580`
- `0x18000b670`

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
0x18000b4e0  push    rbx
0x18000b4e2  sub     rsp, 20h
0x18000b4e6  test    ecx, ecx
0x18000b4e8  jz      short loc_18000B4FC
0x18000b4ea  call    DllRegisterServer
0x18000b4ef  mov     ebx, eax
0x18000b4f1  test    eax, eax
0x18000b4f3  jns     short loc_18000B503
0x18000b4f5  call    DllUnregisterServer
0x18000b4fa  jmp     short loc_18000B503
0x18000b4fc  call    DllUnregisterServer
0x18000b501  mov     ebx, eax
0x18000b503  mov     eax, ebx
0x18000b505  add     rsp, 20h
0x18000b509  pop     rbx
0x18000b50a  retn
```
