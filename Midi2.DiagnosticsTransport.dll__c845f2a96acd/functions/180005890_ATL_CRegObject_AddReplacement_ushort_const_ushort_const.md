# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x180005890`
- end: `0x1800058c8`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `56`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180005568`
- `0x180005890`

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
0x180005890  sub     rsp, 28h
0x180005894  test    rdx, rdx
0x180005897  jz      short loc_1800058BE
0x180005899  test    r8, r8
0x18000589c  jz      short loc_1800058BE
0x18000589e  mov     [rsp+28h+arg_8], 0
0x1800058a7  add     rcx, 8; this
0x1800058ab  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1800058b0  nop
0x1800058b1  neg     eax
0x1800058b3  sbb     eax, eax
0x1800058b5  not     eax
0x1800058b7  and     eax, 8007000Eh
0x1800058bc  jmp     short loc_1800058C3
0x1800058be  mov     eax, 80070057h
0x1800058c3  add     rsp, 28h
0x1800058c7  retn
```
