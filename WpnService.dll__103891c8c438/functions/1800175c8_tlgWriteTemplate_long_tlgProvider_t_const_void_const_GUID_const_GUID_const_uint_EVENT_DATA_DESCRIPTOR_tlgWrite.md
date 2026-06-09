# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)

- ea: `0x1800175c8`
- end: `0x180017671`
- name: `??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z`
- size: `169`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180021270`
- `0x180022eec`
- `0x18002bb04`
- `0x18002d0ec`
- `0x18002f9b0`
- `0x1800328a0`
- `0x1800328d0`

## callees

- `0x180026200`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180017659`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180017659`

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
0x1800175c8  mov     r11, rsp
0x1800175cb  sub     rsp, 78h
0x1800175cf  mov     rax, cs:__security_cookie
0x1800175d6  xor     rax, rsp
0x1800175d9  mov     [rsp+78h+var_10], rax
0x1800175de  movzx   eax, byte ptr [rdx]
0x1800175e1  mov     r10, rcx
0x1800175e4  shl     eax, 18h
0x1800175e7  lea     rcx, [rdx+0Bh]
0x1800175eb  mov     [rsp+78h+var_40], eax
0x1800175ef  xor     r9d, r9d; RelatedActivityId
0x1800175f2  movzx   eax, word ptr [rdx+1]
0x1800175f6  mov     [rsp+78h+var_3C], eax
0x1800175fa  mov     rax, [rdx+3]
0x1800175fe  mov     edx, 2
0x180017603  mov     [r11-38h], rax
0x180017607  mov     rax, [r10+8]
0x18001760b  mov     [r11-30h], rax
0x18001760f  movzx   eax, word ptr [rax]
0x180017612  mov     [rsp+78h+var_28], eax
0x180017616  movzx   eax, word ptr [rcx]
0x180017619  mov     [rsp+78h+var_24], edx
0x18001761d  mov     [r11-20h], rcx
0x180017621  lea     rcx, _TraceLoggingMetadata
0x180017628  mov     [rsp+78h+var_18], eax
0x18001762c  lea     rax, _TraceLoggingMetadataEnd
0x180017633  sub     eax, ecx
0x180017635  mov     [rsp+78h+var_14], 1
0x18001763d  mov     [rsp+78h+var_48], eax
0x180017641  mov     eax, [rsp+78h+var_48]
0x180017645  mov     rcx, [r10+20h]; RegHandle
0x180017649  lea     rax, [r11-30h]
0x18001764d  mov     [r11-50h], rax
0x180017651  mov     [rsp+78h+UserDataCount], edx; UserDataCount
0x180017655  lea     rdx, [r11-40h]; EventDescriptor
0x180017659  call    cs:__imp_EventWriteTransfer
0x18001765f  mov     rcx, [rsp+78h+var_10]
0x180017664  xor     rcx, rsp; StackCookie
0x180017667  call    __security_check_cookie
0x18001766c  add     rsp, 78h
0x180017670  retn
```
