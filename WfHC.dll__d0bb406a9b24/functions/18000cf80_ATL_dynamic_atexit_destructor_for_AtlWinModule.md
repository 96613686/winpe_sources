# ATL::_dynamic_atexit_destructor_for___AtlWinModule__

- ea: `0x18000cf80`
- end: `0x18000cff9`
- name: `ATL::_dynamic_atexit_destructor_for___AtlWinModule__`
- size: `121`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000cf80`

## import_xrefs

- `msvcrt!free` at `0x18000cf99`
- `msvcrt!free` at `0x18000cfd8`
- `msvcrt!free` at `0x18000cf99`
- `msvcrt!free` at `0x18000cfd8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cfbc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cfbc`

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
    qword_180015AB0 = 0;
    DeleteCriticalSection(&stru_180015A78);
    ATL::_AtlWinModule = 0;
  }
  if ( Block )
  {
    free(Block);
    Block = 0;
  }
  qword_180015AB0 = 0;
}

```

## disassembly

```asm
0x18000cf80  sub     rsp, 28h
0x18000cf84  cmp     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 48h ; 'H'; ATL::CAtlWinModule ATL::_AtlWinModule
0x18000cf8b  jnz     short loc_18000CFCC
0x18000cf8d  mov     rcx, cs:Block; Block
0x18000cf94  test    rcx, rcx
0x18000cf97  jz      short loc_18000CFAA
0x18000cf99  call    cs:__imp_free
0x18000cf9f  mov     cs:Block, 0
0x18000cfaa  lea     rcx, stru_180015A78; lpCriticalSection
0x18000cfb1  mov     cs:qword_180015AB0, 0
0x18000cfbc  call    cs:__imp_DeleteCriticalSection
0x18000cfc2  mov     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 0; ATL::CAtlWinModule ATL::_AtlWinModule
0x18000cfcc  mov     rcx, cs:Block; Block
0x18000cfd3  test    rcx, rcx
0x18000cfd6  jz      short loc_18000CFE9
0x18000cfd8  call    cs:__imp_free
0x18000cfde  mov     cs:Block, 0
0x18000cfe9  mov     cs:qword_180015AB0, 0
0x18000cff4  add     rsp, 28h
0x18000cff8  retn
```
