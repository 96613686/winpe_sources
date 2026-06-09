# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1800555d8`
- end: `0x180055734`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U4@U?$_tlgWrapperByVal@$00@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@6AEBU?$_tlgWrapperByVal@$00@@6@Z`
- size: `348`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800210bc`

## callees

- `0x1800555d8`
- `0x1800764d0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180055712`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180055712`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 *a6,
        int **a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11)
{
  int *v11; // rcx
  __int64 v12; // rax
  int v13; // eax
  __int64 v14; // rcx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-99h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-81h] BYREF
  unsigned __int8 *v18; // [rsp+60h] [rbp-71h]
  int v19; // [rsp+68h] [rbp-69h]
  int v20; // [rsp+6Ch] [rbp-65h]
  __int64 v21; // [rsp+70h] [rbp-61h]
  __int64 v22; // [rsp+78h] [rbp-59h]
  __int64 v23; // [rsp+80h] [rbp-51h]
  __int64 v24; // [rsp+88h] [rbp-49h]
  int *v25; // [rsp+90h] [rbp-41h]
  int v26; // [rsp+98h] [rbp-39h]
  int v27; // [rsp+9Ch] [rbp-35h]
  __int64 v28; // [rsp+A0h] [rbp-31h]
  __int64 v29; // [rsp+A8h] [rbp-29h]
  __int64 v30; // [rsp+B0h] [rbp-21h]
  __int64 v31; // [rsp+B8h] [rbp-19h]
  __int64 v32; // [rsp+C0h] [rbp-11h]
  __int64 v33; // [rsp+C8h] [rbp-9h]
  __int64 v34; // [rsp+D0h] [rbp-1h]
  __int64 v35; // [rsp+D8h] [rbp+7h]

  v34 = a11;
  v32 = a10;
  v30 = a9;
  v28 = a8;
  v35 = 4;
  v33 = 1;
  v31 = 4;
  v11 = *a7;
  v29 = 4;
  if ( v11 )
  {
    v12 = -1;
    do
      ++v12;
    while ( *((_WORD *)v11 + v12) );
    v13 = 2 * v12 + 2;
  }
  else
  {
    v11 = &dword_1800DB714;
    v13 = 2;
  }
  v26 = v13;
  v25 = v11;
  v27 = 0;
  v24 = 16;
  v14 = *a6;
  v21 = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (ULONGLONG)off_1801091E8;
  v23 = v14;
  v22 = 8;
  UserData.Size = *(unsigned __int16 *)off_1801091E8;
  v19 = *(unsigned __int16 *)(a2 + 11);
  v18 = a2 + 11;
  UserData.Reserved = 2;
  v20 = 1;
  return EventWriteTransfer(qword_180109200, &EventDescriptor, 0, 0, 9u, &UserData);
}

```

## disassembly

```asm
0x1800555d8  push    rbp
0x1800555da  lea     rbp, [rsp-1Fh]
0x1800555df  sub     rsp, 0F0h
0x1800555e6  mov     rax, cs:__security_cookie
0x1800555ed  xor     rax, rsp
0x1800555f0  mov     [rbp+1Fh+var_10], rax
0x1800555f4  mov     rax, [rbp+1Fh+arg_50]
0x1800555f8  xor     r8d, r8d; ActivityId
0x1800555fb  mov     [rbp+1Fh+var_20], rax
0x1800555ff  mov     rax, [rbp+1Fh+arg_48]
0x180055603  mov     [rbp+1Fh+var_30], rax
0x180055607  mov     rax, [rbp+1Fh+arg_40]
0x18005560b  lea     r10d, [r8+1]
0x18005560f  mov     [rbp+1Fh+var_40], rax
0x180055613  lea     r9d, [r8+2]
0x180055617  mov     rax, [rbp+1Fh+arg_38]
0x18005561b  mov     [rbp+1Fh+var_50], rax
0x18005561f  mov     rax, [rbp+1Fh+arg_30]
0x180055623  mov     [rbp+1Fh+var_18], 4
0x18005562b  mov     [rbp+1Fh+var_28], r10
0x18005562f  mov     [rbp+1Fh+var_38], 4
0x180055637  mov     rcx, [rax]
0x18005563a  mov     [rbp+1Fh+var_48], 4
0x180055642  test    rcx, rcx
0x180055645  jz      short loc_18005565E
0x180055647  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005564b  inc     rax
0x18005564e  cmp     [rcx+rax*2], r8w
0x180055653  jnz     short loc_18005564B
0x180055655  lea     eax, ds:2[rax*2]
0x18005565c  jmp     short loc_180055668
0x18005565e  lea     rcx, dword_1800DB714
0x180055665  mov     eax, r9d
0x180055668  mov     [rbp+1Fh+var_58], eax
0x18005566b  mov     rax, [rbp+1Fh+arg_28]
0x18005566f  mov     [rbp+1Fh+var_60], rcx
0x180055673  mov     [rbp+1Fh+var_54], r8d
0x180055677  mov     [rbp+1Fh+var_68], 10h
0x18005567f  mov     rcx, [rax]
0x180055682  mov     rax, [rbp+1Fh+arg_20]
0x180055686  mov     [rbp+1Fh+var_80], rax
0x18005568a  movzx   eax, byte ptr [rdx]
0x18005568d  shl     eax, 18h
0x180055690  mov     dword ptr [rsp+0F0h+EventDescriptor.Id], eax
0x180055694  movzx   eax, word ptr [rdx+1]
0x180055698  mov     dword ptr [rsp+0F0h+EventDescriptor.Level], eax
0x18005569c  mov     rax, [rdx+3]
0x1800556a0  mov     [rsp+0F0h+EventDescriptor.Keyword], rax
0x1800556a5  mov     rax, cs:off_1801091E8
0x1800556ac  mov     [rsp+0F0h+var_A0.Ptr], rax
0x1800556b1  mov     [rbp+1Fh+var_70], rcx
0x1800556b5  lea     rcx, [rdx+0Bh]
0x1800556b9  mov     [rbp+1Fh+var_78], 8
0x1800556c1  lea     rdx, [rsp+0F0h+EventDescriptor]; EventDescriptor
0x1800556c6  movzx   eax, word ptr [rax]
0x1800556c9  mov     [rbp+1Fh+var_A0.Size], eax
0x1800556cc  movzx   eax, word ptr [rcx]
0x1800556cf  mov     [rbp+1Fh+var_88], eax
0x1800556d2  lea     rax, _TraceLoggingMetadataEnd
0x1800556d9  mov     [rbp+1Fh+var_90], rcx
0x1800556dd  lea     rcx, _TraceLoggingMetadata
0x1800556e4  sub     eax, ecx
0x1800556e6  mov     dword ptr [rbp+1Fh+var_A0.0Ch], r9d
0x1800556ea  mov     [rbp+1Fh+var_84], r10d
0x1800556ee  xor     r9d, r9d; RelatedActivityId
0x1800556f1  mov     [rsp+0F0h+var_C0], eax
0x1800556f5  mov     eax, [rsp+0F0h+var_C0]
0x1800556f9  mov     rcx, cs:qword_180109200; RegHandle
0x180055700  lea     rax, [rsp+0F0h+var_A0]
0x180055705  mov     [rsp+0F0h+UserData], rax; UserData
0x18005570a  mov     [rsp+0F0h+UserDataCount], 9; UserDataCount
0x180055712  call    cs:__imp_EventWriteTransfer
0x180055719  nop     dword ptr [rax+rax+00h]
0x18005571e  mov     rcx, [rbp+1Fh+var_10]
0x180055722  xor     rcx, rsp; StackCookie
0x180055725  call    __security_check_cookie
0x18005572a  add     rsp, 0F0h
0x180055731  pop     rbp
0x180055732  retn
```
