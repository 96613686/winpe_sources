# std::tr1::shared_ptr<IRegistryMultiStringValue>::shared_ptr<IRegistryMultiStringValue>(std::tr1::shared_ptr<IRegistryMultiStringValue> const &)

- ea: `0x1800221e0`
- end: `0x180022228`
- name: `??0?$shared_ptr@VIRegistryMultiStringValue@@@tr1@std@@QEAA@AEBV012@@Z`
- size: `72`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ddc0`

## callees

- `0x180021098`
- `0x1800221e0`

## pseudocode

```c
_QWORD *__fastcall std::tr1::shared_ptr<IRegistryMultiStringValue>::shared_ptr<IRegistryMultiStringValue>(
        _QWORD *a1,
        __int64 *a2)
{
  __int64 v3; // r8
  __int64 v4; // rdx
  signed __int32 v5; // eax

  *a1 = 0;
  a1[1] = 0;
  v3 = a2[1];
  v4 = *a2;
  if ( v3 )
  {
    while ( 1 )
    {
      v5 = *(_DWORD *)(v3 + 8);
      if ( !v5 )
        break;
      if ( v5 == _InterlockedCompareExchange((volatile signed __int32 *)(v3 + 8), v5 + 1, v5) )
      {
        std::tr1::_Ptr_base<IRegistryMultiStringValue>::_Reset0(a1, v4, v3);
        return a1;
      }
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1800221e0  push    rbx
0x1800221e2  sub     rsp, 20h
0x1800221e6  mov     qword ptr [rcx], 0
0x1800221ed  mov     rbx, rcx
0x1800221f0  mov     qword ptr [rcx+8], 0
0x1800221f8  mov     r8, [rdx+8]
0x1800221fc  mov     rdx, [rdx]
0x1800221ff  test    r8, r8
0x180022202  jz      short loc_18002221F
0x180022204  mov     eax, [r8+8]
0x180022208  test    eax, eax
0x18002220a  jz      short loc_18002221F
0x18002220c  lea     ecx, [rax+1]
0x18002220f  lock cmpxchg [r8+8], ecx
0x180022215  jnz     short loc_180022204
0x180022217  mov     rcx, rbx
0x18002221a  call    ?_Reset0@?$_Ptr_base@VIRegistryMultiStringValue@@@tr1@std@@QEAAXPEAVIRegistryMultiStringValue@@PEAV_Ref_count_base@23@@Z; std::tr1::_Ptr_base<IRegistryMultiStringValue>::_Reset0(IRegistryMultiStringValue *,std::tr1::_Ref_count_base *)
0x18002221f  mov     rax, rbx
0x180022222  add     rsp, 20h
0x180022226  pop     rbx
0x180022227  retn
```
