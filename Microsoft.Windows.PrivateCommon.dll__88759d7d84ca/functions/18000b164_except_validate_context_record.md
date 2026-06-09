# __except_validate_context_record

- ea: `0x18000b164`
- end: `0x18000b19b`
- name: `__except_validate_context_record`
- size: `55`
- prototype: `struct _TEB *__fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180008c3c`
- `0x18000a060`
- `0x18000a530`

## callees

- `0x18000b164`

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
0x18000b164  mov     rax, cs:__guard_check_icall_fptr
0x18000b16b  lea     rdx, _guard_check_icall_nop
0x18000b172  cmp     rax, rdx
0x18000b175  jz      short locret_18000B19A
0x18000b177  mov     rax, gs:30h
0x18000b180  mov     rcx, [rcx+98h]
0x18000b187  cmp     rcx, [rax+10h]
0x18000b18b  jb      short loc_18000B193
0x18000b18d  cmp     rcx, [rax+8]
0x18000b191  jbe     short locret_18000B19A
0x18000b193  mov     ecx, 0Dh
0x18000b198  int     29h; Win8: RtlFailFast(ecx)
0x18000b19a  retn
```
