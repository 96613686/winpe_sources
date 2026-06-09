# vt::imgdbg::_dynamic_atexit_destructor_for__g_commLock__

- ea: `0x180141230`
- end: `0x18014125d`
- name: `vt::imgdbg::_dynamic_atexit_destructor_for__g_commLock__`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180141230`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18014124b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18014124b`

## pseudocode

```c
void vt::imgdbg::_dynamic_atexit_destructor_for__g_commLock__()
{
  vt::imgdbg::ImgDbgCritSection::s_bInit = 0;
  if ( vt::imgdbg::g_commLock )
  {
    DeleteCriticalSection(&stru_1801607D8);
    vt::imgdbg::g_commLock = 0;
  }
}

```

## disassembly

```asm
0x180141230  sub     rsp, 28h
0x180141234  cmp     cs:?g_commLock@imgdbg@vt@@3VImgDbgCritSection@12@A, 0; vt::imgdbg::ImgDbgCritSection vt::imgdbg::g_commLock
0x18014123b  mov     cs:?s_bInit@ImgDbgCritSection@imgdbg@vt@@0_NA, 0; bool vt::imgdbg::ImgDbgCritSection::s_bInit
0x180141242  jz      short loc_180141258
0x180141244  lea     rcx, stru_1801607D8; lpCriticalSection
0x18014124b  call    cs:__imp_DeleteCriticalSection
0x180141251  mov     cs:?g_commLock@imgdbg@vt@@3VImgDbgCritSection@12@A, 0; vt::imgdbg::ImgDbgCritSection vt::imgdbg::g_commLock
0x180141258  add     rsp, 28h
0x18014125c  retn
```
