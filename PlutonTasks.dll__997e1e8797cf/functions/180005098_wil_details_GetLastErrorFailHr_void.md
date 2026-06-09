# wil::details::GetLastErrorFailHr(void)

- ea: `0x180005098`
- end: `0x1800050c3`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `43`
- prototype: `signed int __fastcall(wil::details *this, __int64, __int64, const char *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180003d18`
- `0x180003e80`
- `0x180008b48`

## callees

- `0x180005030`
- `0x180005098`

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
0x180005098  sub     rsp, 38h
0x18000509c  mov     rax, [rsp+38h]
0x1800050a1  xor     r8d, r8d; unsigned int
0x1800050a4  xor     edx, edx; void *
0x1800050a6  mov     [rsp+38h+var_10], rax; char *
0x1800050ab  xor     ecx, ecx; this
0x1800050ad  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x1800050b2  test    eax, eax
0x1800050b4  jle     short loc_1800050BE
0x1800050b6  movzx   eax, ax
0x1800050b9  or      eax, 80070000h
0x1800050be  add     rsp, 38h
0x1800050c2  retn
```
