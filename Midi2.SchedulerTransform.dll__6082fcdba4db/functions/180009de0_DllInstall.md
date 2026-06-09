# DllInstall

- ea: `0x180009de0`
- end: `0x180009e0b`
- name: `DllInstall`
- size: `43`
- prototype: `HRESULT __stdcall(BOOL bInstall, PCWSTR pszCmdLine)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x180009de0`
- `0x180009e80`
- `0x180009f70`

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
0x180009de0  push    rbx
0x180009de2  sub     rsp, 20h
0x180009de6  test    ecx, ecx
0x180009de8  jz      short loc_180009DFC
0x180009dea  call    DllRegisterServer
0x180009def  mov     ebx, eax
0x180009df1  test    eax, eax
0x180009df3  jns     short loc_180009E03
0x180009df5  call    DllUnregisterServer
0x180009dfa  jmp     short loc_180009E03
0x180009dfc  call    DllUnregisterServer
0x180009e01  mov     ebx, eax
0x180009e03  mov     eax, ebx
0x180009e05  add     rsp, 20h
0x180009e09  pop     rbx
0x180009e0a  retn
```
