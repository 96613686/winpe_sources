# try_cor_exit_process(uint)

- ea: `0x140014c58`
- end: `0x140014cbd`
- name: `?try_cor_exit_process@@YAXI@Z`
- size: `101`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140014b38`
- `0x140014c00`

## callees

- `0x140014c58`
- `0x1400ae030`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x140014cb0`
- `KERNEL32!FreeLibrary` at `0x140014cb0`
- `KERNEL32!GetProcAddress` at `0x140014c93`
- `KERNEL32!GetProcAddress` at `0x140014c93`
- `KERNEL32!GetModuleHandleExW` at `0x140014c7d`
- `KERNEL32!GetModuleHandleExW` at `0x140014c7d`

## string_xrefs

- `0x140014c74`: `mscoree.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x140014c58  push    rbx
0x140014c5a  sub     rsp, 30h
0x140014c5e  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x140014c67  mov     ebx, ecx
0x140014c69  and     [rsp+38h+phModule], 0
0x140014c6f  lea     r8, [rsp+38h+phModule]; phModule
0x140014c74  lea     rdx, ModuleName
0x140014c7b  xor     ecx, ecx; dwFlags
0x140014c7d  call    cs:GetModuleHandleExW
0x140014c83  mov     rcx, [rsp+38h+phModule]; hModule
0x140014c88  test    eax, eax
0x140014c8a  jz      short loc_140014CAB
0x140014c8c  lea     rdx, ProcName
0x140014c93  call    cs:GetProcAddress
0x140014c99  test    rax, rax
0x140014c9c  jz      short loc_140014CA6
0x140014c9e  mov     ecx, ebx
0x140014ca0  call    cs:__guard_dispatch_icall_fptr
0x140014ca6  mov     rcx, [rsp+38h+phModule]; hLibModule
0x140014cab  test    rcx, rcx
0x140014cae  jz      short loc_140014CB7
0x140014cb0  call    cs:FreeLibrary
0x140014cb6  nop
0x140014cb7  add     rsp, 30h
0x140014cbb  pop     rbx
0x140014cbc  retn
```
