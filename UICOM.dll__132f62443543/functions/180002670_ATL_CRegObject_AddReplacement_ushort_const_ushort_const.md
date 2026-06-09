# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x180002670`
- end: `0x18000269e`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `46`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002448`
- `0x180002670`

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
0x180002670  sub     rsp, 28h
0x180002674  test    rdx, rdx
0x180002677  jz      short loc_180002694
0x180002679  test    r8, r8
0x18000267c  jz      short loc_180002694
0x18000267e  add     rcx, 8; this
0x180002682  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180002687  neg     eax
0x180002689  sbb     eax, eax
0x18000268b  not     eax
0x18000268d  and     eax, 8007000Eh
0x180002692  jmp     short loc_180002699
0x180002694  mov     eax, 80070057h
0x180002699  add     rsp, 28h
0x18000269d  retn
```
