# ATL::_dynamic_atexit_destructor_for___AtlWinModule__

- ea: `0x18000d510`
- end: `0x18000d587`
- name: `ATL::_dynamic_atexit_destructor_for___AtlWinModule__`
- size: `119`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002a44`
- `0x18000d510`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d54b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d54b`

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
    qword_180015360 = 0;
    DeleteCriticalSection(&stru_180015328);
    ATL::_AtlWinModule = 0;
  }
  if ( Block )
  {
    free(Block);
    Block = 0;
  }
  qword_180015360 = 0;
}

```

## disassembly

```asm
0x18000d510  sub     rsp, 28h
0x18000d514  cmp     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 48h ; 'H'; ATL::CAtlWinModule ATL::_AtlWinModule
0x18000d51b  jnz     short loc_18000D55B
0x18000d51d  mov     rcx, cs:Block; Block
0x18000d524  test    rcx, rcx
0x18000d527  jz      short loc_18000D539
0x18000d529  call    free
0x18000d52e  mov     cs:Block, 0
0x18000d539  lea     rcx, stru_180015328; lpCriticalSection
0x18000d540  mov     cs:qword_180015360, 0
0x18000d54b  call    cs:__imp_DeleteCriticalSection
0x18000d551  mov     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 0; ATL::CAtlWinModule ATL::_AtlWinModule
0x18000d55b  mov     rcx, cs:Block; Block
0x18000d562  test    rcx, rcx
0x18000d565  jz      short loc_18000D577
0x18000d567  call    free
0x18000d56c  mov     cs:Block, 0
0x18000d577  mov     cs:qword_180015360, 0
0x18000d582  add     rsp, 28h
0x18000d586  retn
```
