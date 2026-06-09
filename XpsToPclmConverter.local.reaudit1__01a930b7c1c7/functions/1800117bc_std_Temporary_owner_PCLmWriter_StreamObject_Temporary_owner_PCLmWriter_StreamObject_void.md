# std::_Temporary_owner<PCLmWriter::StreamObject>::~_Temporary_owner<PCLmWriter::StreamObject>(void)

- ea: `0x1800117bc`
- end: `0x1800117dd`
- name: `??1?$_Temporary_owner@VStreamObject@PCLmWriter@@@std@@QEAA@XZ`
- size: `33`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180012a80`
- `0x18001d70c`

## callees

- `0x1800117bc`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall std::_Temporary_owner<PCLmWriter::StreamObject>::~_Temporary_owner<PCLmWriter::StreamObject>(
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
0x1800117bc  sub     rsp, 28h
0x1800117c0  mov     rcx, [rcx]
0x1800117c3  test    rcx, rcx
0x1800117c6  jz      short loc_1800117D8
0x1800117c8  mov     rax, [rcx]
0x1800117cb  mov     edx, 1
0x1800117d0  mov     rax, [rax]
0x1800117d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800117d8  add     rsp, 28h
0x1800117dc  retn
```
