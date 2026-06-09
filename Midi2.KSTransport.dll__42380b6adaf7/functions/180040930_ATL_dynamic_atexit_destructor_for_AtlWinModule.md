# ATL::_dynamic_atexit_destructor_for___AtlWinModule__

- ea: `0x180040930`
- end: `0x1800409a7`
- name: `ATL::_dynamic_atexit_destructor_for___AtlWinModule__`
- size: `119`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180005224`
- `0x180040930`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004096b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004096b`

## pseudocode

```c
void ATL::_dynamic_atexit_destructor_for___AtlWinModule__()
{
  if ( ATL::_AtlWinModule == 72 )
  {
    if ( qword_180071928 )
    {
      free(qword_180071928);
      qword_180071928 = 0;
    }
    qword_180071930 = 0;
    DeleteCriticalSection(&stru_1800718F8);
    ATL::_AtlWinModule = 0;
  }
  if ( qword_180071928 )
  {
    free(qword_180071928);
    qword_180071928 = 0;
  }
  qword_180071930 = 0;
}

```

## disassembly

```asm
0x180040930  sub     rsp, 28h
0x180040934  cmp     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 48h ; 'H'; ATL::CAtlWinModule ATL::_AtlWinModule
0x18004093b  jnz     short loc_18004097B
0x18004093d  mov     rcx, cs:qword_180071928; Block
0x180040944  test    rcx, rcx
0x180040947  jz      short loc_180040959
0x180040949  call    free
0x18004094e  mov     cs:qword_180071928, 0
0x180040959  lea     rcx, stru_1800718F8; lpCriticalSection
0x180040960  mov     cs:qword_180071930, 0
0x18004096b  call    cs:__imp_DeleteCriticalSection
0x180040971  mov     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 0; ATL::CAtlWinModule ATL::_AtlWinModule
0x18004097b  mov     rcx, cs:qword_180071928; Block
0x180040982  test    rcx, rcx
0x180040985  jz      short loc_180040997
0x180040987  call    free
0x18004098c  mov     cs:qword_180071928, 0
0x180040997  mov     cs:qword_180071930, 0
0x1800409a2  add     rsp, 28h
0x1800409a6  retn
```
