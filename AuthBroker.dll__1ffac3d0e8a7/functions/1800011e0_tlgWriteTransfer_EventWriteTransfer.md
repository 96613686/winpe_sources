# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x1800011e0`
- end: `0x180001277`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `HRESULT __fastcall(const _tlgProvider_t *hProvider, const void *pEventMetadata, const _GUID *pActivityId, const _GUID *pRelatedActivityId, unsigned int cData, _EVENT_DATA_DESCRIPTOR *pData)`
- caller_count: `18`
- callee_count: `0`
- tags: ``

## callers

- `0x18000102c`
- `0x180001150`
- `0x180001280`
- `0x1800012c4`
- `0x180001354`
- `0x1800013fc`
- `0x180001488`
- `0x1800014fc`
- `0x180001558`
- `0x18000180c`
- `0x1800018b4`
- `0x1800019e0`
- `0x180001a50`
- `0x180001ae0`
- `0x180001d84`
- `0x18000207c`
- `0x180015f40`
- `0x180016018`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000126c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000126c`

## pseudocode

```c
ULONG __fastcall tlgWriteTransfer_EventWriteTransfer(
        const _tlgProvider_t *hProvider,
        char *pEventMetadata,
        const _GUID *pActivityId,
        const _GUID *pRelatedActivityId,
        ULONG cData,
        _EVENT_DATA_DESCRIPTOR *pData)
{
  unsigned __int64 v6; // rax
  unsigned __int16 *v7; // rdx
  _EVENT_DESCRIPTOR desc; // [rsp+30h] [rbp-18h] BYREF

  *(_DWORD *)&desc.Id = (unsigned __int8)*pEventMetadata << 24;
  *(_DWORD *)&desc.Level = *(unsigned __int16 *)(pEventMetadata + 1);
  v6 = *(_QWORD *)(pEventMetadata + 3);
  v7 = (unsigned __int16 *)(pEventMetadata + 11);
  desc.Keyword = v6;
  pData->Ptr = (unsigned __int64)hProvider->ProviderMetadataPtr;
  pData->Size = *hProvider->ProviderMetadataPtr;
  pData[1].Ptr = (unsigned __int64)v7;
  pData->Reserved = 2;
  pData[1].Size = *v7;
  pData[1].Reserved = 1;
  return EventWriteTransfer(hProvider->RegHandle, &desc, pActivityId, pRelatedActivityId, cData, pData);
}

```

## disassembly

```asm
0x1800011e0  sub     rsp, 48h
0x1800011e4  movzx   eax, byte ptr [pEventMetadata]
0x1800011e7  mov     r11, hProvider
0x1800011ea  shl     eax, 18h
0x1800011ed  mov     r10, pActivityId
0x1800011f0  mov     pActivityId, [rsp+48h+arg_28]
0x1800011f5  mov     dword ptr [rsp+48h+desc.Id], eax
0x1800011f9  movzx   eax, word ptr [pEventMetadata+1]
0x1800011fd  mov     dword ptr [rsp+48h+desc.Level], eax
0x180001201  mov     rax, [pEventMetadata+3]
0x180001205  add     pEventMetadata, 0Bh
0x180001209  mov     [rsp+48h+desc.Keyword], rax
0x18000120e  mov     rax, [hProvider+8]
0x180001212  mov     [pActivityId], rax
0x180001215  mov     rax, [hProvider+8]
0x180001219  mov     [rsp+48h+UserData], pActivityId; UserData
0x18000121e  movzx   ecx, word ptr [rax]
0x180001221  mov     [pActivityId+8], ecx
0x180001225  lea     hProvider, _TraceLoggingMetadata
0x18000122c  mov     [pActivityId+10h], pEventMetadata
0x180001230  mov     dword ptr [pActivityId+0Ch], 2
0x180001238  movzx   eax, word ptr [pEventMetadata]
0x18000123b  lea     pEventMetadata, [rsp+48h+desc]; EventDescriptor
0x180001240  mov     [pActivityId+18h], eax
0x180001244  lea     rax, _TraceLoggingMetadataEnd
0x18000124b  sub     eax, ecx
0x18000124d  mov     dword ptr [pActivityId+1Ch], 1
0x180001255  mov     dword ptr [rsp+48h+arg_28], eax
0x180001259  mov     pActivityId, r10; ActivityId
0x18000125c  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001260  mov     eax, [rsp+48h+arg_20]
0x180001264  mov     hProvider, [r11+20h]; RegHandle
0x180001268  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x18000126c  call    cs:__imp_EventWriteTransfer
0x180001272  add     rsp, 48h
0x180001276  retn
```
