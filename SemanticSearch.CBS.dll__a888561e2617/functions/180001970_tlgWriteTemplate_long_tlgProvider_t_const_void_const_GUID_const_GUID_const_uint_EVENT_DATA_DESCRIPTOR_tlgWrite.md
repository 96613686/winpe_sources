# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)

- ea: `0x180001970`
- end: `0x180001a71`
- name: `??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z`
- size: `257`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, __int64, __int64, __int64 **)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180019470`
- `0x18001d410`
- `0x180035fa0`
- `0x180040a80`

## callees

- `0x180001970`
- `0x18004c070`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001a56`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001a56`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 **a5)
{
  __int64 *v6; // rcx
  __int64 v7; // rax
  int v9; // eax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-50h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+48h] [rbp-40h] BYREF
  unsigned __int8 *v13; // [rsp+58h] [rbp-30h]
  int v14; // [rsp+60h] [rbp-28h]
  int v15; // [rsp+64h] [rbp-24h]
  __int64 *v16; // [rsp+68h] [rbp-20h]
  int v17; // [rsp+70h] [rbp-18h]
  int v18; // [rsp+74h] [rbp-14h]

  v6 = *a5;
  if ( *a5 )
  {
    v7 = -1;
    while ( *((_WORD *)v6 + ++v7) != 0 )
      ;
    v9 = 2 * v7 + 2;
  }
  else
  {
    v6 = &qword_18006D0D8;
    v9 = 2;
  }
  v17 = v9;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = *(_QWORD *)(a1 + 8);
  v16 = v6;
  v18 = 0;
  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
  v14 = *(unsigned __int16 *)(a2 + 11);
  v13 = a2 + 11;
  UserData.Reserved = 2;
  v15 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, 0, 0, 3u, &UserData);
}

```

## disassembly

```asm
0x180001970  sub     rsp, 88h
0x180001977  mov     rax, cs:__security_cookie
0x18000197e  xor     rax, rsp
0x180001981  mov     [rsp+88h+var_10], rax
0x180001986  mov     rax, [rsp+88h+arg_20]
0x18000198e  mov     r10, rcx
0x180001991  mov     rcx, [rax]
0x180001994  test    rcx, rcx
0x180001997  jz      short loc_1800019B5
0x180001999  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800019a0  cmp     word ptr [rcx+rax*2+2], 0
0x1800019a6  lea     rax, [rax+1]
0x1800019aa  jnz     short loc_1800019A0
0x1800019ac  lea     eax, ds:2[rax*2]
0x1800019b3  jmp     short loc_1800019C1
0x1800019b5  lea     rcx, qword_18006D0D8
0x1800019bc  mov     eax, 2
0x1800019c1  mov     [rsp+88h+var_18], eax
0x1800019c5  xor     r9d, r9d; RelatedActivityId
0x1800019c8  movzx   eax, byte ptr [rdx]
0x1800019cb  xor     r8d, r8d; ActivityId
0x1800019ce  shl     eax, 18h
0x1800019d1  mov     dword ptr [rsp+88h+EventDescriptor.Id], eax
0x1800019d5  movzx   eax, word ptr [rdx+1]
0x1800019d9  mov     dword ptr [rsp+88h+EventDescriptor.Level], eax
0x1800019dd  mov     rax, [rdx+3]
0x1800019e1  mov     [rsp+88h+EventDescriptor.Keyword], rax
0x1800019e6  mov     rax, [r10+8]
0x1800019ea  mov     [rsp+88h+var_40.Ptr], rax
0x1800019ef  mov     [rsp+88h+var_20], rcx
0x1800019f4  lea     rcx, [rdx+0Bh]
0x1800019f8  mov     [rsp+88h+var_14], 0
0x180001a00  lea     rdx, [rsp+88h+EventDescriptor]; EventDescriptor
0x180001a05  movzx   eax, word ptr [rax]
0x180001a08  mov     [rsp+88h+var_40.Size], eax
0x180001a0c  movzx   eax, word ptr [rcx]
0x180001a0f  mov     [rsp+88h+var_28], eax
0x180001a13  lea     rax, _TraceLoggingMetadataEnd
0x180001a1a  mov     [rsp+88h+var_30], rcx
0x180001a1f  lea     rcx, _TraceLoggingMetadata
0x180001a26  sub     eax, ecx
0x180001a28  mov     dword ptr [rsp+88h+var_40.0Ch], 2
0x180001a30  mov     [rsp+88h+var_24], 1
0x180001a38  mov     [rsp+88h+var_58], eax
0x180001a3c  mov     eax, [rsp+88h+var_58]
0x180001a40  mov     rcx, [r10+20h]; RegHandle
0x180001a44  lea     rax, [rsp+88h+var_40]
0x180001a49  mov     [rsp+88h+UserData], rax; UserData
0x180001a4e  mov     [rsp+88h+UserDataCount], 3; UserDataCount
0x180001a56  call    cs:__imp_EventWriteTransfer
0x180001a5c  mov     rcx, [rsp+88h+var_10]
0x180001a61  xor     rcx, rsp; StackCookie
0x180001a64  call    __security_check_cookie
0x180001a69  add     rsp, 88h
0x180001a70  retn
```
