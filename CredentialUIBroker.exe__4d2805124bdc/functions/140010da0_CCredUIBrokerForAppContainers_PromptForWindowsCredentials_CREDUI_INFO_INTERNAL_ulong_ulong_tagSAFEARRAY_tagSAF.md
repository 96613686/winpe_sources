# CCredUIBrokerForAppContainers::PromptForWindowsCredentials(CREDUI_INFO_INTERNAL *,ulong,ulong *,tagSAFEARRAY *,tagSAFEARRAY * *,int *,ulong,ulong *)

- ea: `0x140010da0`
- end: `0x140010eff`
- name: `?PromptForWindowsCredentials@CCredUIBrokerForAppContainers@@UEAAJPEAUCREDUI_INFO_INTERNAL@@KPEAKPEAUtagSAFEARRAY@@PEAPEAU3@PEAHK1@Z`
- size: `351`
- prototype: `__int64 __fastcall(struct IUnknown *this, struct CREDUI_INFO_INTERNAL *, unsigned int, unsigned int *, struct tagSAFEARRAY *psa, struct tagSAFEARRAY **cElements, int *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x140003620`
- `0x140007b20`
- `0x140009254`
- `0x14000c8b0`
- `0x14000f14c`
- `0x140010da0`
- `0x140014684`
- `0x140014bb0`
- `0x140017fc0`
- `0x140018cf8`

## string_xrefs

- `0x140010dd9`: `BrokerForAppContainersActivity`

## pseudocode

```c
__int64 __fastcall CCredUIBrokerForAppContainers::PromptForWindowsCredentials(
        struct IUnknown *this,
        struct CREDUI_INFO_INTERNAL *a2,
        unsigned int a3,
        unsigned int *a4,
        struct tagSAFEARRAY *psa,
        struct tagSAFEARRAY **cElements,
        int *a7,
        unsigned int a8,
        unsigned int *a9)
{
  CCredUIBrokerForAppContainers *v12; // rcx
  unsigned int v13; // edi
  HWND v14; // rdx
  unsigned int BufferSize; // ebx
  unsigned int v16; // eax
  _QWORD v19[42]; // [rsp+60h] [rbp-1A8h] BYREF

  wil::ActivityBase<CredUIBrokerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CredUIBrokerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v19);
  v19[0] = &CredUIBrokerTelemetry::BrokerForAppContainersActivity::`vftable';
  CredUIBrokerTelemetry::BrokerForAppContainersActivity::StartActivity((CredUIBrokerTelemetry::BrokerForAppContainersActivity *)v19);
  LogOwnerWindowTelemetry(a2);
  *cElements = 0;
  if ( !a2
    || (v13 = -2147024809, *(_DWORD *)a2 == 136)
    && !*((_QWORD *)a2 + 12)
    && ((v14 = (HWND)*((_QWORD *)a2 + 1)) == 0
     || CCredUIBrokerForAppContainers::_VerifyWindowIsInCallingProcessOrParentAppContainer(v12, v14) >= 0) )
  {
    v13 = CCredUIBrokerBase::_PromptForWindowsCredentials(
            (CCredUIBrokerBase *)&this[2],
            this,
            a2,
            a3,
            a4,
            psa,
            (ULONG)cElements,
            a7,
            a8,
            a9);
  }
  BufferSize = GetBufferSize(psa);
  v16 = GetBufferSize(*cElements);
  CredUIBrokerTelemetry::BrokerForAppContainersActivity::Stop(
    (CredUIBrokerTelemetry::BrokerForAppContainersActivity *)v19,
    v13,
    a8,
    *a4,
    *a9,
    BufferSize,
    v16);
  CredUIBrokerTelemetry::BrokerForAppContainersActivity::~BrokerForAppContainersActivity((CredUIBrokerTelemetry::BrokerForAppContainersActivity *)v19);
  return v13;
}

```

## disassembly

```asm
0x140010da0  push    rbx
0x140010da2  push    rbp
0x140010da3  push    rsi
0x140010da4  push    rdi
0x140010da5  push    r12
0x140010da7  push    r13
0x140010da9  push    r14
0x140010dab  push    r15
0x140010dad  sub     rsp, 1C8h
0x140010db4  mov     rax, cs:__security_cookie
0x140010dbb  xor     rax, rsp
0x140010dbe  mov     [rsp+208h+var_58], rax
0x140010dc6  mov     rax, [rsp+208h+arg_30]
0x140010dce  mov     rbx, rdx
0x140010dd1  mov     r15, [rsp+208h+psa]
0x140010dd9  lea     rdx, aBrokerforappco; "BrokerForAppContainersActivity"
0x140010de0  mov     rsi, [rsp+208h+arg_28]
0x140010de8  mov     rbp, rcx
0x140010deb  mov     r12, [rsp+208h+arg_40]
0x140010df3  lea     rcx, [rsp+208h+var_1A8]; struct wil::details::IFailureCallback *
0x140010df8  mov     [rsp+208h+var_1B0], rax
0x140010dfd  mov     r14, r9
0x140010e00  mov     [rsp+208h+var_1B8], r8d
0x140010e05  call    ??0?$ActivityBase@VCredUIBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CredUIBrokerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CredUIBrokerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140010e0a  lea     rax, ??_7BrokerForAppContainersActivity@CredUIBrokerTelemetry@@6B@; const CredUIBrokerTelemetry::BrokerForAppContainersActivity::`vftable'
0x140010e11  lea     rcx, [rsp+208h+var_1A8]; this
0x140010e16  mov     [rsp+208h+var_1A8], rax
0x140010e1b  call    ?StartActivity@BrokerForAppContainersActivity@CredUIBrokerTelemetry@@QEAAXXZ; CredUIBrokerTelemetry::BrokerForAppContainersActivity::StartActivity(void)
0x140010e20  mov     rcx, rbx; struct CREDUI_INFO_INTERNAL *
0x140010e23  call    ?LogOwnerWindowTelemetry@@YAXPEAUCREDUI_INFO_INTERNAL@@@Z; LogOwnerWindowTelemetry(CREDUI_INFO_INTERNAL *)
0x140010e28  mov     r13d, [rsp+208h+arg_38]
0x140010e30  mov     qword ptr [rsi], 0
0x140010e37  test    rbx, rbx
0x140010e3a  jz      short loc_140010E62
0x140010e3c  cmp     dword ptr [rbx], 88h
0x140010e42  mov     edi, 80070057h
0x140010e47  jnz     short loc_140010E9B
0x140010e49  cmp     qword ptr [rbx+60h], 0
0x140010e4e  jnz     short loc_140010E9B
0x140010e50  mov     rdx, [rbx+8]; HWND
0x140010e54  test    rdx, rdx
0x140010e57  jz      short loc_140010E62
0x140010e59  call    ?_VerifyWindowIsInCallingProcessOrParentAppContainer@CCredUIBrokerForAppContainers@@AEAAJPEAUHWND__@@@Z; CCredUIBrokerForAppContainers::_VerifyWindowIsInCallingProcessOrParentAppContainer(HWND__ *)
0x140010e5e  test    eax, eax
0x140010e60  js      short loc_140010E9B
0x140010e62  mov     rax, [rsp+208h+var_1B0]
0x140010e67  lea     rcx, [rbp+10h]; this
0x140010e6b  mov     r9d, [rsp+208h+var_1B8]; unsigned int
0x140010e70  mov     r8, rbx; struct CREDUI_INFO_INTERNAL *
0x140010e73  mov     [rsp+208h+var_1C0], r12; unsigned int *
0x140010e78  mov     rdx, rbp; struct IUnknown *
0x140010e7b  mov     [rsp+208h+var_1C8], r13d; unsigned int
0x140010e80  mov     [rsp+208h+var_1D0], rax; int *
0x140010e85  mov     qword ptr [rsp+208h+cElements], rsi; cElements
0x140010e8a  mov     [rsp+208h+var_1E0], r15; psa
0x140010e8f  mov     [rsp+208h+var_1E8], r14; unsigned int *
0x140010e94  call    ?_PromptForWindowsCredentials@CCredUIBrokerBase@@IEAAJPEAUIUnknown@@PEAUCREDUI_INFO_INTERNAL@@KPEAKPEAUtagSAFEARRAY@@PEAPEAU4@PEAHK2@Z; CCredUIBrokerBase::_PromptForWindowsCredentials(IUnknown *,CREDUI_INFO_INTERNAL *,ulong,ulong *,tagSAFEARRAY *,tagSAFEARRAY * *,int *,ulong,ulong *)
0x140010e99  mov     edi, eax
0x140010e9b  mov     rcx, r15; psa
0x140010e9e  call    ?GetBufferSize@@YAKPEAUtagSAFEARRAY@@@Z; GetBufferSize(tagSAFEARRAY *)
0x140010ea3  mov     rcx, [rsi]; psa
0x140010ea6  mov     ebx, eax
0x140010ea8  call    ?GetBufferSize@@YAKPEAUtagSAFEARRAY@@@Z; GetBufferSize(tagSAFEARRAY *)
0x140010ead  mov     ecx, [r12]
0x140010eb1  mov     r8d, r13d; unsigned int
0x140010eb4  mov     r9d, [r14]; unsigned int
0x140010eb7  mov     edx, edi; int
0x140010eb9  mov     [rsp+208h+cElements], eax; unsigned int
0x140010ebd  mov     dword ptr [rsp+208h+var_1E0], ebx; unsigned int
0x140010ec1  mov     dword ptr [rsp+208h+var_1E8], ecx; unsigned int
0x140010ec5  lea     rcx, [rsp+208h+var_1A8]; this
0x140010eca  call    ?Stop@BrokerForAppContainersActivity@CredUIBrokerTelemetry@@QEAAXJKKKKK@Z; CredUIBrokerTelemetry::BrokerForAppContainersActivity::Stop(long,ulong,ulong,ulong,ulong,ulong)
0x140010ecf  lea     rcx, [rsp+208h+var_1A8]; this
0x140010ed4  call    ??1BrokerForAppContainersActivity@CredUIBrokerTelemetry@@QEAA@XZ; CredUIBrokerTelemetry::BrokerForAppContainersActivity::~BrokerForAppContainersActivity(void)
0x140010ed9  mov     eax, edi
0x140010edb  mov     rcx, [rsp+208h+var_58]
0x140010ee3  xor     rcx, rsp; StackCookie
0x140010ee6  call    __security_check_cookie
0x140010eeb  add     rsp, 1C8h
0x140010ef2  pop     r15
0x140010ef4  pop     r14
0x140010ef6  pop     r13
0x140010ef8  pop     r12
0x140010efa  pop     rdi
0x140010efb  pop     rsi
0x140010efc  pop     rbp
0x140010efd  pop     rbx
0x140010efe  retn
```
