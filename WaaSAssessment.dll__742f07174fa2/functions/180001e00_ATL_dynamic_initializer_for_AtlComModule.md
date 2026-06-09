# ATL::_dynamic_initializer_for___AtlComModule__

- ea: `0x180001e00`
- end: `0x180001e2e`
- name: `ATL::_dynamic_initializer_for___AtlComModule__`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001e00`
- `0x180002b08`
- `0x180004d6c`

## pseudocode

```c
int ATL::_dynamic_initializer_for___AtlComModule__()
{
  if ( (int)ATL::CComCriticalSection::Init(&stru_1800270E0) >= 0 )
    ATL::_AtlComModule = 72;
  return atexit((void (__cdecl *)())ATL::_dynamic_atexit_destructor_for___AtlComModule__);
}

```

## disassembly

```asm
0x180001e00  sub     rsp, 28h
0x180001e04  lea     rcx, stru_1800270E0; this
0x180001e0b  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180001e10  test    eax, eax
0x180001e12  js      short loc_180001E1E
0x180001e14  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 48h ; 'H'; ATL::CAtlComModule ATL::_AtlComModule
0x180001e1e  lea     rcx, ATL___dynamic_atexit_destructor_for___AtlComModule__
0x180001e25  add     rsp, 28h
0x180001e29  jmp     atexit
```
