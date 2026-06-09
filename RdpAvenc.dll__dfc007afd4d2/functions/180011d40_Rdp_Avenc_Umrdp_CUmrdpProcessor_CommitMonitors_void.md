# Rdp::Avenc::Umrdp::CUmrdpProcessor::CommitMonitors(void)

- ea: `0x180011d40`
- end: `0x180011ec6`
- name: `?CommitMonitors@CUmrdpProcessor@Umrdp@Avenc@Rdp@@UEAAJXZ`
- size: `390`
- prototype: `__int64 __fastcall(Rdp::Avenc::Umrdp::CUmrdpProcessor *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180011d40`
- `0x1800146bc`
- `0x180015480`
- `0x18001709c`
- `0x180019c10`
- `0x180019df0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011da7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011e67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011da7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011e67`

## pseudocode

```c
__int64 __fastcall Rdp::Avenc::Umrdp::CUmrdpProcessor::CommitMonitors(Rdp::Avenc::Umrdp::CUmrdpProcessor *this)
{
  char v2; // di
  bool v3; // bl
  bool v4; // r14
  char CurrentThreadId; // al
  int v6; // r8d
  int v7; // edx
  __int64 v8; // rbx
  bool v9; // si
  char v10; // al
  int v11; // r8d
  int v12; // edx
  const char *v13; // r9
  __int64 result; // rax
  int v15; // [rsp+20h] [rbp-58h]
  int v16; // [rsp+20h] [rbp-58h]
  int v17; // [rsp+28h] [rbp-50h]
  int v18; // [rsp+28h] [rbp-50h]
  char *v19; // [rsp+30h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v2 = 1;
  v3 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v4 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v6) = v4;
    LOBYTE(v7) = v3;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      v6,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v15,
      v17,
      18,
      &WPP_44e245a864023212cc554d824265b257_Traceguids,
      CurrentThreadId);
  }
  try
  {
    LOBYTE(v15) = *((_BYTE *)this + 16) == 0;
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x152,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\umrdpprocessor.cpp",
      (const char *)0x8000FFFFLL,
      v15,
      (bool)"Processor is not started",
      v19);
    v8 = *((_QWORD *)this + 7);
    Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::lock(v8, 1500);
    Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::SendMonitorLayoutUpdate<std::map<Rdp::Avenc::IMonitorContext *,wil::com_ptr_t<Rdp::Avenc::Umrdp::CMonitorContext,wil::err_exception_policy>>>(
      *((_QWORD *)this + 7),
      (__int64 **)this + 5);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v2 = 0;
    }
    v9 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v10 = GetCurrentThreadId();
      LOBYTE(v11) = v9;
      LOBYTE(v12) = v2;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v12,
        v11,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v16,
        v18,
        19,
        &WPP_44e245a864023212cc554d824265b257_Traceguids,
        v10);
    }
    Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::unlock(v8);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x15E,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\umrdpprocessor.cpp",
                           v13);
  }
  return result;
}

```

## disassembly

```asm
0x180011d40  mov     [rsp+arg_8], rbx
0x180011d45  mov     [rsp+arg_10], rsi
0x180011d4a  push    rdi
0x180011d4b  push    r12
0x180011d4d  push    r13
0x180011d4f  push    r14
0x180011d51  push    r15
0x180011d53  sub     rsp, 50h
0x180011d57  mov     rsi, rcx
0x180011d5a  lea     r12, WPP_GLOBAL_Control
0x180011d61  mov     rax, cs:WPP_GLOBAL_Control
0x180011d68  mov     dil, 1
0x180011d6b  cmp     rax, r12
0x180011d6e  jz      short loc_180011D81
0x180011d70  test    [rax+1Ch], dil
0x180011d74  jz      short loc_180011D81
0x180011d76  cmp     byte ptr [rax+19h], 4
0x180011d7a  jb      short loc_180011D81
0x180011d7c  mov     bl, dil
0x180011d7f  jmp     short loc_180011D83
0x180011d81  xor     bl, bl
0x180011d83  lea     r13, WPP_RECORDER_INITIALIZED
0x180011d8a  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180011d91  setnz   r14b
0x180011d95  test    bl, bl
0x180011d97  jnz     short loc_180011DA7
0x180011d99  test    r14b, r14b
0x180011d9c  jnz     short loc_180011DA7
0x180011d9e  lea     r15, WPP_44e245a864023212cc554d824265b257_Traceguids
0x180011da5  jmp     short loc_180011DDD
0x180011da7  call    cs:__imp_GetCurrentThreadId
0x180011dad  mov     dword ptr [rsp+78h+var_38], eax; char
0x180011db1  lea     r15, WPP_44e245a864023212cc554d824265b257_Traceguids
0x180011db8  mov     [rsp+78h+MessageGuid], r15; MessageGuid
0x180011dbd  mov     word ptr [rsp+78h+var_48], 12h; char *
0x180011dc4  mov     rcx, cs:WPP_GLOBAL_Control
0x180011dcb  mov     r9, [rcx+28h]; int
0x180011dcf  mov     r8b, r14b; int
0x180011dd2  mov     dl, bl; int
0x180011dd4  mov     rcx, [rcx+10h]; int
0x180011dd8  call    WPP_RECORDER_AND_TRACE_SF_D
0x180011ddd  cmp     byte ptr [rsi+10h], 0
0x180011de1  setz    al
0x180011de4  mov     rcx, [rsp+78h]; this
0x180011de9  lea     rdx, aProcessorIsNot; "Processor is not started"
0x180011df0  mov     qword ptr [rsp+78h+var_50], rdx; int
0x180011df5  mov     byte ptr [rsp+78h+var_58], al; int
0x180011df9  mov     r9d, 8000FFFFh; char *
0x180011dff  lea     r8, aOnecoreuapTerm_58; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180011e06  mov     edx, 152h; void *
0x180011e0b  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180011e10  mov     rbx, [rsi+38h]
0x180011e14  mov     [rsp+78h+arg_0], rbx
0x180011e1c  mov     edx, 5DCh
0x180011e21  mov     rcx, rbx
0x180011e24  call    ?lock@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@QEAAXI@Z; Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::lock(uint)
0x180011e29  nop
0x180011e2a  lea     rdx, [rsi+28h]
0x180011e2e  mov     rcx, [rsi+38h]
0x180011e32  call    ??$SendMonitorLayoutUpdate@V?$map@PEAUIMonitorContext@Avenc@Rdp@@V?$com_ptr_t@VCMonitorContext@Umrdp@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@U?$less@PEAUIMonitorContext@Avenc@Rdp@@@std@@V?$allocator@U?$pair@QEAUIMonitorContext@Avenc@Rdp@@V?$com_ptr_t@VCMonitorContext@Umrdp@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@7@@std@@@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@QEAAXAEBV?$map@PEAUIMonitorContext@Avenc@Rdp@@V?$com_ptr_t@VCMonitorContext@Umrdp@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@U?$less@PEAUIMonitorContext@Avenc@Rdp@@@std@@V?$allocator@U?$pair@QEAUIMonitorContext@Avenc@Rdp@@V?$com_ptr_t@VCMonitorContext@Umrdp@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@7@@std@@@Z; Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::SendMonitorLayoutUpdate<std::map<Rdp::Avenc::IMonitorContext *,wil::com_ptr_t<Rdp::Avenc::Umrdp::CMonitorContext,wil::err_exception_policy>>>(std::map<Rdp::Avenc::IMonitorContext *,wil::com_ptr_t<Rdp::Avenc::Umrdp::CMonitorContext,wil::err_exception_policy>> const &)
0x180011e37  mov     rax, cs:WPP_GLOBAL_Control
0x180011e3e  cmp     rax, r12
0x180011e41  jz      short loc_180011E4F
0x180011e43  test    [rax+1Ch], dil
0x180011e47  jz      short loc_180011E4F
0x180011e49  cmp     byte ptr [rax+19h], 4
0x180011e4d  jnb     short loc_180011E52
0x180011e4f  xor     dil, dil
0x180011e52  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180011e59  setnz   sil
0x180011e5d  test    dil, dil
0x180011e60  jnz     short loc_180011E67
0x180011e62  test    sil, sil
0x180011e65  jz      short loc_180011E98
0x180011e67  call    cs:__imp_GetCurrentThreadId
0x180011e6d  mov     dword ptr [rsp+78h+var_38], eax; char
0x180011e71  mov     [rsp+78h+MessageGuid], r15; MessageGuid
0x180011e76  mov     word ptr [rsp+78h+var_48], 13h; __int16
0x180011e7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180011e84  mov     r9, [rcx+28h]; int
0x180011e88  mov     r8b, sil; int
0x180011e8b  mov     dl, dil; int
0x180011e8e  mov     rcx, [rcx+10h]; int
0x180011e92  call    WPP_RECORDER_AND_TRACE_SF_D
0x180011e97  nop
0x180011e98  mov     rcx, rbx
0x180011e9b  call    ?unlock@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@QEAAXXZ; Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::unlock(void)
0x180011ea0  xor     eax, eax
0x180011ea2  jmp     short loc_180011EAB
0x180011ea4  mov     eax, dword ptr [rsp+78h+arg_0]
0x180011eab  lea     r11, [rsp+78h+var_28]
0x180011eb0  mov     rbx, [r11+38h]
0x180011eb4  mov     rsi, [r11+40h]
0x180011eb8  mov     rsp, r11
0x180011ebb  pop     r15
0x180011ebd  pop     r14
0x180011ebf  pop     r13
0x180011ec1  pop     r12
0x180011ec3  pop     rdi
0x180011ec4  retn
```
