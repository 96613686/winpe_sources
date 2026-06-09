# try_cor_exit_process(uint)

- ea: `0x1400050e4`
- end: `0x140005148`
- name: `?try_cor_exit_process@@YAXI@Z`
- size: `100`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140004fd0`
- `0x1400050b4`

## callees

- `0x1400050e4`
- `0x14000cff0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000511f`
- `KERNEL32!GetProcAddress` at `0x14000511f`
- `KERNEL32!FreeLibrary` at `0x14000513b`
- `KERNEL32!FreeLibrary` at `0x14000513b`
- `KERNEL32!GetModuleHandleExW` at `0x140005109`
- `KERNEL32!GetModuleHandleExW` at `0x140005109`

## string_xrefs

- `0x140005100`: `mscoree.dll`

## pseudocode

```c
void __fastcall try_cor_exit_process(unsigned int a1)
{
  BOOL ModuleHandle; // eax
  HMODULE v3; // rcx
  FARPROC CorExitProcess; // rax
  HMODULE phModule; // [rsp+48h] [rbp+10h] BYREF

  phModule = 0;
  ModuleHandle = GetModuleHandleExW(0, L"mscoree.dll", &phModule);
  v3 = phModule;
  if ( ModuleHandle )
  {
    CorExitProcess = GetProcAddress(phModule, "CorExitProcess");
    if ( CorExitProcess )
      ((void (__fastcall *)(_QWORD))CorExitProcess)(a1);
    v3 = phModule;
  }
  if ( v3 )
    FreeLibrary(v3);
}

```

## disassembly

```asm
0x1400050e4  push    rbx
0x1400050e6  sub     rsp, 30h
0x1400050ea  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1400050f3  mov     ebx, ecx
0x1400050f5  and     [rsp+38h+phModule], 0
0x1400050fb  lea     r8, [rsp+38h+phModule]; phModule
0x140005100  lea     rdx, ModuleName
0x140005107  xor     ecx, ecx; dwFlags
0x140005109  call    cs:GetModuleHandleExW
0x14000510f  mov     rcx, [rsp+38h+phModule]; hModule
0x140005114  test    eax, eax
0x140005116  jz      short loc_140005136
0x140005118  lea     rdx, aCorexitprocess
0x14000511f  call    cs:GetProcAddress
0x140005125  test    rax, rax
0x140005128  jz      short loc_140005131
0x14000512a  mov     ecx, ebx
0x14000512c  call    j__guard_dispatch_icall_nop
0x140005131  mov     rcx, [rsp+38h+phModule]; hLibModule
0x140005136  test    rcx, rcx
0x140005139  jz      short loc_140005142
0x14000513b  call    cs:FreeLibrary
0x140005141  nop
0x140005142  add     rsp, 30h
0x140005146  pop     rbx
0x140005147  retn
```
