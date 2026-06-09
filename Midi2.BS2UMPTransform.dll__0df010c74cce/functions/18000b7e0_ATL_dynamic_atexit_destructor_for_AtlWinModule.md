# ATL::_dynamic_atexit_destructor_for___AtlWinModule__

- ea: `0x18000b7e0`
- end: `0x18000b857`
- name: `ATL::_dynamic_atexit_destructor_for___AtlWinModule__`
- size: `119`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800028a4`
- `0x18000b7e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b81b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b81b`

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
    qword_180012360 = 0;
    DeleteCriticalSection(&stru_180012328);
    ATL::_AtlWinModule = 0;
  }
  if ( Block )
  {
    free(Block);
    Block = 0;
  }
  qword_180012360 = 0;
}

```

## disassembly

```asm
0x18000b7e0  sub     rsp, 28h
0x18000b7e4  cmp     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 48h ; 'H'; ATL::CAtlWinModule ATL::_AtlWinModule
0x18000b7eb  jnz     short loc_18000B82B
0x18000b7ed  mov     rcx, cs:Block; Block
0x18000b7f4  test    rcx, rcx
0x18000b7f7  jz      short loc_18000B809
0x18000b7f9  call    free
0x18000b7fe  mov     cs:Block, 0
0x18000b809  lea     rcx, stru_180012328; lpCriticalSection
0x18000b810  mov     cs:qword_180012360, 0
0x18000b81b  call    cs:__imp_DeleteCriticalSection
0x18000b821  mov     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 0; ATL::CAtlWinModule ATL::_AtlWinModule
0x18000b82b  mov     rcx, cs:Block; Block
0x18000b832  test    rcx, rcx
0x18000b835  jz      short loc_18000B847
0x18000b837  call    free
0x18000b83c  mov     cs:Block, 0
0x18000b847  mov     cs:qword_180012360, 0
0x18000b852  add     rsp, 28h
0x18000b856  retn
```
