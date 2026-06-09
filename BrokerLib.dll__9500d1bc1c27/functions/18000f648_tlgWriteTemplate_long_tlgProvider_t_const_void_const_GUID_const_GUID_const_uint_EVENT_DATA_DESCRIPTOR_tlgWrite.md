# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x18000f648`
- end: `0x18000f78e`
- name: `??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@4444@Z`
- size: `326`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180017a9c`
- `0x1800188c0`

## callees

- `0x180015af0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000f773`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000f773`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 *a5,
        __int64 *a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12)
{
  __int64 v12; // rcx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-B1h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-99h] BYREF
  unsigned __int8 *v16; // [rsp+60h] [rbp-89h]
  int v17; // [rsp+68h] [rbp-81h]
  int v18; // [rsp+6Ch] [rbp-7Dh]
  __int64 v19; // [rsp+70h] [rbp-79h]
  __int64 v20; // [rsp+78h] [rbp-71h]
  __int64 v21; // [rsp+80h] [rbp-69h]
  __int64 v22; // [rsp+88h] [rbp-61h]
  __int64 v23; // [rsp+90h] [rbp-59h]
  __int64 v24; // [rsp+98h] [rbp-51h]
  __int64 v25; // [rsp+A0h] [rbp-49h]
  __int64 v26; // [rsp+A8h] [rbp-41h]
  __int64 v27; // [rsp+B0h] [rbp-39h]
  __int64 v28; // [rsp+B8h] [rbp-31h]
  __int64 v29; // [rsp+C0h] [rbp-29h]
  __int64 v30; // [rsp+C8h] [rbp-21h]
  __int64 v31; // [rsp+D0h] [rbp-19h]
  __int64 v32; // [rsp+D8h] [rbp-11h]
  __int64 v33; // [rsp+E0h] [rbp-9h]
  __int64 v34; // [rsp+E8h] [rbp-1h]

  v33 = a12;
  v31 = a11;
  v29 = a10;
  v27 = a9;
  v25 = a8;
  v23 = a7;
  v34 = 4;
  v32 = 4;
  v30 = 4;
  v21 = *a6;
  v28 = 4;
  v26 = 8;
  v12 = *a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (ULONGLONG)off_180028008;
  v19 = v12;
  v24 = 4;
  v22 = 16;
  v20 = 16;
  UserData.Size = *(unsigned __int16 *)off_180028008;
  v17 = *(unsigned __int16 *)(a2 + 11);
  v16 = a2 + 11;
  UserData.Reserved = 2;
  v18 = 1;
  return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 0xAu, &UserData);
}

```

## disassembly

```asm
0x18000f648  push    rbp
0x18000f64a  lea     rbp, [rsp-17h]
0x18000f64f  sub     rsp, 100h
0x18000f656  mov     rax, cs:__security_cookie
0x18000f65d  xor     rax, rsp
0x18000f660  mov     [rbp+17h+var_10], rax
0x18000f664  mov     rax, [rbp+17h+arg_58]
0x18000f668  xor     r9d, r9d; RelatedActivityId
0x18000f66b  mov     [rbp+17h+var_20], rax
0x18000f66f  xor     r8d, r8d; ActivityId
0x18000f672  mov     rax, [rbp+17h+arg_50]
0x18000f676  mov     [rbp+17h+var_30], rax
0x18000f67a  mov     rax, [rbp+17h+arg_48]
0x18000f67e  mov     [rbp+17h+var_40], rax
0x18000f682  mov     rax, [rbp+17h+arg_40]
0x18000f686  mov     [rbp+17h+var_50], rax
0x18000f68a  mov     rax, [rbp+17h+arg_38]
0x18000f68e  mov     [rbp+17h+var_60], rax
0x18000f692  mov     rax, [rbp+17h+arg_30]
0x18000f696  mov     [rbp+17h+var_70], rax
0x18000f69a  mov     rax, [rbp+17h+arg_28]
0x18000f69e  mov     [rbp+17h+var_18], 4
0x18000f6a6  mov     [rbp+17h+var_28], 4
0x18000f6ae  mov     [rbp+17h+var_38], 4
0x18000f6b6  mov     rcx, [rax]
0x18000f6b9  mov     rax, [rbp+17h+arg_20]
0x18000f6bd  mov     [rbp+17h+var_80], rcx
0x18000f6c1  mov     [rbp+17h+var_48], 4
0x18000f6c9  mov     [rbp+17h+var_58], 8
0x18000f6d1  mov     rcx, [rax]
0x18000f6d4  movzx   eax, byte ptr [rdx]
0x18000f6d7  shl     eax, 18h
0x18000f6da  mov     dword ptr [rsp+100h+EventDescriptor.Id], eax
0x18000f6de  movzx   eax, word ptr [rdx+1]
0x18000f6e2  mov     dword ptr [rsp+100h+EventDescriptor.Level], eax
0x18000f6e6  mov     rax, [rdx+3]
0x18000f6ea  mov     [rsp+100h+EventDescriptor.Keyword], rax
0x18000f6ef  mov     rax, cs:off_180028008
0x18000f6f6  mov     [rsp+100h+var_B0.Ptr], rax
0x18000f6fb  mov     [rbp+17h+var_90], rcx
0x18000f6ff  lea     rcx, [rdx+0Bh]
0x18000f703  mov     [rbp+17h+var_68], 4
0x18000f70b  lea     rdx, [rsp+100h+EventDescriptor]; EventDescriptor
0x18000f710  mov     [rbp+17h+var_78], 10h
0x18000f718  mov     [rbp+17h+var_88], 10h
0x18000f720  movzx   eax, word ptr [rax]
0x18000f723  mov     [rsp+100h+var_B0.Size], eax
0x18000f727  movzx   eax, word ptr [rcx]
0x18000f72a  mov     [rsp+100h+var_98], eax
0x18000f72e  lea     rax, _TraceLoggingMetadataEnd
0x18000f735  mov     [rsp+100h+var_A0], rcx
0x18000f73a  lea     rcx, _TraceLoggingMetadata
0x18000f741  sub     eax, ecx
0x18000f743  mov     dword ptr [rsp+100h+var_B0.0Ch], 2
0x18000f74b  mov     [rbp+17h+var_94], 1
0x18000f752  mov     [rsp+100h+var_D0], eax
0x18000f756  mov     eax, [rsp+100h+var_D0]
0x18000f75a  mov     rcx, cs:RegHandle; RegHandle
0x18000f761  lea     rax, [rsp+100h+var_B0]
0x18000f766  mov     [rsp+100h+UserData], rax; UserData
0x18000f76b  mov     [rsp+100h+UserDataCount], 0Ah; UserDataCount
0x18000f773  call    cs:__imp_EventWriteTransfer
0x18000f779  mov     rcx, [rbp+17h+var_10]
0x18000f77d  xor     rcx, rsp; StackCookie
0x18000f780  call    __security_check_cookie
0x18000f785  add     rsp, 100h
0x18000f78c  pop     rbp
0x18000f78d  retn
```
