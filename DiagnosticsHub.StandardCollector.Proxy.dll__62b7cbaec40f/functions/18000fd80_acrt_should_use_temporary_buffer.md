# __acrt_should_use_temporary_buffer

- ea: `0x18000fd80`
- end: `0x18000fdc9`
- name: `__acrt_should_use_temporary_buffer`
- size: `73`
- prototype: `__int64 __fastcall(FILE *Stream)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x18000fdcc`
- `0x18005c8d4`
- `0x18005c9a0`
- `0x18005ccf8`
- `0x18005cdc4`

## callees

- `0x18000fc70`
- `0x18000fd80`
- `0x1800150d0`
- `0x180016224`

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
0x18000fd80  push    rbx
0x18000fd82  sub     rsp, 20h
0x18000fd86  mov     rbx, rcx
0x18000fd89  mov     ecx, 2; Ix
0x18000fd8e  call    __acrt_iob_func
0x18000fd93  cmp     rbx, rax
0x18000fd96  jz      short loc_18000FDC1
0x18000fd98  mov     ecx, 1; Ix
0x18000fd9d  call    __acrt_iob_func
0x18000fda2  cmp     rbx, rax
0x18000fda5  jnz     short loc_18000FDBD
0x18000fda7  mov     rcx, rbx; Stream
0x18000fdaa  call    _fileno
0x18000fdaf  mov     ecx, eax; FileHandle
0x18000fdb1  call    _isatty
0x18000fdb6  test    eax, eax
0x18000fdb8  setnz   al
0x18000fdbb  jmp     short loc_18000FDC3
0x18000fdbd  xor     al, al
0x18000fdbf  jmp     short loc_18000FDC3
0x18000fdc1  mov     al, 1
0x18000fdc3  add     rsp, 20h
0x18000fdc7  pop     rbx
0x18000fdc8  retn
```
