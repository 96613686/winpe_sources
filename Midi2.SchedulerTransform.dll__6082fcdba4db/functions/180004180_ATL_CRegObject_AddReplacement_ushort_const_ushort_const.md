# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x180004180`
- end: `0x1800041b8`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `56`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180003e5c`
- `0x180004180`

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
0x180004180  sub     rsp, 28h
0x180004184  test    rdx, rdx
0x180004187  jz      short loc_1800041AE
0x180004189  test    r8, r8
0x18000418c  jz      short loc_1800041AE
0x18000418e  mov     [rsp+28h+arg_8], 0
0x180004197  add     rcx, 8; this
0x18000419b  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1800041a0  nop
0x1800041a1  neg     eax
0x1800041a3  sbb     eax, eax
0x1800041a5  not     eax
0x1800041a7  and     eax, 8007000Eh
0x1800041ac  jmp     short loc_1800041B3
0x1800041ae  mov     eax, 80070057h
0x1800041b3  add     rsp, 28h
0x1800041b7  retn
```
