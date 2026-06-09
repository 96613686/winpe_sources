# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &)

- ea: `0x18000fc28`
- end: `0x18000fcff`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z`
- size: `215`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b3cc`

## callees

- `0x180015af0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000fce4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000fce4`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 *a6)
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

  v16 = 16;
  v14 = 8;
  v6 = *a6;
  v13 = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (ULONGLONG)off_180028008;
  v15 = v6;
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
0x18000fc28  push    rbp
0x18000fc2a  lea     rbp, [rsp-47h]
0x18000fc2f  sub     rsp, 0A0h
0x18000fc36  mov     rax, cs:__security_cookie
0x18000fc3d  xor     rax, rsp
0x18000fc40  mov     [rbp+47h+var_10], rax
0x18000fc44  mov     rax, [rbp+47h+arg_28]
0x18000fc48  xor     r9d, r9d; RelatedActivityId
0x18000fc4b  mov     [rbp+47h+var_18], 10h
0x18000fc53  xor     r8d, r8d; ActivityId
0x18000fc56  mov     [rbp+47h+var_28], 8
0x18000fc5e  mov     rcx, [rax]
0x18000fc61  mov     rax, [rbp+47h+arg_20]
0x18000fc65  mov     [rbp+47h+var_30], rax
0x18000fc69  movzx   eax, byte ptr [rdx]
0x18000fc6c  shl     eax, 18h
0x18000fc6f  mov     dword ptr [rbp+47h+EventDescriptor.Id], eax
0x18000fc72  movzx   eax, word ptr [rdx+1]
0x18000fc76  mov     dword ptr [rbp+47h+EventDescriptor.Level], eax
0x18000fc79  mov     rax, [rdx+3]
0x18000fc7d  mov     [rbp+47h+EventDescriptor.Keyword], rax
0x18000fc81  mov     rax, cs:off_180028008
0x18000fc88  mov     [rbp+47h+var_50.Ptr], rax
0x18000fc8c  mov     [rbp+47h+var_20], rcx
0x18000fc90  lea     rcx, [rdx+0Bh]
0x18000fc94  lea     rdx, [rbp+47h+EventDescriptor]; EventDescriptor
0x18000fc98  movzx   eax, word ptr [rax]
0x18000fc9b  mov     [rbp+47h+var_50.Size], eax
0x18000fc9e  movzx   eax, word ptr [rcx]
0x18000fca1  mov     [rbp+47h+var_38], eax
0x18000fca4  lea     rax, _TraceLoggingMetadataEnd
0x18000fcab  mov     [rbp+47h+var_40], rcx
0x18000fcaf  lea     rcx, _TraceLoggingMetadata
0x18000fcb6  sub     eax, ecx
0x18000fcb8  mov     dword ptr [rbp+47h+var_50.0Ch], 2
0x18000fcbf  mov     [rbp+47h+var_34], 1
0x18000fcc6  mov     [rbp+47h+var_70], eax
0x18000fcc9  mov     eax, [rbp+47h+var_70]
0x18000fccc  mov     rcx, cs:RegHandle; RegHandle
0x18000fcd3  lea     rax, [rbp+47h+var_50]
0x18000fcd7  mov     [rsp+0A0h+UserData], rax; UserData
0x18000fcdc  mov     [rsp+0A0h+UserDataCount], 4; UserDataCount
0x18000fce4  call    cs:__imp_EventWriteTransfer
0x18000fcea  mov     rcx, [rbp+47h+var_10]
0x18000fcee  xor     rcx, rsp; StackCookie
0x18000fcf1  call    __security_check_cookie
0x18000fcf6  add     rsp, 0A0h
0x18000fcfd  pop     rbp
0x18000fcfe  retn
```
