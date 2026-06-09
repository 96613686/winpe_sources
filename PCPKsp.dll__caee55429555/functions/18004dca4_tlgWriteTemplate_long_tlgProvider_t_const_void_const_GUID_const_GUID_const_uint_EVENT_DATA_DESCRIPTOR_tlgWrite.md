# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &)

- ea: `0x18004dca4`
- end: `0x18004ddc2`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByRef@$0BA@@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByRef@$0BA@@@4@Z`
- size: `286`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001fba8`

## callees

- `0x18004dca4`
- `0x1800764d0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18004dd91`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18004dd91`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        int **a5,
        __int64 *a6,
        __int64 *a7)
{
  int *v8; // rcx
  __int64 v9; // rax
  int v10; // eax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-21h] BYREF
  unsigned __int8 *v14; // [rsp+60h] [rbp-11h]
  int v15; // [rsp+68h] [rbp-9h]
  int v16; // [rsp+6Ch] [rbp-5h]
  int *v17; // [rsp+70h] [rbp-1h]
  int v18; // [rsp+78h] [rbp+7h]
  int v19; // [rsp+7Ch] [rbp+Bh]
  __int64 v20; // [rsp+80h] [rbp+Fh]
  __int64 v21; // [rsp+88h] [rbp+17h]
  __int64 v22; // [rsp+90h] [rbp+1Fh]
  __int64 v23; // [rsp+98h] [rbp+27h]

  v23 = 16;
  v21 = 16;
  v22 = *a7;
  v20 = *a6;
  v8 = *a5;
  if ( *a5 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *((_WORD *)v8 + v9) );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v8 = &dword_1800DB714;
    v10 = 2;
  }
  v18 = v10;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = *(_QWORD *)(a1 + 8);
  v17 = v8;
  v19 = 0;
  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
  v15 = *(unsigned __int16 *)(a2 + 11);
  v14 = a2 + 11;
  UserData.Reserved = 2;
  v16 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, 0, 0, 5u, &UserData);
}

```

## disassembly

```asm
0x18004dca4  push    rbp
0x18004dca6  lea     rbp, [rsp-3Fh]
0x18004dcab  sub     rsp, 0B0h
0x18004dcb2  mov     rax, cs:__security_cookie
0x18004dcb9  xor     rax, rsp
0x18004dcbc  mov     [rbp+3Fh+var_10], rax
0x18004dcc0  mov     rax, [rbp+3Fh+arg_30]
0x18004dcc4  mov     r10, rcx
0x18004dcc7  xor     r9d, r9d; RelatedActivityId
0x18004dcca  mov     [rbp+3Fh+var_18], 10h
0x18004dcd2  mov     [rbp+3Fh+var_28], 10h
0x18004dcda  mov     rcx, [rax]
0x18004dcdd  mov     rax, [rbp+3Fh+arg_28]
0x18004dce1  lea     r8d, [r9+2]
0x18004dce5  mov     [rbp+3Fh+var_20], rcx
0x18004dce9  mov     rcx, [rax]
0x18004dcec  mov     rax, [rbp+3Fh+arg_20]
0x18004dcf0  mov     [rbp+3Fh+var_30], rcx
0x18004dcf4  mov     rcx, [rax]
0x18004dcf7  test    rcx, rcx
0x18004dcfa  jz      loc_18004DDB3
0x18004dd00  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004dd04  inc     rax
0x18004dd07  cmp     [rcx+rax*2], r9w
0x18004dd0c  jnz     short loc_18004DD04
0x18004dd0e  lea     eax, ds:2[rax*2]
0x18004dd15  mov     [rbp+3Fh+var_38], eax
0x18004dd18  movzx   eax, byte ptr [rdx]
0x18004dd1b  shl     eax, 18h
0x18004dd1e  mov     dword ptr [rbp+3Fh+EventDescriptor.Id], eax
0x18004dd21  movzx   eax, word ptr [rdx+1]
0x18004dd25  mov     dword ptr [rbp+3Fh+EventDescriptor.Level], eax
0x18004dd28  mov     rax, [rdx+3]
0x18004dd2c  mov     [rbp+3Fh+EventDescriptor.Keyword], rax
0x18004dd30  mov     rax, [r10+8]
0x18004dd34  mov     [rbp+3Fh+var_60.Ptr], rax
0x18004dd38  mov     [rbp+3Fh+var_40], rcx
0x18004dd3c  lea     rcx, [rdx+0Bh]
0x18004dd40  mov     [rbp+3Fh+var_34], r9d
0x18004dd44  lea     rdx, [rbp+3Fh+EventDescriptor]; EventDescriptor
0x18004dd48  movzx   eax, word ptr [rax]
0x18004dd4b  mov     [rbp+3Fh+var_60.Size], eax
0x18004dd4e  movzx   eax, word ptr [rcx]
0x18004dd51  mov     [rbp+3Fh+var_48], eax
0x18004dd54  lea     rax, _TraceLoggingMetadataEnd
0x18004dd5b  mov     [rbp+3Fh+var_50], rcx
0x18004dd5f  lea     rcx, _TraceLoggingMetadata
0x18004dd66  sub     eax, ecx
0x18004dd68  mov     dword ptr [rbp+3Fh+var_60.0Ch], r8d
0x18004dd6c  mov     [rbp+3Fh+var_44], 1
0x18004dd73  xor     r8d, r8d; ActivityId
0x18004dd76  mov     [rbp+3Fh+var_80], eax
0x18004dd79  mov     eax, [rbp+3Fh+var_80]
0x18004dd7c  mov     rcx, [r10+20h]; RegHandle
0x18004dd80  lea     rax, [rbp+3Fh+var_60]
0x18004dd84  mov     [rsp+0B0h+UserData], rax; UserData
0x18004dd89  mov     [rsp+0B0h+UserDataCount], 5; UserDataCount
0x18004dd91  call    cs:__imp_EventWriteTransfer
0x18004dd98  nop     dword ptr [rax+rax+00h]
0x18004dd9d  mov     rcx, [rbp+3Fh+var_10]
0x18004dda1  xor     rcx, rsp; StackCookie
0x18004dda4  call    __security_check_cookie
0x18004dda9  add     rsp, 0B0h
0x18004ddb0  pop     rbp
0x18004ddb1  retn
0x18004ddb3  lea     rcx, dword_1800DB714
0x18004ddba  mov     eax, r8d
0x18004ddbd  jmp     loc_18004DD15
```
