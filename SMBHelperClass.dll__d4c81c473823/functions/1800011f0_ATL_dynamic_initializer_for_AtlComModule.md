# ATL::_dynamic_initializer_for___AtlComModule__

- ea: `0x1800011f0`
- end: `0x180001227`
- name: `ATL::_dynamic_initializer_for___AtlComModule__`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800011f0`
- `0x180002518`
- `0x1800058dc`

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
0x1800011f0  sub     rsp, 28h
0x1800011f4  lea     rcx, CriticalSection; this
0x1800011fb  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180001200  test    eax, eax
0x180001202  jns     short loc_18000120D
0x180001204  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x18000120b  jmp     short loc_180001217
0x18000120d  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 48h ; 'H'; ATL::CAtlComModule ATL::_AtlComModule
0x180001217  lea     rcx, ATL___dynamic_atexit_destructor_for___AtlComModule__
0x18000121e  add     rsp, 28h
0x180001222  jmp     atexit
```
