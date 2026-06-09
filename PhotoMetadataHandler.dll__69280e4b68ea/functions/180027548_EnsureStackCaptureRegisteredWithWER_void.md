# EnsureStackCaptureRegisteredWithWER(void)

- ea: `0x180027548`
- end: `0x1800275c1`
- name: `?EnsureStackCaptureRegisteredWithWER@@YAXXZ`
- size: `121`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800132ec`

## callees

- `0x180027548`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180027581`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180027581`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180027566`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180027566`

## string_xrefs

- `0x18002755f`: `kernel32.dll`

## pseudocode

```c
void EnsureStackCaptureRegisteredWithWER(void)
{
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  void (__fastcall *v2)(volatile int *, __int64); // rbx

  if ( !_InterlockedCompareExchange(&dword_18009A344, 1, 0) )
  {
    ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
    if ( ModuleHandleW )
    {
      ProcAddress = GetProcAddress(ModuleHandleW, "WerRegisterMemoryBlock");
      v2 = (void (__fastcall *)(volatile int *, __int64))ProcAddress;
      if ( ProcAddress )
      {
        ((void (__fastcall *)(__int64, __int64))ProcAddress)(qword_18009A378, 10240);
        v2(&g_nCurrentStackCaptureIndex, 4);
      }
    }
  }
}

```

## disassembly

```asm
0x180027548  push    rbx
0x18002754a  sub     rsp, 20h
0x18002754e  mov     ecx, 1
0x180027553  xor     eax, eax
0x180027555  lock cmpxchg cs:dword_18009A344, ecx
0x18002755d  jnz     short loc_1800275BA
0x18002755f  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180027566  call    cs:__imp_GetModuleHandleW
0x18002756d  nop     dword ptr [rax+rax+00h]
0x180027572  test    rax, rax
0x180027575  jz      short loc_1800275BA
0x180027577  lea     rdx, aWerregistermem; "WerRegisterMemoryBlock"
0x18002757e  mov     rcx, rax; hModule
0x180027581  call    cs:__imp_GetProcAddress
0x180027588  nop     dword ptr [rax+rax+00h]
0x18002758d  mov     rbx, rax
0x180027590  test    rax, rax
0x180027593  jz      short loc_1800275BA
0x180027595  mov     rcx, cs:qword_18009A378
0x18002759c  mov     edx, 2800h
0x1800275a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800275a6  mov     edx, 4
0x1800275ab  lea     rcx, ?g_nCurrentStackCaptureIndex@@3JC; long volatile g_nCurrentStackCaptureIndex
0x1800275b2  mov     rax, rbx
0x1800275b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800275ba  add     rsp, 20h
0x1800275be  pop     rbx
0x1800275bf  retn
```
