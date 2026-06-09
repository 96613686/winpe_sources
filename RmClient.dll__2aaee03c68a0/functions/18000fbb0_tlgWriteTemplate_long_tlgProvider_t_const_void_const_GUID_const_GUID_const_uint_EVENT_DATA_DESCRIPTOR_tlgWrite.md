# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &)

- ea: `0x18000fbb0`
- end: `0x18000fcd3`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$00@@@Z`
- size: `291`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, __int64, __int64, __int64, __int64, int **, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180010650`

## callees

- `0x18000fbb0`
- `0x18001aec0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000fca9`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000fca9`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int **a7,
        __int64 a8)
{
  int *v8; // rcx
  __int64 v9; // rax
  int v10; // eax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-51h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-39h] BYREF
  unsigned __int8 *v14; // [rsp+60h] [rbp-29h]
  int v15; // [rsp+68h] [rbp-21h]
  int v16; // [rsp+6Ch] [rbp-1Dh]
  __int64 v17; // [rsp+70h] [rbp-19h]
  __int64 v18; // [rsp+78h] [rbp-11h]
  __int64 v19; // [rsp+80h] [rbp-9h]
  __int64 v20; // [rsp+88h] [rbp-1h]
  int *v21; // [rsp+90h] [rbp+7h]
  int v22; // [rsp+98h] [rbp+Fh]
  int v23; // [rsp+9Ch] [rbp+13h]
  __int64 v24; // [rsp+A0h] [rbp+17h]
  __int64 v25; // [rsp+A8h] [rbp+1Fh]

  v24 = a8;
  v25 = 1;
  v8 = *a7;
  if ( *a7 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *((_WORD *)v8 + v9) );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v8 = &dword_1800232A4;
    v10 = 2;
  }
  v22 = v10;
  v19 = a6;
  v17 = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (ULONGLONG)off_18002E040;
  v21 = v8;
  v23 = 0;
  v20 = 8;
  v18 = 4;
  UserData.Size = (unsigned __int16)*off_18002E040;
  v15 = *(unsigned __int16 *)(a2 + 11);
  v14 = a2 + 11;
  UserData.Reserved = 2;
  v16 = 1;
  return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 6u, &UserData);
}

```

## disassembly

```asm
0x18000fbb0  push    rbp
0x18000fbb2  lea     rbp, [rsp-37h]
0x18000fbb7  sub     rsp, 0C0h
0x18000fbbe  mov     rax, cs:__security_cookie
0x18000fbc5  xor     rax, rsp
0x18000fbc8  mov     [rbp+37h+var_10], rax
0x18000fbcc  mov     rax, [rbp+37h+arg_38]
0x18000fbd0  mov     r10d, 1
0x18000fbd6  mov     [rbp+37h+var_20], rax
0x18000fbda  xor     r8d, r8d; ActivityId
0x18000fbdd  mov     rax, [rbp+37h+arg_30]
0x18000fbe1  mov     [rbp+37h+var_18], r10
0x18000fbe5  lea     r9d, [r10+1]
0x18000fbe9  mov     rcx, [rax]
0x18000fbec  test    rcx, rcx
0x18000fbef  jz      loc_18000FCC4
0x18000fbf5  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000fbf9  inc     rax
0x18000fbfc  cmp     [rcx+rax*2], r8w
0x18000fc01  jnz     short loc_18000FBF9
0x18000fc03  lea     eax, ds:2[rax*2]
0x18000fc0a  mov     [rbp+37h+var_28], eax
0x18000fc0d  mov     rax, [rbp+37h+arg_28]
0x18000fc11  mov     [rbp+37h+var_40], rax
0x18000fc15  mov     rax, [rbp+37h+arg_20]
0x18000fc19  mov     [rbp+37h+var_50], rax
0x18000fc1d  movzx   eax, byte ptr [rdx]
0x18000fc20  shl     eax, 18h
0x18000fc23  mov     dword ptr [rbp+37h+EventDescriptor.Id], eax
0x18000fc26  movzx   eax, word ptr [rdx+1]
0x18000fc2a  mov     dword ptr [rbp+37h+EventDescriptor.Level], eax
0x18000fc2d  mov     rax, [rdx+3]
0x18000fc31  mov     [rbp+37h+EventDescriptor.Keyword], rax
0x18000fc35  mov     rax, cs:off_18002E040
0x18000fc3c  mov     [rbp+37h+var_70.Ptr], rax
0x18000fc40  mov     [rbp+37h+var_30], rcx
0x18000fc44  lea     rcx, [rdx+0Bh]
0x18000fc48  mov     [rbp+37h+var_24], r8d
0x18000fc4c  lea     rdx, [rbp+37h+EventDescriptor]; EventDescriptor
0x18000fc50  mov     [rbp+37h+var_38], 8
0x18000fc58  mov     [rbp+37h+var_48], 4
0x18000fc60  movzx   eax, word ptr [rax]
0x18000fc63  mov     [rbp+37h+var_70.Size], eax
0x18000fc66  movzx   eax, word ptr [rcx]
0x18000fc69  mov     [rbp+37h+var_58], eax
0x18000fc6c  lea     rax, _TraceLoggingMetadataEnd
0x18000fc73  mov     [rbp+37h+var_60], rcx
0x18000fc77  lea     rcx, _TraceLoggingMetadata
0x18000fc7e  sub     eax, ecx
0x18000fc80  mov     dword ptr [rbp+37h+var_70.0Ch], r9d
0x18000fc84  mov     [rbp+37h+var_54], r10d
0x18000fc88  xor     r9d, r9d; RelatedActivityId
0x18000fc8b  mov     [rbp+37h+var_90], eax
0x18000fc8e  mov     eax, [rbp+37h+var_90]
0x18000fc91  mov     rcx, cs:RegHandle; RegHandle
0x18000fc98  lea     rax, [rbp+37h+var_70]
0x18000fc9c  mov     [rsp+0C0h+UserData], rax; UserData
0x18000fca1  mov     [rsp+0C0h+UserDataCount], 6; UserDataCount
0x18000fca9  call    cs:__imp_EventWriteTransfer
0x18000fcaf  mov     rcx, [rbp+37h+var_10]
0x18000fcb3  xor     rcx, rsp; StackCookie
0x18000fcb6  call    __security_check_cookie
0x18000fcbb  add     rsp, 0C0h
0x18000fcc2  pop     rbp
0x18000fcc3  retn
0x18000fcc4  lea     rcx, dword_1800232A4
0x18000fccb  mov     eax, r9d
0x18000fcce  jmp     loc_18000FC0A
```
