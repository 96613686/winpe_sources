# ATL::_dynamic_atexit_destructor_for___AtlWinModule__

- ea: `0x18000e990`
- end: `0x18000ea07`
- name: `ATL::_dynamic_atexit_destructor_for___AtlWinModule__`
- size: `119`
- prototype: `void()`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002534`
- `0x18000e990`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e9cb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e9cb`

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
    qword_1800175E0 = 0;
    DeleteCriticalSection(&stru_1800175A8);
    ATL::_AtlWinModule = 0;
  }
  if ( Block )
  {
    free(Block);
    Block = 0;
  }
  qword_1800175E0 = 0;
}

```

## disassembly

```asm
0x18000e990  sub     rsp, 28h
0x18000e994  cmp     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 48h ; 'H'; ATL::CAtlWinModule ATL::_AtlWinModule
0x18000e99b  jnz     short loc_18000E9DB
0x18000e99d  mov     rcx, cs:Block; Block
0x18000e9a4  test    rcx, rcx
0x18000e9a7  jz      short loc_18000E9B9
0x18000e9a9  call    free
0x18000e9ae  mov     cs:Block, 0
0x18000e9b9  lea     rcx, stru_1800175A8; lpCriticalSection
0x18000e9c0  mov     cs:qword_1800175E0, 0
0x18000e9cb  call    cs:__imp_DeleteCriticalSection
0x18000e9d1  mov     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 0; ATL::CAtlWinModule ATL::_AtlWinModule
0x18000e9db  mov     rcx, cs:Block; Block
0x18000e9e2  test    rcx, rcx
0x18000e9e5  jz      short loc_18000E9F7
0x18000e9e7  call    free
0x18000e9ec  mov     cs:Block, 0
0x18000e9f7  mov     cs:qword_1800175E0, 0
0x18000ea02  add     rsp, 28h
0x18000ea06  retn
```
