# ATL::_dynamic_atexit_destructor_for___AtlWinModule__

- ea: `0x18000ed30`
- end: `0x18000eda7`
- name: `ATL::_dynamic_atexit_destructor_for___AtlWinModule__`
- size: `119`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002934`
- `0x18000ed30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ed6b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ed6b`

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
    qword_180015410 = 0;
    DeleteCriticalSection(&stru_1800153D8);
    ATL::_AtlWinModule = 0;
  }
  if ( Block )
  {
    free(Block);
    Block = 0;
  }
  qword_180015410 = 0;
}

```

## disassembly

```asm
0x18000ed30  sub     rsp, 28h
0x18000ed34  cmp     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 48h ; 'H'; ATL::CAtlWinModule ATL::_AtlWinModule
0x18000ed3b  jnz     short loc_18000ED7B
0x18000ed3d  mov     rcx, cs:Block; Block
0x18000ed44  test    rcx, rcx
0x18000ed47  jz      short loc_18000ED59
0x18000ed49  call    free
0x18000ed4e  mov     cs:Block, 0
0x18000ed59  lea     rcx, stru_1800153D8; lpCriticalSection
0x18000ed60  mov     cs:qword_180015410, 0
0x18000ed6b  call    cs:__imp_DeleteCriticalSection
0x18000ed71  mov     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 0; ATL::CAtlWinModule ATL::_AtlWinModule
0x18000ed7b  mov     rcx, cs:Block; Block
0x18000ed82  test    rcx, rcx
0x18000ed85  jz      short loc_18000ED97
0x18000ed87  call    free
0x18000ed8c  mov     cs:Block, 0
0x18000ed97  mov     cs:qword_180015410, 0
0x18000eda2  add     rsp, 28h
0x18000eda6  retn
```
