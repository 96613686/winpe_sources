# _FindAndUnlinkFrame

- ea: `0x180008b78`
- end: `0x180008bcb`
- name: `_FindAndUnlinkFrame`
- size: `83`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000aa20`

## callees

- `0x180008b78`
- `0x180009518`
- `0x18000e7c8`

## pseudocode

```c
__int64 __fastcall FindAndUnlinkFrame(__int64 a1)
{
  __int64 v2; // rdx
  __int64 v3; // rbx
  __int64 result; // rax

  if ( a1 != *(_QWORD *)(_vcrt_getptd() + 88) || (v2 = *(_QWORD *)(_vcrt_getptd() + 88)) == 0 )
LABEL_7:
    abort();
  while ( 1 )
  {
    v3 = *(_QWORD *)(v2 + 8);
    if ( a1 == v2 )
      break;
    v2 = *(_QWORD *)(v2 + 8);
    if ( !v3 )
      goto LABEL_7;
  }
  result = _vcrt_getptd();
  *(_QWORD *)(result + 88) = v3;
  return result;
}

```

## disassembly

```asm
0x180008b78  mov     [rsp+arg_0], rbx
0x180008b7d  push    rdi
0x180008b7e  sub     rsp, 20h
0x180008b82  mov     rdi, rcx
0x180008b85  call    __vcrt_getptd
0x180008b8a  cmp     rdi, [rax+58h]
0x180008b8e  jnz     short loc_180008BC5
0x180008b90  call    __vcrt_getptd
0x180008b95  mov     rdx, [rax+58h]
0x180008b99  test    rdx, rdx
0x180008b9c  jz      short loc_180008BC5
0x180008b9e  mov     rbx, [rdx+8]
0x180008ba2  cmp     rdi, rdx
0x180008ba5  jz      short loc_180008BB1
0x180008ba7  mov     rdx, rbx
0x180008baa  test    rbx, rbx
0x180008bad  jz      short loc_180008BC5
0x180008baf  jmp     short loc_180008B9E
0x180008bb1  call    __vcrt_getptd
0x180008bb6  mov     [rax+58h], rbx
0x180008bba  mov     rbx, [rsp+28h+arg_0]
0x180008bbf  add     rsp, 20h
0x180008bc3  pop     rdi
0x180008bc4  retn
0x180008bc5  call    abort
```
