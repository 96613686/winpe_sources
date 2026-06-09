# _DllMainCRTStartupForGS

- ea: `0x180007820`
- end: `0x180007847`
- name: `_DllMainCRTStartupForGS`
- size: `39`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007820`
- `0x180007aa8`

## import_xrefs

- `ntdll!LdrDisableThreadCalloutsForDll` at `0x180007836`
- `ntdll!LdrDisableThreadCalloutsForDll` at `0x180007836`

## pseudocode

```c
BOOL __stdcall DllMainCRTStartupForGS(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
  {
    _security_init_cookie();
    LdrDisableThreadCalloutsForDll(hinstDLL);
  }
  return 1;
}

```

## disassembly

```asm
0x180007820  push    rbx
0x180007822  sub     rsp, 20h
0x180007826  mov     rbx, rcx
0x180007829  cmp     edx, 1
0x18000782c  jnz     short loc_18000783C
0x18000782e  call    __security_init_cookie
0x180007833  mov     rcx, rbx; BaseAddress
0x180007836  call    cs:__imp_LdrDisableThreadCalloutsForDll
0x18000783c  mov     eax, 1
0x180007841  add     rsp, 20h
0x180007845  pop     rbx
0x180007846  retn
```
