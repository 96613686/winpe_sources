# try_cor_exit_process(uint)

- ea: `0x41085d`
- end: `0x4108b0`
- name: `?try_cor_exit_process@@YAXI@Z`
- size: `83`
- prototype: `void __cdecl(unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x410774`
- `0x4107d8`

## callees

- `0x402330`
- `0x41085d`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x410885`
- `KERNEL32!GetProcAddress` at `0x410885`
- `KERNEL32!FreeLibrary` at `0x4108a8`
- `KERNEL32!FreeLibrary` at `0x4108a8`
- `KERNEL32!GetModuleHandleExW` at `0x410872`
- `KERNEL32!GetModuleHandleExW` at `0x410872`

## string_xrefs

- `0x41086b`: `mscoree.dll`

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
0x41085d  mov     edi, edi
0x41085f  push    ebp
0x410860  mov     ebp, esp
0x410862  push    ecx
0x410863  and     [ebp+phModule], 0
0x410867  lea     eax, [ebp+phModule]
0x41086a  push    eax; phModule
0x41086b  push    offset aMscoreeDll
0x410870  push    0; dwFlags
0x410872  call    ds:GetModuleHandleExW
0x410878  test    eax, eax
0x41087a  jz      short loc_41089F
0x41087c  push    esi
0x41087d  push    offset aCorexitprocess
0x410882  push    [ebp+phModule]; hModule
0x410885  call    ds:GetProcAddress
0x41088b  mov     esi, eax
0x41088d  test    esi, esi
0x41088f  jz      short loc_41089E
0x410891  push    [ebp+arg_0]
0x410894  mov     ecx, esi
0x410896  call    ds:___guard_check_icall_fptr
0x41089c  call    esi
0x41089e  pop     esi
0x41089f  cmp     [ebp+phModule], 0
0x4108a3  jz      short locret_4108AE
0x4108a5  push    [ebp+phModule]; hLibModule
0x4108a8  call    ds:FreeLibrary
0x4108ae  leave
0x4108af  retn
```
