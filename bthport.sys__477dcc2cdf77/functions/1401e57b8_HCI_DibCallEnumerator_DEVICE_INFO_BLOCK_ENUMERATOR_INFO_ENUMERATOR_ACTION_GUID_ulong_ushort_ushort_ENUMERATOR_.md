# HCI_DibCallEnumerator(DEVICE_INFO_BLOCK *,_ENUMERATOR_INFO * *,_ENUMERATOR_ACTION,_GUID *,ulong,ushort *,ushort *,_ENUMERATOR_TYPE *,_DIB_SERVICE_DESCRIPTOR *,uchar,uchar)

- ea: `0x1401e57b8`
- end: `0x1401e6295`
- name: `?HCI_DibCallEnumerator@@YAJPEAUDEVICE_INFO_BLOCK@@PEAPEAU_ENUMERATOR_INFO@@W4_ENUMERATOR_ACTION@@PEAU_GUID@@KPEAG4PEAW4_ENUMERATOR_TYPE@@PEAU_DIB_SERVICE_DESCRIPTOR@@EE@Z`
- size: `2781`
- prototype: `__int64 __usercall@<rax>(struct DEVICE_INFO_BLOCK *@<rcx>, struct _ENUMERATOR_INFO **@<rdx>, enum _ENUMERATOR_ACTION@<r8d>, struct _GUID *@<r9>, unsigned int, unsigned __int16 *, unsigned __int16 *, enum _ENUMERATOR_TYPE *, struct _DIB_SERVICE_DESCRIPTOR *, unsigned __int8, unsigned __int8)`
- caller_count: `6`
- callee_count: `14`
- tags: `service_task`

## callers

- `0x14011fac0`
- `0x14011ff10`
- `0x1401e629c`
- `0x1401e6438`
- `0x1401e64e4`
- `0x1401e83dc`

## callees

- `0x140004368`
- `0x140005690`
- `0x14000c74c`
- `0x140020330`
- `0x140050abc`
- `0x140050b1c`
- `0x1400649d8`
- `0x140130e24`
- `0x140130f0c`
- `0x140165580`
- `0x140165640`
- `0x140165940`
- `0x1401e57b8`
- `0x1401e7c5c`

## import_xrefs

- `ntoskrnl!ExSystemTimeToLocalTime` at `0x1401e5a7b`
- `ntoskrnl!ExSystemTimeToLocalTime` at `0x1401e5a7b`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1401e59b4`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1401e6100`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1401e621c`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1401e59b4`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1401e6100`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1401e621c`

## pseudocode

```c

```
