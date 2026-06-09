# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)

- ea: `0x140001008`
- end: `0x1400010b4`
- name: `??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z`
- size: `172`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x14000685c`
- `0x1400090cc`
- `0x140014d6c`
- `0x140033a28`
- `0x140033a60`

## callees

- `0x140038d10`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x14000109c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x14000109c`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        __int64 a1,
        unsigned __int8 *a2)
{
  int v2; // eax
  EVENT_DESCRIPTOR v4; // [rsp+38h] [rbp-40h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v5; // [rsp+48h] [rbp-30h] BYREF
  unsigned __int8 *v6; // [rsp+58h] [rbp-20h]
  int v7; // [rsp+60h] [rbp-18h]
  int v8; // [rsp+64h] [rbp-14h]

  *(_DWORD *)&v4.Id = *a2 << 24;
  *(_DWORD *)&v4.Level = *(unsigned __int16 *)(a2 + 1);
  v4.Keyword = *(_QWORD *)(a2 + 3);
  v5.Ptr = *(_QWORD *)(a1 + 8);
  v5.Size = *(unsigned __int16 *)v5.Ptr;
  v2 = *(unsigned __int16 *)(a2 + 11);
  v5.Reserved = 2;
  v6 = a2 + 11;
  v7 = v2;
  v8 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &v4, 0, 0, 2u, &v5);
}

```

## disassembly

```asm
0x140001008  mov     r11, rsp
0x14000100b  sub     rsp, 78h
0x14000100f  mov     rax, cs:__security_cookie
0x140001016  xor     rax, rsp
0x140001019  mov     [rsp+78h+var_10], rax
0x14000101e  movzx   eax, byte ptr [rdx]
0x140001021  mov     r10, rcx
0x140001024  shl     eax, 18h
0x140001027  lea     rcx, [rdx+0Bh]
0x14000102b  mov     [rsp+78h+var_40], eax
0x14000102f  xor     r9d, r9d; RelatedActivityId
0x140001032  movzx   eax, word ptr [rdx+1]
0x140001036  xor     r8d, r8d; ActivityId
0x140001039  mov     [rsp+78h+var_3C], eax
0x14000103d  mov     rax, [rdx+3]
0x140001041  mov     edx, 2
0x140001046  mov     [r11-38h], rax
0x14000104a  mov     rax, [r10+8]
0x14000104e  mov     [r11-30h], rax
0x140001052  movzx   eax, word ptr [rax]
0x140001055  mov     [rsp+78h+var_28], eax
0x140001059  movzx   eax, word ptr [rcx]
0x14000105c  mov     [rsp+78h+var_24], edx
0x140001060  mov     [r11-20h], rcx
0x140001064  lea     rcx, _TraceLoggingMetadata
0x14000106b  mov     [rsp+78h+var_18], eax
0x14000106f  lea     rax, _TraceLoggingMetadataEnd
0x140001076  sub     eax, ecx
0x140001078  mov     [rsp+78h+var_14], 1
0x140001080  mov     [rsp+78h+var_48], eax
0x140001084  mov     eax, [rsp+78h+var_48]
0x140001088  mov     rcx, [r10+20h]; RegHandle
0x14000108c  lea     rax, [r11-30h]
0x140001090  mov     [r11-50h], rax
0x140001094  mov     [rsp+78h+UserDataCount], edx; UserDataCount
0x140001098  lea     rdx, [r11-40h]; EventDescriptor
0x14000109c  call    cs:__imp_EventWriteTransfer
0x1400010a2  mov     rcx, [rsp+78h+var_10]
0x1400010a7  xor     rcx, rsp; StackCookie
0x1400010aa  call    __security_check_cookie
0x1400010af  add     rsp, 78h
0x1400010b3  retn
```
