# DllInstall

- ea: `0x180009cc0`
- end: `0x180009ceb`
- name: `DllInstall`
- size: `43`
- prototype: `HRESULT __stdcall(BOOL bInstall, PCWSTR pszCmdLine)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x180009cc0`
- `0x180009d60`
- `0x180009e50`

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
0x180009cc0  push    rbx
0x180009cc2  sub     rsp, 20h
0x180009cc6  test    ecx, ecx
0x180009cc8  jz      short loc_180009CDC
0x180009cca  call    DllRegisterServer
0x180009ccf  mov     ebx, eax
0x180009cd1  test    eax, eax
0x180009cd3  jns     short loc_180009CE3
0x180009cd5  call    DllUnregisterServer
0x180009cda  jmp     short loc_180009CE3
0x180009cdc  call    DllUnregisterServer
0x180009ce1  mov     ebx, eax
0x180009ce3  mov     eax, ebx
0x180009ce5  add     rsp, 20h
0x180009ce9  pop     rbx
0x180009cea  retn
```
