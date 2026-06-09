# wil::details::GetLastErrorFailHr(void)

- ea: `0x140003cc8`
- end: `0x140003cf3`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `43`
- prototype: `signed int __fastcall(wil::details *this, __int64, __int64, const char *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140003440`
- `0x140005c30`
- `0x14000759c`
- `0x14000925c`

## callees

- `0x140003c60`
- `0x140003cc8`

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
0x140003cc8  sub     rsp, 38h
0x140003ccc  mov     rax, [rsp+38h]
0x140003cd1  xor     r8d, r8d; unsigned int
0x140003cd4  xor     edx, edx; void *
0x140003cd6  mov     [rsp+38h+var_10], rax; char *
0x140003cdb  xor     ecx, ecx; this
0x140003cdd  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x140003ce2  test    eax, eax
0x140003ce4  jle     short loc_140003CEE
0x140003ce6  movzx   eax, ax
0x140003ce9  or      eax, 80070000h
0x140003cee  add     rsp, 38h
0x140003cf2  retn
```
