# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)

- ea: `0x180001b90`
- end: `0x180001c91`
- name: `??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z`
- size: `257`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, __int64, __int64, const wchar_t **)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x18001cc10`
- `0x18001d320`
- `0x18001d8e0`
- `0x180022260`
- `0x180026050`
- `0x18003aec0`

## callees

- `0x180001b90`
- `0x180034ef0`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x180001c76`
- `ADVAPI32!EventWriteTransfer` at `0x180001c76`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
    v6 = &Src;
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
0x180001b90  sub     rsp, 88h
0x180001b97  mov     rax, cs:__security_cookie
0x180001b9e  xor     rax, rsp
0x180001ba1  mov     [rsp+88h+var_10], rax
0x180001ba6  mov     rax, [rsp+88h+arg_20]
0x180001bae  mov     r10, rcx
0x180001bb1  mov     rcx, [rax]
0x180001bb4  test    rcx, rcx
0x180001bb7  jz      short loc_180001BD5
0x180001bb9  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180001bc0  cmp     word ptr [rcx+rax*2+2], 0
0x180001bc6  lea     rax, [rax+1]
0x180001bca  jnz     short loc_180001BC0
0x180001bcc  lea     eax, ds:2[rax*2]
0x180001bd3  jmp     short loc_180001BE1
0x180001bd5  lea     rcx, Src
0x180001bdc  mov     eax, 2
0x180001be1  mov     [rsp+88h+var_18], eax
0x180001be5  xor     r9d, r9d; RelatedActivityId
0x180001be8  movzx   eax, byte ptr [rdx]
0x180001beb  xor     r8d, r8d; ActivityId
0x180001bee  shl     eax, 18h
0x180001bf1  mov     dword ptr [rsp+88h+EventDescriptor.Id], eax
0x180001bf5  movzx   eax, word ptr [rdx+1]
0x180001bf9  mov     dword ptr [rsp+88h+EventDescriptor.Level], eax
0x180001bfd  mov     rax, [rdx+3]
0x180001c01  mov     [rsp+88h+EventDescriptor.Keyword], rax
0x180001c06  mov     rax, [r10+8]
0x180001c0a  mov     [rsp+88h+var_40.Ptr], rax
0x180001c0f  mov     [rsp+88h+var_20], rcx
0x180001c14  lea     rcx, [rdx+0Bh]
0x180001c18  mov     [rsp+88h+var_14], 0
0x180001c20  lea     rdx, [rsp+88h+EventDescriptor]; EventDescriptor
0x180001c25  movzx   eax, word ptr [rax]
0x180001c28  mov     [rsp+88h+var_40.Size], eax
0x180001c2c  movzx   eax, word ptr [rcx]
0x180001c2f  mov     [rsp+88h+var_28], eax
0x180001c33  lea     rax, _TraceLoggingMetadataEnd
0x180001c3a  mov     [rsp+88h+var_30], rcx
0x180001c3f  lea     rcx, _TraceLoggingMetadata
0x180001c46  sub     eax, ecx
0x180001c48  mov     dword ptr [rsp+88h+var_40.0Ch], 2
0x180001c50  mov     [rsp+88h+var_24], 1
0x180001c58  mov     [rsp+88h+var_58], eax
0x180001c5c  mov     eax, [rsp+88h+var_58]
0x180001c60  mov     rcx, [r10+20h]; RegHandle
0x180001c64  lea     rax, [rsp+88h+var_40]
0x180001c69  mov     [rsp+88h+UserData], rax; UserData
0x180001c6e  mov     [rsp+88h+UserDataCount], 3; UserDataCount
0x180001c76  call    cs:__imp_EventWriteTransfer
0x180001c7c  mov     rcx, [rsp+88h+var_10]
0x180001c81  xor     rcx, rsp; StackCookie
0x180001c84  call    __security_check_cookie
0x180001c89  add     rsp, 88h
0x180001c90  retn
```
