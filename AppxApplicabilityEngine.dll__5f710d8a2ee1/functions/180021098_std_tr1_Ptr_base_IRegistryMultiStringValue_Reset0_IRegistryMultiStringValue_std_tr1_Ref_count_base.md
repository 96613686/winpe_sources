# std::tr1::_Ptr_base<IRegistryMultiStringValue>::_Reset0(IRegistryMultiStringValue *,std::tr1::_Ref_count_base *)

- ea: `0x180021098`
- end: `0x1800210d5`
- name: `?_Reset0@?$_Ptr_base@VIRegistryMultiStringValue@@@tr1@std@@QEAAXPEAVIRegistryMultiStringValue@@PEAV_Ref_count_base@23@@Z`
- size: `61`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800200c8`
- `0x18002216c`
- `0x1800221e0`

## callees

- `0x180020edc`
- `0x180021098`

## pseudocode

```c
void __fastcall std::tr1::_Ptr_base<IRegistryMultiStringValue>::_Reset0(_QWORD *a1, __int64 a2, __int64 a3)
{
  std::tr1::_Ref_count_base *v5; // rcx

  v5 = (std::tr1::_Ref_count_base *)a1[1];
  if ( v5 )
    std::tr1::_Ref_count_base::_Decref(v5);
  *a1 = a2;
  a1[1] = a3;
}

```

## disassembly

```asm
0x180021098  mov     [rsp+arg_0], rbx
0x18002109d  mov     [rsp+arg_8], rsi
0x1800210a2  push    rdi
0x1800210a3  sub     rsp, 20h
0x1800210a7  mov     rbx, rcx
0x1800210aa  mov     rdi, r8
0x1800210ad  mov     rcx, [rcx+8]; this
0x1800210b1  mov     rsi, rdx
0x1800210b4  test    rcx, rcx
0x1800210b7  jz      short loc_1800210BE
0x1800210b9  call    ?_Decref@_Ref_count_base@tr1@std@@QEAAXXZ; std::tr1::_Ref_count_base::_Decref(void)
0x1800210be  mov     [rbx], rsi
0x1800210c1  mov     rsi, [rsp+28h+arg_8]
0x1800210c6  mov     [rbx+8], rdi
0x1800210ca  mov     rbx, [rsp+28h+arg_0]
0x1800210cf  add     rsp, 20h
0x1800210d3  pop     rdi
0x1800210d4  retn
```
