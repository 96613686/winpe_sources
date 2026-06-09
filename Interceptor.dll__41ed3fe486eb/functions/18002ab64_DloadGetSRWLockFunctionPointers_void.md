# DloadGetSRWLockFunctionPointers(void)

- ea: `0x18002ab64`
- end: `0x18002ac02`
- name: `?DloadGetSRWLockFunctionPointers@@YAEXZ`
- size: `158`
- prototype: `unsigned __int8(void)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002a9bc`
- `0x18002aaa8`
- `0x18002ae30`

## callees

- `0x18002ab64`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18002aba8`
- `KERNEL32!GetProcAddress` at `0x18002abc4`
- `KERNEL32!GetProcAddress` at `0x18002aba8`
- `KERNEL32!GetProcAddress` at `0x18002abc4`
- `KERNEL32!GetModuleHandleW` at `0x18002ab8b`
- `KERNEL32!GetModuleHandleW` at `0x18002ab8b`

## string_xrefs

- `0x18002ab84`: `KERNEL32.DLL`

## pseudocode

```c
bool DloadGetSRWLockFunctionPointers(void)
{
  HMODULE ModuleHandleW; // rax
  signed __int64 v1; // rbx
  void (*ProcAddress)(unsigned __int64 *); // rax
  void (*v3)(unsigned __int64 *); // rax
  signed __int64 v4; // rax

  if ( DloadKernel32 != (HINSTANCE)1 )
  {
    if ( DloadKernel32 )
      return 1;
    ModuleHandleW = GetModuleHandleW(L"KERNEL32.DLL");
    v1 = (signed __int64)ModuleHandleW;
    if ( ModuleHandleW
      && (ProcAddress = (void (*)(unsigned __int64 *))GetProcAddress(ModuleHandleW, "AcquireSRWLockExclusive")) != 0
      && (DloadAcquireSRWLockExclusive = ProcAddress,
          (v3 = (void (*)(unsigned __int64 *))GetProcAddress((HMODULE)v1, "ReleaseSRWLockExclusive")) != 0) )
    {
      DloadReleaseSRWLockExclusive = v3;
    }
    else
    {
      v1 = 1;
    }
    v4 = _InterlockedCompareExchange64((volatile signed __int64 *)&DloadKernel32, v1, 0);
    if ( v4 || v1 != 1 )
      return v4 != 1;
  }
  return 0;
}

```

## disassembly

```asm
0x18002ab64  mov     [rsp+arg_0], rbx
0x18002ab69  push    rdi
0x18002ab6a  sub     rsp, 20h
0x18002ab6e  mov     rax, cs:?DloadKernel32@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * DloadKernel32
0x18002ab75  mov     edi, 1
0x18002ab7a  cmp     rax, rdi
0x18002ab7d  jz      short loc_18002ABF5
0x18002ab7f  test    rax, rax
0x18002ab82  jnz     short loc_18002ABF0
0x18002ab84  lea     rcx, aKernel32Dll_1; "KERNEL32.DLL"
0x18002ab8b  call    cs:__imp_GetModuleHandleW
0x18002ab91  mov     rbx, rax
0x18002ab94  test    rax, rax
0x18002ab97  jnz     short loc_18002AB9E
0x18002ab99  mov     rbx, rdi
0x18002ab9c  jmp     short loc_18002ABD6
0x18002ab9e  lea     rdx, aAcquiresrwlock; "AcquireSRWLockExclusive"
0x18002aba5  mov     rcx, rbx; hModule
0x18002aba8  call    cs:__imp_GetProcAddress
0x18002abae  test    rax, rax
0x18002abb1  jz      short loc_18002AB99
0x18002abb3  lea     rdx, aReleasesrwlock; "ReleaseSRWLockExclusive"
0x18002abba  mov     cs:?DloadAcquireSRWLockExclusive@@3P6AXPEA_K@ZEA, rax; void (*DloadAcquireSRWLockExclusive)(unsigned __int64 *)
0x18002abc1  mov     rcx, rbx; hModule
0x18002abc4  call    cs:__imp_GetProcAddress
0x18002abca  test    rax, rax
0x18002abcd  jz      short loc_18002AB99
0x18002abcf  mov     cs:?DloadReleaseSRWLockExclusive@@3P6AXPEA_K@ZEA, rax; void (*DloadReleaseSRWLockExclusive)(unsigned __int64 *)
0x18002abd6  xor     eax, eax
0x18002abd8  lock cmpxchg cs:?DloadKernel32@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * DloadKernel32
0x18002abe1  jnz     short loc_18002ABE8
0x18002abe3  cmp     rbx, rdi
0x18002abe6  jz      short loc_18002ABF5
0x18002abe8  cmp     rax, rdi
0x18002abeb  setnz   al
0x18002abee  jmp     short loc_18002ABF7
0x18002abf0  mov     al, dil
0x18002abf3  jmp     short loc_18002ABF7
0x18002abf5  xor     al, al
0x18002abf7  mov     rbx, [rsp+28h+arg_0]
0x18002abfc  add     rsp, 20h
0x18002ac00  pop     rdi
0x18002ac01  retn
```
