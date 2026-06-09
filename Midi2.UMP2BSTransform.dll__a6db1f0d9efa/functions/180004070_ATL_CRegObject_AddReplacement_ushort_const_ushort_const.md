# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x180004070`
- end: `0x1800040a8`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `56`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180003d48`
- `0x180004070`

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
0x180004070  sub     rsp, 28h
0x180004074  test    rdx, rdx
0x180004077  jz      short loc_18000409E
0x180004079  test    r8, r8
0x18000407c  jz      short loc_18000409E
0x18000407e  mov     [rsp+28h+arg_8], 0
0x180004087  add     rcx, 8; this
0x18000408b  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180004090  nop
0x180004091  neg     eax
0x180004093  sbb     eax, eax
0x180004095  not     eax
0x180004097  and     eax, 8007000Eh
0x18000409c  jmp     short loc_1800040A3
0x18000409e  mov     eax, 80070057h
0x1800040a3  add     rsp, 28h
0x1800040a7  retn
```
