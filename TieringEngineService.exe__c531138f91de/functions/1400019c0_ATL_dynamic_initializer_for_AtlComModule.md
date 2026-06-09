# ATL::_dynamic_initializer_for___AtlComModule__

- ea: `0x1400019c0`
- end: `0x1400019f7`
- name: `ATL::_dynamic_initializer_for___AtlComModule__`
- size: `55`
- prototype: `int()`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400019c0`
- `0x140001fe4`
- `0x1400035bc`

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
0x1400019c0  sub     rsp, 28h
0x1400019c4  lea     rcx, CriticalSection; this
0x1400019cb  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1400019d0  test    eax, eax
0x1400019d2  jns     short loc_1400019DD
0x1400019d4  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x1400019db  jmp     short loc_1400019E7
0x1400019dd  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 48h ; 'H'; ATL::CAtlComModule ATL::_AtlComModule
0x1400019e7  lea     rcx, ATL___dynamic_atexit_destructor_for___AtlComModule__
0x1400019ee  add     rsp, 28h
0x1400019f2  jmp     atexit
```
