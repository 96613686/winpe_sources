# CMidi2LoopbackMidiBidi::Callback(__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004,void *,uint,__int64,__int64)

- ea: `0x180010a90`
- end: `0x180010b6a`
- name: `?Callback@CMidi2LoopbackMidiBidi@@UEAAJW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@PEAXI_J2@Z`
- size: `218`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x1800016dc`
- `0x180008f64`
- `0x18000add8`
- `0x180010a90`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall CMidi2LoopbackMidiBidi::Callback(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5)
{
  _DWORD *v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rdx
  unsigned int v13; // ebx
  __int64 v15; // rcx
  int v16; // [rsp+20h] [rbp-58h]
  int v17[2]; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  __int64 v19; // [rsp+90h] [rbp+18h] BYREF

  v9 = (_DWORD *)*((_QWORD *)MidiDiagnosticsTransportTelemetryProvider::Instance() + 1);
  if ( *v9 > 4u )
  {
    v19 = a1 - 8;
    *(_QWORD *)v17 = "CMidi2LoopbackMidiBidi::Callback";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (__int64)v9,
      (unsigned __int8 *)byte_180016E09,
      v10,
      v11,
      (const unsigned __int16 **)v17,
      (__int64)&v19);
  }
  if ( !a3 )
  {
    v12 = 183;
LABEL_5:
    v13 = -2147024809;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"avcore\\midi2\\transport\\diagnosticstransport\\midi2.loopbackmidibidi.cpp",
      (const char *)v13,
      v16);
    return v13;
  }
  v15 = *(_QWORD *)(a1 + 16);
  if ( !v15 )
  {
    v13 = -2147467261;
    v12 = 184;
    goto LABEL_6;
  }
  if ( a4 < 4 )
  {
    v12 = 185;
    goto LABEL_5;
  }
  return (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, __int64, _QWORD))(*(_QWORD *)v15 + 24LL))(
           v15,
           a2,
           a3,
           a4,
           a5,
           *(_QWORD *)(a1 + 24));
}

```

## disassembly

```asm
0x180010a90  push    rbx
0x180010a92  push    rbp
0x180010a93  push    rsi
0x180010a94  push    rdi
0x180010a95  sub     rsp, 58h
0x180010a99  mov     edi, r9d
0x180010a9c  mov     rsi, r8
0x180010a9f  mov     ebp, edx
0x180010aa1  mov     rbx, rcx
0x180010aa4  call    ?Instance@MidiDiagnosticsTransportTelemetryProvider@@KAPEAV1@XZ; MidiDiagnosticsTransportTelemetryProvider::Instance(void)
0x180010aa9  mov     rcx, [rax+8]
0x180010aad  mov     eax, [rcx]
0x180010aaf  cmp     eax, 4
0x180010ab2  jbe     short loc_180010AEF
0x180010ab4  lea     rax, [rbx-8]
0x180010ab8  mov     [rsp+78h+arg_10], rax
0x180010ac0  lea     rdx, byte_180016E09
0x180010ac7  lea     rax, aCmidi2loopback; "CMidi2LoopbackMidiBidi::Callback"
0x180010ace  mov     qword ptr [rsp+78h+var_38], rax
0x180010ad3  lea     rax, [rsp+78h+arg_10]
0x180010adb  mov     [rsp+78h+var_50], rax
0x180010ae0  lea     rax, [rsp+78h+var_38]
0x180010ae5  mov     qword ptr [rsp+78h+var_58], rax; int
0x180010aea  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180010aef  test    rsi, rsi
0x180010af2  jnz     short loc_180010B16
0x180010af4  mov     edx, 0B7h; void *
0x180010af9  mov     ebx, 80070057h
0x180010afe  mov     rcx, [rsp+78h]; this
0x180010b03  lea     r8, aAvcoreMidi2Tra_1; "avcore\\midi2\\transport\\diagnosticstr"...
0x180010b0a  mov     r9d, ebx; char *
0x180010b0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010b12  mov     eax, ebx
0x180010b14  jmp     short loc_180010B61
0x180010b16  mov     rcx, [rbx+10h]
0x180010b1a  test    rcx, rcx
0x180010b1d  jnz     short loc_180010B2B
0x180010b1f  mov     ebx, 80004003h
0x180010b24  mov     edx, 0B8h
0x180010b29  jmp     short loc_180010AFE
0x180010b2b  cmp     edi, 4
0x180010b2e  jnb     short loc_180010B37
0x180010b30  mov     edx, 0B9h
0x180010b35  jmp     short loc_180010AF9
0x180010b37  mov     rdx, [rbx+18h]
0x180010b3b  mov     r9d, edi
0x180010b3e  mov     rax, [rcx]
0x180010b41  mov     r8, rsi
0x180010b44  mov     [rsp+78h+var_50], rdx
0x180010b49  mov     rdx, [rsp+78h+arg_20]
0x180010b51  mov     qword ptr [rsp+78h+var_58], rdx
0x180010b56  mov     edx, ebp
0x180010b58  mov     rax, [rax+18h]
0x180010b5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b61  add     rsp, 58h
0x180010b65  pop     rdi
0x180010b66  pop     rsi
0x180010b67  pop     rbp
0x180010b68  pop     rbx
0x180010b69  retn
```
