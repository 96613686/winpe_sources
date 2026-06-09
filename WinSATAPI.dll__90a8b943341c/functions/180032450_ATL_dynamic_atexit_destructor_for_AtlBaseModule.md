# ATL::_dynamic_atexit_destructor_for___AtlBaseModule__

- ea: `0x180032450`
- end: `0x18003249b`
- name: `ATL::_dynamic_atexit_destructor_for___AtlBaseModule__`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180032450`

## import_xrefs

- `msvcrt!free` at `0x180032473`
- `msvcrt!free` at `0x180032473`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003245b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003245b`

## pseudocode

```c
void ATL::_dynamic_atexit_destructor_for___AtlBaseModule__()
{
  DeleteCriticalSection(&stru_18004BE38);
  if ( Block )
  {
    free(Block);
    Block = 0;
  }
  qword_18004BE68 = 0;
}

```

## disassembly

```asm
0x180032450  sub     rsp, 28h
0x180032454  lea     rcx, stru_18004BE38; lpCriticalSection
0x18003245b  call    cs:__imp_DeleteCriticalSection
0x180032462  nop     dword ptr [rax+rax+00h]
0x180032467  mov     rcx, cs:Block; Block
0x18003246e  test    rcx, rcx
0x180032471  jz      short loc_180032487
0x180032473  call    cs:__imp_free
0x18003247a  nop     dword ptr [rax+rax+00h]
0x18003247f  and     cs:Block, 0
0x180032487  and     dword ptr cs:qword_18004BE68, 0
0x18003248e  and     dword ptr cs:qword_18004BE68+4, 0
0x180032495  add     rsp, 28h
0x180032499  retn
```
