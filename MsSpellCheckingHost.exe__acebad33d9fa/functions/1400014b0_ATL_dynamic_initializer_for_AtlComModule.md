# ATL::_dynamic_initializer_for___AtlComModule__

- ea: `0x1400014b0`
- end: `0x1400014e7`
- name: `ATL::_dynamic_initializer_for___AtlComModule__`
- size: `55`
- prototype: `int()`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400014b0`
- `0x140001cc4`
- `0x140003dfc`

## pseudocode

```c
int ATL::_dynamic_initializer_for___AtlComModule__()
{
  if ( (int)ATL::CComCriticalSection::Init(&stru_14001B2F0) >= 0 )
    ATL::_AtlComModule = 72;
  else
    ATL::CAtlBaseModule::m_bInitFailed = 1;
  return atexit(ATL::_dynamic_atexit_destructor_for___AtlComModule__);
}

```

## disassembly

```asm
0x1400014b0  sub     rsp, 28h
0x1400014b4  lea     rcx, stru_14001B2F0; this
0x1400014bb  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1400014c0  test    eax, eax
0x1400014c2  jns     short loc_1400014CD
0x1400014c4  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x1400014cb  jmp     short loc_1400014D7
0x1400014cd  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 48h ; 'H'; ATL::CAtlComModule ATL::_AtlComModule
0x1400014d7  lea     rcx, ATL___dynamic_atexit_destructor_for___AtlComModule__
0x1400014de  add     rsp, 28h
0x1400014e2  jmp     atexit
```
