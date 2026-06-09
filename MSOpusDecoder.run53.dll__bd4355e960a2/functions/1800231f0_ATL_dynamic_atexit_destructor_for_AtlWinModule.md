# ATL::_dynamic_atexit_destructor_for___AtlWinModule__

- ea: `0x1800231f0`
- end: `0x180023267`
- name: `ATL::_dynamic_atexit_destructor_for___AtlWinModule__`
- size: `119`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002258`
- `0x1800231f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002322b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002322b`

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
    qword_1800352C0 = 0;
    DeleteCriticalSection(&stru_180035288);
    ATL::_AtlWinModule = 0;
  }
  if ( Block )
  {
    free(Block);
    Block = 0;
  }
  qword_1800352C0 = 0;
}

```

## disassembly

```asm
0x1800231f0  sub     rsp, 28h
0x1800231f4  cmp     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 48h ; 'H'; ATL::CAtlWinModule ATL::_AtlWinModule
0x1800231fb  jnz     short loc_18002323B
0x1800231fd  mov     rcx, cs:Block; Block
0x180023204  test    rcx, rcx
0x180023207  jz      short loc_180023219
0x180023209  call    free
0x18002320e  mov     cs:Block, 0
0x180023219  lea     rcx, stru_180035288; lpCriticalSection
0x180023220  mov     cs:qword_1800352C0, 0
0x18002322b  call    cs:__imp_DeleteCriticalSection
0x180023231  mov     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 0; ATL::CAtlWinModule ATL::_AtlWinModule
0x18002323b  mov     rcx, cs:Block; Block
0x180023242  test    rcx, rcx
0x180023245  jz      short loc_180023257
0x180023247  call    free
0x18002324c  mov     cs:Block, 0
0x180023257  mov     cs:qword_1800352C0, 0
0x180023262  add     rsp, 28h
0x180023266  retn
```
