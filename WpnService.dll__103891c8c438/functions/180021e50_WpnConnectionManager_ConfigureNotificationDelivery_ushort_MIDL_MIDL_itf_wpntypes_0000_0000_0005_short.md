# WpnConnectionManager::ConfigureNotificationDelivery(ushort *,__MIDL___MIDL_itf_wpntypes_0000_0000_0005,short)

- ea: `0x180021e50`
- end: `0x180021fa6`
- name: `?ConfigureNotificationDelivery@WpnConnectionManager@@UEAAJPEAGW4__MIDL___MIDL_itf_wpntypes_0000_0000_0005@@F@Z`
- size: `342`
- prototype: `__int64 __fastcall(WpnConnectionManager *, const unsigned __int16 *, unsigned int, __int16)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config`

## callees

- `0x180007e20`
- `0x18000a2a0`
- `0x18000a980`
- `0x18000abc0`
- `0x1800202bc`
- `0x180021048`
- `0x180021e50`
- `0x180021fac`
- `0x1800220e0`
- `0x180026200`
- `0x18002e7e0`

## string_xrefs

- `0x180021e7e`: `WnsCMConfigureNotificationDelivery`

## pseudocode

```c
__int64 __fastcall WpnConnectionManager::ConfigureNotificationDelivery(
        WpnConnectionManager *a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        __int16 a4)
{
  __int16 v8; // r9
  __int64 v9; // rdx
  int v11; // eax
  struct _RTL_CRITICAL_SECTION *v12; // rdi
  __int64 v13; // rbx
  const char *v14; // r9
  int v15; // [rsp+20h] [rbp-1A8h]
  unsigned int v16; // [rsp+30h] [rbp-198h]
  _QWORD v17[42]; // [rsp+40h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+0h]

  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v17,
    "WnsCMConfigureNotificationDelivery");
  v17[0] = &WnsCPLog::WnsCMConfigureNotificationDelivery::`vftable';
  WnsCPLog::WnsCMConfigureNotificationDelivery::StartActivity(
    (WnsCPLog::WnsCMConfigureNotificationDelivery *)v17,
    *((_QWORD *)a1 + 4),
    a2,
    a3,
    v8);
  if ( !a2 )
  {
    v9 = 202;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\mux\\wpnconnectionmanager.cpp",
      (const char *)0x80070057LL,
      v15);
    WnsCPLog::WnsCMConfigureNotificationDelivery::~WnsCMConfigureNotificationDelivery((WnsCPLog::WnsCMConfigureNotificationDelivery *)v17);
    return 2147942487LL;
  }
  if ( a3 - 1 > 4 )
  {
    v9 = 203;
    goto LABEL_3;
  }
  if ( (unsigned __int16)(a4 + 1) > 1u )
  {
    v9 = 204;
    goto LABEL_3;
  }
  try
  {
    v11 = WpnConnectionManager::VerifyCallerUserId(a1);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD0,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\mux\\wpnconnectionmanager.cpp",
        (const char *)(unsigned int)v11,
        v15);
    v12 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)a1 + 3);
    v13 = *((_QWORD *)a1 + 6);
    Wns::ConnectionStateMachine::VerifyConnected(v12 + 1);
    LOWORD(v15) = a4;
    Wns::CPTransactionRequestManager::ConfigureNotificationDelivery(&v12[2].LockSemaphore, v13, a2, a3, v15);
    wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v17, 0);
  }
  catch ( ... )
  {
    v16 = wil::details::in1diag3::Return_CaughtException(
            retaddr,
            (void *)0xD6,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\mux\\wpnconnectionmanager.cpp",
            v14);
    WnsCPLog::WnsCMConfigureNotificationDelivery::~WnsCMConfigureNotificationDelivery((WnsCPLog::WnsCMConfigureNotificationDelivery *)v17);
    return v16;
  }
  WnsCPLog::WnsCMConfigureNotificationDelivery::~WnsCMConfigureNotificationDelivery((WnsCPLog::WnsCMConfigureNotificationDelivery *)v17);
  return 0;
}

```

## disassembly

```asm
0x180021e50  push    rbx
0x180021e52  push    rsi
0x180021e53  push    rdi
0x180021e54  push    r14
0x180021e56  push    r15
0x180021e58  sub     rsp, 1A0h
0x180021e5f  mov     rax, cs:__security_cookie
0x180021e66  xor     rax, rsp
0x180021e69  mov     [rsp+1C8h+var_38], rax
0x180021e71  movzx   esi, r9w
0x180021e75  mov     r14d, r8d
0x180021e78  mov     r15, rdx
0x180021e7b  mov     rbx, rcx
0x180021e7e  lea     rdx, aWnscmconfigure_0; "WnsCMConfigureNotificationDelivery"
0x180021e85  lea     rcx, [rsp+1C8h+var_188]
0x180021e8a  call    ??0?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180021e8f  lea     rcx, ??_7WnsCMConfigureNotificationDelivery@WnsCPLog@@6B@; const WnsCPLog::WnsCMConfigureNotificationDelivery::`vftable'
0x180021e96  mov     [rsp+1C8h+var_188], rcx
0x180021e9b  mov     word ptr [rsp+1C8h+var_1A8], r9w; int
0x180021ea1  mov     r9d, r14d; unsigned int
0x180021ea4  mov     r8, r15; unsigned __int16 *
0x180021ea7  mov     rdx, [rbx+20h]; unsigned __int64
0x180021eab  lea     rcx, [rsp+1C8h+var_188]; this
0x180021eb0  call    ?StartActivity@WnsCMConfigureNotificationDelivery@WnsCPLog@@QEAAX_KPEBGIF@Z; WnsCPLog::WnsCMConfigureNotificationDelivery::StartActivity(unsigned __int64,ushort const *,uint,short)
0x180021eb5  nop
0x180021eb6  test    r15, r15
0x180021eb9  jnz     short loc_180021EEE
0x180021ebb  mov     edx, 0CAh; void *
0x180021ec0  mov     ebx, 80070057h
0x180021ec5  mov     rcx, [rsp+1C8h]; this
0x180021ecd  mov     r9d, ebx; char *
0x180021ed0  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180021ed7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021edc  nop
0x180021edd  lea     rcx, [rsp+1C8h+var_188]; this
0x180021ee2  call    ??1WnsCMConfigureNotificationDelivery@WnsCPLog@@QEAA@XZ; WnsCPLog::WnsCMConfigureNotificationDelivery::~WnsCMConfigureNotificationDelivery(void)
0x180021ee7  mov     eax, ebx
0x180021ee9  jmp     loc_180021F87
0x180021eee  lea     eax, [r14-1]
0x180021ef2  cmp     eax, 4
0x180021ef5  jbe     short loc_180021EFE
0x180021ef7  mov     edx, 0CBh
0x180021efc  jmp     short loc_180021EC0
0x180021efe  lea     eax, [rsi+1]
0x180021f01  cmp     ax, 1
0x180021f05  jbe     short loc_180021F0E
0x180021f07  mov     edx, 0CCh
0x180021f0c  jmp     short loc_180021EC0
0x180021f0e  mov     rcx, rbx; this
0x180021f11  call    ?VerifyCallerUserId@WpnConnectionManager@@AEAAJXZ; WpnConnectionManager::VerifyCallerUserId(void)
0x180021f16  mov     rcx, [rsp+1C8h]; this
0x180021f1e  test    eax, eax
0x180021f20  jns     short loc_180021F36
0x180021f22  mov     r9d, eax; char *
0x180021f25  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180021f2c  mov     edx, 0D0h; void *
0x180021f31  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180021f36  mov     rdi, [rbx+18h]
0x180021f3a  mov     rbx, [rbx+30h]
0x180021f3e  lea     rcx, [rdi+28h]; lpCriticalSection
0x180021f42  call    ?VerifyConnected@ConnectionStateMachine@Wns@@AEAAXXZ; Wns::ConnectionStateMachine::VerifyConnected(void)
0x180021f47  lea     rcx, [rdi+68h]
0x180021f4b  mov     word ptr [rsp+1C8h+var_1A8], si
0x180021f50  mov     r9d, r14d
0x180021f53  mov     r8, r15
0x180021f56  mov     rdx, rbx
0x180021f59  call    ?ConfigureNotificationDelivery@CPTransactionRequestManager@Wns@@QEAAX_KPEBGW4__MIDL___MIDL_itf_wpntypes_0000_0000_0005@@F@Z; Wns::CPTransactionRequestManager::ConfigureNotificationDelivery(unsigned __int64,ushort const *,__MIDL___MIDL_itf_wpntypes_0000_0000_0005,short)
0x180021f5e  xor     edx, edx
0x180021f60  lea     rcx, [rsp+1C8h+var_188]
0x180021f65  call    ?Stop@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180021f6a  nop
0x180021f6b  lea     rcx, [rsp+1C8h+var_188]; this
0x180021f70  call    ??1WnsCMConfigureNotificationDelivery@WnsCPLog@@QEAA@XZ; WnsCPLog::WnsCMConfigureNotificationDelivery::~WnsCMConfigureNotificationDelivery(void)
0x180021f75  xor     eax, eax
0x180021f77  jmp     short loc_180021F87
0x180021f79  lea     rcx, [rsp+1C8h+var_188]; this
0x180021f7e  call    ??1WnsCMConfigureNotificationDelivery@WnsCPLog@@QEAA@XZ; WnsCPLog::WnsCMConfigureNotificationDelivery::~WnsCMConfigureNotificationDelivery(void)
0x180021f83  mov     eax, [rsp+1C8h+var_198]
0x180021f87  mov     rcx, [rsp+1C8h+var_38]
0x180021f8f  xor     rcx, rsp; StackCookie
0x180021f92  call    __security_check_cookie
0x180021f97  add     rsp, 1A0h
0x180021f9e  pop     r15
0x180021fa0  pop     r14
0x180021fa2  pop     rdi
0x180021fa3  pop     rsi
0x180021fa4  pop     rbx
0x180021fa5  retn
```
