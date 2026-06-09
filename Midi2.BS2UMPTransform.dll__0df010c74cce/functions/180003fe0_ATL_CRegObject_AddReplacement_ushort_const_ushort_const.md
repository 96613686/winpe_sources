# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x180003fe0`
- end: `0x180004018`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `56`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180003cb8`
- `0x180003fe0`

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
0x180003fe0  sub     rsp, 28h
0x180003fe4  test    rdx, rdx
0x180003fe7  jz      short loc_18000400E
0x180003fe9  test    r8, r8
0x180003fec  jz      short loc_18000400E
0x180003fee  mov     [rsp+28h+arg_8], 0
0x180003ff7  add     rcx, 8; this
0x180003ffb  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180004000  nop
0x180004001  neg     eax
0x180004003  sbb     eax, eax
0x180004005  not     eax
0x180004007  and     eax, 8007000Eh
0x18000400c  jmp     short loc_180004013
0x18000400e  mov     eax, 80070057h
0x180004013  add     rsp, 28h
0x180004017  retn
```
