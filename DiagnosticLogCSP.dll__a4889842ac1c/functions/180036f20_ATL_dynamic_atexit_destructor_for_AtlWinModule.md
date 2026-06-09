# ATL::_dynamic_atexit_destructor_for___AtlWinModule__

- ea: `0x180036f20`
- end: `0x180036f97`
- name: `ATL::_dynamic_atexit_destructor_for___AtlWinModule__`
- size: `119`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800025cc`
- `0x180036f20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180036f5b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180036f5b`

## pseudocode

```c
void ATL::_dynamic_atexit_destructor_for___AtlWinModule__()
{
  if ( ATL::_AtlWinModule == 72 )
  {
    if ( Block )
    {
      free(Block);
      Block = 0;
    }
    qword_180049410 = 0;
    DeleteCriticalSection(&stru_1800493D8);
    ATL::_AtlWinModule = 0;
  }
  if ( Block )
  {
    free(Block);
    Block = 0;
  }
  qword_180049410 = 0;
}

```

## disassembly

```asm
0x180036f20  sub     rsp, 28h
0x180036f24  cmp     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 48h ; 'H'; ATL::CAtlWinModule ATL::_AtlWinModule
0x180036f2b  jnz     short loc_180036F6B
0x180036f2d  mov     rcx, cs:Block; Block
0x180036f34  test    rcx, rcx
0x180036f37  jz      short loc_180036F49
0x180036f39  call    free
0x180036f3e  mov     cs:Block, 0
0x180036f49  lea     rcx, stru_1800493D8; lpCriticalSection
0x180036f50  mov     cs:qword_180049410, 0
0x180036f5b  call    cs:__imp_DeleteCriticalSection
0x180036f61  mov     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 0; ATL::CAtlWinModule ATL::_AtlWinModule
0x180036f6b  mov     rcx, cs:Block; Block
0x180036f72  test    rcx, rcx
0x180036f75  jz      short loc_180036F87
0x180036f77  call    free
0x180036f7c  mov     cs:Block, 0
0x180036f87  mov     cs:qword_180049410, 0
0x180036f92  add     rsp, 28h
0x180036f96  retn
```
