# TestReport

- ea: `0x18000c430`
- end: `0x18000c496`
- name: `TestReport`
- size: `102`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000b7c0`

## callees

- `0x18000c430`
- `0x18001cdf0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000c46f`
- `KERNEL32!GetProcAddress` at `0x18000c46f`
- `KERNEL32!GetModuleHandleW` at `0x18000c458`
- `KERNEL32!GetModuleHandleW` at `0x18000c458`

## string_xrefs

- `0x18000c451`: `kernelbase.dll`

## pseudocode

```c
FARPROC __fastcall TestReport(__int64 a1)
{
  FARPROC result; // rax
  HMODULE ModuleHandleW; // rax

  result = (FARPROC)`TestReport'::`2'::s_pfnTestReport;
  if ( `TestReport'::`2'::s_pfnTestReport )
    return (FARPROC)((__int64 (__fastcall *)(__int64))result)(a1);
  ModuleHandleW = g_tip_details_kernelbaseModuleHandle;
  if ( !g_tip_details_kernelbaseModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
    g_tip_details_kernelbaseModuleHandle = ModuleHandleW;
  }
  result = GetProcAddress(ModuleHandleW, "TestReport");
  `TestReport'::`2'::s_pfnTestReport = (__int64)result;
  if ( result )
    return (FARPROC)((__int64 (__fastcall *)(__int64))result)(a1);
  return result;
}

```

## disassembly

```asm
0x18000c430  push    rbx
0x18000c432  sub     rsp, 20h
0x18000c436  mov     rax, cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x18000c43d  mov     rbx, rcx
0x18000c440  test    rax, rax
0x18000c443  jnz     short loc_18000C481
0x18000c445  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18000c44c  test    rax, rax
0x18000c44f  jnz     short loc_18000C465
0x18000c451  lea     rcx, ModuleName; "kernelbase.dll"
0x18000c458  call    cs:__imp_GetModuleHandleW
0x18000c45e  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18000c465  lea     rdx, aTestreport; "TestReport"
0x18000c46c  mov     rcx, rax; hModule
0x18000c46f  call    cs:__imp_GetProcAddress
0x18000c475  mov     cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA, rax; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x18000c47c  test    rax, rax
0x18000c47f  jz      short loc_18000C490
0x18000c481  mov     rcx, rbx
0x18000c484  add     rsp, 20h
0x18000c488  pop     rbx
0x18000c489  jmp     cs:__guard_dispatch_icall_fptr
0x18000c490  add     rsp, 20h
0x18000c494  pop     rbx
0x18000c495  retn
```
