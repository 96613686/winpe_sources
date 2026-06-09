# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180017430`
- end: `0x1800175a1`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U1@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@43AEBU?$_tlgWrapSz@G@@5@Z`
- size: `369`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, __int64, __int64, __int64, __int64, int **, int **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180018220`

## callees

- `0x180017430`
- `0x180026200`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180017584`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180017584`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        const GUID *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        int **a9,
        int **a10)
{
  __int64 v12; // rcx
  int *v15; // r8
  __int64 v16; // rax
  int v17; // eax
  int *v18; // rdx
  int v19; // ecx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-91h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-79h] BYREF
  unsigned __int8 *v23; // [rsp+60h] [rbp-69h]
  int v24; // [rsp+68h] [rbp-61h]
  int v25; // [rsp+6Ch] [rbp-5Dh]
  __int64 v26; // [rsp+70h] [rbp-59h]
  __int64 v27; // [rsp+78h] [rbp-51h]
  __int64 v28; // [rsp+80h] [rbp-49h]
  __int64 v29; // [rsp+88h] [rbp-41h]
  __int64 v30; // [rsp+90h] [rbp-39h]
  __int64 v31; // [rsp+98h] [rbp-31h]
  __int64 v32; // [rsp+A0h] [rbp-29h]
  __int64 v33; // [rsp+A8h] [rbp-21h]
  int *v34; // [rsp+B0h] [rbp-19h]
  int v35; // [rsp+B8h] [rbp-11h]
  int v36; // [rsp+BCh] [rbp-Dh]
  int *v37; // [rsp+C0h] [rbp-9h]
  int v38; // [rsp+C8h] [rbp-1h]
  int v39; // [rsp+CCh] [rbp+3h]

  v12 = -1;
  v15 = *a10;
  if ( *a10 )
  {
    v16 = -1;
    do
      ++v16;
    while ( *((_WORD *)v15 + v16) );
    v17 = 2 * v16 + 2;
  }
  else
  {
    v15 = &dword_18003A074;
    v17 = 2;
  }
  v38 = v17;
  v37 = v15;
  v39 = 0;
  v18 = *a9;
  if ( *a9 )
  {
    do
      ++v12;
    while ( *((_WORD *)v18 + v12) );
    v19 = 2 * v12 + 2;
  }
  else
  {
    v18 = &dword_18003A074;
    v19 = 2;
  }
  v32 = a8;
  v30 = a7;
  v28 = a6;
  v26 = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = *(_QWORD *)(a1 + 8);
  v35 = v19;
  v34 = v18;
  v36 = 0;
  v33 = 8;
  v27 = 8;
  v31 = 4;
  v29 = 4;
  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
  v24 = *(unsigned __int16 *)(a2 + 11);
  v23 = a2 + 11;
  UserData.Reserved = 2;
  v25 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, a3, a4, 8u, &UserData);
}

```

## disassembly

```asm
0x180017430  push    rbp
0x180017432  push    rbx
0x180017433  push    rdi
0x180017434  lea     rbp, [rsp-17h]
0x180017439  sub     rsp, 0E0h
0x180017440  mov     rax, cs:__security_cookie
0x180017447  xor     rax, rsp
0x18001744a  mov     [rbp+27h+var_20], rax
0x18001744e  mov     rax, [rbp+27h+arg_48]
0x180017452  mov     r11, r8
0x180017455  mov     r10, rcx
0x180017458  xor     edi, edi
0x18001745a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001745e  mov     rbx, r9
0x180017461  mov     r9, rdx
0x180017464  mov     r8, [rax]
0x180017467  test    r8, r8
0x18001746a  jz      short loc_180017482
0x18001746c  mov     rax, rcx
0x18001746f  inc     rax
0x180017472  cmp     [r8+rax*2], di
0x180017477  jnz     short loc_18001746F
0x180017479  lea     eax, ds:2[rax*2]
0x180017480  jmp     short loc_18001748E
0x180017482  lea     r8, dword_18003A074
0x180017489  mov     eax, 2
0x18001748e  mov     [rbp+27h+var_28], eax
0x180017491  mov     rax, [rbp+27h+arg_40]
0x180017495  mov     [rbp+27h+var_30], r8
0x180017499  mov     [rbp+27h+var_24], edi
0x18001749c  mov     rdx, [rax]
0x18001749f  test    rdx, rdx
0x1800174a2  jz      short loc_1800174B6
0x1800174a4  inc     rcx
0x1800174a7  cmp     [rdx+rcx*2], di
0x1800174ab  jnz     short loc_1800174A4
0x1800174ad  lea     ecx, ds:2[rcx*2]
0x1800174b4  jmp     short loc_1800174C2
0x1800174b6  lea     rdx, dword_18003A074
0x1800174bd  mov     ecx, 2
0x1800174c2  mov     rax, [rbp+27h+arg_38]
0x1800174c6  mov     r8, r11; ActivityId
0x1800174c9  mov     [rbp+27h+var_50], rax
0x1800174cd  mov     rax, [rbp+27h+arg_30]
0x1800174d1  mov     [rbp+27h+var_60], rax
0x1800174d5  mov     rax, [rbp+27h+arg_28]
0x1800174d9  mov     [rbp+27h+var_70], rax
0x1800174dd  mov     rax, [rbp+27h+arg_20]
0x1800174e1  mov     [rbp+27h+var_80], rax
0x1800174e5  movzx   eax, byte ptr [r9]
0x1800174e9  shl     eax, 18h
0x1800174ec  mov     dword ptr [rsp+0F0h+EventDescriptor.Id], eax
0x1800174f0  movzx   eax, word ptr [r9+1]
0x1800174f5  mov     dword ptr [rsp+0F0h+EventDescriptor.Level], eax
0x1800174f9  mov     rax, [r9+3]
0x1800174fd  mov     [rsp+0F0h+EventDescriptor.Keyword], rax
0x180017502  mov     rax, [r10+8]
0x180017506  mov     [rbp+27h+var_A0.Ptr], rax
0x18001750a  mov     [rbp+27h+var_38], ecx
0x18001750d  lea     rcx, [r9+0Bh]
0x180017511  mov     [rbp+27h+var_40], rdx
0x180017515  mov     r9, rbx; RelatedActivityId
0x180017518  mov     edx, 8
0x18001751d  mov     [rbp+27h+var_34], edi
0x180017520  mov     [rbp+27h+var_48], rdx
0x180017524  mov     [rbp+27h+var_78], rdx
0x180017528  mov     [rbp+27h+var_58], 4
0x180017530  mov     [rbp+27h+var_68], 4
0x180017538  movzx   eax, word ptr [rax]
0x18001753b  mov     [rbp+27h+var_A0.Size], eax
0x18001753e  movzx   eax, word ptr [rcx]
0x180017541  mov     [rbp+27h+var_88], eax
0x180017544  lea     rax, _TraceLoggingMetadataEnd
0x18001754b  mov     [rbp+27h+var_90], rcx
0x18001754f  lea     rcx, _TraceLoggingMetadata
0x180017556  sub     eax, ecx
0x180017558  mov     dword ptr [rbp+27h+var_A0.0Ch], 2
0x18001755f  mov     [rbp+27h+var_84], 1
0x180017566  mov     [rsp+0F0h+var_C0], eax
0x18001756a  mov     eax, [rsp+0F0h+var_C0]
0x18001756e  mov     rcx, [r10+20h]; RegHandle
0x180017572  lea     rax, [rbp+27h+var_A0]
0x180017576  mov     [rsp+0F0h+UserData], rax; UserData
0x18001757b  mov     [rsp+0F0h+UserDataCount], edx; UserDataCount
0x18001757f  lea     rdx, [rsp+0F0h+EventDescriptor]; EventDescriptor
0x180017584  call    cs:__imp_EventWriteTransfer
0x18001758a  mov     rcx, [rbp+27h+var_20]
0x18001758e  xor     rcx, rsp; StackCookie
0x180017591  call    __security_check_cookie
0x180017596  add     rsp, 0E0h
0x18001759d  pop     rdi
0x18001759e  pop     rbx
0x18001759f  pop     rbp
0x1800175a0  retn
```
