# SocketBrokerTable::~SocketBrokerTable(void)

- ea: `0x1800261b4`
- end: `0x1800261d2`
- name: `??1SocketBrokerTable@@QEAA@XZ`
- size: `30`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180026a08`

## callees

- `0x1800262c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800261c5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800261c5`

## pseudocode

```c
void __fastcall SocketBrokerTable::~SocketBrokerTable(LPCRITICAL_SECTION lpCriticalSection)
{
  SocketBrokerTable::CleanAll(lpCriticalSection);
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x1800261b4  push    rbx
0x1800261b6  sub     rsp, 20h
0x1800261ba  mov     rbx, rcx
0x1800261bd  call    ?CleanAll@SocketBrokerTable@@AEAAXXZ; SocketBrokerTable::CleanAll(void)
0x1800261c2  mov     rcx, rbx; lpCriticalSection
0x1800261c5  call    cs:__imp_DeleteCriticalSection
0x1800261cb  nop
0x1800261cc  add     rsp, 20h
0x1800261d0  pop     rbx
0x1800261d1  retn
```
