# EnsureStackCaptureRegisteredWithWER(void)

- ea: `0x1800228b8`
- end: `0x180022924`
- name: `?EnsureStackCaptureRegisteredWithWER@@YAXXZ`
- size: `108`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001d128`

## callees

- `0x1800228b8`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800228eb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800228eb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800228d6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800228d6`

## string_xrefs

- `0x1800228cf`: `kernel32.dll`

## pseudocode

```c
void EnsureStackCaptureRegisteredWithWER(void)
{
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  void (__fastcall *v2)(volatile int *, __int64); // rbx

  if ( !_InterlockedCompareExchange(&dword_1800402F0, 1, 0) )
  {
    ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
    if ( ModuleHandleW )
    {
      ProcAddress = GetProcAddress(ModuleHandleW, "WerRegisterMemoryBlock");
      v2 = (void (__fastcall *)(volatile int *, __int64))ProcAddress;
      if ( ProcAddress )
      {
        ((void (__fastcall *)(LPVOID, __int64))ProcAddress)(lpMem, 10240);
        v2(&g_nCurrentStackCaptureIndex, 4);
      }
    }
  }
}

```

## disassembly

```asm
0x1800228b8  push    rbx
0x1800228ba  sub     rsp, 20h
0x1800228be  mov     ecx, 1
0x1800228c3  xor     eax, eax
0x1800228c5  lock cmpxchg cs:dword_1800402F0, ecx
0x1800228cd  jnz     short loc_18002291E
0x1800228cf  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800228d6  call    cs:__imp_GetModuleHandleW
0x1800228dc  test    rax, rax
0x1800228df  jz      short loc_18002291E
0x1800228e1  lea     rdx, aWerregistermem; "WerRegisterMemoryBlock"
0x1800228e8  mov     rcx, rax; hModule
0x1800228eb  call    cs:__imp_GetProcAddress
0x1800228f1  mov     rbx, rax
0x1800228f4  test    rax, rax
0x1800228f7  jz      short loc_18002291E
0x1800228f9  mov     rcx, cs:lpMem
0x180022900  mov     edx, 2800h
0x180022905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002290a  mov     edx, 4
0x18002290f  lea     rcx, ?g_nCurrentStackCaptureIndex@@3JC; long volatile g_nCurrentStackCaptureIndex
0x180022916  mov     rax, rbx
0x180022919  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002291e  add     rsp, 20h
0x180022922  pop     rbx
0x180022923  retn
```
