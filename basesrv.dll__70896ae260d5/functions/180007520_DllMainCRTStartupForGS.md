# _DllMainCRTStartupForGS

- ea: `0x180007520`
- end: `0x180007547`
- name: `_DllMainCRTStartupForGS`
- size: `39`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007520`
- `0x1800077a4`

## import_xrefs

- `ntdll!LdrDisableThreadCalloutsForDll` at `0x180007536`
- `ntdll!LdrDisableThreadCalloutsForDll` at `0x180007536`

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
0x180007520  push    rbx
0x180007522  sub     rsp, 20h
0x180007526  mov     rbx, rcx
0x180007529  cmp     edx, 1
0x18000752c  jnz     short loc_18000753C
0x18000752e  call    __security_init_cookie
0x180007533  mov     rcx, rbx; BaseAddress
0x180007536  call    cs:__imp_LdrDisableThreadCalloutsForDll
0x18000753c  mov     eax, 1
0x180007541  add     rsp, 20h
0x180007545  pop     rbx
0x180007546  retn
```
