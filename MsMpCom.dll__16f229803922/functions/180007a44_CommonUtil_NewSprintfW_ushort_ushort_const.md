# CommonUtil::NewSprintfW(ushort * *,ushort const *,...)

- ea: `0x180007a44`
- end: `0x180007a6d`
- name: `?NewSprintfW@CommonUtil@@YAJPEAPEAGPEBGZZ`
- size: `41`
- prototype: `__int64(CommonUtil *__hidden this, unsigned __int16 **, const unsigned __int16 *, ...)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800057f4`
- `0x1800070b8`
- `0x180007304`

## callees

- `0x180007a74`

## pseudocode

```c
__int64 CommonUtil::NewSprintfW(CommonUtil *this, unsigned __int16 **a2, const unsigned __int16 *a3, char *a4, ...)
{
  const unsigned __int16 *v5; // [rsp+50h] [rbp+18h] BYREF

  v5 = a3;
  return CommonUtil::NewVSprintfW(this, a2, (const unsigned __int16 *)&v5, a4);
}

```

## disassembly

```asm
0x180007a44  mov     rax, rsp
0x180007a47  mov     [rax+10h], rdx
0x180007a4b  mov     [rax+18h], r8
0x180007a4f  mov     [rax+20h], r9
0x180007a53  sub     rsp, 38h
0x180007a57  lea     r8, [rax+18h]; unsigned __int16 *
0x180007a5b  mov     qword ptr [rax-18h], 0
0x180007a63  call    ?NewVSprintfW@CommonUtil@@YAJPEAPEAGPEBGPEAD@Z; CommonUtil::NewVSprintfW(ushort * *,ushort const *,char *)
0x180007a68  add     rsp, 38h
0x180007a6c  retn
```
