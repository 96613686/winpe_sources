# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &)

- ea: `0x18000ea30`
- end: `0x18000eb19`
- name: `??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@@Z`
- size: `233`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002868`
- `0x18001da8e`

## callees

- `0x180015af0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000eafe`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000eafe`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 *a5,
        __int64 *a6,
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
  v19 = 1;
  v17 = 16;
  v15 = 16;
  v16 = *a6;
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
0x18000ea30  push    rbp
0x18000ea32  lea     rbp, [rsp-3Fh]
0x18000ea37  sub     rsp, 0B0h
0x18000ea3e  mov     rax, cs:__security_cookie
0x18000ea45  xor     rax, rsp
0x18000ea48  mov     [rbp+3Fh+var_10], rax
0x18000ea4c  mov     rax, [rbp+3Fh+arg_30]
0x18000ea50  mov     r10d, 1
0x18000ea56  mov     [rbp+3Fh+var_20], rax
0x18000ea5a  xor     r9d, r9d; RelatedActivityId
0x18000ea5d  mov     rax, [rbp+3Fh+arg_28]
0x18000ea61  xor     r8d, r8d; ActivityId
0x18000ea64  mov     [rbp+3Fh+var_18], r10
0x18000ea68  mov     [rbp+3Fh+var_28], 10h
0x18000ea70  mov     [rbp+3Fh+var_38], 10h
0x18000ea78  mov     rcx, [rax]
0x18000ea7b  mov     rax, [rbp+3Fh+arg_20]
0x18000ea7f  mov     [rbp+3Fh+var_30], rcx
0x18000ea83  mov     rcx, [rax]
0x18000ea86  movzx   eax, byte ptr [rdx]
0x18000ea89  shl     eax, 18h
0x18000ea8c  mov     dword ptr [rbp+3Fh+EventDescriptor.Id], eax
0x18000ea8f  movzx   eax, word ptr [rdx+1]
0x18000ea93  mov     dword ptr [rbp+3Fh+EventDescriptor.Level], eax
0x18000ea96  mov     rax, [rdx+3]
0x18000ea9a  mov     [rbp+3Fh+EventDescriptor.Keyword], rax
0x18000ea9e  mov     rax, cs:off_180028008
0x18000eaa5  mov     [rbp+3Fh+var_60.Ptr], rax
0x18000eaa9  mov     [rbp+3Fh+var_40], rcx
0x18000eaad  lea     rcx, [rdx+0Bh]
0x18000eab1  lea     rdx, [rbp+3Fh+EventDescriptor]; EventDescriptor
0x18000eab5  movzx   eax, word ptr [rax]
0x18000eab8  mov     [rbp+3Fh+var_60.Size], eax
0x18000eabb  movzx   eax, word ptr [rcx]
0x18000eabe  mov     [rbp+3Fh+var_48], eax
0x18000eac1  lea     rax, _TraceLoggingMetadataEnd
0x18000eac8  mov     [rbp+3Fh+var_50], rcx
0x18000eacc  lea     rcx, _TraceLoggingMetadata
0x18000ead3  sub     eax, ecx
0x18000ead5  mov     dword ptr [rbp+3Fh+var_60.0Ch], 2
0x18000eadc  mov     [rbp+3Fh+var_44], r10d
0x18000eae0  mov     [rbp+3Fh+var_80], eax
0x18000eae3  mov     eax, [rbp+3Fh+var_80]
0x18000eae6  mov     rcx, cs:RegHandle; RegHandle
0x18000eaed  lea     rax, [rbp+3Fh+var_60]
0x18000eaf1  mov     [rsp+0B0h+UserData], rax; UserData
0x18000eaf6  mov     [rsp+0B0h+UserDataCount], 5; UserDataCount
0x18000eafe  call    cs:__imp_EventWriteTransfer
0x18000eb04  mov     rcx, [rbp+3Fh+var_10]
0x18000eb08  xor     rcx, rsp; StackCookie
0x18000eb0b  call    __security_check_cookie
0x18000eb10  add     rsp, 0B0h
0x18000eb17  pop     rbp
0x18000eb18  retn
```
