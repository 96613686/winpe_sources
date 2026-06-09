# tlx::_delete<DbTransactedTableAccess<SharingToken>>(DbTransactedTableAccess<SharingToken> *)

- ea: `0x18001606c`
- end: `0x18001608c`
- name: `??$_delete@V?$DbTransactedTableAccess@VSharingToken@@@@@tlx@@YAXPEAV?$DbTransactedTableAccess@VSharingToken@@@@@Z`
- size: `32`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180015f2c`
- `0x18001616c`
- `0x1800163ec`
- `0x18001669c`
- `0x180017c90`

## callees

- `0x18000be3c`
- `0x18001606c`
- `0x180016268`

## pseudocode

```c
void __fastcall tlx::_delete<DbTransactedTableAccess<SharingToken>>(PVOID P)
{
  if ( P )
  {
    DbTransactedTableAccess<SharingToken>::~DbTransactedTableAccess<SharingToken>();
    Common::GlobalHeap::Free(P);
  }
}

```

## disassembly

```asm
0x18001606c  test    rcx, rcx
0x18001606f  jz      short locret_18001608B
0x180016071  push    rbx
0x180016072  sub     rsp, 20h
0x180016076  mov     rbx, rcx
0x180016079  call    ??1?$DbTransactedTableAccess@VSharingToken@@@@QEAA@XZ
0x18001607e  mov     rcx, rbx; P
0x180016081  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z
0x180016086  add     rsp, 20h
0x18001608a  pop     rbx
0x18001608b  retn
```
