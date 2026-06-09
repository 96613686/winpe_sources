# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x18000ffd0`
- end: `0x1800100a3`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `211`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180011f30`

## callees

- `0x18001aec0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180010088`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180010088`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-9h] BYREF
  unsigned __int8 *v9; // [rsp+60h] [rbp+7h]
  int v10; // [rsp+68h] [rbp+Fh]
  int v11; // [rsp+6Ch] [rbp+13h]
  __int64 v12; // [rsp+70h] [rbp+17h]
  __int64 v13; // [rsp+78h] [rbp+1Fh]
  __int64 v14; // [rsp+80h] [rbp+27h]
  __int64 v15; // [rsp+88h] [rbp+2Fh]

  v14 = a6;
  v12 = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (ULONGLONG)off_18002E040;
  v13 = 4;
  v15 = 8;
  UserData.Size = (unsigned __int16)*off_18002E040;
  v10 = *(unsigned __int16 *)(a2 + 11);
  v9 = a2 + 11;
  UserData.Reserved = 2;
  v11 = 1;
  return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
}

```

## disassembly

```asm
0x18000ffd0  push    rbp
0x18000ffd2  lea     rbp, [rsp-47h]
0x18000ffd7  sub     rsp, 0A0h
0x18000ffde  mov     rax, cs:__security_cookie
0x18000ffe5  xor     rax, rsp
0x18000ffe8  mov     [rbp+47h+var_10], rax
0x18000ffec  mov     rax, [rbp+47h+arg_28]
0x18000fff0  lea     rcx, [rdx+0Bh]
0x18000fff4  mov     [rbp+47h+var_20], rax
0x18000fff8  mov     r8d, 4
0x18000fffe  mov     rax, [rbp+47h+arg_20]
0x180010002  xor     r9d, r9d; RelatedActivityId
0x180010005  mov     [rbp+47h+var_30], rax
0x180010009  movzx   eax, byte ptr [rdx]
0x18001000c  shl     eax, 18h
0x18001000f  mov     dword ptr [rbp+47h+EventDescriptor.Id], eax
0x180010012  movzx   eax, word ptr [rdx+1]
0x180010016  mov     dword ptr [rbp+47h+EventDescriptor.Level], eax
0x180010019  mov     rax, [rdx+3]
0x18001001d  lea     rdx, [rbp+47h+EventDescriptor]; EventDescriptor
0x180010021  mov     [rbp+47h+EventDescriptor.Keyword], rax
0x180010025  mov     rax, cs:off_18002E040
0x18001002c  mov     [rbp+47h+var_50.Ptr], rax
0x180010030  mov     [rbp+47h+var_28], r8
0x180010034  mov     [rbp+47h+var_18], 8
0x18001003c  movzx   eax, word ptr [rax]
0x18001003f  mov     [rbp+47h+var_50.Size], eax
0x180010042  movzx   eax, word ptr [rcx]
0x180010045  mov     [rbp+47h+var_38], eax
0x180010048  lea     rax, _TraceLoggingMetadataEnd
0x18001004f  mov     [rbp+47h+var_40], rcx
0x180010053  lea     rcx, _TraceLoggingMetadata
0x18001005a  sub     eax, ecx
0x18001005c  mov     dword ptr [rbp+47h+var_50.0Ch], 2
0x180010063  mov     [rbp+47h+var_34], 1
0x18001006a  mov     [rbp+47h+var_70], eax
0x18001006d  mov     eax, [rbp+47h+var_70]
0x180010070  mov     rcx, cs:RegHandle; RegHandle
0x180010077  lea     rax, [rbp+47h+var_50]
0x18001007b  mov     [rsp+0A0h+UserData], rax; UserData
0x180010080  mov     [rsp+0A0h+UserDataCount], r8d; UserDataCount
0x180010085  xor     r8d, r8d; ActivityId
0x180010088  call    cs:__imp_EventWriteTransfer
0x18001008e  mov     rcx, [rbp+47h+var_10]
0x180010092  xor     rcx, rsp; StackCookie
0x180010095  call    __security_check_cookie
0x18001009a  add     rsp, 0A0h
0x1800100a1  pop     rbp
0x1800100a2  retn
```
