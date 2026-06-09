# __Wrapper<_SECURITY_ATTRIBUTES>::~__Wrapper<_SECURITY_ATTRIBUTES>(void)

- ea: `0x1400067e8`
- end: `0x140006818`
- name: `??1?$__Wrapper@U_SECURITY_ATTRIBUTES@@@@UEAA@XZ`
- size: `48`
- prototype: `int __fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140006858`
- `0x1400068c0`
- `0x1400069a0`

## callees

- `0x1400067e8`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140006804`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140006804`

## pseudocode

```c
int __fastcall __Wrapper<_SECURITY_ATTRIBUTES>::~__Wrapper<_SECURITY_ATTRIBUTES>(_QWORD *a1)
{
  void **v2; // rax
  void *v3; // rcx

  v2 = &__Wrapper<_SECURITY_ATTRIBUTES>::`vftable';
  *a1 = &__Wrapper<_SECURITY_ATTRIBUTES>::`vftable';
  v3 = (void *)a1[1];
  if ( v3 )
  {
    LODWORD(v2) = CWin32DefaultArena::WbemMemFree(v3);
    a1[1] = 0;
  }
  return (int)v2;
}

```

## disassembly

```asm
0x1400067e8  push    rbx
0x1400067ea  sub     rsp, 20h
0x1400067ee  mov     rbx, rcx
0x1400067f1  lea     rax, ??_7?$__Wrapper@U_SECURITY_ATTRIBUTES@@@@6B@; const __Wrapper<_SECURITY_ATTRIBUTES>::`vftable'
0x1400067f8  mov     [rcx], rax
0x1400067fb  mov     rcx, [rcx+8]
0x1400067ff  test    rcx, rcx
0x140006802  jz      short loc_140006812
0x140006804  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x14000680a  mov     qword ptr [rbx+8], 0
0x140006812  add     rsp, 20h
0x140006816  pop     rbx
0x140006817  retn
```
