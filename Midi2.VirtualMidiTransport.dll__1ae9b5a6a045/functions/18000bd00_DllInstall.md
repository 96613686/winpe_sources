# DllInstall

- ea: `0x18000bd00`
- end: `0x18000bd2b`
- name: `DllInstall`
- size: `43`
- prototype: `HRESULT __stdcall(BOOL bInstall, PCWSTR pszCmdLine)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x18000bd00`
- `0x18000bda0`
- `0x18000be90`

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
0x18000bd00  push    rbx
0x18000bd02  sub     rsp, 20h
0x18000bd06  test    ecx, ecx
0x18000bd08  jz      short loc_18000BD1C
0x18000bd0a  call    DllRegisterServer
0x18000bd0f  mov     ebx, eax
0x18000bd11  test    eax, eax
0x18000bd13  jns     short loc_18000BD23
0x18000bd15  call    DllUnregisterServer
0x18000bd1a  jmp     short loc_18000BD23
0x18000bd1c  call    DllUnregisterServer
0x18000bd21  mov     ebx, eax
0x18000bd23  mov     eax, ebx
0x18000bd25  add     rsp, 20h
0x18000bd29  pop     rbx
0x18000bd2a  retn
```
