# CAMThread::CoInitializeHelper(void)

- ea: `0x1800070c4`
- end: `0x18000710c`
- name: `?CoInitializeHelper@CAMThread@@SAJXZ`
- size: `72`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800071a0`
- `0x180033510`

## callees

- `0x1800070c4`
- `0x180034010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1800070d6`
- `KERNEL32!GetModuleHandleW` at `0x1800070d6`
- `KERNEL32!GetProcAddress` at `0x1800070eb`
- `KERNEL32!GetProcAddress` at `0x1800070eb`

## string_xrefs

- `0x1800070ca`: `ole32.dll`

## pseudocode

```c
__int64 CAMThread::CoInitializeHelper(void)
{
  unsigned int v0; // ebx
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax

  v0 = -2147467259;
  ModuleHandleW = GetModuleHandleW(L"ole32.dll");
  if ( ModuleHandleW )
  {
    ProcAddress = GetProcAddress(ModuleHandleW, "CoInitializeEx");
    if ( ProcAddress )
      return ((unsigned int (__fastcall *)(_QWORD, __int64))ProcAddress)(0, 4);
  }
  return v0;
}

```

## disassembly

```asm
0x1800070c4  push    rbx
0x1800070c6  sub     rsp, 20h
0x1800070ca  lea     rcx, aOle32Dll_0; "ole32.dll"
0x1800070d1  mov     ebx, 80004005h
0x1800070d6  call    cs:__imp_GetModuleHandleW
0x1800070dc  test    rax, rax
0x1800070df  jz      short loc_180007104
0x1800070e1  lea     rdx, aCoinitializeex; "CoInitializeEx"
0x1800070e8  mov     rcx, rax; hModule
0x1800070eb  call    cs:__imp_GetProcAddress
0x1800070f1  test    rax, rax
0x1800070f4  jz      short loc_180007104
0x1800070f6  mov     edx, 4
0x1800070fb  xor     ecx, ecx
0x1800070fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007102  mov     ebx, eax
0x180007104  mov     eax, ebx
0x180007106  add     rsp, 20h
0x18000710a  pop     rbx
0x18000710b  retn
```
