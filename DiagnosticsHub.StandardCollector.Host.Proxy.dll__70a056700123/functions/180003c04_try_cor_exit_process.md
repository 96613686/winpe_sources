# try_cor_exit_process

- ea: `0x180003c04`
- end: `0x180003c68`
- name: `try_cor_exit_process`
- size: `100`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003a6c`
- `0x180003b50`

## callees

- `0x180003c04`
- `0x180060150`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180003c5b`
- `KERNEL32!FreeLibrary` at `0x180003c5b`
- `KERNEL32!GetModuleHandleExW` at `0x180003c29`
- `KERNEL32!GetModuleHandleExW` at `0x180003c29`
- `KERNEL32!GetProcAddress` at `0x180003c3f`
- `KERNEL32!GetProcAddress` at `0x180003c3f`

## string_xrefs

- `0x180003c20`: `mscoree.dll`

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
0x180003c04  push    rbx
0x180003c06  sub     rsp, 30h
0x180003c0a  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180003c13  mov     ebx, ecx
0x180003c15  and     [rsp+38h+phModule], 0
0x180003c1b  lea     r8, [rsp+38h+phModule]; phModule
0x180003c20  lea     rdx, ModuleName; "mscoree.dll"
0x180003c27  xor     ecx, ecx; dwFlags
0x180003c29  call    cs:__imp_GetModuleHandleExW
0x180003c2f  mov     rcx, [rsp+38h+phModule]; hModule
0x180003c34  test    eax, eax
0x180003c36  jz      short loc_180003C56
0x180003c38  lea     rdx, ProcName; "CorExitProcess"
0x180003c3f  call    cs:__imp_GetProcAddress
0x180003c45  test    rax, rax
0x180003c48  jz      short loc_180003C51
0x180003c4a  mov     ecx, ebx
0x180003c4c  call    _guard_dispatch_icall
0x180003c51  mov     rcx, [rsp+38h+phModule]; hLibModule
0x180003c56  test    rcx, rcx
0x180003c59  jz      short loc_180003C62
0x180003c5b  call    cs:__imp_FreeLibrary
0x180003c61  nop
0x180003c62  add     rsp, 30h
0x180003c66  pop     rbx
0x180003c67  retn
```
