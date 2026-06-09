# FilterAgent::FilterAgent(std::unique_ptr<FilterBasicParameter,std::default_delete<FilterBasicParameter>>)

- ea: `0x18000eeb8`
- end: `0x18000eef9`
- name: `??0FilterAgent@@QEAA@V?$unique_ptr@VFilterBasicParameter@@U?$default_delete@VFilterBasicParameter@@@std@@@std@@@Z`
- size: `65`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800104e4`

## callees

- `0x18000eeb8`
- `0x180024010`

## pseudocode

```c
__int64 __fastcall FilterAgent::FilterAgent(__int64 a1, _QWORD *a2)
{
  void (__fastcall ***v3)(_QWORD, __int64); // rax

  *(_WORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  v3 = (void (__fastcall ***)(_QWORD, __int64))*a2;
  *a2 = 0;
  *(_QWORD *)(a1 + 16) = v3;
  *(_BYTE *)a1 = 0;
  if ( *a2 )
    (**(void (__fastcall ***)(_QWORD, __int64))*a2)(*a2, 1);
  return a1;
}

```

## disassembly

```asm
0x18000eeb8  push    rbx
0x18000eeba  sub     rsp, 20h
0x18000eebe  xor     r8d, r8d
0x18000eec1  mov     rbx, rcx
0x18000eec4  mov     [rcx], r8w
0x18000eec8  mov     [rcx+8], r8
0x18000eecc  mov     rax, [rdx]
0x18000eecf  mov     [rdx], r8
0x18000eed2  mov     [rcx+10h], rax
0x18000eed6  mov     [rcx], r8b
0x18000eed9  mov     rcx, [rdx]
0x18000eedc  test    rcx, rcx
0x18000eedf  jz      short loc_18000EEF0
0x18000eee1  mov     rax, [rcx]
0x18000eee4  lea     edx, [r8+1]
0x18000eee8  mov     rax, [rax]
0x18000eeeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eef0  mov     rax, rbx
0x18000eef3  add     rsp, 20h
0x18000eef7  pop     rbx
0x18000eef8  retn
```
