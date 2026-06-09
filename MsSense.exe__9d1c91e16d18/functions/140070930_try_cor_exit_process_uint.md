# try_cor_exit_process(uint)

- ea: `0x140070930`
- end: `0x140070994`
- name: `?try_cor_exit_process@@YAXI@Z`
- size: `100`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14007081c`
- `0x140070900`

## callees

- `0x140070930`
- `0x14007fbf0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x140070987`
- `KERNEL32!FreeLibrary` at `0x140070987`
- `KERNEL32!GetProcAddress` at `0x14007096b`
- `KERNEL32!GetProcAddress` at `0x14007096b`
- `KERNEL32!GetModuleHandleExW` at `0x140070955`
- `KERNEL32!GetModuleHandleExW` at `0x140070955`

## string_xrefs

- `0x14007094c`: `mscoree.dll`

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
0x140070930  push    rbx
0x140070932  sub     rsp, 30h
0x140070936  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x14007093f  mov     ebx, ecx
0x140070941  and     [rsp+38h+phModule], 0
0x140070947  lea     r8, [rsp+38h+phModule]; phModule
0x14007094c  lea     rdx, aMscoreeDll
0x140070953  xor     ecx, ecx; dwFlags
0x140070955  call    cs:GetModuleHandleExW
0x14007095b  mov     rcx, [rsp+38h+phModule]; hModule
0x140070960  test    eax, eax
0x140070962  jz      short loc_140070982
0x140070964  lea     rdx, aCorexitprocess
0x14007096b  call    cs:GetProcAddress
0x140070971  test    rax, rax
0x140070974  jz      short loc_14007097D
0x140070976  mov     ecx, ebx
0x140070978  call    j__guard_dispatch_icall_nop
0x14007097d  mov     rcx, [rsp+38h+phModule]; hLibModule
0x140070982  test    rcx, rcx
0x140070985  jz      short loc_14007098E
0x140070987  call    cs:FreeLibrary
0x14007098d  nop
0x14007098e  add     rsp, 30h
0x140070992  pop     rbx
0x140070993  retn
```
