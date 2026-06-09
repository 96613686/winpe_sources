# _ProcessNewXmlElement_::_1_::dtor$2

- ea: `0x180011ac0`
- end: `0x180011ae6`
- name: `_ProcessNewXmlElement_::_1_::dtor$2`
- size: `38`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180008ebc`
- `0x180011ac0`

## pseudocode

```c
__int64 __fastcall ProcessNewXmlElement_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 64) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 64) &= ~1u;
    return std::shared_ptr<CConfigSet>::~shared_ptr<CConfigSet>(a2 + 112);
  }
  return result;
}

```

## disassembly

```asm
0x180011ac0  push    rbp
0x180011ac2  sub     rsp, 20h
0x180011ac6  mov     rbp, rdx
0x180011ac9  mov     eax, [rbp+40h]
0x180011acc  and     eax, 1
0x180011acf  test    eax, eax
0x180011ad1  jz      short loc_180011AE0
0x180011ad3  and     dword ptr [rbp+40h], 0FFFFFFFEh
0x180011ad7  lea     rcx, [rbp+70h]
0x180011adb  call    ??1?$shared_ptr@VCConfigSet@@@std@@QEAA@XZ; std::shared_ptr<CConfigSet>::~shared_ptr<CConfigSet>(void)
0x180011ae0  add     rsp, 20h
0x180011ae4  pop     rbp
0x180011ae5  retn
```
