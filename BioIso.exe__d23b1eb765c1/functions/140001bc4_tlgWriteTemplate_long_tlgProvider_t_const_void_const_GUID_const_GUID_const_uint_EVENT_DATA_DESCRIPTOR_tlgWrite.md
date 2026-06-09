# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x140001bc4`
- end: `0x140001ca9`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z`
- size: `229`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, __int64, __int64, __int64, __int64)`
- caller_count: `99`
- callee_count: `1`
- tags: ``

## callers

- `0x14000791c`
- `0x140017780`
- `0x14002b630`
- `0x14002b870`
- `0x140040230`
- `0x140046bb0`
- `0x140046df0`
- `0x140047030`
- `0x140047270`
- `0x1400474b0`
- `0x1400476f0`
- `0x140047930`
- `0x140047b70`
- `0x140047db0`
- `0x140047ff0`
- `0x140048230`
- `0x140048470`
- `0x1400486b0`
- `0x1400488f0`
- `0x140048b30`
- `0x140048d70`
- `0x140048fb0`
- `0x1400491f0`
- `0x140049430`
- `0x140049670`
- `0x1400498b0`
- `0x140049af0`
- `0x140049d30`
- `0x140049f70`
- `0x14004a1b0`
- `0x14004a3f0`
- `0x14004a630`
- `0x14004a870`
- `0x14004aab0`
- `0x14004acf0`
- `0x14004af30`
- `0x14004b170`
- `0x14004b3b0`
- `0x14004b5f0`
- `0x14004b830`
- `0x14004ba70`
- `0x14004bcb0`
- `0x14004bef0`
- `0x14004c130`
- `0x14004c370`
- `0x14004c5b0`
- `0x14004c7f0`
- `0x14004ca30`
- `0x14004cc70`
- `0x14004ceb0`

## callees

- `0x14001bd40`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140001c87`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140001c87`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-21h] BYREF
  unsigned __int8 *v10; // [rsp+60h] [rbp-11h]
  int v11; // [rsp+68h] [rbp-9h]
  int v12; // [rsp+6Ch] [rbp-5h]
  __int64 v13; // [rsp+70h] [rbp-1h]
  __int64 v14; // [rsp+78h] [rbp+7h]
  __int64 v15; // [rsp+80h] [rbp+Fh]
  __int64 v16; // [rsp+88h] [rbp+17h]
  __int64 v17; // [rsp+90h] [rbp+1Fh]
  __int64 v18; // [rsp+98h] [rbp+27h]

  v17 = a7;
  v15 = a6;
  v13 = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = *(_QWORD *)(a1 + 8);
  v18 = 4;
  v16 = 4;
  v14 = 8;
  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
  v11 = *(unsigned __int16 *)(a2 + 11);
  v10 = a2 + 11;
  UserData.Reserved = 2;
  v12 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, a3, 0, 5u, &UserData);
}

```

## disassembly

```asm
0x140001bc4  push    rbp
0x140001bc6  lea     rbp, [rsp-3Fh]
0x140001bcb  sub     rsp, 0B0h
0x140001bd2  mov     rax, cs:__security_cookie
0x140001bd9  xor     rax, rsp
0x140001bdc  mov     [rbp+3Fh+var_10], rax
0x140001be0  mov     rax, [rbp+3Fh+arg_30]
0x140001be4  mov     r10, rcx
0x140001be7  mov     [rbp+3Fh+var_20], rax
0x140001beb  lea     rcx, [rdx+0Bh]
0x140001bef  mov     rax, [rbp+3Fh+arg_28]
0x140001bf3  xor     r9d, r9d; RelatedActivityId
0x140001bf6  mov     [rbp+3Fh+var_30], rax
0x140001bfa  mov     rax, [rbp+3Fh+arg_20]
0x140001bfe  mov     [rbp+3Fh+var_40], rax
0x140001c02  movzx   eax, byte ptr [rdx]
0x140001c05  shl     eax, 18h
0x140001c08  mov     dword ptr [rbp+3Fh+EventDescriptor.Id], eax
0x140001c0b  movzx   eax, word ptr [rdx+1]
0x140001c0f  mov     dword ptr [rbp+3Fh+EventDescriptor.Level], eax
0x140001c12  mov     rax, [rdx+3]
0x140001c16  lea     rdx, [rbp+3Fh+EventDescriptor]; EventDescriptor
0x140001c1a  mov     [rbp+3Fh+EventDescriptor.Keyword], rax
0x140001c1e  mov     rax, [r10+8]
0x140001c22  mov     [rbp+3Fh+var_60.Ptr], rax
0x140001c26  mov     [rbp+3Fh+var_18], 4
0x140001c2e  mov     [rbp+3Fh+var_28], 4
0x140001c36  mov     [rbp+3Fh+var_38], 8
0x140001c3e  movzx   eax, word ptr [rax]
0x140001c41  mov     [rbp+3Fh+var_60.Size], eax
0x140001c44  movzx   eax, word ptr [rcx]
0x140001c47  mov     [rbp+3Fh+var_48], eax
0x140001c4a  lea     rax, _TraceLoggingMetadataEnd
0x140001c51  mov     [rbp+3Fh+var_50], rcx
0x140001c55  lea     rcx, _TraceLoggingMetadata
0x140001c5c  sub     eax, ecx
0x140001c5e  mov     dword ptr [rbp+3Fh+var_60.0Ch], 2
0x140001c65  mov     [rbp+3Fh+var_44], 1
0x140001c6c  mov     [rbp+3Fh+var_80], eax
0x140001c6f  mov     eax, [rbp+3Fh+var_80]
0x140001c72  mov     rcx, [r10+20h]; RegHandle
0x140001c76  lea     rax, [rbp+3Fh+var_60]
0x140001c7a  mov     [rsp+0B0h+UserData], rax; UserData
0x140001c7f  mov     [rsp+0B0h+UserDataCount], 5; UserDataCount
0x140001c87  call    cs:__imp_EventWriteTransfer
0x140001c8e  nop     dword ptr [rax+rax+00h]
0x140001c93  mov     rcx, [rbp+3Fh+var_10]
0x140001c97  xor     rcx, rsp; StackCookie
0x140001c9a  call    __security_check_cookie
0x140001c9f  add     rsp, 0B0h
0x140001ca6  pop     rbp
0x140001ca7  retn
```
