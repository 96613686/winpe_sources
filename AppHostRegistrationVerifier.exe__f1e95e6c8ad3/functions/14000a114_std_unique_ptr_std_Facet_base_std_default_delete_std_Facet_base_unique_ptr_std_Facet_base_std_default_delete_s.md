# std::unique_ptr<std::_Facet_base,std::default_delete<std::_Facet_base>>::~unique_ptr<std::_Facet_base,std::default_delete<std::_Facet_base>>(void)

- ea: `0x14000a114`
- end: `0x14000a135`
- name: `??1?$unique_ptr@V_Facet_base@std@@U?$default_delete@V_Facet_base@std@@@2@@std@@QEAA@XZ`
- size: `33`
- prototype: `__int64 __fastcall(__int64 (__fastcall ****)(_QWORD, __int64))`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000989c`
- `0x1400113c4`

## callees

- `0x14000a114`
- `0x140012010`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<std::_Facet_base>::~unique_ptr<std::_Facet_base>(
        __int64 (__fastcall ****a1)(_QWORD, __int64))
{
  __int64 (__fastcall ***v1)(_QWORD, __int64); // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (**v1)(v1, 1);
  return result;
}

```

## disassembly

```asm
0x14000a114  sub     rsp, 28h
0x14000a118  mov     rcx, [rcx]
0x14000a11b  test    rcx, rcx
0x14000a11e  jz      short loc_14000A130
0x14000a120  mov     rax, [rcx]
0x14000a123  mov     edx, 1
0x14000a128  mov     rax, [rax]
0x14000a12b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a130  add     rsp, 28h
0x14000a134  retn
```
