# try_cor_exit_process(uint)

- ea: `0x1400186a4`
- end: `0x140018708`
- name: `?try_cor_exit_process@@YAXI@Z`
- size: `100`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140018590`
- `0x140018674`

## callees

- `0x1400186a4`
- `0x140029c10`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1400186fb`
- `KERNEL32!FreeLibrary` at `0x1400186fb`
- `KERNEL32!GetProcAddress` at `0x1400186df`
- `KERNEL32!GetProcAddress` at `0x1400186df`
- `KERNEL32!GetModuleHandleExW` at `0x1400186c9`
- `KERNEL32!GetModuleHandleExW` at `0x1400186c9`

## string_xrefs

- `0x1400186c0`: `mscoree.dll`

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
0x1400186a4  push    rbx
0x1400186a6  sub     rsp, 30h
0x1400186aa  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1400186b3  mov     ebx, ecx
0x1400186b5  and     [rsp+38h+phModule], 0
0x1400186bb  lea     r8, [rsp+38h+phModule]; phModule
0x1400186c0  lea     rdx, ModuleName
0x1400186c7  xor     ecx, ecx; dwFlags
0x1400186c9  call    cs:GetModuleHandleExW
0x1400186cf  mov     rcx, [rsp+38h+phModule]; hModule
0x1400186d4  test    eax, eax
0x1400186d6  jz      short loc_1400186F6
0x1400186d8  lea     rdx, ProcName
0x1400186df  call    cs:GetProcAddress
0x1400186e5  test    rax, rax
0x1400186e8  jz      short loc_1400186F1
0x1400186ea  mov     ecx, ebx
0x1400186ec  call    j__guard_dispatch_icall_nop
0x1400186f1  mov     rcx, [rsp+38h+phModule]; hLibModule
0x1400186f6  test    rcx, rcx
0x1400186f9  jz      short loc_140018702
0x1400186fb  call    cs:FreeLibrary
0x140018701  nop
0x140018702  add     rsp, 30h
0x140018706  pop     rbx
0x140018707  retn
```
