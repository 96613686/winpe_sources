# SHActivateContext

- ea: `0x18000b030`
- end: `0x18000b099`
- name: `SHActivateContext`
- size: `105`
- prototype: `BOOL __fastcall(ULONG_PTR *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000377c`
- `0x18000b1cc`

## callees

- `0x18000b030`
- `0x18000b0c0`

## import_xrefs

- `KERNEL32!ActivateActCtx` at `0x18000b092`

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
  SHFusionInitializeFromModuleID(hModule);
  v2 = g_hActCtx;
  return g_hActCtx == (HANDLE)-1LL || ActivateActCtx(v2, a1);
}

```

## disassembly

```asm
0x18000b030  push    rbx
0x18000b032  sub     rsp, 20h
0x18000b036  mov     rbx, rcx
0x18000b039  mov     qword ptr [rcx], 0
0x18000b040  mov     rcx, cs:g_hActCtx
0x18000b047  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000b04b  jnz     short loc_18000B08A
0x18000b04d  mov     rcx, cs:hModule; hModule
0x18000b054  test    rcx, rcx
0x18000b057  jz      short loc_18000B07F
0x18000b059  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000b05d  jnz     short loc_18000B067
0x18000b05f  xor     eax, eax
0x18000b061  add     rsp, 20h
0x18000b065  pop     rbx
0x18000b066  retn
0x18000b067  mov     edx, cs:dword_180015B88
0x18000b06d  call    SHFusionInitializeFromModuleID
0x18000b072  mov     rcx, cs:g_hActCtx
0x18000b079  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000b07d  jnz     short loc_18000B08A
0x18000b07f  mov     eax, 1
0x18000b084  add     rsp, 20h
0x18000b088  pop     rbx
0x18000b089  retn
0x18000b08a  mov     rdx, rbx
0x18000b08d  add     rsp, 20h
0x18000b091  pop     rbx
0x18000b092  jmp     cs:__imp_ActivateActCtx
```
