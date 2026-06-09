# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1800042b0`
- end: `0x1800043cf`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `287`
- prototype: ``
- caller_count: `27`
- callee_count: `2`
- tags: ``

## callers

- `0x180009500`
- `0x180011408`
- `0x180015b80`
- `0x180015da0`
- `0x18001c654`
- `0x18001c72c`
- `0x18001c7e0`
- `0x18001ca54`
- `0x18001dac0`
- `0x18001df88`
- `0x18001eea8`
- `0x18001f530`
- `0x18001ff50`
- `0x1800228dc`
- `0x180023f50`
- `0x180025fbf`
- `0x18002634e`
- `0x18002647a`
- `0x180026504`
- `0x1800265b2`
- `0x180026618`
- `0x18002668e`
- `0x1800267eb`
- `0x1800269ce`
- `0x180026a41`
- `0x180026b72`
- `0x180026ecb`

## callees

- `0x1800042b0`
- `0x18000d2a0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800043a0`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800043a0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const wchar_t **a5,
        __int64 a6)
{
  const wchar_t *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-70h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-58h] BYREF
  unsigned __int8 *v12; // [rsp+60h] [rbp-48h]
  int v13; // [rsp+68h] [rbp-40h]
  int v14; // [rsp+6Ch] [rbp-3Ch]
  const wchar_t *v15; // [rsp+70h] [rbp-38h]
  int v16; // [rsp+78h] [rbp-30h]
  int v17; // [rsp+7Ch] [rbp-2Ch]
  __int64 v18; // [rsp+80h] [rbp-28h]
  __int64 v19; // [rsp+88h] [rbp-20h]

  v18 = a6;
  v19 = 4;
  v6 = *a5;
  if ( *a5 )
  {
    v7 = -1;
    do
      ++v7;
    while ( *((_BYTE *)v6 + v7) );
    v8 = v7 + 1;
  }
  else
  {
    v6 = &byte_18002AE5D;
    v8 = 1;
  }
  v16 = v8;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (ULONGLONG)off_180037058;
  v15 = v6;
  v17 = 0;
  UserData.Size = (unsigned __int16)*off_180037058;
  v13 = *(unsigned __int16 *)(a2 + 11);
  v12 = a2 + 11;
  UserData.Reserved = 2;
  v14 = 1;
  return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
}

```

## disassembly

```asm
0x1800042b0  mov     r11, rsp
0x1800042b3  sub     rsp, 0A8h
0x1800042ba  mov     rax, cs:__security_cookie
0x1800042c1  xor     rax, rsp
0x1800042c4  mov     [rsp+0A8h+var_18], rax
0x1800042cc  mov     rax, [rsp+0A8h+arg_28]
0x1800042d4  xor     r8d, r8d; ActivityId
0x1800042d7  mov     [r11-28h], rax
0x1800042db  mov     rax, [rsp+0A8h+arg_20]
0x1800042e3  mov     qword ptr [r11-20h], 4
0x1800042eb  mov     rcx, [rax]
0x1800042ee  test    rcx, rcx
0x1800042f1  jz      loc_1800043BE
0x1800042f7  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800042fe  xchg    ax, ax
0x180004300  inc     rax
0x180004303  cmp     [rcx+rax], r8b
0x180004307  jnz     short loc_180004300
0x180004309  inc     eax
0x18000430b  mov     [rsp+0A8h+var_30], eax
0x18000430f  xor     r9d, r9d; RelatedActivityId
0x180004312  movzx   eax, byte ptr [rdx]
0x180004315  shl     eax, 18h
0x180004318  mov     dword ptr [rsp+0A8h+EventDescriptor.Id], eax
0x18000431c  movzx   eax, word ptr [rdx+1]
0x180004320  mov     dword ptr [rsp+0A8h+EventDescriptor.Level], eax
0x180004324  mov     rax, [rdx+3]
0x180004328  mov     [rsp+0A8h+EventDescriptor.Keyword], rax
0x18000432d  mov     rax, cs:off_180037058
0x180004334  mov     [rsp+0A8h+var_58.Ptr], rax
0x180004339  mov     [rsp+0A8h+var_38], rcx
0x18000433e  lea     rcx, [rdx+0Bh]
0x180004342  mov     [rsp+0A8h+var_2C], r8d
0x180004347  lea     rdx, [rsp+0A8h+EventDescriptor]; EventDescriptor
0x18000434c  movzx   eax, word ptr [rax]
0x18000434f  mov     [rsp+0A8h+var_58.Size], eax
0x180004353  movzx   eax, word ptr [rcx]
0x180004356  mov     [rsp+0A8h+var_40], eax
0x18000435a  lea     rax, _TraceLoggingMetadataEnd
0x180004361  mov     [rsp+0A8h+var_48], rcx
0x180004366  lea     rcx, _TraceLoggingMetadata
0x18000436d  sub     eax, ecx
0x18000436f  mov     dword ptr [rsp+0A8h+var_58.0Ch], 2
0x180004377  mov     [rsp+0A8h+var_3C], 1
0x18000437f  mov     [rsp+0A8h+var_78], eax
0x180004383  mov     eax, [rsp+0A8h+var_78]
0x180004387  mov     rcx, cs:RegHandle; RegHandle
0x18000438e  lea     rax, [rsp+0A8h+var_58]
0x180004393  mov     [rsp+0A8h+UserData], rax; UserData
0x180004398  mov     [rsp+0A8h+UserDataCount], 4; UserDataCount
0x1800043a0  call    cs:__imp_EventWriteTransfer
0x1800043a6  mov     rcx, [rsp+0A8h+var_18]
0x1800043ae  xor     rcx, rsp; StackCookie
0x1800043b1  call    __security_check_cookie
0x1800043b6  add     rsp, 0A8h
0x1800043bd  retn
0x1800043be  lea     rcx, byte_18002AE5D
0x1800043c5  mov     eax, 1
0x1800043ca  jmp     loc_18000430B
```
