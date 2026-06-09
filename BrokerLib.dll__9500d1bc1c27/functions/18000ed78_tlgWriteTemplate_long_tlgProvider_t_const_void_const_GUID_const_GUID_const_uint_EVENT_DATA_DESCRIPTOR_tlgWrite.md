# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)

- ea: `0x18000ed78`
- end: `0x18000ee4e`
- name: `??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `214`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180012220`
- `0x1800183bc`
- `0x1800192fc`
- `0x18001c0e5`

## callees

- `0x180015af0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000ee33`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000ee33`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 *a5,
        __int64 a6)
{
  __int64 v6; // rcx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-9h] BYREF
  unsigned __int8 *v10; // [rsp+60h] [rbp+7h]
  int v11; // [rsp+68h] [rbp+Fh]
  int v12; // [rsp+6Ch] [rbp+13h]
  __int64 v13; // [rsp+70h] [rbp+17h]
  __int64 v14; // [rsp+78h] [rbp+1Fh]
  __int64 v15; // [rsp+80h] [rbp+27h]
  __int64 v16; // [rsp+88h] [rbp+2Fh]

  v15 = a6;
  v16 = 4;
  v14 = 16;
  v6 = *a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (ULONGLONG)off_180028008;
  v13 = v6;
  UserData.Size = *(unsigned __int16 *)off_180028008;
  v11 = *(unsigned __int16 *)(a2 + 11);
  v10 = a2 + 11;
  UserData.Reserved = 2;
  v12 = 1;
  return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
}

```

## disassembly

```asm
0x18000ed78  push    rbp
0x18000ed7a  lea     rbp, [rsp-47h]
0x18000ed7f  sub     rsp, 0A0h
0x18000ed86  mov     rax, cs:__security_cookie
0x18000ed8d  xor     rax, rsp
0x18000ed90  mov     [rbp+47h+var_10], rax
0x18000ed94  mov     rax, [rbp+47h+arg_28]
0x18000ed98  mov     r8d, 4
0x18000ed9e  mov     [rbp+47h+var_20], rax
0x18000eda2  xor     r9d, r9d; RelatedActivityId
0x18000eda5  mov     rax, [rbp+47h+arg_20]
0x18000eda9  mov     [rbp+47h+var_18], r8
0x18000edad  mov     [rbp+47h+var_28], 10h
0x18000edb5  mov     rcx, [rax]
0x18000edb8  movzx   eax, byte ptr [rdx]
0x18000edbb  shl     eax, 18h
0x18000edbe  mov     dword ptr [rbp+47h+EventDescriptor.Id], eax
0x18000edc1  movzx   eax, word ptr [rdx+1]
0x18000edc5  mov     dword ptr [rbp+47h+EventDescriptor.Level], eax
0x18000edc8  mov     rax, [rdx+3]
0x18000edcc  mov     [rbp+47h+EventDescriptor.Keyword], rax
0x18000edd0  mov     rax, cs:off_180028008
0x18000edd7  mov     [rbp+47h+var_50.Ptr], rax
0x18000eddb  mov     [rbp+47h+var_30], rcx
0x18000eddf  lea     rcx, [rdx+0Bh]
0x18000ede3  lea     rdx, [rbp+47h+EventDescriptor]; EventDescriptor
0x18000ede7  movzx   eax, word ptr [rax]
0x18000edea  mov     [rbp+47h+var_50.Size], eax
0x18000eded  movzx   eax, word ptr [rcx]
0x18000edf0  mov     [rbp+47h+var_38], eax
0x18000edf3  lea     rax, _TraceLoggingMetadataEnd
0x18000edfa  mov     [rbp+47h+var_40], rcx
0x18000edfe  lea     rcx, _TraceLoggingMetadata
0x18000ee05  sub     eax, ecx
0x18000ee07  mov     dword ptr [rbp+47h+var_50.0Ch], 2
0x18000ee0e  mov     [rbp+47h+var_34], 1
0x18000ee15  mov     [rbp+47h+var_70], eax
0x18000ee18  mov     eax, [rbp+47h+var_70]
0x18000ee1b  mov     rcx, cs:RegHandle; RegHandle
0x18000ee22  lea     rax, [rbp+47h+var_50]
0x18000ee26  mov     [rsp+0A0h+UserData], rax; UserData
0x18000ee2b  mov     [rsp+0A0h+UserDataCount], r8d; UserDataCount
0x18000ee30  xor     r8d, r8d; ActivityId
0x18000ee33  call    cs:__imp_EventWriteTransfer
0x18000ee39  mov     rcx, [rbp+47h+var_10]
0x18000ee3d  xor     rcx, rsp; StackCookie
0x18000ee40  call    __security_check_cookie
0x18000ee45  add     rsp, 0A0h
0x18000ee4c  pop     rbp
0x18000ee4d  retn
```
