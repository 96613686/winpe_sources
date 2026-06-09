# ATL::_dynamic_atexit_destructor_for___AtlWinModule__

- ea: `0x18000e0e0`
- end: `0x18000e122`
- name: `ATL::_dynamic_atexit_destructor_for___AtlWinModule__`
- size: `66`
- prototype: `void()`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000e0e0`
- `0x18000e128`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e110`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e110`

## pseudocode

```c
void ATL::_dynamic_atexit_destructor_for___AtlWinModule__()
{
  if ( ATL::_AtlWinModule == 72 )
  {
    ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll((__int64)qword_180026358);
    DeleteCriticalSection(&stru_180026328);
    ATL::_AtlWinModule = 0;
  }
  ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll((__int64)qword_180026358);
}

```

## disassembly

```asm
0x18000e0e0  sub     rsp, 28h
0x18000e0e4  cmp     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 48h ; 'H'; ATL::CAtlWinModule ATL::_AtlWinModule
0x18000e0eb  jz      short loc_18000E0FD
0x18000e0ed  lea     rcx, qword_180026358
0x18000e0f4  add     rsp, 28h
0x18000e0f8  jmp     ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x18000e0fd  lea     rcx, qword_180026358
0x18000e104  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x18000e109  lea     rcx, stru_180026328; lpCriticalSection
0x18000e110  call    cs:__imp_DeleteCriticalSection
0x18000e116  mov     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 0; ATL::CAtlWinModule ATL::_AtlWinModule
0x18000e120  jmp     short loc_18000E0ED
```
