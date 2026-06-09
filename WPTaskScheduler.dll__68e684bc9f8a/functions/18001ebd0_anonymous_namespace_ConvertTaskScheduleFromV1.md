# _anonymous_namespace_::ConvertTaskScheduleFromV1

- ea: `0x18001ebd0`
- end: `0x18001ec0f`
- name: `_anonymous_namespace_::ConvertTaskScheduleFromV1`
- size: `63`
- prototype: `__int64 __fastcall(__int64, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18001ed18`
- `0x18001efc8`

## callees

- `0x18001ebd0`
- `0x180020c02`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::ConvertTaskScheduleFromV1(__int64 a1, void *a2)
{
  __int64 result; // rax

  result = (__int64)a2;
  if ( a2 )
  {
    memset_0(a2, 0, 0x58u);
    if ( !qword_180030F28 )
      qword_180030F28 = *(_QWORD *)(a1 + 80);
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x18001ebd0  push    rbx
0x18001ebd2  sub     rsp, 20h
0x18001ebd6  mov     rax, rdx
0x18001ebd9  mov     rbx, rcx
0x18001ebdc  test    rdx, rdx
0x18001ebdf  jz      short loc_18001EC09
0x18001ebe1  xor     edx, edx; Val
0x18001ebe3  mov     rcx, rax; void *
0x18001ebe6  lea     r8d, [rdx+58h]; Size
0x18001ebea  call    memset_0
0x18001ebef  cmp     cs:qword_180030F28, 0
0x18001ebf7  jnz     short loc_18001EC04
0x18001ebf9  mov     rax, [rbx+50h]
0x18001ebfd  mov     cs:qword_180030F28, rax
0x18001ec04  mov     eax, 1
0x18001ec09  add     rsp, 20h
0x18001ec0d  pop     rbx
0x18001ec0e  retn
```
