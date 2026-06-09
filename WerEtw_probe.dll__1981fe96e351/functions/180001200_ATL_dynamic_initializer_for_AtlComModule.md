# ATL::_dynamic_initializer_for___AtlComModule__

- ea: `0x180001200`
- end: `0x18000122e`
- name: `ATL::_dynamic_initializer_for___AtlComModule__`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001200`
- `0x180001d4c`
- `0x180002f84`

## pseudocode

```c
int ATL::_dynamic_initializer_for___AtlComModule__()
{
  if ( (int)ATL::CComCriticalSection::Init(&stru_180036920) >= 0 )
    ATL::_AtlComModule = 72;
  return atexit((void (__cdecl *)())ATL::_dynamic_atexit_destructor_for___AtlComModule__);
}

```

## disassembly

```asm
0x180001200  sub     rsp, 28h
0x180001204  lea     rcx, stru_180036920; this
0x18000120b  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180001210  test    eax, eax
0x180001212  js      short loc_18000121E
0x180001214  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 48h ; 'H'; ATL::CAtlComModule ATL::_AtlComModule
0x18000121e  lea     rcx, ATL___dynamic_atexit_destructor_for___AtlComModule__
0x180001225  add     rsp, 28h
0x180001229  jmp     atexit
```
