# CWDMListener::CloseRemove(void)

- ea: `0x180005000`
- end: `0x180005041`
- name: `?CloseRemove@CWDMListener@@QEAAKXZ`
- size: `65`
- prototype: `unsigned int __fastcall(CWDMListener *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004ad0`
- `0x1800059a8`
- `0x180005f14`

## callees

- `0x180005000`

## import_xrefs

- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180005014`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180005014`
- `WMICLNT!WmiCloseBlock` at `0x18000502b`
- `WMICLNT!WmiCloseBlock` at `0x18000502b`

## pseudocode

```c
__int64 __fastcall CWDMListener::CloseRemove(CWDMListener *this)
{
  void *v2; // rcx

  v2 = (void *)*((_QWORD *)this + 4);
  if ( v2 )
  {
    UnregisterWaitEx(v2, 0);
    *((_QWORD *)this + 4) = 0;
  }
  if ( *((_QWORD *)this + 2) )
  {
    WmiCloseBlock();
    *((_QWORD *)this + 2) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180005000  push    rbx
0x180005002  sub     rsp, 20h
0x180005006  mov     rbx, rcx
0x180005009  mov     rcx, [rcx+20h]; WaitHandle
0x18000500d  test    rcx, rcx
0x180005010  jz      short loc_180005022
0x180005012  xor     edx, edx; CompletionEvent
0x180005014  call    cs:__imp_UnregisterWaitEx
0x18000501a  mov     qword ptr [rbx+20h], 0
0x180005022  mov     rcx, [rbx+10h]
0x180005026  test    rcx, rcx
0x180005029  jz      short loc_180005039
0x18000502b  call    cs:__imp_WmiCloseBlock
0x180005031  mov     qword ptr [rbx+10h], 0
0x180005039  xor     eax, eax
0x18000503b  add     rsp, 20h
0x18000503f  pop     rbx
0x180005040  retn
```
