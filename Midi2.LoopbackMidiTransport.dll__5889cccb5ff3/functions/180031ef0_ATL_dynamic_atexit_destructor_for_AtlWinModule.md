# ATL::_dynamic_atexit_destructor_for___AtlWinModule__

- ea: `0x180031ef0`
- end: `0x180031f67`
- name: `ATL::_dynamic_atexit_destructor_for___AtlWinModule__`
- size: `119`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004fc4`
- `0x180031ef0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180031f2b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180031f2b`

## pseudocode

```c
void ATL::_dynamic_atexit_destructor_for___AtlWinModule__()
{
  if ( ATL::_AtlWinModule == 72 )
  {
    if ( qword_18005F828 )
    {
      free(qword_18005F828);
      qword_18005F828 = 0;
    }
    qword_18005F830 = 0;
    DeleteCriticalSection(&stru_18005F7F8);
    ATL::_AtlWinModule = 0;
  }
  if ( qword_18005F828 )
  {
    free(qword_18005F828);
    qword_18005F828 = 0;
  }
  qword_18005F830 = 0;
}

```

## disassembly

```asm
0x180031ef0  sub     rsp, 28h
0x180031ef4  cmp     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 48h ; 'H'; ATL::CAtlWinModule ATL::_AtlWinModule
0x180031efb  jnz     short loc_180031F3B
0x180031efd  mov     rcx, cs:qword_18005F828; Block
0x180031f04  test    rcx, rcx
0x180031f07  jz      short loc_180031F19
0x180031f09  call    free
0x180031f0e  mov     cs:qword_18005F828, 0
0x180031f19  lea     rcx, stru_18005F7F8; lpCriticalSection
0x180031f20  mov     cs:qword_18005F830, 0
0x180031f2b  call    cs:__imp_DeleteCriticalSection
0x180031f31  mov     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 0; ATL::CAtlWinModule ATL::_AtlWinModule
0x180031f3b  mov     rcx, cs:qword_18005F828; Block
0x180031f42  test    rcx, rcx
0x180031f45  jz      short loc_180031F57
0x180031f47  call    free
0x180031f4c  mov     cs:qword_18005F828, 0
0x180031f57  mov     cs:qword_18005F830, 0
0x180031f62  add     rsp, 28h
0x180031f66  retn
```
