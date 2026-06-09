# RdpIdEvtRequestImpersonate(WDFREQUEST__ *,void *)

- ea: `0x1800102b0`
- end: `0x180010438`
- name: `?RdpIdEvtRequestImpersonate@@YAXPEAUWDFREQUEST__@@PEAX@Z`
- size: `392`
- prototype: `void __fastcall(struct WDFREQUEST__ *, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x180001010`
- `0x18000d614`
- `0x18000e780`
- `0x18000e84c`
- `0x1800102b0`
- `0x18003f010`

## string_xrefs

- `0x1800103d2`: `Impersonate Irp requestor`
- `0x1800103dd`: `RdpIdEvtRequestImpersonate`

## pseudocode

```c
void __fastcall RdpIdEvtRequestImpersonate(struct WDFREQUEST__ *a1, void *a2)
{
  __int64 v3; // rax
  __int64 v4; // rdx
  bool *v5; // rdi
  _DWORD *v6; // rcx
  int v7; // r8d
  int v8; // r9d
  const char *v9; // [rsp+50h] [rbp-30h] BYREF
  const char *v10; // [rsp+58h] [rbp-28h] BYREF
  int v11; // [rsp+60h] [rbp-20h] BYREF
  int v12; // [rsp+64h] [rbp-1Ch] BYREF
  int v13; // [rsp+68h] [rbp-18h] BYREF
  int v14; // [rsp+6Ch] [rbp-14h] BYREF
  int v15[4]; // [rsp+70h] [rbp-10h] BYREF
  int v16; // [rsp+A8h] [rbp+28h] BYREF
  int v17; // [rsp+B0h] [rbp+30h] BYREF
  __int16 v18; // [rsp+B4h] [rbp+34h]
  const char *v19; // [rsp+B8h] [rbp+38h] BYREF

  v3 = (*(__int64 (__fastcall **)(__int64, struct WDFREQUEST__ *))(WdfFunctions_02025 + 1376))(WdfDriverGlobals, a1);
  v5 = (bool *)((*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(WdfFunctions_02025 + 984))(
                  WdfDriverGlobals,
                  v3,
                  off_180057020)
              + 45);
  if ( *(_BYTE *)(*(_QWORD *)a2 + 592LL) )
  {
    LODWORD(v19) = 0;
    v16 = 544;
    v17 = 32;
    WORD2(v19) = 1280;
    wil::test_token_membership_nothrow<unsigned long,unsigned long>(v5, v4, (int *)&v19, &v17, &v16);
  }
  else
  {
    v17 = 0;
    v11 = 446051430;
    v12 = 1559341753;
    v13 = -133025767;
    v14 = 1950928533;
    v15[0] = 810483104;
    v16 = 80;
    v18 = 1280;
    wil::test_token_membership_nothrow<unsigned long,unsigned long &,unsigned long &,unsigned long &,unsigned long &,unsigned long &>(
      v5,
      v4,
      &v17,
      &v16,
      &v11,
      &v12,
      &v13,
      &v14,
      v15);
  }
  v6 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
  if ( *v6 > 4u )
  {
    v16 = *v5;
    v19 = "Impersonate Irp requestor";
    v9 = "RdpIdEvtRequestImpersonate";
    v10 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\device.cpp";
    v17 = 434;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (_DWORD)v6,
      (unsigned int)word_18004C3DA,
      v7,
      v8,
      (__int64)&v10,
      (__int64)&v17,
      (__int64)&v9,
      (__int64)&v19,
      (__int64)&v16);
  }
}

```

## disassembly

```asm
0x1800102b0  push    rbp
0x1800102b2  push    rbx
0x1800102b3  push    rdi
0x1800102b4  mov     rbp, rsp
0x1800102b7  sub     rsp, 80h
0x1800102be  mov     rax, cs:WdfFunctions_02025
0x1800102c5  mov     rbx, rdx
0x1800102c8  mov     rdx, rcx
0x1800102cb  mov     rcx, cs:WdfDriverGlobals
0x1800102d2  mov     rax, [rax+560h]
0x1800102d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102de  mov     rcx, cs:WdfFunctions_02025
0x1800102e5  mov     rdx, rax
0x1800102e8  mov     r8, cs:off_180057020
0x1800102ef  mov     rax, [rcx+3D8h]
0x1800102f6  mov     rcx, cs:WdfDriverGlobals
0x1800102fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010302  xor     ecx, ecx
0x180010304  lea     rdi, [rax+2Dh]
0x180010308  mov     rax, [rbx]
0x18001030b  cmp     [rax+250h], cl
0x180010311  jz      short loc_180010345
0x180010313  mov     dword ptr [rbp+arg_18], ecx
0x180010316  lea     rax, [rbp+arg_8]
0x18001031a  mov     rcx, rdi
0x18001031d  mov     [rsp+80h+var_60], rax
0x180010322  lea     r9, [rbp+arg_10]
0x180010326  mov     [rbp+arg_8], 220h
0x18001032d  lea     r8, [rbp+arg_18]
0x180010331  mov     [rbp+arg_10], 20h ; ' '
0x180010338  mov     word ptr [rbp+arg_18+4], 500h
0x18001033e  call    ??$test_token_membership_nothrow@KK@wil@@YAJPEA_NPEAXAEBU_SID_IDENTIFIER_AUTHORITY@@$$QEAK3@Z; wil::test_token_membership_nothrow<ulong,ulong>(bool *,void *,_SID_IDENTIFIER_AUTHORITY const &,ulong &&,ulong &&)
0x180010343  jmp     short loc_1800103B5
0x180010345  lea     rax, [rbp+var_10]
0x180010349  mov     [rbp+arg_10], ecx
0x18001034c  mov     [rsp+80h+var_40], rax
0x180010351  lea     r9, [rbp+arg_8]
0x180010355  lea     rax, [rbp+var_14]
0x180010359  mov     [rbp+var_20], 1A963466h
0x180010360  mov     [rsp+80h+var_48], rax
0x180010365  lea     r8, [rbp+arg_10]
0x180010369  lea     rax, [rbp+var_18]
0x18001036d  mov     [rbp+var_1C], 5CF1AAB9h
0x180010374  mov     [rsp+80h+var_50], rax
0x180010379  mov     rcx, rdi
0x18001037c  lea     rax, [rbp+var_1C]
0x180010380  mov     [rbp+var_18], 0F8123019h
0x180010387  mov     [rsp+80h+var_58], rax
0x18001038c  lea     rax, [rbp+var_20]
0x180010390  mov     [rsp+80h+var_60], rax
0x180010395  mov     [rbp+var_14], 7448CE95h
0x18001039c  mov     [rbp+var_10], 304EFDA0h
0x1800103a3  mov     [rbp+arg_8], 50h ; 'P'
0x1800103aa  mov     [rbp+arg_14], 500h
0x1800103b0  call    ??$test_token_membership_nothrow@KAEAKAEAKAEAKAEAKAEAK@wil@@YAJPEA_NPEAXAEBU_SID_IDENTIFIER_AUTHORITY@@$$QEAKAEAK4444@Z; wil::test_token_membership_nothrow<ulong,ulong &,ulong &,ulong &,ulong &,ulong &>(bool *,void *,_SID_IDENTIFIER_AUTHORITY const &,ulong &&,ulong &,ulong &,ulong &,ulong &,ulong &)
0x1800103b5  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x1800103ba  mov     rcx, [rax+8]
0x1800103be  mov     eax, [rcx]
0x1800103c0  cmp     eax, 4
0x1800103c3  jbe     short loc_18001042C
0x1800103c5  movzx   eax, byte ptr [rdi]
0x1800103c8  lea     rdx, word_18004C3DA
0x1800103cf  mov     [rbp+arg_8], eax
0x1800103d2  lea     rax, aImpersonateIrp; "Impersonate Irp requestor"
0x1800103d9  mov     [rbp+arg_18], rax
0x1800103dd  lea     rax, aRdpidevtreques; "RdpIdEvtRequestImpersonate"
0x1800103e4  mov     [rbp+var_30], rax
0x1800103e8  lea     rax, aOnecoreuapTerm_5; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x1800103ef  mov     [rbp+var_28], rax
0x1800103f3  lea     rax, [rbp+arg_8]
0x1800103f7  mov     [rsp+80h+var_40], rax
0x1800103fc  lea     rax, [rbp+arg_18]
0x180010400  mov     [rsp+80h+var_48], rax
0x180010405  lea     rax, [rbp+var_30]
0x180010409  mov     [rsp+80h+var_50], rax
0x18001040e  lea     rax, [rbp+arg_10]
0x180010412  mov     [rsp+80h+var_58], rax
0x180010417  lea     rax, [rbp+var_28]
0x18001041b  mov     [rsp+80h+var_60], rax
0x180010420  mov     [rbp+arg_10], 1B2h
0x180010427  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001042c  add     rsp, 80h
0x180010433  pop     rdi
0x180010434  pop     rbx
0x180010435  pop     rbp
0x180010436  retn
```
