# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x18000f888`
- end: `0x18000f96f`
- name: `??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@4@Z`
- size: `231`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180005724`
- `0x1800194c4`
- `0x180019538`

## callees

- `0x180015af0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000f954`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000f954`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 *a5,
        __int64 a6,
        __int64 a7)
{
  __int64 v7; // rcx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-21h] BYREF
  unsigned __int8 *v11; // [rsp+60h] [rbp-11h]
  int v12; // [rsp+68h] [rbp-9h]
  int v13; // [rsp+6Ch] [rbp-5h]
  __int64 v14; // [rsp+70h] [rbp-1h]
  __int64 v15; // [rsp+78h] [rbp+7h]
  __int64 v16; // [rsp+80h] [rbp+Fh]
  __int64 v17; // [rsp+88h] [rbp+17h]
  __int64 v18; // [rsp+90h] [rbp+1Fh]
  __int64 v19; // [rsp+98h] [rbp+27h]

  v18 = a7;
  v16 = a6;
  v19 = 4;
  v17 = 4;
  v15 = 16;
  v7 = *a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (ULONGLONG)off_180028008;
  v14 = v7;
  UserData.Size = *(unsigned __int16 *)off_180028008;
  v12 = *(unsigned __int16 *)(a2 + 11);
  v11 = a2 + 11;
  UserData.Reserved = 2;
  v13 = 1;
  return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 5u, &UserData);
}

```

## disassembly

```asm
0x18000f888  push    rbp
0x18000f88a  lea     rbp, [rsp-3Fh]
0x18000f88f  sub     rsp, 0B0h
0x18000f896  mov     rax, cs:__security_cookie
0x18000f89d  xor     rax, rsp
0x18000f8a0  mov     [rbp+3Fh+var_10], rax
0x18000f8a4  mov     rax, [rbp+3Fh+arg_30]
0x18000f8a8  xor     r9d, r9d; RelatedActivityId
0x18000f8ab  mov     [rbp+3Fh+var_20], rax
0x18000f8af  xor     r8d, r8d; ActivityId
0x18000f8b2  mov     rax, [rbp+3Fh+arg_28]
0x18000f8b6  mov     [rbp+3Fh+var_30], rax
0x18000f8ba  mov     rax, [rbp+3Fh+arg_20]
0x18000f8be  mov     [rbp+3Fh+var_18], 4
0x18000f8c6  mov     [rbp+3Fh+var_28], 4
0x18000f8ce  mov     [rbp+3Fh+var_38], 10h
0x18000f8d6  mov     rcx, [rax]
0x18000f8d9  movzx   eax, byte ptr [rdx]
0x18000f8dc  shl     eax, 18h
0x18000f8df  mov     dword ptr [rbp+3Fh+EventDescriptor.Id], eax
0x18000f8e2  movzx   eax, word ptr [rdx+1]
0x18000f8e6  mov     dword ptr [rbp+3Fh+EventDescriptor.Level], eax
0x18000f8e9  mov     rax, [rdx+3]
0x18000f8ed  mov     [rbp+3Fh+EventDescriptor.Keyword], rax
0x18000f8f1  mov     rax, cs:off_180028008
0x18000f8f8  mov     [rbp+3Fh+var_60.Ptr], rax
0x18000f8fc  mov     [rbp+3Fh+var_40], rcx
0x18000f900  lea     rcx, [rdx+0Bh]
0x18000f904  lea     rdx, [rbp+3Fh+EventDescriptor]; EventDescriptor
0x18000f908  movzx   eax, word ptr [rax]
0x18000f90b  mov     [rbp+3Fh+var_60.Size], eax
0x18000f90e  movzx   eax, word ptr [rcx]
0x18000f911  mov     [rbp+3Fh+var_48], eax
0x18000f914  lea     rax, _TraceLoggingMetadataEnd
0x18000f91b  mov     [rbp+3Fh+var_50], rcx
0x18000f91f  lea     rcx, _TraceLoggingMetadata
0x18000f926  sub     eax, ecx
0x18000f928  mov     dword ptr [rbp+3Fh+var_60.0Ch], 2
0x18000f92f  mov     [rbp+3Fh+var_44], 1
0x18000f936  mov     [rbp+3Fh+var_80], eax
0x18000f939  mov     eax, [rbp+3Fh+var_80]
0x18000f93c  mov     rcx, cs:RegHandle; RegHandle
0x18000f943  lea     rax, [rbp+3Fh+var_60]
0x18000f947  mov     [rsp+0B0h+UserData], rax; UserData
0x18000f94c  mov     [rsp+0B0h+UserDataCount], 5; UserDataCount
0x18000f954  call    cs:__imp_EventWriteTransfer
0x18000f95a  mov     rcx, [rbp+3Fh+var_10]
0x18000f95e  xor     rcx, rsp; StackCookie
0x18000f961  call    __security_check_cookie
0x18000f966  add     rsp, 0B0h
0x18000f96d  pop     rbp
0x18000f96e  retn
```
