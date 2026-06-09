# CrashWithRecovery(uint,CrashContext *)

- ea: `0x140002970`
- end: `0x1400029d3`
- name: `?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z`
- size: `99`
- prototype: `void __fastcall __noreturn(unsigned int, struct CrashContext *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140002d90`

## callees

- `0x140001540`
- `0x140002970`
- `0x140002dfc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000297d`
- `KERNEL32!GetLastError` at `0x14000297d`

## pseudocode

```c
void __fastcall __noreturn CrashWithRecovery(unsigned int a1, struct CrashContext *a2)
{
  __int64 v2; // rcx
  void (__fastcall *v3)(_QWORD); // [rsp+28h] [rbp-30h]

  GetLastError();
  v3 = (void (__fastcall *)(_QWORD))Mso::CrashDetails::PopVecCallback(v2);
  if ( v3 )
    v3(a1);
  MEMORY[0] = 1;
  __fastfail(0);
}

```

## disassembly

```asm
0x140002970  mov     [rsp+arg_8], rdx
0x140002975  mov     [rsp+arg_0], ecx
0x140002979  sub     rsp, 58h
0x14000297d  call    cs:__imp_GetLastError
0x140002983  mov     [rsp+58h+var_38], eax
0x140002987  call    ?PopVecCallback@CrashDetails@Mso@@YAP6AXI@_EXZ
0x14000298c  mov     [rsp+58h+var_30], rax
0x140002991  cmp     [rsp+58h+var_30], 0
0x140002997  jz      short loc_1400029BD
0x140002999  mov     rax, [rsp+58h+var_30]
0x14000299e  mov     [rsp+58h+var_28], rax
0x1400029a3  mov     rax, [rsp+58h+var_28]
0x1400029a8  mov     [rsp+58h+var_20], rax
0x1400029ad  mov     ecx, [rsp+58h+arg_0]
0x1400029b1  mov     rax, [rsp+58h+var_20]
0x1400029b6  call    cs:__guard_dispatch_icall_fptr
0x1400029bc  nop
0x1400029bd  mov     dword ptr ds:0, 1
0x1400029c8  jmp     short $+2
0x1400029ca  xor     ecx, ecx
0x1400029cc  int     29h; Win8: RtlFailFast(ecx)
0x1400029ce  add     rsp, 58h
0x1400029d2  retn
```
