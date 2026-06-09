# wil::details::GetLastErrorFailHr(void)

- ea: `0x140003278`
- end: `0x1400032a3`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `43`
- prototype: `signed int __fastcall(wil::details *this, __int64, __int64, const char *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400029f4`
- `0x140004aa0`

## callees

- `0x140003210`
- `0x140003278`

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
0x140003278  sub     rsp, 38h
0x14000327c  mov     rax, [rsp+38h]
0x140003281  xor     r8d, r8d; unsigned int
0x140003284  xor     edx, edx; void *
0x140003286  mov     [rsp+38h+var_10], rax; char *
0x14000328b  xor     ecx, ecx; this
0x14000328d  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x140003292  test    eax, eax
0x140003294  jle     short loc_14000329E
0x140003296  movzx   eax, ax
0x140003299  or      eax, 80070000h
0x14000329e  add     rsp, 38h
0x1400032a2  retn
```
