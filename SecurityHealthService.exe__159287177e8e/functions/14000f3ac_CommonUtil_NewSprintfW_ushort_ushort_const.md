# CommonUtil::NewSprintfW(ushort * *,ushort const *,...)

- ea: `0x14000f3ac`
- end: `0x14000f3d5`
- name: `?NewSprintfW@CommonUtil@@YAJPEAPEAGPEBGZZ`
- size: `41`
- prototype: `__int64(CommonUtil *this, unsigned __int16 **, const unsigned __int16 *, char *, ...)`
- caller_count: `10`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140002ce8`
- `0x140002f00`
- `0x140003db4`
- `0x140003e58`
- `0x140006008`
- `0x140006714`
- `0x14000eb7c`
- `0x14000ed24`
- `0x140011e50`
- `0x140011ef0`

## callees

- `0x14000f3dc`

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
0x14000f3ac  mov     rax, rsp
0x14000f3af  mov     [rax+10h], rdx
0x14000f3b3  mov     [rax+18h], r8
0x14000f3b7  mov     [rax+20h], r9
0x14000f3bb  sub     rsp, 38h
0x14000f3bf  lea     r8, [rax+18h]; unsigned __int16 *
0x14000f3c3  mov     qword ptr [rax-18h], 0
0x14000f3cb  call    ?NewVSprintfW@CommonUtil@@YAJPEAPEAGPEBGPEAD@Z; CommonUtil::NewVSprintfW(ushort * *,ushort const *,char *)
0x14000f3d0  add     rsp, 38h
0x14000f3d4  retn
```
