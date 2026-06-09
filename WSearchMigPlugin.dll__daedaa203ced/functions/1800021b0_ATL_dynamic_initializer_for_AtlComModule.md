# ATL::_dynamic_initializer_for___AtlComModule__

- ea: `0x1800021b0`
- end: `0x1800021e7`
- name: `ATL::_dynamic_initializer_for___AtlComModule__`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800021b0`
- `0x180002b7c`
- `0x18000b69c`

## pseudocode

```c
int ATL::_dynamic_initializer_for___AtlComModule__()
{
  if ( (int)ATL::CComCriticalSection::Init(&stru_180025530) >= 0 )
    ATL::_AtlComModule = 72;
  else
    ATL::CAtlBaseModule::m_bInitFailed = 1;
  return atexit((void (__cdecl *)())ATL::_dynamic_atexit_destructor_for___AtlComModule__);
}

```

## disassembly

```asm
0x1800021b0  sub     rsp, 28h
0x1800021b4  lea     rcx, stru_180025530; this
0x1800021bb  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800021c0  test    eax, eax
0x1800021c2  jns     short loc_1800021CD
0x1800021c4  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x1800021cb  jmp     short loc_1800021D7
0x1800021cd  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 48h ; 'H'; ATL::CAtlComModule ATL::_AtlComModule
0x1800021d7  lea     rcx, ATL___dynamic_atexit_destructor_for___AtlComModule__
0x1800021de  add     rsp, 28h
0x1800021e2  jmp     atexit
```
