# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x180004730`
- end: `0x180004768`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `56`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000440c`
- `0x180004730`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180004730  sub     rsp, 28h
0x180004734  test    rdx, rdx
0x180004737  jz      short loc_18000475E
0x180004739  test    r8, r8
0x18000473c  jz      short loc_18000475E
0x18000473e  mov     [rsp+28h+arg_8], 0
0x180004747  add     rcx, 8; this
0x18000474b  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180004750  nop
0x180004751  neg     eax
0x180004753  sbb     eax, eax
0x180004755  not     eax
0x180004757  and     eax, 8007000Eh
0x18000475c  jmp     short loc_180004763
0x18000475e  mov     eax, 80070057h
0x180004763  add     rsp, 28h
0x180004767  retn
```
