# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1800113b0`
- end: `0x18001149b`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@34@Z`
- size: `235`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180017a58`
- `0x18002ea84`

## callees

- `0x180026200`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180011480`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180011480`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        const GUID *a4,
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
  UserData.Ptr = *(_QWORD *)(a1 + 8);
  v21 = 4;
  v19 = 8;
  v17 = 4;
  v15 = 8;
  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
  v12 = *(unsigned __int16 *)(a2 + 11);
  v11 = a2 + 11;
  UserData.Reserved = 2;
  v13 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, a3, a4, 6u, &UserData);
}

```

## disassembly

```asm
0x1800113b0  push    rbp
0x1800113b2  lea     rbp, [rsp-37h]
0x1800113b7  sub     rsp, 0C0h
0x1800113be  mov     rax, cs:__security_cookie
0x1800113c5  xor     rax, rsp
0x1800113c8  mov     [rbp+37h+var_10], rax
0x1800113cc  mov     rax, [rbp+37h+arg_38]
0x1800113d0  mov     r10, rcx
0x1800113d3  mov     [rbp+37h+var_20], rax
0x1800113d7  lea     rcx, [rdx+0Bh]
0x1800113db  mov     rax, [rbp+37h+arg_30]
0x1800113df  mov     [rbp+37h+var_30], rax
0x1800113e3  mov     rax, [rbp+37h+arg_28]
0x1800113e7  mov     [rbp+37h+var_40], rax
0x1800113eb  mov     rax, [rbp+37h+arg_20]
0x1800113ef  mov     [rbp+37h+var_50], rax
0x1800113f3  movzx   eax, byte ptr [rdx]
0x1800113f6  shl     eax, 18h
0x1800113f9  mov     dword ptr [rbp+37h+EventDescriptor.Id], eax
0x1800113fc  movzx   eax, word ptr [rdx+1]
0x180011400  mov     dword ptr [rbp+37h+EventDescriptor.Level], eax
0x180011403  mov     rax, [rdx+3]
0x180011407  lea     rdx, [rbp+37h+EventDescriptor]; EventDescriptor
0x18001140b  mov     [rbp+37h+EventDescriptor.Keyword], rax
0x18001140f  mov     rax, [r10+8]
0x180011413  mov     [rbp+37h+var_70.Ptr], rax
0x180011417  mov     [rbp+37h+var_18], 4
0x18001141f  mov     [rbp+37h+var_28], 8
0x180011427  mov     [rbp+37h+var_38], 4
0x18001142f  mov     [rbp+37h+var_48], 8
0x180011437  movzx   eax, word ptr [rax]
0x18001143a  mov     [rbp+37h+var_70.Size], eax
0x18001143d  movzx   eax, word ptr [rcx]
0x180011440  mov     [rbp+37h+var_58], eax
0x180011443  lea     rax, _TraceLoggingMetadataEnd
0x18001144a  mov     [rbp+37h+var_60], rcx
0x18001144e  lea     rcx, _TraceLoggingMetadata
0x180011455  sub     eax, ecx
0x180011457  mov     dword ptr [rbp+37h+var_70.0Ch], 2
0x18001145e  mov     [rbp+37h+var_54], 1
0x180011465  mov     [rbp+37h+var_90], eax
0x180011468  mov     eax, [rbp+37h+var_90]
0x18001146b  mov     rcx, [r10+20h]; RegHandle
0x18001146f  lea     rax, [rbp+37h+var_70]
0x180011473  mov     [rsp+0C0h+UserData], rax; UserData
0x180011478  mov     [rsp+0C0h+UserDataCount], 6; UserDataCount
0x180011480  call    cs:__imp_EventWriteTransfer
0x180011486  mov     rcx, [rbp+37h+var_10]
0x18001148a  xor     rcx, rsp; StackCookie
0x18001148d  call    __security_check_cookie
0x180011492  add     rsp, 0C0h
0x180011499  pop     rbp
0x18001149a  retn
```
