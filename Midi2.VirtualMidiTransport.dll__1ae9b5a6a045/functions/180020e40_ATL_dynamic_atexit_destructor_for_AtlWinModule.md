# ATL::_dynamic_atexit_destructor_for___AtlWinModule__

- ea: `0x180020e40`
- end: `0x180020eb7`
- name: `ATL::_dynamic_atexit_destructor_for___AtlWinModule__`
- size: `119`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004664`
- `0x180020e40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180020e7b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180020e7b`

## pseudocode

```c
void ATL::_dynamic_atexit_destructor_for___AtlWinModule__()
{
  if ( ATL::_AtlWinModule == 72 )
  {
    if ( qword_18002D7A8 )
    {
      free(qword_18002D7A8);
      qword_18002D7A8 = 0;
    }
    qword_18002D7B0 = 0;
    DeleteCriticalSection(&stru_18002D778);
    ATL::_AtlWinModule = 0;
  }
  if ( qword_18002D7A8 )
  {
    free(qword_18002D7A8);
    qword_18002D7A8 = 0;
  }
  qword_18002D7B0 = 0;
}

```

## disassembly

```asm
0x180020e40  sub     rsp, 28h
0x180020e44  cmp     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 48h ; 'H'; ATL::CAtlWinModule ATL::_AtlWinModule
0x180020e4b  jnz     short loc_180020E8B
0x180020e4d  mov     rcx, cs:qword_18002D7A8; Block
0x180020e54  test    rcx, rcx
0x180020e57  jz      short loc_180020E69
0x180020e59  call    free
0x180020e5e  mov     cs:qword_18002D7A8, 0
0x180020e69  lea     rcx, stru_18002D778; lpCriticalSection
0x180020e70  mov     cs:qword_18002D7B0, 0
0x180020e7b  call    cs:__imp_DeleteCriticalSection
0x180020e81  mov     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 0; ATL::CAtlWinModule ATL::_AtlWinModule
0x180020e8b  mov     rcx, cs:qword_18002D7A8; Block
0x180020e92  test    rcx, rcx
0x180020e95  jz      short loc_180020EA7
0x180020e97  call    free
0x180020e9c  mov     cs:qword_18002D7A8, 0
0x180020ea7  mov     cs:qword_18002D7B0, 0
0x180020eb2  add     rsp, 28h
0x180020eb6  retn
```
