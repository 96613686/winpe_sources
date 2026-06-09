# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)

- ea: `0x18000dab0`
- end: `0x18000db65`
- name: `??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z`
- size: `181`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180010650`
- `0x180011f30`
- `0x180012170`
- `0x180019620`

## callees

- `0x18001aec0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000db4d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000db4d`

## pseudocode

```c
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
  UserData.Ptr = (ULONGLONG)off_18002E040;
  UserData.Size = (unsigned __int16)*off_18002E040;
  v6 = *(unsigned __int16 *)(a2 + 11);
  v5 = a2 + 11;
  UserData.Reserved = 2;
  v7 = 1;
  return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, &UserData);
}

```

## disassembly

```asm
0x18000dab0  sub     rsp, 78h
0x18000dab4  mov     rax, cs:__security_cookie
0x18000dabb  xor     rax, rsp
0x18000dabe  mov     [rsp+78h+var_10], rax
0x18000dac3  movzx   eax, byte ptr [rdx]
0x18000dac6  lea     rcx, [rdx+0Bh]
0x18000daca  shl     eax, 18h
0x18000dacd  xor     r9d, r9d; RelatedActivityId
0x18000dad0  mov     dword ptr [rsp+78h+EventDescriptor.Id], eax
0x18000dad4  xor     r8d, r8d; ActivityId
0x18000dad7  movzx   eax, word ptr [rdx+1]
0x18000dadb  mov     dword ptr [rsp+78h+EventDescriptor.Level], eax
0x18000dadf  mov     rax, [rdx+3]
0x18000dae3  lea     rdx, [rsp+78h+EventDescriptor]; EventDescriptor
0x18000dae8  mov     [rsp+78h+EventDescriptor.Keyword], rax
0x18000daed  mov     rax, cs:off_18002E040
0x18000daf4  mov     [rsp+78h+var_30.Ptr], rax
0x18000daf9  movzx   eax, word ptr [rax]
0x18000dafc  mov     [rsp+78h+var_30.Size], eax
0x18000db00  movzx   eax, word ptr [rcx]
0x18000db03  mov     [rsp+78h+var_18], eax
0x18000db07  lea     rax, _TraceLoggingMetadataEnd
0x18000db0e  mov     [rsp+78h+var_20], rcx
0x18000db13  lea     rcx, _TraceLoggingMetadata
0x18000db1a  sub     eax, ecx
0x18000db1c  mov     dword ptr [rsp+78h+var_30.0Ch], 2
0x18000db24  mov     [rsp+78h+var_14], 1
0x18000db2c  mov     [rsp+78h+var_48], eax
0x18000db30  mov     eax, [rsp+78h+var_48]
0x18000db34  mov     rcx, cs:RegHandle; RegHandle
0x18000db3b  lea     rax, [rsp+78h+var_30]
0x18000db40  mov     [rsp+78h+UserData], rax; UserData
0x18000db45  mov     [rsp+78h+UserDataCount], 2; UserDataCount
0x18000db4d  call    cs:__imp_EventWriteTransfer
0x18000db53  mov     rcx, [rsp+78h+var_10]
0x18000db58  xor     rcx, rsp; StackCookie
0x18000db5b  call    __security_check_cookie
0x18000db60  add     rsp, 78h
0x18000db64  retn
```
