# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x180005250`
- end: `0x180005288`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `56`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180004f28`
- `0x180005250`

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
0x180005250  sub     rsp, 28h
0x180005254  test    rdx, rdx
0x180005257  jz      short loc_18000527E
0x180005259  test    r8, r8
0x18000525c  jz      short loc_18000527E
0x18000525e  mov     [rsp+28h+arg_8], 0
0x180005267  add     rcx, 8; this
0x18000526b  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180005270  nop
0x180005271  neg     eax
0x180005273  sbb     eax, eax
0x180005275  not     eax
0x180005277  and     eax, 8007000Eh
0x18000527c  jmp     short loc_180005283
0x18000527e  mov     eax, 80070057h
0x180005283  add     rsp, 28h
0x180005287  retn
```
