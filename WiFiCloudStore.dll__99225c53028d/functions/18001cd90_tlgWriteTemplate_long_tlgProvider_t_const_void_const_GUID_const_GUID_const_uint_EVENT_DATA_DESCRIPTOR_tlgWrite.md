# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &)

- ea: `0x18001cd90`
- end: `0x18001ce8d`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@4@Z`
- size: `253`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800112e4`
- `0x180013c74`

## callees

- `0x18002a030`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001ce72`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001ce72`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-69h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-51h] BYREF
  unsigned __int8 *v12; // [rsp+60h] [rbp-41h]
  int v13; // [rsp+68h] [rbp-39h]
  int v14; // [rsp+6Ch] [rbp-35h]
  __int64 v15; // [rsp+70h] [rbp-31h]
  __int64 v16; // [rsp+78h] [rbp-29h]
  __int64 v17; // [rsp+80h] [rbp-21h]
  __int64 v18; // [rsp+88h] [rbp-19h]
  __int64 v19; // [rsp+90h] [rbp-11h]
  __int64 v20; // [rsp+98h] [rbp-9h]
  __int64 v21; // [rsp+A0h] [rbp-1h]
  __int64 v22; // [rsp+A8h] [rbp+7h]
  __int64 v23; // [rsp+B0h] [rbp+Fh]
  __int64 v24; // [rsp+B8h] [rbp+17h]

  v23 = a9;
  v21 = a8;
  v19 = a7;
  v17 = a6;
  v15 = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = *(_QWORD *)(a1 + 8);
  v24 = 4;
  v22 = 1;
  v20 = 4;
  v18 = 4;
  v16 = 8;
  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
  v13 = *(unsigned __int16 *)(a2 + 11);
  v12 = a2 + 11;
  UserData.Reserved = 2;
  v14 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, a3, 0, 7u, &UserData);
}

```

## disassembly

```asm
0x18001cd90  push    rbp
0x18001cd92  lea     rbp, [rsp-2Fh]
0x18001cd97  sub     rsp, 0D0h
0x18001cd9e  mov     rax, cs:__security_cookie
0x18001cda5  xor     rax, rsp
0x18001cda8  mov     [rbp+2Fh+var_10], rax
0x18001cdac  mov     rax, [rbp+2Fh+arg_40]
0x18001cdb0  mov     r10, rcx
0x18001cdb3  mov     [rbp+2Fh+var_20], rax
0x18001cdb7  lea     rcx, [rdx+0Bh]
0x18001cdbb  mov     rax, [rbp+2Fh+arg_38]
0x18001cdbf  mov     r11d, 1
0x18001cdc5  mov     [rbp+2Fh+var_30], rax
0x18001cdc9  xor     r9d, r9d; RelatedActivityId
0x18001cdcc  mov     rax, [rbp+2Fh+arg_30]
0x18001cdd0  mov     [rbp+2Fh+var_40], rax
0x18001cdd4  mov     rax, [rbp+2Fh+arg_28]
0x18001cdd8  mov     [rbp+2Fh+var_50], rax
0x18001cddc  mov     rax, [rbp+2Fh+arg_20]
0x18001cde0  mov     [rbp+2Fh+var_60], rax
0x18001cde4  movzx   eax, byte ptr [rdx]
0x18001cde7  shl     eax, 18h
0x18001cdea  mov     dword ptr [rbp+2Fh+EventDescriptor.Id], eax
0x18001cded  movzx   eax, word ptr [rdx+1]
0x18001cdf1  mov     dword ptr [rbp+2Fh+EventDescriptor.Level], eax
0x18001cdf4  mov     rax, [rdx+3]
0x18001cdf8  lea     rdx, [rbp+2Fh+EventDescriptor]; EventDescriptor
0x18001cdfc  mov     [rbp+2Fh+EventDescriptor.Keyword], rax
0x18001ce00  mov     rax, [r10+8]
0x18001ce04  mov     [rbp+2Fh+var_80.Ptr], rax
0x18001ce08  mov     [rbp+2Fh+var_18], 4
0x18001ce10  mov     [rbp+2Fh+var_28], r11
0x18001ce14  mov     [rbp+2Fh+var_38], 4
0x18001ce1c  mov     [rbp+2Fh+var_48], 4
0x18001ce24  mov     [rbp+2Fh+var_58], 8
0x18001ce2c  movzx   eax, word ptr [rax]
0x18001ce2f  mov     [rbp+2Fh+var_80.Size], eax
0x18001ce32  movzx   eax, word ptr [rcx]
0x18001ce35  mov     [rbp+2Fh+var_68], eax
0x18001ce38  lea     rax, _TraceLoggingMetadataEnd
0x18001ce3f  mov     [rbp+2Fh+var_70], rcx
0x18001ce43  lea     rcx, _TraceLoggingMetadata
0x18001ce4a  sub     eax, ecx
0x18001ce4c  mov     dword ptr [rbp+2Fh+var_80.0Ch], 2
0x18001ce53  mov     [rbp+2Fh+var_64], r11d
0x18001ce57  mov     [rbp+2Fh+var_A0], eax
0x18001ce5a  mov     eax, [rbp+2Fh+var_A0]
0x18001ce5d  mov     rcx, [r10+20h]; RegHandle
0x18001ce61  lea     rax, [rbp+2Fh+var_80]
0x18001ce65  mov     [rsp+0D0h+UserData], rax; UserData
0x18001ce6a  mov     [rsp+0D0h+UserDataCount], 7; UserDataCount
0x18001ce72  call    cs:__imp_EventWriteTransfer
0x18001ce78  mov     rcx, [rbp+2Fh+var_10]
0x18001ce7c  xor     rcx, rsp; StackCookie
0x18001ce7f  call    __security_check_cookie
0x18001ce84  add     rsp, 0D0h
0x18001ce8b  pop     rbp
0x18001ce8c  retn
```
