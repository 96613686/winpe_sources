# av_get_cpu_flags

- ea: `0x180033c50`
- end: `0x180033c7d`
- name: `av_get_cpu_flags`
- size: `45`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180053d24`
- `0x180054c7c`
- `0x180077a60`
- `0x180077e7c`
- `0x180077eb8`
- `0x180077edc`
- `0x180078050`
- `0x1800780dc`

## callees

- `0x180033c50`
- `0x180077ad8`

## pseudocode

```c
__int64 av_get_cpu_flags()
{
  __int64 result; // rax
  signed __int32 v1[10]; // [rsp+0h] [rbp-28h] BYREF

  _InterlockedOr(v1, 0);
  result = (unsigned int)qword_1800A9000;
  if ( (_DWORD)qword_1800A9000 == -1 )
  {
    result = sub_180077AD8();
    qword_1800A9000 = (int)result;
    _InterlockedOr(v1, 0);
  }
  return result;
}

```

## disassembly

```asm
0x180033c50  sub     rsp, 28h
0x180033c54  lock or [rsp+28h+var_28], 0
0x180033c59  mov     eax, dword ptr cs:qword_1800A9000
0x180033c5f  cmp     eax, 0FFFFFFFFh
0x180033c62  jnz     short loc_180033C78
0x180033c64  call    sub_180077AD8
0x180033c69  movsxd  rcx, eax
0x180033c6c  mov     cs:qword_1800A9000, rcx
0x180033c73  lock or [rsp+28h+var_28], 0
0x180033c78  add     rsp, 28h
0x180033c7c  retn
```
