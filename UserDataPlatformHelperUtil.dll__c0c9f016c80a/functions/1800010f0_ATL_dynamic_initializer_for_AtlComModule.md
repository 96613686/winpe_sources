# ATL::_dynamic_initializer_for___AtlComModule__

- ea: `0x1800010f0`
- end: `0x180001127`
- name: `ATL::_dynamic_initializer_for___AtlComModule__`
- size: `55`
- prototype: `int()`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800010f0`
- `0x1800017c4`
- `0x18000439c`

## pseudocode

```c
int ATL::_dynamic_initializer_for___AtlComModule__()
{
  if ( (int)ATL::CComCriticalSection::Init(&CriticalSection) >= 0 )
    ATL::_AtlComModule = 72;
  else
    ATL::CAtlBaseModule::m_bInitFailed = 1;
  return atexit(ATL::_dynamic_atexit_destructor_for___AtlComModule__);
}

```

## disassembly

```asm
0x1800010f0  sub     rsp, 28h
0x1800010f4  lea     rcx, CriticalSection; this
0x1800010fb  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180001100  test    eax, eax
0x180001102  jns     short loc_18000110D
0x180001104  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x18000110b  jmp     short loc_180001117
0x18000110d  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 48h ; 'H'; ATL::CAtlComModule ATL::_AtlComModule
0x180001117  lea     rcx, ATL___dynamic_atexit_destructor_for___AtlComModule__
0x18000111e  add     rsp, 28h
0x180001122  jmp     atexit
```
