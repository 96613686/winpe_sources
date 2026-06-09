# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)

- ea: `0x180001ca0`
- end: `0x180001d52`
- name: `??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z`
- size: `178`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001cc10`
- `0x180022260`

## callees

- `0x180034ef0`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x180001d3a`
- `ADVAPI32!EventWriteTransfer` at `0x180001d3a`

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
0x180001ca0  sub     rsp, 78h
0x180001ca4  mov     rax, cs:__security_cookie
0x180001cab  xor     rax, rsp
0x180001cae  mov     [rsp+78h+var_10], rax
0x180001cb3  movzx   eax, byte ptr [rdx]
0x180001cb6  mov     r10, rcx
0x180001cb9  shl     eax, 18h
0x180001cbc  lea     rcx, [rdx+0Bh]
0x180001cc0  mov     dword ptr [rsp+78h+EventDescriptor.Id], eax
0x180001cc4  xor     r9d, r9d; RelatedActivityId
0x180001cc7  movzx   eax, word ptr [rdx+1]
0x180001ccb  xor     r8d, r8d; ActivityId
0x180001cce  mov     dword ptr [rsp+78h+EventDescriptor.Level], eax
0x180001cd2  mov     rax, [rdx+3]
0x180001cd6  lea     rdx, [rsp+78h+EventDescriptor]; EventDescriptor
0x180001cdb  mov     [rsp+78h+EventDescriptor.Keyword], rax
0x180001ce0  mov     rax, [r10+8]
0x180001ce4  mov     [rsp+78h+var_30.Ptr], rax
0x180001ce9  movzx   eax, word ptr [rax]
0x180001cec  mov     [rsp+78h+var_30.Size], eax
0x180001cf0  movzx   eax, word ptr [rcx]
0x180001cf3  mov     [rsp+78h+var_18], eax
0x180001cf7  lea     rax, _TraceLoggingMetadataEnd
0x180001cfe  mov     [rsp+78h+var_20], rcx
0x180001d03  lea     rcx, _TraceLoggingMetadata
0x180001d0a  sub     eax, ecx
0x180001d0c  mov     dword ptr [rsp+78h+var_30.0Ch], 2
0x180001d14  mov     [rsp+78h+var_14], 1
0x180001d1c  mov     [rsp+78h+var_48], eax
0x180001d20  mov     eax, [rsp+78h+var_48]
0x180001d24  mov     rcx, [r10+20h]; RegHandle
0x180001d28  lea     rax, [rsp+78h+var_30]
0x180001d2d  mov     [rsp+78h+UserData], rax; UserData
0x180001d32  mov     [rsp+78h+UserDataCount], 2; UserDataCount
0x180001d3a  call    cs:__imp_EventWriteTransfer
0x180001d40  mov     rcx, [rsp+78h+var_10]
0x180001d45  xor     rcx, rsp; StackCookie
0x180001d48  call    __security_check_cookie
0x180001d4d  add     rsp, 78h
0x180001d51  retn
```
