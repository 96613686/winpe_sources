# wil::details::GetLastErrorFailHr(void)

- ea: `0x1400041c8`
- end: `0x1400041f3`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `43`
- prototype: `signed int __fastcall(wil::details *this, __int64, __int64, const char *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140003478`
- `0x1400035e4`
- `0x140007318`

## callees

- `0x140004160`
- `0x1400041c8`

## pseudocode

```c
signed int __fastcall wil::details::GetLastErrorFailHr(wil::details *this, __int64 a2, __int64 a3, const char *a4)
{
  signed int result; // eax
  const char *v5; // [rsp+20h] [rbp-18h]
  const char *retaddr; // [rsp+38h] [rbp+0h]

  result = wil::details::GetLastErrorFail(0, 0, 0, a4, v5, retaddr);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1400041c8  sub     rsp, 38h
0x1400041cc  mov     rax, [rsp+38h]
0x1400041d1  xor     r8d, r8d; unsigned int
0x1400041d4  xor     edx, edx; void *
0x1400041d6  mov     [rsp+38h+var_10], rax; char *
0x1400041db  xor     ecx, ecx; this
0x1400041dd  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x1400041e2  test    eax, eax
0x1400041e4  jle     short loc_1400041EE
0x1400041e6  movzx   eax, ax
0x1400041e9  or      eax, 80070000h
0x1400041ee  add     rsp, 38h
0x1400041f2  retn
```
