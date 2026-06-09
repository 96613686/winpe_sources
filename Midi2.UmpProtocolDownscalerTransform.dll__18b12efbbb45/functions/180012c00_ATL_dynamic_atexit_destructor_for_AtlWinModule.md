# ATL::_dynamic_atexit_destructor_for___AtlWinModule__

- ea: `0x180012c00`
- end: `0x180012c77`
- name: `ATL::_dynamic_atexit_destructor_for___AtlWinModule__`
- size: `119`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800039e4`
- `0x180012c00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180012c3b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180012c3b`

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
    qword_18001B740 = 0;
    DeleteCriticalSection(&stru_18001B708);
    ATL::_AtlWinModule = 0;
  }
  if ( Block )
  {
    free(Block);
    Block = 0;
  }
  qword_18001B740 = 0;
}

```

## disassembly

```asm
0x180012c00  sub     rsp, 28h
0x180012c04  cmp     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 48h ; 'H'; ATL::CAtlWinModule ATL::_AtlWinModule
0x180012c0b  jnz     short loc_180012C4B
0x180012c0d  mov     rcx, cs:Block; Block
0x180012c14  test    rcx, rcx
0x180012c17  jz      short loc_180012C29
0x180012c19  call    free
0x180012c1e  mov     cs:Block, 0
0x180012c29  lea     rcx, stru_18001B708; lpCriticalSection
0x180012c30  mov     cs:qword_18001B740, 0
0x180012c3b  call    cs:__imp_DeleteCriticalSection
0x180012c41  mov     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 0; ATL::CAtlWinModule ATL::_AtlWinModule
0x180012c4b  mov     rcx, cs:Block; Block
0x180012c52  test    rcx, rcx
0x180012c55  jz      short loc_180012C67
0x180012c57  call    free
0x180012c5c  mov     cs:Block, 0
0x180012c67  mov     cs:qword_18001B740, 0
0x180012c72  add     rsp, 28h
0x180012c76  retn
```
