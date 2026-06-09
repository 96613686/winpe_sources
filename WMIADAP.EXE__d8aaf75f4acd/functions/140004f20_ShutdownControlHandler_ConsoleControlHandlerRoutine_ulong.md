# ShutdownControlHandler::ConsoleControlHandlerRoutine(ulong)

- ea: `0x140004f20`
- end: `0x140004f74`
- name: `?ConsoleControlHandlerRoutine@ShutdownControlHandler@@CAHK@Z`
- size: `84`
- prototype: `__int64 __fastcall(DWORD CtrlType)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140004f20`
- `0x140005938`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140004f2e`
- `wbemcomn!GetMemLogObject` at `0x140004f2e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140004f3a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140004f3a`

## pseudocode

```c
__int64 __fastcall ShutdownControlHandler::ConsoleControlHandlerRoutine(DWORD CtrlType)
{
  CMemoryLog *MemLogObject; // rax

  ShutdownControlHandler::g_bShuttingDown = 1;
  MemLogObject = GetMemLogObject();
  CMemoryLog::Write(MemLogObject, -1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14);
  }
  return 0;
}

```

## disassembly

```asm
0x140004f20  sub     rsp, 28h
0x140004f24  mov     cs:?g_bShuttingDown@ShutdownControlHandler@@0HC, 1; int volatile ShutdownControlHandler::g_bShuttingDown
0x140004f2e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140004f34  mov     rcx, rax
0x140004f37  or      edx, 0FFFFFFFFh
0x140004f3a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140004f40  mov     rcx, cs:WPP_GLOBAL_Control
0x140004f47  lea     rax, WPP_GLOBAL_Control
0x140004f4e  cmp     rcx, rax
0x140004f51  jz      short loc_140004F6D
0x140004f53  test    byte ptr [rcx+1Ch], 1
0x140004f57  jz      short loc_140004F6D
0x140004f59  cmp     byte ptr [rcx+19h], 2
0x140004f5d  jb      short loc_140004F6D
0x140004f5f  mov     rcx, [rcx+10h]
0x140004f63  mov     edx, 0Eh
0x140004f68  call    WPP_SF_
0x140004f6d  xor     eax, eax
0x140004f6f  add     rsp, 28h
0x140004f73  retn
```
