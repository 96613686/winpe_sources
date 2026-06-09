# ATL::_dynamic_atexit_destructor_for___AtlWinModule__

- ea: `0x18000a290`
- end: `0x18000a307`
- name: `ATL::_dynamic_atexit_destructor_for___AtlWinModule__`
- size: `119`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001e94`
- `0x18000a290`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a2cb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a2cb`

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
    qword_18000F280 = 0;
    DeleteCriticalSection(&stru_18000F248);
    ATL::_AtlWinModule = 0;
  }
  if ( Block )
  {
    free(Block);
    Block = 0;
  }
  qword_18000F280 = 0;
}

```

## disassembly

```asm
0x18000a290  sub     rsp, 28h
0x18000a294  cmp     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 48h ; 'H'; ATL::CAtlWinModule ATL::_AtlWinModule
0x18000a29b  jnz     short loc_18000A2DB
0x18000a29d  mov     rcx, cs:Block; Block
0x18000a2a4  test    rcx, rcx
0x18000a2a7  jz      short loc_18000A2B9
0x18000a2a9  call    free
0x18000a2ae  mov     cs:Block, 0
0x18000a2b9  lea     rcx, stru_18000F248; lpCriticalSection
0x18000a2c0  mov     cs:qword_18000F280, 0
0x18000a2cb  call    cs:__imp_DeleteCriticalSection
0x18000a2d1  mov     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 0; ATL::CAtlWinModule ATL::_AtlWinModule
0x18000a2db  mov     rcx, cs:Block; Block
0x18000a2e2  test    rcx, rcx
0x18000a2e5  jz      short loc_18000A2F7
0x18000a2e7  call    free
0x18000a2ec  mov     cs:Block, 0
0x18000a2f7  mov     cs:qword_18000F280, 0
0x18000a302  add     rsp, 28h
0x18000a306  retn
```
