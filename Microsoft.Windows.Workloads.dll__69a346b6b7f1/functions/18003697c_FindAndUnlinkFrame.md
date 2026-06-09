# _FindAndUnlinkFrame

- ea: `0x18003697c`
- end: `0x1800369cf`
- name: `_FindAndUnlinkFrame`
- size: `83`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800386a0`

## callees

- `0x1800321c0`
- `0x18003697c`
- `0x180037148`

## pseudocode

```c
__int64 __fastcall FindAndUnlinkFrame(__int64 a1)
{
  __int64 v2; // rdx
  __int64 v3; // rbx
  __int64 result; // rax

  if ( a1 != *(_QWORD *)(_vcrt_getptd() + 88) || (v2 = *(_QWORD *)(_vcrt_getptd() + 88)) == 0 )
LABEL_7:
    abort_0();
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
0x18003697c  mov     [rsp+arg_0], rbx
0x180036981  push    rdi
0x180036982  sub     rsp, 20h
0x180036986  mov     rdi, rcx
0x180036989  call    __vcrt_getptd
0x18003698e  cmp     rdi, [rax+58h]
0x180036992  jnz     short loc_1800369C9
0x180036994  call    __vcrt_getptd
0x180036999  mov     rdx, [rax+58h]
0x18003699d  test    rdx, rdx
0x1800369a0  jz      short loc_1800369C9
0x1800369a2  mov     rbx, [rdx+8]
0x1800369a6  cmp     rdi, rdx
0x1800369a9  jz      short loc_1800369B5
0x1800369ab  mov     rdx, rbx
0x1800369ae  test    rbx, rbx
0x1800369b1  jz      short loc_1800369C9
0x1800369b3  jmp     short loc_1800369A2
0x1800369b5  call    __vcrt_getptd
0x1800369ba  mov     [rax+58h], rbx
0x1800369be  mov     rbx, [rsp+28h+arg_0]
0x1800369c3  add     rsp, 20h
0x1800369c7  pop     rdi
0x1800369c8  retn
0x1800369c9  call    abort_0
```
