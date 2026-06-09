# __except_validate_context_record

- ea: `0x14000e128`
- end: `0x14000e15f`
- name: `__except_validate_context_record`
- size: `55`
- prototype: `struct _TEB *__fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000bc38`
- `0x14000cf60`
- `0x14000d4b0`

## callees

- `0x14000e128`

## pseudocode

```c
struct _TEB *__fastcall _except_validate_context_record(__int64 a1)
{
  struct _TEB *result; // rax
  PVOID v2; // rcx

  result = (struct _TEB *)_guard_check_icall_fptr[0];
  if ( _guard_check_icall_fptr[0] != guard_check_icall_nop )
  {
    result = NtCurrentTeb();
    v2 = *(PVOID *)(a1 + 152);
    if ( v2 < result->NtTib.StackLimit || v2 > result->NtTib.StackBase )
      __fastfail(0xDu);
  }
  return result;
}

```

## disassembly

```asm
0x14000e128  mov     rax, cs:__guard_check_icall_fptr
0x14000e12f  lea     rdx, _guard_check_icall_nop
0x14000e136  cmp     rax, rdx
0x14000e139  jz      short locret_14000E15E
0x14000e13b  mov     rax, gs:30h
0x14000e144  mov     rcx, [rcx+98h]
0x14000e14b  cmp     rcx, [rax+10h]
0x14000e14f  jb      short loc_14000E157
0x14000e151  cmp     rcx, [rax+8]
0x14000e155  jbe     short locret_14000E15E
0x14000e157  mov     ecx, 0Dh
0x14000e15c  int     29h; Win8: RtlFailFast(ecx)
0x14000e15e  retn
```
