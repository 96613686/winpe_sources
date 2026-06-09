# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)

- ea: `0x180001790`
- end: `0x180001891`
- name: `??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z`
- size: `257`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180012470`
- `0x1800677b0`

## callees

- `0x180001790`
- `0x1801f7110`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001876`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001876`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const wchar_t **a5)
{
  const wchar_t *v6; // rcx
  __int64 v7; // rax
  int v9; // eax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-50h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+48h] [rbp-40h] BYREF
  unsigned __int8 *v13; // [rsp+58h] [rbp-30h]
  int v14; // [rsp+60h] [rbp-28h]
  int v15; // [rsp+64h] [rbp-24h]
  const wchar_t *v16; // [rsp+68h] [rbp-20h]
  int v17; // [rsp+70h] [rbp-18h]
  int v18; // [rsp+74h] [rbp-14h]

  v6 = *a5;
  if ( *a5 )
  {
    v7 = -1;
    while ( v6[++v7] != 0 )
      ;
    v9 = 2 * v7 + 2;
  }
  else
  {
    v6 = &String;
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
0x180001790  sub     rsp, 88h
0x180001797  mov     rax, cs:__security_cookie
0x18000179e  xor     rax, rsp
0x1800017a1  mov     [rsp+88h+var_10], rax
0x1800017a6  mov     rax, [rsp+88h+arg_20]
0x1800017ae  mov     r10, rcx
0x1800017b1  mov     rcx, [rax]
0x1800017b4  test    rcx, rcx
0x1800017b7  jz      short loc_1800017D5
0x1800017b9  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800017c0  cmp     word ptr [rcx+rax*2+2], 0
0x1800017c6  lea     rax, [rax+1]
0x1800017ca  jnz     short loc_1800017C0
0x1800017cc  lea     eax, ds:2[rax*2]
0x1800017d3  jmp     short loc_1800017E1
0x1800017d5  lea     rcx, String
0x1800017dc  mov     eax, 2
0x1800017e1  mov     [rsp+88h+var_18], eax
0x1800017e5  xor     r9d, r9d; RelatedActivityId
0x1800017e8  movzx   eax, byte ptr [rdx]
0x1800017eb  xor     r8d, r8d; ActivityId
0x1800017ee  shl     eax, 18h
0x1800017f1  mov     dword ptr [rsp+88h+EventDescriptor.Id], eax
0x1800017f5  movzx   eax, word ptr [rdx+1]
0x1800017f9  mov     dword ptr [rsp+88h+EventDescriptor.Level], eax
0x1800017fd  mov     rax, [rdx+3]
0x180001801  mov     [rsp+88h+EventDescriptor.Keyword], rax
0x180001806  mov     rax, [r10+8]
0x18000180a  mov     [rsp+88h+var_40.Ptr], rax
0x18000180f  mov     [rsp+88h+var_20], rcx
0x180001814  lea     rcx, [rdx+0Bh]
0x180001818  mov     [rsp+88h+var_14], 0
0x180001820  lea     rdx, [rsp+88h+EventDescriptor]; EventDescriptor
0x180001825  movzx   eax, word ptr [rax]
0x180001828  mov     [rsp+88h+var_40.Size], eax
0x18000182c  movzx   eax, word ptr [rcx]
0x18000182f  mov     [rsp+88h+var_28], eax
0x180001833  lea     rax, _TraceLoggingMetadataEnd
0x18000183a  mov     [rsp+88h+var_30], rcx
0x18000183f  lea     rcx, _TraceLoggingMetadata
0x180001846  sub     eax, ecx
0x180001848  mov     dword ptr [rsp+88h+var_40.0Ch], 2
0x180001850  mov     [rsp+88h+var_24], 1
0x180001858  mov     [rsp+88h+var_58], eax
0x18000185c  mov     eax, [rsp+88h+var_58]
0x180001860  mov     rcx, [r10+20h]; RegHandle
0x180001864  lea     rax, [rsp+88h+var_40]
0x180001869  mov     [rsp+88h+UserData], rax; UserData
0x18000186e  mov     [rsp+88h+UserDataCount], 3; UserDataCount
0x180001876  call    cs:__imp_EventWriteTransfer
0x18000187c  mov     rcx, [rsp+88h+var_10]
0x180001881  xor     rcx, rsp; StackCookie
0x180001884  call    __security_check_cookie
0x180001889  add     rsp, 88h
0x180001890  retn
```
