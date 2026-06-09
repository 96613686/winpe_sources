# TestClose

- ea: `0x18000dfa0`
- end: `0x18000e006`
- name: `TestClose`
- size: `102`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180009e10`
- `0x18000a930`

## callees

- `0x18000dfa0`
- `0x18001cdf0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000dfdf`
- `KERNEL32!GetProcAddress` at `0x18000dfdf`
- `KERNEL32!GetModuleHandleW` at `0x18000dfc8`
- `KERNEL32!GetModuleHandleW` at `0x18000dfc8`

## string_xrefs

- `0x18000dfc1`: `kernelbase.dll`

## pseudocode

```c
FARPROC __fastcall TestClose(__int64 a1)
{
  FARPROC result; // rax
  HMODULE ModuleHandleW; // rax

  result = (FARPROC)`TestClose'::`2'::s_pfnTestClose;
  if ( `TestClose'::`2'::s_pfnTestClose )
    return (FARPROC)((__int64 (__fastcall *)(__int64))result)(a1);
  ModuleHandleW = g_tip_details_kernelbaseModuleHandle;
  if ( !g_tip_details_kernelbaseModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
    g_tip_details_kernelbaseModuleHandle = ModuleHandleW;
  }
  result = GetProcAddress(ModuleHandleW, "TestClose");
  `TestClose'::`2'::s_pfnTestClose = (__int64)result;
  if ( result )
    return (FARPROC)((__int64 (__fastcall *)(__int64))result)(a1);
  return result;
}

```

## disassembly

```asm
0x18000dfa0  push    rbx
0x18000dfa2  sub     rsp, 20h
0x18000dfa6  mov     rax, cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x18000dfad  mov     rbx, rcx
0x18000dfb0  test    rax, rax
0x18000dfb3  jnz     short loc_18000DFF1
0x18000dfb5  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18000dfbc  test    rax, rax
0x18000dfbf  jnz     short loc_18000DFD5
0x18000dfc1  lea     rcx, ModuleName; "kernelbase.dll"
0x18000dfc8  call    cs:__imp_GetModuleHandleW
0x18000dfce  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18000dfd5  lea     rdx, aTestclose; "TestClose"
0x18000dfdc  mov     rcx, rax; hModule
0x18000dfdf  call    cs:__imp_GetProcAddress
0x18000dfe5  mov     cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA, rax; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x18000dfec  test    rax, rax
0x18000dfef  jz      short loc_18000E000
0x18000dff1  mov     rcx, rbx
0x18000dff4  add     rsp, 20h
0x18000dff8  pop     rbx
0x18000dff9  jmp     cs:__guard_dispatch_icall_fptr
0x18000e000  add     rsp, 20h
0x18000e004  pop     rbx
0x18000e005  retn
```
