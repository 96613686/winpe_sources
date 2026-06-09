# ATL::_dynamic_atexit_destructor_for___AtlWinModule__

- ea: `0x18008b0b0`
- end: `0x18008b0f0`
- name: `ATL::_dynamic_atexit_destructor_for___AtlWinModule__`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800471ec`
- `0x18008b0b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008b0d0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008b0d0`

## pseudocode

```c
__int64 ATL::_dynamic_atexit_destructor_for___AtlWinModule__()
{
  if ( ATL::_AtlWinModule == 72 )
  {
    ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll(qword_1800BE278);
    DeleteCriticalSection(&CriticalSection);
    ATL::_AtlWinModule = 0;
  }
  return ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll(qword_1800BE278);
}

```

## disassembly

```asm
0x18008b0b0  sub     rsp, 28h
0x18008b0b4  cmp     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 48h ; 'H'; ATL::CAtlWinModule ATL::_AtlWinModule
0x18008b0bb  jnz     short loc_18008B0E0
0x18008b0bd  lea     rcx, qword_1800BE278
0x18008b0c4  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x18008b0c9  lea     rcx, CriticalSection; lpCriticalSection
0x18008b0d0  call    cs:__imp_DeleteCriticalSection
0x18008b0d6  mov     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 0; ATL::CAtlWinModule ATL::_AtlWinModule
0x18008b0e0  lea     rcx, qword_1800BE278
0x18008b0e7  add     rsp, 28h
0x18008b0eb  jmp     ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
```
