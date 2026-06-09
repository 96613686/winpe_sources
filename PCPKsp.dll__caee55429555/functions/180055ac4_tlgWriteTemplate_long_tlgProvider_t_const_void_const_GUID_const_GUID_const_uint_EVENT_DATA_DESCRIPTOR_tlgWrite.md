# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180055ac4`
- end: `0x180055bd5`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800157c0`

## callees

- `0x180055ac4`
- `0x1800764d0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180055bb3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180055bb3`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int **a6,
        __int64 a7)
{
  int *v8; // rcx
  __int64 v9; // rax
  int v10; // eax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-21h] BYREF
  unsigned __int8 *v14; // [rsp+60h] [rbp-11h]
  int v15; // [rsp+68h] [rbp-9h]
  int v16; // [rsp+6Ch] [rbp-5h]
  __int64 v17; // [rsp+70h] [rbp-1h]
  __int64 v18; // [rsp+78h] [rbp+7h]
  int *v19; // [rsp+80h] [rbp+Fh]
  int v20; // [rsp+88h] [rbp+17h]
  int v21; // [rsp+8Ch] [rbp+1Bh]
  __int64 v22; // [rsp+90h] [rbp+1Fh]
  __int64 v23; // [rsp+98h] [rbp+27h]

  v22 = a7;
  v23 = 4;
  v8 = *a6;
  if ( *a6 )
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
  v20 = v10;
  v17 = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = *(_QWORD *)(a1 + 8);
  v19 = v8;
  v21 = 0;
  v18 = 8;
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
0x180055ac4  push    rbp
0x180055ac6  lea     rbp, [rsp-3Fh]
0x180055acb  sub     rsp, 0B0h
0x180055ad2  mov     rax, cs:__security_cookie
0x180055ad9  xor     rax, rsp
0x180055adc  mov     [rbp+3Fh+var_10], rax
0x180055ae0  mov     rax, [rbp+3Fh+arg_30]
0x180055ae4  xor     r8d, r8d; ActivityId
0x180055ae7  mov     [rbp+3Fh+var_20], rax
0x180055aeb  mov     r10, rcx
0x180055aee  mov     rax, [rbp+3Fh+arg_28]
0x180055af2  mov     [rbp+3Fh+var_18], 4
0x180055afa  lea     r9d, [r8+2]
0x180055afe  mov     rcx, [rax]
0x180055b01  test    rcx, rcx
0x180055b04  jz      short loc_180055B1D
0x180055b06  or      rax, 0FFFFFFFFFFFFFFFFh
0x180055b0a  inc     rax
0x180055b0d  cmp     [rcx+rax*2], r8w
0x180055b12  jnz     short loc_180055B0A
0x180055b14  lea     eax, ds:2[rax*2]
0x180055b1b  jmp     short loc_180055B27
0x180055b1d  lea     rcx, dword_1800DB714
0x180055b24  mov     eax, r9d
0x180055b27  mov     [rbp+3Fh+var_28], eax
0x180055b2a  mov     rax, [rbp+3Fh+arg_20]
0x180055b2e  mov     [rbp+3Fh+var_40], rax
0x180055b32  movzx   eax, byte ptr [rdx]
0x180055b35  shl     eax, 18h
0x180055b38  mov     dword ptr [rbp+3Fh+EventDescriptor.Id], eax
0x180055b3b  movzx   eax, word ptr [rdx+1]
0x180055b3f  mov     dword ptr [rbp+3Fh+EventDescriptor.Level], eax
0x180055b42  mov     rax, [rdx+3]
0x180055b46  mov     [rbp+3Fh+EventDescriptor.Keyword], rax
0x180055b4a  mov     rax, [r10+8]
0x180055b4e  mov     [rbp+3Fh+var_60.Ptr], rax
0x180055b52  mov     [rbp+3Fh+var_30], rcx
0x180055b56  lea     rcx, [rdx+0Bh]
0x180055b5a  mov     [rbp+3Fh+var_24], r8d
0x180055b5e  lea     rdx, [rbp+3Fh+EventDescriptor]; EventDescriptor
0x180055b62  mov     [rbp+3Fh+var_38], 8
0x180055b6a  movzx   eax, word ptr [rax]
0x180055b6d  mov     [rbp+3Fh+var_60.Size], eax
0x180055b70  movzx   eax, word ptr [rcx]
0x180055b73  mov     [rbp+3Fh+var_48], eax
0x180055b76  lea     rax, _TraceLoggingMetadataEnd
0x180055b7d  mov     [rbp+3Fh+var_50], rcx
0x180055b81  lea     rcx, _TraceLoggingMetadata
0x180055b88  sub     eax, ecx
0x180055b8a  mov     dword ptr [rbp+3Fh+var_60.0Ch], r9d
0x180055b8e  mov     [rbp+3Fh+var_44], 1
0x180055b95  xor     r9d, r9d; RelatedActivityId
0x180055b98  mov     [rbp+3Fh+var_80], eax
0x180055b9b  mov     eax, [rbp+3Fh+var_80]
0x180055b9e  mov     rcx, [r10+20h]; RegHandle
0x180055ba2  lea     rax, [rbp+3Fh+var_60]
0x180055ba6  mov     [rsp+0B0h+UserData], rax; UserData
0x180055bab  mov     [rsp+0B0h+UserDataCount], 5; UserDataCount
0x180055bb3  call    cs:__imp_EventWriteTransfer
0x180055bba  nop     dword ptr [rax+rax+00h]
0x180055bbf  mov     rcx, [rbp+3Fh+var_10]
0x180055bc3  xor     rcx, rsp; StackCookie
0x180055bc6  call    __security_check_cookie
0x180055bcb  add     rsp, 0B0h
0x180055bd2  pop     rbp
0x180055bd3  retn
```
