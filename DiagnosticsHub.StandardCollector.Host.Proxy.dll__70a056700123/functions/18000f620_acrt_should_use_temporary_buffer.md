# __acrt_should_use_temporary_buffer

- ea: `0x18000f620`
- end: `0x18000f669`
- name: `__acrt_should_use_temporary_buffer`
- size: `73`
- prototype: `__int64 __fastcall(FILE *Stream)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x18000f66c`
- `0x18005c5f4`
- `0x18005c6c0`
- `0x18005ca18`
- `0x18005cae4`

## callees

- `0x18000f510`
- `0x18000f620`
- `0x180014970`
- `0x180015ac4`

## pseudocode

```c
bool __fastcall _acrt_should_use_temporary_buffer(FILE *Stream)
{
  int v2; // eax

  if ( Stream == _acrt_iob_func(2u) )
    return 1;
  if ( Stream != _acrt_iob_func(1u) )
    return 0;
  v2 = fileno(Stream);
  return isatty(v2) != 0;
}

```

## disassembly

```asm
0x18000f620  push    rbx
0x18000f622  sub     rsp, 20h
0x18000f626  mov     rbx, rcx
0x18000f629  mov     ecx, 2; Ix
0x18000f62e  call    __acrt_iob_func
0x18000f633  cmp     rbx, rax
0x18000f636  jz      short loc_18000F661
0x18000f638  mov     ecx, 1; Ix
0x18000f63d  call    __acrt_iob_func
0x18000f642  cmp     rbx, rax
0x18000f645  jnz     short loc_18000F65D
0x18000f647  mov     rcx, rbx; Stream
0x18000f64a  call    _fileno
0x18000f64f  mov     ecx, eax; FileHandle
0x18000f651  call    _isatty
0x18000f656  test    eax, eax
0x18000f658  setnz   al
0x18000f65b  jmp     short loc_18000F663
0x18000f65d  xor     al, al
0x18000f65f  jmp     short loc_18000F663
0x18000f661  mov     al, 1
0x18000f663  add     rsp, 20h
0x18000f667  pop     rbx
0x18000f668  retn
```
