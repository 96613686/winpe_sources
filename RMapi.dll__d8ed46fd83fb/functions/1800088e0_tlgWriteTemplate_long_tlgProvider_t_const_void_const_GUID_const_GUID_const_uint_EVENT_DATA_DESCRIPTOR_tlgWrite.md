# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)

- ea: `0x1800088e0`
- end: `0x1800089ca`
- name: `??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z`
- size: `234`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x180009500`
- `0x180009614`
- `0x18000970c`
- `0x180015b80`
- `0x180015da0`
- `0x18001cd4c`
- `0x18001f870`
- `0x18001fd00`
- `0x18002036c`
- `0x1800219ec`

## callees

- `0x1800088e0`
- `0x18000d2a0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800089af`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800089af`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const wchar_t **a5)
{
  const wchar_t *v5; // rcx
  __int64 v6; // rax
  int v7; // eax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+48h] [rbp-38h] BYREF
  unsigned __int8 *v11; // [rsp+58h] [rbp-28h]
  int v12; // [rsp+60h] [rbp-20h]
  int v13; // [rsp+64h] [rbp-1Ch]
  const wchar_t *v14; // [rsp+68h] [rbp-18h]
  int v15; // [rsp+70h] [rbp-10h]
  int v16; // [rsp+74h] [rbp-Ch]

  v5 = *a5;
  if ( *a5 )
  {
    v6 = -1;
    do
      ++v6;
    while ( *((_BYTE *)v5 + v6) );
    v7 = v6 + 1;
  }
  else
  {
    v5 = &byte_18002AE5D;
    v7 = 1;
  }
  v15 = v7;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (ULONGLONG)off_180037058;
  v14 = v5;
  v16 = 0;
  UserData.Size = (unsigned __int16)*off_180037058;
  v12 = *(unsigned __int16 *)(a2 + 11);
  v11 = a2 + 11;
  v13 = 1;
  UserData.Reserved = 2;
  return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
}

```

## disassembly

```asm
0x1800088e0  push    rbp
0x1800088e2  mov     rbp, rsp
0x1800088e5  sub     rsp, 80h
0x1800088ec  mov     rax, cs:__security_cookie
0x1800088f3  xor     rax, rsp
0x1800088f6  mov     [rbp+var_8], rax
0x1800088fa  mov     rax, [rbp+arg_20]
0x1800088fe  mov     r8d, 1
0x180008904  mov     rcx, [rax]
0x180008907  test    rcx, rcx
0x18000890a  jz      short loc_18000891D
0x18000890c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008910  inc     rax
0x180008913  cmp     byte ptr [rcx+rax], 0
0x180008917  jnz     short loc_180008910
0x180008919  inc     eax
0x18000891b  jmp     short loc_180008927
0x18000891d  lea     rcx, byte_18002AE5D
0x180008924  mov     eax, r8d
0x180008927  mov     [rbp+var_10], eax
0x18000892a  xor     r9d, r9d; RelatedActivityId
0x18000892d  movzx   eax, byte ptr [rdx]
0x180008930  shl     eax, 18h
0x180008933  mov     dword ptr [rbp+EventDescriptor.Id], eax
0x180008936  movzx   eax, word ptr [rdx+1]
0x18000893a  mov     dword ptr [rbp+EventDescriptor.Level], eax
0x18000893d  mov     rax, [rdx+3]
0x180008941  mov     [rbp+EventDescriptor.Keyword], rax
0x180008945  mov     rax, cs:off_180037058
0x18000894c  mov     [rbp+var_38.Ptr], rax
0x180008950  mov     [rbp+var_18], rcx
0x180008954  lea     rcx, [rdx+0Bh]
0x180008958  mov     [rbp+var_C], 0
0x18000895f  lea     rdx, [rbp+EventDescriptor]; EventDescriptor
0x180008963  movzx   eax, word ptr [rax]
0x180008966  mov     [rbp+var_38.Size], eax
0x180008969  movzx   eax, word ptr [rcx]
0x18000896c  mov     [rbp+var_20], eax
0x18000896f  lea     rax, _TraceLoggingMetadataEnd
0x180008976  mov     [rbp+var_28], rcx
0x18000897a  lea     rcx, _TraceLoggingMetadata
0x180008981  sub     eax, ecx
0x180008983  mov     [rbp+var_1C], r8d
0x180008987  mov     dword ptr [rbp+var_38.0Ch], 2
0x18000898e  xor     r8d, r8d; ActivityId
0x180008991  mov     [rbp+var_50], eax
0x180008994  mov     eax, [rbp+var_50]
0x180008997  mov     rcx, cs:RegHandle; RegHandle
0x18000899e  lea     rax, [rbp+var_38]
0x1800089a2  mov     [rsp+80h+UserData], rax; UserData
0x1800089a7  mov     [rsp+80h+UserDataCount], 3; UserDataCount
0x1800089af  call    cs:__imp_EventWriteTransfer
0x1800089b5  mov     rcx, [rbp+var_8]
0x1800089b9  xor     rcx, rsp; StackCookie
0x1800089bc  call    __security_check_cookie
0x1800089c1  add     rsp, 80h
0x1800089c8  pop     rbp
0x1800089c9  retn
```
