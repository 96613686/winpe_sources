# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x180003b40`
- end: `0x180003b90`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `80`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180003988`
- `0x180003b40`
- `0x180007700`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::AddReplacement(
        ATL::CRegObject *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  if ( a2 && a3 )
    return ATL::CExpansionVector::Add((ATL::CRegObject *)((char *)this + 8), a2, a3) == 0 ? 0x8007000E : 0;
  else
    return 2147942487LL;
}

```

## disassembly

```asm
0x180003b40  sub     rsp, 38h
0x180003b44  mov     rax, cs:__security_cookie
0x180003b4b  xor     rax, rsp
0x180003b4e  mov     [rsp+38h+var_10], rax
0x180003b53  test    rdx, rdx
0x180003b56  jz      short loc_180003B79
0x180003b58  test    r8, r8
0x180003b5b  jz      short loc_180003B79
0x180003b5d  and     [rsp+38h+var_18], 0
0x180003b63  add     rcx, 8; this
0x180003b67  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180003b6c  neg     eax
0x180003b6e  sbb     eax, eax
0x180003b70  not     eax
0x180003b72  and     eax, 8007000Eh
0x180003b77  jmp     short loc_180003B7E
0x180003b79  mov     eax, 80070057h
0x180003b7e  mov     rcx, [rsp+38h+var_10]
0x180003b83  xor     rcx, rsp; StackCookie
0x180003b86  call    __security_check_cookie
0x180003b8b  add     rsp, 38h
0x180003b8f  retn
```
