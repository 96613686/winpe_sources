# _DllMainCRTStartup

- ea: `0x100468eec`
- end: `0x100468f29`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x100468db4`
- `0x100468eec`
- `0x1004694d0`

## pseudocode

```c
BOOL __stdcall DllMainCRTStartup(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    _security_init_cookie();
  return dllmain_dispatch(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x100468eec  mov     [rsp+arg_0], rbx
0x100468ef1  mov     [rsp+arg_8], rsi
0x100468ef6  push    rdi
0x100468ef7  sub     rsp, 20h
0x100468efb  mov     rdi, r8
0x100468efe  mov     ebx, edx
0x100468f00  mov     rsi, rcx
0x100468f03  cmp     edx, 1
0x100468f06  jnz     short loc_100468F0D
0x100468f08  call    __security_init_cookie
0x100468f0d  mov     r8, rdi; lpvReserved
0x100468f10  mov     edx, ebx; fdwReason
0x100468f12  mov     rcx, rsi; hinstDLL
0x100468f15  mov     rbx, [rsp+28h+arg_0]
0x100468f1a  mov     rsi, [rsp+28h+arg_8]
0x100468f1f  add     rsp, 20h
0x100468f23  pop     rdi
0x100468f24  jmp     dllmain_dispatch
```
