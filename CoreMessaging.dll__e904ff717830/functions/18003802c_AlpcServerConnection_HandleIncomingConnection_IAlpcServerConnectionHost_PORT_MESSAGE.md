# AlpcServerConnection::HandleIncomingConnection(IAlpcServerConnectionHost *,_PORT_MESSAGE *)

- ea: `0x18003802c`
- end: `0x18003821c`
- name: `?HandleIncomingConnection@AlpcServerConnection@@AEAAXPEAUIAlpcServerConnectionHost@@PEAU_PORT_MESSAGE@@@Z`
- size: `496`
- prototype: `void __fastcall(AlpcServerConnection *__hidden this, struct IAlpcServerConnectionHost *, struct _PORT_MESSAGE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180038cbc`

## callees

- `0x18003773c`
- `0x18003802c`
- `0x18003950c`
- `0x180039a24`
- `0x18009d670`
- `0x18009e054`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003818a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003818a`
- `ntdll!NtClose` at `0x1800381fe`
- `ntdll!NtClose` at `0x1800381fe`
- `ntdll!NtAlpcAcceptConnectPort` at `0x180038124`
- `ntdll!NtAlpcAcceptConnectPort` at `0x180038124`

## pseudocode

```c

```
