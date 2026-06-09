# __except_validate_context_record

- ea: `0x180014598`
- end: `0x1800145cf`
- name: `__except_validate_context_record`
- size: `55`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180010d04`
- `0x180012d80`
- `0x180012fb4`
- `0x1800134f0`
- `0x1800136f0`

## callees

- `0x180014598`

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
0x180014598  mov     rax, cs:__guard_check_icall_fptr
0x18001459f  lea     rdx, _guard_check_icall_nop
0x1800145a6  cmp     rax, rdx
0x1800145a9  jz      short locret_1800145CE
0x1800145ab  mov     rax, gs:30h
0x1800145b4  mov     rcx, [rcx+98h]
0x1800145bb  cmp     rcx, [rax+10h]
0x1800145bf  jb      short loc_1800145C7
0x1800145c1  cmp     rcx, [rax+8]
0x1800145c5  jbe     short locret_1800145CE
0x1800145c7  mov     ecx, 0Dh
0x1800145cc  int     29h; Win8: RtlFailFast(ecx)
0x1800145ce  retn
```
