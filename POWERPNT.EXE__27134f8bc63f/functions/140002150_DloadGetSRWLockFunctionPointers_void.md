# DloadGetSRWLockFunctionPointers(void)

- ea: `0x140002150`
- end: `0x1400021ee`
- name: `?DloadGetSRWLockFunctionPointers@@YAEXZ`
- size: `158`
- prototype: `unsigned __int8(void)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000194c`
- `0x140001e10`
- `0x140002090`

## callees

- `0x140002150`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140002194`
- `KERNEL32!GetProcAddress` at `0x1400021b0`
- `KERNEL32!GetProcAddress` at `0x140002194`
- `KERNEL32!GetProcAddress` at `0x1400021b0`
- `KERNEL32!GetModuleHandleW` at `0x140002177`
- `KERNEL32!GetModuleHandleW` at `0x140002177`

## string_xrefs

- `0x140002170`: `KERNEL32.DLL`

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
0x140002150  mov     [rsp+arg_0], rbx
0x140002155  push    rdi
0x140002156  sub     rsp, 20h
0x14000215a  mov     rax, cs:?DloadKernel32@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * DloadKernel32
0x140002161  mov     edi, 1
0x140002166  cmp     rax, rdi
0x140002169  jz      short loc_1400021E1
0x14000216b  test    rax, rax
0x14000216e  jnz     short loc_1400021DC
0x140002170  lea     rcx, ModuleName; "KERNEL32.DLL"
0x140002177  call    cs:__imp_GetModuleHandleW
0x14000217d  mov     rbx, rax
0x140002180  test    rax, rax
0x140002183  jnz     short loc_14000218A
0x140002185  mov     rbx, rdi
0x140002188  jmp     short loc_1400021C2
0x14000218a  lea     rdx, ProcName; "AcquireSRWLockExclusive"
0x140002191  mov     rcx, rbx; hModule
0x140002194  call    cs:__imp_GetProcAddress
0x14000219a  test    rax, rax
0x14000219d  jz      short loc_140002185
0x14000219f  lea     rdx, aReleasesrwlock; "ReleaseSRWLockExclusive"
0x1400021a6  mov     cs:?DloadAcquireSRWLockExclusive@@3P6AXPEA_K@ZEA, rax; void (*DloadAcquireSRWLockExclusive)(unsigned __int64 *)
0x1400021ad  mov     rcx, rbx; hModule
0x1400021b0  call    cs:__imp_GetProcAddress
0x1400021b6  test    rax, rax
0x1400021b9  jz      short loc_140002185
0x1400021bb  mov     cs:?DloadReleaseSRWLockExclusive@@3P6AXPEA_K@ZEA, rax; void (*DloadReleaseSRWLockExclusive)(unsigned __int64 *)
0x1400021c2  xor     eax, eax
0x1400021c4  lock cmpxchg cs:?DloadKernel32@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * DloadKernel32
0x1400021cd  jnz     short loc_1400021D4
0x1400021cf  cmp     rbx, rdi
0x1400021d2  jz      short loc_1400021E1
0x1400021d4  cmp     rax, rdi
0x1400021d7  setnz   al
0x1400021da  jmp     short loc_1400021E3
0x1400021dc  mov     al, dil
0x1400021df  jmp     short loc_1400021E3
0x1400021e1  xor     al, al
0x1400021e3  mov     rbx, [rsp+28h+arg_0]
0x1400021e8  add     rsp, 20h
0x1400021ec  pop     rdi
0x1400021ed  retn
```
