# try_cor_exit_process

- ea: `0x140012ca4`
- end: `0x140012d08`
- name: `try_cor_exit_process`
- size: `100`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140012b90`
- `0x140012c74`

## callees

- `0x140012ca4`
- `0x140024c80`

## import_xrefs

- `KERNEL32!GetModuleHandleExW` at `0x140012cc9`
- `KERNEL32!GetModuleHandleExW` at `0x140012cc9`
- `KERNEL32!GetProcAddress` at `0x140012cdf`
- `KERNEL32!GetProcAddress` at `0x140012cdf`
- `KERNEL32!FreeLibrary` at `0x140012cfb`
- `KERNEL32!FreeLibrary` at `0x140012cfb`

## string_xrefs

- `0x140012cc0`: `mscoree.dll`

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
0x140012ca4  push    rbx
0x140012ca6  sub     rsp, 30h
0x140012caa  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x140012cb3  mov     ebx, ecx
0x140012cb5  and     [rsp+38h+phModule], 0
0x140012cbb  lea     r8, [rsp+38h+phModule]; phModule
0x140012cc0  lea     rdx, aMscoreeDll
0x140012cc7  xor     ecx, ecx; dwFlags
0x140012cc9  call    cs:__imp_GetModuleHandleExW
0x140012ccf  mov     rcx, [rsp+38h+phModule]; hModule
0x140012cd4  test    eax, eax
0x140012cd6  jz      short loc_140012CF6
0x140012cd8  lea     rdx, aCorexitprocess
0x140012cdf  call    cs:__imp_GetProcAddress
0x140012ce5  test    rax, rax
0x140012ce8  jz      short loc_140012CF1
0x140012cea  mov     ecx, ebx
0x140012cec  call    _guard_dispatch_icall
0x140012cf1  mov     rcx, [rsp+38h+phModule]; hLibModule
0x140012cf6  test    rcx, rcx
0x140012cf9  jz      short loc_140012D02
0x140012cfb  call    cs:__imp_FreeLibrary
0x140012d01  nop
0x140012d02  add     rsp, 30h
0x140012d06  pop     rbx
0x140012d07  retn
```
