# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x18000f978`
- end: `0x18000faaf`
- name: `??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@44@Z`
- size: `311`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180012300`
- `0x1800124b0`

## callees

- `0x18000f978`
- `0x180015af0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000fa85`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000fa85`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 *a5,
        __int64 a6,
        const WCHAR **a7,
        __int64 a8,
        __int64 a9)
{
  const WCHAR *v9; // rcx
  __int64 v10; // rax
  int v11; // eax
  __int64 v12; // rcx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-69h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-51h] BYREF
  unsigned __int8 *v16; // [rsp+60h] [rbp-41h]
  int v17; // [rsp+68h] [rbp-39h]
  int v18; // [rsp+6Ch] [rbp-35h]
  __int64 v19; // [rsp+70h] [rbp-31h]
  __int64 v20; // [rsp+78h] [rbp-29h]
  __int64 v21; // [rsp+80h] [rbp-21h]
  __int64 v22; // [rsp+88h] [rbp-19h]
  const WCHAR *v23; // [rsp+90h] [rbp-11h]
  int v24; // [rsp+98h] [rbp-9h]
  int v25; // [rsp+9Ch] [rbp-5h]
  __int64 v26; // [rsp+A0h] [rbp-1h]
  __int64 v27; // [rsp+A8h] [rbp+7h]
  __int64 v28; // [rsp+B0h] [rbp+Fh]
  __int64 v29; // [rsp+B8h] [rbp+17h]

  v28 = a9;
  v26 = a8;
  v29 = 4;
  v27 = 4;
  v9 = *a7;
  if ( *a7 )
  {
    v10 = -1;
    do
      ++v10;
    while ( v9[v10] );
    v11 = 2 * v10 + 2;
  }
  else
  {
    v9 = &LocaleName;
    v11 = 2;
  }
  v24 = v11;
  v21 = a6;
  v23 = v9;
  v25 = 0;
  v22 = 4;
  v12 = *a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (ULONGLONG)off_180028008;
  v19 = v12;
  v20 = 16;
  UserData.Size = *(unsigned __int16 *)off_180028008;
  v17 = *(unsigned __int16 *)(a2 + 11);
  v16 = a2 + 11;
  UserData.Reserved = 2;
  v18 = 1;
  return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 7u, &UserData);
}

```

## disassembly

```asm
0x18000f978  push    rbp
0x18000f97a  lea     rbp, [rsp-2Fh]
0x18000f97f  sub     rsp, 0D0h
0x18000f986  mov     rax, cs:__security_cookie
0x18000f98d  xor     rax, rsp
0x18000f990  mov     [rbp+2Fh+var_10], rax
0x18000f994  mov     rax, [rbp+2Fh+arg_40]
0x18000f998  xor     r8d, r8d; ActivityId
0x18000f99b  mov     [rbp+2Fh+var_20], rax
0x18000f99f  mov     rax, [rbp+2Fh+arg_38]
0x18000f9a3  mov     [rbp+2Fh+var_30], rax
0x18000f9a7  mov     rax, [rbp+2Fh+arg_30]
0x18000f9ab  lea     r10d, [r8+2]
0x18000f9af  mov     [rbp+2Fh+var_18], 4
0x18000f9b7  mov     [rbp+2Fh+var_28], 4
0x18000f9bf  mov     rcx, [rax]
0x18000f9c2  test    rcx, rcx
0x18000f9c5  jz      loc_18000FAA0
0x18000f9cb  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f9cf  inc     rax
0x18000f9d2  cmp     [rcx+rax*2], r8w
0x18000f9d7  jnz     short loc_18000F9CF
0x18000f9d9  lea     eax, ds:2[rax*2]
0x18000f9e0  mov     [rbp+2Fh+var_38], eax
0x18000f9e3  xor     r9d, r9d; RelatedActivityId
0x18000f9e6  mov     rax, [rbp+2Fh+arg_28]
0x18000f9ea  mov     [rbp+2Fh+var_50], rax
0x18000f9ee  mov     rax, [rbp+2Fh+arg_20]
0x18000f9f2  mov     [rbp+2Fh+var_40], rcx
0x18000f9f6  mov     [rbp+2Fh+var_34], r8d
0x18000f9fa  mov     [rbp+2Fh+var_48], 4
0x18000fa02  mov     rcx, [rax]
0x18000fa05  movzx   eax, byte ptr [rdx]
0x18000fa08  shl     eax, 18h
0x18000fa0b  mov     dword ptr [rbp+2Fh+EventDescriptor.Id], eax
0x18000fa0e  movzx   eax, word ptr [rdx+1]
0x18000fa12  mov     dword ptr [rbp+2Fh+EventDescriptor.Level], eax
0x18000fa15  mov     rax, [rdx+3]
0x18000fa19  mov     [rbp+2Fh+EventDescriptor.Keyword], rax
0x18000fa1d  mov     rax, cs:off_180028008
0x18000fa24  mov     [rbp+2Fh+var_80.Ptr], rax
0x18000fa28  mov     [rbp+2Fh+var_60], rcx
0x18000fa2c  lea     rcx, [rdx+0Bh]
0x18000fa30  mov     [rbp+2Fh+var_58], 10h
0x18000fa38  lea     rdx, [rbp+2Fh+EventDescriptor]; EventDescriptor
0x18000fa3c  movzx   eax, word ptr [rax]
0x18000fa3f  mov     [rbp+2Fh+var_80.Size], eax
0x18000fa42  movzx   eax, word ptr [rcx]
0x18000fa45  mov     [rbp+2Fh+var_68], eax
0x18000fa48  lea     rax, _TraceLoggingMetadataEnd
0x18000fa4f  mov     [rbp+2Fh+var_70], rcx
0x18000fa53  lea     rcx, _TraceLoggingMetadata
0x18000fa5a  sub     eax, ecx
0x18000fa5c  mov     dword ptr [rbp+2Fh+var_80.0Ch], r10d
0x18000fa60  mov     [rbp+2Fh+var_64], 1
0x18000fa67  mov     [rbp+2Fh+var_A0], eax
0x18000fa6a  mov     eax, [rbp+2Fh+var_A0]
0x18000fa6d  mov     rcx, cs:RegHandle; RegHandle
0x18000fa74  lea     rax, [rbp+2Fh+var_80]
0x18000fa78  mov     [rsp+0D0h+UserData], rax; UserData
0x18000fa7d  mov     [rsp+0D0h+UserDataCount], 7; UserDataCount
0x18000fa85  call    cs:__imp_EventWriteTransfer
0x18000fa8b  mov     rcx, [rbp+2Fh+var_10]
0x18000fa8f  xor     rcx, rsp; StackCookie
0x18000fa92  call    __security_check_cookie
0x18000fa97  add     rsp, 0D0h
0x18000fa9e  pop     rbp
0x18000fa9f  retn
0x18000faa0  lea     rcx, LocaleName
0x18000faa7  mov     eax, r10d
0x18000faaa  jmp     loc_18000F9E0
```
