# wil::details::GetLastErrorFailHr(void)

- ea: `0x180007c90`
- end: `0x180007caf`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `31`
- prototype: `__int64 __fastcall(wil::details *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180007640`
- `0x1800077a8`
- `0x180007ad0`
- `0x180007b28`

## callees

- `0x180006730`

## pseudocode

```c
__int64 __fastcall wil::details::GetLastErrorFailHr(wil::details *this, __int64 a2, __int64 a3, const char *a4)
{
  const char *v5; // [rsp+20h] [rbp-18h]
  void *v6; // [rsp+30h] [rbp-8h]
  const char *retaddr; // [rsp+38h] [rbp+0h]

  return wil::details::GetLastErrorFailHr(0, 0, 0, a4, v5, retaddr, v6);
}

```

## disassembly

```asm
0x180007c90  sub     rsp, 38h
0x180007c94  mov     rax, [rsp+38h]
0x180007c99  xor     r8d, r8d; unsigned int
0x180007c9c  xor     edx, edx; void *
0x180007c9e  mov     [rsp+38h+var_10], rax; char *
0x180007ca3  xor     ecx, ecx; this
0x180007ca5  call    ?GetLastErrorFailHr@details@wil@@YAJPEAXIPEBD110@Z; wil::details::GetLastErrorFailHr(void *,uint,char const *,char const *,char const *,void *)
0x180007caa  add     rsp, 38h
0x180007cae  retn
```
