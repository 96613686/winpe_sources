# std::collate<wchar_t>::do_compare(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *)

- ea: `0x1800160f0`
- end: `0x180016132`
- name: `?do_compare@?$collate@_W@std@@MEBAHPEB_W000@Z`
- size: `66`
- prototype: `__int64 __fastcall(const _Collvec *, const wchar_t *, const wchar_t *, const wchar_t *, wchar_t *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180022e8c`

## pseudocode

```c
__int64 __fastcall std::collate<wchar_t>::do_compare(
        const _Collvec *a1,
        const wchar_t *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        wchar_t *a5)
{
  int v5; // ecx
  __int64 result; // rax

  v5 = Wcscoll(a2, a3, a4, a5, a1 + 1);
  result = v5 != 0;
  if ( v5 < 0 )
    return 0xFFFFFFFFLL;
  return result;
}

```

## disassembly

```asm
0x1800160f0  push    rbx
0x1800160f2  sub     rsp, 30h
0x1800160f6  mov     r10, r9
0x1800160f9  lea     rax, [rcx+10h]
0x1800160fd  mov     r9, [rsp+38h+arg_20]; wchar_t *
0x180016102  mov     r11, r8
0x180016105  mov     rbx, rdx
0x180016108  mov     [rsp+38h+var_18], rax; _Collvec *
0x18001610d  mov     r8, r10; wchar_t *
0x180016110  mov     rdx, r11; wchar_t *
0x180016113  mov     rcx, rbx; wchar_t *
0x180016116  call    _Wcscoll
0x18001611b  mov     ecx, eax
0x18001611d  xor     eax, eax
0x18001611f  test    ecx, ecx
0x180016121  setnz   al
0x180016124  or      edx, 0FFFFFFFFh
0x180016127  test    ecx, ecx
0x180016129  cmovs   eax, edx
0x18001612c  add     rsp, 30h
0x180016130  pop     rbx
0x180016131  retn
```
