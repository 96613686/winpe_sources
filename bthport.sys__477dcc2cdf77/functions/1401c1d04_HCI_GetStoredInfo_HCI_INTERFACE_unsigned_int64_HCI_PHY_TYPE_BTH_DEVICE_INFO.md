# HCI_GetStoredInfo(HCI_INTERFACE *,unsigned __int64 *,_HCI_PHY_TYPE,_BTH_DEVICE_INFO *)

- ea: `0x1401c1d04`
- end: `0x1401c2232`
- name: `?HCI_GetStoredInfo@@YAJPEAUHCI_INTERFACE@@PEA_KW4_HCI_PHY_TYPE@@PEAU_BTH_DEVICE_INFO@@@Z`
- size: `1326`
- prototype: `__int64 __fastcall(struct HCI_INTERFACE *, unsigned __int64 *, enum _HCI_PHY_TYPE, struct _BTH_DEVICE_INFO *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x140064d4c`

## callees

- `0x14000f27c`
- `0x14000fab4`
- `0x140165540`
- `0x140165640`
- `0x1401c18d0`
- `0x1401c1c04`
- `0x1401c1d04`
- `0x14020934c`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x1401c1ddd`
- `ntoskrnl!ZwQueryValueKey` at `0x1401c1e44`
- `ntoskrnl!ZwQueryValueKey` at `0x1401c1eac`
- `ntoskrnl!ZwQueryValueKey` at `0x1401c1f12`
- `ntoskrnl!ZwQueryValueKey` at `0x1401c1f99`
- `ntoskrnl!ZwQueryValueKey` at `0x1401c2001`
- `ntoskrnl!ZwQueryValueKey` at `0x1401c20aa`
- `ntoskrnl!ZwQueryValueKey` at `0x1401c2103`
- `ntoskrnl!ZwQueryValueKey` at `0x1401c2176`
- `ntoskrnl!ZwQueryValueKey` at `0x1401c1ddd`
- `ntoskrnl!ZwQueryValueKey` at `0x1401c1e44`
- `ntoskrnl!ZwQueryValueKey` at `0x1401c1eac`
- `ntoskrnl!ZwQueryValueKey` at `0x1401c1f12`
- `ntoskrnl!ZwQueryValueKey` at `0x1401c1f99`
- `ntoskrnl!ZwQueryValueKey` at `0x1401c2001`
- `ntoskrnl!ZwQueryValueKey` at `0x1401c20aa`
- `ntoskrnl!ZwQueryValueKey` at `0x1401c2103`
- `ntoskrnl!ZwQueryValueKey` at `0x1401c2176`
- `ntoskrnl!ZwClose` at `0x1401c2034`
- `ntoskrnl!ZwClose` at `0x1401c21f6`
- `ntoskrnl!ZwClose` at `0x1401c2034`
- `ntoskrnl!ZwClose` at `0x1401c21f6`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401c1dad`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401c1e14`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401c1e7c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401c1ee2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401c1f69`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401c1fd1`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401c2079`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401c20d7`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401c214a`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401c21a3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401c1dad`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401c1e14`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401c1e7c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401c1ee2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401c1f69`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401c1fd1`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401c2079`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401c20d7`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401c214a`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401c21a3`

## string_xrefs

- `0x1401c2197`: `DynamicCachedServices`

## pseudocode

```c

```
