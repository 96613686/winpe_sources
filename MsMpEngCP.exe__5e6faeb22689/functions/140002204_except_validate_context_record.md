# __except_validate_context_record

- ea: `0x140002204`
- end: `0x14000223b`
- name: `__except_validate_context_record`
- size: `55`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140001db0`
- `0x140003a20`
- `0x140003d60`

## callees

- `0x140002204`

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
0x140002204  mov     rax, cs:__guard_check_icall_fptr
0x14000220b  lea     rdx, _guard_check_icall_nop
0x140002212  cmp     rax, rdx
0x140002215  jz      short locret_14000223A
0x140002217  mov     rax, gs:30h
0x140002220  mov     rcx, [rcx+98h]
0x140002227  cmp     rcx, [rax+10h]
0x14000222b  jb      short loc_140002233
0x14000222d  cmp     rcx, [rax+8]
0x140002231  jbe     short locret_14000223A
0x140002233  mov     ecx, 0Dh
0x140002238  int     29h; Win8: RtlFailFast(ecx)
0x14000223a  retn
```
