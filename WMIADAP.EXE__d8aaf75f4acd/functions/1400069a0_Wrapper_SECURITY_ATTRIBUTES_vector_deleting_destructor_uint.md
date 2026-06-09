# __Wrapper<_SECURITY_ATTRIBUTES>::`vector deleting destructor'(uint)

- ea: `0x1400069a0`
- end: `0x1400069d0`
- name: `??_E?$__Wrapper@U_SECURITY_ATTRIBUTES@@@@UEAAPEAXI@Z`
- size: `48`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400067e8`
- `0x1400069a0`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1400069bc`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1400069bc`

## pseudocode

```c
_QWORD *__fastcall __Wrapper<_SECURITY_ATTRIBUTES>::`vector deleting destructor'(_QWORD *a1, char a2)
{
  __Wrapper<_SECURITY_ATTRIBUTES>::~__Wrapper<_SECURITY_ATTRIBUTES>(a1);
  if ( (a2 & 1) != 0 )
    CWin32DefaultArena::WbemMemFree(a1);
  return a1;
}

```

## disassembly

```asm
0x1400069a0  mov     [rsp+arg_0], rbx
0x1400069a5  push    rdi
0x1400069a6  sub     rsp, 20h
0x1400069aa  mov     ebx, edx
0x1400069ac  mov     rdi, rcx
0x1400069af  call    ??1?$__Wrapper@U_SECURITY_ATTRIBUTES@@@@UEAA@XZ; __Wrapper<_SECURITY_ATTRIBUTES>::~__Wrapper<_SECURITY_ATTRIBUTES>(void)
0x1400069b4  test    bl, 1
0x1400069b7  jz      short loc_1400069C2
0x1400069b9  mov     rcx, rdi
0x1400069bc  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1400069c2  mov     rax, rdi
0x1400069c5  mov     rbx, [rsp+28h+arg_0]
0x1400069ca  add     rsp, 20h
0x1400069ce  pop     rdi
0x1400069cf  retn
```
