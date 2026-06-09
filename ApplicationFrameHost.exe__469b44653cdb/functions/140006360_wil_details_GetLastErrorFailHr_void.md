# wil::details::GetLastErrorFailHr(void)

- ea: `0x140006360`
- end: `0x14000637f`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `31`
- prototype: `__int64 __fastcall(wil::details *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400052f8`
- `0x140005464`
- `0x14000966c`

## callees

- `0x140002bf0`

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
0x140006360  sub     rsp, 38h
0x140006364  mov     rax, [rsp+38h]
0x140006369  xor     r8d, r8d; unsigned int
0x14000636c  xor     edx, edx; void *
0x14000636e  mov     [rsp+38h+var_10], rax; char *
0x140006373  xor     ecx, ecx; this
0x140006375  call    ?GetLastErrorFailHr@details@wil@@YAJPEAXIPEBD110@Z; wil::details::GetLastErrorFailHr(void *,uint,char const *,char const *,char const *,void *)
0x14000637a  add     rsp, 38h
0x14000637e  retn
```
