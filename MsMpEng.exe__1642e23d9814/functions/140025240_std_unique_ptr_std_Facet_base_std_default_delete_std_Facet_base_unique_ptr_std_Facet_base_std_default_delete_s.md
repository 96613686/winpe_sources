# std::unique_ptr<std::_Facet_base,std::default_delete<std::_Facet_base>>::~unique_ptr<std::_Facet_base,std::default_delete<std::_Facet_base>>(void)

- ea: `0x140025240`
- end: `0x140025262`
- name: `??1?$unique_ptr@V_Facet_base@std@@U?$default_delete@V_Facet_base@std@@@2@@std@@QEAA@XZ`
- size: `34`
- prototype: `__int64 __fastcall(__int64 (__fastcall ****)(_QWORD, __int64))`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14002b3b4`

## callees

- `0x140025240`
- `0x140029bd0`

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
0x140025240  sub     rsp, 28h
0x140025244  mov     rcx, [rcx]
0x140025247  test    rcx, rcx
0x14002524a  jz      short loc_14002525D
0x14002524c  mov     rax, [rcx]
0x14002524f  mov     edx, 1
0x140025254  mov     rax, [rax]
0x140025257  call    cs:__guard_dispatch_icall_fptr
0x14002525d  add     rsp, 28h
0x140025261  retn
```
