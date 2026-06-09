# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)

- ea: `0x1800017d0`
- end: `0x1800018d1`
- name: `??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z`
- size: `257`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, __int64, __int64, const wchar_t **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001f91a`
- `0x18001fa07`

## callees

- `0x1800017d0`
- `0x1800181b0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800018b6`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800018b6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
    v6 = &S2;
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
0x1800017d0  sub     rsp, 88h
0x1800017d7  mov     rax, cs:__security_cookie
0x1800017de  xor     rax, rsp
0x1800017e1  mov     [rsp+88h+var_10], rax
0x1800017e6  mov     rax, [rsp+88h+arg_20]
0x1800017ee  mov     r10, rcx
0x1800017f1  mov     rcx, [rax]
0x1800017f4  test    rcx, rcx
0x1800017f7  jz      short loc_180001815
0x1800017f9  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180001800  cmp     word ptr [rcx+rax*2+2], 0
0x180001806  lea     rax, [rax+1]
0x18000180a  jnz     short loc_180001800
0x18000180c  lea     eax, ds:2[rax*2]
0x180001813  jmp     short loc_180001821
0x180001815  lea     rcx, S2
0x18000181c  mov     eax, 2
0x180001821  mov     [rsp+88h+var_18], eax
0x180001825  xor     r9d, r9d; RelatedActivityId
0x180001828  movzx   eax, byte ptr [rdx]
0x18000182b  xor     r8d, r8d; ActivityId
0x18000182e  shl     eax, 18h
0x180001831  mov     dword ptr [rsp+88h+EventDescriptor.Id], eax
0x180001835  movzx   eax, word ptr [rdx+1]
0x180001839  mov     dword ptr [rsp+88h+EventDescriptor.Level], eax
0x18000183d  mov     rax, [rdx+3]
0x180001841  mov     [rsp+88h+EventDescriptor.Keyword], rax
0x180001846  mov     rax, [r10+8]
0x18000184a  mov     [rsp+88h+var_40.Ptr], rax
0x18000184f  mov     [rsp+88h+var_20], rcx
0x180001854  lea     rcx, [rdx+0Bh]
0x180001858  mov     [rsp+88h+var_14], 0
0x180001860  lea     rdx, [rsp+88h+EventDescriptor]; EventDescriptor
0x180001865  movzx   eax, word ptr [rax]
0x180001868  mov     [rsp+88h+var_40.Size], eax
0x18000186c  movzx   eax, word ptr [rcx]
0x18000186f  mov     [rsp+88h+var_28], eax
0x180001873  lea     rax, _TraceLoggingMetadataEnd
0x18000187a  mov     [rsp+88h+var_30], rcx
0x18000187f  lea     rcx, _TraceLoggingMetadata
0x180001886  sub     eax, ecx
0x180001888  mov     dword ptr [rsp+88h+var_40.0Ch], 2
0x180001890  mov     [rsp+88h+var_24], 1
0x180001898  mov     [rsp+88h+var_58], eax
0x18000189c  mov     eax, [rsp+88h+var_58]
0x1800018a0  mov     rcx, [r10+20h]; RegHandle
0x1800018a4  lea     rax, [rsp+88h+var_40]
0x1800018a9  mov     [rsp+88h+UserData], rax; UserData
0x1800018ae  mov     [rsp+88h+UserDataCount], 3; UserDataCount
0x1800018b6  call    cs:__imp_EventWriteTransfer
0x1800018bc  mov     rcx, [rsp+88h+var_10]
0x1800018c1  xor     rcx, rsp; StackCookie
0x1800018c4  call    __security_check_cookie
0x1800018c9  add     rsp, 88h
0x1800018d0  retn
```
