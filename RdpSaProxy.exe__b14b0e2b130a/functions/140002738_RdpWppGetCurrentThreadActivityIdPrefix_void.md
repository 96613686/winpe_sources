# RdpWppGetCurrentThreadActivityIdPrefix(void)

- ea: `0x140002738`
- end: `0x1400027c6`
- name: `?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ`
- size: `142`
- prototype: `__int64(void)`
- caller_count: `17`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140002578`
- `0x140002944`
- `0x140002f60`
- `0x1400032f0`
- `0x1400035d8`
- `0x1400039e0`
- `0x140003c20`
- `0x140003d90`
- `0x140003ef4`
- `0x140004240`
- `0x140004370`
- `0x140004590`
- `0x140004750`
- `0x14000499c`
- `0x140004c0c`
- `0x140005058`
- `0x1400054f0`

## callees

- `0x140002738`
- `0x1400056f0`
- `0x140006010`

## import_xrefs

- `KERNEL32!GetModuleHandleExA` at `0x140002775`
- `KERNEL32!GetModuleHandleExA` at `0x140002775`
- `KERNEL32!GetProcAddress` at `0x14000278b`
- `KERNEL32!GetProcAddress` at `0x14000278b`
- `KERNEL32!FreeLibrary` at `0x1400027aa`
- `KERNEL32!FreeLibrary` at `0x1400027aa`

## string_xrefs

- `0x140002760`: `Advapi32.dll`

## pseudocode

```c
__int64 RdpWppGetCurrentThreadActivityIdPrefix(void)
{
  FARPROC ProcAddress; // rax
  HMODULE phModule; // [rsp+20h] [rbp-28h] BYREF
  unsigned int v3; // [rsp+28h] [rbp-20h] BYREF
  __int64 v4; // [rsp+2Ch] [rbp-1Ch]
  int v5; // [rsp+34h] [rbp-14h]

  phModule = 0;
  v4 = 0;
  v5 = 0;
  v3 = -186580992;
  if ( GetModuleHandleExA(0, "Advapi32.dll", &phModule) )
  {
    ProcAddress = GetProcAddress(phModule, "EventActivityIdControl");
    if ( ProcAddress )
      ((void (__fastcall *)(__int64, unsigned int *))ProcAddress)(1, &v3);
    FreeLibrary(phModule);
  }
  return v3;
}

```

## disassembly

```asm
0x140002738  sub     rsp, 48h
0x14000273c  mov     rax, cs:__security_cookie
0x140002743  xor     rax, rsp
0x140002746  mov     [rsp+48h+var_10], rax
0x14000274b  xor     eax, eax
0x14000274d  mov     [rsp+48h+phModule], 0
0x140002756  lea     r8, [rsp+48h+phModule]; phModule
0x14000275b  mov     [rsp+48h+var_1C], rax
0x140002760  lea     rdx, ModuleName; "Advapi32.dll"
0x140002767  mov     [rsp+48h+var_14], eax
0x14000276b  xor     ecx, ecx; dwFlags
0x14000276d  mov     [rsp+48h+var_20], 0F4E10000h
0x140002775  call    cs:__imp_GetModuleHandleExA
0x14000277b  test    eax, eax
0x14000277d  jz      short loc_1400027B0
0x14000277f  mov     rcx, [rsp+48h+phModule]; hModule
0x140002784  lea     rdx, ProcName; "EventActivityIdControl"
0x14000278b  call    cs:__imp_GetProcAddress
0x140002791  test    rax, rax
0x140002794  jz      short loc_1400027A5
0x140002796  lea     rdx, [rsp+48h+var_20]
0x14000279b  mov     ecx, 1
0x1400027a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400027a5  mov     rcx, [rsp+48h+phModule]; hLibModule
0x1400027aa  call    cs:__imp_FreeLibrary
0x1400027b0  mov     eax, [rsp+48h+var_20]
0x1400027b4  mov     rcx, [rsp+48h+var_10]
0x1400027b9  xor     rcx, rsp; StackCookie
0x1400027bc  call    __security_check_cookie
0x1400027c1  add     rsp, 48h
0x1400027c5  retn
```
