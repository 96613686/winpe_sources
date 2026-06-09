# __Wrapper<WmiSecurity>::`scalar deleting destructor'(uint)

- ea: `0x1400069e0`
- end: `0x140006a10`
- name: `??_G?$__Wrapper@VWmiSecurity@@@@UEAAPEAXI@Z`
- size: `48`
- prototype: `_QWORD *__fastcall(_QWORD *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140006820`
- `0x1400069e0`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1400069fc`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1400069fc`

## pseudocode

```c
_QWORD *__fastcall __Wrapper<WmiSecurity>::`scalar deleting destructor'(_QWORD *a1, unsigned int a2)
{
  char v2; // bl

  v2 = a2;
  __Wrapper<WmiSecurity>::~__Wrapper<WmiSecurity>(a1, a2);
  if ( (v2 & 1) != 0 )
    CWin32DefaultArena::WbemMemFree(a1);
  return a1;
}

```

## disassembly

```asm
0x1400069e0  mov     [rsp+arg_0], rbx
0x1400069e5  push    rdi
0x1400069e6  sub     rsp, 20h
0x1400069ea  mov     ebx, edx
0x1400069ec  mov     rdi, rcx
0x1400069ef  call    ??1?$__Wrapper@VWmiSecurity@@@@UEAA@XZ; __Wrapper<WmiSecurity>::~__Wrapper<WmiSecurity>(void)
0x1400069f4  test    bl, 1
0x1400069f7  jz      short loc_140006A02
0x1400069f9  mov     rcx, rdi
0x1400069fc  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x140006a02  mov     rax, rdi
0x140006a05  mov     rbx, [rsp+28h+arg_0]
0x140006a0a  add     rsp, 20h
0x140006a0e  pop     rdi
0x140006a0f  retn
```
