# DllInstall

- ea: `0x180009c30`
- end: `0x180009c5b`
- name: `DllInstall`
- size: `43`
- prototype: `HRESULT __stdcall(BOOL bInstall, PCWSTR pszCmdLine)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x180009c30`
- `0x180009cd0`
- `0x180009dc0`

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
0x180009c30  push    rbx
0x180009c32  sub     rsp, 20h
0x180009c36  test    ecx, ecx
0x180009c38  jz      short loc_180009C4C
0x180009c3a  call    DllRegisterServer
0x180009c3f  mov     ebx, eax
0x180009c41  test    eax, eax
0x180009c43  jns     short loc_180009C53
0x180009c45  call    DllUnregisterServer
0x180009c4a  jmp     short loc_180009C53
0x180009c4c  call    DllUnregisterServer
0x180009c51  mov     ebx, eax
0x180009c53  mov     eax, ebx
0x180009c55  add     rsp, 20h
0x180009c59  pop     rbx
0x180009c5a  retn
```
