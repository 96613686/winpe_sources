# ATL::_dynamic_initializer_for___AtlComModule__

- ea: `0x180001210`
- end: `0x18000123e`
- name: `ATL::_dynamic_initializer_for___AtlComModule__`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001210`
- `0x180001b9c`
- `0x1800069ec`

## pseudocode

```c
int ATL::_dynamic_initializer_for___AtlComModule__()
{
  if ( (int)ATL::CComCriticalSection::Init(&stru_1800210C0) >= 0 )
    ATL::_AtlComModule = 72;
  return atexit((void (__cdecl *)())ATL::_dynamic_atexit_destructor_for___AtlComModule__);
}

```

## disassembly

```asm
0x180001210  sub     rsp, 28h
0x180001214  lea     rcx, stru_1800210C0; this
0x18000121b  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180001220  test    eax, eax
0x180001222  js      short loc_18000122E
0x180001224  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 48h ; 'H'; ATL::CAtlComModule ATL::_AtlComModule
0x18000122e  lea     rcx, ATL___dynamic_atexit_destructor_for___AtlComModule__
0x180001235  add     rsp, 28h
0x180001239  jmp     atexit
```
