# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)

- ea: `0x180018cdc`
- end: `0x180018dfd`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@5@Z`
- size: `289`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, __int64, __int64, char **, __int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180020a40`
- `0x180020b4c`
- `0x180020bd8`
- `0x18003a770`
- `0x18003a93c`

## callees

- `0x180018cdc`
- `0x18002a030`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180018dd3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180018dd3`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        char **a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  char *v9; // rcx
  __int64 v10; // rax
  int v11; // eax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-51h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-39h] BYREF
  unsigned __int8 *v15; // [rsp+60h] [rbp-29h]
  int v16; // [rsp+68h] [rbp-21h]
  int v17; // [rsp+6Ch] [rbp-1Dh]
  char *v18; // [rsp+70h] [rbp-19h]
  int v19; // [rsp+78h] [rbp-11h]
  int v20; // [rsp+7Ch] [rbp-Dh]
  __int64 v21; // [rsp+80h] [rbp-9h]
  __int64 v22; // [rsp+88h] [rbp-1h]
  __int64 v23; // [rsp+90h] [rbp+7h]
  __int64 v24; // [rsp+98h] [rbp+Fh]
  __int64 v25; // [rsp+A0h] [rbp+17h]
  __int64 v26; // [rsp+A8h] [rbp+1Fh]

  v25 = a8;
  v23 = a7;
  v21 = a6;
  v26 = 8;
  v24 = 8;
  v22 = 4;
  v9 = *a5;
  if ( *a5 )
  {
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)&v9[2 * v10] );
    v11 = 2 * v10 + 2;
  }
  else
  {
    v9 = byte_180043BA0;
    v11 = 2;
  }
  v19 = v11;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = *(_QWORD *)(a1 + 8);
  v18 = v9;
  v20 = 0;
  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
  v16 = *(unsigned __int16 *)(a2 + 11);
  v15 = a2 + 11;
  UserData.Reserved = 2;
  v17 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, 0, 0, 6u, &UserData);
}

```

## disassembly

```asm
0x180018cdc  push    rbp
0x180018cde  lea     rbp, [rsp-37h]
0x180018ce3  sub     rsp, 0C0h
0x180018cea  mov     rax, cs:__security_cookie
0x180018cf1  xor     rax, rsp
0x180018cf4  mov     [rbp+37h+var_10], rax
0x180018cf8  mov     rax, [rbp+37h+arg_38]
0x180018cfc  xor     r8d, r8d; ActivityId
0x180018cff  mov     [rbp+37h+var_20], rax
0x180018d03  mov     r10, rcx
0x180018d06  mov     rax, [rbp+37h+arg_30]
0x180018d0a  mov     [rbp+37h+var_30], rax
0x180018d0e  mov     rax, [rbp+37h+arg_28]
0x180018d12  lea     r9d, [r8+2]
0x180018d16  mov     [rbp+37h+var_40], rax
0x180018d1a  mov     rax, [rbp+37h+arg_20]
0x180018d1e  mov     [rbp+37h+var_18], 8
0x180018d26  mov     [rbp+37h+var_28], 8
0x180018d2e  mov     [rbp+37h+var_38], 4
0x180018d36  mov     rcx, [rax]
0x180018d39  test    rcx, rcx
0x180018d3c  jz      loc_180018DEE
0x180018d42  or      rax, 0FFFFFFFFFFFFFFFFh
0x180018d46  inc     rax
0x180018d49  cmp     [rcx+rax*2], r8w
0x180018d4e  jnz     short loc_180018D46
0x180018d50  lea     eax, ds:2[rax*2]
0x180018d57  mov     [rbp+37h+var_48], eax
0x180018d5a  movzx   eax, byte ptr [rdx]
0x180018d5d  shl     eax, 18h
0x180018d60  mov     dword ptr [rbp+37h+EventDescriptor.Id], eax
0x180018d63  movzx   eax, word ptr [rdx+1]
0x180018d67  mov     dword ptr [rbp+37h+EventDescriptor.Level], eax
0x180018d6a  mov     rax, [rdx+3]
0x180018d6e  mov     [rbp+37h+EventDescriptor.Keyword], rax
0x180018d72  mov     rax, [r10+8]
0x180018d76  mov     [rbp+37h+var_70.Ptr], rax
0x180018d7a  mov     [rbp+37h+var_50], rcx
0x180018d7e  lea     rcx, [rdx+0Bh]
0x180018d82  mov     [rbp+37h+var_44], r8d
0x180018d86  lea     rdx, [rbp+37h+EventDescriptor]; EventDescriptor
0x180018d8a  movzx   eax, word ptr [rax]
0x180018d8d  mov     [rbp+37h+var_70.Size], eax
0x180018d90  movzx   eax, word ptr [rcx]
0x180018d93  mov     [rbp+37h+var_58], eax
0x180018d96  lea     rax, _TraceLoggingMetadataEnd
0x180018d9d  mov     [rbp+37h+var_60], rcx
0x180018da1  lea     rcx, _TraceLoggingMetadata
0x180018da8  sub     eax, ecx
0x180018daa  mov     dword ptr [rbp+37h+var_70.0Ch], r9d
0x180018dae  mov     [rbp+37h+var_54], 1
0x180018db5  xor     r9d, r9d; RelatedActivityId
0x180018db8  mov     [rbp+37h+var_90], eax
0x180018dbb  mov     eax, [rbp+37h+var_90]
0x180018dbe  mov     rcx, [r10+20h]; RegHandle
0x180018dc2  lea     rax, [rbp+37h+var_70]
0x180018dc6  mov     [rsp+0C0h+UserData], rax; UserData
0x180018dcb  mov     [rsp+0C0h+UserDataCount], 6; UserDataCount
0x180018dd3  call    cs:__imp_EventWriteTransfer
0x180018dd9  mov     rcx, [rbp+37h+var_10]
0x180018ddd  xor     rcx, rsp; StackCookie
0x180018de0  call    __security_check_cookie
0x180018de5  add     rsp, 0C0h
0x180018dec  pop     rbp
0x180018ded  retn
0x180018dee  lea     rcx, byte_180043BA0
0x180018df5  mov     eax, r9d
0x180018df8  jmp     loc_180018D57
```
