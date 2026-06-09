# try_cor_exit_process(uint)

- ea: `0x40ecd7`
- end: `0x40ed2a`
- name: `?try_cor_exit_process@@YAXI@Z`
- size: `83`
- prototype: `void __cdecl(unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x40ebee`
- `0x40ec52`

## callees

- `0x407eb0`
- `0x40ecd7`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x40ecff`
- `KERNEL32!GetProcAddress` at `0x40ecff`
- `KERNEL32!FreeLibrary` at `0x40ed22`
- `KERNEL32!FreeLibrary` at `0x40ed22`
- `KERNEL32!GetModuleHandleExW` at `0x40ecec`
- `KERNEL32!GetModuleHandleExW` at `0x40ecec`

## string_xrefs

- `0x40ece5`: `mscoree.dll`

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
0x40ecd7  mov     edi, edi
0x40ecd9  push    ebp
0x40ecda  mov     ebp, esp
0x40ecdc  push    ecx
0x40ecdd  and     [ebp+phModule], 0
0x40ece1  lea     eax, [ebp+phModule]
0x40ece4  push    eax; phModule
0x40ece5  push    offset aMscoreeDll
0x40ecea  push    0; dwFlags
0x40ecec  call    ds:GetModuleHandleExW
0x40ecf2  test    eax, eax
0x40ecf4  jz      short loc_40ED19
0x40ecf6  push    esi
0x40ecf7  push    offset aCorexitprocess
0x40ecfc  push    [ebp+phModule]; hModule
0x40ecff  call    ds:GetProcAddress
0x40ed05  mov     esi, eax
0x40ed07  test    esi, esi
0x40ed09  jz      short loc_40ED18
0x40ed0b  push    [ebp+arg_0]
0x40ed0e  mov     ecx, esi
0x40ed10  call    ds:___guard_check_icall_fptr
0x40ed16  call    esi
0x40ed18  pop     esi
0x40ed19  cmp     [ebp+phModule], 0
0x40ed1d  jz      short locret_40ED28
0x40ed1f  push    [ebp+phModule]; hLibModule
0x40ed22  call    ds:FreeLibrary
0x40ed28  leave
0x40ed29  retn
```
