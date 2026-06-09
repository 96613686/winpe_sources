# CRdpIdMonitor::ProcessMonitorSurfaceUpdate(uint,uint,std::span<uchar,-1> const &)

- ea: `0x180025c90`
- end: `0x180025f20`
- name: `?ProcessMonitorSurfaceUpdate@CRdpIdMonitor@@QEAAXIIAEBV?$span@E$0?0@std@@@Z`
- size: `656`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001a5c0`

## callees

- `0x180001bc4`
- `0x18000d614`
- `0x18000ead8`
- `0x18001cd04`
- `0x18001dd70`
- `0x18001ddf4`
- `0x180022f84`
- `0x1800232b4`
- `0x180025c90`
- `0x18003f010`

## string_xrefs

- `0x180025d78`: `Failed to create RAIL frame processor`
- `0x180025e85`: `Failed to update RAIL secure desktop`
- `0x180025e90`: `CRdpIdMonitor::ProcessMonitorSurfaceUpdate`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CRdpIdMonitor::ProcessMonitorSurfaceUpdate(__int64 a1, unsigned int a2, unsigned int a3, _QWORD *a4)
{
  unsigned __int64 v8; // rax
  unsigned int v9; // ebx
  unsigned __int64 v10; // rcx
  char v11; // al
  __int64 *v12; // rcx
  __int64 v13; // rax
  unsigned int v14; // eax
  unsigned int v15; // eax
  _DWORD *v16; // r8
  int v17; // r9d
  char *v19; // [rsp+28h] [rbp-48h]
  char *v20; // [rsp+28h] [rbp-48h]
  const char *v21; // [rsp+30h] [rbp-40h]
  const char *v22; // [rsp+30h] [rbp-40h]
  __int64 v23; // [rsp+50h] [rbp-20h] BYREF
  const char *v24; // [rsp+58h] [rbp-18h] BYREF
  const char *v25; // [rsp+60h] [rbp-10h] BYREF
  const char *v26; // [rsp+68h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  __int64 v28; // [rsp+B0h] [rbp+40h] BYREF
  int v29; // [rsp+B8h] [rbp+48h] BYREF
  int v30; // [rsp+C8h] [rbp+58h] BYREF

  v23 = 0;
  v8 = 4LL * a2;
  v9 = 0;
  if ( v8 > 0xFFFFFFFF )
  {
    v11 = 1;
  }
  else
  {
    v10 = a3 * (unsigned __int64)(unsigned int)v8;
    if ( v10 <= 0xFFFFFFFF )
      v9 = a3 * v8;
    v11 = v10 > 0xFFFFFFFF;
  }
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x63E,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)0x80070216LL,
    v11,
    (bool)"Width and Height are out of range",
    v21);
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x644,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)0x80070057LL,
    (unsigned __int64)v9 > a4[1],
    (bool)"Surface array is out of boundary",
    v22);
  if ( *(_QWORD *)(a1 + 304) )
  {
    v23 = 0;
    wil::com_ptr_t<Rdp::Avenc::IFrameProcessor,wil::err_exception_policy>::copy_to<Rdp::Avenc::Umrdp::IUmrdpFrameProcessorRailPrivate>(
      a1 + 304,
      &v23);
  }
  else
  {
    v28 = 0;
    v12 = *(__int64 **)(a1 + 312);
    v13 = *v12;
    v28 = 0;
    v14 = (*(__int64 (__fastcall **)(__int64 *, __int64 *, _QWORD))(v13 + 56))(v12, &v28, 0);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x650,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
      (const char *)v14,
      (int)"Failed to create RAIL frame processor",
      v19);
    wil::com_ptr_t<Rdp::Avenc::IFrameProcessor,wil::err_exception_policy>::operator=<Rdp::Avenc::ICpuFrameProcessor,wil::err_exception_policy,void>(
      a1 + 304,
      &v28);
    v23 = 0;
    wil::com_ptr_t<Rdp::Avenc::IFrameProcessor,wil::err_exception_policy>::copy_to<Rdp::Avenc::Umrdp::IUmrdpFrameProcessorRailPrivate>(
      a1 + 304,
      &v23);
    v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 24LL))(v23);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x659,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
      (const char *)v15,
      (int)"Failed to start RAIL frame processor",
      v20);
    wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(&v28);
  }
  if ( (*(int (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v23 + 32LL))(v23, a2, a3, a4[1], *a4) < 0 )
  {
    v16 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
    if ( *v16 > 2u )
    {
      v29 = *(_DWORD *)(*(_QWORD *)(a1 + 232) + 516LL);
      LODWORD(v28) = *(_DWORD *)(a1 + 280);
      v24 = "Failed to update RAIL secure desktop";
      v25 = "CRdpIdMonitor::ProcessMonitorSurfaceUpdate";
      v30 = 1643;
      v26 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v16,
        (unsigned int)byte_18004E56B,
        (_DWORD)v16,
        v17,
        (__int64)&v26,
        (__int64)&v30,
        (__int64)&v25,
        (__int64)&v24,
        (__int64)&v28,
        (__int64)&v29);
    }
    CRdpIdAdapter::ReportCriticalError(*(_QWORD *)(a1 + 232), 2, 1, 2147500037LL);
  }
  return wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(&v23);
}

```

## disassembly

```asm
0x180025c90  push    rbp
0x180025c92  push    rbx
0x180025c93  push    rsi
0x180025c94  push    rdi
0x180025c95  push    r13
0x180025c97  push    r14
0x180025c99  push    r15
0x180025c9b  mov     rbp, rsp
0x180025c9e  sub     rsp, 70h
0x180025ca2  mov     rsi, r9
0x180025ca5  mov     r15d, r8d
0x180025ca8  mov     r14d, edx
0x180025cab  mov     rdi, rcx
0x180025cae  mov     [rbp+var_20], 0
0x180025cb6  mov     eax, edx
0x180025cb8  shl     rax, 2
0x180025cbc  mov     edx, 0FFFFFFFFh
0x180025cc1  xor     ebx, ebx
0x180025cc3  cmp     rax, rdx
0x180025cc6  ja      short loc_180025CD9
0x180025cc8  mov     ecx, eax
0x180025cca  imul    rcx, r15
0x180025cce  cmp     rcx, rdx
0x180025cd1  cmovbe  ebx, ecx
0x180025cd4  setnbe  al
0x180025cd7  jmp     short loc_180025CDB
0x180025cd9  mov     al, 1
0x180025cdb  mov     rcx, [rbp+38h]; this
0x180025cdf  lea     rdx, aWidthAndHeight; "Width and Height are out of range"
0x180025ce6  mov     [rsp+70h+var_48], rdx; bool
0x180025ceb  mov     [rsp+70h+var_50], al; char
0x180025cef  mov     r9d, 80070216h; char *
0x180025cf5  lea     r13, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180025cfc  mov     r8, r13; unsigned int
0x180025cff  mov     edx, 63Eh; void *
0x180025d04  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180025d09  mov     eax, ebx
0x180025d0b  cmp     rax, [rsi+8]
0x180025d0f  setnbe  al
0x180025d12  mov     rcx, [rbp+38h]; this
0x180025d16  lea     rdx, aSurfaceArrayIs; "Surface array is out of boundary"
0x180025d1d  mov     [rsp+70h+var_48], rdx; char *
0x180025d22  mov     [rsp+70h+var_50], al; char
0x180025d26  mov     r9d, 80070057h; char *
0x180025d2c  mov     r8, r13; unsigned int
0x180025d2f  mov     edx, 644h; void *
0x180025d34  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180025d39  lea     rbx, [rdi+130h]
0x180025d40  cmp     qword ptr [rbx], 0
0x180025d44  jnz     loc_180025E07
0x180025d4a  mov     [rbp+arg_0], 0
0x180025d52  mov     rcx, [rdi+138h]
0x180025d59  mov     rax, [rcx]
0x180025d5c  mov     [rbp+arg_0], 0
0x180025d64  xor     r8d, r8d
0x180025d67  lea     rdx, [rbp+arg_0]
0x180025d6b  mov     rax, [rax+38h]
0x180025d6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d74  mov     rcx, [rbp+38h]; this
0x180025d78  lea     rdx, aFailedToCreate_11; "Failed to create RAIL frame processor"
0x180025d7f  mov     qword ptr [rsp+70h+var_50], rdx; int
0x180025d84  mov     r9d, eax; char *
0x180025d87  mov     r8, r13; unsigned int
0x180025d8a  mov     edx, 650h; void *
0x180025d8f  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180025d94  lea     rdx, [rbp+arg_0]
0x180025d98  mov     rcx, rbx
0x180025d9b  call    ??$?4UICpuFrameProcessor@Avenc@Rdp@@Uerr_exception_policy@wil@@X@?$com_ptr_t@UIFrameProcessor@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@$$QEAV?$com_ptr_t@UICpuFrameProcessor@Avenc@Rdp@@Uerr_exception_policy@wil@@@1@@Z; wil::com_ptr_t<Rdp::Avenc::IFrameProcessor,wil::err_exception_policy>::operator=<Rdp::Avenc::ICpuFrameProcessor,wil::err_exception_policy,void>(wil::com_ptr_t<Rdp::Avenc::ICpuFrameProcessor,wil::err_exception_policy> &&)
0x180025da0  nop
0x180025da1  mov     rcx, [rbp+var_20]
0x180025da5  mov     [rbp+var_20], 0
0x180025dad  test    rcx, rcx
0x180025db0  jz      short loc_180025DBF
0x180025db2  mov     rax, [rcx]
0x180025db5  mov     rax, [rax+10h]
0x180025db9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025dbe  nop
0x180025dbf  lea     rdx, [rbp+var_20]
0x180025dc3  mov     rcx, rbx
0x180025dc6  call    ??$copy_to@UIUmrdpFrameProcessorRailPrivate@Umrdp@Avenc@Rdp@@@?$com_ptr_t@UIFrameProcessor@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEBAXPEAPEAUIUmrdpFrameProcessorRailPrivate@Umrdp@Avenc@Rdp@@@Z; wil::com_ptr_t<Rdp::Avenc::IFrameProcessor,wil::err_exception_policy>::copy_to<Rdp::Avenc::Umrdp::IUmrdpFrameProcessorRailPrivate>(Rdp::Avenc::Umrdp::IUmrdpFrameProcessorRailPrivate * *)
0x180025dcb  mov     rcx, [rbp+var_20]
0x180025dcf  mov     rax, [rcx]
0x180025dd2  mov     rax, [rax+18h]
0x180025dd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ddb  mov     rcx, [rbp+38h]; this
0x180025ddf  lea     rdx, aFailedToStartR; "Failed to start RAIL frame processor"
0x180025de6  mov     qword ptr [rsp+70h+var_50], rdx; int
0x180025deb  mov     r9d, eax; char *
0x180025dee  mov     r8, r13; unsigned int
0x180025df1  mov     edx, 659h; void *
0x180025df6  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180025dfb  nop
0x180025dfc  lea     rcx, [rbp+arg_0]
0x180025e00  call    ??1?$com_ptr_t@UIColorSpaceTransform@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(void)
0x180025e05  jmp     short loc_180025E31
0x180025e07  mov     rcx, [rbp+var_20]
0x180025e0b  mov     [rbp+var_20], 0
0x180025e13  test    rcx, rcx
0x180025e16  jz      short loc_180025E25
0x180025e18  mov     rax, [rcx]
0x180025e1b  mov     rax, [rax+10h]
0x180025e1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e24  nop
0x180025e25  lea     rdx, [rbp+var_20]
0x180025e29  mov     rcx, rbx
0x180025e2c  call    ??$copy_to@UIUmrdpFrameProcessorRailPrivate@Umrdp@Avenc@Rdp@@@?$com_ptr_t@UIFrameProcessor@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEBAXPEAPEAUIUmrdpFrameProcessorRailPrivate@Umrdp@Avenc@Rdp@@@Z; wil::com_ptr_t<Rdp::Avenc::IFrameProcessor,wil::err_exception_policy>::copy_to<Rdp::Avenc::Umrdp::IUmrdpFrameProcessorRailPrivate>(Rdp::Avenc::Umrdp::IUmrdpFrameProcessorRailPrivate * *)
0x180025e31  mov     rcx, [rbp+var_20]
0x180025e35  mov     rax, [rcx]
0x180025e38  mov     rdx, [rsi]
0x180025e3b  mov     qword ptr [rsp+70h+var_50], rdx
0x180025e40  mov     r9, [rsi+8]
0x180025e44  mov     r8d, r15d
0x180025e47  mov     edx, r14d
0x180025e4a  mov     rax, [rax+20h]
0x180025e4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e53  test    eax, eax
0x180025e55  jns     loc_180025F07
0x180025e5b  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x180025e60  mov     r8, [rax+8]
0x180025e64  mov     eax, [r8]
0x180025e67  cmp     eax, 2
0x180025e6a  jbe     short loc_180025EEB
0x180025e6c  mov     rax, [rdi+0E8h]
0x180025e73  mov     ecx, [rax+204h]
0x180025e79  mov     [rbp+arg_8], ecx
0x180025e7c  mov     eax, [rdi+118h]
0x180025e82  mov     dword ptr [rbp+arg_0], eax
0x180025e85  lea     rax, aFailedToUpdate; "Failed to update RAIL secure desktop"
0x180025e8c  mov     [rbp+var_18], rax
0x180025e90  lea     rax, aCrdpidmonitorP; "CRdpIdMonitor::ProcessMonitorSurfaceUpd"...
0x180025e97  mov     [rbp+var_10], rax
0x180025e9b  mov     [rbp+arg_18], 66Bh
0x180025ea2  mov     [rbp+var_8], r13
0x180025ea6  lea     rax, [rbp+arg_8]
0x180025eaa  mov     [rsp+70h+var_28], rax
0x180025eaf  lea     rax, [rbp+arg_0]
0x180025eb3  mov     [rsp+70h+var_30], rax
0x180025eb8  lea     rax, [rbp+var_18]
0x180025ebc  mov     [rsp+70h+var_38], rax
0x180025ec1  lea     rax, [rbp+var_10]
0x180025ec5  mov     [rsp+70h+var_40], rax
0x180025eca  lea     rax, [rbp+arg_18]
0x180025ece  mov     [rsp+70h+var_48], rax
0x180025ed3  lea     rax, [rbp+var_8]
0x180025ed7  mov     qword ptr [rsp+70h+var_50], rax
0x180025edc  lea     rdx, byte_18004E56B
0x180025ee3  mov     rcx, r8
0x180025ee6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180025eeb  mov     edx, 2
0x180025ef0  mov     r9d, 80004005h
0x180025ef6  lea     r8d, [rdx-1]
0x180025efa  mov     rcx, [rdi+0E8h]
0x180025f01  call    ?ReportCriticalError@CRdpIdAdapter@@QEAAXW4FailFastMajorCode@@IJ@Z; CRdpIdAdapter::ReportCriticalError(FailFastMajorCode,uint,long)
0x180025f06  nop
0x180025f07  lea     rcx, [rbp+var_20]
0x180025f0b  call    ??1?$com_ptr_t@UIColorSpaceTransform@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(void)
0x180025f10  add     rsp, 70h
0x180025f14  pop     r15
0x180025f16  pop     r14
0x180025f18  pop     r13
0x180025f1a  pop     rdi
0x180025f1b  pop     rsi
0x180025f1c  pop     rbx
0x180025f1d  pop     rbp
0x180025f1e  retn
```
