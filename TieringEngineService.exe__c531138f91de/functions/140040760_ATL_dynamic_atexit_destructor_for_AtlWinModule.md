# ATL::_dynamic_atexit_destructor_for___AtlWinModule__

- ea: `0x140040760`
- end: `0x1400407d9`
- name: `ATL::_dynamic_atexit_destructor_for___AtlWinModule__`
- size: `121`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140040760`

## import_xrefs

- `msvcrt!free` at `0x140040779`
- `msvcrt!free` at `0x1400407b8`
- `msvcrt!free` at `0x140040779`
- `msvcrt!free` at `0x1400407b8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14004079c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14004079c`

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
    qword_14004C3E0 = 0;
    DeleteCriticalSection(&stru_14004C3A8);
    ATL::_AtlWinModule = 0;
  }
  if ( Block )
  {
    free(Block);
    Block = 0;
  }
  qword_14004C3E0 = 0;
}

```

## disassembly

```asm
0x140040760  sub     rsp, 28h
0x140040764  cmp     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 48h ; 'H'; ATL::CAtlWinModule ATL::_AtlWinModule
0x14004076b  jnz     short loc_1400407AC
0x14004076d  mov     rcx, cs:Block; Block
0x140040774  test    rcx, rcx
0x140040777  jz      short loc_14004078A
0x140040779  call    cs:__imp_free
0x14004077f  mov     cs:Block, 0
0x14004078a  lea     rcx, stru_14004C3A8; lpCriticalSection
0x140040791  mov     cs:qword_14004C3E0, 0
0x14004079c  call    cs:__imp_DeleteCriticalSection
0x1400407a2  mov     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 0; ATL::CAtlWinModule ATL::_AtlWinModule
0x1400407ac  mov     rcx, cs:Block; Block
0x1400407b3  test    rcx, rcx
0x1400407b6  jz      short loc_1400407C9
0x1400407b8  call    cs:__imp_free
0x1400407be  mov     cs:Block, 0
0x1400407c9  mov     cs:qword_14004C3E0, 0
0x1400407d4  add     rsp, 28h
0x1400407d8  retn
```
