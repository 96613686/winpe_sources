# ScoCxnS_ConnectionRequestEvent(_SCO_INTERFACE *,_HCI_COMMAND *,_HCI_EVENT *,_HCI_CONNECTION *)

- ea: `0x14013a260`
- end: `0x14013a97c`
- name: `?ScoCxnS_ConnectionRequestEvent@@YAEPEAU_SCO_INTERFACE@@PEAT_HCI_COMMAND@@PEAT_HCI_EVENT@@PEAU_HCI_CONNECTION@@@Z`
- size: `1820`
- prototype: `unsigned __int8 __fastcall(struct _SCO_INTERFACE *, union _HCI_COMMAND *, union _HCI_EVENT *, struct _HCI_CONNECTION *)`
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x140037f30`

## callees

- `0x140005608`
- `0x140005690`
- `0x140005748`
- `0x140005b4c`
- `0x140005c04`
- `0x14000bdb8`
- `0x14003667c`
- `0x140039854`
- `0x140132efc`
- `0x140135f80`
- `0x1401367ec`
- `0x14013728c`
- `0x140138b08`
- `0x140139c94`
- `0x14013a260`
- `0x14013c2c4`
- `0x14013c434`
- `0x14013e51c`
- `0x1401429d0`
- `0x140161a44`
- `0x140161d7c`
- `0x140165580`

## import_xrefs

- `ntoskrnl!KeSetTimer` at `0x14013a782`
- `ntoskrnl!KeSetTimer` at `0x14013a782`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14013a798`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14013a798`
- `ntoskrnl!KeReleaseSpinLock` at `0x14013a7b1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14013a7b1`

## pseudocode

```c

```
