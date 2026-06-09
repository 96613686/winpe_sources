# ATL::_dynamic_atexit_destructor_for___AtlWinModule__

- ea: `0x180017e10`
- end: `0x180017e87`
- name: `ATL::_dynamic_atexit_destructor_for___AtlWinModule__`
- size: `119`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180003254`
- `0x180017e10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180017e4b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180017e4b`

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
    qword_180025BF0 = 0;
    DeleteCriticalSection(&stru_180025BB8);
    ATL::_AtlWinModule = 0;
  }
  if ( Block )
  {
    free(Block);
    Block = 0;
  }
  qword_180025BF0 = 0;
}

```

## disassembly

```asm
0x180017e10  sub     rsp, 28h
0x180017e14  cmp     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 48h ; 'H'; ATL::CAtlWinModule ATL::_AtlWinModule
0x180017e1b  jnz     short loc_180017E5B
0x180017e1d  mov     rcx, cs:Block; Block
0x180017e24  test    rcx, rcx
0x180017e27  jz      short loc_180017E39
0x180017e29  call    free
0x180017e2e  mov     cs:Block, 0
0x180017e39  lea     rcx, stru_180025BB8; lpCriticalSection
0x180017e40  mov     cs:qword_180025BF0, 0
0x180017e4b  call    cs:__imp_DeleteCriticalSection
0x180017e51  mov     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 0; ATL::CAtlWinModule ATL::_AtlWinModule
0x180017e5b  mov     rcx, cs:Block; Block
0x180017e62  test    rcx, rcx
0x180017e65  jz      short loc_180017E77
0x180017e67  call    free
0x180017e6c  mov     cs:Block, 0
0x180017e77  mov     cs:qword_180025BF0, 0
0x180017e82  add     rsp, 28h
0x180017e86  retn
```
