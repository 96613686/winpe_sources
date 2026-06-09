# ATL::_dynamic_atexit_destructor_for___AtlWinModule__

- ea: `0x180028fb0`
- end: `0x180029027`
- name: `ATL::_dynamic_atexit_destructor_for___AtlWinModule__`
- size: `119`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800023d8`
- `0x180028fb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180028feb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180028feb`

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
    qword_180036DA0 = 0;
    DeleteCriticalSection(&stru_180036D68);
    ATL::_AtlWinModule = 0;
  }
  if ( Block )
  {
    free(Block);
    Block = 0;
  }
  qword_180036DA0 = 0;
}

```

## disassembly

```asm
0x180028fb0  sub     rsp, 28h
0x180028fb4  cmp     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 48h ; 'H'; ATL::CAtlWinModule ATL::_AtlWinModule
0x180028fbb  jnz     short loc_180028FFB
0x180028fbd  mov     rcx, cs:Block; Block
0x180028fc4  test    rcx, rcx
0x180028fc7  jz      short loc_180028FD9
0x180028fc9  call    free
0x180028fce  mov     cs:Block, 0
0x180028fd9  lea     rcx, stru_180036D68; lpCriticalSection
0x180028fe0  mov     cs:qword_180036DA0, 0
0x180028feb  call    cs:__imp_DeleteCriticalSection
0x180028ff1  mov     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 0; ATL::CAtlWinModule ATL::_AtlWinModule
0x180028ffb  mov     rcx, cs:Block; Block
0x180029002  test    rcx, rcx
0x180029005  jz      short loc_180029017
0x180029007  call    free
0x18002900c  mov     cs:Block, 0
0x180029017  mov     cs:qword_180036DA0, 0
0x180029022  add     rsp, 28h
0x180029026  retn
```
