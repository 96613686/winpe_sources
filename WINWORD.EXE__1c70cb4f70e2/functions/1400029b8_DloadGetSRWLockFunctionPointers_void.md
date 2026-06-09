# DloadGetSRWLockFunctionPointers(void)

- ea: `0x1400029b8`
- end: `0x140002a56`
- name: `?DloadGetSRWLockFunctionPointers@@YAEXZ`
- size: `158`
- prototype: `unsigned __int8(void)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140002810`
- `0x1400028fc`
- `0x140002c84`

## callees

- `0x1400029b8`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1400029fc`
- `KERNEL32!GetProcAddress` at `0x140002a18`
- `KERNEL32!GetProcAddress` at `0x1400029fc`
- `KERNEL32!GetProcAddress` at `0x140002a18`
- `KERNEL32!GetModuleHandleW` at `0x1400029df`
- `KERNEL32!GetModuleHandleW` at `0x1400029df`

## string_xrefs

- `0x1400029d8`: `KERNEL32.DLL`

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
0x1400029b8  mov     [rsp+arg_0], rbx
0x1400029bd  push    rdi
0x1400029be  sub     rsp, 20h
0x1400029c2  mov     rax, cs:?DloadKernel32@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * DloadKernel32
0x1400029c9  mov     edi, 1
0x1400029ce  cmp     rax, rdi
0x1400029d1  jz      short loc_140002A49
0x1400029d3  test    rax, rax
0x1400029d6  jnz     short loc_140002A44
0x1400029d8  lea     rcx, ModuleName; "KERNEL32.DLL"
0x1400029df  call    cs:__imp_GetModuleHandleW
0x1400029e5  mov     rbx, rax
0x1400029e8  test    rax, rax
0x1400029eb  jnz     short loc_1400029F2
0x1400029ed  mov     rbx, rdi
0x1400029f0  jmp     short loc_140002A2A
0x1400029f2  lea     rdx, aAcquiresrwlock; "AcquireSRWLockExclusive"
0x1400029f9  mov     rcx, rbx; hModule
0x1400029fc  call    cs:__imp_GetProcAddress
0x140002a02  test    rax, rax
0x140002a05  jz      short loc_1400029ED
0x140002a07  lea     rdx, aReleasesrwlock; "ReleaseSRWLockExclusive"
0x140002a0e  mov     cs:?DloadAcquireSRWLockExclusive@@3P6AXPEA_K@ZEA, rax; void (*DloadAcquireSRWLockExclusive)(unsigned __int64 *)
0x140002a15  mov     rcx, rbx; hModule
0x140002a18  call    cs:__imp_GetProcAddress
0x140002a1e  test    rax, rax
0x140002a21  jz      short loc_1400029ED
0x140002a23  mov     cs:?DloadReleaseSRWLockExclusive@@3P6AXPEA_K@ZEA, rax; void (*DloadReleaseSRWLockExclusive)(unsigned __int64 *)
0x140002a2a  xor     eax, eax
0x140002a2c  lock cmpxchg cs:?DloadKernel32@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * DloadKernel32
0x140002a35  jnz     short loc_140002A3C
0x140002a37  cmp     rbx, rdi
0x140002a3a  jz      short loc_140002A49
0x140002a3c  cmp     rax, rdi
0x140002a3f  setnz   al
0x140002a42  jmp     short loc_140002A4B
0x140002a44  mov     al, dil
0x140002a47  jmp     short loc_140002A4B
0x140002a49  xor     al, al
0x140002a4b  mov     rbx, [rsp+28h+arg_0]
0x140002a50  add     rsp, 20h
0x140002a54  pop     rdi
0x140002a55  retn
```
