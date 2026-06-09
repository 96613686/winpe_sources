# CrashHandler(_EXCEPTION_POINTERS const *,uint,CrashContext *)

- ea: `0x140002dbc`
- end: `0x140002dfb`
- name: `?CrashHandler@@YAHPEBU_EXCEPTION_POINTERS@@IPEAUCrashContext@@@Z`
- size: `63`
- prototype: `__int64 __fastcall(const struct _EXCEPTION_POINTERS *, unsigned int, struct CrashContext *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400029d3`

## callees

- `0x140002dbc`

## pseudocode

```c
__int64 __fastcall CrashHandler(const struct _EXCEPTION_POINTERS *a1, DWORD a2, struct CrashContext *a3)
{
  a1->ExceptionRecord->ExceptionCode = a2;
  if ( a3 )
  {
    a1->ContextRecord->ContextFlags = 1048577;
    a1->ExceptionRecord->ExceptionAddress = *(PVOID *)a3;
    a1->ContextRecord->Rip = *(_QWORD *)a3;
    a1->ContextRecord->Rsp = *((_QWORD *)a3 + 2);
  }
  return 0;
}

```

## disassembly

```asm
0x140002dbc  mov     rax, [rcx]
0x140002dbf  mov     [rax], edx
0x140002dc1  test    r8, r8
0x140002dc4  jz      short loc_140002DF8
0x140002dc6  mov     rax, [rcx+8]
0x140002dca  mov     dword ptr [rax+30h], 100001h
0x140002dd1  mov     rdx, [rcx]
0x140002dd4  mov     rax, [r8]
0x140002dd7  mov     [rdx+10h], rax
0x140002ddb  mov     rdx, [rcx+8]
0x140002ddf  mov     rax, [r8]
0x140002de2  mov     [rdx+0F8h], rax
0x140002de9  mov     rcx, [rcx+8]
0x140002ded  mov     rax, [r8+10h]
0x140002df1  mov     [rcx+98h], rax
0x140002df8  xor     eax, eax
0x140002dfa  retn
```
