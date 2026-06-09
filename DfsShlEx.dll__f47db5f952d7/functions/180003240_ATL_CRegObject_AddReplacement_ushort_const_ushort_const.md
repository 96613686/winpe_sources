# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x180003240`
- end: `0x180003278`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `56`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002e98`
- `0x180003240`

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
0x180003240  sub     rsp, 28h
0x180003244  test    rdx, rdx
0x180003247  jz      short loc_18000326E
0x180003249  test    r8, r8
0x18000324c  jz      short loc_18000326E
0x18000324e  mov     [rsp+28h+arg_8], 0
0x180003257  add     rcx, 8; this
0x18000325b  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180003260  nop
0x180003261  neg     eax
0x180003263  sbb     eax, eax
0x180003265  not     eax
0x180003267  and     eax, 8007000Eh
0x18000326c  jmp     short loc_180003273
0x18000326e  mov     eax, 80070057h
0x180003273  add     rsp, 28h
0x180003277  retn
```
