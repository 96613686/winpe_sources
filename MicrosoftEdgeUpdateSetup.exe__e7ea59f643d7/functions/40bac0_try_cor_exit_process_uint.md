# try_cor_exit_process(uint)

- ea: `0x40bac0`
- end: `0x40bb13`
- name: `?try_cor_exit_process@@YAXI@Z`
- size: `83`
- prototype: `void __cdecl(unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x40b9d7`
- `0x40ba3b`

## callees

- `0x405810`
- `0x40bac0`

## import_xrefs

- `KERNEL32!GetModuleHandleExW` at `0x40bad5`
- `KERNEL32!GetModuleHandleExW` at `0x40bad5`
- `KERNEL32!GetProcAddress` at `0x40bae8`
- `KERNEL32!GetProcAddress` at `0x40bae8`
- `KERNEL32!FreeLibrary` at `0x40bb0b`
- `KERNEL32!FreeLibrary` at `0x40bb0b`

## string_xrefs

- `0x40bace`: `mscoree.dll`

## pseudocode

```c
void __cdecl try_cor_exit_process(unsigned int a1)
{
  FARPROC CorExitProcess; // eax
  HMODULE phModule; // [esp+0h] [ebp-4h] BYREF

  phModule = 0;
  if ( GetModuleHandleExW(0, L"mscoree.dll", &phModule) )
  {
    CorExitProcess = GetProcAddress(phModule, "CorExitProcess");
    if ( CorExitProcess )
      ((void (__thiscall *)(FARPROC, unsigned int))CorExitProcess)(CorExitProcess, a1);
  }
  if ( phModule )
    FreeLibrary(phModule);
}

```

## disassembly

```asm
0x40bac0  mov     edi, edi
0x40bac2  push    ebp
0x40bac3  mov     ebp, esp
0x40bac5  push    ecx
0x40bac6  and     [ebp+phModule], 0
0x40baca  lea     eax, [ebp+phModule]
0x40bacd  push    eax; phModule
0x40bace  push    offset aMscoreeDll
0x40bad3  push    0; dwFlags
0x40bad5  call    ds:GetModuleHandleExW
0x40badb  test    eax, eax
0x40badd  jz      short loc_40BB02
0x40badf  push    esi
0x40bae0  push    offset aCorexitprocess
0x40bae5  push    [ebp+phModule]; hModule
0x40bae8  call    ds:GetProcAddress
0x40baee  mov     esi, eax
0x40baf0  test    esi, esi
0x40baf2  jz      short loc_40BB01
0x40baf4  push    [ebp+arg_0]
0x40baf7  mov     ecx, esi
0x40baf9  call    ds:___guard_check_icall_fptr
0x40baff  call    esi
0x40bb01  pop     esi
0x40bb02  cmp     [ebp+phModule], 0
0x40bb06  jz      short locret_40BB11
0x40bb08  push    [ebp+phModule]; hLibModule
0x40bb0b  call    ds:FreeLibrary
0x40bb11  leave
0x40bb12  retn
```
