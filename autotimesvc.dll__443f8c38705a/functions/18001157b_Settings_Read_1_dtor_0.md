# _Settings::Read_::_1_::dtor$0

- ea: `0x18001157b`
- end: `0x1800115a1`
- name: `_Settings::Read_::_1_::dtor$0`
- size: `38`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180005754`
- `0x18001157b`

## pseudocode

```c
__int64 __fastcall Settings::Read_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 32) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    return std::shared_ptr<Settings>::~shared_ptr<Settings>(*(_QWORD *)(a2 + 64));
  }
  return result;
}

```

## disassembly

```asm
0x18001157b  push    rbp
0x18001157d  sub     rsp, 20h
0x180011581  mov     rbp, rdx
0x180011584  mov     eax, [rbp+20h]
0x180011587  and     eax, 1
0x18001158a  test    eax, eax
0x18001158c  jz      short loc_18001159B
0x18001158e  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x180011592  mov     rcx, [rbp+40h]
0x180011596  call    ??1?$shared_ptr@VSettings@@@std@@QEAA@XZ
0x18001159b  add     rsp, 20h
0x18001159f  pop     rbp
0x1800115a0  retn
```
