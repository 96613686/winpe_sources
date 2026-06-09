# std::collate<char>::do_compare(char const *,char const *,char const *,char const *)

- ea: `0x180020530`
- end: `0x180020572`
- name: `?do_compare@?$collate@D@std@@MEBAHPEBD000@Z`
- size: `66`
- prototype: `__int64 __fastcall(const _Collvec *, const char *, const char *, const char *, char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180022d4c`

## pseudocode

```c
__int64 __fastcall std::collate<char>::do_compare(
        const _Collvec *a1,
        const char *a2,
        const char *a3,
        const char *a4,
        char *a5)
{
  int v5; // ecx
  __int64 result; // rax

  v5 = Strcoll(a2, a3, a4, a5, a1 + 1);
  result = v5 != 0;
  if ( v5 < 0 )
    return 0xFFFFFFFFLL;
  return result;
}

```

## disassembly

```asm
0x180020530  push    rbx
0x180020532  sub     rsp, 30h
0x180020536  mov     r10, r9
0x180020539  lea     rax, [rcx+10h]
0x18002053d  mov     r9, [rsp+38h+arg_20]; char *
0x180020542  mov     r11, r8
0x180020545  mov     rbx, rdx
0x180020548  mov     [rsp+38h+var_18], rax; _Collvec *
0x18002054d  mov     r8, r10; char *
0x180020550  mov     rdx, r11; char *
0x180020553  mov     rcx, rbx; char *
0x180020556  call    _Strcoll
0x18002055b  mov     ecx, eax
0x18002055d  xor     eax, eax
0x18002055f  test    ecx, ecx
0x180020561  setnz   al
0x180020564  or      edx, 0FFFFFFFFh
0x180020567  test    ecx, ecx
0x180020569  cmovs   eax, edx
0x18002056c  add     rsp, 30h
0x180020570  pop     rbx
0x180020571  retn
```
