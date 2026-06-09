# SHActivateContext

- ea: `0x1800105f8`
- end: `0x180010661`
- name: `SHActivateContext`
- size: `105`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180010668`
- `0x180010804`
- `0x180010864`

## callees

- `0x1800105f8`
- `0x1800106f8`

## import_xrefs

- `KERNEL32!ActivateActCtx` at `0x18001065a`

## pseudocode

```c
BOOL __fastcall SHActivateContext(ULONG_PTR *a1)
{
  HANDLE v2; // rcx

  *a1 = 0;
  v2 = g_hActCtx;
  if ( g_hActCtx != (HANDLE)-1LL )
    return ActivateActCtx(v2, a1);
  if ( !hModule )
    return 1;
  if ( hModule == (HMODULE)-1LL )
    return 0;
  SHFusionInitializeFromModuleID(hModule, dword_180020D28);
  v2 = g_hActCtx;
  return g_hActCtx == (HANDLE)-1LL || ActivateActCtx(v2, a1);
}

```

## disassembly

```asm
0x1800105f8  push    rbx
0x1800105fa  sub     rsp, 20h
0x1800105fe  mov     rbx, rcx
0x180010601  mov     qword ptr [rcx], 0
0x180010608  mov     rcx, cs:g_hActCtx
0x18001060f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180010613  jnz     short loc_180010652
0x180010615  mov     rcx, cs:hModule; hModule
0x18001061c  test    rcx, rcx
0x18001061f  jz      short loc_180010647
0x180010621  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180010625  jnz     short loc_18001062F
0x180010627  xor     eax, eax
0x180010629  add     rsp, 20h
0x18001062d  pop     rbx
0x18001062e  retn
0x18001062f  mov     edx, cs:dword_180020D28
0x180010635  call    SHFusionInitializeFromModuleID
0x18001063a  mov     rcx, cs:g_hActCtx
0x180010641  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180010645  jnz     short loc_180010652
0x180010647  mov     eax, 1
0x18001064c  add     rsp, 20h
0x180010650  pop     rbx
0x180010651  retn
0x180010652  mov     rdx, rbx
0x180010655  add     rsp, 20h
0x180010659  pop     rbx
0x18001065a  jmp     cs:__imp_ActivateActCtx
```
