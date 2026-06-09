# ATL::_dynamic_initializer_for___AtlComModule__

- ea: `0x180001750`
- end: `0x180001787`
- name: `ATL::_dynamic_initializer_for___AtlComModule__`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001750`
- `0x180001d50`
- `0x180005670`

## pseudocode

```c
int ATL::_dynamic_initializer_for___AtlComModule__()
{
  if ( (int)ATL::CComCriticalSection::Init(&stru_1800202F0) >= 0 )
    ATL::_AtlComModule = 72;
  else
    ATL::CAtlBaseModule::m_bInitFailed = 1;
  return atexit((void (__cdecl *)())ATL::_dynamic_atexit_destructor_for___AtlComModule__);
}

```

## disassembly

```asm
0x180001750  sub     rsp, 28h
0x180001754  lea     rcx, stru_1800202F0; this
0x18000175b  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180001760  test    eax, eax
0x180001762  jns     short loc_18000176D
0x180001764  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x18000176b  jmp     short loc_180001777
0x18000176d  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 48h ; 'H'; ATL::CAtlComModule ATL::_AtlComModule
0x180001777  lea     rcx, ATL___dynamic_atexit_destructor_for___AtlComModule__
0x18000177e  add     rsp, 28h
0x180001782  jmp     atexit
```
