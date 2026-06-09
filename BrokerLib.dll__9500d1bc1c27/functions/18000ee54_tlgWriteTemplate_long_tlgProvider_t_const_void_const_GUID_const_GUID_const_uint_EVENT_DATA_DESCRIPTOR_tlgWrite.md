# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &)

- ea: `0x18000ee54`
- end: `0x18000ef4d`
- name: `??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `249`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001ff8`
- `0x180012710`

## callees

- `0x180015af0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000ef32`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000ef32`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 *a5,
        __int64 *a6,
        __int64 a7,
        __int64 a8)
{
  __int64 v8; // rcx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-51h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-39h] BYREF
  unsigned __int8 *v12; // [rsp+60h] [rbp-29h]
  int v13; // [rsp+68h] [rbp-21h]
  int v14; // [rsp+6Ch] [rbp-1Dh]
  __int64 v15; // [rsp+70h] [rbp-19h]
  __int64 v16; // [rsp+78h] [rbp-11h]
  __int64 v17; // [rsp+80h] [rbp-9h]
  __int64 v18; // [rsp+88h] [rbp-1h]
  __int64 v19; // [rsp+90h] [rbp+7h]
  __int64 v20; // [rsp+98h] [rbp+Fh]
  __int64 v21; // [rsp+A0h] [rbp+17h]
  __int64 v22; // [rsp+A8h] [rbp+1Fh]

  v21 = a8;
  v19 = a7;
  v22 = 8;
  v20 = 1;
  v18 = 16;
  v17 = *a6;
  v16 = 16;
  v8 = *a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (ULONGLONG)off_180028008;
  v15 = v8;
  UserData.Size = *(unsigned __int16 *)off_180028008;
  v13 = *(unsigned __int16 *)(a2 + 11);
  v12 = a2 + 11;
  UserData.Reserved = 2;
  v14 = 1;
  return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 6u, &UserData);
}

```

## disassembly

```asm
0x18000ee54  push    rbp
0x18000ee56  lea     rbp, [rsp-37h]
0x18000ee5b  sub     rsp, 0C0h
0x18000ee62  mov     rax, cs:__security_cookie
0x18000ee69  xor     rax, rsp
0x18000ee6c  mov     [rbp+37h+var_10], rax
0x18000ee70  mov     rax, [rbp+37h+arg_38]
0x18000ee74  mov     r10d, 1
0x18000ee7a  mov     [rbp+37h+var_20], rax
0x18000ee7e  xor     r9d, r9d; RelatedActivityId
0x18000ee81  mov     rax, [rbp+37h+arg_30]
0x18000ee85  xor     r8d, r8d; ActivityId
0x18000ee88  mov     [rbp+37h+var_30], rax
0x18000ee8c  mov     rax, [rbp+37h+arg_28]
0x18000ee90  mov     [rbp+37h+var_18], 8
0x18000ee98  mov     [rbp+37h+var_28], r10
0x18000ee9c  mov     [rbp+37h+var_38], 10h
0x18000eea4  mov     rcx, [rax]
0x18000eea7  mov     rax, [rbp+37h+arg_20]
0x18000eeab  mov     [rbp+37h+var_40], rcx
0x18000eeaf  mov     [rbp+37h+var_48], 10h
0x18000eeb7  mov     rcx, [rax]
0x18000eeba  movzx   eax, byte ptr [rdx]
0x18000eebd  shl     eax, 18h
0x18000eec0  mov     dword ptr [rbp+37h+EventDescriptor.Id], eax
0x18000eec3  movzx   eax, word ptr [rdx+1]
0x18000eec7  mov     dword ptr [rbp+37h+EventDescriptor.Level], eax
0x18000eeca  mov     rax, [rdx+3]
0x18000eece  mov     [rbp+37h+EventDescriptor.Keyword], rax
0x18000eed2  mov     rax, cs:off_180028008
0x18000eed9  mov     [rbp+37h+var_70.Ptr], rax
0x18000eedd  mov     [rbp+37h+var_50], rcx
0x18000eee1  lea     rcx, [rdx+0Bh]
0x18000eee5  lea     rdx, [rbp+37h+EventDescriptor]; EventDescriptor
0x18000eee9  movzx   eax, word ptr [rax]
0x18000eeec  mov     [rbp+37h+var_70.Size], eax
0x18000eeef  movzx   eax, word ptr [rcx]
0x18000eef2  mov     [rbp+37h+var_58], eax
0x18000eef5  lea     rax, _TraceLoggingMetadataEnd
0x18000eefc  mov     [rbp+37h+var_60], rcx
0x18000ef00  lea     rcx, _TraceLoggingMetadata
0x18000ef07  sub     eax, ecx
0x18000ef09  mov     dword ptr [rbp+37h+var_70.0Ch], 2
0x18000ef10  mov     [rbp+37h+var_54], r10d
0x18000ef14  mov     [rbp+37h+var_90], eax
0x18000ef17  mov     eax, [rbp+37h+var_90]
0x18000ef1a  mov     rcx, cs:RegHandle; RegHandle
0x18000ef21  lea     rax, [rbp+37h+var_70]
0x18000ef25  mov     [rsp+0C0h+UserData], rax; UserData
0x18000ef2a  mov     [rsp+0C0h+UserDataCount], 6; UserDataCount
0x18000ef32  call    cs:__imp_EventWriteTransfer
0x18000ef38  mov     rcx, [rbp+37h+var_10]
0x18000ef3c  xor     rcx, rsp; StackCookie
0x18000ef3f  call    __security_check_cookie
0x18000ef44  add     rsp, 0C0h
0x18000ef4b  pop     rbp
0x18000ef4c  retn
```
