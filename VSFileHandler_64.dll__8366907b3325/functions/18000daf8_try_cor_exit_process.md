# try_cor_exit_process

- ea: `0x18000daf8`
- end: `0x18000db53`
- name: `try_cor_exit_process`
- size: `91`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000d9f0`
- `0x18000daac`

## callees

- `0x18000daf8`
- `0x1800241c0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18000db47`
- `KERNEL32!FreeLibrary` at `0x18000db47`
- `KERNEL32!GetProcAddress` at `0x18000db2a`
- `KERNEL32!GetProcAddress` at `0x18000db2a`
- `KERNEL32!GetModuleHandleExW` at `0x18000db14`
- `KERNEL32!GetModuleHandleExW` at `0x18000db14`

## string_xrefs

- `0x18000db0b`: `mscoree.dll`

## pseudocode

```c
int __fastcall try_cor_exit_process(unsigned int a1)
{
  FARPROC ProcAddress; // rax
  HMODULE phModule; // [rsp+38h] [rbp+10h] BYREF

  phModule = 0;
  LODWORD(ProcAddress) = GetModuleHandleExW(0, L"mscoree.dll", &phModule);
  if ( (_DWORD)ProcAddress )
  {
    ProcAddress = GetProcAddress(phModule, "CorExitProcess");
    if ( ProcAddress )
      LODWORD(ProcAddress) = ((__int64 (__fastcall *)(_QWORD))ProcAddress)(a1);
  }
  if ( phModule )
    LODWORD(ProcAddress) = FreeLibrary(phModule);
  return (int)ProcAddress;
}

```

## disassembly

```asm
0x18000daf8  push    rbx
0x18000dafa  sub     rsp, 20h
0x18000dafe  and     [rsp+28h+phModule], 0
0x18000db04  lea     r8, [rsp+28h+phModule]; phModule
0x18000db09  mov     ebx, ecx
0x18000db0b  lea     rdx, aMscoreeDll; "mscoree.dll"
0x18000db12  xor     ecx, ecx; dwFlags
0x18000db14  call    cs:__imp_GetModuleHandleExW
0x18000db1a  test    eax, eax
0x18000db1c  jz      short loc_18000DB3D
0x18000db1e  mov     rcx, [rsp+28h+phModule]; hModule
0x18000db23  lea     rdx, aCorexitprocess; "CorExitProcess"
0x18000db2a  call    cs:__imp_GetProcAddress
0x18000db30  test    rax, rax
0x18000db33  jz      short loc_18000DB3D
0x18000db35  mov     ecx, ebx
0x18000db37  call    cs:__guard_dispatch_icall_fptr
0x18000db3d  mov     rcx, [rsp+28h+phModule]; hLibModule
0x18000db42  test    rcx, rcx
0x18000db45  jz      short loc_18000DB4D
0x18000db47  call    cs:__imp_FreeLibrary
0x18000db4d  add     rsp, 20h
0x18000db51  pop     rbx
0x18000db52  retn
```
