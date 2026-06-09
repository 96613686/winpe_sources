# try_cor_exit_process(uint)

- ea: `0x10016340`
- end: `0x10016395`
- name: `?try_cor_exit_process@@YAXI@Z`
- size: `85`
- prototype: `void __cdecl(unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x10016255`
- `0x100162bb`

## callees

- `0x1000b035`
- `0x10016340`

## import_xrefs

- `KERNEL32!GetModuleHandleExW` at `0x10016355`
- `KERNEL32!GetModuleHandleExW` at `0x10016355`
- `KERNEL32!FreeLibrary` at `0x1001638b`
- `KERNEL32!FreeLibrary` at `0x1001638b`
- `KERNEL32!GetProcAddress` at `0x10016368`
- `KERNEL32!GetProcAddress` at `0x10016368`

## string_xrefs

- `0x1001634e`: `mscoree.dll`

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
0x10016340  mov     edi, edi
0x10016342  push    ebp
0x10016343  mov     ebp, esp
0x10016345  push    ecx
0x10016346  and     [ebp+phModule], 0
0x1001634a  lea     eax, [ebp+phModule]
0x1001634d  push    eax; phModule
0x1001634e  push    offset aMscoreeDll
0x10016353  push    0; dwFlags
0x10016355  call    ds:GetModuleHandleExW
0x1001635b  test    eax, eax
0x1001635d  jz      short loc_10016382
0x1001635f  push    esi
0x10016360  push    offset aCorexitprocess
0x10016365  push    [ebp+phModule]; hModule
0x10016368  call    ds:GetProcAddress
0x1001636e  mov     esi, eax
0x10016370  test    esi, esi
0x10016372  jz      short loc_10016381
0x10016374  push    [ebp+arg_0]
0x10016377  mov     ecx, esi
0x10016379  call    ds:___guard_check_icall_fptr
0x1001637f  call    esi
0x10016381  pop     esi
0x10016382  cmp     [ebp+phModule], 0
0x10016386  jz      short loc_10016391
0x10016388  push    [ebp+phModule]; hLibModule
0x1001638b  call    ds:FreeLibrary
0x10016391  mov     esp, ebp
0x10016393  pop     ebp
0x10016394  retn
```
