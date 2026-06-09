# ATL::_dynamic_initializer_for___AtlComModule__

- ea: `0x180001f60`
- end: `0x180001f97`
- name: `ATL::_dynamic_initializer_for___AtlComModule__`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001f60`
- `0x180003d10`
- `0x180007aa8`

## pseudocode

```c
int ATL::_dynamic_initializer_for___AtlComModule__()
{
  if ( (int)ATL::CComCriticalSection::Init(&stru_18002D110) >= 0 )
    ATL::_AtlComModule = 72;
  else
    ATL::CAtlBaseModule::m_bInitFailed = 1;
  return atexit((void (__cdecl *)())ATL::_dynamic_atexit_destructor_for___AtlComModule__);
}

```

## disassembly

```asm
0x180001f60  sub     rsp, 28h
0x180001f64  lea     rcx, stru_18002D110; this
0x180001f6b  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180001f70  test    eax, eax
0x180001f72  jns     short loc_180001F7D
0x180001f74  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x180001f7b  jmp     short loc_180001F87
0x180001f7d  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 48h ; 'H'; ATL::CAtlComModule ATL::_AtlComModule
0x180001f87  lea     rcx, ATL___dynamic_atexit_destructor_for___AtlComModule__
0x180001f8e  add     rsp, 28h
0x180001f92  jmp     atexit
```
