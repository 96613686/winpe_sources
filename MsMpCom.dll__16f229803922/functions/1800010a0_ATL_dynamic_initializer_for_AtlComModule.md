# ATL::_dynamic_initializer_for___AtlComModule__

- ea: `0x1800010a0`
- end: `0x1800010d7`
- name: `ATL::_dynamic_initializer_for___AtlComModule__`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800010a0`
- `0x180001b78`
- `0x18000233c`

## pseudocode

```c
int ATL::_dynamic_initializer_for___AtlComModule__()
{
  if ( (int)ATL::CComCriticalSection::Init(&CriticalSection) >= 0 )
    ATL::_AtlComModule = 72;
  else
    ATL::CAtlBaseModule::m_bInitFailed = 1;
  return atexit((void (__cdecl *)())ATL::_dynamic_atexit_destructor_for___AtlComModule__);
}

```

## disassembly

```asm
0x1800010a0  sub     rsp, 28h
0x1800010a4  lea     rcx, CriticalSection; this
0x1800010ab  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800010b0  test    eax, eax
0x1800010b2  jns     short loc_1800010BD
0x1800010b4  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x1800010bb  jmp     short loc_1800010C7
0x1800010bd  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 48h ; 'H'; ATL::CAtlComModule ATL::_AtlComModule
0x1800010c7  lea     rcx, ATL___dynamic_atexit_destructor_for___AtlComModule__
0x1800010ce  add     rsp, 28h
0x1800010d2  jmp     atexit
```
