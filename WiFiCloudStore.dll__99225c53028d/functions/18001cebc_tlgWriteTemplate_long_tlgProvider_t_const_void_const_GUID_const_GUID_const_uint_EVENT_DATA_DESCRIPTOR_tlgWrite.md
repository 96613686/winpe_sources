# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)

- ea: `0x18001cebc`
- end: `0x18001cf65`
- name: `??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z`
- size: `169`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180015b6c`
- `0x180016794`
- `0x18002f8f8`
- `0x180036474`
- `0x1800364c8`
- `0x18003bb30`

## callees

- `0x18002a030`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001cf4d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001cf4d`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3)
{
  int v3; // eax
  EVENT_DESCRIPTOR v5; // [rsp+38h] [rbp-40h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+48h] [rbp-30h] BYREF
  unsigned __int8 *v7; // [rsp+58h] [rbp-20h]
  int v8; // [rsp+60h] [rbp-18h]
  int v9; // [rsp+64h] [rbp-14h]

  *(_DWORD *)&v5.Id = *a2 << 24;
  *(_DWORD *)&v5.Level = *(unsigned __int16 *)(a2 + 1);
  v5.Keyword = *(_QWORD *)(a2 + 3);
  v6.Ptr = *(_QWORD *)(a1 + 8);
  v6.Size = *(unsigned __int16 *)v6.Ptr;
  v3 = *(unsigned __int16 *)(a2 + 11);
  v6.Reserved = 2;
  v7 = a2 + 11;
  v8 = v3;
  v9 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &v5, a3, 0, 2u, &v6);
}

```

## disassembly

```asm
0x18001cebc  mov     r11, rsp
0x18001cebf  sub     rsp, 78h
0x18001cec3  mov     rax, cs:__security_cookie
0x18001ceca  xor     rax, rsp
0x18001cecd  mov     [rsp+78h+var_10], rax
0x18001ced2  movzx   eax, byte ptr [rdx]
0x18001ced5  mov     r10, rcx
0x18001ced8  shl     eax, 18h
0x18001cedb  lea     rcx, [rdx+0Bh]
0x18001cedf  mov     [rsp+78h+var_40], eax
0x18001cee3  xor     r9d, r9d; RelatedActivityId
0x18001cee6  movzx   eax, word ptr [rdx+1]
0x18001ceea  mov     [rsp+78h+var_3C], eax
0x18001ceee  mov     rax, [rdx+3]
0x18001cef2  mov     edx, 2
0x18001cef7  mov     [r11-38h], rax
0x18001cefb  mov     rax, [r10+8]
0x18001ceff  mov     [r11-30h], rax
0x18001cf03  movzx   eax, word ptr [rax]
0x18001cf06  mov     [rsp+78h+var_28], eax
0x18001cf0a  movzx   eax, word ptr [rcx]
0x18001cf0d  mov     [rsp+78h+var_24], edx
0x18001cf11  mov     [r11-20h], rcx
0x18001cf15  lea     rcx, _TraceLoggingMetadata
0x18001cf1c  mov     [rsp+78h+var_18], eax
0x18001cf20  lea     rax, _TraceLoggingMetadataEnd
0x18001cf27  sub     eax, ecx
0x18001cf29  mov     [rsp+78h+var_14], 1
0x18001cf31  mov     [rsp+78h+var_48], eax
0x18001cf35  mov     eax, [rsp+78h+var_48]
0x18001cf39  mov     rcx, [r10+20h]; RegHandle
0x18001cf3d  lea     rax, [r11-30h]
0x18001cf41  mov     [r11-50h], rax
0x18001cf45  mov     [rsp+78h+UserDataCount], edx; UserDataCount
0x18001cf49  lea     rdx, [r11-40h]; EventDescriptor
0x18001cf4d  call    cs:__imp_EventWriteTransfer
0x18001cf53  mov     rcx, [rsp+78h+var_10]
0x18001cf58  xor     rcx, rsp; StackCookie
0x18001cf5b  call    __security_check_cookie
0x18001cf60  add     rsp, 78h
0x18001cf64  retn
```
