# __Wrapper<WmiSecurity>::~__Wrapper<WmiSecurity>(void)

- ea: `0x140006820`
- end: `0x14000684f`
- name: `??1?$__Wrapper@VWmiSecurity@@@@UEAA@XZ`
- size: `47`
- prototype: `void **__fastcall(_QWORD *, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140006864`
- `0x1400068c0`
- `0x1400069e0`

## callees

- `0x140006820`
- `0x140006a18`

## pseudocode

```c
void **__fastcall __Wrapper<WmiSecurity>::~__Wrapper<WmiSecurity>(_QWORD *a1, unsigned int a2)
{
  void **result; // rax
  WmiSecurity *v4; // rcx

  result = &__Wrapper<WmiSecurity>::`vftable';
  *a1 = &__Wrapper<WmiSecurity>::`vftable';
  v4 = (WmiSecurity *)a1[1];
  if ( v4 )
  {
    result = (void **)WmiSecurity::`scalar deleting destructor'(v4, a2);
    a1[1] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140006820  push    rbx
0x140006822  sub     rsp, 20h
0x140006826  lea     rax, ??_7?$__Wrapper@VWmiSecurity@@@@6B@; const __Wrapper<WmiSecurity>::`vftable'
0x14000682d  mov     rbx, rcx
0x140006830  mov     [rcx], rax
0x140006833  mov     rcx, [rcx+8]; this
0x140006837  test    rcx, rcx
0x14000683a  jz      short loc_140006849
0x14000683c  call    ??_GWmiSecurity@@QEAAPEAXI@Z; WmiSecurity::`scalar deleting destructor'(uint)
0x140006841  mov     qword ptr [rbx+8], 0
0x140006849  add     rsp, 20h
0x14000684d  pop     rbx
0x14000684e  retn
```
