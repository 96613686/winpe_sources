# EnsureStackCaptureRegisteredWithWER(void)

- ea: `0x18002629c`
- end: `0x180026308`
- name: `?EnsureStackCaptureRegisteredWithWER@@YAXXZ`
- size: `108`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800129e8`

## callees

- `0x18002629c`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800262cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800262cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800262ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800262ba`

## string_xrefs

- `0x1800262b3`: `kernel32.dll`

## pseudocode

```c
void EnsureStackCaptureRegisteredWithWER(void)
{
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  void (__fastcall *v2)(volatile int *, __int64); // rbx

  if ( !_InterlockedCompareExchange(&dword_180099254, 1, 0) )
  {
    ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
    if ( ModuleHandleW )
    {
      ProcAddress = GetProcAddress(ModuleHandleW, "WerRegisterMemoryBlock");
      v2 = (void (__fastcall *)(volatile int *, __int64))ProcAddress;
      if ( ProcAddress )
      {
        ((void (__fastcall *)(__int64, __int64))ProcAddress)(qword_180099288, 10240);
        v2(&g_nCurrentStackCaptureIndex, 4);
      }
    }
  }
}

```

## disassembly

```asm
0x18002629c  push    rbx
0x18002629e  sub     rsp, 20h
0x1800262a2  mov     ecx, 1
0x1800262a7  xor     eax, eax
0x1800262a9  lock cmpxchg cs:dword_180099254, ecx
0x1800262b1  jnz     short loc_180026302
0x1800262b3  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800262ba  call    cs:__imp_GetModuleHandleW
0x1800262c0  test    rax, rax
0x1800262c3  jz      short loc_180026302
0x1800262c5  lea     rdx, aWerregistermem; "WerRegisterMemoryBlock"
0x1800262cc  mov     rcx, rax; hModule
0x1800262cf  call    cs:__imp_GetProcAddress
0x1800262d5  mov     rbx, rax
0x1800262d8  test    rax, rax
0x1800262db  jz      short loc_180026302
0x1800262dd  mov     rcx, cs:qword_180099288
0x1800262e4  mov     edx, 2800h
0x1800262e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800262ee  mov     edx, 4
0x1800262f3  lea     rcx, ?g_nCurrentStackCaptureIndex@@3JC; long volatile g_nCurrentStackCaptureIndex
0x1800262fa  mov     rax, rbx
0x1800262fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026302  add     rsp, 20h
0x180026306  pop     rbx
0x180026307  retn
```
