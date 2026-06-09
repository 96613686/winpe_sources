# wil::details::GetLastErrorFailHr(void)

- ea: `0x180002be4`
- end: `0x180002c0f`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `43`
- prototype: `__int64 __fastcall(wil::details *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180001ea0`
- `0x18000279c`
- `0x18000763c`
- `0x180008344`

## callees

- `0x180002be4`
- `0x180002c18`

## pseudocode

```c
signed int __fastcall wil::details::GetLastErrorFailHr(wil::details *this, __int64 a2, __int64 a3, const char *a4)
{
  signed int result; // eax
  const char *v5; // [rsp+20h] [rbp-18h]
  void *v6; // [rsp+30h] [rbp-8h]
  const char *retaddr; // [rsp+38h] [rbp+0h]

  result = wil::details::GetLastErrorFail(0, 0, 0, a4, v5, retaddr, v6);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180002be4  sub     rsp, 38h
0x180002be8  mov     rax, [rsp+38h]
0x180002bed  xor     r8d, r8d; unsigned int
0x180002bf0  xor     edx, edx; void *
0x180002bf2  mov     [rsp+38h+var_10], rax; char *
0x180002bf7  xor     ecx, ecx; this
0x180002bf9  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x180002bfe  test    eax, eax
0x180002c00  jle     short loc_180002C0A
0x180002c02  movzx   eax, ax
0x180002c05  or      eax, 80070000h
0x180002c0a  add     rsp, 38h
0x180002c0e  retn
```
