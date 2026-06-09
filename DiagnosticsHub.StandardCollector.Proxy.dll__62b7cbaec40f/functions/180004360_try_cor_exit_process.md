# try_cor_exit_process

- ea: `0x180004360`
- end: `0x1800043c4`
- name: `try_cor_exit_process`
- size: `100`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800041c8`
- `0x1800042ac`

## callees

- `0x180004360`
- `0x180060430`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1800043b7`
- `KERNEL32!FreeLibrary` at `0x1800043b7`
- `KERNEL32!GetModuleHandleExW` at `0x180004385`
- `KERNEL32!GetModuleHandleExW` at `0x180004385`
- `KERNEL32!GetProcAddress` at `0x18000439b`
- `KERNEL32!GetProcAddress` at `0x18000439b`

## string_xrefs

- `0x18000437c`: `mscoree.dll`

## pseudocode

```c
int __fastcall try_cor_exit_process(unsigned int a1)
{
  FARPROC ProcAddress; // rax
  HMODULE v3; // rcx
  HMODULE phModule; // [rsp+48h] [rbp+10h] BYREF

  phModule = 0;
  LODWORD(ProcAddress) = GetModuleHandleExW(0, L"mscoree.dll", &phModule);
  v3 = phModule;
  if ( (_DWORD)ProcAddress )
  {
    ProcAddress = GetProcAddress(phModule, "CorExitProcess");
    if ( ProcAddress )
      LODWORD(ProcAddress) = ((__int64 (__fastcall *)(_QWORD))ProcAddress)(a1);
    v3 = phModule;
  }
  if ( v3 )
    LODWORD(ProcAddress) = FreeLibrary(v3);
  return (int)ProcAddress;
}

```

## disassembly

```asm
0x180004360  push    rbx
0x180004362  sub     rsp, 30h
0x180004366  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000436f  mov     ebx, ecx
0x180004371  and     [rsp+38h+phModule], 0
0x180004377  lea     r8, [rsp+38h+phModule]; phModule
0x18000437c  lea     rdx, ModuleName; "mscoree.dll"
0x180004383  xor     ecx, ecx; dwFlags
0x180004385  call    cs:__imp_GetModuleHandleExW
0x18000438b  mov     rcx, [rsp+38h+phModule]; hModule
0x180004390  test    eax, eax
0x180004392  jz      short loc_1800043B2
0x180004394  lea     rdx, ProcName; "CorExitProcess"
0x18000439b  call    cs:__imp_GetProcAddress
0x1800043a1  test    rax, rax
0x1800043a4  jz      short loc_1800043AD
0x1800043a6  mov     ecx, ebx
0x1800043a8  call    _guard_dispatch_icall
0x1800043ad  mov     rcx, [rsp+38h+phModule]; hLibModule
0x1800043b2  test    rcx, rcx
0x1800043b5  jz      short loc_1800043BE
0x1800043b7  call    cs:__imp_FreeLibrary
0x1800043bd  nop
0x1800043be  add     rsp, 30h
0x1800043c2  pop     rbx
0x1800043c3  retn
```
