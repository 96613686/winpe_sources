# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x18000ed44`
- end: `0x18000ee78`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@444@Z`
- size: `308`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, __int64, __int64, int **, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180011a90`

## callees

- `0x18000ed44`
- `0x18001aec0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000ee4e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000ee4e`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        int **a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  int *v9; // rcx
  __int64 v10; // rax
  int v11; // eax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-69h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-51h] BYREF
  unsigned __int8 *v15; // [rsp+60h] [rbp-41h]
  int v16; // [rsp+68h] [rbp-39h]
  int v17; // [rsp+6Ch] [rbp-35h]
  int *v18; // [rsp+70h] [rbp-31h]
  int v19; // [rsp+78h] [rbp-29h]
  int v20; // [rsp+7Ch] [rbp-25h]
  __int64 v21; // [rsp+80h] [rbp-21h]
  __int64 v22; // [rsp+88h] [rbp-19h]
  __int64 v23; // [rsp+90h] [rbp-11h]
  __int64 v24; // [rsp+98h] [rbp-9h]
  __int64 v25; // [rsp+A0h] [rbp-1h]
  __int64 v26; // [rsp+A8h] [rbp+7h]
  __int64 v27; // [rsp+B0h] [rbp+Fh]
  __int64 v28; // [rsp+B8h] [rbp+17h]

  v27 = a9;
  v25 = a8;
  v23 = a7;
  v21 = a6;
  v28 = 4;
  v26 = 4;
  v24 = 4;
  v9 = *a5;
  v22 = 4;
  if ( v9 )
  {
    v10 = -1;
    do
      ++v10;
    while ( *((_WORD *)v9 + v10) );
    v11 = 2 * v10 + 2;
  }
  else
  {
    v9 = &dword_1800232A4;
    v11 = 2;
  }
  v19 = v11;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (ULONGLONG)off_18002E008;
  v18 = v9;
  v20 = 0;
  UserData.Size = *(unsigned __int16 *)off_18002E008;
  v16 = *(unsigned __int16 *)(a2 + 11);
  v15 = a2 + 11;
  UserData.Reserved = 2;
  v17 = 1;
  return EventWriteTransfer(qword_18002E020, &EventDescriptor, 0, 0, 7u, &UserData);
}

```

## disassembly

```asm
0x18000ed44  push    rbp
0x18000ed46  lea     rbp, [rsp-2Fh]
0x18000ed4b  sub     rsp, 0D0h
0x18000ed52  mov     rax, cs:__security_cookie
0x18000ed59  xor     rax, rsp
0x18000ed5c  mov     [rbp+2Fh+var_10], rax
0x18000ed60  mov     rax, [rbp+2Fh+arg_40]
0x18000ed64  xor     r8d, r8d; ActivityId
0x18000ed67  mov     [rbp+2Fh+var_20], rax
0x18000ed6b  mov     rax, [rbp+2Fh+arg_38]
0x18000ed6f  mov     [rbp+2Fh+var_30], rax
0x18000ed73  mov     rax, [rbp+2Fh+arg_30]
0x18000ed77  lea     r9d, [r8+2]
0x18000ed7b  mov     [rbp+2Fh+var_40], rax
0x18000ed7f  mov     rax, [rbp+2Fh+arg_28]
0x18000ed83  mov     [rbp+2Fh+var_50], rax
0x18000ed87  mov     rax, [rbp+2Fh+arg_20]
0x18000ed8b  mov     [rbp+2Fh+var_18], 4
0x18000ed93  mov     [rbp+2Fh+var_28], 4
0x18000ed9b  mov     [rbp+2Fh+var_38], 4
0x18000eda3  mov     rcx, [rax]
0x18000eda6  mov     [rbp+2Fh+var_48], 4
0x18000edae  test    rcx, rcx
0x18000edb1  jz      loc_18000EE69
0x18000edb7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000edbb  inc     rax
0x18000edbe  cmp     [rcx+rax*2], r8w
0x18000edc3  jnz     short loc_18000EDBB
0x18000edc5  lea     eax, ds:2[rax*2]
0x18000edcc  mov     [rbp+2Fh+var_58], eax
0x18000edcf  movzx   eax, byte ptr [rdx]
0x18000edd2  shl     eax, 18h
0x18000edd5  mov     dword ptr [rbp+2Fh+EventDescriptor.Id], eax
0x18000edd8  movzx   eax, word ptr [rdx+1]
0x18000eddc  mov     dword ptr [rbp+2Fh+EventDescriptor.Level], eax
0x18000eddf  mov     rax, [rdx+3]
0x18000ede3  mov     [rbp+2Fh+EventDescriptor.Keyword], rax
0x18000ede7  mov     rax, cs:off_18002E008
0x18000edee  mov     [rbp+2Fh+var_80.Ptr], rax
0x18000edf2  mov     [rbp+2Fh+var_60], rcx
0x18000edf6  lea     rcx, [rdx+0Bh]
0x18000edfa  mov     [rbp+2Fh+var_54], r8d
0x18000edfe  lea     rdx, [rbp+2Fh+EventDescriptor]; EventDescriptor
0x18000ee02  movzx   eax, word ptr [rax]
0x18000ee05  mov     [rbp+2Fh+var_80.Size], eax
0x18000ee08  movzx   eax, word ptr [rcx]
0x18000ee0b  mov     [rbp+2Fh+var_68], eax
0x18000ee0e  lea     rax, _TraceLoggingMetadataEnd
0x18000ee15  mov     [rbp+2Fh+var_70], rcx
0x18000ee19  lea     rcx, _TraceLoggingMetadata
0x18000ee20  sub     eax, ecx
0x18000ee22  mov     dword ptr [rbp+2Fh+var_80.0Ch], r9d
0x18000ee26  mov     [rbp+2Fh+var_64], 1
0x18000ee2d  xor     r9d, r9d; RelatedActivityId
0x18000ee30  mov     [rbp+2Fh+var_A0], eax
0x18000ee33  mov     eax, [rbp+2Fh+var_A0]
0x18000ee36  mov     rcx, cs:qword_18002E020; RegHandle
0x18000ee3d  lea     rax, [rbp+2Fh+var_80]
0x18000ee41  mov     [rsp+0D0h+UserData], rax; UserData
0x18000ee46  mov     [rsp+0D0h+UserDataCount], 7; UserDataCount
0x18000ee4e  call    cs:__imp_EventWriteTransfer
0x18000ee54  mov     rcx, [rbp+2Fh+var_10]
0x18000ee58  xor     rcx, rsp; StackCookie
0x18000ee5b  call    __security_check_cookie
0x18000ee60  add     rsp, 0D0h
0x18000ee67  pop     rbp
0x18000ee68  retn
0x18000ee69  lea     rcx, dword_1800232A4
0x18000ee70  mov     eax, r9d
0x18000ee73  jmp     loc_18000EDCC
```
