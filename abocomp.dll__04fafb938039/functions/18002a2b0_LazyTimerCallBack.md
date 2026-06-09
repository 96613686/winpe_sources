# LazyTimerCallBack

- ea: `0x18002a2b0`
- end: `0x18002a327`
- name: `LazyTimerCallBack`
- size: `119`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001f90`
- `0x18002a004`
- `0x18002a070`
- `0x18002a2b0`

## import_xrefs

- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18002a311`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18002a311`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18002a2d6`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18002a2d6`

## string_xrefs

- `0x18002a301`: `Commit callback called on a tree that has been committed or discarded`

## pseudocode

```c
void __fastcall LazyTimerCallBack(PVOID a1)
{
  ABO_WRAPPER *v1; // rbx
  LAZY_WRITER *v2; // rsi

  v1 = g_pAboWrapper;
  if ( g_pAboWrapper )
  {
    v2 = (LAZY_WRITER *)*((_QWORD *)g_pAboWrapper + 28);
    CReaderWriterLock3::WriteLock((ABO_WRAPPER *)((char *)g_pAboWrapper + 32));
    LAZY_WRITER::ClearTimer(v2);
    if ( *((_QWORD *)v1 + 3) )
      LAZY_WRITER::CommitChanges((DWORD *)v2, 1);
    else
      ABO_MAPPER_LOG::WriteLogEntry(
        (HANDLE *)g_pAboLog,
        L"Commit callback called on a tree that has been committed or discarded");
    CReaderWriterLock3::WriteUnlock((ABO_WRAPPER *)((char *)v1 + 32));
  }
}

```

## disassembly

```asm
0x18002a2b0  mov     [rsp+arg_0], rbx
0x18002a2b5  mov     [rsp+arg_8], rsi
0x18002a2ba  push    rdi
0x18002a2bb  sub     rsp, 20h
0x18002a2bf  mov     rbx, cs:?g_pAboWrapper@@3PEAVABO_WRAPPER@@EA; ABO_WRAPPER * g_pAboWrapper
0x18002a2c6  test    rbx, rbx
0x18002a2c9  jz      short loc_18002A317
0x18002a2cb  mov     rsi, [rbx+0E0h]
0x18002a2d2  lea     rcx, [rbx+20h]
0x18002a2d6  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18002a2dc  mov     rcx, rsi; this
0x18002a2df  call    ?ClearTimer@LAZY_WRITER@@QEAAXXZ; LAZY_WRITER::ClearTimer(void)
0x18002a2e4  cmp     qword ptr [rbx+18h], 0
0x18002a2e9  jz      short loc_18002A2FA
0x18002a2eb  mov     edx, 1; int
0x18002a2f0  mov     rcx, rsi; this
0x18002a2f3  call    ?CommitChanges@LAZY_WRITER@@QEAAJH@Z; LAZY_WRITER::CommitChanges(int)
0x18002a2f8  jmp     short loc_18002A30D
0x18002a2fa  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x18002a301  lea     rdx, aCommitCallback; "Commit callback called on a tree that h"...
0x18002a308  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x18002a30d  lea     rcx, [rbx+20h]
0x18002a311  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18002a317  mov     rbx, [rsp+28h+arg_0]
0x18002a31c  mov     rsi, [rsp+28h+arg_8]
0x18002a321  add     rsp, 20h
0x18002a325  pop     rdi
0x18002a326  retn
```
