# _errctrctlib::ComApiErrorContract__lambda_d697201f0e940cc49f30cd307c600d23____::_1_::catch$1

- ea: `0x1400119ac`
- end: `0x1400119e1`
- name: `_errctrctlib::ComApiErrorContract__lambda_d697201f0e940cc49f30cd307c600d23____::_1_::catch$1`
- size: `53`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400119ac`

## pseudocode

```c
__int64 __fastcall errctrctlib::ComApiErrorContract__lambda_d697201f0e940cc49f30cd307c600d23____::_1_::catch_1(
        __int64 a1,
        __int64 a2)
{
  signed int v2; // ecx

  v2 = *(_DWORD *)(*(_QWORD *)(a2 + 32) + 24LL);
  if ( v2 > 0 )
    v2 = (unsigned __int16)v2 | 0x80070000;
  *(_DWORD *)(a2 + 80) = v2;
  return 0;
}

```

## disassembly

```asm
0x1400119ac  mov     [rsp+arg_8], rdx
0x1400119b1  push    rbp
0x1400119b2  sub     rsp, 20h
0x1400119b6  mov     rbp, rdx
0x1400119b9  mov     rax, [rbp+20h]
0x1400119bd  mov     ecx, [rax+18h]
0x1400119c0  test    ecx, ecx
0x1400119c2  jle     short loc_1400119CD
0x1400119c4  movzx   ecx, cx
0x1400119c7  or      ecx, 80070000h
0x1400119cd  mov     [rbp+50h], ecx
0x1400119d0  mov     rax, 0
0x1400119da  add     rsp, 20h
0x1400119de  pop     rbp
0x1400119df  retn
```
