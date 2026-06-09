# ATL::_dynamic_atexit_destructor_for___AtlWinModule__

- ea: `0x180012650`
- end: `0x1800126c7`
- name: `ATL::_dynamic_atexit_destructor_for___AtlWinModule__`
- size: `119`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004134`
- `0x180012650`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001268b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001268b`

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
    qword_18001A3F0 = 0;
    DeleteCriticalSection(&stru_18001A3B8);
    ATL::_AtlWinModule = 0;
  }
  if ( Block )
  {
    free(Block);
    Block = 0;
  }
  qword_18001A3F0 = 0;
}

```

## disassembly

```asm
0x180012650  sub     rsp, 28h
0x180012654  cmp     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 48h ; 'H'; ATL::CAtlWinModule ATL::_AtlWinModule
0x18001265b  jnz     short loc_18001269B
0x18001265d  mov     rcx, cs:Block; Block
0x180012664  test    rcx, rcx
0x180012667  jz      short loc_180012679
0x180012669  call    free
0x18001266e  mov     cs:Block, 0
0x180012679  lea     rcx, stru_18001A3B8; lpCriticalSection
0x180012680  mov     cs:qword_18001A3F0, 0
0x18001268b  call    cs:__imp_DeleteCriticalSection
0x180012691  mov     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 0; ATL::CAtlWinModule ATL::_AtlWinModule
0x18001269b  mov     rcx, cs:Block; Block
0x1800126a2  test    rcx, rcx
0x1800126a5  jz      short loc_1800126B7
0x1800126a7  call    free
0x1800126ac  mov     cs:Block, 0
0x1800126b7  mov     cs:qword_18001A3F0, 0
0x1800126c2  add     rsp, 28h
0x1800126c6  retn
```
