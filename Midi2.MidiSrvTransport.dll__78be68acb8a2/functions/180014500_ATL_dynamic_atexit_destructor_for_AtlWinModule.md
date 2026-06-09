# ATL::_dynamic_atexit_destructor_for___AtlWinModule__

- ea: `0x180014500`
- end: `0x180014577`
- name: `ATL::_dynamic_atexit_destructor_for___AtlWinModule__`
- size: `119`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002fd4`
- `0x180014500`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001453b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001453b`

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
    qword_18001E3E0 = 0;
    DeleteCriticalSection(&stru_18001E3A8);
    ATL::_AtlWinModule = 0;
  }
  if ( Block )
  {
    free(Block);
    Block = 0;
  }
  qword_18001E3E0 = 0;
}

```

## disassembly

```asm
0x180014500  sub     rsp, 28h
0x180014504  cmp     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 48h ; 'H'; ATL::CAtlWinModule ATL::_AtlWinModule
0x18001450b  jnz     short loc_18001454B
0x18001450d  mov     rcx, cs:Block; Block
0x180014514  test    rcx, rcx
0x180014517  jz      short loc_180014529
0x180014519  call    free
0x18001451e  mov     cs:Block, 0
0x180014529  lea     rcx, stru_18001E3A8; lpCriticalSection
0x180014530  mov     cs:qword_18001E3E0, 0
0x18001453b  call    cs:__imp_DeleteCriticalSection
0x180014541  mov     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 0; ATL::CAtlWinModule ATL::_AtlWinModule
0x18001454b  mov     rcx, cs:Block; Block
0x180014552  test    rcx, rcx
0x180014555  jz      short loc_180014567
0x180014557  call    free
0x18001455c  mov     cs:Block, 0
0x180014567  mov     cs:qword_18001E3E0, 0
0x180014572  add     rsp, 28h
0x180014576  retn
```
