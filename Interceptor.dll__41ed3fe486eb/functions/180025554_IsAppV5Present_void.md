# IsAppV5Present(void)

- ea: `0x180025554`
- end: `0x1800255ae`
- name: `?IsAppV5Present@@YA_NXZ`
- size: `90`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800256e0`

## callees

- `0x180025554`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180025561`
- `KERNEL32!GetModuleHandleW` at `0x180025575`
- `KERNEL32!GetModuleHandleW` at `0x180025587`
- `KERNEL32!GetModuleHandleW` at `0x180025599`
- `KERNEL32!GetModuleHandleW` at `0x180025561`
- `KERNEL32!GetModuleHandleW` at `0x180025575`
- `KERNEL32!GetModuleHandleW` at `0x180025587`
- `KERNEL32!GetModuleHandleW` at `0x180025599`

## string_xrefs

- `0x180025592`: `AppvEntSubsystems32.dll`
- `0x180025580`: `AppvEntSubsystems64.dll`
- `0x18002555a`: `AppvIsvSubsystems64.dll`
- `0x18002556e`: `AppvIsvSubsystems32.dll`

## pseudocode

```c
char IsAppV5Present(void)
{
  char v0; // bl

  v0 = 0;
  if ( GetModuleHandleW(L"AppvIsvSubsystems64.dll")
    || GetModuleHandleW(L"AppvIsvSubsystems32.dll")
    || GetModuleHandleW(L"AppvEntSubsystems64.dll")
    || GetModuleHandleW(L"AppvEntSubsystems32.dll") )
  {
    return 1;
  }
  return v0;
}

```

## disassembly

```asm
0x180025554  push    rbx
0x180025556  sub     rsp, 20h
0x18002555a  lea     rcx, ?APPV_V5_ISV_SUBSYSTEM_64@@3QB_WB; "AppvIsvSubsystems64.dll"
0x180025561  call    cs:__imp_GetModuleHandleW
0x180025567  xor     ebx, ebx
0x180025569  test    rax, rax
0x18002556c  jnz     short loc_1800255A4
0x18002556e  lea     rcx, ?APPV_V5_ISV_SUBSYSTEM_32@@3QB_WB; "AppvIsvSubsystems32.dll"
0x180025575  call    cs:__imp_GetModuleHandleW
0x18002557b  test    rax, rax
0x18002557e  jnz     short loc_1800255A4
0x180025580  lea     rcx, ?APPV_V5_ENT_SUBSYSTEM_64@@3QB_WB; "AppvEntSubsystems64.dll"
0x180025587  call    cs:__imp_GetModuleHandleW
0x18002558d  test    rax, rax
0x180025590  jnz     short loc_1800255A4
0x180025592  lea     rcx, ?APPV_V5_ENT_SUBSYSTEM_32@@3QB_WB; "AppvEntSubsystems32.dll"
0x180025599  call    cs:__imp_GetModuleHandleW
0x18002559f  test    rax, rax
0x1800255a2  jz      short loc_1800255A6
0x1800255a4  mov     bl, 1
0x1800255a6  mov     al, bl
0x1800255a8  add     rsp, 20h
0x1800255ac  pop     rbx
0x1800255ad  retn
```
