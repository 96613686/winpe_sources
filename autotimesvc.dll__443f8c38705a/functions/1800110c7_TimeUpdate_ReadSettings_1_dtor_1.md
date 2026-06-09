# _TimeUpdate::ReadSettings_::_1_::dtor$1

- ea: `0x1800110c7`
- end: `0x1800110ed`
- name: `_TimeUpdate::ReadSettings_::_1_::dtor$1`
- size: `38`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x180005754`
- `0x1800110c7`

## pseudocode

```c
__int64 __fastcall TimeUpdate::ReadSettings_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 72) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 72) &= ~1u;
    return std::shared_ptr<Settings>::~shared_ptr<Settings>(*(_QWORD *)(a2 + 104));
  }
  return result;
}

```

## disassembly

```asm
0x1800110c7  push    rbp
0x1800110c9  sub     rsp, 20h
0x1800110cd  mov     rbp, rdx
0x1800110d0  mov     eax, [rbp+48h]
0x1800110d3  and     eax, 1
0x1800110d6  test    eax, eax
0x1800110d8  jz      short loc_1800110E7
0x1800110da  and     dword ptr [rbp+48h], 0FFFFFFFEh
0x1800110de  mov     rcx, [rbp+68h]
0x1800110e2  call    ??1?$shared_ptr@VSettings@@@std@@QEAA@XZ; std::shared_ptr<Settings>::~shared_ptr<Settings>(void)
0x1800110e7  add     rsp, 20h
0x1800110eb  pop     rbp
0x1800110ec  retn
```
