# HANDLE_ENTRY::Create(ushort const *)

- ea: `0x18000c944`
- end: `0x18000c97b`
- name: `?Create@HANDLE_ENTRY@@QEAAJPEBG@Z`
- size: `55`
- prototype: `__int64 __fastcall(HANDLE_ENTRY *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000bf00`
- `0x18000ed00`

## callees

- `0x18000c944`
- `0x18000f754`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000c963`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000c963`

## pseudocode

```c
int __fastcall HANDLE_ENTRY::Create(HANDLE_ENTRY *this, const unsigned __int16 *a2)
{
  struct STRU *v2; // rbx
  int result; // eax

  v2 = (HANDLE_ENTRY *)((char *)this + 16);
  *((_DWORD *)this + 3) = _InterlockedIncrement(&HANDLE_ENTRY::sm_lHandleCount);
  result = STRU::Copy((HANDLE_ENTRY *)((char *)this + 16), a2);
  if ( result >= 0 )
    return HANDLE_ENTRY::SanitizePath(v2);
  return result;
}

```

## disassembly

```asm
0x18000c944  push    rbx
0x18000c946  sub     rsp, 20h
0x18000c94a  mov     eax, 1
0x18000c94f  lock xadd cs:?sm_lHandleCount@HANDLE_ENTRY@@0JC, eax; long volatile HANDLE_ENTRY::sm_lHandleCount
0x18000c957  inc     eax
0x18000c959  lea     rbx, [rcx+10h]
0x18000c95d  mov     [rcx+0Ch], eax
0x18000c960  mov     rcx, rbx
0x18000c963  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000c969  test    eax, eax
0x18000c96b  js      short loc_18000C975
0x18000c96d  mov     rcx, rbx; struct STRU *
0x18000c970  call    ?SanitizePath@HANDLE_ENTRY@@CAJPEAVSTRU@@@Z; HANDLE_ENTRY::SanitizePath(STRU *)
0x18000c975  add     rsp, 20h
0x18000c979  pop     rbx
0x18000c97a  retn
```
