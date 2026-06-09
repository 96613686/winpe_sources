# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)

- ea: `0x1800018b0`
- end: `0x180001962`
- name: `??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z`
- size: `178`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *)`
- caller_count: `28`
- callee_count: `1`
- tags: ``

## callers

- `0x180009bb0`
- `0x180009e70`
- `0x18000a710`
- `0x18000afa0`
- `0x18000b2a0`
- `0x180017600`
- `0x180017760`
- `0x180017960`
- `0x180018550`
- `0x18001bcf0`
- `0x18001bfc0`
- `0x18001c120`
- `0x18001c320`
- `0x18001cc80`
- `0x180033f70`
- `0x180034400`
- `0x180034b20`
- `0x180034c70`
- `0x180034e70`
- `0x180034f70`
- `0x18003f9f0`
- `0x18003fb50`
- `0x18003fd50`
- `0x1800406a0`
- `0x180052c90`
- `0x180053610`
- `0x1800583b0`
- `0x18005bc90`

## callees

- `0x18004c070`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000194a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000194a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        __int64 a1,
        unsigned __int8 *a2)
{
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-40h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+48h] [rbp-30h] BYREF
  unsigned __int8 *v5; // [rsp+58h] [rbp-20h]
  int v6; // [rsp+60h] [rbp-18h]
  int v7; // [rsp+64h] [rbp-14h]

  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = *(_QWORD *)(a1 + 8);
  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
  v6 = *(unsigned __int16 *)(a2 + 11);
  v5 = a2 + 11;
  UserData.Reserved = 2;
  v7 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, 0, 0, 2u, &UserData);
}

```

## disassembly

```asm
0x1800018b0  sub     rsp, 78h
0x1800018b4  mov     rax, cs:__security_cookie
0x1800018bb  xor     rax, rsp
0x1800018be  mov     [rsp+78h+var_10], rax
0x1800018c3  movzx   eax, byte ptr [rdx]
0x1800018c6  mov     r10, rcx
0x1800018c9  shl     eax, 18h
0x1800018cc  lea     rcx, [rdx+0Bh]
0x1800018d0  mov     dword ptr [rsp+78h+EventDescriptor.Id], eax
0x1800018d4  xor     r9d, r9d; RelatedActivityId
0x1800018d7  movzx   eax, word ptr [rdx+1]
0x1800018db  xor     r8d, r8d; ActivityId
0x1800018de  mov     dword ptr [rsp+78h+EventDescriptor.Level], eax
0x1800018e2  mov     rax, [rdx+3]
0x1800018e6  lea     rdx, [rsp+78h+EventDescriptor]; EventDescriptor
0x1800018eb  mov     [rsp+78h+EventDescriptor.Keyword], rax
0x1800018f0  mov     rax, [r10+8]
0x1800018f4  mov     [rsp+78h+var_30.Ptr], rax
0x1800018f9  movzx   eax, word ptr [rax]
0x1800018fc  mov     [rsp+78h+var_30.Size], eax
0x180001900  movzx   eax, word ptr [rcx]
0x180001903  mov     [rsp+78h+var_18], eax
0x180001907  lea     rax, _TraceLoggingMetadataEnd
0x18000190e  mov     [rsp+78h+var_20], rcx
0x180001913  lea     rcx, _TraceLoggingMetadata
0x18000191a  sub     eax, ecx
0x18000191c  mov     dword ptr [rsp+78h+var_30.0Ch], 2
0x180001924  mov     [rsp+78h+var_14], 1
0x18000192c  mov     [rsp+78h+var_48], eax
0x180001930  mov     eax, [rsp+78h+var_48]
0x180001934  mov     rcx, [r10+20h]; RegHandle
0x180001938  lea     rax, [rsp+78h+var_30]
0x18000193d  mov     [rsp+78h+UserData], rax; UserData
0x180001942  mov     [rsp+78h+UserDataCount], 2; UserDataCount
0x18000194a  call    cs:__imp_EventWriteTransfer
0x180001950  mov     rcx, [rsp+78h+var_10]
0x180001955  xor     rcx, rsp; StackCookie
0x180001958  call    __security_check_cookie
0x18000195d  add     rsp, 78h
0x180001961  retn
```
