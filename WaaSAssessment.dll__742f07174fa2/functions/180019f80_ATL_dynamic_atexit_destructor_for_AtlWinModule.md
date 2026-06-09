# ATL::_dynamic_atexit_destructor_for___AtlWinModule__

- ea: `0x180019f80`
- end: `0x180019ff9`
- name: `ATL::_dynamic_atexit_destructor_for___AtlWinModule__`
- size: `121`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180019f80`

## import_xrefs

- `msvcrt!free` at `0x180019f99`
- `msvcrt!free` at `0x180019fd8`
- `msvcrt!free` at `0x180019f99`
- `msvcrt!free` at `0x180019fd8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180019fbc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180019fbc`

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
    qword_180027420 = 0;
    DeleteCriticalSection(&stru_1800273E8);
    ATL::_AtlWinModule = 0;
  }
  if ( Block )
  {
    free(Block);
    Block = 0;
  }
  qword_180027420 = 0;
}

```

## disassembly

```asm
0x180019f80  sub     rsp, 28h
0x180019f84  cmp     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 48h ; 'H'; ATL::CAtlWinModule ATL::_AtlWinModule
0x180019f8b  jnz     short loc_180019FCC
0x180019f8d  mov     rcx, cs:Block; Block
0x180019f94  test    rcx, rcx
0x180019f97  jz      short loc_180019FAA
0x180019f99  call    cs:__imp_free
0x180019f9f  mov     cs:Block, 0
0x180019faa  lea     rcx, stru_1800273E8; lpCriticalSection
0x180019fb1  mov     cs:qword_180027420, 0
0x180019fbc  call    cs:__imp_DeleteCriticalSection
0x180019fc2  mov     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 0; ATL::CAtlWinModule ATL::_AtlWinModule
0x180019fcc  mov     rcx, cs:Block; Block
0x180019fd3  test    rcx, rcx
0x180019fd6  jz      short loc_180019FE9
0x180019fd8  call    cs:__imp_free
0x180019fde  mov     cs:Block, 0
0x180019fe9  mov     cs:qword_180027420, 0
0x180019ff4  add     rsp, 28h
0x180019ff8  retn
```
