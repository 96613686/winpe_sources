# CommonUtil::NewSprintfW(ushort * *,ushort const *,...)

- ea: `0x14000de38`
- end: `0x14000de61`
- name: `?NewSprintfW@CommonUtil@@YAJPEAPEAGPEBGZZ`
- size: `41`
- prototype: `__int64(CommonUtil *this, unsigned __int16 **, const unsigned __int16 *, char *, ...)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000285c`
- `0x14000d968`

## callees

- `0x14000de68`

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
0x14000de38  mov     rax, rsp
0x14000de3b  mov     [rax+10h], rdx
0x14000de3f  mov     [rax+18h], r8
0x14000de43  mov     [rax+20h], r9
0x14000de47  sub     rsp, 38h
0x14000de4b  lea     r8, [rax+18h]; unsigned __int16 *
0x14000de4f  mov     qword ptr [rax-18h], 0
0x14000de57  call    ?NewVSprintfW@CommonUtil@@YAJPEAPEAGPEBGPEAD@Z; CommonUtil::NewVSprintfW(ushort * *,ushort const *,char *)
0x14000de5c  add     rsp, 38h
0x14000de60  retn
```
