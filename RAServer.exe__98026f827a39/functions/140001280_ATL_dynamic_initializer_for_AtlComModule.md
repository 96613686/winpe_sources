# ATL::_dynamic_initializer_for___AtlComModule__

- ea: `0x140001280`
- end: `0x1400012b7`
- name: `ATL::_dynamic_initializer_for___AtlComModule__`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140001280`
- `0x140001e40`
- `0x1400072dc`

## pseudocode

```c
int ATL::_dynamic_initializer_for___AtlComModule__()
{
  if ( (int)ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)qword_140021200) >= 0 )
    ATL::_AtlComModule = 72;
  else
    ATL::CAtlBaseModule::m_bInitFailed = 1;
  return atexit((void (__cdecl *)())ATL::_dynamic_atexit_destructor_for___AtlComModule__);
}

```

## disassembly

```asm
0x140001280  sub     rsp, 28h
0x140001284  lea     rcx, qword_140021200; this
0x14000128b  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x140001290  test    eax, eax
0x140001292  jns     short loc_14000129D
0x140001294  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x14000129b  jmp     short loc_1400012A7
0x14000129d  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 48h ; 'H'; ATL::CAtlComModule ATL::_AtlComModule
0x1400012a7  lea     rcx, ATL___dynamic_atexit_destructor_for___AtlComModule__
0x1400012ae  add     rsp, 28h
0x1400012b2  jmp     atexit
```
