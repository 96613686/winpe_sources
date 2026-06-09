# DllInstall

- ea: `0x18000aea0`
- end: `0x18000aecb`
- name: `DllInstall`
- size: `43`
- prototype: `HRESULT __stdcall(BOOL bInstall, PCWSTR pszCmdLine)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x18000aea0`
- `0x18000af40`
- `0x18000b030`

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
0x18000aea0  push    rbx
0x18000aea2  sub     rsp, 20h
0x18000aea6  test    ecx, ecx
0x18000aea8  jz      short loc_18000AEBC
0x18000aeaa  call    DllRegisterServer
0x18000aeaf  mov     ebx, eax
0x18000aeb1  test    eax, eax
0x18000aeb3  jns     short loc_18000AEC3
0x18000aeb5  call    DllUnregisterServer
0x18000aeba  jmp     short loc_18000AEC3
0x18000aebc  call    DllUnregisterServer
0x18000aec1  mov     ebx, eax
0x18000aec3  mov     eax, ebx
0x18000aec5  add     rsp, 20h
0x18000aec9  pop     rbx
0x18000aeca  retn
```
