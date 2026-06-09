# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>,_tlgWrapSid<_SID>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &,_tlgWrapSid<_SID> const &)

- ea: `0x18000e8a4`
- end: `0x18000e9ed`
- name: `??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapSz@G@@U?$_tlgWrapSid@U_SID@@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapSid@U_SID@@@@@Z`
- size: `329`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180017a9c`
- `0x1800188c0`

## callees

- `0x18000e8a4`
- `0x180015af0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000e9c3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000e9c3`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapSid<_SID>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 *a5,
        __int64 *a6,
        __int64 a7,
        const WCHAR **a8,
        __int64 *a9)
{
  int v9; // eax
  const WCHAR *v10; // rcx
  __int64 v11; // rax
  int v12; // eax
  __int64 v13; // rcx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-69h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-51h] BYREF
  unsigned __int8 *v17; // [rsp+60h] [rbp-41h]
  int v18; // [rsp+68h] [rbp-39h]
  int v19; // [rsp+6Ch] [rbp-35h]
  __int64 v20; // [rsp+70h] [rbp-31h]
  __int64 v21; // [rsp+78h] [rbp-29h]
  __int64 v22; // [rsp+80h] [rbp-21h]
  __int64 v23; // [rsp+88h] [rbp-19h]
  __int64 v24; // [rsp+90h] [rbp-11h]
  __int64 v25; // [rsp+98h] [rbp-9h]
  const WCHAR *v26; // [rsp+A0h] [rbp-1h]
  int v27; // [rsp+A8h] [rbp+7h]
  int v28; // [rsp+ACh] [rbp+Bh]
  __int64 v29; // [rsp+B0h] [rbp+Fh]
  int v30; // [rsp+B8h] [rbp+17h]
  int v31; // [rsp+BCh] [rbp+1Bh]

  v9 = *(unsigned __int8 *)(*a9 + 1);
  v29 = *a9;
  v31 = 0;
  v30 = 4 * v9 + 8;
  v10 = *a8;
  if ( *a8 )
  {
    v11 = -1;
    do
      ++v11;
    while ( v10[v11] );
    v12 = 2 * v11 + 2;
  }
  else
  {
    v10 = &LocaleName;
    v12 = 2;
  }
  v27 = v12;
  v24 = a7;
  v26 = v10;
  v25 = 1;
  v28 = 0;
  v22 = *a6;
  v23 = 16;
  v21 = 16;
  v13 = *a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (ULONGLONG)off_180028008;
  v20 = v13;
  UserData.Size = *(unsigned __int16 *)off_180028008;
  v18 = *(unsigned __int16 *)(a2 + 11);
  v17 = a2 + 11;
  v19 = 1;
  UserData.Reserved = 2;
  return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 7u, &UserData);
}

```

## disassembly

```asm
0x18000e8a4  push    rbp
0x18000e8a6  lea     rbp, [rsp-2Fh]
0x18000e8ab  sub     rsp, 0D0h
0x18000e8b2  mov     rax, cs:__security_cookie
0x18000e8b9  xor     rax, rsp
0x18000e8bc  mov     [rbp+2Fh+var_10], rax
0x18000e8c0  mov     rax, [rbp+2Fh+arg_40]
0x18000e8c4  xor     r10d, r10d
0x18000e8c7  mov     rcx, [rax]
0x18000e8ca  lea     r11d, [r10+2]
0x18000e8ce  movzx   eax, byte ptr [rcx+1]
0x18000e8d2  mov     [rbp+2Fh+var_20], rcx
0x18000e8d6  mov     [rbp+2Fh+var_14], r10d
0x18000e8da  lea     eax, ds:8[rax*4]
0x18000e8e1  mov     [rbp+2Fh+var_18], eax
0x18000e8e4  mov     rax, [rbp+2Fh+arg_38]
0x18000e8e8  mov     rcx, [rax]
0x18000e8eb  test    rcx, rcx
0x18000e8ee  jz      loc_18000E9DE
0x18000e8f4  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e8f8  inc     rax
0x18000e8fb  cmp     [rcx+rax*2], r10w
0x18000e900  jnz     short loc_18000E8F8
0x18000e902  lea     eax, ds:2[rax*2]
0x18000e909  mov     [rbp+2Fh+var_28], eax
0x18000e90c  mov     r9d, 1
0x18000e912  mov     rax, [rbp+2Fh+arg_30]
0x18000e916  xor     r8d, r8d; ActivityId
0x18000e919  mov     [rbp+2Fh+var_40], rax
0x18000e91d  mov     rax, [rbp+2Fh+arg_28]
0x18000e921  mov     [rbp+2Fh+var_30], rcx
0x18000e925  mov     [rbp+2Fh+var_38], r9
0x18000e929  mov     [rbp+2Fh+var_24], r10d
0x18000e92d  mov     rcx, [rax]
0x18000e930  mov     rax, [rbp+2Fh+arg_20]
0x18000e934  mov     [rbp+2Fh+var_50], rcx
0x18000e938  mov     [rbp+2Fh+var_48], 10h
0x18000e940  mov     [rbp+2Fh+var_58], 10h
0x18000e948  mov     rcx, [rax]
0x18000e94b  movzx   eax, byte ptr [rdx]
0x18000e94e  shl     eax, 18h
0x18000e951  mov     dword ptr [rbp+2Fh+EventDescriptor.Id], eax
0x18000e954  movzx   eax, word ptr [rdx+1]
0x18000e958  mov     dword ptr [rbp+2Fh+EventDescriptor.Level], eax
0x18000e95b  mov     rax, [rdx+3]
0x18000e95f  mov     [rbp+2Fh+EventDescriptor.Keyword], rax
0x18000e963  mov     rax, cs:off_180028008
0x18000e96a  mov     [rbp+2Fh+var_80.Ptr], rax
0x18000e96e  mov     [rbp+2Fh+var_60], rcx
0x18000e972  lea     rcx, [rdx+0Bh]
0x18000e976  lea     rdx, [rbp+2Fh+EventDescriptor]; EventDescriptor
0x18000e97a  movzx   eax, word ptr [rax]
0x18000e97d  mov     [rbp+2Fh+var_80.Size], eax
0x18000e980  movzx   eax, word ptr [rcx]
0x18000e983  mov     [rbp+2Fh+var_68], eax
0x18000e986  lea     rax, _TraceLoggingMetadataEnd
0x18000e98d  mov     [rbp+2Fh+var_70], rcx
0x18000e991  lea     rcx, _TraceLoggingMetadata
0x18000e998  sub     eax, ecx
0x18000e99a  mov     [rbp+2Fh+var_64], r9d
0x18000e99e  mov     dword ptr [rbp+2Fh+var_80.0Ch], r11d
0x18000e9a2  xor     r9d, r9d; RelatedActivityId
0x18000e9a5  mov     [rbp+2Fh+var_A0], eax
0x18000e9a8  mov     eax, [rbp+2Fh+var_A0]
0x18000e9ab  mov     rcx, cs:RegHandle; RegHandle
0x18000e9b2  lea     rax, [rbp+2Fh+var_80]
0x18000e9b6  mov     [rsp+0D0h+UserData], rax; UserData
0x18000e9bb  mov     [rsp+0D0h+UserDataCount], 7; UserDataCount
0x18000e9c3  call    cs:__imp_EventWriteTransfer
0x18000e9c9  mov     rcx, [rbp+2Fh+var_10]
0x18000e9cd  xor     rcx, rsp; StackCookie
0x18000e9d0  call    __security_check_cookie
0x18000e9d5  add     rsp, 0D0h
0x18000e9dc  pop     rbp
0x18000e9dd  retn
0x18000e9de  lea     rcx, LocaleName
0x18000e9e5  mov     eax, r11d
0x18000e9e8  jmp     loc_18000E909
```
