# av_packet_alloc

- ea: `0x18000ed70`
- end: `0x18000ed99`
- name: `av_packet_alloc`
- size: `41`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x180004150`
- `0x180005ac0`
- `0x180007f70`
- `0x18000eda0`
- `0x18000fb70`
- `0x180010740`
- `0x18001115c`

## callees

- `0x18000ed70`
- `0x18000fc2c`
- `0x1800228dc`

## pseudocode

```c
_QWORD *av_packet_alloc()
{
  _QWORD *result; // rax
  __int64 v1; // rdx
  __int64 v2; // r8
  __int64 v3; // r9
  _QWORD *v4; // rbx

  result = (_QWORD *)av_malloc(104);
  v4 = result;
  if ( result )
  {
    sub_18000FC2C(result, v1, v2, v3);
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x18000ed70  push    rbx
0x18000ed72  sub     rsp, 20h
0x18000ed76  mov     ecx, 68h ; 'h'
0x18000ed7b  call    av_malloc
0x18000ed80  mov     rbx, rax
0x18000ed83  test    rax, rax
0x18000ed86  jz      short loc_18000ED93
0x18000ed88  mov     rcx, rbx
0x18000ed8b  call    sub_18000FC2C
0x18000ed90  mov     rax, rbx
0x18000ed93  add     rsp, 20h
0x18000ed97  pop     rbx
0x18000ed98  retn
```
