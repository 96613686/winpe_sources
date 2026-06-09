# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x18000cf38`
- end: `0x18000d02c`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@43@Z`
- size: `244`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ee8c`

## callees

- `0x180012dd0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000d011`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000d011`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-51h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-39h] BYREF
  unsigned __int8 *v11; // [rsp+60h] [rbp-29h]
  int v12; // [rsp+68h] [rbp-21h]
  int v13; // [rsp+6Ch] [rbp-1Dh]
  __int64 v14; // [rsp+70h] [rbp-19h]
  __int64 v15; // [rsp+78h] [rbp-11h]
  __int64 v16; // [rsp+80h] [rbp-9h]
  __int64 v17; // [rsp+88h] [rbp-1h]
  __int64 v18; // [rsp+90h] [rbp+7h]
  __int64 v19; // [rsp+98h] [rbp+Fh]
  __int64 v20; // [rsp+A0h] [rbp+17h]
  __int64 v21; // [rsp+A8h] [rbp+1Fh]

  v20 = a8;
  v18 = a7;
  v16 = a6;
  v14 = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (ULONGLONG)off_180026060;
  v21 = 8;
  v19 = 4;
  v17 = 4;
  v15 = 8;
  UserData.Size = *(unsigned __int16 *)off_180026060;
  v12 = *(unsigned __int16 *)(a2 + 11);
  v11 = a2 + 11;
  UserData.Reserved = 2;
  v13 = 1;
  return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 6u, &UserData);
}

```

## disassembly

```asm
0x18000cf38  push    rbp
0x18000cf3a  lea     rbp, [rsp-37h]
0x18000cf3f  sub     rsp, 0C0h
0x18000cf46  mov     rax, cs:__security_cookie
0x18000cf4d  xor     rax, rsp
0x18000cf50  mov     [rbp+37h+var_10], rax
0x18000cf54  mov     rax, [rbp+37h+arg_38]
0x18000cf58  lea     rcx, [rdx+0Bh]
0x18000cf5c  mov     [rbp+37h+var_20], rax
0x18000cf60  xor     r9d, r9d; RelatedActivityId
0x18000cf63  mov     rax, [rbp+37h+arg_30]
0x18000cf67  xor     r8d, r8d; ActivityId
0x18000cf6a  mov     [rbp+37h+var_30], rax
0x18000cf6e  mov     rax, [rbp+37h+arg_28]
0x18000cf72  mov     [rbp+37h+var_40], rax
0x18000cf76  mov     rax, [rbp+37h+arg_20]
0x18000cf7a  mov     [rbp+37h+var_50], rax
0x18000cf7e  movzx   eax, byte ptr [rdx]
0x18000cf81  shl     eax, 18h
0x18000cf84  mov     dword ptr [rbp+37h+EventDescriptor.Id], eax
0x18000cf87  movzx   eax, word ptr [rdx+1]
0x18000cf8b  mov     dword ptr [rbp+37h+EventDescriptor.Level], eax
0x18000cf8e  mov     rax, [rdx+3]
0x18000cf92  lea     rdx, [rbp+37h+EventDescriptor]; EventDescriptor
0x18000cf96  mov     [rbp+37h+EventDescriptor.Keyword], rax
0x18000cf9a  mov     rax, cs:off_180026060
0x18000cfa1  mov     [rbp+37h+var_70.Ptr], rax
0x18000cfa5  mov     [rbp+37h+var_18], 8
0x18000cfad  mov     [rbp+37h+var_28], 4
0x18000cfb5  mov     [rbp+37h+var_38], 4
0x18000cfbd  mov     [rbp+37h+var_48], 8
0x18000cfc5  movzx   eax, word ptr [rax]
0x18000cfc8  mov     [rbp+37h+var_70.Size], eax
0x18000cfcb  movzx   eax, word ptr [rcx]
0x18000cfce  mov     [rbp+37h+var_58], eax
0x18000cfd1  lea     rax, _TraceLoggingMetadataEnd
0x18000cfd8  mov     [rbp+37h+var_60], rcx
0x18000cfdc  lea     rcx, _TraceLoggingMetadata
0x18000cfe3  sub     eax, ecx
0x18000cfe5  mov     dword ptr [rbp+37h+var_70.0Ch], 2
0x18000cfec  mov     [rbp+37h+var_54], 1
0x18000cff3  mov     [rbp+37h+var_90], eax
0x18000cff6  mov     eax, [rbp+37h+var_90]
0x18000cff9  mov     rcx, cs:RegHandle; RegHandle
0x18000d000  lea     rax, [rbp+37h+var_70]
0x18000d004  mov     [rsp+0C0h+UserData], rax; UserData
0x18000d009  mov     [rsp+0C0h+UserDataCount], 6; UserDataCount
0x18000d011  call    cs:__imp_EventWriteTransfer
0x18000d017  mov     rcx, [rbp+37h+var_10]
0x18000d01b  xor     rcx, rsp; StackCookie
0x18000d01e  call    __security_check_cookie
0x18000d023  add     rsp, 0C0h
0x18000d02a  pop     rbp
0x18000d02b  retn
```
