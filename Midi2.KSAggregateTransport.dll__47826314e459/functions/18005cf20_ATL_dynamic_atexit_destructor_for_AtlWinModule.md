# ATL::_dynamic_atexit_destructor_for___AtlWinModule__

- ea: `0x18005cf20`
- end: `0x18005cf97`
- name: `ATL::_dynamic_atexit_destructor_for___AtlWinModule__`
- size: `119`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180005e54`
- `0x18005cf20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005cf5b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005cf5b`

## pseudocode

```c
void ATL::_dynamic_atexit_destructor_for___AtlWinModule__()
{
  if ( ATL::_AtlWinModule == 72 )
  {
    if ( qword_180096968 )
    {
      free(qword_180096968);
      qword_180096968 = 0;
    }
    qword_180096970 = 0;
    DeleteCriticalSection(&stru_180096938);
    ATL::_AtlWinModule = 0;
  }
  if ( qword_180096968 )
  {
    free(qword_180096968);
    qword_180096968 = 0;
  }
  qword_180096970 = 0;
}

```

## disassembly

```asm
0x18005cf20  sub     rsp, 28h
0x18005cf24  cmp     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 48h ; 'H'; ATL::CAtlWinModule ATL::_AtlWinModule
0x18005cf2b  jnz     short loc_18005CF6B
0x18005cf2d  mov     rcx, cs:qword_180096968; Block
0x18005cf34  test    rcx, rcx
0x18005cf37  jz      short loc_18005CF49
0x18005cf39  call    free
0x18005cf3e  mov     cs:qword_180096968, 0
0x18005cf49  lea     rcx, stru_180096938; lpCriticalSection
0x18005cf50  mov     cs:qword_180096970, 0
0x18005cf5b  call    cs:__imp_DeleteCriticalSection
0x18005cf61  mov     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 0; ATL::CAtlWinModule ATL::_AtlWinModule
0x18005cf6b  mov     rcx, cs:qword_180096968; Block
0x18005cf72  test    rcx, rcx
0x18005cf75  jz      short loc_18005CF87
0x18005cf77  call    free
0x18005cf7c  mov     cs:qword_180096968, 0
0x18005cf87  mov     cs:qword_180096970, 0
0x18005cf92  add     rsp, 28h
0x18005cf96  retn
```
