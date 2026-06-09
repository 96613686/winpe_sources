# CRdpIdAdapter::ForwardIoctl(RDPIDD_FILEOBJECT_CONTEXT *,std::span<uchar,-1> const &,std::span<uchar,-1> const &,uint *)

- ea: `0x180016910`
- end: `0x180016a4c`
- name: `?ForwardIoctl@CRdpIdAdapter@@QEAAXPEAURDPIDD_FILEOBJECT_CONTEXT@@AEBV?$span@E$0?0@std@@1PEAI@Z`
- size: `316`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180011088`

## callees

- `0x180001f14`
- `0x18000d614`
- `0x180012b54`
- `0x180016910`
- `0x18001ddf4`
- `0x18003f010`

## string_xrefs

- `0x18001692c`: `Encoding processor is not ready`
- `0x18001698f`: `Forwarding ioctl to encoding dll`

## pseudocode

```c
__int64 __fastcall CRdpIdAdapter::ForwardIoctl(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        _QWORD *a4,
        __int64 a5,
        const char *a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  _QWORD *v9; // rdi
  _DWORD *v14; // rcx
  int v15; // r8d
  int v16; // r9d
  __int64 v17; // rdx
  unsigned int v18; // eax
  const char *v20; // [rsp+50h] [rbp-10h] BYREF
  const char *v21; // [rsp+58h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  int v23; // [rsp+A0h] [rbp+40h] BYREF
  int v24; // [rsp+A8h] [rbp+48h] BYREF
  __int64 v25; // [rsp+B0h] [rbp+50h] BYREF
  const char *v26; // [rsp+B8h] [rbp+58h] BYREF

  v9 = (_QWORD *)(a1 + 560);
  wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<Rdp::Avenc::IEncodingProcessor,wil::err_exception_policy>,0>(
    (_DWORD)retaddr,
    2691,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
    -2147024809,
    a1 + 560);
  v14 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
  if ( *v14 > 5u )
  {
    v25 = *(_QWORD *)(a1 + 520);
    v23 = *(_DWORD *)(a1 + 516);
    v26 = "Forwarding ioctl to encoding dll";
    v20 = "CRdpIdAdapter::ForwardIoctl";
    v24 = 2698;
    v21 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      (_DWORD)v14,
      (unsigned int)&word_18004C88E,
      v15,
      v16,
      (__int64)&v21,
      (__int64)&v24,
      (__int64)&v20,
      (__int64)&v26,
      (__int64)&v23,
      (__int64)&v25);
  }
  v17 = a4[1];
  LOBYTE(v17) = *(_BYTE *)(a2 + 45);
  v18 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _QWORD, _QWORD, __int64))(*(_QWORD *)*v9 + 80LL))(
          *v9,
          v17,
          a3[1],
          *a3,
          a4[1],
          *a4,
          a5);
  return wil::details::in1diag3::Throw_IfFailedMsg(
           retaddr,
           (void *)0xA94,
           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
           (const char *)v18,
           (int)"Failed to forward Ioctl to Avenc",
           a6,
           a7,
           a8,
           a9);
}

```

## disassembly

```asm
0x180016910  push    rbp
0x180016912  push    rbx
0x180016913  push    rsi
0x180016914  push    rdi
0x180016915  push    r12
0x180016917  push    r14
0x180016919  push    r15
0x18001691b  mov     rbp, rsp
0x18001691e  sub     rsp, 60h
0x180016922  lea     rdi, [rcx+230h]
0x180016929  mov     rsi, r9
0x18001692c  lea     rax, aEncodingProces_2; "Encoding processor is not ready"
0x180016933  mov     r14, r8
0x180016936  mov     r15, rdx
0x180016939  mov     [rsp+60h+var_38], rax
0x18001693e  mov     rbx, rcx
0x180016941  mov     [rsp+60h+var_40], rdi
0x180016946  mov     rcx, [rbp+38h]
0x18001694a  lea     r12, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180016951  mov     r8, r12
0x180016954  mov     r9d, 80070057h
0x18001695a  mov     edx, 0A83h
0x18001695f  call    ??$Throw_HrIfNullMsg@V?$com_ptr_t@UIEncodingProcessor@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@$0A@@in1diag3@details@wil@@YAXPEAXIPEBDJAEBV?$com_ptr_t@UIEncodingProcessor@Avenc@Rdp@@Uerr_exception_policy@wil@@@2@1ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<Rdp::Avenc::IEncodingProcessor,wil::err_exception_policy>,0>(void *,uint,char const *,long,wil::com_ptr_t<Rdp::Avenc::IEncodingProcessor,wil::err_exception_policy> const &,char const *,...)
0x180016964  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x180016969  mov     rcx, [rax+8]
0x18001696d  mov     eax, [rcx]
0x18001696f  cmp     eax, 5
0x180016972  jbe     short loc_1800169EB
0x180016974  mov     rax, [rbx+208h]
0x18001697b  lea     rdx, word_18004C88E
0x180016982  mov     [rbp+arg_10], rax
0x180016986  mov     eax, [rbx+204h]
0x18001698c  mov     [rbp+arg_0], eax
0x18001698f  lea     rax, aForwardingIoct; "Forwarding ioctl to encoding dll"
0x180016996  mov     [rbp+arg_18], rax
0x18001699a  lea     rax, aCrdpidadapterF_0; "CRdpIdAdapter::ForwardIoctl"
0x1800169a1  mov     [rbp+var_10], rax
0x1800169a5  lea     rax, [rbp+arg_10]
0x1800169a9  mov     [rsp+60h+var_18], rax
0x1800169ae  lea     rax, [rbp+arg_0]
0x1800169b2  mov     [rsp+60h+var_20], rax
0x1800169b7  lea     rax, [rbp+arg_18]
0x1800169bb  mov     [rsp+60h+var_28], rax
0x1800169c0  lea     rax, [rbp+var_10]
0x1800169c4  mov     [rsp+60h+var_30], rax
0x1800169c9  lea     rax, [rbp+arg_8]
0x1800169cd  mov     [rsp+60h+var_38], rax
0x1800169d2  lea     rax, [rbp+var_8]
0x1800169d6  mov     [rsp+60h+var_40], rax
0x1800169db  mov     [rbp+arg_8], 0A8Ah
0x1800169e2  mov     [rbp+var_8], r12
0x1800169e6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1800169eb  mov     rcx, [rdi]
0x1800169ee  mov     rdx, [rbp+arg_20]
0x1800169f2  mov     r9, [r14]
0x1800169f5  mov     r8, [r14+8]
0x1800169f9  mov     rax, [rcx]
0x1800169fc  mov     [rsp+60h+var_30], rdx
0x180016a01  mov     rdx, [rsi]
0x180016a04  mov     [rsp+60h+var_38], rdx
0x180016a09  mov     rdx, [rsi+8]
0x180016a0d  mov     rax, [rax+50h]
0x180016a11  mov     [rsp+60h+var_40], rdx
0x180016a16  mov     dl, [r15+2Dh]
0x180016a1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a1f  mov     rcx, [rbp+38h]; this
0x180016a23  lea     rdx, aFailedToForwar; "Failed to forward Ioctl to Avenc"
0x180016a2a  mov     [rbp+arg_20], rdx
0x180016a2e  mov     r9d, eax; char *
0x180016a31  mov     edx, 0A94h; void *
0x180016a36  mov     r8, r12; unsigned int
0x180016a39  add     rsp, 60h
0x180016a3d  pop     r15
0x180016a3f  pop     r14
0x180016a41  pop     r12
0x180016a43  pop     rdi
0x180016a44  pop     rsi
0x180016a45  pop     rbx
0x180016a46  pop     rbp
0x180016a47  jmp     ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
```
