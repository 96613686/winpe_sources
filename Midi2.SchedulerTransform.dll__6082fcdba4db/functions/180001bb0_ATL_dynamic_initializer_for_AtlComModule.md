# ATL::_dynamic_initializer_for___AtlComModule__

- ea: `0x180001bb0`
- end: `0x180001be7`
- name: `ATL::_dynamic_initializer_for___AtlComModule__`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001bb0`
- `0x180002420`
- `0x180005d08`

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
0x180001bb0  sub     rsp, 28h
0x180001bb4  lea     rcx, CriticalSection; this
0x180001bbb  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180001bc0  test    eax, eax
0x180001bc2  jns     short loc_180001BCD
0x180001bc4  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x180001bcb  jmp     short loc_180001BD7
0x180001bcd  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 48h ; 'H'; ATL::CAtlComModule ATL::_AtlComModule
0x180001bd7  lea     rcx, ATL___dynamic_atexit_destructor_for___AtlComModule__
0x180001bde  add     rsp, 28h
0x180001be2  jmp     atexit
```
