# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x180006750`
- end: `0x18000677e`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `46`
- prototype: `__int64 __fastcall(void **this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180006468`
- `0x180006750`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::AddReplacement(void **this, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  if ( a2 && a3 )
    return !ATL::CExpansionVector::Add(this + 1, a2, a3) ? 0x8007000E : 0;
  else
    return 2147942487LL;
}

```

## disassembly

```asm
0x180006750  sub     rsp, 28h
0x180006754  test    rdx, rdx
0x180006757  jz      short loc_180006774
0x180006759  test    r8, r8
0x18000675c  jz      short loc_180006774
0x18000675e  add     rcx, 8; this
0x180006762  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180006767  neg     eax
0x180006769  sbb     eax, eax
0x18000676b  not     eax
0x18000676d  and     eax, 8007000Eh
0x180006772  jmp     short loc_180006779
0x180006774  mov     eax, 80070057h
0x180006779  add     rsp, 28h
0x18000677d  retn
```
